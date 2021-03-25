---
title: Bereitstellen der Medienumgehung in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: In diesem Thema erfahren Sie mehr über die Schritte zum Bereitstellen der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher.
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119364"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Bereitstellen der Medienumgehung in Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

In diesem Thema erfahren Sie mehr über die Schritte zum Bereitstellen der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher. 
  
Mit der Medienumgehung kann ein Client Medien direkt an das Public Switched Telephone Network (PSTN) des nächsten Hops senden – ein Gateway oder einen Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen. Siehe auch [Planen der Medienumgehung in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Medienumgehung aktivieren

Zum Aktivieren der Medienumgehung müssen Sie den DNS-Namen des Medienumgehungswebdiensts konfigurieren und die Medienumgehung in der Mandantenkonfiguration aktivieren. Der Webdienst für die Medienumgehung wird automatisch auf jedem Vermittlungsserver bereitgestellt. Ein Mandantenadministrator muss einen Namen für einen Hybrid-Voicedienst (Standort) auswählen, und dieser Name sollte aus einer für Hybridstimme registrierten SIP-Domäne sein. Der Dienstname sollte unabhängig vom Clientspeicherort für alle Cloud Connector-Appliances und alle PSTN-Standorte identisch sein. Der Webdienst sollte nur intern im Netzwerk verfügbar sein.
  
Ein Mandantenadministrator muss einen DNS-A-Eintrag im internen Active Directory für die Produktionsumgebung konfigurieren. Wenn Sie über eine komplexe Umgebung mit mehreren Websites verfügen, lesen Sie das Beispiel in [Beispiel: Medienumgehung von Website-DNS-Einträgen in](deploy-media-bypass-in-cloud-connector.md#Example)komplexen Umgebungen mit mehreren Websites. Der #A0 sollte nur für interne Netzwerkclients aufgelöst werden. Es sollte nicht für externe Netzwerkclients aufgelöst werden.
  
Stellen Sie nach der Konfiguration von DNS eine Verbindung mit Skype for Business Online mithilfe von Remote-PowerShell mit Skype for Business-Administratoranmeldeinformationen auf. Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die Medienumgehung zu aktivieren:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Das Aktivieren der Medienumgehung ist ein Zwei-Schritt-Prozess. Das New-CsNetworkMedia-Cmdlet speichern die neue Konfiguration nicht sofort. Es werden nur die Einstellungen im Arbeitsspeicher erstellt. Das von diesem Cmdlet erstellte Objekt muss in einer Variablen gespeichert und dann der MediaBypassSettings-Eigenschaft der Netzwerkkonfiguration zugewiesen werden. Weitere Informationen finden Sie unter [Beispiel: Medienumgehung von Website-DNS-Einträgen in komplexen Umgebungen mit mehreren Websites.](deploy-media-bypass-in-cloud-connector.md#Example)
  
Die Replikation zwischen der lokalen und der Onlinekomponenten kann bis zu 24 Stunden dauern. Daher empfiehlt Microsoft, die erforderlichen Befehle auszuführen, bevor Sie Benutzer aktivieren.
  
## <a name="confirm-media-bypass-settings"></a>Bestätigen von Einstellungen für die Medienumgehung

Sie können die Einstellungen für die Medienumgehung wie folgt überprüfen. 
  
Führen Sie den folgenden Befehl in remote PowerShell aus, um die Onlinereplikation in Ihrem Mandantenpool zu überprüfen:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Stellen Sie zum Überprüfen der lokalen Replikation eine Verbindung mit den Cloud Connector-Vermittlungsservern her, führen Sie den folgenden Befehl in PowerShell aus, und vergewissern Sie sich, dass Enabled=True und AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Um die Clienteinstellungen zu überprüfen, melden Sie sich beim Skype for Business-Client ab, melden Sie sich wieder an, und bestätigen Sie, dass der Client die Dienst-URL wie folgt erhalten hat:
  
1. Öffnen Sie %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Suchen Sie nach hybridconfigserviceinternalurl, und vergewissern Sie sich, dass die URL der von Ihnen definierten entspricht.
    
## <a name="change-media-bypass-parameters"></a>Ändern von Medienumgehungsparametern

Mandantenadministratoren können den DNS-Namen des Webdiensts ändern, indem sie das folgende Cmdlet ausführen:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Clients müssen sich abmelden und sich anmelden, um den neuen Dienstnamen zu erhalten und die Änderung zu erkennen. 
  
## <a name="temporarily-disable-media-bypass"></a>Vorübergehendes Deaktivieren der Medienumgehung

Dieses Szenario kann für die Problembehandlung oder Wartung hilfreich sein. Führen Sie die folgenden Cmdlets aus, um den Dienst zu deaktivieren:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Nach der Änderung kann es einige Zeit dauern, bis Die Änderungen auf alle Cloud Connectors repliziert wurden. Führen Sie zum Überprüfen des Replikationsstatus das folgende Cmdlet in PowerShell auf Cloud Connector-Vermittlungsservern aus: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Nachdem die Änderungen repliziert wurden, beginnt der Webdienst auf dem Vermittlungsserver, Clientanforderungen für den Medienumgehungsdienst abzulehnen.
  
## <a name="disable-media-bypass-permanently"></a>Medienumgehung dauerhaft deaktivieren

Um die Medienumgehung dauerhaft zu deaktivieren, muss ein Mandantenadministrator die folgenden Befehle ausführen: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Ein Administrator muss außerdem die Webadressen für die Medienumgehung von internen DNS-Servern entfernen. Nach der Änderung kann es einige Zeit dauern, bis Änderungen auf alle Cloud Connector-Appliances repliziert wurden. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Beispiel: DNS-Einträge der Website für die Medienumgehung in komplexen Umgebungen mit mehreren Websites
<a name="Example"> </a>

Clients erhalten die Webadresse des Medienumgehungswebdiensts von einem internen DNS-Server. Der Name des Webdiensts ist für alle Cloud Connector-Appliances und Cloud Connector-PSTN-Standorte identisch. In einer komplexen Umgebung mit mehreren Websites wird die Verwendung der Windows 2016-DNS-Richtlinie für Geo-Location Based Traffic Management empfohlen, damit Clients an den Webdienst umgeleitet werden können, der für ihr Netzwerk lokal ist. 
  
Weitere Informationen zu Windows 2016-DNS-Richtlinien finden Sie unter [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).
  
Im Folgenden finden Sie ein Beispiel für die Konfiguration für ein Unternehmen mit mehreren Websites, die windows 2016-DNS-Richtlinie für die Geo-Location Datenverkehrsverwaltung verwenden.
  
Der Name für den Umgehungsdienst ist "hybridvoice.adatum.biz".
  
Der Standort in Amsterdam verfügt über vier Cloud Connector-Appliances, die mit den folgenden Vermittlungsserver-IP-Adressen bereitgestellt werden:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Der Standort in Seattle verfügt über drei Cloud Connector-Appliances, die mit den folgenden Vermittlungsserver-IP-Adressen bereitgestellt werden:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Mithilfe Geo-Location basierten Datenverkehrsverwaltung werden die DNS-Server wie folgt konfiguriert:
  
1. Erstellen Sie DNS-Clientsubnetze für die Subnetze Amsterdam und Seattle.
    
2. Erstellen Sie DNS-Zonenbereiche für adatum.biz für Amsterdam und Seattle.
    
3. Erstellen Sie DNS-Einträge in jedem DNS-Zonenbereich.
    
    Amsterdam
    
   - Typ A;
    
   - Name : hybridvoice in der adatum.biz-DNS-Zone
    
   - Ziel: 192.168.1.45
    
     Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Typ A
    
   - Name : hybridvoice in adatum.biz-DNS-Zone
    
   - Ziel: 10.10.1.8
    
     Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Erstellen Sie die DNS-Richtlinie, die die Clientsubnetze mit den entsprechenden Zonenbereich verbindet, um die gewünschte DNS-Auflösung sicherzustellen.
    
An diesem Punkt geben Clients, die DNS-Abfragen aus dem Subnetz von Amsterdam für hybridvoice.adatum.biz ausführen, die 192.168.1.45 zurück. 192.168.1.46, 192.168.1.47 und 192.168.1.48-Adressen, während Clients mit demselben Abfrageformular Seattle 10.10.1.8, 10.10.1.9 und 10.10.1.10 zurückgeben.

> [!NOTE]
> Wenn die CCE-Appliance nicht die aktualisierten Einstellungen zu erhalten scheint, überprüfen Sie, ob die Appliance den Mandanten über die Remote-PowerShell kontaktieren kann. Sie können Remote PowerShell verwenden, um den Gerätestatus mit Get-CsHybridPSTNAppliance oder PowerShell auf dem CCE-Host zu verwenden, um den Status mit Get-CcApplianceStatus zu überprüfen.

  
## <a name="see-also"></a>Siehe auch
<a name="Example"> </a>

[Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
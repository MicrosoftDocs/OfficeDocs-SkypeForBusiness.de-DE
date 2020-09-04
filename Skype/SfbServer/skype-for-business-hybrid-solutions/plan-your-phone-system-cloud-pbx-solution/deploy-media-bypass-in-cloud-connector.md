---
title: Bereitstellen der medienumgehung in Cloud Connector Edition
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
description: In diesem Thema erfahren Sie mehr über die Schritte zur Bereitstellung der medienumgehung mit Cloud Connector Edition Version 2,0 und höher.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359311"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Bereitstellen der medienumgehung in Cloud Connector Edition
 
> [!Important]
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

In diesem Thema erfahren Sie mehr über die Schritte zur Bereitstellung der medienumgehung mit Cloud Connector Edition Version 2,0 und höher. 
  
Durch die medienumgehung kann ein Client Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – einen Gateway-oder Session Border Controller (SBC) – senden und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen. Siehe auch [Plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Medienumgehung aktivieren

Um die medienumgehung zu aktivieren, müssen Sie den DNS-Namen des Medien Umgehungs-Webdiensts konfigurieren und die medienumgehung in der Mandanten Konfiguration aktivieren. Der Medien Umgehungs-Webdienst wird automatisch auf jeder Vermittlungsserver bereitgestellt. Ein mandantenadministrator muss einen Namen für einen Hybrid-VoIP-Dienst (Standort) auswählen, und dieser Name sollte aus einer für Hybrid-VoIP registrierten SIP-Domäne sein. Der Dienstname sollte unabhängig vom Clientstandort für alle Cloud Connector-Appliances und alle PSTN-Standorte gleich sein. Der Webdienst sollte nur intern im Netzwerk verfügbar sein.
  
Ein mandantenadministrator muss einen DNS-a-Eintrag im internen Produktions Active Directory konfigurieren. Wenn Sie über eine komplexe Umgebung mit mehreren Standorten verfügen, lesen Sie das Beispiel unter [Beispiel: DNS-Einträge für die Medien Umgehungs Website in komplexen Umgebungen mit mehreren](deploy-media-bypass-in-cloud-connector.md#Example)Standorten. Der DNS-Eintrag sollte nur für interne Netzwerkclients aufgelöst werden; Es sollte nicht für externe Netzwerkclients aufgelöst werden.
  
Stellen Sie nach dem Konfigurieren von DNS eine Verbindung mit Skype for Business Online mithilfe von Remote-PowerShell mit Skype for Business Administrator Anmeldeinformationen her. Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die medienumgehung zu aktivieren:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Das Aktivieren der medienumgehung ist ein zweistufiger Prozess. Mit dem Cmdlet New-CsNetworkMedia wird die neue Konfiguration nicht sofort gespeichert; Es werden nur die Einstellungen im Arbeitsspeicher erstellt. Das von diesem Cmdlet erstellte Objekt muss in einer Variablen gespeichert und dann der MediaBypassSettings-Eigenschaft der Netzwerkkonfiguration zugewiesen werden. Weitere Informationen finden Sie unter [Beispiel: DNS-Einträge für die Medien Umgehungs Website in komplexen Umgebungen mit mehreren Standorten](deploy-media-bypass-in-cloud-connector.md#Example).
  
Die Replikation zwischen den lokalen und den Online-Komponenten kann bis zu 24 Stunden dauern, daher empfiehlt Microsoft, die erforderlichen Befehle auszuführen, bevor Sie Benutzer aktivieren.
  
## <a name="confirm-media-bypass-settings"></a>Bestätigen der Einstellungen für die medienumgehung

Sie können die Einstellungen für die medienumgehung wie folgt überprüfen. 
  
Führen Sie den folgenden Befehl in Remote PowerShell aus, um die Online Replikation auf ihren Mandanten Pool zu überprüfen:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Um die lokale Replikation zu überprüfen, stellen Sie eine Verbindung mit den Cloud Connector-Vermittlungsservern her, führen Sie den folgenden Befehl in PowerShell aus, und bestätigen Sie, dass Enabled = true und "alwaysbypass" = true sind.
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Um die Clienteinstellungen zu überprüfen, melden Sie sich vom Skype for Business-Client ab, melden Sie sich wieder an, und bestätigen Sie, dass der Client die Dienst-URL wie folgt erhalten hat:
  
1. %Appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. Öffnen 
    
2. Suchen Sie nach "hybridconfigserviceinternalurl", und bestätigen Sie, dass die URL mit der von Ihnen definierten übereinstimmt.
    
## <a name="change-media-bypass-parameters"></a>Ändern der Parameter für die medienumgehung

Mandantenadministratoren können den DNS-Namen des Webdiensts ändern, indem Sie das folgende Cmdlet ausführen:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Clients müssen sich abmelden und sich anmelden, um den neuen Dienstnamen zu erhalten und die Änderung zu erkennen. 
  
## <a name="temporarily-disable-media-bypass"></a>Medienumgehung vorübergehend deaktivieren

Dieses Szenario kann bei der Problembehandlung oder Wartung hilfreich sein. Führen Sie die folgenden Cmdlets aus, um den Dienst zu deaktivieren:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Nachdem Sie die Änderung vorgenommen haben, kann es einige Zeit dauern, bis Änderungen an alle Cloud-Konnektoren repliziert wurden. Um den Status der Replikation zu überprüfen, führen Sie das folgende Cmdlet in PowerShell auf den Vermittlungsservern von Cloud Connector aus: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Nachdem die Änderungen repliziert wurden, startet der Webdienst im Vermittlungsserver die Ablehnung von Clientanforderungen für den Medien Umgehungs Dienst.
  
## <a name="disable-media-bypass-permanently"></a>Medienumgehung dauerhaft deaktivieren

Um die medienumgehung dauerhaft zu deaktivieren, muss ein mandantenadministrator die folgenden Befehle ausführen: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Ein Administrator muss außerdem die Webadressen für die medienumgehung von internen DNS-Servern entfernen. Nachdem Sie die Änderung vorgenommen haben, kann es einige Zeit dauern, bis Änderungen an alle Cloud Connector-Appliances repliziert wurden. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Beispiel: DNS-Einträge für die Medien Umgehungs Website in komplexen Umgebungen mit mehreren Standorten
<a name="Example"> </a>

Clients erhalten die Webadresse des Medien Umgehungs-Webdiensts von einem internen DNS-Server. Der Name des Webdiensts ist für alle Cloud Connector-Appliances und Cloud Connector-PSTN-Standorte gleich. In einer komplexen Umgebung mit mehreren Standorten empfiehlt es sich, die Windows 2016-DNS-Richtlinie für die Verwaltung geografischer Standorte zu verwenden, sodass Clients an den Webdienst umgeleitet werden können, der für Ihr Netzwerk lokal ist. 
  
Weitere Informationen zu Windows 2016-DNS-Richtlinien finden Sie unter [use DNS Policy for Geo-Location based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Im folgenden finden Sie ein Beispiel für die Konfiguration für ein Unternehmen mit mehreren Standorten, die die Windows 2016-DNS-Richtlinie für die Verwaltung von Geo-Standort-Datenverkehr verwenden.
  
Der Name für den Bypass-Dienst lautet "hybridvoice.adatum.biz".
  
Auf der Website in Amsterdam sind vier Cloud Connector-Appliances mit den folgenden Vermittlungsserver-IP-Adressen bereitgestellt:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Die Website in Seattle verfügt über drei Cloud Connector-Appliances, die mit den folgenden Vermittlungsserver-IP-Adressen bereitgestellt werden:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Mithilfe der geografischen standortbasierten Datenverkehrsverwaltung würden die DNS-Server wie folgt konfiguriert:
  
1. Erstellen Sie DNS-Client-Subnetze für die Subnetze Amsterdam und Seattle.
    
2. Erstellen von DNS-Zonen Bereichen für adatum.biz für Amsterdam und Seattle.
    
3. Erstellen von DNS-Einträgen in jedem DNS-zonenbereich.
    
    Amsterdam
    
   - Geben Sie A ein;
    
   - Name: hybridvoice in der Adatum.biz-DNS-Zone
    
   - Ziel: 192.168.1.45
    
     Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Geben Sie A ein.
    
   - Name: hybridvoice in der Adatum.biz-DNS-Zone
    
   - Ziel: 10.10.1.8
    
     Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Erstellen Sie die DNS-Richtlinie, mit der die Client Subnetze mit den entsprechenden Zonen Bereichen verbunden werden, um die gewünschte DNS-Auflösung sicherzustellen.
    
Zu diesem Zeitpunkt werden von Clients, die DNS-Abfragen aus dem Amsterdamer Subnetz für hybridvoice.adatum.biz durchführen, die 192.168.1.45-, 192.168.1.46-, 192.168.1.47-und 192.168.1.48-Adressen zurückgegeben, während Clients, die dasselbe Abfrage Formular in Seattle erstellen, 10.10.1.8, 10.10.1.9 und 10.10.1.10 zurückgeben.

> [!NOTE]
> Wenn die CCE-Appliance anscheinend nicht die aktualisierten Einstellungen erhält, überprüfen Sie, ob die Appliance über Remote-PowerShell Kontakt mit dem Mandanten aufnehmen kann. Mithilfe von Remote-PowerShell können Sie den Appliance-Status mit Get-CsHybridPSTNAppliance überprüfen oder mithilfe von PowerShell auf dem CCE-Host den Status mit Get-CcApplianceStatus überprüfen.

  
## <a name="see-also"></a>Weitere Artikel
<a name="Example"> </a>

[Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

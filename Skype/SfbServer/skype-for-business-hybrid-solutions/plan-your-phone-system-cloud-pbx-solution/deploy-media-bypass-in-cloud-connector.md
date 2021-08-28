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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lesen Sie dieses Thema, um mehr über die Schritte zum Bereitstellen der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu erfahren.
ms.openlocfilehash: edc00467d878f0f2ae137c86f179f864bb2ca53f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613775"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Bereitstellen der Medienumgehung in Cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Lesen Sie dieses Thema, um mehr über die Schritte zum Bereitstellen der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu erfahren. 
  
Die Medienumgehung ermöglicht es einem Client, Medien direkt an den nächsten Hop (PsTN) zu senden – ein Gateway oder Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad zu entfernen. Siehe auch [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Medienumgehung aktivieren

Um die Medienumgehung zu aktivieren, müssen Sie den DNS-Namen des Webdiensts für die Medienumgehung konfigurieren und die Medienumgehung in der Mandantenkonfiguration aktivieren. Der Webdienst für die Medienumgehung wird automatisch auf jedem Vermittlungsserver bereitgestellt. Ein Mandantenadministrator muss einen Namen für einen Hybrid-VoIP-Dienst (Standort) auswählen, und dieser Name sollte aus einer SIP-Domäne stammen, die für Hybrid voice registriert ist. Der Dienstname sollte für alle Cloud Connector-Appliances und alle PSTN-Standorte unabhängig vom Clientstandort identisch sein. Der Webdienst sollte nur intern im Netzwerk verfügbar sein.
  
Ein Mandantenadministrator muss einen DNS A-Eintrag im internen Produktions-Active Directory konfigurieren. Wenn Sie über eine komplexe Umgebung mit mehreren Websites verfügen, sehen Sie sich das Beispiel in [Beispiel: DNS-Einträge der Medienumgehungswebsite in komplexen Umgebungen mit mehreren Websites an.](deploy-media-bypass-in-cloud-connector.md#Example) Der DNS-Eintrag sollte nur für interne Netzwerkclients aufgelöst werden. sie sollte für externe Netzwerkclients nicht aufgelöst werden.
  
Stellen Sie nach dem Konfigurieren von DNS mithilfe von Remote-PowerShell mit Skype for Business Administratoranmeldeinformationen eine Verbindung mit Skype for Business Online her. Weitere Informationen finden Sie unter [Einrichten des Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die Medienumgehung zu aktivieren:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Das Aktivieren der Medienumgehung besteht aus zwei Schritten. Das Cmdlet New-CsNetworkMedia speichert die neue Konfiguration nicht sofort. Es werden nur die Einstellungen im Arbeitsspeicher erstellt. Das mit diesem Cmdlet erstellte Objekt muss in einer Variablen gespeichert und dann der MediaBypassSettings-Eigenschaft der Netzwerkkonfiguration zugewiesen werden. Weitere Informationen finden Sie unter [Beispiel: DNS-Einträge der Medienumgehungswebsite in komplexen Umgebungen mit mehreren Websites.](deploy-media-bypass-in-cloud-connector.md#Example)
  
Die Replikation zwischen den lokalen und Onlinekomponenten kann bis zu 24 Stunden dauern, daher empfiehlt Microsoft, die erforderlichen Befehle auszuführen, bevor Sie Benutzer aktivieren.
  
## <a name="confirm-media-bypass-settings"></a>Bestätigen der Medienumgehungseinstellungen

Sie können die Medienumgehungseinstellungen wie folgt überprüfen. 
  
Führen Sie den folgenden Befehl in Remote-PowerShell aus, um die Onlinereplikation in Ihrem Mandantenpool zu überprüfen:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Um die lokale Replikation zu überprüfen, stellen Sie eine Verbindung mit den Cloud Connector-Vermittlungsservern her, führen Sie den folgenden Befehl in PowerShell aus, und vergewissern Sie sich, dass Enabled=True und AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Um die Clienteinstellungen zu überprüfen, melden Sie sich vom Skype for Business Client ab, melden Sie sich wieder an, und stellen Sie sicher, dass der Client die Dienst-URL wie folgt erhalten hat:
  
1. Öffnen Sie "%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog". 
    
2. Suchen Sie nach hybridconfigserviceinternalurl, und bestätigen Sie, dass die URL mit der von Ihnen definierten übereinstimmt.
    
## <a name="change-media-bypass-parameters"></a>Ändern von Medienumgehungsparametern

Mandantenadministratoren können den DNS-Namen des Webdiensts ändern, indem sie das folgende Cmdlet ausführen:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Clients müssen sich abmelden und anmelden, um den neuen Dienstnamen abzurufen und die Änderung zu erkennen. 
  
## <a name="temporarily-disable-media-bypass"></a>Vorübergehendes Deaktivieren der Medienumgehung

Dieses Szenario kann für die Problembehandlung oder Wartung hilfreich sein. Führen Sie die folgenden Cmdlets aus, um den Dienst zu deaktivieren:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Nachdem Sie die Änderung vorgenommen haben, kann es einige Zeit dauern, bis änderungen an alle Cloud Connectors repliziert wurden. Führen Sie das folgende Cmdlet in PowerShell auf Cloud Connector-Vermittlungsservern aus, um den Status der Replikation zu überprüfen: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

Nachdem die Änderungen repliziert wurden, beginnt der Webdienst auf dem Vermittlungsserver mit der Ablehnung von Clientanforderungen für den Medienumgehungsdienst.
  
## <a name="disable-media-bypass-permanently"></a>Dauerhaftes Deaktivieren der Medienumgehung

Um die Medienumgehung dauerhaft zu deaktivieren, muss ein Mandantenadministrator die folgenden Befehle ausführen: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Ein Administrator muss außerdem die Webadressen für die Medienumgehung von internen DNS-Servern entfernen. Nach der Änderung kann es einige Zeit dauern, bis Änderungen in alle Cloud Connector-Appliances repliziert wurden. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Beispiel: DNS-Einträge für Die Medienumgehungswebsite in komplexen Umgebungen mit mehreren Websites
<a name="Example"> </a>

Clients erhalten die Webadresse des Medienumgehungswebdiensts von einem internen DNS-Server. Der Name des Webdiensts ist für alle Cloud Connector-Appliances und Cloud Connector-PSTN-Standorte identisch. In einer komplexen Umgebung mit mehreren Websites wird empfohlen, die DNS-Richtlinie Windows 2016 für Geo-Location Based Traffic Management zu verwenden, damit Clients an den Webdienst umgeleitet werden können, der für ihr Netzwerk lokal ist. 
  
Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).
  
Es folgt ein Beispiel für die Konfiguration für ein Unternehmen mit mehreren Standorten, die Windows 2016-DNS-Richtlinie für Geo-Location Based Traffic Management verwenden.
  
Der Name für den Umgehungsdienst lautet "hybridvoice.adatum.biz".
  
Der Standort in Amsterdam verfügt über vier Cloud Connector-Appliances, die mit den folgenden VERMITTLUNGsserver-IP-Adressen bereitgestellt werden:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Der Standort in Seattle verfügt über drei Cloud Connector-Appliances, die mit den folgenden VERMITTLUNGsserver-IP-Adressen bereitgestellt werden:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Mit Geo-Location Based Traffic Management würden die DNS-Server wie folgt konfiguriert:
  
1. Erstellen Sie DNS-Clientsubnetze für die Subnetze von Amsterdam und Seattle.
    
2. Erstellen Sie DNS-Zonenbereiche für adatum.biz für Amsterdam und Seattle.
    
3. Erstellen Sie DNS-Einträge in jedem DNS-Zonenbereich.
    
    Amsterdam
    
   - Typ A;
    
   - Name: hybridvoice in der adatum.biz DNS-Zone
    
   - Ziel: 192.168.1.45
    
     Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Seattle
    
   - Typ A
    
   - Name: hybridvoice in adatum.biz DNS-Zone
    
   - Ziel: 10.10.1.8
    
     Erstellen zusätzlicher Datensätze für zusätzliche Vermittlungsserver
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Erstellen Sie die DNS-Richtlinie, die die Clientsubnetze mit den entsprechenden Zonenbereichen verbindet, um die gewünschte DNS-Auflösung sicherzustellen.
    
Zu diesem Zeitpunkt geben Clients, die DNS-Abfragen aus dem Subnetz Von Amsterdam für hybridvoice.adatum.biz durchführen, den Wert 192.168.1.45 zurück. 192.168.1.46, 192.168.1.47- und 192.168.1.48-Adressen, während Clients, die dasselbe Abfrageformular in Seattle erstellen, 10.10.1.8, 10.10.1.9 und 10.10.1.10 zurückgeben.

> [!NOTE]
> Wenn die CCE-Appliance scheinbar nicht die aktualisierten Einstellungen abruft, überprüfen Sie, ob die Appliance in der Lage ist, den Mandanten über Remote-PowerShell zu kontaktieren. Sie können Remote-PowerShell verwenden, um den Appliance-Status mit Get-CsHybridPSTNAppliance zu überprüfen, oder PowerShell auf dem CCE-Host verwenden, um den Status mit Get-CcApplianceStatus zu überprüfen.

  
## <a name="see-also"></a>Siehe auch
<a name="Example"> </a>

[Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
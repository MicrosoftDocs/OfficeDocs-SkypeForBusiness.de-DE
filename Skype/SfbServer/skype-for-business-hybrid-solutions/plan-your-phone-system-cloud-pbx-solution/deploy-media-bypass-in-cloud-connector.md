---
title: Die medienumgehung in der Cloud Connector Edition bereitstellen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lesen Sie dieses Thema Weitere Informationen zu den Schritten zum Bereitstellen von, dass die medienumgehung mit Cloud Connector Edition, Version 2.0 und höher.
ms.openlocfilehash: 4d0400682702c528e9e1ccb324731378d8c09b2c
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246687"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Die medienumgehung in der Cloud Connector Edition bereitstellen
 
Lesen Sie dieses Thema Weitere Informationen zu den Schritten zum Bereitstellen von, dass die medienumgehung mit Cloud Connector Edition, Version 2.0 und höher. 
  
Die medienumgehung kann ein Client zum Senden von Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – Session Border Controller (SBC) oder ein Gateway – und die Cloud Connector Edition-Komponente aus dem Medienpfad auszuschließen. Siehe auch [Planen Medien in der Cloud Connector Edition umgehen](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Medienumgehung aktivieren

Um die medienumgehung aktivieren, müssen Sie konfigurieren den DNS-Namen des Media Bypass-Webdiensts und schalten Sie die medienumgehung in der Mandantenkonfiguration. Der Media Bypass-Webdienst wird automatisch auf jedem Vermittlungsserver bereitgestellt. Mandantenadministrator muss wählen Sie einen Namen für einen Hybrid-VoIP-Dienst (Website), und dieser Name aus einer SIP-Domäne für Hybrid-VoIP registriert sein. Der Dienstname sollten über alle Cloud Connector Einheiten und alle PSTN-Websites, unabhängig von der Standort des Clients übereinstimmen. Der Webdienst sollte nur intern im Netzwerk verfügbar sein.
  
Mandantenadministrator muss einen DNS-A-Eintrag in der internen Active Directory-Produktion konfigurieren. Wenn Sie eine komplexe Umgebung mit mehreren Standorte haben, finden Sie im Beispiel in [Beispiel: medienumgehung Website DNS-Einträgen in komplexen mit mehreren Umgebungen](deploy-media-bypass-in-cloud-connector.md#Example). Der DNS-Eintrag sollte nur für interne Netzwerkclients auflösen; Es sollte nicht für externe Netzwerkclients aufgelöst werden.
  
Verbinden Sie nach der Konfiguration des DNS mit Skype für Business Online mithilfe von remote-PowerShell mit Skype Business Administratoranmeldeinformationen. Weitere Informationen finden Sie unter [Connecting to Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die Medienumgehung zu aktivieren:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Aktivieren der medienumgehung umfasst zwei Schritte. Das Cmdlet New-CsNetworkMedia speichern nicht sofort die neue Konfiguration. Es werden nur die Einstellungen im Arbeitsspeicher erstellt. Das Objekt, das mit diesem Cmdlet erstellten muss in einer Variablen gespeichert, und klicken Sie dann an die MediaBypassSettings-Eigenschaft die Netzwerkkonfiguration zugewiesen. Weitere Informationen finden Sie unter [Beispiel: medienumgehung Website DNS-Einträgen in komplexen mit mehreren Umgebungen](deploy-media-bypass-in-cloud-connector.md#Example).
  
Die Replikation zwischen den lokalen Komponenten und den Onlinekomponenten kann bis zu 24 Stunden dauern. Daher empfiehlt Microsoft, die notwendigen Befehle auszuführen, bevor Sie Benutzer aktivieren. 

  
## <a name="confirm-media-bypass-settings"></a>Überprüfen der Medienumgehungseinstellungen

Sie können die Medienumgehungseinstellungen wie folgt überprüfen.  
  
Führen Sie den folgenden Befehl zum Überprüfen des Mandanten Pools online-Replikation in remote-PowerShell:
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Überprüfen Sie die lokale Replikation, eine Verbindung mit der Cloud Connector Vermittlungsserver, führen Sie den folgenden Befehl in PowerShell und vergewissern Sie sich, Enabled = True und AlwaysBypass = True
  
```
Get-CsNetworkConfiguration -LocalStore
```

Zum Überprüfen der Clienteinstellungen Abmelden bei der Skype für Business-Client, erneut anmelden, und bestätigen Sie, dass der Client die Dienst-URL wie folgt erhalten hat:
  
1. Öffnen Sie „%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog“.  
    
2. Suchen Sie nach „hybridconfigserviceinternalurl“, und vergewissern Sie sich, dass die URL mit der übereinstimmt, die Sie definiert haben. 

    
## <a name="change-media-bypass-parameters"></a>Ändern von Medienumgehungsparametern

Mandantenadministratoren können den DNS-Namen des Webdiensts ändern, indem sie das folgende Cmdlet ausführen:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Clients müssen sich abmelden und dann wieder anmelden, um den neuen Dienstnahmen zu erhalten und die Änderung zu erkennen.  
  
## <a name="temporarily-disable-media-bypass"></a>Vorübergehendes Deaktivieren der Medienumgehung

Dieses Szenario kann bei der Problembehandlung oder Wartung hilfreich sein. Um den Dienst zu deaktivieren, führen Sie die folgenden Cmdlets aus:
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Nach der Änderung kann es einige Zeit Änderungen für die Replikation auf alle Cloud Connectors dauern. Um den Status der Replikation zu überprüfen, führen Sie das folgende Cmdlet auf Cloud Connector Vermittlungsservern in PowerShell: 
  
```
Get- CsNetworkConfiguration -LocalStore
```

Nach der Replikation der Änderungen lehnt der Webdienst auf dem Vermittlungsserver Clientanforderungen für den Medienumgehungsdienst ab.
  
## <a name="disable-media-bypass-permanently"></a>Dauerhaftes Deaktivieren der Medienumgehung

Um die Medienumgehung dauerhaft zu deaktivieren, muss ein Mandantenadministrator die folgenden Befehle ausführen:  
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Ein Administrator müssen auch die Webadressen für die medienumgehung von internen DNS-Servern zu entfernen. Nach der Änderung kann es Änderungen auf alle Cloud Connector Einheiten repliziert werden einige Zeit dauern. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Beispiel: DNS-Einträge für Medienumgehungs-Website in komplexen Umgebungen mit mehreren Standorten
<a name="Example"> </a>

Clients erhalten die Webadresse des Media Bypass-Webdiensts vom einen internen DNS-Server. Der Name des Webdiensts wird in allen Cloud Connector Appliances und Cloud Connector PSTN Websites übereinstimmen. In einer Umgebung mit komplexen mit mehreren Standorten wird empfohlen, die Windows 2016 DNS-Richtlinie für Geo-Location-basiertes Datenverkehr Management verwenden, damit Clients an den Webdienst umgeleitet werden können, die lokal für ihr Netzwerk ist. 
  
Weitere Informationen zu Windows 2016 DNS-Richtlinien finden Sie unter [Verwendung DNS-Richtlinie für Geo-Location basierte Datenverkehr Management mit primären Servern](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).
  
Das folgende Beispiel zeigt eine Konfiguration für eine Firma mit mehreren Standorten, in der eine Windows 2016-DNS-Richtlinie für geolocationbasierte Verwaltung des Datenverkehrs verwendet wird.
  
"Hybridvoice.adatum.biz" ist der Name für den Dienst umgehen.
  
Die Website in Amsterdam besteht aus vier Cloud Connector Appliances mit den folgenden Mediation Server-IP-Adressen bereitgestellt:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Die Website in Seattle verfügt über drei Cloud Connector Appliances mit den folgenden Mediation Server-IP-Adressen bereitgestellt:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Mithilfe von geolocationbasierter Verwaltung des Datenverkehrs würden Sie die DNS-Server so konfigurieren:
  
1. Erstellen Sie DNS-Clientsubnetze für die Subnetze von Amsterdam und Seattle.
    
2. Erstellen Sie für Amsterdam und Seattle DNS-Zonenbereiche für „adatum.biz“.
    
3. Erstellen Sie in jedem DNS-Zonenbereich DNS-Einträge.
    
    Amsterdam
    
  - Typ A
    
  - Name: „hybridvoice“ in der DNS-Zone für „adatum.biz“
    
  - Ziel: 192.168.1.45
    
    Erstellen Sie zusätzliche Einträge für weitere Vermittlungsserver.
    
  - 192.168.1.46
    
  - 192.168.1.47
    
  - 192.168.1.48
    
    Seattle
    
  - Typ A
    
  - Name: „hybridvoice“ in der DNS-Zone für „adatum.biz“
    
  - Ziel: 10.10.1.8
    
    Erstellen Sie zusätzliche Einträge für weitere Vermittlungsserver.
    
  - 10.10.1.9
    
  - 10.10.1.10
    
4. Erstellen Sie die DNS-Richtlinie, die die Clientsubnetze mit den entsprechenden Zonenbereichen verbindet, um die gewünschte DNS-Auflösung sicherzustellen.
    
An dieser Stelle geben Clients aus dem Amsterdam-Subnetz die DNS-Abfragen für „hybridvoice.adatum.biz“ ausführen, die Adressen 192.168.1.45, 192.168.1.46, 192.168.1.47 und 192.168.1.48 zurück. Clients, die die gleiche Abfrage aus Seattle ausführen, geben dagegen 10.10.1.8, 10.10.1.9 und 10.10.1.10 zurück.

> [!NOTE]
> Wenn die Appliance CCE scheinbar nicht, die aktualisierten Einstellungen zu erhalten, überprüfen Sie, um festzustellen, ob das Gerät mit den Mandanten über remote-PowerShell eine Verbindung herstellen. Remote-PowerShell können Sie überprüfen des Appliance Status mit Get-CsHybridPSTNAppliance oder mithilfe von PowerShell auf dem Host CCE um Status mit Get-CcApplianceStatus zu überprüfen.

  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="Example"> </a>

[Planen der Medienumgehung in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

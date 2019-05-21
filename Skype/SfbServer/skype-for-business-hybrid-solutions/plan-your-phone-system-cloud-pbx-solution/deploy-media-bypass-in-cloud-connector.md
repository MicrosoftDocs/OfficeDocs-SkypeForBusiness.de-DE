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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lesen Sie dieses Thema, um Informationen zu den Schritten zum Bereitstellen der medienumgehung mit Cloud Connector Edition, Version 2,0 und höher, zu erhalten.
ms.openlocfilehash: 6f3ad140d25d5f1d03196e576ac57dc56e905d44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287545"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Bereitstellen der medienumgehung in Cloud Connector Edition
 
Lesen Sie dieses Thema, um Informationen zu den Schritten zum Bereitstellen der medienumgehung mit Cloud Connector Edition, Version 2,0 und höher, zu erhalten. 
  
Die medienumgehung ermöglicht es einem Client, Medien direkt an das öffentlich geschaltete Telefon Netzwerk (PSTN) nächster Hop zu senden – einen Gateway-oder Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad zu entfernen. Siehe auch [Planen der medienumgehung in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Medienumgehung aktivieren

Um die medienumgehung zu aktivieren, müssen Sie den DNS-Namen des Media Bypass-Webdiensts konfigurieren und die medienumgehung in der Mandanten Konfiguration aktivieren. Der Medien Umgehungs-Web-Service wird automatisch auf jedem Vermittlungs Server bereitgestellt. Ein mandantenadministrator muss einen Namen für einen Hybrid-Voice-Service (Website) aussuchen, und dieser Name sollte aus einer für Hybrid-VoIP registrierten SIP-Domäne sein. Der Dienstname sollte unabhängig vom Clientstandort für alle Cloud Connector-Appliances und alle PSTN-Standorte identisch sein. Der Webdienst sollte nur intern im Netzwerk zur Verfügung stehen.
  
Ein Mandantenadministrator muss einen DNS-A-Eintrag in der internen Active Directory-Produktionsinstanz konfigurieren. Wenn Sie über eine komplexe Multi-Site-Umgebung verfügen, lesen Sie das Beispiel in [Beispiel: medienumgehung von Website-DNS-Einträgen in komplexen Multi-Site-Umgebungen](deploy-media-bypass-in-cloud-connector.md#Example). Der DNS-Eintrag sollte nur für interne Netzwerkclients aufgelöst werden, nicht für externe Netzwerkclients.
  
Nachdem Sie DNS konfiguriert haben, stellen Sie über Remote-PowerShell mit Skype for Business-Administratoranmeldeinformationen eine Verbindung mit Skype for Business Online her. Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .
  
Geben Sie in der PowerShell-Sitzung die folgenden Befehle ein, um die Medienumgehung zu aktivieren:
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Die Aktivierung der Medienumgehung besteht aus zwei Schritten. Das Cmdlet „New-CsNetworkMedia“ speichert die neue Konfiguration nicht sofort, es erstellt die Einstellungen nur im Arbeitsspeicher. Das von diesem Cmdlet erstellte Objekt muss in einer Variablen gespeichert und dann der Eigenschaft „MediaBypassSettings“ der Netzwerkkonfiguration zugewiesen werden. Weitere Informationen finden Sie unter [Beispiel: Website-DNS-Einträge für die medienumgehung in komplexen Multi-Site-Umgebungen](deploy-media-bypass-in-cloud-connector.md#Example).
  
Die Replikation zwischen den lokalen Komponenten und den Onlinekomponenten kann bis zu 24 Stunden dauern. Daher empfiehlt Microsoft, die notwendigen Befehle auszuführen, bevor Sie Benutzer aktivieren. 

  
## <a name="confirm-media-bypass-settings"></a>Überprüfen der Medienumgehungseinstellungen

Sie können die Medienumgehungseinstellungen wie folgt überprüfen.  
  
Führen Sie den folgenden Befehl in Remote PowerShell aus, um die Online Replikation auf ihren Mandanten Pool zu überprüfen:
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Um die lokale Replikation zu überprüfen, stellen Sie eine Verbindung mit dem Cloud Connector-Vermittlungsserver her, führen Sie in PowerShell den folgenden Befehl aus, und bestätigen Sie, dass Enabled = true und AlwaysBypass = true sind.
  
```
Get-CsNetworkConfiguration -LocalStore
```

Um die Clienteinstellungen zu überprüfen, melden Sie sich beim Skype for Business-Client ab, melden Sie sich wieder an, und bestätigen Sie, dass der Client die Dienst-URL wie folgt erhalten hat:
  
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

Nachdem Sie die Änderung vorgenommen haben, kann es eine Weile dauern, bis die Änderungen an alle Cloud Connector-Appliances repliziert sind. Führen Sie zum Überprüfen des Replikationsstatus das folgende Cmdlet in PowerShell auf Mediations Servern für Cloud Connector aus: 
  
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

Außerdem muss ein Administrator die Webadressen für die Medienumgehung von internen DNS-Servern entfernen. Nach der Änderung kann es einige Zeit dauern, bis Änderungen an allen Cloud Connector-Appliances repliziert wurden. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Beispiel: DNS-Einträge für Medienumgehungs-Website in komplexen Umgebungen mit mehreren Standorten
<a name="Example"> </a>

Clients erhalten die Webadresse des Medienumgehungs-Webdiensts von einem internen DNS-Server. Der Name des Webdiensts ist in allen Cloud Connector-Appliances und den PSTN-Websites für Cloud Connector identisch. In einer komplexen Umgebung mit mehreren Standorten empfehlen wir die Verwendung einer Windows 2016-DNS-Richtlinie für geolocationbasierte Verwaltung des Datenverkehrs, damit Clients an den für ihr Netzwerk lokalen Webdienst umgeleitet werden können. 
  
Weitere Informationen zu DNS-Richtlinien für Windows 2016 finden Sie unter [Verwenden der DNS-Richtlinie für die Geolocation-basierte Datenverkehrsverwaltung mit primären Servern](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).
  
Das folgende Beispiel zeigt eine Konfiguration für eine Firma mit mehreren Standorten, in der eine Windows 2016-DNS-Richtlinie für geolocationbasierte Verwaltung des Datenverkehrs verwendet wird.
  
Der Name für den Bypass-Dienst lautet "hybridvoice.adatum.biz".
  
Die Website in Amsterdam verfügt über vier Cloud Connector-Appliances, die mit den folgenden IP-Adressen des Vermittlungsservers bereitgestellt werden:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
Die Website in Seattle verfügt über drei Cloud Connector-Appliances, die mit den folgenden Vermittlungs Server-IP-Adressen bereitgestellt werden:
  
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
> Wenn die CCE-Appliance die aktualisierten Einstellungen anscheinend nicht erhält, überprüfen Sie, ob die Appliance über die Remote-PowerShell mit dem Mandanten Kontakt aufnehmen kann. Sie können Remote-PowerShell verwenden, um den Appliance-Status mit Get-CsHybridPSTNAppliance zu überprüfen oder PowerShell auf dem CCE-Host zu verwenden, um den Status mithilfe von Get-CcApplianceStatus zu überprüfen.

  
## <a name="see-also"></a>Siehe auch
<a name="Example"> </a>

[Planen der Medienumgehung in der Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

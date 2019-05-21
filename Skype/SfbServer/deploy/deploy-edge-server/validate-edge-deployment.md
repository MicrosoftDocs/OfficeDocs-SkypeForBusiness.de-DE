---
title: Überprüfen Ihrer Edge-Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie überprüfen können, ob Ihre Bereitstellung des Edge-Servers oder des Edge-Server-Pools in Skype for Business Server funktioniert.'
ms.openlocfilehash: 0c432cba78e97add71bb7c4e21e155f92c9fe66a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306888"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Überprüfen Ihrer Edge-Bereitstellung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen können, ob Ihre Bereitstellung des Edge-Servers oder des Edge-Server-Pools in Skype for Business Server funktioniert.
  
Nachdem Sie Ihren Edge-Server oder Edge-Server-Pool bereitgestellt haben, müssen Sie wissen, ob er ordnungsgemäß funktioniert. Hier sind ein paar Dinge, die Ihnen helfen können, zu bestätigen, dass Ihre Edge-Umgebung mit ihren internen Servern verbunden ist, und dass Ihre externen Benutzer auch über Ihren Edge eine Verbindung mit Ihrer Skype for Business Server-Umgebung herstellen können.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Überprüfen der Konnektivität zwischen Ihren internen Servern und Ihren Edgeservern

Während die Überprüfung der Konnektivität automatisch im Edge-Server oder im Edge-Server-Pool erfolgt, wenn die Edgeserver installiert sind, können Sie dies mit Windows PowerShell dennoch selbst bestätigen. Führen Sie das Cmdlet "Get-CsManagementStoreReplicationStatus" auf dem internen Server mit dem zentralen Verwaltungsspeicher oder einem beliebigen Domänen verbundenen Computer aus, auf dem die Skype for Business Server Core-Komponenten (OcsCore. msi) installiert sind.
  
Das erste Ergebnis beim Ausführen dieses Befehls kann für Replikation der Status „False“ statt „True“ sein. Führen Sie das cmdlet Invoke-CsManagementStoreReplication aus, wenn das der Fall ist. Lassen Sie ausreichend Zeit für den Abschluss der Replikation und führen Sie dann das cmdlet Get-CsManagementStoreReplicationStatus erneut aus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Überprüfen der Konnektivität für Ihre externen Benutzer

Wir verfügen über ein großartiges Tool zur Bestätigung Ihrer Edge-Server-Konfiguration und die Möglichkeit, die richtigen Nachrichten für Edge-Server-Szenarien zu verbinden, zu senden und zu empfangen. Es handelt sich um die [Anaylzer-Website für Remote Konnektivität](https://testconnectivity.microsoft.com/). Dieser Standort wird vom Microsoft-Support verwaltet. Um dieses Instrument zu verwenden, öffnen Sie die Website in einem Browser und folgen Sie den Anweisungen zum Auswählen des richtigen Szenarios.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Zu beachtende Punkte beim Testen der Konnektivität für externe Benutzer

Jegliche Tests für den Zugriff durch externe Benutzer müssen sämtliche Typen interner Benutzer umfassen, die von Ihrer Organisation unterstützt werden. Dazu können einer oder alle der folgenden Typen zählen:
  
- Benutzer aus mindestens einer Partnerdomäne (wir empfehlen, dass Sie alle testen)
    
- Anonyme Benutzer.
    
- Benutzer in Ihrer Organisation, die in Skype for Business Remote angemeldet sind, aber keine VPN-Verbindung verwenden.
    
Mit diesen Tests wird ermittelt, ob der Edgeserver wie folgt lautet:
  
- Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.
    
  - Zum Beispiel: telnet sip.contoso.com 443
    
  - Je nach Bereitstellung sollten Sie den vorhergehenden Test für die Ports ausführen, die Sie auf Ihrem Edge-Server oder Edge-Server-Pool verwenden.
    
- Ausführen einer präzisen externen DNS-Auflösung.
    
  - Pingen Sie von außerhalb Ihres Netzwerks alle externen FQDNs Ihres Edge-Servers oder Edge-Server-Pools. Auch wenn der Ping-Fehler fehlschlägt, werden die IP-Adressen angezeigt, die Sie mit den zuvor zugewiesenen IP-Adressen vergleichen können.
    


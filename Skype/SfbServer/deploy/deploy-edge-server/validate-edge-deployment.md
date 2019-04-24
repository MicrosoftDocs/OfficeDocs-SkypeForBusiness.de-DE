---
title: Überprüfen Sie Ihre edgebereitstellung in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Zusammenfassung: Erfahren Sie, wie stellen Sie sicher, dass Ihre Bereitstellung von Edge-Server oder Edge-Server-Pool in Skype für Business Server funktionsfähig ist.'
ms.openlocfilehash: 63c4cb1af599da191d0e0f4b95cfdaa775a64ba4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223789"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Überprüfen Sie Ihre edgebereitstellung in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie stellen Sie sicher, dass Ihre Bereitstellung von Edge-Server oder Edge-Server-Pool in Skype für Business Server funktionsfähig ist.
  
Nachdem Sie den Edge-Server oder Pool von Edge-Server bereitgestellt haben, müssen Sie wissen, ob sie ordnungsgemäß funktioniert. Hier sind einige Dinge, die mit bestätigt wird, ist der Edge-Umgebung verbunden helfen kann von internen Servern und auch, die für externe Benutzer auf Ihre Skype für Business Server-Umgebung durch Ihre Kante verbinden können.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Überprüfen der Konnektivität zwischen Ihren internen Servern und Ihren Edgeservern

Während der Überprüfung der Konnektivität automatisch erfolgt in Edgeserver oder edgeserverpool Wenn die Edge-Server installiert sind, können Sie weiterhin dies für sich selbst mit Windows PowerShell überprüfen. Führen Sie das Get-CsManagementStoreReplicationStatus-Cmdlet auf dem internen Server, der die zentrale Verwaltung gespeichert hat, oder einem beliebigen Computer der Domäne beigetreten sind auf welche Skype für Business Server-Hauptkomponenten (OcsCore.msi) installiert sind.
  
Das erste Ergebnis beim Ausführen dieses Befehls kann für Replikation der Status „False“ statt „True“ sein. Führen Sie das cmdlet Invoke-CsManagementStoreReplication aus, wenn das der Fall ist. Lassen Sie ausreichend Zeit für den Abschluss der Replikation und führen Sie dann das cmdlet Get-CsManagementStoreReplicationStatus erneut aus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Überprüfen der Konnektivität für Ihre externen Benutzer

Wir haben ein hervorragendes Tool für die Bestätigung der Edge-Server-Konfiguration und die Möglichkeit, eine Verbindung herstellen, Nachrichten senden und empfangen die richtigen für Edge-Server-Szenarien. Es ist die [Remote Connectivity Anaylzer-Website](https://testconnectivity.microsoft.com/). Dieser Standort wird vom Microsoft-Support verwaltet. Um dieses Instrument zu verwenden, öffnen Sie die Website in einem Browser und folgen Sie den Anweisungen zum Auswählen des richtigen Szenarios.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Zu beachtende Punkte beim Testen der Konnektivität für externe Benutzer

Jegliche Tests für den Zugriff durch externe Benutzer müssen sämtliche Typen interner Benutzer umfassen, die von Ihrer Organisation unterstützt werden. Dazu können einer oder alle der folgenden Typen zählen:
  
- Benutzer aus mindestens einer Partnerdomäne (wir empfehlen, dass Sie alle testen)
    
- Anonyme Benutzer.
    
- Benutzer in Ihrer Organisation, Remote bei Skype für Unternehmen angemeldet sind, aber nicht VPN verwenden.
    
Diese Tests bestimmt, ob der Edge-Server ist:
  
- Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.
    
  - Zum Beispiel: telnet sip.contoso.com 443
    
  - Sie sollten des vorstehenden Tests für die Ports ausführen, die Sie auf dem Edge-Server oder Pool für Edge-Server, abhängig von Ihrer Bereitstellung verwenden.
    
- Ausführen einer präzisen externen DNS-Auflösung.
    
  - Pingen auf außerhalb Ihres Netzwerks aller externen FQDNs der Edge-Server oder Pool für Edge-Server. Selbst wenn der Ping-Befehl ein Fehler auftritt, sehen Sie die IP-Adressen, denen Sie die IP-Adressen vergleichen können, die Sie zuvor zugewiesen haben.
    


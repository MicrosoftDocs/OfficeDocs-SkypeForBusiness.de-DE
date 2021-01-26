---
title: Überprüfen Der Edgebereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Zusammenfassung: Erfahren Sie, wie Sie überprüfen, ob Ihre Bereitstellung von Edgeserver oder Edgeserverpool in Skype for Business Server funktioniert.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804355"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Überprüfen Der Edgebereitstellung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen, ob Ihre Bereitstellung von Edgeserver oder Edgeserverpool in Skype for Business Server funktioniert.
  
Nachdem Sie Den Edgeserver oder Edgeserverpool bereitgestellt haben, müssen Sie wissen, ob er ordnungsgemäß funktioniert. Im Anschluss finden Sie einige Dinge, die Ihnen dabei helfen können, zu bestätigen, dass Ihre Edgeumgebung mit Ihren internen Servern verbunden ist, und dass Ihre externen Benutzer über Ihren Edge eine Verbindung mit Ihrer Skype for Business Server-Umgebung herstellen können.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Überprüfen der Konnektivität zwischen Ihren internen Servern und Ihren Edgeservern

Während die Überprüfung der Konnektivität automatisch im Edgeserver- oder Edgeserverpool erfolgt, wenn die Edgeserver installiert sind, können Sie dies mit der Windows PowerShell. Führen Sie das cmdlet Get-CsManagementStoreReplicationStatus auf dem internen Server aus, der über den zentralen Verwaltungsspeicher verfügt, oder auf einem computer, der einer Domäne beigetreten ist, auf dem Skype for Business Server Core Components (OcsCore.msi) installiert sind.
  
Das erste Ergebnis der Ausführung dieses Befehls kann für die Replikation den Status "False" und nicht "True" geben. Führen Sie in diesem Fall das Invoke-CsManagementStoreReplication aus. Geben Sie ihm etwas Zeit, um die Replikation fertig zu machen, und führen Sie dann das Get-CsManagementStoreReplicationStatus erneut aus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Überprüfen der Konnektivität für externe Benutzer

Wir verfügen über ein hervorragendes Tool zum Bestätigen Ihrer Edgeserverkonfiguration und die Möglichkeit, eine Verbindung herzustellen, die richtigen Nachrichten für Edgeserverszenarien zu senden und zu empfangen. Dies ist der [Remoteverbindungs-Anaylzer-Standort.](https://testconnectivity.microsoft.com/) Dies ist eine Website, die vom Microsoft Support verwaltet und verwaltet wird. Um dieses Tool zu verwenden, navigieren Sie zur Website, und folgen Sie den Anweisungen, um das richtige Szenario für Sie zu wählen.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Beim Testen der Konnektivität externer Benutzer zu berücksichtigende Dinge

Jeder Test für den Zugriff durch externe Benutzer muss jeden Typ von internen Benutzern enthalten, der von Ihrer Organisation unterstützt wird. Dies kann folgendes umfassen:
  
- Benutzer aus mindestens einer Verbunddomäne (es wird jedoch empfohlen, sie alle zu testen).
    
- Anonyme Benutzer.
    
- Benutzer in Ihrer Organisation, die remote bei Skype for Business angemeldet sind, aber kein VPN verwenden.
    
Diese Tests bestimmen, ob Ihr Edgeserver:
  
- Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.
    
  - Beispiel: telnet sip.contoso.com 443
    
  - Sie sollten den vorstehenden Test an den Ports durchführen, die Sie je nach Bereitstellung auf Dem Edgeserver oder Edgeserverpool verwenden.
    
- Ausführen einer präzisen externen DNS-Auflösung.
    
  - Pingen Sie von außerhalb Des Netzwerks an jeden externen FQDN Ihres Edgeservers oder Edgeserverpools. Selbst wenn der Ping fehlschlägt, werden die IP-Adressen, die Sie zuvor zugewiesen haben, verglichen.
    


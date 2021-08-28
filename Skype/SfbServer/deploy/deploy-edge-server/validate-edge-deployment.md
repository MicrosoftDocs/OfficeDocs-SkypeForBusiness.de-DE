---
title: Überprüfen der Edgebereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Zusammenfassung: Erfahren Sie, wie Sie überprüfen, ob Ihre Bereitstellung des Edgeservers oder Edgeserverpools in Skype for Business Server funktioniert.'
ms.openlocfilehash: 175baab9770e6013820e0e632712bf75b7669a57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583239"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Überprüfen der Edgebereitstellung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen, ob Ihre Bereitstellung des Edgeservers oder Edgeserverpools in Skype for Business Server funktioniert.
  
Nachdem Sie Ihren Edgeserver oder Edgeserverpool bereitgestellt haben, müssen Sie wissen, ob er ordnungsgemäß funktioniert. Hier sind einige Dinge, die Ihnen dabei helfen können, zu bestätigen, dass Ihre Edgeumgebung mit Ihren internen Servern verbunden ist, und dass Ihre externen Benutzer über Edge eine Verbindung mit Ihrer Skype for Business Server Umgebung herstellen können.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Überprüfen der Konnektivität zwischen Ihren internen Servern und Ihren Edgeservern

Während die Überprüfung der Konnektivität automatisch im Edgeserver oder Edgeserverpool erfolgt, wenn die Edgeserver installiert werden, können Sie dies dennoch selbst mit Windows PowerShell bestätigen. Führen Sie das Cmdlet Get-CsManagementStoreReplicationStatus auf dem internen Server mit dem zentralen Verwaltungsspeicher oder auf einem beliebigen Computer aus, auf dem Skype for Business Server Core Components (OcsCore.msi) installiert sind.
  
Das anfängliche Ergebnis der Ausführung dieses Befehls gibt möglicherweise für die Replikation den Status "False" und nicht "True" aus. Führen Sie in diesem Fall das Cmdlet Invoke-CsManagementStoreReplication aus. Geben Sie ihr etwas Zeit, um die Replikation abzuschließen, und führen Sie dann das Cmdlet Get-CsManagementStoreReplicationStatus erneut aus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Überprüfen der Konnektivität für Ihre externen Benutzer

Wir verfügen über ein hervorragendes Tool für die Bestätigung Ihrer Edgeserverkonfiguration und die Möglichkeit, die richtigen Nachrichten für Edgeserverszenarien zu verbinden, zu senden und zu empfangen. Dies ist der [Anaylzer-Standort für Remotekonnektivität.](https://testconnectivity.microsoft.com/) Dies ist eine Website, die vom Microsoft-Support verwaltet und verwaltet wird. Um dieses Tool zu verwenden, navigieren Sie zur Website, und folgen Sie den Anweisungen, um das richtige Szenario für Sie auszuwählen.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Zu berücksichtigende Punkte beim Testen der Konnektivität externer Benutzer

Jeder Test für den Zugriff durch externe Benutzer muss jeden Internen Benutzertyp enthalten, den Ihre Organisation unterstützt, der eine oder alle der folgenden Elemente umfassen kann:
  
- Benutzer aus mindestens einer Verbunddomäne (wir empfehlen jedoch, sie alle zu testen).
    
- Anonyme Benutzer.
    
- Benutzer in Ihrer Organisation, die remote bei Skype for Business angemeldet sind, aber kein VPN verwenden.
    
Diese Tests bestimmen, ob ihr Edgeserver:
  
- Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.
    
  - Beispiel: telnet sip.contoso.com 443
    
  - Sie sollten den vorherigen Test je nach Bereitstellung auf den Ports durchführen, die Sie auf Ihrem Edgeserver oder Edgeserverpool verwenden.
    
- Ausführen einer präzisen externen DNS-Auflösung.
    
  - Pingen Sie von außerhalb Des Netzwerks an jeden der externen FQDNs Ihres Edgeservers oder Edgeserverpools. Auch wenn das Pingen fehlschlägt, werden die IP-Adressen angezeigt, die Sie mit den zuvor zugewiesenen IP-Adressen vergleichen können.
    


---
title: Aktualisieren von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server aktualisieren.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821765"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Aktualisieren von Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server aktualisieren.
  
In diesem Thema wird das Upgrade einer vorhandenen Installation von Statistics Manager für Skype for Business Server beschrieben, einem leistungsstarken Tool, mit dem Sie Integritäts- und Leistungsdaten von Skype for Business Server in Echtzeit anzeigen können. Sie können alle paar Sekunden Leistungsdaten auf Hunderten von Servern abfragen und die Ergebnisse sofort auf der Statistics Manager-Website anzeigen. 
  
Weitere Informationen zu Statistics Manager und den neuen Funktionen in Version 2.0 finden Sie unter [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy Statistics Manager for Skype for Business [Server](deploy.md).
  
Es gibt zwei Methoden für das Upgrade:
  
- **Automatisiertes Upgrade.** Diese Methode verwendet ein automatisiertes Skript. Dies ist die einfachste Methode und sollte für alle Upgradeszenarien gelten.
    
- **Manuelles Upgrade.** Diese Methode wird als Sicherungsplan für den ungewöhnlichen Fall bereitgestellt, dass das automatische Upgrade fehlschlägt.
    
## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie vor dem Upgrade sicher, dass Sie über die folgenden Informationen verfügen:
  
- Active Listener Certificate Thumbprint
    
- Listener service password (eingegeben bei der Installation des Listeners und jedes Agents)
    
- Konfiguration des SSL-Zertifikats für die Website
    
## <a name="automated-upgrade"></a>Automatisiertes Upgrade

Das Skript sammelt Ihre aktuellen Zertifikatinformationen und das Listenerkennwort, deinstalliert die alte Version des Produkts und installiert dann die neue Version des Produkts. Die auf dem Server installierte Redis-Instanz wird nicht berührt, sodass alle im Cache gespeicherten Daten während des Upgradeprozesses beibehalten werden.
  
1. Platzieren Sie die MSI-Dateien für die neue Version des Agents, Listeners und der Website zusammen mit dem skript Update-StatsMan.ps1 in einem einzigen Ordner auf dem Listener-Computer.
    
2. Öffnen Sie ein administratives PowerShell-Fenster. Aktualisieren Sie die Listener-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Das Statistics Manager -Dienstkennwort wird als Klartext in der Befehlszeile angezeigt, wenn es an das Installationsprogramm übergeben wird. Achten Sie darauf, den Monitor nach Bedarf zu schützen. 
  
1. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Antwort Ja.
    
2. Wenn der Listenerdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Zulassen, dass die Anwendung geschlossen wird (der Statistics Manager-Listenerdienst wird beendet).
    
3. Setzen Sie den Installationsvorgang fort. Beachten Sie, dass das Dienstkennwort und der Zertifikatfingerabdruck vorab ausgefüllt sind. Falls nicht, fügen Sie die Werte hinzu, die Sie gespeichert haben, bevor Sie fortfahren.
    
4. Öffnen Sie ein administratives PowerShell-Fenster. Aktualisieren sie die Websitekomponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Antwort Ja.
    
6. Wenn der Agentdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Zulassen, dass die Anwendung geschlossen wird (der StatsMan-Agent-Dienst wird beendet).
    
7. Setzen Sie den Installationsvorgang fort. Beachten Sie, dass das Dienstkennwort und der Zertifikatfingerabdruck vorab ausgefüllt sind. Falls nicht, fügen Sie die Werte hinzu, die Sie gespeichert haben, bevor Sie fortfahren.
    
8. Öffnen Sie ein administratives PowerShell-Fenster. Aktualisieren Sie die Agent-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Antwort Ja.
    
10. Setzen Sie den Installationsvorgang fort. Beachten Sie, dass der Websiteport bereits ausgefüllt ist. Falls nicht, fügen Sie den gespeicherten Wert hinzu, bevor Sie fortfahren.
    
11. Überprüfen Sie mithilfe des Browsers, ob die Website wie erwartet funktioniert.
    
> [!NOTE]
> Das Upgrade des Agents kann mit dem Switch "-NoPrompt" verwendet werden. Dadurch kann der Deinstallations-/Installationsvorgang im Hintergrund ausgeführt werden, sodass Tools wie PSExec das Upgrade remote auf einer großen Anzahl von Servern ausführen können. 
  
### <a name="manual-upgrade"></a>Manuelles Upgrade

Wenn das automatisierte Upgrade aus einem bestimmten Grund fehlschlägt, können Sie ein manuelles Upgrade wie folgt ausführen:
  
1. Deinstallieren Sie auf dem Computer "Listener", "Website" und "Agent" (falls auf diesem Server installiert) über die Systemsteuerung "Programme und Features". 
    
    > [!NOTE]
    >  Lassen Sie Redis installiert, damit die Daten im Cache dann im Upgradeprozess verwaltet werden.
  
2. Installieren Sie die neuen Versionen der Komponenten, einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Fixed"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)
    
- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)

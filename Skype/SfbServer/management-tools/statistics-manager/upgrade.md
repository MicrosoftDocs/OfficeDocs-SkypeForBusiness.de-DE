---
title: Aktualisieren von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Statistics Manager für Skype for Business Server aktualisieren.'
ms.openlocfilehash: 2196f07d25fb761055df4432f0c2fd930368474d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772001"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Aktualisieren von Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server aktualisieren.
  
In diesem Thema wird beschrieben, wie Sie eine vorhandene Installation von Statistics Manager für Skype for Business Server aktualisieren– ein leistungsstarkes Tool, mit dem Sie Skype for Business Server Integritäts- und Leistungsdaten in Echtzeit anzeigen können. Sie können alle paar Sekunden Leistungsdaten über Hunderte von Servern abrufen und die Ergebnisse sofort auf der Statistics Manager-Website anzeigen. 
  
Weitere Informationen zu Statistics Manager und den neuen Features in Version 2.0 finden Sie unter [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy Statistics Manager for [Skype for Business Server.](deploy.md)
  
Es gibt zwei Methoden für das Upgrade:
  
- **Automatisiertes Upgrade.** Diese Methode verwendet ein automatisiertes Skript. Dies ist die einfachste Methode und sollte für alle Upgradeszenarien gelten.
    
- **Manuelles Upgrade.** Diese Methode wird als Sicherungsplan für den ungewöhnlichen Fall bereitgestellt, dass das automatische Upgrade fehlschlägt.
    
## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie vor dem Upgrade sicher, dass Sie über die folgenden Informationen verfügen:
  
- Active Listener Certificate Thumbprint
    
- Listener-Dienstkennwort (bei Installation des Listeners und jedes Agents eingegeben)
    
- SSL-Zertifikatkonfiguration für die Website
    
## <a name="automated-upgrade"></a>Automatisiertes Upgrade

Das Skript sammelt Ihre aktuellen Zertifikatinformationen und ihr Listenerkennwort, deinstalliert die alte Version des Produkts und installiert dann die neue Version des Produkts. Die auf dem Server installierte Redis-Instanz wird nicht berührt, sodass alle im Cache gespeicherten Daten während des Upgradeprozesses beibehalten werden.
  
1. Platzieren Sie die MSI-Dateien für die neue Version des Agents, Listeners und der Website zusammen mit dem Update-StatsMan.ps1 Skript in einem einzigen Ordner auf dem Listener-Computer.
    
2. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Listener-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Das Statistics Manager-Dienstkennwort wird in Klartext in der Befehlszeile angezeigt, während es an das Installationsprogramm übergeben wird. Achten Sie darauf, ihren Monitor nach Bedarf zu schützen. 
  
1. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Antwort Ja.
    
2. Wenn der Listener-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Zulassen, dass die Anwendung geschlossen wird (der Listenerdienst des Statistics Manager wird beendet).
    
3. Setzen Sie den Installationsvorgang fort. Beachten Sie, dass das Dienstkennwort und der Zertifikatfingerabdruck bereits ausgefüllt sind. Falls nicht, fügen Sie die gespeicherten Werte hinzu, bevor Sie fortfahren.
    
4. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren der Websitekomponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Antwort Ja.
    
6. Wenn der Agent-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Zulassen, dass die Anwendung geschlossen wird (der StatsMan-Agent-Dienst wird beendet).
    
7. Setzen Sie den Installationsvorgang fort. Beachten Sie, dass das Dienstkennwort und der Zertifikatfingerabdruck bereits ausgefüllt sind. Falls nicht, fügen Sie die gespeicherten Werte hinzu, bevor Sie fortfahren.
    
8. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Agent-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Antwort Ja.
    
10. Setzen Sie den Installationsvorgang fort. Beachten Sie, dass der Websiteport bereits ausgefüllt ist. Wenn nicht, fügen Sie den Wert hinzu, den Sie gespeichert haben, bevor Sie fortfahren.
    
11. Überprüfen Sie mithilfe des Browsers, ob die Website wie erwartet funktioniert.
    
> [!NOTE]
> Das Agent-Upgrade kann mit dem Switch -NoPrompt verwendet werden. Dadurch kann der Deinstallations-/Installationsvorgang im Hintergrund ausgeführt werden, sodass Tools wie PSExec das Upgrade remote auf einer großen Anzahl von Servern ausführen können. 
  
### <a name="manual-upgrade"></a>Manuelles Upgrade

Wenn das automatisierte Upgrade aus irgendeinem Grund fehlschlägt, können Sie ein manuelles Upgrade immer wie folgt ausführen:
  
1. Deinstallieren Sie auf dem Listener-Computer den Listener, die Website und den Agent (falls er auf diesem Server installiert wurde) über die Systemsteuerung "Programme und Features". 
    
    > [!NOTE]
    >  Lassen Sie Redis installiert, damit die Daten im Cache dann während des Upgradeprozesses verwaltet werden.
  
2. Installieren Sie die neuen Versionen der Komponenten, einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Fixed"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)
    
- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)

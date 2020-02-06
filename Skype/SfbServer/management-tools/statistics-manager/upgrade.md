---
title: Aktualisieren von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Statistics Manager für Skype for Business Server aktualisieren.'
ms.openlocfilehash: 6d54261ce9148986df5342bc228fe70b1477e17a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816204"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Aktualisieren von Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server aktualisieren.
  
In diesem Thema wird beschrieben, wie Sie eine vorhandene Installation von Statistics Manager für Skype for Business Server aktualisieren – ein leistungsfähiges Tool, mit dem Sie Skype for Business Server-Integritäts-und-Leistungsdaten in Echtzeit anzeigen können. Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen. 
  
Weitere Informationen zum Statistik-Manager und zu den neuen Features in Release 2,0 finden Sie unter [Planen von Statistics Manager für Skype for Business Server](plan.md) und [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md).
  
Es gibt zwei Verfahren für die Aktualisierung:
  
- **Automatische Aktualisierung.** Diese Methode verwendet ein automatisches Skript. Dies ist die einfachste Methode, die für alle Upgrade-Szenarien gelten sollte.
    
- **Manuelle Aktualisierung.** Diese Methode wird im ungewöhnlichen Fall als Sicherungsplan bereitgestellt, wenn das automatisierte Upgrade fehlschlägt.
    
## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie aktualisieren, stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:
  
- Active Listener-Zertifikatfingerabdruck
    
- Listener-Dienst-Kennwort (eingegeben bei der Installation des Listeners und jedes Agents)
    
- SSL-Zertifikat-Konfiguration für die Website
    
## <a name="automated-upgrade"></a>Automatische Aktualisierung

Das Skript sammelt Ihre aktuellen Zertifikatinformationen und das Listener-Kennwort, deinstallieren die alte Version des Produkts und installieren dann die neue Version des Produkts. Die auf dem Server installierte Instanz von "auf dem Server" wird nicht berührt, sodass alle im Cache gespeicherten Daten über den Upgradeprozess aufbewahrt werden.
  
1. Platzieren Sie die MSI-Dateien für die neue Version des Agents, Listener und der Website zusammen mit dem Update-StatsMan. ps1-Skript in einem einzelnen Ordner auf dem Listener-Computer.
    
2. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Listener-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Das Kennwort des Statistik-Manager-Diensts wird in Klartext in der Befehlszeile angezeigt, wenn es an das Installationsprogramm übergeben wird. Achten Sie darauf, Ihren Bildschirm bei Bedarf entsprechend abzudecken. 
  
1. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Bestätigen Sie dies mit „Ja“.
    
2. Wenn der Listenerdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Zulassen, dass die Anwendung geschlossen wird (der Statistik-Manager-Listener-Dienst wird beendet).
    
3. Setzen Sie den Installationsprozess fort. Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind. Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.
    
4. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Website-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Bestätigen Sie dies mit „Ja“.
    
6. Wenn der Agent-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Warten Sie, bis die Anwendung geschlossen ist (der StatsMan-Agent-Dienst wird beendet).
    
7. Setzen Sie den Installationsprozess fort. Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind. Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.
    
8. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Agent-Komponente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Bestätigen Sie dies mit „Ja“.
    
10. Setzen Sie den Installationsprozess fort. Beachten Sie, dass eine Eintragung für den Website-Port bereits im Voraus vorgenommen worden ist. Falls das nicht der Fall ist, tragen Sie den Wert ein, den Sie zuvor gespeichert haben, bevor Sie fortfahren.
    
11. Stellen Sie mithilfe des Browsers sicher, dass die Website wie erwartet funktioniert.
    
> [!NOTE]
> Das Agent-Upgrade kann mit der Schalter-noprompt verwendet werden. Auf diese Weise kann der Deinstallations-/Installationsvorgang im Hintergrund ausgeführt werden, sodass Tools wie PSExec das Upgrade Remote auf einer Vielzahl von Servern durchführen können. 
  
### <a name="manual-upgrade"></a>Manuelle Aktualisierung

Sollte aus irgendeinem Grund die automatisierte Aktualisierung fehlschlagen, können Sie jederzeit eine manuelle Aktualisierung wie folgt durchführen:
  
1. 	Deinstallieren Sie auf dem Listener-Computer den Listener, die Website und den Agent (sofern er auf diesem Server installiert war) über die Systemsteuerung „Programme und Funktionen“.   
    
    > [!NOTE]
    >   Lassen Sie Redis installiert, damit die Daten im Cache während des Aktualisierungsverfahrens erhalten bleiben.
  
2. 	Installieren Sie die neuen Versionen der Komponenten einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Deploy Statistics Manager](deploy.md#BKMK_Deploy).

    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Fixed"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)
    
- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)

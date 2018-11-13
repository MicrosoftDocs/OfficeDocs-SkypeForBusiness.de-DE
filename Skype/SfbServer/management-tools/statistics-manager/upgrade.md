---
title: Aktualisieren von Statistics Manager für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server 2015 zu aktualisieren.'
ms.openlocfilehash: d10dd5cd92fc0d7dbbb3285c43df78e8149f58c0
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295706"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a>Upgrade Statistics Manager for Skype for Business Server 2015
 
**Zusammenfassung:** Gelesen Sie in diesem Thema erfahren, wie ein Upgrade Statistiken Manager für Skype für Business Server 2015.
  
In diesem Thema wird beschrieben, wie zum Aktualisieren einer vorhandenen Installation von Statistiken Manager für Skype für Business Server – ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht. Sie können Leistungsdaten auf Hunderten von Servern kurzen Abständen Abfragen und sofort Anzeigen der Ergebnisse auf der Website Statistiken-Managers. 
  
Weitere Informationen zu Statistiken Manager und die neuen Features in Version 1.1 finden Sie unter [für Statistiken Manager für Skype für Business Server 2015 planen](plan.md) und [Bereitstellen von Statistiken Manager für Skype für Business Server 2015](deploy.md). Informationen zu bekannten Problemen, die in Version 1.1 behoben sind, finden Sie unter [Bekannte Probleme, die in Version 1.1 behoben wurden](upgrade.md#BKMK_Fixed).
  
Es gibt zwei Verfahren für die Aktualisierung:
  
- **Automatische Aktualisierung.** Diese Methode wird ein automatisiertes Skript verwendet. Es ist die einfachste Methode und für alle Upgradeszenarien anwendbar sein.
    
- **Manuelle Aktualisierung.** Diese Methode wird als einen Sicherungsplan im ungewöhnliche Fall bereitgestellt, die die automatische Aktualisierung fehlschlägt.
    
## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie aktualisieren, stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:
  
- Active Listener-Zertifikatfingerabdruck
    
- Listener-Dienst-Kennwort (eingegeben bei der Installation des Listeners und jedes Agents)
    
- SSL-Zertifikat-Konfiguration für die Website
    
## <a name="automated-upgrade"></a>Automatische Aktualisierung

Das Skript wird Ihre aktuelle Zertifikatinformationen sammeln und die alte Version des Produkts deinstallieren Listener Kennwort verwenden aus, und klicken Sie dann die neue Version des Produkts installieren. Die Redis-Instanz auf dem Server installiert wird nicht verschoben werden, damit im Cache gespeicherten Daten über den Upgradeprozess beibehalten werden.
  
1. Platzieren Sie die MSI-Dateien für die neue Version der Agent, Listener und Website zusammen mit der Update-StatsMan.ps1-Skript in einem gemeinsamen Ordner auf dem Computer Listener.
    
2. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Listener-Komponente:
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> Das Statistiken Manager-Dienstkennwort wird unverschlüsselt in der Befehlszeile wie es an das Installationsprogramm übergeben wird angezeigt. Achten Sie darauf, Ihren Bildschirm bei Bedarf entsprechend abzudecken. 
  
1. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Bestätigen Sie dies mit „Ja“.
    
2. Wenn der Listenerdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Ermöglichen der Anwendung, schließen (der Dienst beendet werden soll, Statistiken Manager-Listener).
    
3. Setzen Sie den Installationsprozess fort. Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind. Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.
    
4. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Website-Komponente:
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Bestätigen Sie dies mit „Ja“.
    
6. Wenn der Agent-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren. Warten Sie, bis die Anwendung geschlossen ist (der StatsMan-Agent-Dienst wird beendet).
    
7. Setzen Sie den Installationsprozess fort. Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind. Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.
    
8. Öffnen Sie ein PowerShell-Verwaltungsfenster. Aktualisieren Sie die Agent-Komponente:
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren. Bestätigen Sie dies mit „Ja“.
    
10. Setzen Sie den Installationsprozess fort. Beachten Sie, dass eine Eintragung für den Website-Port bereits im Voraus vorgenommen worden ist. Falls das nicht der Fall ist, tragen Sie den Wert ein, den Sie zuvor gespeichert haben, bevor Sie fortfahren.
    
11. Stellen Sie mithilfe des Browsers sicher, dass die Website wie erwartet funktioniert.
    
> [!NOTE]
> Die Agent-Aktualisierung verwendet werden kann mit der Option - NoPrompt. Dies ermöglicht den Prozess Deinstallation/Installation im Hintergrund, führen Sie Tools wie PSExec zu Remote Ausführen des Upgrades für eine große Anzahl von Servern zu ermöglichen. 
  
### <a name="manual-upgrade"></a>Manuelle Aktualisierung

Sollte aus irgendeinem Grund die automatisierte Aktualisierung fehlschlagen, können Sie jederzeit eine manuelle Aktualisierung wie folgt durchführen:
  
1. 	Deinstallieren Sie auf dem Listener-Computer den Listener, die Website und den Agent (sofern er auf diesem Server installiert war) über die Systemsteuerung „Programme und Funktionen“.   
    
    > [!NOTE]
    >   Lassen Sie Redis installiert, damit die Daten im Cache während des Aktualisierungsverfahrens erhalten bleiben.
  
2. 	Installieren Sie die neuen Versionen der Komponenten einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Deploy Statistics Manager](deploy.md#BKMK_Deploy).
    
## <a name="known-issues-fixed-in-release-11"></a>Bekannte Probleme, die in Version 1.1 behoben wurden
<a name="BKMK_Fixed"> </a>

Die folgenden bekannten Probleme wurden in der Version 1.1 behoben:
  
- Benutzeroberfläche/Server/Agent - zahlreiche erhebliche Zuverlässigkeit und Leistung bei
    
- UI - Main Filtersteuerelement jetzt sortiert ordnungsgemäß mit anderen Fällen (wurde, führt Personen vorstellen bestimmte Servern im System nicht waren, wenn ihr Gesprächspartner direkt)
    
- Server – Serverkomponenten werden jetzt auch auf nicht englischsprachigen Servern installiert.
    
- Server/Agent – In einigen Fällen wurden Agent- und Serverkomponenten im Zusammenhang mit .NET-Fehlern in Bezug auf eine bestimmte Version von .NET 4.0 nicht installiert. Dieser Fehler wurde behoben.
    
- Agent - erweiterte Protokollierung für den StatsMan Agent hinzugefügt. Der Agent wird nicht mehr bei der Installation auf einem Server nicht in der Topologie abstürzen, dies wird jetzt im Ereignisprotokoll zusammen mit zahlreichen möglichen fehlerbedingungen protokolliert werden.
    
- UI - Webclients mithilfe des Chrome-Browsers würde mehrere Anmeldung fordert sehen, wenn mit einem Clientcomputer nicht mit der gleichen Arbeitsgruppe oder Domäne als Statistiken Manager Webserver verbunden. Jetzt sollte pro Sitzung nur eine einzige Anmeldung notwendig sein.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Fixed"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Plan for Statistics Manager for Skype for Business Server 2015](plan.md)
    
- [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md)
    
- [Troubleshoot Statistics Manager for Skype for Business Server 2015](troubleshoot.md)
    
- [Blog zu Statistics Manager für Skype for Business Server](https://blogs.technet.microsoft.com/skypestatsman/)
    


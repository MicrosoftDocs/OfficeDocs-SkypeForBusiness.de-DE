---
title: Übersicht über die Verwaltung für Microsoft Teams-Chatrooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie laufende Wartungen und Vorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams rooms-Systeme für Ihre Benutzer verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd1b552e9a59ee36856d23478a7e414637976889
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085951"
---
# <a name="management-overview"></a>Verwaltung (Übersicht)

Es ist wichtig, dass Sie kontinuierliche Wartung und Vorgänge entwickeln und ausführen, um sicherzustellen, dass Ihre Microsoft Teams rooms-Systeme für Ihre Benutzer verfügbar sind und eine hervorragende Benutzererfahrung bieten. 

## <a name="monitoring"></a>Überwachung 

Das Überwachen von Microsoft Teams rooms Systems umfasst zwei Hauptaktivitäten:

- Überwachung von Geräten, Anwendungen und Peripheriegeräten
- Qualitäts-und Zuverlässigkeitsüberwachung (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Geräte-, Anwendungs-und Peripheriegeräte Überwachung in Microsoft Teams

Um sicherzustellen, dass die Benutzer die Microsoft Teams-Zimmereinheiten verwenden können, müssen die Einheiten aktiviert sein, mit dem Netzwerk verbunden sein, wobei die Microsoft Teams rooms-Anwendung ordnungsgemäß konfiguriert ist und mit funktionierenden Peripheriegeräten verbunden sein. 

Informationen zum Status der Microsoft Teams rooms-Anwendung und verbundenen Peripheriegeräte werden von der Microsoft Teams rooms-Anwendung in das Windows-Ereignisprotokoll geschrieben und in [verstehen der Protokolleinträge](azure-monitor-manage.md#understand-the-log-entries)dokumentiert. 

|**Einstellung**|**Ermöglicht**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1  <br/> |Ermöglicht das Starten von Microsoft Teams-Räumen  <br/> |
|Power Management- \> auf AC, schalten Sie den Bildschirm nach 10 Minuten aus.  <br/> Power Management- \> auf AC, niemals System in den Standbymodus versetzen  <br/> |Ermöglicht Microsoft Teams-Räumen, die angefügten anzeigen zu deaktivieren und automatisch zu aktivieren  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |

Das Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren eines Dateielements](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.
  
## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Wir empfehlen, Microsoft Operations Manager Suite zum Überwachen Ihrer Microsoft Teams rooms-Systeme zu verwenden. Anleitungen zum Einrichten der Überwachung und grundlegender Warnungen finden Sie unter [Bereitstellen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-deploy.md). 

Anhand dieser Anleitung können Sie ein einfach zu bedienendes Dashboard erstellen, um Probleme mit Ihren Microsoft Teams-Räumen für Ihre Bereitstellung zu erkennen. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Sie die Operations Management Suite verwenden, um die Bereitstellung von Microsoft Teams Rooms zu überwachen.</li><li>Wählen Sie die Ziel Verteilerliste aus, die Sie für e-Mail-Benachrichtigungen verwenden möchten.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Ihres Überwachungs Ansatzes für Qualität und Zuverlässigkeit</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualitäts-und Zuverlässigkeitsüberwachung (CQD)

Wir empfehlen, dass Sie die laufenden Überwachungsverfahren zur betrieblichen Qualitäts-und Zuverlässigkeitsüberwachung im Rahmen ihrer Bereitstellung implementieren, um den Trend der Anruf-und Besprechungs Qualität und-Zuverlässigkeit zu überwachen, alle bedenklichen Bereiche zu identifizieren und auf eine Lösung hinzuarbeiten. 

Wenn Sie Ihre Gebäudeinformationen auf CQD hochladen, können Sie die Trends für die Anrufqualität und-Zuverlässigkeit auf pro-Gebäude-Ebene untersuchen, wodurch es einfacher ist, Gebäude zu vergleichen und ihre Aufmerksamkeit auf bestimmte Probleme zu konzentrieren.

Wir empfehlen Ihnen, die [Anrufqualität für Teams](../monitor-call-quality-qos.md) zu überprüfen und zu verfolgen, um Qualitäts-und Zuverlässigkeits Trends zu erkennen und einen Aktionsplan zur Lösung dieser Probleme zu erstellen. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Aktualisieren der Office-Anwendung Microsoft Teams Rooms und Microsoft Teams rooms

Wir empfehlen, dass Sie die Anwendung Microsoft Teams rooms OS und Microsoft Teams rooms aktualisieren, um von Produktupdates und Verbesserungen profitieren zu können. Detaillierte Anleitungen finden Sie unter [Verwalten von Microsoft Teams-Räumen](rooms-operations.md#software-updates). 

## <a name="windows-updates"></a>Windows-Updates

Microsoft Teams rooms läuft unter Windows 10 Enterprise-oder Windows 10 Enterprise (VL) und empfängt dieselben Windows-Updates und Betriebssystem-Builds wie ein Standard-Desktop. Weitere Informationen finden Sie unter [Verwalten von Windows-Updates](updates.md) .


## <a name="troubleshooting"></a>Problembehandlung

Wir empfehlen, dass Sie die Operations Management Suite-Benachrichtigung so einrichten, wie es im obigen Abschnitt beschrieben ist, damit Ihr Betriebsteam und Ihr Helpdesk über alle Probleme mit Microsoft Teams rooms benachrichtigt werden. Die für die PowerShell-Remoteverwaltung verfügbaren Optionen werden in der [Remoteverwaltung mithilfe von PowerShell](rooms-operations.md#remote-management-using-powershell)beschrieben. Für den Fall, dass ein Peripheriegerät getrennt wird, müssen Sie sich möglicherweise auf lokale "Smart Hands" oder IT-Unterstützung verlassen, um die Geräte zu untersuchen und erneut zu verbinden. 

Weitere Informationen zur Problembehandlung und zum Administratormodus finden Sie unter [Administratormodus und Geräteverwaltung](rooms-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Remoteverwaltung einer Microsoft Teams rooms-Konsoleneinstellungen mit einer XML-Konfigurationsdatei](xml-config-file.md)

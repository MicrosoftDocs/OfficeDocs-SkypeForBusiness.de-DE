---
title: Übersicht über die Verwaltung für Microsoft-Teams Räume
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Übersicht über die Verwaltung für Microsoft-Teams Chatrooms.
ms.openlocfilehash: 5ee6d4a3f797ee8dbc5fa54a139b847e549611a1
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362855"
---
# <a name="management-overview"></a>Verwaltung (Übersicht) 

Es ist wichtig, dass Sie entwickeln und Ausführen von laufenden Wartung und erleben Sie die Vorgänge, um sicherzustellen, dass die Microsoft-Teams Chatrooms Systeme für Ihre Benutzer verfügbar sind und einen hervorragendes Benutzer bereitzustellen. 

## <a name="monitoring"></a>Überwachung 

Überwachen von Microsoft-Teams Räume-Systemen umfasst zwei wichtige Aktivitäten:

-  Gerät, Anwendung und Überwachen von Peripheriegeräte

-  Qualität und Zuverlässigkeit Überwachung (CQD)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Microsoft-Teams Chatrooms Gerät, Anwendung und Überwachen von Peripheriegeräte

Die Einheiten, um sicherzustellen, dass Benutzer die Einheiten für die Microsoft-Teams Chatrooms verwenden können, müssen auf, mit dem Netzwerk verbunden ist, mit der Microsoft-Teams Chatrooms Anwendung ordnungsgemäß konfiguriert und funktionsfähig Peripheriegeräte hergestellt werden. 


Informationen zum Status der Anwendung Microsoft Teams Chatrooms und der verbundenen Peripheriegeräte wird von der Anwendung Microsoft Teams Rooms in der Windows-Ereignisprotokoll geschrieben und in [die Protokolleinträge verstehen](azure-monitor-manage.md#understand-the-log-entries)dokumentiert. 

|**Einstellung**|**Ermöglicht**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon automatische Anmeldung = (Dword) 1  <br/> |Microsoft-Teams Chatrooms starten aktiviert  <br/> |
|Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten  <br/> Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus  <br/> |Microsoft-Teams Chatrooms angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert  <br/> |
|net accounts /maxpwage:unlimited  <br/> Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto. Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten. Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.  <br/> |Ermöglicht die ständige Anmeldung des Skype-Kontos  <br/> |
   
Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)erläutert.
  
## <a name="remote-management-using-powershell"></a>Remoteverwaltung mit PowerShell
<a name="RemotePS"> </a>

Es wird empfohlen, dass Sie Microsoft Operations Manager-Suite verwenden, um die Microsoft-Teams Chatrooms Systeme überwachen. Anleitungen für Überwachung und Warnungen grundlegende einrichten finden Sie unter [Bereitstellen von Microsoft Teams Chatrooms Management mit Azure überwachen](azure-monitor-deploy.md). 

Dieser Anleitung können Sie ein Dashboard einfach zu verwendende, um Probleme mit Ihrem Microsoft-Teams Chatrooms Einheiten in Ihrer Bereitstellung zu erkennen erstellen. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Vergewissern Sie sich, dass Sie zum Überwachen der bereitstellungs von Microsoft-Teams Chatrooms Vorgänge Management-Suite verwenden.</li><li>Entscheiden Sie, die Ziel-Verteilerliste, die Sie für e-Mail-Benachrichtigungen verwenden.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>Nächste Schritte|<ul><li>Definieren Sie die Qualität und Zuverlässigkeit Ansatz monitoring.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Qualität und Zuverlässigkeit Überwachung (CQD)

Es wird empfohlen, dass Sie laufenden Betrieb Qualität und Zuverlässigkeit Verfahren als Teil der Bereitstellung zum Überwachen der Trend Anruf und Besprechung Qualität und Zuverlässigkeit, Überwachung, die alle Bereiche identifiziert und arbeiten in Richtung einer Lösung implementieren. 

Wenn Sie Ihre Informationen zum Erstellen von in CQD hochladen können Sie Anruf Qualität und Zuverlässigkeit Trends auf einer Ebene pro Erstellen von untersuchen sie einfach zu vergleichen Gebäude und konzentrieren Sie sich Ihre Aufmerksamkeit zu bestimmten Problemen. Laden Sie weitere Informationen der [Monitor-CQD für Skype für Online-Bereitstellung von Business und Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15). 

Es wird empfohlen, dass Sie überprüfen, und führen Sie die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide) um Trends für die Qualität und Zuverlässigkeit zu identifizieren, und eines Aktionsplans erstellen zu deren Lösung beschrieben. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Aktualisieren der Anwendung Microsoft Teams Chatrooms OS und Microsoft Teams Räume

Es wird empfohlen, dass Sie die Anwendung Microsoft-Teams Chatrooms OS und Microsoft Teams Chatrooms von Produktupdates und Verbesserungen profitieren aktualisieren. Ausführliche Anleitungen finden Sie unter [Verwalten von Microsoft Teams Chatrooms](room-systems-v2-operations.md#software-updates). 

## <a name="windows-updates"></a>Windows-Updates

Microsoft Teams Räume auf Windows 10 Enterprise IoT oder Windows 10 Enterprise (VL) ausgeführt wird und die gleichen Windows-Updates und OS Builds als standard Desktop empfängt. Einzelheiten finden Sie unter [Verwalten von Windows-Updates](updates.md) .


## <a name="troubleshooting"></a>Problembehandlung

Es wird empfohlen, dass Sie Operationen Management Suite Warnungen, wie oben beschrieben, damit Ihre Vorgänge Teams und der Helpdesk Probleme, wenn Microsoft Teams Chatrooms benachrichtigt werden, eingerichtet. Die Optionen für die Remoteverwaltung PowerShell haben Sie werden in die [Remoteverwaltung mithilfe von PowerShell](room-systems-v2-operations.md#remote-management-using-powershell)beschrieben. Den Fall, dass eine Peripheriegeräte getrennt ist, müssen Sie "intelligente Zeiger" lokale oder IT-Support zu untersuchen und schließen Sie die Geräte abhängig. 

Weitere Informationen zu Problembehandlung und Admin-Modus finden Sie unter [Verwalten von Microsoft Teams Chatrooms](room-systems-v2-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)

[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)

[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)

[Verwalten einer Microsoft-Teams Chatrooms Konsolenstamm Remote mit einer XML-Konfigurationsdatei](xml-config-file.md)

---
title: Verwenden von Echtzeit-Telemetrie zur Problembehandlung bei schlechter Besprechungsqualität
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Verwenden Sie Echtzeit-Telemetrie mit Details zu Geräten, Netzwerken und Konnektivität, um Benutzerprobleme mit Microsoft Teams Besprechungen zu beheben.
ms.openlocfilehash: 2730cb41267e8d02572f72d4d9ed7f154e021d9d
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082955"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Verwenden von Echtzeit-Telemetrie zur Problembehandlung bei schlechter Besprechungsqualität

> [!NOTE]
> Dieses Feature wird derzeit bis Ende 2021 als öffentliche Vorschauversion angezeigt. Danach wird das Add-On Advanced Communications für Microsoft Teams für jeden Benutzer benötigt, dessen Telemetrie Sie in Echtzeit anzeigen möchten. Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/advanced-communications).

In diesem Artikel wird erläutert, wie Sie Real-Time Analytics (RTA) verwenden, um Probleme mit Microsoft Teams Besprechungsqualität für einzelne Benutzer zu beheben. Sie können auf ihre Real-Time zugreifen, wenn Sie über eine der folgenden Rollen verfügen:

- Teams-Administrator
- Supportfachmann für die Teams-Kommunikation
- Teams-Kommunikationssupporttechniker

Weitere Informationen zu Teams Administratorrollen finden Sie unter Verwenden Microsoft Teams zum Verwalten [von Teams.](/MicrosoftTeams/using-admin-roles)

Real-Time Mit Real-Time Analytics können IT-Administratoren die geplanten Besprechungen ihrer wichtigen Benutzer sowie Audio-, Video-, Inhaltsfreigabe- und netzwerkbezogene Probleme anzeigen. Als Administrator können Sie diese Telemetrie verwenden, um diese Probleme während Besprechungen zu untersuchen und die Problembehandlung in Echtzeit zu führen.

## <a name="what-is-real-time-analytics"></a>Was ist Real-Time Analyse?

Heute steht die Problembehandlung einzelner Besprechungen für Teams Administratoren über die [Anrufanalyse](use-call-analytics-to-troubleshoot-poor-call-quality.md) nach Dem Ende der Besprechung zur Verfügung. Real-Time mit Analyse können Administratoren geplante Besprechungen behandeln, während sie in Bearbeitung sind.

Real-Time Analyse zeigt detaillierte Informationen zu Teams Besprechungen für jeden Benutzer in Ihrem Office 365-Konto an, die in Echtzeit aktualisiert werden. Sie enthält Informationen zu Geräten, Netzwerk, Konnektivität, Audio-, Video- und Inhaltsfreigabeproblemen, die Administratoren dabei unterstützen, Probleme mit der Anrufqualität effektiver zu behandeln.

Als Teams erhalten Sie Vollzugriff auf alle Echtzeit-Telemetriedaten für jeden Benutzer. Darüber hinaus können Sie den Mitarbeitern Azure Active Directory Rollen zuweisen. Weitere Informationen zu diesen Rollen finden Sie unter [Erteilen von Berechtigungen für Support- und Helpdesk-Mitarbeiter.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Wo finde ich Echtzeit-Problembehandlung für Telemetriedaten pro Benutzer?

Um alle Besprechungsinformationen und Daten für einen Benutzer zu sehen, wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com). Wählen **Sie unter** Benutzer verwalten einen Benutzer aus, und öffnen Sie die Registerkarte & Besprechungen und Anrufe auf der  >  Profilseite des Benutzers.  Unter **Aktuelle Besprechungen** wird eine Liste der Besprechungen angezeigt, an denen der Benutzer innerhalb der letzten 24 Stunden teilgenommen hat, für die *Echtzeit-Telemetrie* zur Verfügung steht, einschließlich aller in Bearbeitung ausgeführten Besprechungen. Wenn die Besprechung noch nicht läuft oder keine Echtzeit-Telemetriedaten enthält, werden diese in Vergangene **Besprechungen angezeigt.**

![Screenshot der Tabelle für kürzliche Besprechungen](media/recent-meetings.png)

Um zusätzliche Informationen zu den Teilnehmern einer aktuellen Besprechung zu erhalten, einschließlich Geräte-, Netzwerk- und Audiostatistiken, suchen Sie die Besprechung **unter** Aktuelle Besprechungen, und wählen Sie den Link unter der Spalte **Teilnehmer** aus.

![Screenshot der Tabelle "Teilnehmerdetails".](media/participant-details.png)

Wenn Sie sich die Telemetrie eines bestimmten Benutzers für eine in Bearbeitung befindende Besprechung, einschließlich Informationen zu Gerät, Netzwerk, Audio, Video und Inhaltsfreigabe, anzeigen möchten, wählen Sie die Besprechungs-ID **aus.**

![Screenshot der Benutzersitzungsdaten der Anrufanalyse](media/real-time-telemetry.png)

## <a name="client-platforms-supported-for-real-time-telemetry"></a>Für Echtzeit-Telemetrie unterstützte Clientplattformen

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams-Geräten mit Unterstützung für Echtzeit-Telemetrie

- MTR - Surface Hub
- MTR – Teams Display
- MTR – Zusammenarbeitsleiste
- IP Telefon Geräte

## <a name="limitations"></a>Einschränkungen

- Echtzeit-Telemetrie ist nur für geplante Besprechungen verfügbar. Für Ad-hoc-Besprechungen wie "Jetztbesprechung", "PSTN", 1:1-Anrufe und Gruppenanrufe steht keine Echtzeit-Telemetrie zur Verfügung.
- Echtzeit-Telemetrie ist nur für Moderatoren eines geplanten Live-Ereignisses verfügbar. Es steht derzeit für Teilnehmer an Live-Veranstaltungen nicht zur Verfügung.
- Echtzeit-Telemetriedaten stehen für eine  Besprechung unter Letzte Besprechungen für 24 Stunden nach Dem Ende der Besprechung zur Verfügung. Nach 24 Stunden können Sie nicht mehr auf die Daten zugreifen, und die Besprechung wechselt zu Vergangene **Besprechungen.** Wenn eine Besprechung länger als 3 Stunden dauert, steht die Echtzeit-Telemetrie nur für die letzten *3 Stunden zur Verfügung.*
- Telemetrie ist in Echtzeit nicht verfügbar, wenn Sie ältere Versionen von Teams. Wenn keine Telemetrie verfügbar ist, versuchen Sie, Ihren Client zu aktualisieren.
- Wenn externe Teilnehmer oder anonyme Benutzer an einer  Besprechung teilnehmen, wird der Anzeigename als nicht verfügbar angezeigt, um die Mandantenübergreifende Privatsphäre zu bewahren.

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse pro Benutzer](set-up-call-analytics.md)

[Verwenden Microsoft Teams Administratorrollen zum Verwalten von Teams.](/MicrosoftTeams/using-admin-roles)

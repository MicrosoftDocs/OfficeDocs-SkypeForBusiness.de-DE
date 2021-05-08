---
title: Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Verwenden Sie Anrufanalysedetails pro Benutzer zu Geräten, Netzwerken und zur Konnektivität, um Benutzerprobleme mit Microsoft Teams und Besprechungen zu beheben.
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760560"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität

In diesem Artikel wird erläutert, wie Sie mit der Anrufanalyse eine schlechte Microsoft Teams-Anruf- oder Besprechungsqualität für einzelne Benutzer beheben können, wenn Sie Teams-Administrator oder Teams-Kommunikationssupportspezialist oder -Techniker sind.

## <a name="call-analytics-permissions"></a>Berechtigungen für die Anrufanalyse

In diesem Artikel wird davon ausgegangen, dass Sie die Anrufanalyse bereits eingerichtet haben. Falls nicht, lesen Sie Einrichten [der Anrufanalyse für Teams.](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>Einführung in die Anrufanalyse

Die Anrufanalyse zeigt detaillierte Informationen zu Teams Anrufen und Besprechungen für jeden Benutzer in Ihrem Office 365 Konto an. Hierzu gehören Informationen zu Geräten, Netzwerken, Konnektivität und Anrufqualität (jeder dieser Faktoren kann ein Faktor für eine schlechte Anruf- oder Besprechungsqualität sein). Wenn Sie Informationen zu Gebäude, Standort und Mandanten hochladen, werden diese Informationen auch für jeden Anruf und jede Besprechung angezeigt. Verwenden Sie die Anrufanalyse, um herauszufinden, warum ein Benutzer eine schlechte Anruf- oder Besprechungserfahrung hatte.

Die Anrufanalyse zeigt Ihnen jeden Wegabschnitt eines Anrufs oder einer Besprechung , z. B. von einem Teilnehmer zu einem zweiten Teilnehmer. Durch Analysieren dieser Details kann ein Teams Problembereiche isolieren und die Ursache für eine schlechte Qualität identifizieren.

Als Teams haben Sie Vollzugriff auf alle Anrufanalysedaten für jeden Benutzer. Darüber hinaus können Sie ihren Mitarbeitern Azure Active Directory Rollen zuweisen. Weitere Informationen zu diesen Rollen finden Sie unter Erteilen [von Berechtigungen für Support- und Helpdesk-Mitarbeiter.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) Verpassen Sie nicht, was [die einzelnen Teams Supportrolle tun?](#what-does-each-teams-support-role-do) unten.

## <a name="where-to-find-per-user-call-analytics"></a>Wo finde ich die Anrufanalyse pro Benutzer?

Um alle Anrufinformationen und Daten für einen Benutzer zu sehen, wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com). Wählen **Sie** unter Benutzer einen Benutzer  aus, und öffnen Sie & auf der Profilseite des Benutzers die Registerkarte & anrufe. Hier finden Sie alle Anrufe und Besprechungen für diesen Benutzer der letzten 30 Tage.

![Screenshot aller Analyse-Benutzerdaten](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Wenn Sie zusätzliche Informationen zu einer bestimmten Sitzung erhalten, einschließlich detaillierter Medien- und Netzwerkstatistiken, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Screenshot der Benutzersitzungsdaten der Anrufanalyse](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Welche Funktion hat Teams support-Rolle?

Der **Teams für Kommunikationsunterstützung** (Unterstützung der Stufe 1) behandelt grundlegende Probleme mit der Anrufqualität. Sie untersuchen keine Probleme mit Besprechungen. Stattdessen sammeln sie verwandte Informationen und eskalieren dann an einen Kommunikationssupporttechniker.

Der **Teams** für Kommunikationsunterstützung (Unterstützung der Stufe 2) sieht Informationen in detaillierten Anrufprotokollen, die für den Experten Teams Kommunikationsunterstützung ausgeblendet sind. In der folgenden Tabelle sind die Informationen aufgeführt, die für die einzelnen Teams Kommunikationsunterstützungsrolle verfügbar sind.

In der folgenden Tabelle ist aufgeführt, welche Informationen pro Benutzer für die einzelnen Kommunikationsunterstützungsrolle verfügbar sind.

|Aktivität|Informationen|Kommunikation<br>Support *Specialist* Sees|Kommunikation<br>*Supporttechniker* sieht|
|---|---|---|---|
|**Anrufe**|Name des Anrufers|Nur der Name des Benutzers, nach dem der Agent gesucht hat.|Benutzername|
||Name des Angerufenen|Wird als „Interner Benutzer" oder „Externer Benutzer" angezeigt.|Name des Angerufenen|
||Telefonnummer des Anrufers|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823. \* \* \*|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823. \* \* \*|
||Telefonnummer des Angerufenen|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823. \* \* \*|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823. \* \* \*|
||**Anrufdetails** \> **Registerkarte "Erweitert"**|Es werden keine Informationen angezeigt.|Es werden alle Details angezeigt, beispielsweise Gerätenamen, IP-Adresse, Subnetzzuordnung und mehr.|
||**Anrufdetails** \> **"Erweitert"** \> **Registerkarte Debuggen**|Es werden keine Informationen angezeigt.|Es werden alle Details angezeigt, beispielsweise DNS-Suffix und SSID.|
|**Besprechungen**|Namen der Teilnehmer|Nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert.|Es werden alle Namen angezeigt.|
||Anzahl der Teilnehmer|Anzahl der Teilnehmer|Anzahl der Teilnehmer|
||Sitzungsdetails|Die Sitzungsdetails werden mit Ausnahmen angezeigt. Angezeigt wird nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.|Die Sitzungsdetails werden angezeigt. Benutzernamen und Sitzungsdetails werden angezeigt. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>Behandeln von Problemen mit der Anrufqualität für Benutzer

1. Öffnen Sie Teams Admin Center ( ), und melden Sie sich mit Ihrem <https://admin.teams.microsoft.com> Teams-Support oder Teams Administratoranmeldeinformationen an.

2. Beginnen Sie **im Dashboard** **in** der Benutzersuche mit der Eingabe des Namens oder der SIP-Adresse des Benutzers, dessen Anrufe Sie behandeln möchten, oder wählen Sie Benutzer anzeigen aus, um eine Liste der Benutzer anzuzeigen. 

3. Wählen Sie den Benutzer aus der Liste aus.

4. Wählen **Sie Anrufverlauf** und dann den Anruf oder die Besprechung aus, für den bzw. die Sie eine Problembehandlung wünschen.

5. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.

   In den Sitzungsdetails für jeden Anruf oder jede Besprechung werden kleinere Probleme gelb angezeigt. Wenn etwas gelb ist, liegt es außerhalb des normalen Bereichs und kann zu dem Problem beitragen, aber es ist wahrscheinlich nicht die Hauptursache für das Problem. Wenn etwas rot ist, ist dies ein erhebliches Problem, und dies ist wahrscheinlich die Hauptursache für die schlechte Anrufqualität in dieser Sitzung.

In seltenen Fällen werden Daten zur Qualität der Benutzererfahrung bei Audiositzungen nicht empfangen. Häufig wird dies durch einen verworfenen Aufruf verursacht oder wenn die Verbindung mit dem Client beendet wird. In diesem Fall ist die Sitzungsbewertung **nicht verfügbar.**

Bei Audiositzungen mit QoE-Daten (Quality of Experience) werden in der folgenden Tabelle die wichtigsten Probleme beschrieben, die eine Sitzung als "schlecht" **qualifizieren.**

|Problem|Bereich|Beschreibung|
|---|---|---|
|Anrufeinrichtung|Sitzung|Der Fehlercode Ms-diag 20-29 gibt an, dass die Anrufeinrichtung fehlgeschlagen ist. Der Benutzer konnte nicht am Anruf oder der Besprechung teilnehmen.|
|Audionetzwerk als "schlecht" klassifizierter Anruf|Sitzung|Probleme mit der Netzwerkqualität (wie Paketverlust, Jitter, NMOS-Degradierung, RTT oder Ausleierungsverhältnis) sind aufgetreten.|
|Gerät funktioniert nicht|Gerät|Ein Gerät funktioniert nicht ordnungsgemäß. Geräte ohne Funktionsverhältnisse sind: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse pro Benutzer](set-up-call-analytics.md)

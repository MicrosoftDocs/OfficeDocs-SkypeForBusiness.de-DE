---
title: Verwenden von Anrufanalysen zur Problembehandlung bei schlechter Anrufqualität
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
description: Verwenden Sie Details zur Anrufanalyse pro Benutzer zu Geräten, Netzwerken und Konnektivität, um Benutzerprobleme mit Microsoft Teams-Anrufen und Besprechungen zu beheben.
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760560"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Verwenden von Anrufanalysen zur Problembehandlung bei schlechter Anrufqualität

In diesem Artikel wird erläutert, wie Sie die Anrufanalyse verwenden, um eine schlechte Anruf- oder Besprechungsqualität von Microsoft Teams für einzelne Benutzer zu beheben, wenn Sie ein Teams-Administrator oder ein Microsoft Teams-Kommunikationssupportspezialist oder -techniker sind.

## <a name="call-analytics-permissions"></a>Anrufanalyseberechtigungen

In diesem Artikel wird davon ausgegangen, dass Sie die Anrufanalyse bereits eingerichtet haben. Wenn nicht, lesen Sie Einrichten der [Anrufanalyse für Teams](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>Einführung in die Anrufanalyse

Die Anrufanalyse zeigt detaillierte Informationen zu Teams-Anrufen und Besprechungen für jeden Benutzer in Ihrem Office 365-Konto an. Sie enthält Informationen zu Geräten, Netzwerken, Konnektivität und Anrufqualität (jeder dieser Faktoren kann ein Faktor bei schlechter Anruf- oder Besprechungsqualität sein). Wenn Sie Gebäude-, Website- und Mandanteninformationen hochladen, werden diese Informationen auch für jeden Anruf und jede Besprechung angezeigt. Verwenden Sie Anrufanalysen, um herauszufinden, warum ein Benutzer eine schlechte Anruf- oder Besprechungserfahrung hatte.

Die Anrufanalyse zeigt Ihnen die einzelnen Teilabschnitte eines Anrufs oder einer Besprechung an, z. B. von einem Teilnehmer bis zu einem zweiten Teilnehmer. Durch Die Analyse dieser Details kann ein Teams-Administrator Problembereiche isolieren und die Ursache für eine schlechte Qualität ermitteln.

Als Teamadministrator erhalten Sie vollen Zugriff auf alle Anrufanalysedaten für jeden Benutzer. Darüber hinaus können Sie Den Mitarbeitern Azure Active Directory-Rollen zuweisen. Weitere Informationen zu diesen Rollen finden Sie unter Erteilen von Berechtigungen [für Support- und Helpdeskmitarbeiter.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) Verpassen Sie [nicht, was die einzelnen Teams-Support-Rollen tun?](#what-does-each-teams-support-role-do) weiter unten.

## <a name="where-to-find-per-user-call-analytics"></a>Wo finden Sie anrufanalytik pro Benutzer

Wenn Sie alle Anrufinformationen und -daten für einen Benutzer sehen, wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com). Wählen **Sie unter** Benutzer einen Benutzer aus, und öffnen Sie dann die Registerkarte Besprechungen & **Anrufe** auf der Profilseite des Benutzers. Hier finden Sie alle Anrufe und Besprechungen für diesen Benutzer für die letzten 30 Tage.

![Screenshot aller Analysebenutzerdaten](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Wenn Sie zusätzliche Informationen zu einer bestimmten Sitzung erhalten, einschließlich detaillierter Medien- und Netzwerkstatistiken, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Screenshot der Benutzersitzungsdaten der Anrufanalyse](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Welche Aufgaben hat jede Teams-Support-Rolle?

Der **Supportspezialist für Die** Kommunikation von Teams (Support der Stufe 1) behandelt grundlegende Probleme bei der Anrufqualität. Sie untersuchen keine Probleme mit Besprechungen. Stattdessen sammeln sie verwandte Informationen und eskalieren dann an einen Kommunikationssupporttechniker.

Der **Supporttechniker für** Die Kommunikation von Teams (Support der Stufe 2) sieht Informationen in detaillierten Anrufprotokollen, die für den Supportspezialisten für Kommunikationen von Teams ausgeblendet sind. In der nachstehenden Tabelle sind die Informationen aufgeführt, die für jede Rolle des Teams-Kommunikationssupports verfügbar sind.

In der folgenden Tabelle ist aufgeführt, welche Informationen pro Benutzer für jede Kommunikationsunterstützungsrolle verfügbar sind.

|Aktivität|Informationen|Was die Kommunikationen<br>*Supportspezialisten* sehen|Was die Kommunikationen<br>*Supporttechniker* sieht|
|---|---|---|---|
|**Anrufe**|Name des Anrufers|Nur der Name des Benutzers, nach dem der Agent gesucht hat.|Benutzername|
||Name des Angerufenen|Wird als „Interner Benutzer" oder „Externer Benutzer" angezeigt.|Name des Angerufenen|
||Telefonnummer des Anrufers|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823 \* \* \* .|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823 \* \* \* .|
||Telefonnummer des Angerufenen|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823 \* \* \* .|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823 \* \* \* .|
||**Anrufdetails** \> **Registerkarte "Erweitert"**|Es werden keine Informationen angezeigt.|Es werden alle Details angezeigt, beispielsweise Gerätenamen, IP-Adresse, Subnetzzuordnung und mehr.|
||**Anrufdetails** \> **Erweitert** \> **Registerkarte Debuggen**|Es werden keine Informationen angezeigt.|Es werden alle Details angezeigt, beispielsweise DNS-Suffix und SSID.|
|**Besprechungen**|Namen der Teilnehmer|Nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert.|Es werden alle Namen angezeigt.|
||Anzahl der Teilnehmer|Anzahl der Teilnehmer|Anzahl der Teilnehmer|
||Sitzungsdetails|Die Sitzungsdetails werden mit Ausnahmen angezeigt. Angezeigt wird nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.|Die Sitzungsdetails werden angezeigt. Benutzernamen und Sitzungsdetails werden angezeigt. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>Behandeln von Problemen mit der Anrufqualität von Benutzern

1. Öffnen Sie das Teams Admin Center ( ), und melden Sie <https://admin.teams.microsoft.com> sich mit Ihrem Teams-Kommunikationssupport oder den Anmeldeinformationen für Teams-Administratoren an.

2. Beginnen Sie im **Dashboard** **in** der Benutzersuche mit der Eingabe des Namens oder der SIP-Adresse des Benutzers, dessen Anrufe Sie beheben möchten, oder wählen Sie Benutzer anzeigen aus, um eine Liste der Benutzer anzuzeigen. 

3. Wählen Sie den Benutzer aus der Liste aus.

4. Wählen **Sie Anrufverlauf** aus, und wählen Sie dann den Anruf oder die Besprechung aus, den Sie behandeln möchten.

5. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.

   In den Sitzungsdetails für jeden Anruf oder jede Besprechung werden kleinere Probleme gelb angezeigt. Wenn etwas gelb ist, liegt es außerhalb des normalen Bereichs, und es kann zu dem Problem beitragen, aber es ist unwahrscheinlich, dass es die Hauptursache für das Problem ist. Wenn etwas rot ist, ist es ein erhebliches Problem, und es ist wahrscheinlich die Hauptursache für die schlechte Anrufqualität für diese Sitzung.

In seltenen Fällen werden Daten zur Qualität der Benutzererfahrung nicht für Audiositzungen empfangen. Dies wird häufig durch einen verworfenen Aufruf oder durch das Beenden der Verbindung mit dem Client verursacht. In diesem Fall ist die Sitzungsbewertung **nicht verfügbar.**

Bei Audiositzungen mit QoE-Daten (Quality of Experience) werden in der folgenden Tabelle wichtige Probleme beschrieben, die eine Sitzung als schlecht **qualifizieren.**

|Problem|Bereich|Beschreibung|
|---|---|---|
|Anrufeinrichtung|Sitzung|Der Fehlercode Ms-diag 20-29 gibt an, dass die Anrufeinrichtung fehlgeschlagen ist. Der Benutzer konnte nicht an dem Anruf oder der Besprechung teilnehmen.|
|Audionetzwerk klassifizierte anrufe|Sitzung|Probleme mit der Netzwerkqualität (z. B. Paketverlust, Jitter, NMOS-Degradierung, RTT oder verdecktes Verhältnis) sind aufgetreten.|
|Gerät funktioniert nicht|Gerät|Ein Gerät funktioniert nicht ordnungsgemäß. Die Nicht-Funktionsverhältnisse des Geräts sind: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse pro Benutzer](set-up-call-analytics.md)

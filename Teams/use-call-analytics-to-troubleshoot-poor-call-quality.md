---
title: Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln
author: CarolynRowe
ms.author: crowe
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
description: Verwenden Sie benutzerspezifische Anrufanalysedetails zu Geräten, Netzwerken und Konnektivität, um Benutzerprobleme mit Microsoft Teams-Anrufen und -Besprechungen zu beheben.
ms.openlocfilehash: 38636d911be55648ec17628bcec7d4cee21358c5
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794313"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln

In diesem Artikel wird erläutert, wie Sie die Anrufanalyse verwenden, um probleme mit schlechter Anruf- oder Besprechungsqualität von Microsoft Teams für einzelne Benutzer zu beheben, wenn Sie die Rolle "Teams-Administrator", "Supportspezialist für Die Teams-Kommunikation" oder "Supporttechniker für die Teams-Kommunikation" innehaben.

## <a name="call-analytics-permissions"></a>Anrufanalyseberechtigungen

In diesem Artikel wird davon ausgegangen, dass Sie die Anrufanalyse bereits eingerichtet haben. Wenn nicht, lesen Sie "Einrichten der [Anrufanalyse für Teams](set-up-call-analytics.md)".

## <a name="introduction-to-call-analytics"></a>Einführung in die Anrufanalyse

Die Anrufanalyse zeigt detaillierte Informationen zu Teams-Anrufen und -Besprechungen für jeden Benutzer in Ihrem Office 365-Konto an. Es enthält Informationen zu Geräten, Netzwerken, Konnektivität und Anrufqualität (jedes dieser Elemente kann ein Faktor für eine schlechte Anruf- oder Besprechungsqualität sein). Wenn Sie Gebäude-, Website- und Mandanteninformationen hochladen, werden diese Informationen auch für jeden Anruf und jede Besprechung angezeigt. Verwenden Sie die Anrufanalyse, um herauszufinden, warum ein Benutzer eine schlechte Anruf- oder Besprechungserfahrung hatte.

Die Anrufanalyse zeigt Ihnen jeden Teil eines Anrufs oder einer Besprechung an, z. B. von einem Teilnehmer bis zu einem zweiten Teilnehmer. Durch die Analyse dieser Details kann ein Teams-Administrator Problembereiche isolieren und die Ursache für eine schlechte Qualität identifizieren.

Als Teams-Administrator erhalten Sie vollumfänglichen Zugriff auf alle Anrufanalysedaten für jeden Benutzer. Darüber hinaus können Sie Azure Active Directory-Rollen zur Unterstützung von Mitarbeitern zuweisen. Weitere Informationen zu diesen Rollen finden Sie unter [Erteilen von Berechtigungen für Support- und Helpdeskmitarbeiter](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff). Verpassen Sie nicht [, was die einzelnen Teams-Supportrollen tun?](#what-does-each-teams-support-role-do) Weiter unten.

## <a name="where-to-find-per-user-call-analytics"></a>Wo finden Sie die Anrufanalyse pro Benutzer

Um alle Anrufinformationen und -daten für einen Benutzer anzuzeigen, wechseln Sie zum [Teams Admin Center](https://admin.teams.microsoft.com). Wählen Sie unter **"Benutzer**" einen Benutzer aus, und öffnen Sie dann die Registerkarte " **Besprechungen & Anrufe** " auf der Profilseite des Benutzers. Hier finden Sie alle Anrufe und Besprechungen für diesen Benutzer für die letzten 30 Tage.

![Screenshot aller Analysebenutzerdaten.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Wenn Sie zusätzliche Informationen zu einer bestimmten Sitzung erhalten möchten, einschließlich detaillierter Medien- und Netzwerkstatistiken, klicken Sie auf eine Sitzung, um die Details anzuzeigen.

![Screenshot der Benutzersitzungsdaten der Anrufanalyse.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>Was bewirkt jede Teams-Supportrolle?

Der **Teams-Kommunikationssupportspezialist** (Stufe 1-Support) behandelt grundlegende Probleme mit der Anrufqualität. Sie untersuchen keine Probleme mit Besprechungen. Stattdessen sammeln sie verwandte Informationen und eskalieren dann an einen Supporttechniker für die Teams-Kommunikation.

Der **Supporttechniker für die Teams-Kommunikation** (Stufe 2-Support) sieht Informationen in detaillierten Anrufprotokollen, die dem Supportspezialisten für die Teams-Kommunikation verborgen sind. In der folgenden Tabelle sind die Informationen aufgeführt, die für jede Teams-Kommunikationsunterstützungsrolle verfügbar sind.

In der folgenden Tabelle erfahren Sie, welche Benutzerinformationen für jede Kommunikationsunterstützungsrolle verfügbar sind.

|Aktivität|Informationen|Was die Kommunikation<br>*Supportspezialist* sieht|Was die Kommunikation<br>*Supporttechniker* sieht|
|---|---|---|---|
|**Anrufe**|Name des Anrufers|Nur der Name des Benutzers, nach dem der Agent gesucht hat.|Benutzername|
||Name des Angerufenen|Wird als „Interner Benutzer" oder „Externer Benutzer" angezeigt.|Name des Angerufenen|
||Telefonnummer des Anrufers|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823\*\*\*.|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823\*\*\*.|
||Telefonnummer des Angerufenen|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823\*\*\*.|Die gesamte Telefonnummer bis auf die letzten drei Ziffern wird durch Sternchen verschleiert. Beispiel: 15552823\*\*\*.|
||**Anrufdetails** \> **Registerkarte "Erweitert** "|Es werden keine Informationen angezeigt.|Es werden alle Details angezeigt, beispielsweise Gerätenamen, IP-Adresse, Subnetzzuordnung und mehr.|
||**Anrufdetails** \> **Erweiterte** \> Registerkarte **"Debuggen** "|Es werden keine Informationen angezeigt.|Es werden alle Details angezeigt, beispielsweise DNS-Suffix und SSID.|
|**Besprechungen**|Namen der Teilnehmer|Nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert.|Es werden alle Namen angezeigt.|
||Anzahl der Teilnehmer|Anzahl der Teilnehmer|Anzahl der Teilnehmer|
||Sitzungsdetails|Die Sitzungsdetails werden mit Ausnahmen angezeigt. Angezeigt wird nur der Name des Benutzers, nach dem der Agent gesucht hat. Andere Teilnehmer werden als „Interner Benutzer" oder „Externer Benutzer" identifiziert. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.|Die Sitzungsdetails werden angezeigt. Benutzernamen und Sitzungsdetails werden angezeigt. Die letzten drei Ziffern der Telefonnummer werden durch Sternchen verschleiert.|
||||

> [!NOTE]
> Die Informationen, die sowohl im Abschnitt "Sonstige" der Registerkarte "Erweitert" als auch auf der Registerkarte "Debuggen" enthalten sind, enthalten Telemetrie- und Dienstdiagnosedaten, die Microsoft-Supporttechnikern helfen sollen. Ohne den Kontext der zusätzlichen Daten, die den Technikern zur Verfügung stehen, können sie redundant, ungenau oder verwirrend erscheinen. Obwohl wir es für fortgeschrittene Benutzer verfügbar machen, die nach einer weiteren Detailebene bei der Behandlung von Anrufproblemen suchen, empfehlen wir nicht, Urteile basierend auf diesen Daten ohne Microsoft-Support zu treffen.

## <a name="troubleshoot-user-call-quality-problems"></a>Behandeln von Problemen mit der Anrufqualität von Benutzern

1. Öffnen Sie das Teams Admin Center (<https://admin.teams.microsoft.com>), und melden Sie sich mit Ihrem Teams-Kommunikationssupport oder Ihren Anmeldeinformationen für Den Teams-Administrator an.

2. Beginnen Sie im **Dashboard** in der **Benutzersuche** mit der Eingabe des Namens oder der SIP-Adresse des Benutzers, dessen Anrufe Sie behandeln möchten, oder wählen Sie " **Benutzer anzeigen"** aus, um eine Liste der Benutzer anzuzeigen.

3. Wählen Sie den Benutzer aus der Liste aus.

4. Wählen Sie **"Anrufverlauf**" und dann den Anruf oder die Besprechung aus, für den Bzw. die Sie eine Problembehandlung ausführen möchten.

5. Wählen Sie die Registerkarte **Erweitert** aus, und suchen Sie dann nach gelben und roten Elementen, die auf eine schlechte Anrufqualität oder auf Verbindungsprobleme hinweisen.

   In den Sitzungsdetails für jeden Anruf oder jede Besprechung werden kleinere Probleme gelb angezeigt. Wenn etwas gelb ist, liegt es außerhalb des normalen Bereichs und kann zu dem Problem beitragen, aber es ist unwahrscheinlich, dass es die Hauptursache für das Problem ist. Wenn etwas rot ist, ist es ein erhebliches Problem, und es ist wahrscheinlich die Hauptursache für die schlechte Anrufqualität für diese Sitzung.

In seltenen Fällen werden die Quality of Experience-Daten für Audiositzungen nicht empfangen. Dies wird häufig durch einen abgebrochenen Anruf oder das Beenden der Verbindung mit dem Client verursacht. In diesem Fall ist die Sitzungsbewertung **nicht verfügbar**.

Bei Audiositzungen mit QoE-Daten (Quality of Experience) werden in der folgenden Tabelle die wichtigsten Probleme beschrieben, die eine Sitzung als **"schlecht**" qualifizieren.

|Problem|Bereich|Beschreibung|
|---|---|---|
|Anrufeinrichtung|Sitzung|Der Fehlercode Ms-diag 20-29 gibt an, dass die Anrufeinrichtung fehlgeschlagen ist. Der Benutzer konnte dem Anruf oder der Besprechung nicht beitreten.|
|Audio network classified poor call|Sitzung|Probleme mit der Netzwerkqualität (z. B. Paketverlust, Jitter, NMOS-Verschlechterung, RTT oder verdecktes Verhältnis) sind aufgetreten.|
|Gerät funktioniert nicht|Gerät|Ein Gerät funktioniert nicht ordnungsgemäß. Nicht funktionierende Geräteverhältnisse sind: <p> DeviceRenderNotFunctioningEventRatio >= 0,005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0,005|
||||

## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse pro Benutzer](set-up-call-analytics.md)

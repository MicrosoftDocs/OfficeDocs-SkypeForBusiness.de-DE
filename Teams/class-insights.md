---
title: Insights für Microsoft Teams for Education für IT-Administratoren
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Ein Leitfaden für IT-Administratoren zu Insights für Microsoft Teams for Education.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e122071a9a4173250a78468126ed576d1e560607
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581496"
---
# <a name="insights-in-teams-for-education-for-it-admins"></a>Insights in Teams for Education für IT-Administratoren

Mit Insights in Microsoft Teams for Education können Lehrkräfte auf Analysen zum digitalen Engagement, Arbeitsauslastung, Noten, Kommunikation und mehr zugreifen.

Insights ist in den Office 365 Education-SKUs A1, A3 und A5 aktiv.

> [!NOTE]
> Lehrkräfte finden [hier](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc) Informationen zur Verwendung von Insights.

## <a name="permissions"></a>Berechtigungen

Lehrkräfte können Insights zu einem öffentlichen Kanal innerhalb eines Klassenteams hinzufügen, indem sie in der App-Leiste "Teams" zu "Apps" navigieren und nach "Insights" suchen.

- Die Schüler werden durch ihre Lizenz identifiziert und **haben keinen Zugriff auf die Registerkarte "Insights"** (auch wenn sie Besitzer des Teams sind).
- Lehrkräfte werden durch Lehrpersonal-Lizenzen definiert.
- Lehrkräfte müssen über eine Lehrpersonal-Lizenz verfügen und Besitzer eines Klassenteams sein, um die Registerkarte "Insights" hinzufügen und anzeigen zu können. Die Registerkarte spiegelt die Aktivitäten aller Mitglieder des Klassenteams wider, die nicht Besitzer des Teams sind (einschließlich Lehrkräfte, die nicht Besitzer des Teams sind).

## <a name="compliance"></a>Compliance

Insights hat branchenführende Compliance-Verpflichtungen und ist als Tier-C-Dienst innerhalb des Office 365 Compliance-Frameworks klassifiziert.

> [!NOTE]
> Besuchen Sie das [Microsoft Trust Center](https://www.microsoft.com/trust-center), um mehr darüber zu erfahren, wie Microsoft Ihre Daten schützt.

## <a name="privacy"></a>Datenschutz

Die im Rahmen von Insights gesammelten und gezeigten Informationen erfüllen mehr als 90 behördliche und Branchenstandards, einschließlich der DSGVO und dem FERPA (Family Education Rights and Privacy Act) für die Sicherheit von Schülern und Kindern und anderer, ähnlicher, privatwirtschaftlich orientierter Vorschriften. Für IT-Administratoren ist es wichtig zu wissen, dass die pro Schüler gesammelten Informationen nur im Klassenkontext verwendet werden sollen, um Lehrkräften die Bestimmung des Klassenverhaltens zu ermöglichen. Die Informationen werden für sinnvolle Lernaktivitäten gesammelt, wie z. B. die Teilnahme an Klassentreffen, das Veröffentlichen von Nachrichten, das Antworten auf Beiträge von Klassenkameraden, die Arbeit an Aufgaben, das Bearbeiten von Dateien und vieles mehr. Wir zeigen zum Beispiel keine Informationen über einen privaten Chat oder einer Anmeldung in Teams.

Unser Ziel ist es, Lehrkräften dabei zu helfen, Engagement zu verstehen und das Lernen der Schüler ins Rampenlicht zu rücken. Während diese Klassenaktivitäten auf Aktionen auf Schülerebene konzentriert werden können, wird diesen Aktionen von Microsoft Teams kein positiver oder negativer Wert zugewiesen, und es gibt keine wertende Identifizierung einzelner Schüler anhand von Kriterien. Die Informationen in Insights informieren Lehrkräfte darüber, dass z. B. ein Schüler während einer bestimmten Zeitspanne nicht aktiv an dem Tool teilgenommen hat oder in der vergangenen Woche alle seine Aufgaben pünktlich erledigt hat. Es liegt weiterhin in der Verantwortung der Lehrkraft, mit dem Schüler und seiner Familie oder seinem Vormund zu interagieren, um den eigentlichen Grund für jede festgestellte Aktivität oder Inaktivität zu ermitteln.

## <a name="data-collection"></a>Datenerfassung

Wir erfassen Daten für Insights, wenn Education Analytics für den Mandanten aktiviert ist. Die Daten werden aus der Aktivität in Teams erfasst, um verwertbare Einblicke für das Lehren und Lernen zu gewinnen.

Standardmäßig ist Education Analytics **Aktiviert**.

Derzeit werden diese Daten aus den folgenden Aktivitätsbereichen von Schülern und Lehrkräften in Klassenteams abgerufen:

|Teams-Komponente  |Erfasste Daten  |
|-----------------|------------------------|------------------------|
|Aufgaben |Eröffnen, Abgeben und Benoten von Aufgaben. |
|Engagement im Kanal |Einen Kanal besuchen, einen Beitrag erstellen, auf einen Beitrag antworten und einen Beitrag mit "Gefällt mir" markieren (ohne Chatinhalt). |
|Dateien |Hochladen, Herunterladen, Zugreifen, Ändern, Kommentieren und Freigeben einer Datei (ohne Dateiinhalt). |
|Besprechungen |Anwesenheit (ohne Besprechungsinhalt) |

## <a name="data-location"></a>Datenspeicherort

Insights-Daten für in Europa ansässige Mandanten werden auf Servern in Europa gespeichert. Daten für in den USA ansässige Mandanten werden auf Servern in den Vereinigten Staaten gespeichert. Wenn Sie Insights verwenden und sich Ihr Office 365-Mandant in einer Region außerhalb Europas oder der Vereinigten Staaten befindet, werden Ihre Daten in der entsprechenden geografischen Region gespeichert.

## <a name="performance-and-reliability"></a>Leistung und Zuverlässigkeit

Insights wurde entwickelt, um eine große Menge an Daten, die bei der Aktivität in Teams erfasst wurden, mit optimaler Leistung und Zuverlässigkeit zu verarbeiten.

Der Prozess der Datenerfassung findet unabhängig von der Installation der Registerkarte "Insights" in Teams auf separaten Servern statt. Die Registerkarte "Insights" oder die persönliche App hat keinen Einfluss auf die Anwendungsleistung oder die Netzwerkbandbreite für Lehrkräfte und Schüler, die die restlichen Teams-Funktionen nutzen.

> [!TIP]
> Lesen Sie [hier](edu-remote-low-bandwidth.md) über die Nutzung von Teams for Education, wenn die Bandbreite gering ist.

## <a name="how-to-delete-your-data"></a>So werden Daten gelöscht

Der Education-Dienst speichert die Aktionen von Schülern und Lehrkräften, die im Zusammenhang mit einem Klassenteam durchgeführt wurden. Diese Daten werden als gemischter Datensatz betrachtet und daher nicht automatisch aus dem Dienst gelöscht, sobald die Benutzerkonten von Schülern oder Lehrkräften aus Ihrer Organisation gelöscht werden.

> [!NOTE]
> Das Löschen von Daten wirkt sich im Laufe der Zeit negativ auf die Fähigkeit von Insights aus, das Engagement von Klassenteams zu analysieren.

- Öffnen Sie ein Supportticket [hier](https://edusupport.microsoft.com/support). Das Supportticket muss eindeutig die Anforderung für einen "GDPR Delete DSR"-Vorgang angeben und die zu löschende Benutzerobjekt-ID enthalten. Es gibt keine Möglichkeit, den Datensatz oder das Zeitfenster des Löschvorgangs zu begrenzen.
- Nach dem Einreichen wartet das Supportticket eine Woche lang in der Warteschlange, um die Richtlinie zur minimalen Aufbewahrung von Daten zu erfüllen. Sie haben während dieser Zeit die Möglichkeit, den Vorgang abzubrechen.
- Nach einer Woche ergreift das Education Analytics-Team Maßnahmen, um sicherzustellen, dass alle Daten im Zusammenhang mit der Benutzer-ID aus dem Dienst gelöscht werden. Der Microsoft-Support überwacht das ICM-Ticket und benachrichtigt Sie, sobald der Löschvorgang abgeschlossen ist, spätestens in 28 Tagen.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Aktivieren und Deaktivieren von Insights mit School Data Sync (SDS)

School Data Sync (SDS) unterstützt bei der Automatisierung des Imports und der Synchronisierung von Student Information System(SIS)-Daten mit Office 365.

Die Verwendung von Insights erfordert nicht die Verwendung von SDS. Sie können sich jedoch jederzeit von Education Analytics abmelden, indem Sie die Umschaltfläche im SDS Admin Center unter **Einstellungen** > **Education Analytics verwalten** deaktivieren.

:::image type="content" source="media/class-insights-on-off.png" alt-text="Die Umschaltfläche zum Aktivieren oder Deaktivieren von Insights.":::

Standardmäßig ist Education Analytics und damit Insights aktiviert. Wenn Sie sich von Analytics abmelden, löschen wir alle für die Registerkarte "Insights" erfassten Daten. Schalten Sie Analytics wieder ein, und wir beginnen mit der Datenerfassung ab dem Zeitpunkt, an dem sie wieder aktiviert wird.

Weitere Informationen: [Insights für Lehrkräfte](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)

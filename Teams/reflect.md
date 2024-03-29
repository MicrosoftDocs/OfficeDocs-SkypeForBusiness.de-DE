---
title: Leitfaden für IT-Administratoren zu Reflect in Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Ein Leitfaden für IT-Administratoren zu Reflect in Microsoft Teams Education
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7cb846cfeafeff3009890b8745e9b13fc6bdd97
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268380"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a>Leitfaden für IT-Administratoren zu Reflect in Microsoft Teams

Dieses Dokument enthält Informationen zu [Reflect](https://aka.ms/reflect), einem festen Bestandteil von [Education Insights in Microsoft Teams](class-insights.md). Reflect hilft Studenten, ihre Stimmung zu erkennen und damit umzugehen durch regelmäßige Gelegenheiten, sich diesbezüglich mitzuteilen und gehört zu werden. Mithilfe von Reflect können Lernende ihr emotionales Vokabular erweitern und ihr Einfühlungsvermögen gegenüber anderen Lernenden verbessern, während Lehrkräfte gleichzeitig wertvolles Feedback für eine gesunde Gemeinschaft erhalten.

Diese kostenlose Check-In-App verwendet Emojis und Zeichen, um Schülern/Studenten zu helfen, emotionale Granularität zu entwickeln. Studien haben gezeigt, dass sich das explizite Erlernen von sozialen und emotionalen Fähigkeiten förderlich auf die Lernleistung und das Verhalten von Schülern/Studenten auswirkt und lebenslang positive Auswirkungen hat.

## <a name="privacy-and-security"></a>Datenschutz und Sicherheit

Reflect befolgt die gleichen Datenschutz- und Sicherheitsstandards wie [Education Insights](class-insights.md), um vertrauliche Informationen von Schülern und Studenten zu schützen.

Reflect erfüllt im Rahmen von Microsoft 365 nationale, regionale und branchenspezifische Vorschriften für die Datenerfassung und -verwendung, einschließlich der [DSGVO](/compliance/regulatory/gdpr) und des [Family Educational Rights and Privacy Act (FERPA)](/compliance/regulatory/offering-ferpa), der die Privatsphäre der Bildungsunterlagen von Schülern schützt.

Die Daten gehören der Bildungseinrichtung, und Microsoft sammelt und speichert die Daten nur. Microsoft-Mitarbeiter können nicht auf die Daten zugreifen oder sie sehen, es sei denn, dies ist im Rahmen der Compliance in einer geprüften Art und Weise zur Aufrechterhaltung des Dienstes, z. B. zur Datenwiederherstellung, erlaubt.

Schüler/Studenten sehen *niemals* die Namen anderer Schüler/Studenten, sondern nur, wie sie geantwortet haben. Zwar können sie die Verteilung der Antworten sehen, jedoch *keine* mit den einzelnen Antworten verknüpften Namen.

> [!NOTE]
> Wenn weniger als fünf Schüler/Studenten antworten, werden den Schülern/Studenten keine Daten angezeigt. Dadurch wird die Wahrscheinlichkeit minimiert, dass Schüler/Studenten die Antworten anderer Personen zuordnen können.

> [!TIP]
> * Besuchen Sie das [Microsoft Trust Center](https://www.microsoft.com/trust-center), um mehr darüber zu erfahren, wie Microsoft Ihre Daten schützt.
> * Besuchen Sie die [Microsoft Compliance-Angebote](/compliance/regulatory/offering-home), um zu erfahren, wie Microsoft 365 Ihrer Einrichtung dabei hilft, die Einhaltung gesetzlicher Compliance-Standards zu erfüllen.

## <a name="data-collection-and-storage"></a>Datenerfassung und -speicherung
Die Daten gehören der Bildungseinrichtung, und Microsoft erfasst und speichert die Daten nur. Microsoft-Mitarbeiter können nicht auf die Daten zugreifen oder sie sehen, es sei denn, dies ist im Rahmen der Compliance in einer geprüften Art und Weise zur Aufrechterhaltung des Dienstes, z. B. zur Datenwiederherstellung, erlaubt.

Die Daten werden in Education Insights gespeichert. Standardmäßig ist Education Insights aktiviert. Wenn Sie diese Option deaktivieren, **löschen wir alle für Reflect erfassten Daten**. Wenn Sie Education Insights reaktivieren, wird die Datenerfassung ab dem Zeitpunkt der Reaktivierung wiederaufgenommen.

Im [Leitfaden für IT-Administratoren zu Education Insights](class-insights.md) erfahren Sie, wie Education Insights funktioniert (einschließlich Speicherorten) und wie Sie [Education Insights deaktivieren oder aktiveren](class-insights.md#turn-on-and-off-insights) können, wenn Sie die Daten löschen oder den Dienst aktivieren möchten.

In Reflect werden Daten von Schülern/Studenten erfasst, jedoch keine Gastdaten. **Wenn ein Schüler/Student als Gast definiert ist, werden seine Daten nicht erfasst.**

## <a name="enable-reflect"></a>Aktivieren von Reflect
Wenn Sie die App-Setuprichtlinie für Ihre Bildungseinrichtung verwalten, stellen Sie sicher, dass Reflect in Ihrem Mandanten *zulässig* ist. Sie können Reflect auch über das Microsoft Teams Admin Center zu den jeweiligen Kursteams hinzufügen.

Um einem Benutzer die Installation von und Interaktion mit einer App zu ermöglichen, müssen Sie die App auf Organisationsebene auf der Seite **Apps verwalten** und in der dem Benutzer zugewiesenen **App-Berechtigungsrichtlinie** zulassen.

Wenn Sie zuvor festgelegt haben, dass jede App erlaubt werden muss, wechseln Sie zur Seite "Apps verwalten", und wählen Sie für Reflect "Zulassen" aus. **Wenn Sie eine App blockieren, wird diese in Microsoft Teams keinem Benutzer in Ihrer Organisation angezeigt.**

> [!NOTE]
> Für den Zugriff auf die Reflect-App benötigen Sie eine A1-, A3- oder A5-Lizenz für Microsoft 365.

> [!TIP]
> Weitere Details finden Sie unter [Zulassen oder Hinzufügen einer App zu einem Kursteam](manage-apps.md#allow-and-block-apps).

## <a name="where-do-educators-find-reflect"></a>Wo finden Lehrkräfte Reflect?
Reflect ist standardmäßig in jedem Kurs- oder Mitarbeiterteam verfügbar. Um auf die App zuzugreifen, navigieren Sie zu Ihrem gewünschten Team, und wählen Sie dann die Registerkarte „Reflect“ aus.

> [!TIP]
> Weitere Einzelheiten finden Sie auf der [Reflect-Supportseite](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a). Diese Seite enthält Richtlinien für Lehrkräfte und Schüler und hilft bei der Erstellung ihres ersten Reflect-Check-ins.

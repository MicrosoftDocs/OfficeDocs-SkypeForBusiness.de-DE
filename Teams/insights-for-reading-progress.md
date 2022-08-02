---
title: Grundlegendes zu Insights für Lesefortschrittsempfehlungen
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Erfahren Sie, wie Insights-Daten im Lesefortschritt verwendet werden, um die Lesefähigkeit der Kursteilnehmer zu verbessern.
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157883"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>Grundlegendes zu Insights für Lesefortschrittsempfehlungen

Dieser Artikel richtet sich an IT-Administratoren im Bildungsbereich, die verstehen möchten, wie Insights-Daten für Lesefortschrittsempfehlungen verwendet werden.

Insights ermöglicht Es Lehrkräften, die Leseflussfähigkeit ihrer Schüler mithilfe des Lesefortschritts nachzuverfolgen, einem Tool, mit dem Schüler laut vorlesen und Fehler automatisch erkennen können.

Der Lesefortschritt stellt die folgenden Arten von Aufgaben für Leseaufgaben bereit:

- **Kontextwörter: Übungswörter**, die basierend auf den Wörtern empfohlen werden, die Kursteilnehmer in früheren Aufgaben zum Lesefortschritt falsch angegeben haben.
- **Korrelierte Wörter**: Übungswörter, die basierend auf Fehlern empfohlen werden, die Schülern mit der gleichen Art von Leseproblemen gemeinsam sind.

Anleitungen für Lehrkräfte zur Verwendung von Insights für den Lesefortschritt finden [Sie unter Erstellen von Aufgaben zur Lesefortschritts-Herausforderung mit Insights](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe).

## <a name="how-does-microsoft-recommend-correlated-words"></a>Wie empfiehlt Microsoft korrelierte Wörter?

Korrelierte Wörter sind personalisierte, empfohlene Wörter, die Insights for Education für andere Schüler, die ähnliche Lesemuster teilen, als herausfordernd identifiziert hat.

Korrelierte Wörter basieren auf einer Machine Learning-Technik namens **Collaborative Filtering**.

- Insights analysiert die Lesedaten von Kursteilnehmern über Klassen hinweg, die Ihren geografischen Bereich und Ihre Sprache teilen, um Cluster von Wörtern zu identifizieren, die für Schüler/Studenten eine Herausforderung darstellen.

- Angesichts einer Reihe anspruchsvoller Wörter identifiziert Insights auch ähnliche Cluster und verwendet diese, um Kursteilnehmern andere Wörter für gezieltes Üben zu empfehlen.

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Hält Microsoft die Daten der Kursteilnehmer privat und sicher?

Microsoft verpflichtet sich, Daten verantwortungsvoll und ethisch zu verwenden.

Hier sind einige der Maßnahmen, die zum Erstellen dieses Features ergriffen werden:

- Die Analyse von Studentendaten erfolgt auf augenfreundliche Weise, d. h., Microsoft hat keinen Zugriff auf die Lesedaten der Kursteilnehmer, nur auf die Analyseergebnisse.

- Mandantenadministratoren können sich vom Datenanalyseprozess abmelden, indem sie die [Umschaltfläche "Erweiterte Rückschlüsse"](class-insights.md#turn-on-and-off-advanced-inferences-in-insights) deaktivieren.

- Unangemessene Wörter werden aus den Empfehlungslisten für **korrelierte Wörter** herausgefiltert. Dies geschieht durch eine Kombination aus Data Science-Techniken und dem Blockieren bekannter problematischer Wörter. Dieser Vorgang ist jedoch kein Fehlernachweis. Lehrkräfte sollten die Empfehlungen überprüfen.

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Was sind die Einschränkungen der Wortempfehlungen von Insights?

- Word-Empfehlungen für den Lesefortschritt werden derzeit in [diesen Sprachen](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages) unterstützt.

- Korrelierte Wörter werden nur in Kursen mit mindestens fünf Kursteilnehmern angezeigt, die Lesefortschritts-Aufgaben eingereicht haben.

- Insights empfiehlt möglicherweise keine neuen Wörter in Fällen, in denen es keine Schüler mit ähnlichen, aber nicht identischen Fehlermustern gibt.

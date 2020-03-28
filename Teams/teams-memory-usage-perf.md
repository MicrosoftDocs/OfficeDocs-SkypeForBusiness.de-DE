---
title: Verwendung des Arbeitsspeichers durch Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Wie Microsoft Teams den Systemspeicher verwendet und warum die Speicherauslastung zwischen der Desktopanwendung und der Webanwendung identisch ist.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59940eafcdb6f86961b3cd6805cb9c5bb40f9fb2
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033399"
---
# <a name="how-microsoft-teams-uses-memory"></a>Verwendung des Arbeitsspeichers durch Microsoft Teams

Einige Microsoft Teams-Benutzer haben Fragen zur Verwendung von Arbeitsspeicher durch Teams. In diesem Artikel wird beschrieben, wie Arbeitsspeicher von Teams verwendet wird und warum die Team-Desktopanwendung (app) und die Teams-Web-App nicht verhindern, dass andere apps und Arbeitsauslastungen auf demselben Computer genügend Arbeitsspeicher aufweisen, um optimal ausgeführt zu werden. Teams ist für die Nutzung der modernen Web-Technologie konzipiert. Um dies zu erreichen, wurde der Desktop-Client von Teams auf Electron entwickelt, der Chrom für das Rendering verwendet. Dabei handelt es sich um das gleiche Rendering-Modul hinter vielen der heute beliebtesten Browser, einschließlich Edge und Chrome.

## <a name="how-teams-works"></a>Funktionsweise von Teams

Teams, die auf Elektronen entwickelt wurden, ermöglichen eine schnellere Entwicklung, und es wird auch die Parität zwischen den Teams-Versionen für verschiedene Betriebssysteme (Windows, Mac und Linux) beibehalten. Diese Parität ist möglich, da Elektron und Chrom eine ähnliche CodeBase in allen Versionen aufweisen. Ein weiterer Vorteil dieser Architektur ist ein ähnliches Speicher Nutzungsprofil zwischen der Team Web App und der Desktop Version. Sowohl die Web-App als auch die Desktop Versionen verwenden den Arbeitsspeicher auf ähnliche Weise wie in einem Browser. Weitere Informationen zu Electron finden Sie auf [der](https://electronjs.org/)Website.

Weitere Informationen finden Sie unter [Chrom Speichernutzung](https://www.chromium.org/developers/memory-usage-backgrounder) und [Schlüsselkonzepte im Chrom Speicher](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .

Die folgende Abbildung zeigt die parallele Speichernutzung der Team-Desktop-App für Windows und der Team-Web-App (in diesem Beispiel, die in Google Chrome ausgeführt wird).

![Arbeitsspeichernutzung von Teams-Desktop-App und Web App](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Speicherauslastung in Teams

Es ist wichtig, das *erwartete* Verhalten von Teams zu verstehen, wenn es um den Systemspeicher geht, und die Symptome wirklich problematischer Systemspeicher Probleme zu erkennen.

### <a name="expected-memory-usage-by-teams"></a>Erwartete Speicherauslastung durch Teams

Unabhängig davon, ob Sie die Desktop-App "Teams" oder die Team-Web-App ausführen, erkennt Chrom, wie viel Systemarbeitsspeicher verfügbar ist, und nutzt genügend Arbeitsspeicher, um die Rendering-Funktionalität zu optimieren. Wenn andere apps oder Dienste Systemspeicher erfordern, gibt Chrom Speicher für diese Prozesse aus. Chrom optimiert die Arbeitsspeichernutzung von Teams kontinuierlich, um die Leistung von Teams zu optimieren, ohne dass sich dies auf etwas anderes auswirkt, das derzeit ausgeführt wird.

Auf diese Weise können ähnliche Chrom Arbeitslasten je nach verfügbarem Systemspeicher unterschiedliche Speichermengen verwenden.

Das folgende Diagramm zeigt die Speicherauslastung von Teams auf vier separaten Systemen, wobei jeweils unterschiedliche Speichermengen zur Verfügung stehen. Jedes System verarbeitet ähnliche Arbeitslasten (die gleichen apps werden geöffnet und ausgeführt).

![Arbeitsspeichernutzung in Teams auf unterschiedlichen Systemen](media/teams-memory-usage.png)

Wenn Computer mehr Speicher haben, wird dieser Speicher von Teams verwendet. In Systemen, in denen der Arbeitsspeicher knapp ist, werden die Teams kleiner verwendet.

### <a name="symptoms-of-system-memory-issues"></a>Symptome von Problemen mit dem Systemspeicher

Wenn ein oder mehrere der folgenden Symptome auf Ihrem Computer angezeigt wird, kann ein schwerwiegender Systemspeicher auftreten:

- Hohe Speicherauslastung, wenn mehrere große Anwendungen gleichzeitig ausgeführt werden.
- Langsame Systemleistung oder hängende Anwendungen
- Dauerhafte Nutzung des gesamten Systemspeichers von 90% oder höher in allen apps. Bei dieser Speicherauslastung sollten Teams anderen apps und Arbeitsauslastungen Speicher zurückgeben. Nachhaltige Speichernutzung von 90% kann bedeuten, dass Teams dem System keinen Arbeitsspeicher zurückgeben, was auf ein Problem hindeutet.

Die folgenden Bilder zeigen Beispiele für Ansichten im Task-Manager, wenn die Systemspeicherauslastung ungewöhnlich groß ist.

![Ansicht der Arbeitsspeichernutzung in Teams im Task-Manager](media/teams-memory-high-mem-process-list.png)

![Arbeitsspeicher Auslastungsdiagramm für Teams im Task-Manager](media/teams-memory-high-mem-process-list2.png)

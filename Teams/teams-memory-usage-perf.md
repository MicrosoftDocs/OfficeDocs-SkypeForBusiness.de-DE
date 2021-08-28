---
title: Verwendung des Arbeitsspeichers durch Microsoft Teams
author: msdmaguire
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Erfahren Sie Microsoft Teams die Speicherauslastung des Systems und warum die Speicherauslastung zwischen der Desktopanwendung und der Webanwendung identisch ist.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 7e0606848d5a6d3816ef0c6d16bb46e069b0941b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625827"
---
# <a name="how-microsoft-teams-uses-memory"></a>Verwendung des Arbeitsspeichers durch Microsoft Teams

Einige Microsoft Teams Benutzer haben Fragen zur Verwendung Teams Speichers. In diesem Artikel wird beschrieben, wie der Arbeitsspeicher von Teams verwendet wird und warum die Teams-Desktopanwendung (App) und die Teams-Web-App nicht verhindern, dass andere Apps und Workloads auf demselben Computer über genügend Arbeitsspeicher für eine optimale Ausführung verfügbar sind. Teams ist für die Verwendung moderner Webtechnologien konzipiert. Um dies zu erreichen, Teams der Desktopclient für Windows-Apps auf der Website "Electron" entwickelt, die Chromium Rendern verwendet. Dies ist das gleiche Renderingmodul hinter vielen der beliebtesten Browser, darunter Edge und Chrome.

## <a name="how-teams-works"></a>Funktionsweise Teams E-Teams

Teams die Entwicklung auf Basis von Electron ermöglicht eine schnellere Entwicklung und sorgt außerdem für eine Parität zwischen Teams-Versionen verschiedener Betriebssysteme (Windows, Mac und Linux). Diese Parität ist möglich, da "Electron" und Chromium über alle Versionen hinweg eine ähnliche Codebasis unterhalten. Ein weiterer Vorteil dieser Architektur ist ein ähnliches Speicherauslastungsprofil zwischen der Teams Web App und der Desktopversion. Sowohl die Web-App als auch die Desktopversionen nutzen Arbeitsspeicher auf ähnliche Weise wie ein Browser. Weitere Informationen zu Electron finden Sie [auf der jeweiligen Website.](https://electronjs.org/)

Weitere [Chromium finden](https://www.chromium.org/developers/memory-usage-backgrounder) Sie unter Verwenden des Speichers und wichtige Konzepte im [Chrome-Speicher.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)

Die folgende Abbildung zeigt die Speicherauslastung der Teams-Desktop-App für Windows und der Teams Web-App (in diesem Beispiel in Google Chrome).

![Teams speicherauslastung für die Desktop-App und Web-App](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Speicherauslastung in Teams

Es ist wichtig,  das erwartete Verhalten von Teams Systemspeicher zu verstehen und die Symptome von wirklich problematischen Systemspeicherproblemen zu kennen.

### <a name="expected-memory-usage-by-teams"></a>Erwartete Speicherauslastung durch Teams

Unabhängig davon, ob Sie die Teams-Desktop-App oder die Teams-Web-App ausführen, erkennt Chromium, wie viel Systemspeicher verfügbar ist, und nutzt ausreichend Speicherplatz, um die Renderingerfahrung zu optimieren. Wenn andere Apps oder Dienste Systemspeicher erfordern, Chromium Sie diesen Prozessen Arbeitsspeicher. Chromium die Teams fortlaufend optimieren, um die Teams leistung zu optimieren, ohne dass sich dies auf andere derzeit ausgeführte Ressourcen auswirken kann.

Auf diese Weise können Chromium Arbeitslasten abhängig von der Menge des verfügbaren Systemspeichers unterschiedliche Speichermengen nutzen.

Das folgende Diagramm stellt die Speicherauslastung durch die Teams auf vier separaten Systemen mit jeweils unterschiedlichen Mengen verfügbarer Speichermengen bereit. Jedes der Systeme verarbeitet ähnliche Workloads (dieselben Apps werden geöffnet und ausgeführt).

![Teams der Speicherauslastung verschiedener Systeme](media/teams-memory-usage.png)

Wenn Computer über mehr Arbeitsspeicher verfügen, Teams Computer diesen Speicher aus. Bei Systemen, in denen Arbeitsspeicher vorhanden ist, Teams weniger Speicherplatz ein.

### <a name="symptoms-of-system-memory-issues"></a>Symptome von Problemen mit dem Systemspeicher

Wenn Sie eines oder mehrere der folgenden Symptome auf Ihrem Computer sehen, könnte ein schwerwiegendes Systemspeicherproblem auftreten:

- Hohe Arbeitsspeichernutzung, wenn mehrere große Anwendungen gleichzeitig ausgeführt werden.
- Langsame Systemleistung oder hängende Anwendungen.
- Dauerhafte allgemeine Speicherauslastung des Systems von 90 % oder höher für alle Apps. Bei dieser Menge an Arbeitsspeicher sollte Teams anderen Apps und Workloads wieder Arbeitsspeicher geben. Eine dauerhafte Speicherauslastung von 90 % könnte bedeuten, Teams dem System keinen Arbeitsspeicher zurückgibt, was auf ein Problem hinweist.

Die folgenden Abbildungen zeigen Beispiele für Ansichten im Task-Manager, wenn die Arbeitsspeicherauslastung des Systems ungewöhnlich hoch ist.

![Teams der Speicherauslastung im Task-Manager](media/teams-memory-high-mem-process-list.png)

![Teams zur Arbeitsspeicherauslastung im Task-Manager](media/teams-memory-high-mem-process-list2.png)

---
title: Verwendung des Arbeitsspeichers durch Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Erfahren Sie mehr über die Systemspeicherauslastung von Microsoft Teams und warum die Speichernutzung zwischen der Desktopanwendung und der Webanwendung identisch ist.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: cb2405c50d758c5879bcc44451a0ce9c50a7d614
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268140"
---
# <a name="how-microsoft-teams-uses-memory"></a>Verwendung des Arbeitsspeichers durch Microsoft Teams

Einige Microsoft Teams-Benutzer haben Fragen zur Verwendung des Arbeitsspeichers durch Teams. In diesem Artikel wird beschrieben, wie Arbeitsspeicher von Teams verwendet wird und warum die Teams-Desktopanwendung (App) und die Teams-Web-App nicht verhindern, dass andere Apps und Workloads auf demselben Computer über genügend Arbeitsspeicher verfügen, um optimal ausgeführt zu werden. Teams wurde für die Verwendung moderner Webtechnologie entwickelt. Um dies zu erreichen, wurde der Teams-Desktopclient auf Electron entwickelt, der Chromium zum Rendern verwendet. Dies ist das gleiche Renderingmodul hinter vielen der beliebtesten Browser von heute, einschließlich Edge und Chrome.

## <a name="how-teams-works"></a>Funktionsweise von Teams

Teams, die auf Electron entworfen wurden, ermöglicht eine schnellere Entwicklung und hält auch die Parität zwischen Teams-Versionen über verschiedene Betriebssysteme (Windows, Mac und Linux) hinweg aufrecht. Diese Parität ist möglich, da Electron und Chromium eine ähnliche Codebasis in allen Versionen beibehalten. Ein weiterer Vorteil dieser Architektur ist ein ähnliches Speichernutzungsprofil zwischen der Teams-Web-App und der Desktopversion. Sowohl die Web-App als auch die Desktopversionen verwenden Speicher auf ähnliche Weise wie ein Browser sie verwenden würde. Weitere Informationen zu Electron finden Sie auf [ihrer Website](https://electronjs.org/).

Weitere Informationen finden Sie [unter Chromium Speichernutzung](https://www.chromium.org/developers/memory-usage-backgrounder) und [Schlüsselkonzepte im Chrome-Speicher](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md).

Die folgende Abbildung zeigt die parallele Speicherauslastung der Teams-Desktop-App für Windows und der Teams-Web-App (in diesem Beispiel wird in Google Chrome ausgeführt).

![Teams-Speicherauslastung für die Desktop-App und Web-App.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Speicherauslastung in Teams

Es ist wichtig, das *erwartete* Verhalten von Teams in Bezug auf den Systemspeicher zu verstehen und die Symptome wirklich problematischer Systemspeicherprobleme zu kennen.

### <a name="expected-memory-usage-by-teams"></a>Speicherauslastung durch Teams erwartet

Unabhängig davon, ob Sie die Teams-Desktop-App oder die Teams-Web-App ausführen, erkennt Chromium, wie viel Systemspeicher verfügbar ist, und nutzt genügend Arbeitsspeicher, um die Renderingumgebung zu optimieren. Wenn andere Apps oder Dienste Systemspeicher benötigen, gibt Chromium Speicher für diese Prozesse auf. Chromium optimiert die Speicherauslastung von Teams kontinuierlich, um die Leistung von Teams zu optimieren, ohne dass sich dies auf andere derzeit ausgeführte Elemente auswirkt.

Auf diese Weise können ähnliche Chromium Workloads je nach verfügbarem Systemspeicher unterschiedliche Speichermengen nutzen.

Das folgende Diagramm zeigt die Speicherauslastung von Teams auf vier separaten Systemen mit jeweils unterschiedlichen Verfügbaren Arbeitsspeichermengen. Jedes der Systeme verarbeitet ähnliche Workloads (die gleichen Apps werden geöffnet und ausgeführt).

![Teams-Speicherauslastung über verschiedene Systeme hinweg.](media/teams-memory-usage.png)

Wenn Computer mehr Arbeitsspeicher haben, verwendet Teams diesen Speicher. In Systemen, in denen Arbeitsspeicher knapp ist, verwendet Teams weniger.

### <a name="symptoms-of-system-memory-issues"></a>Symptome von Systemgedächtnisproblemen

Wenn auf Ihrem Computer eines oder mehrere der folgenden Symptome auftreten, könnte ein schwerwiegendes Systemspeicherproblem auftreten:

- Hoher Speichereinsatz, wenn mehrere große Anwendungen gleichzeitig ausgeführt werden.
- Langsame Systemleistung oder hängende Anwendungen.
- Anhaltende Gesamtauslastung des Systemspeichers von 90 % oder höher für alle Apps. Mit dieser Menge an Arbeitsspeicher sollte Microsoft Teams Arbeitsspeicher an andere Apps und Workloads zurückgeben. Eine dauerhafte Speicherauslastung von 90 % könnte bedeuten, dass Teams dem System keinen Arbeitsspeicher zurückgibt, was auf ein Problem hindeutet.

Die folgenden Bilder zeigen Beispiele für Ansichten im Task-Manager, wenn die Speicherauslastung des Systems ungewöhnlich hoch ist.

![Teams-Speichernutzungsansicht im Task-Manager.](media/teams-memory-high-mem-process-list.png)

![Teams-Speicherauslastungsdiagramm im Task-Manager.](media/teams-memory-high-mem-process-list2.png)

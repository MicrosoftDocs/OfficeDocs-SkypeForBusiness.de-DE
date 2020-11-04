---
title: Verwendung des Arbeitsspeichers durch Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Erfahren Sie mehr über die Verwendung von Microsoft Teams für den Systemspeicher, und warum die Speicherauslastung zwischen der Desktopanwendung und der Webanwendung identisch ist.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878719"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="11545-103">Verwendung des Arbeitsspeichers durch Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11545-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="11545-104">Einige Microsoft Teams-Benutzer haben Fragen zur Verwendung von Arbeitsspeicher durch Teams.</span><span class="sxs-lookup"><span data-stu-id="11545-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="11545-105">In diesem Artikel wird beschrieben, wie Arbeitsspeicher von Teams verwendet wird und warum die Team-Desktopanwendung (app) und die Teams-Web-App nicht verhindern, dass andere apps und Arbeitsauslastungen auf demselben Computer genügend Arbeitsspeicher aufweisen, um optimal ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="11545-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="11545-106">Teams ist für die Nutzung der modernen Web-Technologie konzipiert.</span><span class="sxs-lookup"><span data-stu-id="11545-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="11545-107">Um dies zu erreichen, wurde der Desktop-Client von Teams auf Electron entwickelt, der Chrom für das Rendering verwendet.</span><span class="sxs-lookup"><span data-stu-id="11545-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="11545-108">Dabei handelt es sich um das gleiche Rendering-Modul hinter vielen der heute beliebtesten Browser, einschließlich Edge und Chrome.</span><span class="sxs-lookup"><span data-stu-id="11545-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="11545-109">Funktionsweise von Teams</span><span class="sxs-lookup"><span data-stu-id="11545-109">How Teams works</span></span>

<span data-ttu-id="11545-110">Teams, die auf Elektronen entwickelt wurden, ermöglichen eine schnellere Entwicklung, und es wird auch die Parität zwischen den Teams-Versionen für verschiedene Betriebssysteme (Windows, Mac und Linux) beibehalten.</span><span class="sxs-lookup"><span data-stu-id="11545-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="11545-111">Diese Parität ist möglich, da Elektron und Chrom eine ähnliche CodeBase in allen Versionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="11545-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="11545-112">Ein weiterer Vorteil dieser Architektur ist ein ähnliches Speicher Nutzungsprofil zwischen der Team Web App und der Desktop Version.</span><span class="sxs-lookup"><span data-stu-id="11545-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="11545-113">Sowohl die Web-App als auch die Desktop Versionen verwenden den Arbeitsspeicher auf ähnliche Weise wie in einem Browser.</span><span class="sxs-lookup"><span data-stu-id="11545-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="11545-114">Weitere Informationen zu Electron finden Sie auf [der](https://electronjs.org/)Website.</span><span class="sxs-lookup"><span data-stu-id="11545-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="11545-115">Weitere Informationen finden Sie unter [Chrom Speichernutzung](https://www.chromium.org/developers/memory-usage-backgrounder) und [Schlüsselkonzepte im Chrom Speicher](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .</span><span class="sxs-lookup"><span data-stu-id="11545-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="11545-116">Die folgende Abbildung zeigt die parallele Speichernutzung der Team-Desktop-App für Windows und der Team-Web-App (in diesem Beispiel, die in Google Chrome ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="11545-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Arbeitsspeicherauslastung von Teams für die Desktop-App und Web-App](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="11545-118">Speicherauslastung in Teams</span><span class="sxs-lookup"><span data-stu-id="11545-118">Memory usage in Teams</span></span>

<span data-ttu-id="11545-119">Es ist wichtig, das *erwartete* Verhalten von Teams zu verstehen, wenn es um den Systemspeicher geht, und die Symptome wirklich problematischer Systemspeicher Probleme zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="11545-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="11545-120">Erwartete Speicherauslastung durch Teams</span><span class="sxs-lookup"><span data-stu-id="11545-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="11545-121">Unabhängig davon, ob Sie die Desktop-App "Teams" oder die Team-Web-App ausführen, erkennt Chrom, wie viel Systemarbeitsspeicher verfügbar ist, und nutzt genügend Arbeitsspeicher, um die Rendering-Funktionalität zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="11545-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="11545-122">Wenn andere apps oder Dienste Systemspeicher erfordern, gibt Chrom Speicher für diese Prozesse aus.</span><span class="sxs-lookup"><span data-stu-id="11545-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="11545-123">Chrom optimiert die Arbeitsspeichernutzung von Teams kontinuierlich, um die Leistung von Teams zu optimieren, ohne dass sich dies auf etwas anderes auswirkt, das derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11545-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="11545-124">Auf diese Weise können ähnliche Chrom Arbeitslasten je nach verfügbarem Systemspeicher unterschiedliche Speichermengen verwenden.</span><span class="sxs-lookup"><span data-stu-id="11545-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="11545-125">Das folgende Diagramm zeigt die Speicherauslastung von Teams auf vier separaten Systemen, wobei jeweils unterschiedliche Speichermengen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="11545-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="11545-126">Jedes System verarbeitet ähnliche Arbeitslasten (die gleichen apps werden geöffnet und ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="11545-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Arbeitsspeichernutzung in Teams auf unterschiedlichen Systemen](media/teams-memory-usage.png)

<span data-ttu-id="11545-128">Wenn Computer mehr Speicher haben, wird dieser Speicher von Teams verwendet.</span><span class="sxs-lookup"><span data-stu-id="11545-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="11545-129">In Systemen, in denen der Arbeitsspeicher knapp ist, werden die Teams kleiner verwendet.</span><span class="sxs-lookup"><span data-stu-id="11545-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="11545-130">Symptome von Problemen mit dem Systemspeicher</span><span class="sxs-lookup"><span data-stu-id="11545-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="11545-131">Wenn ein oder mehrere der folgenden Symptome auf Ihrem Computer angezeigt wird, kann ein schwerwiegender Systemspeicher auftreten:</span><span class="sxs-lookup"><span data-stu-id="11545-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="11545-132">Hohe Speicherauslastung, wenn mehrere große Anwendungen gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11545-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="11545-133">Langsame Systemleistung oder hängende Anwendungen</span><span class="sxs-lookup"><span data-stu-id="11545-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="11545-134">Dauerhafte Nutzung des gesamten Systemspeichers von 90% oder höher in allen apps.</span><span class="sxs-lookup"><span data-stu-id="11545-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="11545-135">Bei dieser Speicherauslastung sollten Teams anderen apps und Arbeitsauslastungen Speicher zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="11545-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="11545-136">Nachhaltige Speichernutzung von 90% kann bedeuten, dass Teams dem System keinen Arbeitsspeicher zurückgeben, was auf ein Problem hindeutet.</span><span class="sxs-lookup"><span data-stu-id="11545-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="11545-137">Die folgenden Bilder zeigen Beispiele für Ansichten im Task-Manager, wenn die Systemspeicherauslastung ungewöhnlich groß ist.</span><span class="sxs-lookup"><span data-stu-id="11545-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Ansicht der Arbeitsspeichernutzung in Teams im Task-Manager](media/teams-memory-high-mem-process-list.png)

![Arbeitsspeicher Auslastungsdiagramm für Teams im Task-Manager](media/teams-memory-high-mem-process-list2.png)

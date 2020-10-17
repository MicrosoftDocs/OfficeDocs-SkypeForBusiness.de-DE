---
title: 'Lync Server 2013: Überwachen des Betriebssystems'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d6cad561761b7387cb4c268229f76b52f4bd24b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500632"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="d1dc4-102">Überwachen des Betriebssystems in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dc4-102">Monitoring operating system in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1dc4-103">_**Letztes Änderungsstand des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="d1dc4-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="d1dc4-104">Sie müssen die Leistung aller Server und Komponenten im lync Server 2013 überwachen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="d1dc4-105">Eine der wichtigsten Komponenten ist natürlich das Betriebssystem selbst.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="d1dc4-106">Lync Server 2013 unterstützt x64-Editionen von:</span><span class="sxs-lookup"><span data-stu-id="d1dc4-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="d1dc4-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d1dc4-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="d1dc4-108">Windows Server 2012 und Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d1dc4-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="d1dc4-109">Die transparenteste Möglichkeit zum Überwachen eines Betriebssystems ist die Verwendung des Windows Server Operating System Management Packs.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="d1dc4-110">Es bietet die grundlegenden Überwachungs Grundlagen wie Leistung, Integrität und Verfügbarkeit für Computer, auf denen Windows Server 2012, Windows Server 2012 R2 und Windows Server 2008 R2 durchführen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="d1dc4-111">Durch die Erkennung, Warnung und automatische Reaktion auf wichtige Ereignisse und Leistungsindikatoren reduzieren diese Management Packs Lösungszeiten für Probleme und verbessern die allgemeine Verfügbarkeit und Leistung von Systemen, die die Windows Server-Betriebssysteme ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="d1dc4-112">Neben den relevanten Windows Server Management Packs für System Center Operations Manager können die folgenden System Tools und Ressourcen verwendet werden, um die Integrität des Betriebssystems zu überwachen (je nach Betriebssystemversion).</span><span class="sxs-lookup"><span data-stu-id="d1dc4-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="d1dc4-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d1dc4-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="d1dc4-114">Windows Server 2008 R2 enthält die folgenden zusätzlichen Features und Tools, die Administratoren bei der grundlegenden Betriebssystemüberwachung und-Verwaltung helfen:</span><span class="sxs-lookup"><span data-stu-id="d1dc4-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="d1dc4-115">Der **Windows-Ressourcen Monitor** ist ein leistungsfähiges Tool, um zu verstehen, wie Systemressourcen von Prozessen und Diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-115">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="d1dc4-116">Zusätzlich zur Überwachung der Ressourcennutzung in Echtzeit kann ein Ressourcen Monitor dazu beitragen, nicht reagierende Prozesse zu analysieren, zu ermitteln, welche Anwendungen Dateien verwenden, und Prozesse und Dienste zu steuern.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-116">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="d1dc4-117">Die **Komponente zur Zuverlässigkeitsanalyse** ist ein in-Box-Agent, der detaillierte Informationen zur Systemnutzung und Zuverlässigkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-117">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="d1dc4-118">Diese Informationen werden über eine WMI-Schnittstelle verfügbar gemacht, um Sie für den Verbrauch von tragbaren Reader-Systemen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-118">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="d1dc4-119">Durch das verfügbar machen der Komponente für die Zuverlässigkeitsanalyse über eine WMI-Schnittstelle können Entwickler Anwendungen überwachen und analysieren, wodurch Zuverlässigkeit und Leistung erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-119">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="d1dc4-120">**Windows Server 2008 R2** verwendet die integrierte Komponente für die Zuverlässigkeitsanalyse, um einen Zuverlässigkeits Index zu berechnen, der Informationen über die allgemeine Systemauslastung und-Stabilität im Laufe der Zeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="d1dc4-121">Die Komponente Zuverlässigkeitsanalyse verfolgt außerdem wichtige Änderungen am System, die sich wahrscheinlich auf die Stabilität auswirken, beispielsweise Windows-Updates und Anwendungsinstallationen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="d1dc4-122">Windows Server 2008 Windows-Zuverlässigkeits-und Leistungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="d1dc4-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="d1dc4-123">Windows-Zuverlässigkeits-und Leistungsüberwachung ist ein MMC-Snap-in, das die Funktionen früherer eigenständiger Tools kombiniert, einschließlich Leistungsprotokolle und Warnungen, Server Leistungs Ratgeber und System Monitor.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-123">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="d1dc4-124">Es stellt eine grafische Oberfläche zum Anpassen von Leistungsdatensammlung und Ereignisablaufverfolgungssitzungen bereit.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-124">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="d1dc4-125">Es umfasst auch Zuverlässigkeitsüberwachung, ein MMC-Snap-in, das Änderungen am System nachverfolgt und diese mit Änderungen in der Systemstabilität vergleicht und eine grafische Ansicht Ihrer Beziehung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="d1dc4-126">Windows-Zuverlässigkeits-und Leistungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="d1dc4-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="d1dc4-127">Während die Windows-Zuverlässigkeits-und Leistungsüberwachung Funktionen einiger ehemaliger eigenständiger Tools wie Leistungsprotokolle und Warnungen sowie System Monitor und Server Leistungs Ratgeber kombinieren, stellt Sie auch einige neue Funktionen für Windows Server 2008 und Windows Server 2008 R2 bereit, beispielsweise die folgenden:</span><span class="sxs-lookup"><span data-stu-id="d1dc4-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="d1dc4-128">Sammlungssätze</span><span class="sxs-lookup"><span data-stu-id="d1dc4-128">Data Collector Sets</span></span>

  - <span data-ttu-id="d1dc4-129">Ressourcenansicht</span><span class="sxs-lookup"><span data-stu-id="d1dc4-129">Resource View</span></span>

  - <span data-ttu-id="d1dc4-130">Zuverlässigkeitsüberwachung</span><span class="sxs-lookup"><span data-stu-id="d1dc4-130">Reliability Monitor</span></span>

  - <span data-ttu-id="d1dc4-131">Assistenten und Vorlagen zum Erstellen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="d1dc4-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="d1dc4-132">Der **Daten sammlersatz** gruppiert Datensammler in wieder verwendbare Elemente für die Verwendung mit unterschiedlichen Leistungs Überwachungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-132">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="d1dc4-133">Nachdem eine Gruppe von Datensammlungen als Daten sammlersatz gespeichert wurde, können Vorgänge wie das Planen mithilfe einer einzelnen Eigenschaftenänderung auf die gesamte Gruppe angewendet werden. Windows-Zuverlässigkeits-und Leistungsüberwachung enthält Standardvorlagen für den Sammlungs, damit Systemadministratoren sofort Leistungsdaten sammeln können, die für eine Serverrolle oder ein Überwachungsszenario spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-133">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="d1dc4-134">Die Startseite der Windows-Zuverlässigkeits-und Leistungsüberwachung ist der neue **Ressourcen Ansichts** Bildschirm, der eine grafische Übersicht über die CPU-, Datenträger-, Netzwerk-und Speicherauslastung in Echtzeit bietet.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-134">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="d1dc4-135">Durch das Erweitern dieser überwachten Elemente können Systemadministratoren ermitteln, welche Prozesse welche Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-135">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="d1dc4-136">In früheren Versionen von Windows waren diese prozessspezifischen Daten in Echtzeit nur in beschränkter Form im Task-Manager verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-136">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="d1dc4-137">Die **Zuverlässigkeitsüberwachung** berechnet einen System Stabilitäts Index, der angibt, ob unerwartete Probleme die Zuverlässigkeit des Systems verringert haben.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-137">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="d1dc4-138">Ein Diagramm des Stabilitäts Index im Laufe der Zeit erkennt schnell Daten, wenn Probleme auftreten begannen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-138">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="d1dc4-139">Der zugehörige System Stabilitätsbericht enthält Details zur Problembehandlung bei der Ursache für eine geringere Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-139">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="d1dc4-140">Durch Anzeigen von Systemänderungen (Installation oder Entfernung von Anwendungen, Updates des Betriebssystems oder hinzufügen oder Ändern von Treibern) nebeneinander mit Fehlern (Anwendungsfehler, Betriebssystemabstürze oder Hardwarefehler) kann eine Strategie zur Problembehandlung schnell entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-140">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="d1dc4-141">Das Hinzufügen von Leistungsindikatoren zu Protokolldateien und das Planen von Start, Stopp und Dauer kann nun über eine **Assistentenschnittstelle**erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-141">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="d1dc4-142">Wenn Sie diese Konfiguration als Vorlage speichern, können Systemadministratoren außerdem dasselbe Protokoll auf anderen Computern erfassen, ohne die Daten Sammlungsauswahl und die Planungsprozesse zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-142">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="d1dc4-143">Leistungsprotokolle und Warnungen wurden in die Windows-Zuverlässigkeits-und-Leistungsüberwachung zur Verwendung mit beliebigen Datensammlersätzen integriert.</span><span class="sxs-lookup"><span data-stu-id="d1dc4-143">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


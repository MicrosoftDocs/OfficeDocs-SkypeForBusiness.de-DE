---
title: 'Lync Server 2013: Betriebshandbuch'
description: 'Lync Server 2013: Betriebshandbuch.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85e562b96e87f54529a9e2ce077a0a82574020c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565881"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="5a5a8-103">Betriebsanleitung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-103">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a5a8-104">_**Letztes Änderungsstand des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="5a5a8-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="5a5a8-105">In diesem Dokument werden die Betriebsprozesse, Aufgaben und Tools beschrieben, die für die Verwaltung einer Microsoft lync Server 2013 Kommunikationssoftware Umgebung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5a5a8-105">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="5a5a8-106">In diesem Artikel wird erklärt, wie Sie lync Server 2013 entsprechend dem Microsoft Operations Framework (MOF)-Modell verwalten, und Sie unterstützen Sie beim Entwerfen einer effizienten Betriebsverwaltungsumgebung, die die Implementierung von Zeitplänen, Prozessen und Verfahren zur Aufrechterhaltung einer effizienten Arbeitsumgebung umfasst.</span><span class="sxs-lookup"><span data-stu-id="5a5a8-106">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a5a8-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5a5a8-107">In This Section</span></span>

<span data-ttu-id="5a5a8-108">Die folgenden Abschnitte sind enthalten:</span><span class="sxs-lookup"><span data-stu-id="5a5a8-108">The following sections are included:</span></span>

  - [<span data-ttu-id="5a5a8-109">Bewährte Methoden für lync Server 2013 Umgebungen</span><span class="sxs-lookup"><span data-stu-id="5a5a8-109">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="5a5a8-110">Tägliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="5a5a8-111">Wöchentliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="5a5a8-112">Monatliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="5a5a8-113">Erforderliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="5a5a8-114">Betriebs Prüflisten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-114">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="5a5a8-115">Überwachen von lync Server 2013 mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="5a5a8-115">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="5a5a8-116">Betriebs Abhängigkeiten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-116">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="5a5a8-117">Problembehandlung und wichtige Integritätsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-117">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="5a5a8-118">Es wird davon ausgegangen, dass Ihre Microsoft lync Server 2013-Bereitstellung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5a5a8-118">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="5a5a8-119">Wenn dies nicht der Fall ist, lesen Sie den Planungs-und Bereitstellungs Inhalt für Microsoft lync Server 2013, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5a5a8-119">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a5a8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a5a8-120">See Also</span></span>


[<span data-ttu-id="5a5a8-121">Erste Schritte mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-121">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="5a5a8-122">Planen von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-122">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="5a5a8-123">Bereitstellung von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5a8-123">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="5a5a8-124">Lync Server 2013 Management-Shell</span><span class="sxs-lookup"><span data-stu-id="5a5a8-124">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


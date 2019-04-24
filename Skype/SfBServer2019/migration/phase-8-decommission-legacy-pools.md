---
title: Phase 8 nehmen legacypools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: Das folgende Thema bietet Hilfestellung für Aktualisieren von DNS-Einträge, die Content Management Server verschieben, Außerbetriebnahme von Pools, und deaktivieren und Entfernen von Servern und Pools aus einer Vorgängerversion Bereitstellung. Nicht alle Verfahren in diesem Abschnitt aufgeführten sind erforderlich. Lesen Sie die Dokumentation und bestimmen Sie, welche Außerbetriebnahme Verfahren verwenden.
ms.openlocfilehash: 2363b90f1bcc71c3c8c1ee42d258101240bcacb7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231511"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="a7dbd-105">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="a7dbd-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="a7dbd-106">Das folgende Thema bietet Hilfestellung für Aktualisieren von DNS-Einträge, die Content Management Server verschieben, Außerbetriebnahme von Pools, und deaktivieren und Entfernen von Servern und Pools aus einer Vorgängerversion Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a7dbd-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="a7dbd-107">Nicht alle Verfahren in diesem Abschnitt aufgeführten sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7dbd-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="a7dbd-108">Lesen Sie die Dokumentation und bestimmen Sie, welche Außerbetriebnahme Verfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7dbd-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="a7dbd-109">Laden Sie ein Datum, aber vollständige Artikel zum Entfernen von Servern und Serverrollen und eine schrittweise Anleitung zum Außerbetriebsetzen einer Bereitstellung [Deinstallieren von Microsoft Lync Server und Serverrollen entfernen](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="a7dbd-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a7dbd-110">Informationen zum Migrieren und Aktualisieren von Microsoft Unified Communications Managed API (UCMA) Applications, vor dem Außerbetriebsetzen Ihrer vorversionsumgebung finden Sie unter [UCMA-Anwendungen: Koexistenz, Migration und Upgrade-Szenarien](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="a7dbd-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a7dbd-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="a7dbd-111">In this section</span></span>

> [<span data-ttu-id="a7dbd-112">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="a7dbd-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="a7dbd-113">Verschieben der Vorversionen Installation zentralen Verwaltungsserver in Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a7dbd-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="a7dbd-114">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="a7dbd-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="a7dbd-115">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="a7dbd-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="a7dbd-116">Entfernen der Zuordnung der Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="a7dbd-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="a7dbd-117">Entfernen Sie die Enterprise Edition-Front-End-Server oder Standard Edition-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="a7dbd-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="a7dbd-118">Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="a7dbd-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    


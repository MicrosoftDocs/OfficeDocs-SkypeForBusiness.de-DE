---
title: Phase 8 decommission Legacy-Pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: Im folgenden Thema finden Sie Anleitungen zum Aktualisieren von DNS-Einträgen, zum Verschieben des Inhalts Verwaltungsservers, zur Außerbetriebnahme von Pools sowie zum Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung. Es sind nicht alle der in diesem Abschnitt aufgeführten Verfahren notwendig. Lesen Sie die Dokumentation, um das Verfahren zu ermitteln, das Sie für die Außerbetriebsetzung ausführen möchten.
ms.openlocfilehash: 2406b25436bc13cafca8b09c92220a96e0635ae3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753693"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="e1564-105">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="e1564-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="e1564-106">Im folgenden Thema finden Sie Anleitungen zum Aktualisieren von DNS-Einträgen, zum Verschieben des Inhalts Verwaltungsservers, zur Außerbetriebnahme von Pools sowie zum Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e1564-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="e1564-107">Es sind nicht alle der in diesem Abschnitt aufgeführten Verfahren notwendig.</span><span class="sxs-lookup"><span data-stu-id="e1564-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="e1564-108">Lesen Sie die Dokumentation, um das Verfahren zu ermitteln, das Sie für die Außerbetriebsetzung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1564-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="e1564-109">Einen datierten, aber erschöpfenden Artikel zum Entfernen von Servern und Serverrollen sowie eine Schritt-für-Schritt-Anleitung zur Außerbetriebnahme einer Bereitstellung finden Sie herunterladen [deinstallieren Microsoft lync Server und Entfernen von Serverrollen](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="e1564-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e1564-110">Informationen zum Migrieren und Aktualisieren von verwaltete API von Microsoft Unified Communications (UCMA)-Anwendungen finden Sie unter [UCMA Applications: Koexistenz, Migration und Upgrade Scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555)vor der Außerbetriebnahme ihrer Vorgänger Umgebung.</span><span class="sxs-lookup"><span data-stu-id="e1564-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e1564-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="e1564-111">In this section</span></span>

> [<span data-ttu-id="e1564-112">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="e1564-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="e1564-113">Installieren des Legacy-Installations-zentralen Verwaltungsservers auf Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e1564-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="e1564-114">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="e1564-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="e1564-115">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="e1564-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="e1564-116">Entfernen der Zuordnung der Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="e1564-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="e1564-117">Entfernen der Enterprise Edition-Front-End-Server oder Standard Edition Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="e1564-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="e1564-118">Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="e1564-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    


---
title: Phase 8 Legacy Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: Das folgende Thema enthält Anleitungen zum Aktualisieren von DNS-Einträgen, zum Verschieben des Inhalts Verwaltungsservers, zur Außerbetriebnahme von Pools sowie zum Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung. Nicht alle in diesem Abschnitt aufgelisteten Verfahren sind erforderlich. Lesen Sie die Dokumentation, und legen Sie fest, welches Verfahren für die Außerbetriebnahme verwendet werden soll.
ms.openlocfilehash: 5edad470bcd7bcf0340a311a890f73ef01645138
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236996"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="5f6e2-105">Phase 8: Außerbetriebsetzen der Legacypools</span><span class="sxs-lookup"><span data-stu-id="5f6e2-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="5f6e2-106">Das folgende Thema enthält Anleitungen zum Aktualisieren von DNS-Einträgen, zum Verschieben des Inhalts Verwaltungsservers, zur Außerbetriebnahme von Pools sowie zum Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5f6e2-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="5f6e2-107">Nicht alle in diesem Abschnitt aufgelisteten Verfahren sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f6e2-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="5f6e2-108">Lesen Sie die Dokumentation, und legen Sie fest, welches Verfahren für die Außerbetriebnahme verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f6e2-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="5f6e2-109">Einen datierten, aber ausführlichen Artikel zum Entfernen von Servern und Serverrollen sowie eine schrittweise Anleitung zur Außerbetriebnahme einer Bereitstellung finden Sie unter Deinstallieren von [Microsoft lync Server und Entfernen von Serverrollen](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="5f6e2-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5f6e2-110">Informationen zum Migrieren und Aktualisieren von Microsoft Unified Communications Managed API-Anwendungen (UCMA) vor der Außerbetriebnahme ihrer Legacyumgebung finden Sie unter [UCMA-Anwendungen: Koexistenz-, Migrations-und Upgrade-Szenarien](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="5f6e2-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5f6e2-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="5f6e2-111">In this section</span></span>

> [<span data-ttu-id="5f6e2-112">Aktualisieren von DNS SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="5f6e2-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="5f6e2-113">Verschieben der Legacy Installation des zentralen Verwaltungsservers in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5f6e2-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="5f6e2-114">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="5f6e2-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="5f6e2-115">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="5f6e2-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="5f6e2-116">Entfernen der Zuordnung der Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="5f6e2-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="5f6e2-117">Entfernen des Enterprise Edition-Front-End-Servers oder des Standard Edition-Front-End-Servers</span><span class="sxs-lookup"><span data-stu-id="5f6e2-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="5f6e2-118">Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="5f6e2-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    


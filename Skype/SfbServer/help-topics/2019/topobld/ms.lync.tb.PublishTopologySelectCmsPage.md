---
title: Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Sie veröffentlichen die Topologie, die Sie mit dem Topologie-Generator konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, auf der der Front-End-Server oder der Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Diese Rolle kann nur von einem Front-End-Server oder einem Front-End-Pool zu einem beliebigen Zeitpunkt übernommen werden.
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277881"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="a297a-105">Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"</span><span class="sxs-lookup"><span data-stu-id="a297a-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="a297a-106">Sie veröffentlichen die Topologie, die Sie mit dem Topologie-Generator konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="a297a-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="a297a-107">Sie werden aufgefordert, aus einer Liste auszuwählen, auf der der Front-End-Server oder der Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt.</span><span class="sxs-lookup"><span data-stu-id="a297a-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="a297a-108">Diese Rolle kann nur von einem Front-End-Server oder einem Front-End-Pool zu einem beliebigen Zeitpunkt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="a297a-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="a297a-109">Informationen zum zentralen Verwaltungs Server</span><span class="sxs-lookup"><span data-stu-id="a297a-109">About the Central Management Server</span></span>
<span data-ttu-id="a297a-110">Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Kopie der Datenbank vom Front-End-Server, auf dem sich der zentrale Verwaltungsserver befindet, gelesen/geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="a297a-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="a297a-111">Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der zentralen Verwaltungsspeicher Daten in der SQL Server-Datenbank (standardmäßig mit dem Namen RTCLOCAL), die während des Setups auf dem Computer installiert sind, und Bereitstellungs.</span><span class="sxs-lookup"><span data-stu-id="a297a-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="a297a-112">Die lokale Datenbank erhält Replikat Updates über den lync Server Replica Replicator-Agent, der auf allen Computern als Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a297a-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="a297a-113">Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="a297a-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="a297a-114">Auf den Speicherort der Master Datenbank wird in den Active Directory-Domänendiensten von einem Dienst Kontrollpunkt (Service Control Point, SCP) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="a297a-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="a297a-115">Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und Konfigurieren von lync Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.</span><span class="sxs-lookup"><span data-stu-id="a297a-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a297a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a297a-116">See also</span></span>

[<span data-ttu-id="a297a-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="a297a-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)

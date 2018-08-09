---
title: Veröffentlichen der Topologie zentralen Verwaltungsserver auswählen (Seite)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Sie veröffentlichen die Topologie, die Sie mithilfe des Topologie-Generators konfiguriert haben. Sie werden aufgefordert, aus einer Liste Wählen Sie die Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers halten übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle zu einem bestimmten Zeitpunkt enthalten.
ms.openlocfilehash: 5f5c25982194246490232966d5c7da3a48759a57
ms.sourcegitcommit: 16421e244f866e13600765a41cca509202815819
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "22290278"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="cea9b-105">Veröffentlichen der Topologie zentralen Verwaltungsserver auswählen (Seite)</span><span class="sxs-lookup"><span data-stu-id="cea9b-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="cea9b-106">Sie veröffentlichen die Topologie, die Sie mithilfe des Topologie-Generators konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="cea9b-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="cea9b-107">Sie werden aufgefordert, aus einer Liste Wählen Sie die Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers halten übernimmt.</span><span class="sxs-lookup"><span data-stu-id="cea9b-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="cea9b-108">Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle zu einem bestimmten Zeitpunkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="cea9b-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="cea9b-109">Informationen zu den zentralen Verwaltungsserver</span><span class="sxs-lookup"><span data-stu-id="cea9b-109">About the Central Management Server</span></span>
<span data-ttu-id="cea9b-110">Den zentralen Verwaltungsserver ist ein einzelnes Master/mehreren Replikat System, auf dem wird die Lese-Schreib-Kopie der Datenbank vom Front-End-Server gespeichert, der den zentralen Verwaltungsserver enthält.</span><span class="sxs-lookup"><span data-stu-id="cea9b-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="cea9b-111">Auf jedem Computer in der Topologie, einschließlich der Front-End-Server, der den zentralen Verwaltungsserver enthält ist eine schreibgeschützte Kopie der zentralen Speicherdaten in SQL Server-Datenbank (namens RTCLOCAL standardmäßig) auf dem Computer während des Setups installiert und Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="cea9b-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="cea9b-112">Die lokale Datenbank empfängt Replikat Updates über die Lync Server Replikat Replicator-Agent, der als Dienst auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cea9b-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="cea9b-113">Der Name der aktuellen Datenbank auf den zentralen Verwaltungsserver und dem lokalen Replikat ist XDS, die der Dateien xds.mdf und xds.ldf besteht.</span><span class="sxs-lookup"><span data-stu-id="cea9b-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="cea9b-114">Einen Dienststeuerungspunkt (SCP) in Active Directory Domain Services verweist auf der Speicherort der master-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="cea9b-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="cea9b-115">Alle Tools, die verwenden den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Lync Server, mithilfe des Dienstverbindungspunkts um den zentralen Verwaltungsspeicher zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cea9b-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cea9b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cea9b-116">See also</span></span>

[<span data-ttu-id="cea9b-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="cea9b-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
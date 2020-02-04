---
title: 'Lync Server 2013: Neue Funktionen für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="8bb4d-102">Neue Funktionen für die Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb4d-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bb4d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8bb4d-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8bb4d-104">Bei der Archivierung in lync Server 2013 können die folgenden Arten von Inhalten archiviert werden:</span><span class="sxs-lookup"><span data-stu-id="8bb4d-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="8bb4d-105">Peer-zu-Peer-Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="8bb4d-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="8bb4d-106">Konferenzen (Besprechungen), die mehr Parteien-Sofortnachrichten sind</span><span class="sxs-lookup"><span data-stu-id="8bb4d-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="8bb4d-107">Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)</span><span class="sxs-lookup"><span data-stu-id="8bb4d-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="8bb4d-108">Darüber hinaus bietet die Archivierung in lync Server 2013 neue Funktionen, die die Bereitstellung und die Effizienz des Betriebs verbessern.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="8bb4d-109">Diese neuen Features bestehen aus:</span><span class="sxs-lookup"><span data-stu-id="8bb4d-109">These new features consist of:</span></span>

  - <span data-ttu-id="8bb4d-110">**Übersetzung der Archivierung auf Front-End-Servern.**    Lync Server 2013 verfügt nicht über eine separate Archivierungs Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="8bb4d-111">Die Archivierung ist ein optionales Feature, das auf allen Front-End-Servern in einer Enterprise Edition-Bereitstellung und auf Standard Edition-Servern zur Verfügung steht, die für einen Pool oder eine Website konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="8bb4d-112">**Integration von Microsoft Exchange.**    Wenn Sie die Archivierung bereitstellen, können Sie Datenspeicher für die Archivierung mit Ihrem vorhandenen Exchange 2013-Speicher für alle Benutzer integrieren, die sich in Exchange 2013 befinden und deren Postfächer in-situ-Speicher abgelegt werden, damit Sie keine separaten SQL Server-Datenbanken zum Archivieren von lync-Daten bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="8bb4d-113">Wenn Sie keine Exchange 2013-Bereitstellung haben, oder wenn Sie es vorziehen, Sie nicht zu integrieren, oder wenn Sie lync 2013-Benutzer haben, die nicht in Exchange 2013 mit ihren Postfächern in-situ-Speicher abgelegt sind, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie SQL Server zum Speichern verwenden e archivierte Daten aus lync Communications.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="8bb4d-114">Sie können sowohl die Microsoft Exchange-Integration als auch die lync Server 2013-Archivierungsdatenbanken verwenden, wenn Sie die Microsoft Exchange-Integration für einige, aber nicht für alle Benutzer in Ihrer Bereitstellung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="8bb4d-115">Details zum in-situ-Speicher finden Sie unter "in-situ-Speicher [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)" unter.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="8bb4d-116">**SQL Store-Spiegelung.**    Wenn Sie die Archivierung bereitstellen, können Sie die SQL Server-Datenbankspiegelung für Ihre Archivierungsdatenbank aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="8bb4d-117">**Archivierung von Whiteboards und Umfragen.**    Archivierte Konferenzinhalte enthalten nun Whiteboards und Umfragen, die während der Besprechung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8bb4d-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="8bb4d-118">Die folgenden Inhaltstypen werden nicht archiviert:</span><span class="sxs-lookup"><span data-stu-id="8bb4d-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="8bb4d-119">Peer-to-Peer-Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="8bb4d-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="8bb4d-120">Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen</span><span class="sxs-lookup"><span data-stu-id="8bb4d-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="8bb4d-121">Anwendungsfreigabe für Peer-to-Peer-Sofortnachrichten und-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="8bb4d-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8bb4d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bb4d-122">See Also</span></span>


[<span data-ttu-id="8bb4d-123">Planen der Archivierung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bb4d-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


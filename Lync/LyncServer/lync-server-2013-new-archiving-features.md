---
title: 'Lync Server 2013: neue Archivierungs Features'
description: 'Lync Server 2013: neue Archivierungs Features.'
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
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561351"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="041dd-103">Neue Archivierungs Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="041dd-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="041dd-104">_**Letztes Änderungsstand des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="041dd-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="041dd-105">Die Archivierung in lync Server 2013 kann die folgenden Inhaltstypen archivieren:</span><span class="sxs-lookup"><span data-stu-id="041dd-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="041dd-106">Peer-zu-Peer-Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="041dd-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="041dd-107">Konferenzen (Besprechungen), bei denen es sich um Chatnachrichten mit mehreren Teilnehmern handelt</span><span class="sxs-lookup"><span data-stu-id="041dd-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="041dd-108">Konferenzinhalt, einschließlich hochgeladenem Inhalt (z. B. Handzettel) und ereignisbezogenem Inhalt (z. B. Beitritt, Verlassen, Hochladen, Freigabe und Änderungen in der Sichtbarkeit)</span><span class="sxs-lookup"><span data-stu-id="041dd-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="041dd-109">Darüber hinaus bietet die Archivierung in lync Server 2013 neue Features, die die Bereitstellung und die Effizienz des Betriebs verbessern.</span><span class="sxs-lookup"><span data-stu-id="041dd-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="041dd-110">Diese neuen Features umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="041dd-110">These new features consist of:</span></span>

  - <span data-ttu-id="041dd-111">Nebeneinander **der Archivierung auf Front-End-Servern.**     Lync Server 2013 verfügt nicht über eine separate Archivierungsserver Rolle.</span><span class="sxs-lookup"><span data-stu-id="041dd-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="041dd-112">Die Archivierung ist ein optionales Feature, das auf allen Front-End-Servern in einer Enterprise Edition-Bereitstellung, und auf Standard Edition-Servern, die für einen Pool oder einen Standort implementiert und konfiguriert werden können, verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="041dd-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="041dd-113">**Microsoft Exchange Integration.**     Wenn Sie die Archivierung bereitstellen, können Sie Datenspeicher für die Archivierung mit dem vorhandenen Exchange 2013 Speicher für alle Benutzer integrieren, die in Exchange 2013 verwaltet werden und deren Postfächer In-Place halten, sodass Sie keine separaten SQL Server Datenbanken zum Archivieren von lync-Daten bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="041dd-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="041dd-114">Wenn Sie nicht über eine Exchange 2013-Bereitstellung verfügen oder keine Integration in die Datenbank wünschen oder wenn Sie lync 2013-Benutzer haben, die nicht in Exchange 2013 mit ihren Postfächern gespeichert sind, die In-Place Aufbewahrungsstelle gespeichert sind, können Sie mithilfe von SQL Server separate Archivierungsdatenbanken bereitstellen, um archivierte Daten aus lync Communications zu speichern.</span><span class="sxs-lookup"><span data-stu-id="041dd-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="041dd-115">Sie können sowohl Microsoft Exchange Integration als auch lync Server 2013 Archivierungsdatenbanken verwenden, wenn Sie Microsoft Exchange Integration für einige, jedoch nicht für alle Benutzer in Ihrer Bereitstellung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="041dd-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="041dd-116">Ausführliche Informationen zum In-Place Haltestatus finden Sie unter "in-situ-Speicher" unter [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) .</span><span class="sxs-lookup"><span data-stu-id="041dd-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="041dd-117">**SQL-Speicherspiegelung.**     Wenn Sie die Archivierung bereitstellen, können Sie SQL Server Datenbankspiegelung für Ihre Archivierungsdatenbank aktivieren.</span><span class="sxs-lookup"><span data-stu-id="041dd-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="041dd-118">**Archivierung von Whiteboards und Umfragen.**     Archivierte Konferenzinhalte enthalten jetzt Whiteboards und Umfragen, die während der Besprechung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="041dd-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="041dd-119">Die folgenden Arten von Inhalt können nicht archiviert werden:</span><span class="sxs-lookup"><span data-stu-id="041dd-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="041dd-120">Peer-zu-Peer-Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="041dd-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="041dd-121">Audio/Video für Peer-zu-Peer-Chatnachrichten und -Konferenzen</span><span class="sxs-lookup"><span data-stu-id="041dd-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="041dd-122">Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -Konferenzen</span><span class="sxs-lookup"><span data-stu-id="041dd-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="041dd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="041dd-123">See Also</span></span>


[<span data-ttu-id="041dd-124">Planen der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="041dd-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


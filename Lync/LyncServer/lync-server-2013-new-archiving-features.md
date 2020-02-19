---
title: 'Lync Server 2013: neue Archivierungs Features'
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
ms.openlocfilehash: 3e09284d78ead2e8cd4249c2dc54159284ddad43
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42127648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="10542-102">Neue Archivierungs Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10542-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10542-103">_**Letztes Änderungsstand des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="10542-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="10542-104">Die Archivierung in lync Server 2013 kann die folgenden Inhaltstypen archivieren:</span><span class="sxs-lookup"><span data-stu-id="10542-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="10542-105">Peer-zu-Peer-Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="10542-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="10542-106">Konferenzen (Besprechungen), bei denen es sich um Chatnachrichten mit mehreren Teilnehmern handelt</span><span class="sxs-lookup"><span data-stu-id="10542-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="10542-107">Konferenzinhalt, einschließlich hochgeladenem Inhalt (z. B. Handzettel) und ereignisbezogenem Inhalt (z. B. Beitritt, Verlassen, Hochladen, Freigabe und Änderungen in der Sichtbarkeit)</span><span class="sxs-lookup"><span data-stu-id="10542-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="10542-108">Darüber hinaus bietet die Archivierung in lync Server 2013 neue Features, die die Bereitstellung und die Effizienz des Betriebs verbessern.</span><span class="sxs-lookup"><span data-stu-id="10542-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="10542-109">Diese neuen Features umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="10542-109">These new features consist of:</span></span>

  - <span data-ttu-id="10542-110">**Nebeneinander der Archivierung auf Front-End-Servern.**    Lync Server 2013 verfügt nicht über eine separate Archivierungsserver Rolle.</span><span class="sxs-lookup"><span data-stu-id="10542-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="10542-111">Die Archivierung ist ein optionales Feature, das auf allen Front-End-Servern in einer Enterprise Edition-Bereitstellung, und auf Standard Edition-Servern, die für einen Pool oder einen Standort implementiert und konfiguriert werden können, verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="10542-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="10542-112">**Microsoft Exchange Integration.**    Wenn Sie die Archivierung bereitstellen, können Sie den Datenspeicher für die Archivierung mit dem vorhandenen Exchange 2013 Speicher für alle Benutzer integrieren, die in Exchange 2013 verwaltet werden und deren Postfächer in einem Compliance-Archiv abgelegt werden, sodass Sie keine separaten SQL Server Datenbanken zur Archivierung von lync-Daten bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="10542-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="10542-113">Wenn Sie nicht über eine Exchange 2013-Bereitstellung verfügen oder keine Integration in die Datenbank wünschen oder wenn Sie lync 2013 Benutzer haben, die nicht in Exchange 2013 mit ihren Postfächern in-situ-Speicher verwaltet werden, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie SQL Server zum Speichern verwenden. e archivierte Daten aus lync Communications.</span><span class="sxs-lookup"><span data-stu-id="10542-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="10542-114">Sie können sowohl Microsoft Exchange Integration als auch lync Server 2013 Archivierungsdatenbanken verwenden, wenn Sie Microsoft Exchange Integration für einige, jedoch nicht für alle Benutzer in Ihrer Bereitstellung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="10542-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="10542-115">Ausführliche Informationen zum in-situ-Speicher finden Sie unter "in-situ- [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500)Speicher" unter "in-situ-Aufbewahrung".</span><span class="sxs-lookup"><span data-stu-id="10542-115">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="10542-116">**SQL-Speicherspiegelung.**    Wenn Sie die Archivierung bereitstellen, können Sie SQL Server Datenbankspiegelung für Ihre Archivierungsdatenbank aktivieren.</span><span class="sxs-lookup"><span data-stu-id="10542-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="10542-117">**Archivierung von Whiteboards und Umfragen.**    Archivierte Konferenzinhalte enthalten jetzt Whiteboards und Umfragen, die während der Besprechung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="10542-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="10542-118">Die folgenden Arten von Inhalt können nicht archiviert werden:</span><span class="sxs-lookup"><span data-stu-id="10542-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="10542-119">Peer-zu-Peer-Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="10542-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="10542-120">Audio/Video für Peer-zu-Peer-Chatnachrichten und -Konferenzen</span><span class="sxs-lookup"><span data-stu-id="10542-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="10542-121">Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -Konferenzen</span><span class="sxs-lookup"><span data-stu-id="10542-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="10542-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10542-122">See Also</span></span>


[<span data-ttu-id="10542-123">Planen der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10542-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


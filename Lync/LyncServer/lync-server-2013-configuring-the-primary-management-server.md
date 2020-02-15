---
title: 'Lync Server 2013: Konfigurieren des primären Verwaltungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6640e13209700d50aac04c43728175a4fcb4e6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="ad6b7-102">Konfigurieren des primären Verwaltungsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad6b7-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad6b7-103">_**Letztes Änderungsstand des Themas:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="ad6b7-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="ad6b7-104">Um die neuen Funktionen für die Integritätsüberwachung in vollem Umfang nutzen zu können, müssen Administratoren zunächst einen Computer als primären Verwaltungs Server für Microsoft lync Server 2013 festlegen. auf diesem Computer müssen Sie System Center Operations Manager 2007 R2 oder System Center Operations Manager 2012 installieren.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="ad6b7-105">Darüber hinaus müssen Sie eine unterstützte Version von SQL Server installieren, die als Operations Manager-Back-End-Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="ad6b7-106">Wenn Sie System Center Operations Manager 2012 verwenden, können Sie eine der folgenden Versionen von SQL Server als Back-End-Datenbank verwenden:</span><span class="sxs-lookup"><span data-stu-id="ad6b7-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="ad6b7-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="ad6b7-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="ad6b7-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="ad6b7-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="ad6b7-109">Wenn Sie System Center Operations Manager 2007 R2 verwenden, sollten Sie entweder SQL Server 2005 Service Pack 4 oder SQL Server 2008 Service Pack 3 installieren.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="ad6b7-110">Sie können auch SQL Server 2008 R2 als Back-End-Datenbank für System Center Operations Manager 2007 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="ad6b7-111">In Anhang 1 dieser Dokumentation finden Sie weitere Informationen zum Konfigurieren von SQL Server 2008 R2 für die Verwendung von System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="ad6b7-112">Bei der Installation von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 müssen Sie alle Komponenten des Produkts installieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="ad6b7-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="ad6b7-113">Betriebsdatenbank</span><span class="sxs-lookup"><span data-stu-id="ad6b7-113">Operational database</span></span>

  - <span data-ttu-id="ad6b7-114">Server</span><span class="sxs-lookup"><span data-stu-id="ad6b7-114">Server</span></span>

  - <span data-ttu-id="ad6b7-115">Konsole</span><span class="sxs-lookup"><span data-stu-id="ad6b7-115">Console</span></span>

  - <span data-ttu-id="ad6b7-116">Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ad6b7-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="ad6b7-117">Webkonsole</span><span class="sxs-lookup"><span data-stu-id="ad6b7-117">Web console</span></span>

  - <span data-ttu-id="ad6b7-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="ad6b7-118">Reporting</span></span>

  - <span data-ttu-id="ad6b7-119">Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="ad6b7-119">Data warehouse</span></span>

<span data-ttu-id="ad6b7-120">Diese Komponenten und ihre Installation werden in diesem Dokument nicht ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="ad6b7-121">Ausführliche Informationen zu System Center Operations Manager 2007 R2 finden Sie in der Operations Manager 2007 R2- <http://go.microsoft.com/fwlink/p/?linkid=257526> Dokumentation unter und in der System Center Operations Manager <http://go.microsoft.com/fwlink/p/?linkid=257527>2012-Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="ad6b7-122">Befolgen Sie diese Anweisungen, wenn Sie SQL Server 2005 oder SQL Server 2008 Service Pack 1 als Back-End-Datenbank verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="ad6b7-123">Wenn Sie System Center Operations Manager 2012 verwenden, können Sie SQL Server 2012 als Back-End-Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="ad6b7-124">Ausführliche Informationen zu SQL Server 2012 finden Sie in [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)der Online Dokumentation zu SQL Server 2012 unter.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="ad6b7-125">Beachten Sie, dass Sie pro lync Server-Bereitstellung nur einen einzigen primären Verwaltungs Server haben können.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="ad6b7-126">Auch wenn Sie entweder System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 verwenden können, können Sie die beiden Anwendungen nicht gleichzeitig ausführen – Sie müssen die eine oder die andere auswählen.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="ad6b7-127">Wenn Sie beispielsweise System Center Operations Manager 2012 ausführen, müssen auf allen System Center-Agents auch System Center Operations Manager 2012 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="ad6b7-128">Es können nicht einige Agents mit System Center Operations Manager 2012 und anderen Agents ausgeführt werden, auf denen System Center Operations Manager 2007 R2 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad6b7-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


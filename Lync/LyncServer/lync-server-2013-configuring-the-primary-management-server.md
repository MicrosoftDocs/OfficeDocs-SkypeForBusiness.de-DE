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
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="9f5ef-102">Konfigurieren des primären Verwaltungsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f5ef-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f5ef-103">_**Letztes Änderungsdatum des Themas:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="9f5ef-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="9f5ef-104">Um die neuen Integritäts Überwachungsfunktionen in Microsoft lync Server 2013 vollständig nutzen zu können, müssen Administratoren zunächst einen Computer als primären Verwaltungs Server festlegen. auf diesem Computer müssen Sie System Center Operations Manager 2007 R2 oder System Center Operations Manager 2012 installieren.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="9f5ef-105">Darüber hinaus müssen Sie eine unterstützte Version von SQL Server installieren, um als Ihre Operations Manager-Back-End-Datenbank zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="9f5ef-106">Wenn Sie System Center Operations Manager 2012 verwenden, können Sie eine der folgenden Versionen von SQL Server als Back-End-Datenbank verwenden:</span><span class="sxs-lookup"><span data-stu-id="9f5ef-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="9f5ef-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="9f5ef-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="9f5ef-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="9f5ef-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="9f5ef-109">Wenn Sie System Center Operations Manager 2007 R2 verwenden, empfiehlt es sich, entweder SQL Server 2005 Service Pack 4 oder SQL Server 2008 Service Pack 3 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="9f5ef-110">Sie können auch SQL Server 2008 R2 als Back-End-Datenbank für System Center Operations Manager 2007 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="9f5ef-111">Weitere Informationen zum Konfigurieren von SQL Server 2008 R2 für die Zusammenarbeit mit System Center Operations Manager 2007 R2 finden Sie in Anhang 1 dieser Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="9f5ef-112">Wenn Sie System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 installieren, müssen Sie alle Komponenten dieses Produkts installieren, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="9f5ef-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="9f5ef-113">Betriebsdatenbank</span><span class="sxs-lookup"><span data-stu-id="9f5ef-113">Operational database</span></span>

  - <span data-ttu-id="9f5ef-114">Server</span><span class="sxs-lookup"><span data-stu-id="9f5ef-114">Server</span></span>

  - <span data-ttu-id="9f5ef-115">Konsole</span><span class="sxs-lookup"><span data-stu-id="9f5ef-115">Console</span></span>

  - <span data-ttu-id="9f5ef-116">Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9f5ef-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="9f5ef-117">Webkonsole</span><span class="sxs-lookup"><span data-stu-id="9f5ef-117">Web console</span></span>

  - <span data-ttu-id="9f5ef-118">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="9f5ef-118">Reporting</span></span>

  - <span data-ttu-id="9f5ef-119">Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="9f5ef-119">Data warehouse</span></span>

<span data-ttu-id="9f5ef-120">Diese Komponenten und deren Installation werden in diesem Dokument nicht ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="9f5ef-121">Ausführliche Informationen zu System Center Operations Manager 2007 R2 finden Sie in der Dokumentation zu Operations Manager 2007 <http://go.microsoft.com/fwlink/p/?linkid=257526> R2 unter und in <http://go.microsoft.com/fwlink/p/?linkid=257527>der System Center Operations Manager 2012-Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="9f5ef-122">Befolgen Sie diese Anweisungen, wenn Sie SQL Server 2005 oder SQL Server 2008 Service Pack 1 als Back-End-Datenbank verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="9f5ef-123">Wenn Sie System Center Operations Manager 2012 verwenden, können Sie SQL Server 2012 als Back-End-Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="9f5ef-124">Ausführliche Informationen zu SQL Server 2012 finden Sie unter Online Dokumentation für SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)unter.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="9f5ef-125">Beachten Sie, dass pro lync Server-Bereitstellung nur ein einzelner primärer Verwaltungs Server verfügbar sein kann.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="9f5ef-126">Auch wenn Sie System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 verwenden können, können Sie die beiden Anwendungen nicht gleichzeitig ausführen – Sie müssen die eine oder andere auswählen.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="9f5ef-127">Wenn Sie beispielsweise System Center Operations Manager 2012 ausführen, müssen alle Ihre System Center-Agents auch System Center Operations Manager 2012 ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="9f5ef-128">Sie können nicht über einige Agents verfügen, auf denen System Center Operations Manager 2012 und andere Agents mit System Center Operations Manager 2007 R2 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9f5ef-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


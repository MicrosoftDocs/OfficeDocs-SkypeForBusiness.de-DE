---
title: 'Lync Server 2013: Überprüfen des Topologieentwurfs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="784ec-102">Überprüfen des Topologieentwurfs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="784ec-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="784ec-103">_**Letztes Änderungsdatum des Themas:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="784ec-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="784ec-104">Der Topologie-Generator überprüft die Topologie automatisch.</span><span class="sxs-lookup"><span data-stu-id="784ec-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="784ec-105">Jeder topologiefehler wird als Überprüfungsfehler identifiziert, der durch das Symbol "Gültigkeitsprüfungsfehler" neben der Serverrolle angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="784ec-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="784ec-106">Es ist wichtig, auch zu überprüfen, ob die Topologie die Topologie für Ihre Bereitstellung richtig darstellt.</span><span class="sxs-lookup"><span data-stu-id="784ec-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="784ec-107">So überprüfen Sie die Topologie vor der Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="784ec-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="784ec-108">Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="784ec-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="784ec-109">Stellen Sie sicher, dass der SQL Server-basierte Server online und für den Computer verfügbar ist, auf dem der Topologie-Generator installiert wurde (einschließlich aller erforderlichen Firewallregeln).</span><span class="sxs-lookup"><span data-stu-id="784ec-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="784ec-110">Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist und die entsprechenden Berechtigungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="784ec-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="784ec-111">Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="784ec-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="784ec-112">Stellen Sie sicher, dass die Server in den Active Directory-Domänendiensten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="784ec-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="784ec-113">Dies geschieht automatisch, wenn Sie die Server der Domäne beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="784ec-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="784ec-114">Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="784ec-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="784ec-115">Wenn Validierungsfehler vorliegen, müssen Sie diese korrigieren, bevor Sie die Topologie veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="784ec-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="784ec-116">Details zum Veröffentlichen Ihrer Topologie finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="784ec-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


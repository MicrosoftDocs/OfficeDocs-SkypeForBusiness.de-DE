---
title: 'Lync Server 2013: Überprüfen des Topologie-Designs'
description: 'Lync Server 2013: Überprüfen des Topologie Designs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560191"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="09e9f-103">Überprüfen des Topologie-Designs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e9f-103">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e9f-104">_**Letztes Änderungsstand des Themas:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="09e9f-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="09e9f-105">Der Topologie-Generator überprüft die Topologie automatisch.</span><span class="sxs-lookup"><span data-stu-id="09e9f-105">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="09e9f-106">Jeder Topologiefehler wird als Überprüfungsfehler identifiziert, angegeben durch das entsprechende Fehlersymbol neben der Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="09e9f-106">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="09e9f-107">Es ist wichtig, ebenfalls sicherzustellen, dass die Topologie die gewünschte Konfiguration für Ihre Bereitstellung richtig darstellt.</span><span class="sxs-lookup"><span data-stu-id="09e9f-107">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="09e9f-108">So überprüfen Sie die Topologie vor deren Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="09e9f-108">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="09e9f-109">Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="09e9f-109">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="09e9f-110">Stellen Sie sicher, dass der SQL Server basierte Server Online ist und für den Computer verfügbar ist, auf dem der Topologie-Generator installiert ist, einschließlich aller erforderlichen Firewallregeln.</span><span class="sxs-lookup"><span data-stu-id="09e9f-110">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="09e9f-111">Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist, und dass die richtigen Berechtigungen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="09e9f-111">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="09e9f-112">Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="09e9f-112">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="09e9f-113">Stellen Sie sicher, dass die Server in Active Directory-Domänendienste vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="09e9f-113">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="09e9f-114">Dies geschieht automatisch, wenn Sie die Server der Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="09e9f-114">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="09e9f-115">Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="09e9f-115">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="09e9f-116">Im Falle von Überprüfungsfehlern müssen Sie diese zunächst korrigieren, bevor Sie die Topologie veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="09e9f-116">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="09e9f-117">Ausführliche Informationen zum Veröffentlichen Ihrer Topologie finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="09e9f-117">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


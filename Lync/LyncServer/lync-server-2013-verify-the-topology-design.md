---
title: 'Lync Server 2013: Überprüfen des Topologie-Designs'
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
ms.openlocfilehash: 452bd18d19fa61a0479ee8040361290b0b99d702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="243c4-102">Überprüfen des Topologie-Designs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="243c4-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="243c4-103">_**Letztes Änderungsstand des Themas:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="243c4-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="243c4-104">Der Topologie-Generator überprüft die Topologie automatisch.</span><span class="sxs-lookup"><span data-stu-id="243c4-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="243c4-105">Jeder Topologiefehler wird als Überprüfungsfehler identifiziert, angegeben durch das entsprechende Fehlersymbol neben der Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="243c4-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="243c4-106">Es ist wichtig, ebenfalls sicherzustellen, dass die Topologie die gewünschte Konfiguration für Ihre Bereitstellung richtig darstellt.</span><span class="sxs-lookup"><span data-stu-id="243c4-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="243c4-107">So überprüfen Sie die Topologie vor deren Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="243c4-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="243c4-108">Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="243c4-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="243c4-109">Stellen Sie sicher, dass der SQL Server basierte Server Online ist und für den Computer verfügbar ist, auf dem der Topologie-Generator installiert ist, einschließlich aller erforderlichen Firewallregeln.</span><span class="sxs-lookup"><span data-stu-id="243c4-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="243c4-110">Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist, und dass die richtigen Berechtigungen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="243c4-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="243c4-111">Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="243c4-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="243c4-112">Stellen Sie sicher, dass die Server in Active Directory-Domänendienste vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="243c4-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="243c4-113">Dies geschieht automatisch, wenn Sie die Server der Domäne hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="243c4-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="243c4-114">Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="243c4-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="243c4-115">Im Falle von Überprüfungsfehlern müssen Sie diese zunächst korrigieren, bevor Sie die Topologie veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="243c4-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="243c4-116">Ausführliche Informationen zum Veröffentlichen Ihrer Topologie finden Sie unter [Veröffentlichen der Topologie in lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="243c4-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


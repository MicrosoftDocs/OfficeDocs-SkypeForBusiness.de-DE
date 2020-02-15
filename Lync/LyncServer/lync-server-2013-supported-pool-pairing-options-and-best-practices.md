---
title: Lync Server 2013 unterstützte Optionen für das Pool koppeln und bewährte Methoden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 963f1532ca7a1aa5402a54936909a22727ab9716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="85ba5-102">Unterstützte Optionen für das Pool koppeln und bewährte Methoden für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ba5-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ba5-103">_**Letztes Änderungsstand des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="85ba5-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="85ba5-p101">Die Entfernung zwischen zwei Rechenzentren, die als Paar bereitgestellte Front-End-Pools enthalten sollen, ist nicht begrenzt. Wir empfehlen die Verwendung zweier Rechenzentren in derselben Weltregion mit Hochgeschwindigkeitsverbindung. Die Rechenzentren sollen weit genug voneinander entfernt sein, damit sie nicht gleichzeitig von einem Notfall betroffen sein können.</span><span class="sxs-lookup"><span data-stu-id="85ba5-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="85ba5-107">Die Verwendung zweier Rechenzentren in verschiedenen Weltregionen ist zwar möglich, führt jedoch u. U. zu größeren Datenverlusten aufgrund von Wartezeiten bei der Datenreplikation.</span><span class="sxs-lookup"><span data-stu-id="85ba5-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="85ba5-108">Wenn Sie planen, welche Pools gekoppelt werden sollen, müssen Sie beachten, dass nur die folgenden Paarungen unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="85ba5-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="85ba5-p102">Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="85ba5-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="85ba5-p103">Physische Pool können nur mit andere physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="85ba5-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="85ba5-113">Für Pools, die zusammen gekoppelt sind, muss das gleiche Betriebssystem installiert sein.</span><span class="sxs-lookup"><span data-stu-id="85ba5-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="85ba5-114">Das Paaren zweier Pools, das nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert.</span><span class="sxs-lookup"><span data-stu-id="85ba5-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="85ba5-115">Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu.</span><span class="sxs-lookup"><span data-stu-id="85ba5-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="85ba5-116">Diese Typen von Kopplungen werden jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85ba5-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="85ba5-117">Jeder Pool in einem Paar sollte über ausreichend Kapazität verfügen, um bei einem Notfall alle Benutzer zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="85ba5-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="85ba5-118">Wenn Sie Enterprise Edition-Pools paaren, können Sie auch auf den Back-End-Servern hohe Verfügbarkeit bereitstellen; bei Paaren aus Standard Edition-Pools stehen jedoch nur die Notfallwiederherstellungsmaßnahmen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="85ba5-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


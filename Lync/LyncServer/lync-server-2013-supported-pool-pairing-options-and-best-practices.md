---
title: Lync Server 2013 unterstützte Pool-Kopplungs Optionen und bewährte Methoden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="35ee2-102">Unterstützte Pool-Kopplungs Optionen und bewährte Methoden für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ee2-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ee2-103">_**Letztes Änderungsdatum des Themas:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="35ee2-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="35ee2-104">Es gibt keine Einschränkung für den Abstand zwischen zwei Rechenzentren, in denen Front-End-Pools miteinander kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="35ee2-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="35ee2-105">Wir empfehlen, dass Sie zwei Rechenzentren in der gleichen Weltregion verwenden, mit Hochgeschwindigkeits-Links zwischen Ihnen.</span><span class="sxs-lookup"><span data-stu-id="35ee2-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="35ee2-106">Am besten ist es, wenn die beiden Rechenzentren voneinander getrennt sind, um zu verhindern, dass ein einzelner Notfall gleichzeitig anschlägt.</span><span class="sxs-lookup"><span data-stu-id="35ee2-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="35ee2-107">Die Möglichkeit, zwei Rechenzentren in verschiedenen Weltregionen zu nutzen, kann aufgrund der Latenz bei der Datenreplikation zu einem höheren Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="35ee2-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="35ee2-108">Beachten Sie bei der Planung, welche Pools als Paar bereitgestellt werden, dass nur die folgenden Paarungen unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="35ee2-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="35ee2-109">Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="35ee2-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="35ee2-110">Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="35ee2-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="35ee2-111">Physische Pools können nur mit anderen physischen Pools gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="35ee2-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="35ee2-112">Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="35ee2-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="35ee2-113">Für Pools, die zusammen gekoppelt sind, muss dasselbe Betriebssystem ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="35ee2-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="35ee2-p104">Eine Paarung zweier Pools, die nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Art von Paarung wird jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35ee2-p104">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations. For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool. However, these types of pairings are not supported.</span></span>

<span data-ttu-id="35ee2-117">Jeder Pool in einem Paar sollte in der Lage sein, alle Benutzer aus beiden Pools im Fall eines Notfalls zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="35ee2-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="35ee2-118">Wenn Sie Enterprise Edition-Pools koppeln, können Sie auch eine höhere Verfügbarkeit auf den Back-End-Servern implementieren, bei Paaren von Standard Edition-Pools sind jedoch nur die Wiederherstellungsmaßnahmen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="35ee2-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


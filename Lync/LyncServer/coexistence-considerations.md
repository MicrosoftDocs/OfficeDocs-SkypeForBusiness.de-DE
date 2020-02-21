---
title: Überlegungen zur Koexistenz
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b31b8f3e534fc7b060f194f84310050a0386d8c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="a86cc-102">Überlegungen zur Koexistenz</span><span class="sxs-lookup"><span data-stu-id="a86cc-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a86cc-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a86cc-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a86cc-104">Nach der Migration ist nur ein lync Server 2013 Server Pool für beständigen Chat vorhanden, und Sie können Ihre Legacy-Bereitstellung außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="a86cc-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="a86cc-105">Bevor die Migration abgeschlossen ist und Sie Ihre aktuelle Gruppen Chat Server-Bereitstellung vollständig außer Betrieb genommen haben, haben Sie möglicherweise eine der folgenden Bereitstellungen:</span><span class="sxs-lookup"><span data-stu-id="a86cc-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="a86cc-106">Lync Server 2013 Server Pool für beständigen Chat, der in einem lync Server 2013-Pool verwaltet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a86cc-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="a86cc-107">Lync Server 2010 Gruppen Chat Pool, der in einem lync Server 2010-Pool verwaltet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a86cc-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="a86cc-108">Office Communications Server 2007 R2 Gruppen Chat-Pool, der in einem Office Communications Server 2007 R2-Pool verwaltet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a86cc-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="a86cc-p101">Diese Bereitstellungen können nebeneinander vorhanden sein. Die Kategorien, Chatrooms und Add-ins in einer Bereitstellung interagieren nicht mit denen einer anderen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a86cc-p101">These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="a86cc-111">Mithilfe der manuellen Konfiguration kann ein Legacyclient (Gruppenchatclient) gleichzeitig eine Verbindung mit einem Pool für Office Communications Server 2007 R2, lync Server 2010, Gruppenchat oder lync Server 2013 herstellen.</span><span class="sxs-lookup"><span data-stu-id="a86cc-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="a86cc-112">Der lync 2013 (Client) kann nur mit dem Serverpool für lync Server 2013, beständigen Chat und nicht mit Legacy-Gruppen Chat Server-Pools interagieren.</span><span class="sxs-lookup"><span data-stu-id="a86cc-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="a86cc-113">Damit der beständige Chat in einem lync 2013 (Client) verwendet werden kann, muss der Benutzer in lync 2013 verwaltet werden und durch eine Richtlinie aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="a86cc-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


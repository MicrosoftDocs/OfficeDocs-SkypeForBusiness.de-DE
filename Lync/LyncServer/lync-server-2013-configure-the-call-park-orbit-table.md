---
title: 'Lync Server 2013: Konfigurieren der Orbittabelle für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="ce088-102">Konfigurieren der Orbittabelle für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce088-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce088-103">_**Letztes Änderungsdatum des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="ce088-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="ce088-104">Call Park verwendet Umlaufbahnen für Park Anrufe.</span><span class="sxs-lookup"><span data-stu-id="ce088-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="ce088-105">Bevor Benutzer Anrufe parken und abrufen können, müssen Sie die Umlaufbahn Tabelle des Anruf Parks konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ce088-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="ce088-106">Sie müssen die Bereiche der Durchwahlnummern (Orbits) angeben, die Ihre Organisation für Park Anrufe reserviert, und den Arbeitsplan für diese Bereiche definieren, indem Sie angeben, welcher Anruf Park Pool für jeden Bereich zuständig ist.</span><span class="sxs-lookup"><span data-stu-id="ce088-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="ce088-107">Wenn Sie Umlaufbahn Bereiche definieren, besteht das Ziel darin, genügend Umlaufbahnen zu haben, damit eine Umlaufbahn nicht zu schnell wieder verwendet wird, aber nicht so viele Umlaufbahnen, dass Sie die Anzahl der für Benutzer oder andere Dienste verfügbaren Erweiterungen einschränken.</span><span class="sxs-lookup"><span data-stu-id="ce088-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="ce088-108">Sie können für jeden lync Server-Pool, in dem die Park-Anwendung bereitgestellt wird, mehrere orbitbereiche für den Anruf Bereich erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce088-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="ce088-109">Jeder Orbit-Bereich für das Parken von Anrufen muss einen global eindeutigen Namen und einen eindeutigen Satz von Erweiterungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ce088-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce088-p102">Ein Orbitbereich umfasst normalerweise 100 oder weniger Orbits. Jeder Bereich kann deutlich größer sein, solange der Höchstwert von 10.000 Orbits pro Bereich nicht überschritten wird und Sie über weniger als 50.000 Orbits pro Pool verfügen. Ist ein Bereich zu klein, werden die Orbits zu schnell wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="ce088-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="ce088-113">Verwenden Sie für Ihre Orbitbereiche Blöcke virtueller Durchwahlnummern (Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist).</span><span class="sxs-lookup"><span data-stu-id="ce088-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce088-114">Das Zuweisen von Direktwahlnummern (DID) als Orbit-Nummern in der Orbit-Tabelle des Anruf Parks wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ce088-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce088-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ce088-115">In This Section</span></span>

[<span data-ttu-id="ce088-116">Erstellen oder Ändern eines orbitbereichs für einen Anruf Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce088-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


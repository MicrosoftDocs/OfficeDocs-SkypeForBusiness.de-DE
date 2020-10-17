---
title: 'Lync Server 2013: Konfigurieren von Durchwahlnummern für das Parken von Anrufen'
description: 'Lync Server 2013: Konfigurieren von Durchwahlnummern für das Parken von anrufen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548831"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="ffbe6-103">Konfigurieren von Durchwahlnummern für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbe6-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffbe6-104">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="ffbe6-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="ffbe6-105">Der Anwendung zum Parken von Anrufen verwendet Durchwahlnummern in der Orbit-Tabelle für das Parken von anrufen, um Anrufe abzustellen.</span><span class="sxs-lookup"><span data-stu-id="ffbe6-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="ffbe6-106">Sie müssen die Orbit-Tabelle für das Parken von Anrufen mit den Bereichen der Durchwahlnummern konfigurieren, die Ihre Organisation für geparkte Anrufe reserviert.</span><span class="sxs-lookup"><span data-stu-id="ffbe6-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="ffbe6-107">Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist).</span><span class="sxs-lookup"><span data-stu-id="ffbe6-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="ffbe6-108">Jeder lync Server Pool, in dem ein Anwendung zum Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ffbe6-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="ffbe6-109">Umlaufbahn Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ffbe6-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ffbe6-110">Sie müssen das Kontrollkästchen <STRONG>Parken von Anrufen</STRONG> in Ihrer VoIP-Richtlinie aktivieren, bevor Sie das Parken von Anrufen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ffbe6-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="ffbe6-111">Diese Option ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ffbe6-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ffbe6-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ffbe6-112">In This Section</span></span>

  - [<span data-ttu-id="ffbe6-113">Erstellen oder Ändern eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbe6-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="ffbe6-114">Löschen eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbe6-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


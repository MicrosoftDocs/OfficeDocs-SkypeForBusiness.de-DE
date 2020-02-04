---
title: 'Lync Server 2013: Konfigurieren von Telefonnummern Erweiterungen für Park Anrufe'
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
ms.openlocfilehash: ba64f4f622a6f9ae9e134b2447abe21bc99ec62c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="a1371-102">Konfigurieren von Telefonnummern Erweiterungen für Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1371-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1371-103">_**Letztes Änderungsdatum des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="a1371-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="a1371-104">Die Anruf Park Anwendung verwendet Durchwahlnummern in der Orbit-Tabelle des Anruf Parks, um Anrufe zu parken.</span><span class="sxs-lookup"><span data-stu-id="a1371-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="a1371-105">Sie müssen die Orbit-Tabelle des Anruf Parks mit den Bereichen der Durchwahlnummern konfigurieren, die Ihre Organisation für geparkte Anrufe reserviert.</span><span class="sxs-lookup"><span data-stu-id="a1371-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="a1371-106">Dabei muss es sich um virtuelle Durchwahlnummern handeln (also Nummern, denen kein Benutzer oder Telefon zugeordnet ist).</span><span class="sxs-lookup"><span data-stu-id="a1371-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="a1371-107">Jeder lync-Server Pool, in dem eine Anruf Park Anwendung bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a1371-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="a1371-108">Umlaufbahn Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="a1371-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1371-109">Sie müssen das Kontrollkästchen <STRONG>Anruf Park aktivieren</STRONG> in Ihrer VoIP-Richtlinie aktivieren, bevor Sie den Anruf Park verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a1371-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="a1371-110">Diese Option ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1371-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1371-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a1371-111">In This Section</span></span>

  - [<span data-ttu-id="a1371-112">Erstellen oder Ändern eines orbitbereichs für einen Anruf Bereich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1371-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="a1371-113">Löschen eines Umlauf Bereichs für einen Anruf Park in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1371-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


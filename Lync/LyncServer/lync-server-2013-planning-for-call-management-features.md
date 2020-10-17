---
title: 'Lync Server 2013: Planen von Funktionen für die Anrufverwaltung'
description: 'Lync Server 2013: Planen von Funktionen für die Anrufverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call management features
ms:assetid: 5f557345-5a04-45d6-b274-c02dbfe41b33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398421(v=OCS.15)
ms:contentKeyID: 48184298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec990aad40baf33365e92e78ee8071216a2add1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554301"
---
# <a name="planning-for-call-management-features-in-lync-server-2013"></a><span data-ttu-id="4fb3c-103">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb3c-103">Planning for call management features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fb3c-104">_**Letztes Änderungsstand des Themas:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="4fb3c-104">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="4fb3c-105">Enterprise-VoIP-anrufverwaltungsfunktionen steuern, wie eingehende Anrufe weitergeleitet und beantwortet werden.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-105">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="4fb3c-106">Lync Server 2013 bietet die folgenden Funktionen für die Anrufverwaltung:</span><span class="sxs-lookup"><span data-stu-id="4fb3c-106">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="4fb3c-107">**Parken von Anrufen**: ermöglicht VoIP-Benutzern das vorübergehende Parken eines Anrufs und das anschließende abholen über das gleiche oder ein anderes Telefon.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-107">**Call Park**:   Enables voice users to temporarily park a call and then pick it up from the same or another phone.</span></span>

  - <span data-ttu-id="4fb3c-108">**Gruppen Abholung**: ermöglicht VoIP-Benutzern das annehmen von anrufen, die für andere VoIP-Benutzer, die der Anrufannahme Gruppe zugewiesen sind, Klingeln.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-108">**Group Pickup**:   Enables voice users to pick up calls that are ringing for other voice users who are assigned to call pickup groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fb3c-109">Die Gruppen Abholung ist neu mit kumulativen Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-109">Group Pickup is new with Cumulative Updates for Lync Server 2013: February 2013.</span></span>

    
    </div>

  - <span data-ttu-id="4fb3c-110">**Reaktionsgruppe**: leitet eingehende Anrufe an Gruppen von Agents mithilfe von Sammelanschlüssen oder interaktiven Sprachantworten (Interactive Voice Response, IVR) weiter.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-110">**Response Group**:   Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="4fb3c-111">**Ansage:**     Gibt eine Nachricht für Anrufe an, die an eine nicht zugewiesene Nummer gesendet werden, oder leitet den Anruf an einer anderen Stelle oder beides weiter.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-111">**Announcement:**    Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="4fb3c-112">Wenn Sie Enterprise-VoIP bereitstellen möchten, können Sie eine oder alle dieser anrufverwaltungsfunktionen implementieren.</span><span class="sxs-lookup"><span data-stu-id="4fb3c-112">If you plan to deploy Enterprise Voice, you can choose to implement any or all of these call management features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4fb3c-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4fb3c-113">In This Section</span></span>

  - [<span data-ttu-id="4fb3c-114">Planung für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb3c-114">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)

  - [<span data-ttu-id="4fb3c-115">Planen der gruppenanrufannahme in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb3c-115">Planning for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-planning-for-group-call-pickup.md)

  - [<span data-ttu-id="4fb3c-116">Planen von Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb3c-116">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)

  - [<span data-ttu-id="4fb3c-117">Planen von Ankündigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb3c-117">Planning for announcements in Lync Server 2013</span></span>](lync-server-2013-planning-for-announcements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


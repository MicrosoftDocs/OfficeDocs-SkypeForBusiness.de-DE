---
title: 'Lync Server 2013: Verwalten von Richtlinien für gehostete Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="15eed-102">Verwalten von Richtlinien für gehostete Voicemail in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15eed-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15eed-103">_**Letztes Änderungsdatum des Themas:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="15eed-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="15eed-104">Eine *Richtlinie für gehostete Voicemail* bietet Informationen für die lync Server 2013 ExUM-Routing Anwendung über den Ort, an den Anrufe für Benutzer weitergeleitet werden sollen, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</span><span class="sxs-lookup"><span data-stu-id="15eed-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15eed-105">In der Regel ist nur eine Richtlinie für gehostete Voicemail erforderlich.</span><span class="sxs-lookup"><span data-stu-id="15eed-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="15eed-106">In vielen Fällen können Sie die globale Richtlinie so ändern, dass Sie allen Ihren Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="15eed-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="15eed-107">Wenn Sie eine Richtlinie mit Website Bereich erstellen, wird Sie automatisch allen Benutzern zugewiesen, die sich auf der angegebenen Website befinden.</span><span class="sxs-lookup"><span data-stu-id="15eed-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="15eed-108">Wenn Sie eine Richtlinie mit benutzerspezifischem Bereich erstellen, müssen Sie Sie explizit Benutzern, Gruppen und Kontaktobjekten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15eed-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="15eed-109">Es ist möglich, mehrere gehostete Voicemail-Richtlinien bereitzustellen, in diesem Fall müssen die Richtlinien jedoch für einzelne Benutzer zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="15eed-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="15eed-110">Ausführliche Informationen zum Planen von gehosteten Voicemail-Richtlinien finden Sie unter [Richtlinien für gehostete Voicemail in lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15eed-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="15eed-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="15eed-111">In This Section</span></span>

  - [<span data-ttu-id="15eed-112">Ändern der Global Hosted Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15eed-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="15eed-113">Erstellen einer gehosteten Voicemail-Richtlinie auf Websiteebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15eed-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="15eed-114">Erstellen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15eed-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="15eed-115">Zuweisen einer pro Benutzer gehosteten Voicemail-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15eed-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


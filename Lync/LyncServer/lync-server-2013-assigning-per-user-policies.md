---
title: 'Lync Server 2013: Zuweisen von Richtlinien für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b80446d9117a37b86c386132aa80439cb568a98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="513b5-102">Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="513b5-103">_**Letztes Änderungsdatum des Themas:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="513b5-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="513b5-104">Sie können einem Benutzer oder einer Gruppe von Benutzern bestimmte Richtlinien zuweisen, um bestimmte Einstellungen anzugeben, die von den Einstellungen abweichen, die in Richtlinien definiert sind, die anderen Benutzern zugewiesen sind, beispielsweise globale Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="513b5-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="513b5-105">Diese Richtlinien werden als Richtlinien für einzelne Benutzer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="513b5-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="513b5-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="513b5-106">In This Section</span></span>

  - [<span data-ttu-id="513b5-107">Zuweisen einer pro-Benutzer-konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="513b5-108">Zuweisen einer clientversionsrichtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="513b5-109">Zuweisen einer pro-Benutzer-PIN-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="513b5-110">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="513b5-111">Zuweisen einer pro-Benutzer-Archivierungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="513b5-112">Zuweisen einer Standortrichtlinie für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="513b5-113">Zuweisen einer Mobilitätsrichtlinie für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="513b5-114">Zuweisen einer beständigen Chat Richtlinie für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="513b5-115">Zuweisen einer benutzerseitigen Wähl Plan Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="513b5-116">Zuweisen einer VoIP-Richtlinie für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="513b5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="513b5-117">See Also</span></span>


[<span data-ttu-id="513b5-118">Verwalten von Benutzern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="513b5-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


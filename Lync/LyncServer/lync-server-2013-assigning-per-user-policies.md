---
title: 'Lync Server 2013: Zuweisen von Richtlinien pro Benutzer'
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
ms.openlocfilehash: acee046ebe05d87e17cd72ef1c5d8d19830d4ee8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="70d63-102">Zuweisen von Richtlinien pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70d63-103">_**Letztes Änderungsstand des Themas:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="70d63-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="70d63-p101">Sie können einem Benutzer oder einer Gruppe von Benutzern bestimmte Richtlinien zuweisen, um spezifische Einstellungen festzulegen, die von denjenigen abweichen, die in Richtlinien für andere Benutzer definiert sind (beispielsweise in globalen Richtlinien). Diese Richtlinien werden Richtlinien auf Benutzerebene genannt.</span><span class="sxs-lookup"><span data-stu-id="70d63-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="70d63-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="70d63-106">In This Section</span></span>

  - [<span data-ttu-id="70d63-107">Zuweisen einer benutzerbezogenen konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="70d63-108">Zuweisen einer clientversionsrichtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="70d63-109">Zuweisen einer benutzerbasierten PIN-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="70d63-110">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="70d63-111">Zuweisen einer benutzerbasierten Archivierungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="70d63-112">Zuweisen einer Standortrichtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="70d63-113">Zuweisen einer benutzerbezogenen Mobilitätsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="70d63-114">Zuweisen einer Richtlinie für beständigen Chat pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="70d63-115">Zuweisen einer benutzerbezogenen Wähl Plan Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="70d63-116">Zuweisen einer VoIP-Richtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70d63-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d63-117">See Also</span></span>


[<span data-ttu-id="70d63-118">Verwalten von Benutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70d63-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


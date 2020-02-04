---
title: Verwalten von Chatrooms
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 416da390f277dfc7179a45e0b1dc989b240ab394
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="82977-102">Verwalten von Chatrooms</span><span class="sxs-lookup"><span data-stu-id="82977-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82977-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="82977-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="82977-104">So erstellen Sie einen neuen Server Raum für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="82977-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="82977-105">-PersistentChatPoolFqdn ist nicht erforderlich, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="82977-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="82977-106">Es gibt nur einen beständigen Chat Server Pool.</span><span class="sxs-lookup"><span data-stu-id="82977-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="82977-107">Sie stellen für die Kategorie einen Pool-FQDN bereit.</span><span class="sxs-lookup"><span data-stu-id="82977-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="82977-108">Sie stellen einen Pool-FQDN zum Hinzufügen des Chatrooms bereit.</span><span class="sxs-lookup"><span data-stu-id="82977-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="82977-109">So nehmen Sie Änderungen an einem vorhandenen beständigen Chat Server Raum vor</span><span class="sxs-lookup"><span data-stu-id="82977-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="82977-110">Windows PowerShell: Mitglieder, Manager und Referenten können gleichzeitig eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="82977-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="82977-111">Sie alle sollten die Teilmenge von AllowedMembers minus DeniedMembers der Host Kategorie sein.</span><span class="sxs-lookup"><span data-stu-id="82977-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="82977-112">Ein Raum mit dem Typ = Normal kann keine Referenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="82977-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="82977-113">Erstellen, abrufen, einrichten, löschen oder Entfernen eines Chatrooms</span><span class="sxs-lookup"><span data-stu-id="82977-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="82977-114">So erstellen Sie einen neuen Raum</span><span class="sxs-lookup"><span data-stu-id="82977-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="82977-115">So stellen Sie einen Raum ein</span><span class="sxs-lookup"><span data-stu-id="82977-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="82977-116">So erhalten Sie ein Zimmer</span><span class="sxs-lookup"><span data-stu-id="82977-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="82977-117">oder</span><span class="sxs-lookup"><span data-stu-id="82977-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="82977-118">Where – Filter unterstützt nur Name und Beschreibung und hilft Ihnen, Räume zu finden, deren Name/Beschreibung mit der Schlüsselwortzeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="82977-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="82977-119">PoolFqdn sucht in einem bestimmten beständigen Chat Server Pool.</span><span class="sxs-lookup"><span data-stu-id="82977-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="82977-120">So löschen Sie einen Raum und löschen Nachrichten aus einem Chatroom</span><span class="sxs-lookup"><span data-stu-id="82977-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="82977-121">oder</span><span class="sxs-lookup"><span data-stu-id="82977-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="82977-122">So entfernen Sie einen Raum</span><span class="sxs-lookup"><span data-stu-id="82977-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="82977-123">oder</span><span class="sxs-lookup"><span data-stu-id="82977-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>


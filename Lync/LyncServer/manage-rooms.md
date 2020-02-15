---
title: Verwalten von Räumen
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
ms.openlocfilehash: 32185d1f6124109bd957b0af4440ee054e872f54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="bc423-102">Verwalten von Räumen</span><span class="sxs-lookup"><span data-stu-id="bc423-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc423-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bc423-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bc423-104">So erstellen Sie einen neuen Server Raum für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="bc423-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc423-105">-PersistentChatPoolFqdn wird nicht benötigt, wenn einer der folgenden zutrifft:</span><span class="sxs-lookup"><span data-stu-id="bc423-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bc423-106">Es gibt nur einen Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="bc423-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="bc423-107">Sie geben einen Pool-FQDN für die Kategorie an.</span><span class="sxs-lookup"><span data-stu-id="bc423-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="bc423-108">Sie stellen einen Pool-FQDN zum Hinzufügen des Raums bereit.</span><span class="sxs-lookup"><span data-stu-id="bc423-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="bc423-109">So nehmen Sie Änderungen an einem vorhandenen beständigen Chat Server Raum vor</span><span class="sxs-lookup"><span data-stu-id="bc423-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="bc423-110">Windows PowerShell: Mitglieder, Manager und Referenten können gleichzeitig festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bc423-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="bc423-111">Sie sollten alle die Teilmenge von AllowedMembers minus "deniedmembers" der Host Kategorie sein.</span><span class="sxs-lookup"><span data-stu-id="bc423-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="bc423-112">Ein Raum, der vom Typ = normal ist, kann keine Referenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc423-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="bc423-113">Erstellen, abrufen, festlegen, löschen oder Entfernen eines Raums</span><span class="sxs-lookup"><span data-stu-id="bc423-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="bc423-114">So erstellen Sie einen neuen Raum</span><span class="sxs-lookup"><span data-stu-id="bc423-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="bc423-115">So legen Sie einen Chatroom fest</span><span class="sxs-lookup"><span data-stu-id="bc423-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="bc423-116">So erhalten Sie einen Raum</span><span class="sxs-lookup"><span data-stu-id="bc423-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="bc423-117">oder</span><span class="sxs-lookup"><span data-stu-id="bc423-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="bc423-118">Where – Filter unterstützt nur Name und Description und hilft Ihnen beim Auffinden von Räumen, deren Name/Beschreibung mit der Schlüsselwortzeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bc423-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="bc423-119">Poolfqdn "sucht in einem bestimmten Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="bc423-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="bc423-120">So löschen Sie einen Raum und löschen Nachrichten aus einem Chatroom</span><span class="sxs-lookup"><span data-stu-id="bc423-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="bc423-121">oder</span><span class="sxs-lookup"><span data-stu-id="bc423-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="bc423-122">So entfernen Sie einen Chatroom</span><span class="sxs-lookup"><span data-stu-id="bc423-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="bc423-123">oder</span><span class="sxs-lookup"><span data-stu-id="bc423-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>


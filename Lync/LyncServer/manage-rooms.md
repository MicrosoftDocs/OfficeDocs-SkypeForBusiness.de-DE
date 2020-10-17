---
title: Verwalten von Räumen
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ddb9e074a0eb0bdd614abb3fa29cd0785d2df42
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527562"
---
# <a name="manage-rooms"></a>Verwalten von Räumen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

So erstellen Sie einen neuen Server Raum für beständigen Chat

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> -PersistentChatPoolFqdn wird nicht benötigt, wenn einer der folgenden zutrifft: 
> <UL>
> <LI>
> <P>Es gibt nur einen Server Pool für beständigen Chat.</P>
> <LI>
> <P>Sie geben einen Pool-FQDN für die Kategorie an.</P>
> <LI>
> <P>Sie stellen einen Pool-FQDN zum Hinzufügen des Raums bereit.</P></LI></UL>



</div>

So nehmen Sie Änderungen an einem vorhandenen beständigen Chat Server Raum vor

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell: Mitglieder, Manager und Referenten können gleichzeitig festgelegt werden. Sie sollten alle die Teilmenge von AllowedMembers minus "deniedmembers" der Host Kategorie sein. Ein Raum, der vom Typ = normal ist, kann keine Referenten enthalten.

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a>Erstellen, abrufen, festlegen, löschen oder Entfernen eines Raums

So erstellen Sie einen neuen Raum

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

So legen Sie einen Chatroom fest

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

So erhalten Sie einen Raum

    Get-CsPersistentChatRoom -Identity <String>

oder

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

Where – Filter unterstützt nur Name und Description und hilft Ihnen beim Auffinden von Räumen, deren Name/Beschreibung mit der Schlüsselwortzeichenfolge übereinstimmt. Poolfqdn "sucht in einem bestimmten Server Pool für beständigen Chat.

So löschen Sie einen Raum und löschen Nachrichten aus einem Chatroom

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

oder

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

So entfernen Sie einen Chatroom

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

oder

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>


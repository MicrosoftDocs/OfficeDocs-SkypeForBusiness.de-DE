---
title: Verwalten von Chatrooms
TOCTitle: Verwalten von Chatrooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205292(v=OCS.15)
ms:contentKeyID: 49295520
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Chatrooms

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

So erstellen Sie einen neuen Server für beständigen Chatroom

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]


> [!IMPORTANT]
> -PersistentChatPoolFqdn ist nicht erforderlich, wenn eine der folgenden Aussagen zutrifft: 
> <UL>
> <LI>
> <P>Es gibt nur einen Serverpool für beständigen Chat.</P>
> <LI>
> <P>Sie stellen für die Kategorie einen Pool-FQDN bereit.</P>
> <LI>
> <P>Sie stellen einen Pool-FQDN zum Hinzufügen des Chatrooms bereit.</P></LI></UL>



So nehmen Sie Änderungen an einem vorhandenen Server für beständigen Chatroom vor

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell: Mitglieder ( Members ), Manager ( Managers ) und Referenten ( Presenters ) können gleichzeitig festgelegt werden. Sie sollten alle Teilmengen von AllowedMembers minus DeniedMembers des Hosts Category sein. Ein Chatroom mit type=normal darf Presenters nicht enthalten.

## Erstellen, Abrufen, Festlegen, Löschen oder Entfernen eines Chatrooms

So erstellen Sie einen Chatroom

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

So legen Sie einen Chatroom fest

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

So rufen Sie einen Chatroom ab

    Get-CsPersistentChatRoom -Identity <String>

oder

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

Dabei unterstützt -filter nur Name und Description und hilft beim Auffinden von Chatrooms, deren Name/Beschreibung mit der Schlüsselwortzeichenfolge übereinstimmt. PoolFqdn sucht in einem bestimmten Serverpool für beständigen Chat.

So löschen Sie einen Chatroom und löschen Nachrichten in einem Chatroom

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

oder

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

So entfernen Sie einen Chatroom

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

oder

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]


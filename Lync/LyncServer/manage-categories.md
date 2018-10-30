---
title: Verwalten von Kategorien
TOCTitle: Verwalten von Kategorien
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204719(v=OCS.15)
ms:contentKeyID: 49293331
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Kategorien

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

So erstellen Sie eine neue Kategorie für den Server für beständigen Chat

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]


> [!IMPORTANT]
> "PersistentChatPoolFqdn" ist nur erforderlich, wenn mehr als ein Serverpool für beständigen Chat vorhanden ist.



So nehmen Sie Änderungen an einer vorhandenen Kategorie für den Server für beständigen Chat vor

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell: "AllowedMembers", "DeniedMembers" und "Creators" können gleichzeitig festgelegt werden. "Creators" sollte die Teilmenge von "AllowedMembers" minus "DeniedMembers" sein. Sie können die Eigenschaften einer Kategorie auch gleichzeitig mit den Mitgliedern und Erstellen festlegen.

## Erstellen, Abrufen, Festlegen oder Entfernen einer Kategorie

So erstellen Sie eine neue Kategorie

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

So rufen Sie eine Kategorie ab

    Get-CsPersistentChatCategory -Identity <String>

oder

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

So legen Sie eine Kategorie fest

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

oder

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

So entfernen Sie eine Kategorie

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

oder

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]


---
title: Verwalten von Add-Ins
TOCTitle: Verwalten von Add-Ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205193(v=OCS.15)
ms:contentKeyID: 49295190
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Add-Ins

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

So erstellen Sie ein neues Server für beständigen Chat-Add-in

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

## Add-In erstellen, abrufen, festlegen oder entfernen

So erstellen Sie ein neues Add-in

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>


> [!IMPORTANT]
> PersistentChatPoolFqdn &lt;String&gt; ist nur dann erforderlich, wenn mehr als ein Serverpool für beständigen Chat vorhanden ist.



So rufen Sie ein Add-in ab

    Get-CsPersistentChatAddin -Identity <String>]

oder

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

So legen Sie ein Add-in fest

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

oder

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

So entfernen Sie ein Add-in

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

oder

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]


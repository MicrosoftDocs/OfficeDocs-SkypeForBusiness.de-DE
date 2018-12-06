---
title: 'Lync Server 2013: Ausführen, Ausstellen, Abrufen, Entfernen oder Festlegen einer Richtlinie für den beständigen Chat'
TOCTitle: Ausführen, Ausstellen, Abrufen, Entfernen oder Festlegen einer Richtlinie für den beständigen Chat
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204810(v=OCS.15)
ms:contentKeyID: 49293716
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen, Ausstellen, Abrufen, Entfernen oder Festlegen einer Richtlinie für den beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

So erstellen Sie eine neue Beständiger Chat-Richtlinie

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

So gewähren Sie eine Beständiger Chat-Richtlinie

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

So rufen Sie eine Beständiger Chat-Richtlinie ab

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

So entfernen Sie eine Beständiger Chat-Richtlinie

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

So legen Sie eine Beständiger Chat-Richtlinie fest

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]


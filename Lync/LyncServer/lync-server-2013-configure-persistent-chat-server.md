---
title: 'Lync Server 2013: Konfigurieren des Server für beständigen Chat'
TOCTitle: Konfigurieren des Server für beständigen Chat
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205054(v=OCS.15)
ms:contentKeyID: 49294624
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

So erstellen Sie eine neue Konfiguration des Beständiger Chats

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

So erhalten Sie die Konfiguration von Beständiger Chat

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

So entfernen Sie die Konfiguration von Beständiger Chat

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

So richten Sie die Konfiguration von Beständiger Chat ein

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Bei Lync Server 2013 wird der gesamte Datenverkehr des Webdiensts auf Lync Server 2013, Front-End-Server unterstützt. Die gcweb01-Adresse auf Server für beständigen Chat ist daher nicht erforderlich. Von uns wird der interne Zugriff auf den Webdienst nach wie vor unterstützt, da wir den Webdienst für das Hochladen/Herunterladen von Dateien nur auf *internen* Websites (nicht auf *externen* Websites für Remotebenutzer) bereitstellen.


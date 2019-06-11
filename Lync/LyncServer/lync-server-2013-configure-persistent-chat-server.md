---
title: 'Lync Server 2013: Konfigurieren des Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ff9c59efeb2eb8106a3fe823c8256c86474f51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a>Konfigurieren des Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

So erstellen Sie eine neue Konfiguration für beständigen Chat

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

So erhalten Sie die Konfiguration für beständigen Chat

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

So entfernen Sie die Konfiguration des beständigen Chats

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

So setzen Sie die Konfiguration für beständigen Chat

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

Bei lync Server 2013 wird der gesamte Webdienstdatenverkehr auf den lync Server 2013-Front-End-Servern unterstützt. Daher ist die gcweb01-Adresse auf dem beständigen Chat Server nicht erforderlich. Wir unterstützen weiterhin den Zugriff auf den internen Webdienst, da wir den Datei Upload/Download-Webdienst nur zur *internen* Website (nicht zur *externen* Website für Remotebenutzer) bereitstellen.

</div>

<span> </span>

</div>

</div>

</div>


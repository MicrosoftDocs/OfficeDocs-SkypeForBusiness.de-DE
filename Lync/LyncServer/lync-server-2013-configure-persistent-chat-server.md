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

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="dfd94-102">Konfigurieren des Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfd94-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfd94-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="dfd94-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="dfd94-104">So erstellen Sie eine neue Konfiguration für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="dfd94-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="dfd94-105">So erhalten Sie die Konfiguration für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="dfd94-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="dfd94-106">So entfernen Sie die Konfiguration des beständigen Chats</span><span class="sxs-lookup"><span data-stu-id="dfd94-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="dfd94-107">So setzen Sie die Konfiguration für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="dfd94-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="dfd94-108">Bei lync Server 2013 wird der gesamte Webdienstdatenverkehr auf den lync Server 2013-Front-End-Servern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dfd94-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="dfd94-109">Daher ist die gcweb01-Adresse auf dem beständigen Chat Server nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dfd94-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="dfd94-110">Wir unterstützen weiterhin den Zugriff auf den internen Webdienst, da wir den Datei Upload/Download-Webdienst nur zur *internen* Website (nicht zur *externen* Website für Remotebenutzer) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dfd94-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


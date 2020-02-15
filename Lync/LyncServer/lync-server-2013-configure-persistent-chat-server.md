---
title: 'Lync Server 2013: Konfigurieren des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c43bfaf3b40a746f09a000cb089509b589e39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="46c06-102">Konfigurieren des Servers für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c06-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c06-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="46c06-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="46c06-104">So erstellen Sie eine neue Konfiguration für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="46c06-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="46c06-105">So rufen Sie die Konfiguration für beständigen Chat auf</span><span class="sxs-lookup"><span data-stu-id="46c06-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="46c06-106">So entfernen Sie die Konfiguration für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="46c06-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="46c06-107">So legen Sie die Konfiguration für beständigen Chat fest</span><span class="sxs-lookup"><span data-stu-id="46c06-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="46c06-108">Für lync Server 2013 wird der gesamte Webdienstdatenverkehr auf dem lync Server 2013, den Front-End-Servern, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46c06-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="46c06-109">Daher ist die gcweb01-Adresse auf dem Server für beständigen Chat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46c06-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="46c06-110">Von uns wird der interne Zugriff auf den Webdienst nach wie vor unterstützt, da wir den Webdienst für das Hochladen/Herunterladen von Dateien nur auf *internen* Websites (nicht auf *externen* Websites für Remotebenutzer) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="46c06-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


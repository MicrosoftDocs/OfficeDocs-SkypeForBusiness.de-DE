---
title: 'Lync Server 2013: ausführen, gewähren, abrufen, entfernen oder Festlegen einer Richtlinie für beständigen Chat'
description: 'Lync Server 2013: ausführen, erteilen, abrufen, entfernen oder Festlegen einer Richtlinie für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run, grant, get, remove, or set Persistent Chat Policy
ms:assetid: 39ccdbe8-fb3d-47bc-96e2-9486b6d317e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204810(v=OCS.15)
ms:contentKeyID: 48183857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45763fa4d521efccd5ada62589e76e893d7a4933
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566291"
---
# <a name="run-grant-get-remove-or-set-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="7bc3c-103">Ausführen, gewähren, abrufen, entfernen oder Festlegen einer Richtlinie für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bc3c-103">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bc3c-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7bc3c-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7bc3c-105">So erstellen Sie eine neue Richtlinie für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="7bc3c-105">To create a new Persistent Chat policy</span></span>

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Enable <Switch Parameter>] [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>] [-InMemory <Switch Parameter>]

<span data-ttu-id="7bc3c-106">So gewähren Sie Richtlinien für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="7bc3c-106">To grant Persistent Chat policy</span></span>

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> -PolicyName <String> [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="7bc3c-107">So rufen Sie Richtlinien für beständigen Chat auf</span><span class="sxs-lookup"><span data-stu-id="7bc3c-107">To get Persistent Chat policy</span></span>

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Filter <String>] [-LocalStore <Switch Parameter>]

<span data-ttu-id="7bc3c-108">So entfernen Sie Richtlinien für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="7bc3c-108">To remove Persistent Chat policy</span></span>

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm <Switch Parameter>] [-Force <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="7bc3c-109">So legen Sie Richtlinien für beständigen Chat fest</span><span class="sxs-lookup"><span data-stu-id="7bc3c-109">To set Persistent Chat policy</span></span>

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] [-Instance < PSObject>]

</div>

<span> </span>

</div>

</div>

</div>


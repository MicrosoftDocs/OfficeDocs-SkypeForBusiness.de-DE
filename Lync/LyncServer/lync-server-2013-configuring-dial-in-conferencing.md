---
title: 'Lync Server 2013: Konfigurieren von Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d722abaf76ef915b7587039cb7732cb281a06308
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5693e-102">Konfigurieren von Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5693e-103">_**Letztes Änderungsdatum des Themas:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="5693e-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="5693e-104">Dieser Abschnitt führt Sie durch die Konfiguration der lync Server 2013-Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="5693e-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5693e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5693e-105">In This Section</span></span>

  - [<span data-ttu-id="5693e-106">Konfigurationsvoraussetzungen und -berechtigungen für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="5693e-107">Prüfliste zur Bereitstellung für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="5693e-108">Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="5693e-109">Sicherstellen, dass die Wähleinstellungen lync Server 2013 Regionen zugewiesen haben</span><span class="sxs-lookup"><span data-stu-id="5693e-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="5693e-110">(Optional) Überprüfen der PIN-Richtlinieneinstellungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="5693e-111">Konfigurieren von Konferenzrichtlinien für die Einwahl in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="5693e-112">Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="5693e-113">(Optional) Überprüfen der Einwahlkonferenzeinstellungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="5693e-114">(Optional) Ändern der Tastenzuordnung für DTMF-Befehle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="5693e-115">(Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="5693e-116">(Optional) Überprüfen von Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="5693e-117">Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="5693e-118">Konfigurieren der Benutzerkontoeinstellungen  in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="5693e-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="5693e-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="5693e-120">(Optional) Einladen von Benutzern zu Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="5693e-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5693e-121">Related Sections</span></span>

[<span data-ttu-id="5693e-122">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5693e-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


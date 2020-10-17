---
title: Verbleibenden Benutzer in lync Server 2013 verlagern
description: Verschiebe die verbleibenden Benutzer in lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291b58d6644f9ac8f10c63f6585ba865602580df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571311"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="3504f-103">Verbleibenden Benutzer in lync Server 2013 verlagern</span><span class="sxs-lookup"><span data-stu-id="3504f-103">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3504f-104">_**Letztes Änderungsstand des Themas:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="3504f-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="3504f-105">Sie können Benutzer mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell zur neuen lync Server 2013-Bereitstellung migrieren.</span><span class="sxs-lookup"><span data-stu-id="3504f-105">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="3504f-106">Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu lync Server 2013 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="3504f-106">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="3504f-107">Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="3504f-107">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="3504f-108">Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="3504f-108">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3504f-109">Sie können nicht das Snap-in Active Directory Benutzer und Computer oder die lync Server 2010 Verwaltungstools verwenden, um Benutzer aus ihrer Legacyumgebung in lync Server 2013 zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="3504f-109">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="3504f-110">Wenn Sie einen Benutzer in einen lync Server 2013 Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3504f-110">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3504f-111">Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="3504f-111">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="3504f-112">Wenn beispielsweise ein älterer Benutzer eine " <STRONG>Meine Besprechung</STRONG> "-Konferenz konfiguriert hat, ist diese Konferenz weiterhin im neuen lync Server 2013 Pool verfügbar, nachdem der Benutzer verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="3504f-112">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="3504f-113">Die Details für den Zugriff auf diese Besprechung sind die gleiche <STRONG>Konferenz-URL und Konferenz-ID</STRONG> wie vorher.</span><span class="sxs-lookup"><span data-stu-id="3504f-113">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="3504f-114">Der einzige Unterschied besteht darin, dass die Konferenz nun im lync Server 2013 Pool und nicht im lync Server 2010-Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3504f-114">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3504f-115">Für das Homing von Benutzern in lync Server 2013 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3504f-115">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="3504f-116">Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="3504f-116">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="3504f-117">Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="3504f-117">Post Migration Task</span></span>

1.  <span data-ttu-id="3504f-118">Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="3504f-118">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="3504f-119">Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die auf lync Server 2013 verwaltet werden, nahtlos mit Verbundbenutzern zusammenarbeiten, die in lync Server 2010 verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="3504f-119">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="3504f-120">Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **ermöglichen Teilnehmern das einladen anonymer Benutzer** , die in lync Server 2013 Systemsteuerung ausgewählt wurden, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der lync Server-Verwaltungsshell auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3504f-120">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="3504f-121">Ausführliche Informationen zum Konfigurieren der konferenzrichtlinie mithilfe lync Server-Verwaltungsshell finden Sie unter [Festlegen von CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="3504f-121">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Verbleibenden Benutzer in lync Server 2013 verlagern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81d74c9cc578909061d098d349e685817b71e4d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500172"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="1362f-102">Verbleibenden Benutzer in lync Server 2013 verlagern</span><span class="sxs-lookup"><span data-stu-id="1362f-102">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1362f-103">_**Letztes Änderungsstand des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="1362f-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="1362f-104">Sie können Benutzer mithilfe von lync Server-Systemsteuerung oder lync Server-Verwaltungsshell zur neuen lync Server 2013-Bereitstellung migrieren.</span><span class="sxs-lookup"><span data-stu-id="1362f-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="1362f-105">Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu lync Server 2013 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="1362f-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="1362f-106">Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="1362f-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="1362f-107">Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 6: Verschieben von Benutzern in den Pilot Pool](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="1362f-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1362f-108">Sie können nicht das Snap-in Active Directory Benutzer und Computer oder die Microsoft Office Communications Server 2007 R2 Verwaltungstools verwenden, um Benutzer aus ihrer Legacyumgebung in lync Server 2013 zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="1362f-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1362f-p102">Die Verwendung des <STRONG>Move-CsLegacyUser</STRONG>-Cmdlets setzt voraus, dass Benutzernamen im korrekten Format ohne vorangestellte oder nachgestellte Leerzeichen vorliegen. Sie können ein Benutzerkonto nicht mithilfe des <STRONG>Move-CsLegacyUser</STRONG>-Cmdlets verschieben, wenn der Name vorangestellte oder nachgestellte Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="1362f-p102">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces. You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="1362f-111">Wenn Sie einen Benutzer in einen lync Server 2013 Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1362f-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1362f-112">Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="1362f-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="1362f-113">Wenn beispielsweise ein älterer Benutzer eine " <STRONG>Meine Besprechung</STRONG> "-Konferenz konfiguriert hat, ist diese Konferenz nach dem Verschieben des Benutzers weiterhin im neuen lync Server 2013 Pool verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1362f-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="1362f-114">Die Details für den Zugriff auf diese Besprechung sind die gleiche <STRONG>Konferenz-URL und Konferenz-ID</STRONG> wie vorher.</span><span class="sxs-lookup"><span data-stu-id="1362f-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="1362f-115">Der einzige Unterschied besteht darin, dass die Konferenz nun im lync Server 2013 Pool und nicht in Office Communications Server 2007 R2 Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="1362f-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1362f-116">Für das Homing von Benutzern in lync Server 2013 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1362f-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="1362f-117">Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="1362f-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="1362f-118">Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="1362f-118">Post Migration Task</span></span>

1.  <span data-ttu-id="1362f-119">Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="1362f-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="1362f-120">Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die auf lync Server 2013 verwaltet werden, nahtlos mit Verbundbenutzern zusammenarbeiten, die in Office Communications Server 2007 R2 verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="1362f-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="1362f-121">Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **ermöglichen Teilnehmern das einladen anonymer Benutzer** , die in lync Server 2013 Systemsteuerung ausgewählt wurden, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der lync Server-Verwaltungsshell auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1362f-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="1362f-122">Ausführliche Informationen zum Konfigurieren der konferenzrichtlinie mithilfe lync Server-Verwaltungsshell finden Sie unter [Festlegen von CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in der lync Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="1362f-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Verschieben der verbleibenden Benutzer zu Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a728afae37c2e8d317cd6c75872c75d358226475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="97d83-102">Verschieben der verbleibenden Benutzer zu Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d83-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97d83-103">_**Letztes Änderungsdatum des Themas:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="97d83-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="97d83-104">Mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell können Sie Benutzer zur neuen lync Server 2013-Bereitstellung verschieben.</span><span class="sxs-lookup"><span data-stu-id="97d83-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="97d83-105">Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu lync Server 2013 zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="97d83-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="97d83-106">Details zu den Voraussetzungen für die Durchführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="97d83-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="97d83-107">Detaillierte Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 6: Verschieben von Benutzern in den Pilot Pool](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="97d83-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97d83-108">Sie können das Snap-in Active Directory-Benutzer und-Computer oder die Verwaltungstools von Microsoft Office Communications Server 2007 R2 nicht verwenden, um Benutzer aus ihrer Legacyumgebung in lync Server 2013 zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="97d83-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97d83-109">Das Cmdlet <STRONG>Move-CsLegacyUser</STRONG> setzt voraus, dass Benutzernamen richtig formatiert sind und keine führenden oder nachfolgenden Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="97d83-109">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces.</span></span> <span data-ttu-id="97d83-110">Sie können ein Benutzerkonto nicht mithilfe des Cmdlets <STRONG>Move-CsLegacyUser</STRONG> verschieben, wenn es führende oder nachgestellte Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="97d83-110">You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="97d83-111">Wenn Sie einen Benutzer in einen lync Server 2013-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="97d83-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97d83-112">Dazu gehören die vom Legacy Benutzer erstellten aktiven Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="97d83-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="97d83-113">Wenn ein älterer Benutzer beispielsweise eine Konferenz für <STRONG>Meine Besprechung</STRONG> konfiguriert hat, steht diese Konferenz nach dem Verschieben des Benutzers weiterhin im neuen lync Server 2013-Pool zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="97d83-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="97d83-114">Die Details für den Zugriff auf die Besprechung sind weiterhin dieselbe <STRONG>Konferenz-URL und Konferenz-ID</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="97d83-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="97d83-115">Der einzige Unterschied besteht darin, dass die Konferenz jetzt im lync Server 2013-Pool und nicht im Office Communications Server 2007 R2-Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="97d83-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="97d83-116">Für Homing-Benutzer in lync Server 2013 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="97d83-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="97d83-117">Neue Funktionen stehen Benutzern nur zur Verfügung, wenn Sie ein Upgrade auf die neue Client Software durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="97d83-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="97d83-118">Aufgabe der nach der Migration</span><span class="sxs-lookup"><span data-stu-id="97d83-118">Post Migration Task</span></span>

1.  <span data-ttu-id="97d83-119">Nachdem Sie die Benutzer verschoben haben, überprüfen Sie die konferenzrichtlinie, die Ihnen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="97d83-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="97d83-120">Um sicherzustellen, dass Besprechungen, die von Benutzern verwaltet werden, die in lync Server 2013 verwaltet werden, nahtlos mit Verbundbenutzern funktionieren, die sich auf Office Communications Server 2007 R2 befinden, sollten die den migrierten Benutzern zugewiesenen Konferenzrichtlinien anonymen Teilnehmern ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="97d83-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="97d83-121">Konferenzrichtlinien, die anonymen Teilnehmern gestatten, **Teilnehmern die Möglichkeit zu geben,** in der lync Server 2013 \*\*\*\* -Systemsteuerung ausgewählte anonyme Benutzer einzuladen, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe von das Cmdlet " **Get-CsConferencingPolicy** " in der lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="97d83-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="97d83-122">Details zum Konfigurieren von Konferenzrichtlinien mithilfe der lync Server-Verwaltungsshell finden Sie unter Dokumentation zu CsConferencingPolicy in der lync Server [-](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="97d83-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Verschieben der verbleibenden Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Sie können Benutzer über die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell zur neuen Skype for Business Server 2019-Bereitstellung bewegen. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 zu gewährleisten. Details zu den Voraussetzungen für die Durchführung der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Detaillierte Anweisungen zum Verschieben von Benutzern finden Sie unter Phase 4: Verschieben von Testbenutzern in den Pilot Pool.'
ms.openlocfilehash: ac384e9f9e4aaaa534f5b646f1d847485dbb4c23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813263"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="75391-106">Verschieben von verbleibenden Benutzern in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="75391-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="75391-107">Sie können Benutzer über die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell zur neuen Skype for Business Server 2019-Bereitstellung bewegen.</span><span class="sxs-lookup"><span data-stu-id="75391-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="75391-108">Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="75391-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="75391-109">Details zu den Voraussetzungen für die Durchführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="75391-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="75391-110">Detaillierte Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="75391-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="75391-111">Sie können das Snap-in Active Directory-Benutzer und-Computer oder die Legacy-Verwaltungstools nicht verwenden, um Benutzer aus ihrer Legacyumgebung in Skype for Business Server 2019 zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="75391-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="75391-112">Wenn Sie einen Benutzer in einen Skype for Business Server 2019-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="75391-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="75391-113">Dazu gehören die vom Legacy Benutzer erstellten aktiven Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="75391-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="75391-114">Wenn ein älterer Benutzer beispielsweise eine Konferenz für **Meine Besprechung** konfiguriert hat, steht diese Konferenz nach dem Verschieben des Benutzers weiterhin im neuen Skype for Business Server 2019-Pool zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="75391-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="75391-115">Die Details für den Zugriff auf die Besprechung sind weiterhin dieselbe **Konferenz-URL und Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="75391-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="75391-116">Der einzige Unterschied besteht darin, dass die Konferenz jetzt im Skype for Business Server 2019-Pool und nicht im Legacy Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="75391-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75391-117">Für Homing-Benutzer in Skype for Business Server 2019 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75391-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="75391-118">Neue Funktionen stehen Benutzern nur zur Verfügung, wenn Sie ein Upgrade auf die neue Client Software durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="75391-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="75391-119">Aufgabe der nach der Migration</span><span class="sxs-lookup"><span data-stu-id="75391-119">Post migration task</span></span>

1. <span data-ttu-id="75391-120">Nachdem Sie die Benutzer verschoben haben, überprüfen Sie die konferenzrichtlinie, die Ihnen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="75391-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="75391-121">Um sicherzustellen, dass Besprechungen, die von Benutzern verwaltet werden, die sich in Skype for Business Server 2019 befinden, nahtlos mit Verbundbenutzern zusammenarbeiten, die bei der Legacy Installation verwaltet werden, sollten die den migrierten Benutzern zugewiesenen Konferenzrichtlinien anonymen Teilnehmern ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="75391-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="75391-122">Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **können Teilnehmern erlauben, anonyme Benutzer einzuladen** , die in der Skype for Business Server 2019-Systemsteuerung ausgewählt sind, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der Skype for Business Server-Verwaltungsshell auf " **true** " festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="75391-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


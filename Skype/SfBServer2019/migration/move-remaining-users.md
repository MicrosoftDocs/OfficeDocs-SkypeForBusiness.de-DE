---
title: Verschieben der restlichen Benutzer
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Sie können Benutzer in die neue Skype for Business Server 2019-Bereitstellung über Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell migrieren. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter Phase 4: Verschieben von Testbenutzern in den Pilot Pool.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753713"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="81257-106">Verschiebe verbleibenden Benutzer auf Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="81257-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="81257-107">Sie können Benutzer in die neue Skype for Business Server 2019-Bereitstellung über Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell migrieren.</span><span class="sxs-lookup"><span data-stu-id="81257-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="81257-108">Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="81257-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="81257-109">Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="81257-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="81257-110">Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="81257-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="81257-111">Sie können nicht das Snap-in Active Directory Benutzer und Computer oder die Legacy-Verwaltungstools verwenden, um Benutzer aus ihrer Legacyumgebung in Skype for Business Server 2019 zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="81257-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="81257-112">Wenn Sie einen Benutzer in einen Skype for Business Server 2019-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="81257-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="81257-113">Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="81257-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="81257-114">Wenn beispielsweise ein älterer Benutzer eine " **Meine Besprechung** "-Konferenz konfiguriert hat, ist diese Konferenz weiterhin im neuen Skype for Business Server 2019-Pool verfügbar, nachdem der Benutzer verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="81257-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="81257-115">Die Details für den Zugriff auf diese Besprechung sind die gleiche **Konferenz-URL und Konferenz-ID** wie vorher.</span><span class="sxs-lookup"><span data-stu-id="81257-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="81257-116">Der einzige Unterschied besteht darin, dass die Konferenz nun im Pool Skype for Business Server 2019 und nicht im Legacy Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="81257-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="81257-117">Für das Homing von Benutzern in Skype for Business Server 2019 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="81257-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="81257-118">Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="81257-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="81257-119">Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="81257-119">Post migration task</span></span>

1. <span data-ttu-id="81257-120">Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="81257-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="81257-121">Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die in Skype for Business Server 2019 verwaltet werden, nahtlos mit Verbundbenutzern zusammenarbeiten, die in einer Legacy Installation verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="81257-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="81257-122">Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **ermöglichen Teilnehmern das einladen anonymer Benutzer** in Skype for Business Server 2019-Systemsteuerung und haben in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der Skype for Business Server Verwaltungsshell **AllowAnonymousParticipantsInMeetings** auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="81257-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


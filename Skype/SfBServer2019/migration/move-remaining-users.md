---
title: Verschieben der verbleibenden Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Sie können Benutzer in der neuen Skype für Business Server 2019 Bereitstellung verschieben, unter Verwendung von entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell. Sie müssen einige Anforderungen um einen reibungslosen Übergang zur Skype für Business Server 2019 sicherzustellen erfüllen. Ausführliche Informationen zu den erforderlichen Komponenten bis zum Abschluss der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Ausführliche Schritte zum Verschieben von Benutzern, finden Sie unter Phase 4: Verschieben von Testbenutzern in den pilotpool.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231588"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="ae094-106">Verschieben der restlichen Benutzer zu Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="ae094-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="ae094-107">Sie können Benutzer in der neuen Skype für Business Server 2019 Bereitstellung verschieben, unter Verwendung von entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="ae094-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ae094-108">Sie müssen einige Anforderungen um einen reibungslosen Übergang zur Skype für Business Server 2019 sicherzustellen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ae094-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="ae094-109">Ausführliche Informationen zu den erforderlichen Komponenten bis zum Abschluss der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="ae094-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="ae094-110">Ausführliche Schritte zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den pilotpool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ae094-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ae094-111">Sie können nicht das Snap-in Active Directory-Benutzer und-Computer oder die Vorversion Verwaltungstools verwenden, um Benutzer aus der vorgängerumgebung nach Skype für Business Server 2019 verschieben.</span><span class="sxs-lookup"><span data-stu-id="ae094-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="ae094-112">Wenn Sie einen Benutzer in einen Skype für Business Server 2019 Pool verschieben, werden die Daten für den Benutzer mit der Back-End-Datenbank verschoben, die den neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ae094-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ae094-113">Dazu gehören die aktiven Besprechungen vom legacy Benutzer erstellt.</span><span class="sxs-lookup"><span data-stu-id="ae094-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="ae094-114">Beispielsweise wenn ein älterer Benutzer eine Konferenz **meiner Besprechung** konfiguriert hat, werden der Konferenz in die neue Skype für Business Server 2019 Pool verfügbar, nachdem der Benutzer verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="ae094-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="ae094-115">Die Details zum Zugriff auf diese Besprechung werden die gleichen **Konferenz-URL und Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="ae094-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="ae094-116">Der einzige Unterschied ist, dass die Konferenz jetzt in die Skype für Business Server 2019 Pool und nicht im Pool Vorgängerversion gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ae094-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae094-117">Das Verwalten von Benutzern in Skype für Business Server 2019 nicht erfordert, dass Sie aktualisierte Clients zur selben Zeit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ae094-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="ae094-118">Neuer Funktionen werden für Benutzer verfügbar, nur, wenn sie auf die neue Clientsoftware aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="ae094-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="ae094-119">Aufgaben nach der migration</span><span class="sxs-lookup"><span data-stu-id="ae094-119">Post migration task</span></span>

1. <span data-ttu-id="ae094-120">Nachdem Sie Benutzer verschieben möchten, überprüfen Sie die konferenzrichtlinie, die ihnen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ae094-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="ae094-121">Um sicherzustellen, dass Benutzer organisierte Besprechungen in Skype für die Arbeit mit partnerverbundbenutzern Business Server 2019 verwaltet, die in älteren Install verwaltet werden, sollte die den migrierten Benutzern zugeordnete konferenzrichtlinie anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="ae094-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="ae094-122">Legen Sie konferenzrichtlinien, anonyme Teilnehmer haben **anonyme Benutzer einladen von Teilnehmern gestatten** für Business Server 2019 Control Panel in Skype ausgewählt und **AllowAnonymousParticipantsInMeetings** auf **true fest,** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="ae094-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


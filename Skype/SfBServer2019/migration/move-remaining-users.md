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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878324"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="8f963-106">Verschieben der restlichen Benutzer zu Skype für Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8f963-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="8f963-107">Sie können Benutzer in der neuen Skype für Business Server 2019 Bereitstellung verschieben, unter Verwendung von entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8f963-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8f963-108">Sie müssen einige Anforderungen um einen reibungslosen Übergang zur Skype für Business Server 2019 sicherzustellen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8f963-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="8f963-109">Ausführliche Informationen zu den erforderlichen Komponenten bis zum Abschluss der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="8f963-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="8f963-110">Ausführliche Schritte zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den pilotpool](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8f963-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f963-111">Sie können nicht das Snap-in Active Directory-Benutzer und-Computer oder die Vorversion Verwaltungstools verwenden, um Benutzer aus der vorgängerumgebung nach Skype für Business Server 2019 verschieben.</span><span class="sxs-lookup"><span data-stu-id="8f963-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="8f963-112">Wenn Sie einen Benutzer in einen Skype für Business Server 2019 Pool verschieben, werden die Daten für den Benutzer mit der Back-End-Datenbank verschoben, die den neuen Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8f963-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8f963-113">Dazu gehören die aktiven Besprechungen vom legacy Benutzer erstellt.</span><span class="sxs-lookup"><span data-stu-id="8f963-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="8f963-114">Beispielsweise wenn ein älterer Benutzer eine Konferenz **meiner Besprechung** konfiguriert hat, werden der Konferenz in die neue Skype für Business Server 2019 Pool verfügbar, nachdem der Benutzer verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="8f963-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="8f963-115">Die Details zum Zugriff auf diese Besprechung werden die gleichen **Konferenz-URL und Konferenz-ID**.</span><span class="sxs-lookup"><span data-stu-id="8f963-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="8f963-116">Der einzige Unterschied ist, dass die Konferenz jetzt in die Skype für Business Server 2019 Pool und nicht im Pool Vorgängerversion gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="8f963-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8f963-117">Das Verwalten von Benutzern in Skype für Business Server 2019 nicht erfordert, dass Sie aktualisierte Clients zur selben Zeit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8f963-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="8f963-118">Neuer Funktionen werden für Benutzer verfügbar, nur, wenn sie auf die neue Clientsoftware aktualisiert haben.</span><span class="sxs-lookup"><span data-stu-id="8f963-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="8f963-119">Aufgaben nach der migration</span><span class="sxs-lookup"><span data-stu-id="8f963-119">Post migration task</span></span>

1. <span data-ttu-id="8f963-120">Nachdem Sie Benutzer verschieben möchten, überprüfen Sie die konferenzrichtlinie, die ihnen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8f963-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="8f963-121">Um sicherzustellen, dass Benutzer organisierte Besprechungen in Skype für die Arbeit mit partnerverbundbenutzern Business Server 2019 verwaltet, die in älteren Install verwaltet werden, sollte die den migrierten Benutzern zugeordnete konferenzrichtlinie anonyme Teilnehmer zulassen.</span><span class="sxs-lookup"><span data-stu-id="8f963-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="8f963-122">Legen Sie konferenzrichtlinien, anonyme Teilnehmer haben **anonyme Benutzer einladen von Teilnehmern gestatten** für Business Server 2019 Control Panel in Skype ausgewählt und **AllowAnonymousParticipantsInMeetings** auf **true fest,** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8f963-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    


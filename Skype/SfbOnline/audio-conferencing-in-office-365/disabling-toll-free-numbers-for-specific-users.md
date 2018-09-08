---
title: Deaktivieren von gebührenfreie Nummern für bestimmte Skype für Business Online-Benutzern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Nummern für ihre Besprechungen verwenden können.
ms.openlocfilehash: b438ee16135485a79458869858c52dd35bafa560
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885171"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="41e34-103">Deaktivieren von gebührenfreie Nummern für bestimmte Skype für Business Online-Benutzern</span><span class="sxs-lookup"><span data-stu-id="41e34-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="41e34-104">Informationen zu deaktivieren Tool frei Zahlen für Teams Benutzer finden Sie unter [gebührenfreie Nummern bestimmte Teams Benutzer deaktivieren](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="41e34-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="41e34-105">Wenn Ihre Organisation gebührenfreie Nummern in der Microsoft Audio Conferencing Bridge verfügt, können Sie erlauben oder verhindern ihrer Verwendung in Besprechungen von bestimmten Organisatoren durch.</span><span class="sxs-lookup"><span data-stu-id="41e34-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="41e34-106">Standardmäßig werden alle Benutzer in Ihrer Organisation aktiviert, für die Verwendung von gebührenfreier Nummern, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern verwendet werden können an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="41e34-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="41e34-107">Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer einschränken, verwenden Sie diese Nummern in ihre Besprechungen über eine gebührenfreie Nummern Aktivierung-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="41e34-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="41e34-108">Wenn für einen bestimmten Organizer gebührenfreie Nummern deaktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="41e34-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="41e34-109">Eine gebührenfreie Nummer wird nicht mehr in seinem enthalten sein oder ihrer Besprechung eingeladen.</span><span class="sxs-lookup"><span data-stu-id="41e34-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="41e34-110">Gebührenfreie Nummern werden nicht mehr auf der Seite mit "Hier finden Sie eine lokale Nummer", die in seinem verwiesen wird aufgelistet oder ihrer Besprechung eingeladen.</span><span class="sxs-lookup"><span data-stu-id="41e34-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="41e34-111">Teilnehmer möglich nicht, der des angegebenen Organisators die Besprechung teilnehmen, wenn sie eine beliebige gebührenfreie Telefonnummer des Unternehmens wählen.</span><span class="sxs-lookup"><span data-stu-id="41e34-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="41e34-112">Der Organisator alle Besprechungen werden automatisch neu geplant, und die gebührenfreie Telefonnummer daraus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="41e34-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="41e34-113">Dies erneut alle des Dialogfelds Organisieren der e-Mail-Einladungen an alle Teilnehmer der Besprechungen senden.</span><span class="sxs-lookup"><span data-stu-id="41e34-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="41e34-114">Teilnehmer können weiterhin teilnehmen an Besprechungen des Dialogfelds Organisieren von gebührenfreie Nummern.</span><span class="sxs-lookup"><span data-stu-id="41e34-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="41e34-115">Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="41e34-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="41e34-116">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.</span><span class="sxs-lookup"><span data-stu-id="41e34-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="41e34-117">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="41e34-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="41e34-118">Deaktivieren **von gebührenfreie Nummern zum Teilnehmen an Besprechungen dieses Benutzers zulassen**.</span><span class="sxs-lookup"><span data-stu-id="41e34-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="41e34-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="41e34-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="41e34-120">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="41e34-120">**Using PowerShell**</span></span>  

<span data-ttu-id="41e34-121">Den AllowTollFreeDialIn-Parameter des Set-CsOnlineDialInConferencingUser-Cmdlets können zum Aktivieren oder Deaktivieren dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="41e34-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="41e34-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41e34-122">For example:</span></span> 

 - <span data-ttu-id="41e34-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="41e34-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>

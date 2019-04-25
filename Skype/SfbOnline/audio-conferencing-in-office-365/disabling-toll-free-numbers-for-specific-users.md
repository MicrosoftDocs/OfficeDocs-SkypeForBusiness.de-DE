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
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229281"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="ea3d1-103">Deaktivieren von gebührenfreie Nummern für bestimmte Skype für Business Online-Benutzern</span><span class="sxs-lookup"><span data-stu-id="ea3d1-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="ea3d1-104">Informationen zu deaktivieren Tool frei Zahlen für Teams Benutzer finden Sie unter [gebührenfreie Nummern bestimmte Teams Benutzer deaktivieren](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="ea3d1-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="ea3d1-105">Wenn Ihre Organisation gebührenfreie Nummern in der Microsoft Audio Conferencing Bridge verfügt, können Sie erlauben oder verhindern ihrer Verwendung in Besprechungen von bestimmten Organisatoren durch.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="ea3d1-106">Standardmäßig werden alle Benutzer in Ihrer Organisation aktiviert, für die Verwendung von gebührenfreier Nummern, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern verwendet werden können an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="ea3d1-107">Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer einschränken, verwenden Sie diese Nummern in ihre Besprechungen über eine gebührenfreie Nummern Aktivierung-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="ea3d1-108">Wenn für einen bestimmten Organizer gebührenfreie Nummern deaktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="ea3d1-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="ea3d1-109">Eine gebührenfreie Nummer wird nicht mehr in seinem enthalten sein oder ihrer Besprechung eingeladen.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="ea3d1-110">Gebührenfreie Nummern werden nicht mehr auf der Seite mit "Hier finden Sie eine lokale Nummer", die in seinem verwiesen wird aufgelistet oder ihrer Besprechung eingeladen.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="ea3d1-111">Teilnehmer möglich nicht, der des angegebenen Organisators die Besprechung teilnehmen, wenn sie eine beliebige gebührenfreie Telefonnummer des Unternehmens wählen.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="ea3d1-112">Der Organisator alle Besprechungen werden automatisch neu geplant, und die gebührenfreie Telefonnummer daraus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="ea3d1-113">Dies erneut alle des Dialogfelds Organisieren der e-Mail-Einladungen an alle Teilnehmer der Besprechungen senden.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="ea3d1-114">Teilnehmer können weiterhin teilnehmen an Besprechungen des Dialogfelds Organisieren von gebührenfreie Nummern.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="ea3d1-115">Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="ea3d1-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="ea3d1-116">Aus dem **Microsoft-Teams, Administrationscenter**:</span><span class="sxs-lookup"><span data-stu-id="ea3d1-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ea3d1-117">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ea3d1-118">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="ea3d1-119">**Gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer umfassen** auf **deaktiviert**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="ea3d1-120">Klicken Sie auf **zu speichern.**</span><span class="sxs-lookup"><span data-stu-id="ea3d1-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="ea3d1-121">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ea3d1-121">**Using PowerShell**</span></span>  

<span data-ttu-id="ea3d1-122">Den AllowTollFreeDialIn-Parameter des Set-CsOnlineDialInConferencingUser-Cmdlets können zum Aktivieren oder Deaktivieren dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ea3d1-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="ea3d1-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ea3d1-123">For example:</span></span> 

- <span data-ttu-id="ea3d1-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="ea3d1-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>

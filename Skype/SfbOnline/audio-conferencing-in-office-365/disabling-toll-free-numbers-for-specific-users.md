---
title: Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Nummern für ihre Besprechungen verwenden können.
ms.openlocfilehash: 2f506163ce815f71d18935040dbf13bf4af4f04c
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2018
ms.locfileid: "20324141"
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="cd599-103">Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="cd599-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="cd599-104">Wenn Ihre Organisation gebührenfreie Nummern in der Microsoft Audio Conferencing Bridge verfügt, können Sie erlauben oder verhindern ihrer Verwendung in Besprechungen von bestimmten Organisatoren durch.</span><span class="sxs-lookup"><span data-stu-id="cd599-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="cd599-105">Standardmäßig werden alle Benutzer in Ihrer Organisation aktiviert, für die Verwendung von gebührenfreier Nummern, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern verwendet werden können an einer Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="cd599-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="cd599-106">Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer einschränken, verwenden Sie diese Nummern in ihre Besprechungen über eine gebührenfreie Nummern Aktivierung-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cd599-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="cd599-107">Wenn für einen bestimmten Organizer gebührenfreie Nummern deaktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="cd599-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="cd599-108">Eine gebührenfreie Nummer wird nicht mehr in seinem enthalten sein oder ihrer Besprechung eingeladen.</span><span class="sxs-lookup"><span data-stu-id="cd599-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="cd599-109">Gebührenfreie Nummern werden nicht mehr auf der Seite mit "Hier finden Sie eine lokale Nummer", die in seinem verwiesen wird aufgelistet oder ihrer Besprechung eingeladen.</span><span class="sxs-lookup"><span data-stu-id="cd599-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="cd599-110">Teilnehmer möglich nicht, der des angegebenen Organisators die Besprechung teilnehmen, wenn sie eine beliebige gebührenfreie Telefonnummer des Unternehmens wählen.</span><span class="sxs-lookup"><span data-stu-id="cd599-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="cd599-111">Der Organisator alle Besprechungen werden automatisch neu geplant, und die gebührenfreie Telefonnummer daraus entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="cd599-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="cd599-112">Dies erneut alle des Dialogfelds Organisieren der e-Mail-Einladungen an alle Teilnehmer der Besprechungen senden.</span><span class="sxs-lookup"><span data-stu-id="cd599-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="cd599-113">Teilnehmer können weiterhin teilnehmen an Besprechungen des Dialogfelds Organisieren von gebührenfreie Nummern.</span><span class="sxs-lookup"><span data-stu-id="cd599-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="cd599-114">Deaktivieren von gebührenfreien Nummern für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="cd599-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="cd599-115">![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="cd599-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="cd599-116">Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="cd599-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="cd599-117">Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="cd599-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="cd599-118">Klicken Sie auf das Menü neben **Konferenz Brücken**, und klicken Sie dann auf **Bearbeiten** , in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="cd599-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="cd599-119">Deaktivieren Sie im Bereich **Konferenz Bridge Anbieter** **Zulassen gebührenfreie Nummern in die Konferenzbrücke Ihrer Organisation zur Teilnahme an Besprechungen dieses Benutzers verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="cd599-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="cd599-120">Klicken Sie auf **anwenden.**</span><span class="sxs-lookup"><span data-stu-id="cd599-120">Click **Apply.**</span></span> 

<span data-ttu-id="cd599-121">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="cd599-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="cd599-122">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cd599-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="cd599-123">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="cd599-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="cd599-124">Deaktivieren **von gebührenfreie Nummern zum Teilnehmen an Besprechungen dieses Benutzers zulassen**.</span><span class="sxs-lookup"><span data-stu-id="cd599-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="cd599-125">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cd599-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="cd599-126">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cd599-126">**Using PowerShell**</span></span>  

<span data-ttu-id="cd599-127">Den AllowTollFreeDialIn-Parameter des Set-CsOnlineDialInConferencingUser-Cmdlets können zum Aktivieren oder Deaktivieren dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cd599-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="cd599-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cd599-128">For example:</span></span> 

 - <span data-ttu-id="cd599-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="cd599-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>

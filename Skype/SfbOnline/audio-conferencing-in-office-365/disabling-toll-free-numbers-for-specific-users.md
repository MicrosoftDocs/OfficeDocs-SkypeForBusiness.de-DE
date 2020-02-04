---
title: Deaktivieren von gebührenfreien Nummern für bestimmte Skype for Business Online-Benutzer
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Nummern für Ihre Besprechungen verwenden können.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695680"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="7d40c-103">Deaktivieren von gebührenfreien Nummern für bestimmte Skype for Business Online-Benutzer</span><span class="sxs-lookup"><span data-stu-id="7d40c-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="7d40c-104">Informationen zum Deaktivieren von Tool freien Nummern für Team Benutzer finden Sie unter [Deaktivieren von gebührenfreien Nummern für bestimmte Teams-Benutzer](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="7d40c-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="7d40c-105">Wenn in Ihrer Organisation gebührenfreie Nummern in der Microsoft-Audiokonferenz-Brücke zur Verfügung stehen, können Sie deren Verwendung in den Besprechungen bestimmter Organisatoren zulassen oder verhindern.</span><span class="sxs-lookup"><span data-stu-id="7d40c-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="7d40c-106">Standardmäßig sind alle Benutzer in Ihrer Organisation für die Verwendung von gebührenfreien Nummern aktiviert, was bedeutet, dass diese Nummern, falls verfügbar, von Teilnehmern zur Teilnahme an Besprechungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7d40c-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="7d40c-107">Wenn dies nicht das gewünschte Verhalten für einige Benutzer in Ihrer Organisation ist, können Sie bestimmte Benutzer davon abhalten, diese Nummern in ihren Besprechungen über eine gebührenfreie Nummer-Aktivierung-Steuerung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d40c-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="7d40c-108">Wenn gebührenfreie Nummern für einen bestimmten Organisator deaktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="7d40c-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="7d40c-109">Eine gebührenfreie Nummer wird nicht mehr in Ihre Besprechungseinladungen aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="7d40c-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="7d40c-110">Gebührenfreie Nummern werden nicht mehr auf der Seite "Ortsnummer suchen" aufgelistet, auf die in den Einladungen zu ihren Besprechungen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7d40c-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="7d40c-111">Teilnehmer können an der Besprechung des angegebenen Organisators nicht teilnehmen, wenn Sie eine gebührenfreie Nummer der Organisation wählen.</span><span class="sxs-lookup"><span data-stu-id="7d40c-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="7d40c-112">Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Nummer wird von Ihnen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7d40c-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="7d40c-113">Dadurch werden alle e-Mail-Einladungen des Organisators an alle Teilnehmer dieser Besprechungen erneut gesendet.</span><span class="sxs-lookup"><span data-stu-id="7d40c-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="7d40c-114">Teilnehmer können mit gebührenpflichtigen Nummern weiterhin an Besprechungen des Organisators teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="7d40c-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="7d40c-115">Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="7d40c-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="7d40c-116">Im **Microsoft Teams Admin Center**:</span><span class="sxs-lookup"><span data-stu-id="7d40c-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="7d40c-117">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="7d40c-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7d40c-118">Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7d40c-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="7d40c-119">Legen Sie **gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer** auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="7d40c-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="7d40c-120">Klicken Sie auf **speichern.**</span><span class="sxs-lookup"><span data-stu-id="7d40c-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="7d40c-121">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7d40c-121">**Using PowerShell**</span></span>  

<span data-ttu-id="7d40c-122">Sie können den AllowTollFreeDialIn-Parameter des Cmdlets "Satz-csonlinedialinconferencinguser zeigt" verwenden, um dieses Steuerelement zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d40c-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="7d40c-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7d40c-123">For example:</span></span> 

- <span data-ttu-id="7d40c-124">Satz-csonlinedialinconferencinguser zeigt user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="7d40c-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>

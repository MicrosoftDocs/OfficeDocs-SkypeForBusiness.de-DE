---
title: Deaktivieren von gebührenfreien Telefonnummern für bestimmte Microsoft Teams-Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können steuern, wie Organisatoren gebührenfreie Telefonnummern für ihre Besprechungen verwenden können.
ms.openlocfilehash: e2dddd04f376de69dbbc9579525966bac6351a0a
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "37572102"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="45e89-103">Deaktivieren von gebührenfreien Telefonnummern für bestimmte Microsoft Teams-Benutzer</span><span class="sxs-lookup"><span data-stu-id="45e89-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="45e89-104">Wenn die Microsoft-Audiokonferenzbrücke Ihrer Organisation gebührenfreie Telefonnummern enthält, können Sie die Verwendung dieser Nummern in den Besprechungen bestimmter Organisatoren zulassen oder verhindern.</span><span class="sxs-lookup"><span data-stu-id="45e89-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="45e89-105">Standardmäßig ist die Verwendung von gebührenfreien Telefonnummern für alle Benutzer in der Organisation aktiviert. Das heißt, wenn diese Nummern verfügbar sind, können sie von Teilnehmern für die Teilnahme an den Besprechungen der Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45e89-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="45e89-106">Wenn dieses Verhalten für einige Benutzer in der Organisation nicht gewünscht wird, können Sie über ein Steuerelement für die Aktivierung gebührenfreier Telefonnummern festlegen, dass bestimmte Benutzer diese Nummern nicht in ihren Besprechungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="45e89-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="45e89-107">Wenn gebührenfreie Telefonnummern für einen bestimmten Organisator deaktiviert sind, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="45e89-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="45e89-108">Die Besprechungseinladungen dieses Benutzers enthalten keine gebührenfreie Telefonnummer mehr.</span><span class="sxs-lookup"><span data-stu-id="45e89-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="45e89-109">Gebührenfreie Telefonnummern werden nicht mehr auf der Seite „Lokale Rufnummer suchen“ aufgelistet, auf die in den Besprechungseinladungen dieses Benutzers verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="45e89-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="45e89-110">Teilnehmer können nicht an der Besprechung des entsprechenden Organisators teilnehmen, wenn sie eine gebührenfreie Telefonnummer der Organisation wählen.</span><span class="sxs-lookup"><span data-stu-id="45e89-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="45e89-111">Alle Besprechungen des Organisators werden automatisch neu geplant, und die gebührenfreie Telefonnummer wird aus den Besprechungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="45e89-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="45e89-112">Dies bedeutet, dass alle E-Mail-Einladungen des Organisators erneut an die Teilnehmer dieser Besprechungen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="45e89-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="45e89-113">Die Teilnehmer können weiterhin über gebührenpflichtige Telefonnummern an den Besprechungen des Organisators teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="45e89-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="45e89-114">Deaktivieren von gebührenfreien Telefonnummern für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="45e89-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="45e89-115">Im **Microsoft Teams Admin Center**:</span><span class="sxs-lookup"><span data-stu-id="45e89-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="45e89-116">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="45e89-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="45e89-117">Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45e89-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="45e89-118">Legen Sie **gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer** auf **aus**.</span><span class="sxs-lookup"><span data-stu-id="45e89-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="45e89-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45e89-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="45e89-120">**Verwenden von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="45e89-120">**Using PowerShell**</span></span>  

<span data-ttu-id="45e89-121">Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="45e89-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

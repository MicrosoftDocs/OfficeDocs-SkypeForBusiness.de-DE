---
title: Zuweisen, Ändern von Orten für Notfall Standorte für Benutzer
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie den Ort für einen Notfall Standort für Benutzer in Ihrer Organisation zuweisen oder ändern können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232466"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="ae453-103">Zuweisen oder Ändern des Orts eines Notfall Standorts für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ae453-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="ae453-104">Jede aktive Telefonnummer muss über einen zugehörigen Notfall Standort verfügen, wenn Sie die Telefonnummer einem Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ae453-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="ae453-105">(Sie ordnen die Adresse zu, wenn Sie in Office 365 eine Telefonnummer erhalten oder wenn Sie eine Telefonnummer übertragen.) Wenn Sie die Nummer mit einem Notfall Standort verknüpfen, können Sie auch einen Ort hinzufügen, um eine genauere Position innerhalb eines physikalischen Standorts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ae453-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="ae453-106">Bei einem Ort kann es sich um den Boden, den Gebäudetrakt oder die Office-Nummer handeln, in der sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="ae453-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="ae453-107">Sie können eine unbegrenzte Anzahl von Orten für einen bestimmten Notfall Standort haben, und Sie können den Ort ändern, wenn der Benutzer zu einer anderen Niederlassung oder einem anderen Gebäude wechselt.</span><span class="sxs-lookup"><span data-stu-id="ae453-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="ae453-108">Wenn der Benutzer beispielsweise von Floor 34 auf Floor 35 umzieht.</span><span class="sxs-lookup"><span data-stu-id="ae453-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="ae453-109">Informationen dazu, wie Sie Anrufpläne erhalten und wie viel Sie Kosten, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ae453-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="ae453-110">Sie können den Ort für einen Notfall Standort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="ae453-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ae453-111">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="ae453-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ae453-112">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **VoIP**-Rufnummern  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="ae453-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="ae453-113">Wählen Sie auf der Seite **Telefonnummern** eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ae453-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="ae453-114">Führen Sie im **Bearbeitungs** Bereich unter **Notfall Speicherort**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ae453-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="ae453-115">Wenn Sie einen Ort zuweisen möchten, suchen Sie nach dem Ort oder Ort, und wählen Sie dann die Stelle in den Suchergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="ae453-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="ae453-116">Wenn Sie die Position ändern möchten, die dem Benutzer bereits zugewiesen ist, klicken Sie auf **X** , um die vorhandene Position zu entfernen, suchen Sie nach dem Ort, den Sie zuweisen möchten, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="ae453-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="ae453-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae453-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="ae453-118">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae453-118">Using PowerShell</span></span>

<span data-ttu-id="ae453-119">Weitere Informationen finden Sie unter [Satz-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="ae453-119">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="ae453-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ae453-120">Related topics</span></span>

- [<span data-ttu-id="ae453-121">Verwalten von Notrufen</span><span class="sxs-lookup"><span data-stu-id="ae453-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="ae453-122">Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ae453-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="ae453-123">Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ae453-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="ae453-124">Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ae453-124">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="ae453-125">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ae453-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="ae453-126">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="ae453-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

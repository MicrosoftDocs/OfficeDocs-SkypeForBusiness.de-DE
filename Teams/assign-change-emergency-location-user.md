---
title: Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie einen Notfall Standort für Benutzer in Ihrer Organisation zuweisen oder ändern können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232476"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="be18b-103">Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="be18b-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="be18b-104">Wenn Sie Anrufpläne einrichten, müssen Sie jeder Telefonnummer oder einem Nutzer einen Notfall Standort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="be18b-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="be18b-105">In europäischen Ländern ist der Notfall Standort mit der Telefonnummer verbunden, wenn Sie ihn von Office 365 abrufen oder wenn Sie eine Telefonnummer an Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="be18b-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="be18b-106">In den Vereinigten Staaten ist der Notfall Standort mit der Telefonnummer verbunden, wenn Sie dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="be18b-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="be18b-107">Die Notfalladresse kann geändert werden, wenn der Benutzer, dem Sie zugewiesen wurde, an einen neuen Speicherort wechselt.</span><span class="sxs-lookup"><span data-stu-id="be18b-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="be18b-108">Weitere Informationen zu Notfalladressen und-Standorten finden Sie unter [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="be18b-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="be18b-109">Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="be18b-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="be18b-110">Sie können einen Notfall Standort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="be18b-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="be18b-111">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="be18b-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="be18b-112">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **VoIP**-Rufnummern  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="be18b-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="be18b-113">Wählen Sie auf der Seite **Telefonnummern** eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="be18b-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="be18b-114">Führen Sie im **Bearbeitungs** Bereich unter **Notfall Speicherort**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="be18b-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="be18b-115">Wenn Sie einen Notfall Standort zuweisen möchten, suchen Sie nach einem Notfall Standort, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="be18b-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="be18b-116">Wenn Sie den Notfall Standort ändern möchten, der dem Benutzer bereits zugewiesen ist, klicken Sie auf **X** , um den vorhandenen Speicherort zu entfernen, und suchen Sie dann nach dem Speicherort, den Sie zuweisen möchten, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="be18b-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="be18b-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="be18b-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="be18b-118">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="be18b-118">Using PowerShell</span></span>

<span data-ttu-id="be18b-119">Weitere Informationen finden Sie unter [Satz-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="be18b-119">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="be18b-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="be18b-120">Related topics</span></span>

- [<span data-ttu-id="be18b-121">Verwalten von Notrufen</span><span class="sxs-lookup"><span data-stu-id="be18b-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="be18b-122">Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="be18b-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="be18b-123">Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="be18b-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="be18b-124">Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="be18b-124">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="be18b-125">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="be18b-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="be18b-126">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="be18b-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="be18b-127">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be18b-127">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

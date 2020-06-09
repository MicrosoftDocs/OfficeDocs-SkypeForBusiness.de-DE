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
ms.openlocfilehash: 450fe848052af1e331964da3d7b695daf0f1567a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610994"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="01583-103">Zuweisen oder Ändern eines Notfallstandorts für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="01583-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="01583-104">Wenn Sie Anrufpläne einrichten, müssen Sie jeder Telefonnummer oder einem Nutzer einen Notfall Standort zuweisen.</span><span class="sxs-lookup"><span data-stu-id="01583-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="01583-105">In europäischen Ländern ist der Notfall Standort mit der Telefonnummer verbunden, wenn Sie ihn von Microsoft 365 oder Office 365 erhalten oder wenn Sie eine Telefonnummer an Microsoft 365 oder Office 365 übertragen.</span><span class="sxs-lookup"><span data-stu-id="01583-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="01583-106">In den Vereinigten Staaten ist der Notfall Standort mit der Telefonnummer verbunden, wenn Sie dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="01583-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="01583-107">Die Notfalladresse kann geändert werden, wenn der Benutzer, dem Sie zugewiesen wurde, an einen neuen Speicherort wechselt.</span><span class="sxs-lookup"><span data-stu-id="01583-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="01583-108">Weitere Informationen zu Notfalladressen und-Standorten finden Sie unter [Was sind Notfall Standorte, Orte und Anrufweiterleitung?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="01583-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="01583-109">Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="01583-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="01583-110">Sie können einen Notfall Standort für einen Benutzer im Microsoft Teams Admin Center oder mithilfe von PowerShell zuweisen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="01583-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="01583-111">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="01583-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="01583-112">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **VoIP**-Rufnummern  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="01583-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="01583-113">Klicken Sie auf der Seite **Telefonnummern** auf die Registerkarte **Zahlen** , wählen Sie eine Benutzernummer in der Liste aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="01583-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="01583-114">Führen Sie im **Bearbeitungs** Bereich unter **Notfall Speicherort**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="01583-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="01583-115">Wenn Sie einen Notfall Standort zuweisen möchten, suchen Sie nach einem Notfall Standort, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="01583-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="01583-116">Wenn Sie den Notfall Standort ändern möchten, der dem Benutzer bereits zugewiesen ist, klicken Sie auf **X** , um den vorhandenen Speicherort zu entfernen, und suchen Sie dann nach dem Speicherort, den Sie zuweisen möchten, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="01583-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="01583-117">Je nachdem, ob Sie dem Benutzer eine e-Mail mit den Informationen zur Telefonnummer senden möchten, deaktivieren oder aktivieren Sie **e-Mail-Nutzer mit Telefonnummerninformationen**.</span><span class="sxs-lookup"><span data-stu-id="01583-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="01583-118">Standardmäßig ist dies aktiviert.</span><span class="sxs-lookup"><span data-stu-id="01583-118">By default, this is on.</span></span>

5. <span data-ttu-id="01583-119">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="01583-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="01583-120">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="01583-120">Using PowerShell</span></span>

<span data-ttu-id="01583-121">Weitere Informationen finden Sie unter [Satz-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span><span class="sxs-lookup"><span data-stu-id="01583-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="01583-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="01583-122">Related topics</span></span>

- [<span data-ttu-id="01583-123">Verwalten von Notrufen</span><span class="sxs-lookup"><span data-stu-id="01583-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="01583-124">Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="01583-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="01583-125">Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="01583-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="01583-126">Zuweisen oder Ändern eines Ortes als Notfallstandort für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="01583-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="01583-127">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="01583-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="01583-128">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="01583-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="01583-129">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01583-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

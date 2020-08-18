---
title: Hinzufügen, ändern und Entfernen von Notfall Standorten
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
description: 'Hier erfahren Sie, wie Sie im Microsoft Teams Admin Center einen Notfall Standort für Ihre Organisation hinzufügen, ändern oder entfernen. '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 762246630d245acf92c16aff8df2c9392a307b07
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788569"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="1d2be-103">Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1d2be-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="1d2be-104">Ein Notfall Standort muss einer Telefonnummer zugeordnet sein, aber wenn dies der Fall ist, kann dies zwischen Ländern und Regionen variieren.</span><span class="sxs-lookup"><span data-stu-id="1d2be-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="1d2be-105">In den Vereinigten Staaten müssen Sie beispielsweise einen Notfall Standort zuordnen, wenn Sie dem Benutzer die Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1d2be-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="1d2be-106">Im Vereinigten Königreich müssen Sie der Telefonnummer einen Notfall Standort zuordnen, wenn Sie die Telefonnummern von Microsoft 365 oder Office 365 erhalten oder Telefonnummern von Ihrem aktuellen Dienstanbieter übertragen.</span><span class="sxs-lookup"><span data-stu-id="1d2be-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="1d2be-107">Unabhängig davon, in welchem Land oder in welcher Region Sie sich befinden, können Sie einen Ort oder eine Stelle zu einem Notfall Standort hinzufügen und einen Notfall Standort entfernen.</span><span class="sxs-lookup"><span data-stu-id="1d2be-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="1d2be-108">Je nach Anzahl der physikalischen Standorte in Ihrer Organisation können Sie Orte für Gebäude, Etagen und Büros erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d2be-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="1d2be-109">Siehe [Notfall Anruf verwalten](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1d2be-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="1d2be-110">Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="1d2be-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="1d2be-111">Sie können Notfall Speicherorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="1d2be-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="1d2be-112">Hinzufügen eines Notfall Standorts</span><span class="sxs-lookup"><span data-stu-id="1d2be-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1d2be-113">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="1d2be-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1d2be-114">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.</span><span class="sxs-lookup"><span data-stu-id="1d2be-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="1d2be-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1d2be-115">Click **Add**.</span></span>
3. <span data-ttu-id="1d2be-116">Geben Sie einen Namen und eine Beschreibung für den Ort ein.</span><span class="sxs-lookup"><span data-stu-id="1d2be-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="1d2be-117">Wählen Sie das Land oder die Region aus, und geben Sie dann die Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="1d2be-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1d2be-118">In Belgien, Frankreich, Deutschland, Irland, den Niederlanden und Spanien ist es wichtig zu verstehen, dass für eine erfolgreiche Aktivierung einer Telefonnummer in Microsoft 365 oder Office 365 die Adresse des Notfall Standorts, die zum Abrufen der Nummer verwendet wird, mit der Ortsvorwahl der Telefonnummer übereinstimmen muss.</span><span class="sxs-lookup"><span data-stu-id="1d2be-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

5. <span data-ttu-id="1d2be-119">Wenn die Adresse nicht gefunden wird und Sie die Adresse manuell bearbeiten möchten, aktivieren Sie **die Option Adresse manuell bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1d2be-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="1d2be-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1d2be-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1d2be-121">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d2be-121">Using PowerShell</span></span>

<span data-ttu-id="1d2be-122">Weitere Informationen finden Sie unter [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="1d2be-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="1d2be-123">Ändern eines Notfallstandorts</span><span class="sxs-lookup"><span data-stu-id="1d2be-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1d2be-124">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="1d2be-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1d2be-125">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.</span><span class="sxs-lookup"><span data-stu-id="1d2be-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="1d2be-126">Wählen Sie in der Liste den Speicherort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1d2be-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="1d2be-127">Nehmen Sie die gewünschten Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="1d2be-127">Make the changes you want.</span></span>
4. <span data-ttu-id="1d2be-128">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1d2be-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d2be-129">Sie können die Adressinformationen für einen Speicherort nur ändern, wenn die Adresse nicht überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="1d2be-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="1d2be-130">Wenn die Adresse bereits überprüft wurde und Sie die Adresse ändern müssen, löschen Sie den Speicherort, und erstellen Sie dann einen neuen Speicherort mit der richtigen Adresse.</span><span class="sxs-lookup"><span data-stu-id="1d2be-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1d2be-131">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d2be-131">Using PowerShell</span></span>

<span data-ttu-id="1d2be-132">Weitere Informationen finden Sie unter [Satz-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="1d2be-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="1d2be-133">Entfernen eines Notfall Standorts</span><span class="sxs-lookup"><span data-stu-id="1d2be-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1d2be-134">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="1d2be-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="1d2be-135">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.</span><span class="sxs-lookup"><span data-stu-id="1d2be-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="1d2be-136">Wählen Sie in der Liste den Speicherort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="1d2be-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="1d2be-137">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d2be-137">Using PowerShell</span></span>

<span data-ttu-id="1d2be-138">Siehe [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span><span class="sxs-lookup"><span data-stu-id="1d2be-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d2be-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1d2be-139">Related topics</span></span>

- [<span data-ttu-id="1d2be-140">Verwalten von Notrufen</span><span class="sxs-lookup"><span data-stu-id="1d2be-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="1d2be-141">Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1d2be-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="1d2be-142">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="1d2be-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="1d2be-143">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="1d2be-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

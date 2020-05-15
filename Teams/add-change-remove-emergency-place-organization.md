---
title: Hinzufügen, ändern und Entfernen von Orten für Notfall Standorte
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
description: Hier erfahren Sie, wie Sie einen Ort für einen Notfall Standort für Ihre Organisation im Microsoft Teams Admin Center hinzufügen, ändern oder entfernen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232496"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="fc83f-103">Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="fc83f-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="fc83f-104">Je nach der Anzahl der physikalischen Standorte in Ihrer Organisation können Sie Orte für Gebäude, Etagen und Büros hinzufügen, um einen spezifischeren Notfall Standort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc83f-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="fc83f-105">Weitere Informationen finden Sie unter [Verwalten von Notruf anrufen](what-are-emergency-locations-addresses-and-call-routing.md) .</span><span class="sxs-lookup"><span data-stu-id="fc83f-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="fc83f-106">Informationen dazu, wie Sie einen Anrufplan erhalten und wie viel er kostet, finden Sie unter [Lizenzierung von Teams-Add-ons](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="fc83f-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="fc83f-107">Sie können Notfall Speicherorte für Ihre Organisation im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="fc83f-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="fc83f-108">Hinzufügen eines Orts zu einem Notfall Standort</span><span class="sxs-lookup"><span data-stu-id="fc83f-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc83f-109">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="fc83f-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fc83f-110">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.</span><span class="sxs-lookup"><span data-stu-id="fc83f-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="fc83f-111">Klicken Sie in der Liste auf den Namen des Standorts, für den Sie einen Ort hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc83f-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="fc83f-112">Klicken Sie auf der Registerkarte **Orte** auf **Ort hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fc83f-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="fc83f-113">Geben Sie einen Ortsnamen ein, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="fc83f-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc83f-114">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc83f-114">Using PowerShell</span></span>

<span data-ttu-id="fc83f-115">Weitere Informationen finden Sie unter [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="fc83f-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="fc83f-116">Ändern eines Orts für einen Notfall Standort</span><span class="sxs-lookup"><span data-stu-id="fc83f-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc83f-117">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="fc83f-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fc83f-118">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.</span><span class="sxs-lookup"><span data-stu-id="fc83f-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="fc83f-119">Klicken Sie in der Liste auf den Namen des Standorts, für den Sie einen Ort ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="fc83f-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="fc83f-120">Wählen Sie auf der Registerkarte **Orte** den Ort aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fc83f-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="fc83f-121">Aktualisieren Sie die Ortsinformationen, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="fc83f-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc83f-122">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc83f-122">Using PowerShell</span></span>

<span data-ttu-id="fc83f-123">Weitere Informationen finden Sie unter [Satz-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="fc83f-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="fc83f-124">Entfernen eines Orts aus einem Notfall Standort</span><span class="sxs-lookup"><span data-stu-id="fc83f-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc83f-125">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="fc83f-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="fc83f-126">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Locations**  >  **Notfalladressen**für Standorte.</span><span class="sxs-lookup"><span data-stu-id="fc83f-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="fc83f-127">Klicken Sie in der Liste auf den Namen des Standorts, für den Sie einen Ort entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc83f-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="fc83f-128">Wählen Sie auf der Registerkarte **Orte** den Ort aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="fc83f-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="fc83f-129">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc83f-129">Using PowerShell</span></span>

<span data-ttu-id="fc83f-130">Siehe [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="fc83f-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fc83f-131">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fc83f-131">Related topics</span></span>

- [<span data-ttu-id="fc83f-132">Hinzufügen, Ändern oder Entfernen eines Ortes als Notfallstandort für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="fc83f-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="fc83f-133">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="fc83f-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="fc83f-134">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="fc83f-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

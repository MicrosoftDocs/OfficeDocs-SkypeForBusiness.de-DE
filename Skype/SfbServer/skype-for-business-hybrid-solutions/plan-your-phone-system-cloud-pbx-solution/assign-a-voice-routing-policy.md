---
title: Zuweisen einer VoIP-Routing Richtlinie
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Zusammenfassung: in diesem Thema erfahren Sie, wie Sie eine VoIP-Richtlinie für Benutzer mit Telefon System mit lokaler PSTN-Konnektivität zuweisen.'
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221859"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="4ce69-103">Zuweisen einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="4ce69-104">**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie eine VoIP-Richtlinie für Benutzer mit Telefon System mit lokaler PSTN-Konnektivität zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ce69-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="4ce69-105">Sobald ein Benutzer Skype for Business Online und Telefon System mit lokaler PSTN-Konnektivität verwendet, gelten zwei VoIP-Richtlinien für diese.</span><span class="sxs-lookup"><span data-stu-id="4ce69-105">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="4ce69-106">Eine ist eine lokale VoIP-Routing Richtlinie, die Sie lokal zuweisen werden.</span><span class="sxs-lookup"><span data-stu-id="4ce69-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="4ce69-107">Diese Richtlinie kann global oder benutzerspezifisch sein und definiert, welche PSTN-Verwendungsdaten Sätze dem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4ce69-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="4ce69-108">In diesem Thema wird erläutert, wie diese Richtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4ce69-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="4ce69-109">Die andere VoIP-Richtlinie definiert, welche Anruffunktionen dem Benutzer zur Verfügung stehen. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für alle Telefonsysteme mit lokalen PSTN-Konnektivitäts-Benutzern identisch.</span><span class="sxs-lookup"><span data-stu-id="4ce69-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="4ce69-110">Sie wird automatisch den Telefon System Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4ce69-110">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="4ce69-111">**Lokaler Benutzer**</span><span class="sxs-lookup"><span data-stu-id="4ce69-111">**On-premises user**</span></span>|<span data-ttu-id="4ce69-112">**Telefon System mit lokaler PSTN-Konnektivität Benutzer**</span><span class="sxs-lookup"><span data-stu-id="4ce69-112">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ce69-113">In festgelegte Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="4ce69-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="4ce69-114">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-114">Voice policy</span></span>  <br/> |<span data-ttu-id="4ce69-115">Vordefinierte VoIP-Richtlinie, die automatisch zugewiesen wird, wenn der Benutzer für das Telefon System lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="4ce69-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="4ce69-116">Zugeordnete PSTN-Verwendungsdaten Sätze</span><span class="sxs-lookup"><span data-stu-id="4ce69-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="4ce69-117">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-117">Voice policy</span></span>  <br/> |<span data-ttu-id="4ce69-118">VoIP-Routing Richtlinie, die zugewiesen wird, während der Benutzer noch lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4ce69-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="4ce69-119">Sie führen die folgenden Schritte mithilfe Ihrer lokalen Bereitstellung aus, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4ce69-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="4ce69-120">Verwenden einer globalen VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-120">Using a global voice routing policy</span></span>

<span data-ttu-id="4ce69-121">Bevor Sie eine globale VoIP-Routing Richtlinie für Ihr Telefon System mit lokalen PSTN-Konnektivitäts-Benutzern verwenden, müssen Sie der Richtlinie PSTN-Verwendungsdaten Sätze hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ce69-121">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="4ce69-122">So weisen Sie der globalen VoIP-Routing Richtlinie PSTN-Verwendungsdaten Sätze zu</span><span class="sxs-lookup"><span data-stu-id="4ce69-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="4ce69-123">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ce69-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ce69-124">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4ce69-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ce69-125">Fügen Sie die PSTN-Verwendungsdaten Sätze zur Richtlinie hinzu:</span><span class="sxs-lookup"><span data-stu-id="4ce69-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="4ce69-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4ce69-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="4ce69-127">Erstellen einer neuen VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="4ce69-128">So erstellen Sie eine neue VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="4ce69-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ce69-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ce69-130">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4ce69-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ce69-131">Erstellen Sie eine neue VoIP-Routing Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="4ce69-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="4ce69-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4ce69-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="4ce69-133">In diesem Beispiel wird eine neue VoIP-Routing Richtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4ce69-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="4ce69-134">Zuweisen einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4ce69-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="4ce69-135">Unabhängig davon, ob Sie die globale VoIP-Routing Richtlinie oder benutzerspezifische verwenden, führen Sie die folgenden Schritte aus, um die Richtlinie einem Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ce69-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="4ce69-136">So weisen Sie die VoIP-Routing Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="4ce69-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="4ce69-137">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4ce69-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ce69-138">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4ce69-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4ce69-139">Zuweisen einer vorhandenen VoIP-Richtlinie zu einem Benutzer:</span><span class="sxs-lookup"><span data-stu-id="4ce69-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="4ce69-140">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4ce69-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="4ce69-141">In diesem Beispiel wird der Benutzer mit dem Anzeigenamen Bob Kelly der zuvor erstellten VoIP-Richtlinie mit dem Namen HybridVoice zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4ce69-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="4ce69-142">Weitere Informationen zu VoIP-Routing Richtlinien finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4ce69-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  


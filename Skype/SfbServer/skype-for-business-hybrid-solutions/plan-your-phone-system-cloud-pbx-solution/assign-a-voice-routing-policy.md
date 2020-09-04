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
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359321"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="f7c83-103">Zuweisen einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="f7c83-104">Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f7c83-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="f7c83-105">Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f7c83-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="f7c83-106">Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="f7c83-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="f7c83-107">**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie eine VoIP-Richtlinie für Benutzer mit Telefon System mit lokaler PSTN-Konnektivität zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7c83-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="f7c83-108">Sobald ein Benutzer Skype for Business Online und Telefon System mit lokaler PSTN-Konnektivität verwendet, gelten zwei VoIP-Richtlinien für diese.</span><span class="sxs-lookup"><span data-stu-id="f7c83-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="f7c83-109">Eine ist eine lokale VoIP-Routing Richtlinie, die Sie lokal zuweisen werden.</span><span class="sxs-lookup"><span data-stu-id="f7c83-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="f7c83-110">Diese Richtlinie kann global oder benutzerspezifisch sein und definiert, welche PSTN-Verwendungsdaten Sätze dem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f7c83-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="f7c83-111">In diesem Thema wird erläutert, wie diese Richtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f7c83-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="f7c83-112">Die andere VoIP-Richtlinie definiert, welche Anruffunktionen dem Benutzer zur Verfügung stehen. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für alle Telefonsysteme mit lokalen PSTN-Konnektivitäts-Benutzern identisch.</span><span class="sxs-lookup"><span data-stu-id="f7c83-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="f7c83-113">Sie wird automatisch den Telefon System Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7c83-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="f7c83-114">**Lokaler Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f7c83-114">**On-premises user**</span></span>|<span data-ttu-id="f7c83-115">**Telefon System mit lokaler PSTN-Konnektivität Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f7c83-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7c83-116">In festgelegte Anruffunktionen</span><span class="sxs-lookup"><span data-stu-id="f7c83-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="f7c83-117">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-117">Voice policy</span></span>  <br/> |<span data-ttu-id="f7c83-118">Vordefinierte VoIP-Richtlinie, die automatisch zugewiesen wird, wenn der Benutzer für das Telefon System lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="f7c83-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="f7c83-119">Zugeordnete PSTN-Verwendungsdaten Sätze</span><span class="sxs-lookup"><span data-stu-id="f7c83-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="f7c83-120">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-120">Voice policy</span></span>  <br/> |<span data-ttu-id="f7c83-121">VoIP-Routing Richtlinie, die zugewiesen wird, während der Benutzer noch lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="f7c83-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="f7c83-122">Sie führen die folgenden Schritte mithilfe Ihrer lokalen Bereitstellung aus, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="f7c83-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="f7c83-123">Verwenden einer globalen VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-123">Using a global voice routing policy</span></span>

<span data-ttu-id="f7c83-124">Bevor Sie eine globale VoIP-Routing Richtlinie für Ihr Telefon System mit lokalen PSTN-Konnektivitäts-Benutzern verwenden, müssen Sie der Richtlinie PSTN-Verwendungsdaten Sätze hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7c83-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="f7c83-125">So weisen Sie der globalen VoIP-Routing Richtlinie PSTN-Verwendungsdaten Sätze zu</span><span class="sxs-lookup"><span data-stu-id="f7c83-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="f7c83-126">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f7c83-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f7c83-127">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7c83-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f7c83-128">Fügen Sie die PSTN-Verwendungsdaten Sätze zur Richtlinie hinzu:</span><span class="sxs-lookup"><span data-stu-id="f7c83-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="f7c83-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f7c83-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="f7c83-130">Erstellen einer neuen VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="f7c83-131">So erstellen Sie eine neue VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="f7c83-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f7c83-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f7c83-133">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7c83-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f7c83-134">Erstellen Sie eine neue VoIP-Routing Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="f7c83-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="f7c83-135">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f7c83-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="f7c83-136">In diesem Beispiel wird eine neue VoIP-Routing Richtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f7c83-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="f7c83-137">Zuweisen einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7c83-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="f7c83-138">Unabhängig davon, ob Sie die globale VoIP-Routing Richtlinie oder benutzerspezifische verwenden, führen Sie die folgenden Schritte aus, um die Richtlinie einem Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7c83-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="f7c83-139">So weisen Sie die VoIP-Routing Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="f7c83-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="f7c83-140">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f7c83-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f7c83-141">Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7c83-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f7c83-142">Zuweisen einer vorhandenen VoIP-Richtlinie zu einem Benutzer:</span><span class="sxs-lookup"><span data-stu-id="f7c83-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="f7c83-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f7c83-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="f7c83-144">In diesem Beispiel wird der Benutzer mit dem Anzeigenamen Bob Kelly der zuvor erstellten VoIP-Richtlinie mit dem Namen HybridVoice zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7c83-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="f7c83-145">Weitere Informationen zu VoIP-Routing Richtlinien finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f7c83-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  


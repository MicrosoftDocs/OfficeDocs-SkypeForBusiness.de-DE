---
title: Zuweisen einer VoIP-Routingrichtlinie
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie eine VoIP-Richtlinie für Benutzer mit Telefonsystem im Office 365 mit lokalen PSTN-Anbindung zuweisen.'
ms.openlocfilehash: 12e74a6ea4a0adf652cc4e9477d20f91b4e13732
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657440"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="34384-103">Zuweisen einer VoIP-Routingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="34384-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie eine VoIP-Richtlinie für Benutzer mit Telefonsystem im Office 365 mit lokalen PSTN-Anbindung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="34384-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="34384-105">Sobald ein Benutzer auf Skype für Business Online und lokalen PSTN-Anbindung Telefonsystem in Office 365 mit ist, werden zwei VoIP-Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="34384-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="34384-106">Eine ist eine lokale VoIP-Routingrichtlinie, die Sie lokal zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="34384-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="34384-107">Diese Richtlinie kann global oder benutzerspezifische und definiert, welche PSTN-verwendungsdatensätzen dem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="34384-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="34384-108">In diesem Thema wird erläutert, wie die Richtlinie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="34384-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="34384-109">Die VoIP-Richtlinie definiert, welche Anruffunktionen für den Benutzer verfügbar sind. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für alle Telefonsystem in Office 365 mit lokalen PSTN Connectivity Benutzer identisch.</span><span class="sxs-lookup"><span data-stu-id="34384-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="34384-110">Es wird automatisch Telefonsystem in Office 365-Benutzer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="34384-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="34384-111">**Lokale Benutzer**</span><span class="sxs-lookup"><span data-stu-id="34384-111">**On-premises user**</span></span>|<span data-ttu-id="34384-112">**Telefonsystem in Office 365 mit lokalen PSTN Connectivity-Benutzer**</span><span class="sxs-lookup"><span data-stu-id="34384-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34384-113">Anruffunktionen definiert in</span><span class="sxs-lookup"><span data-stu-id="34384-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="34384-114">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-114">Voice policy</span></span>  <br/> |<span data-ttu-id="34384-115">Vordefiniert sind VoIP-Richtlinie, die automatisch zugeordnet werden, wenn der Benutzer für Telefonsystem in Office 365 lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="34384-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="34384-116">PSTN-Verwendungsdatensätze in Verbindung mit</span><span class="sxs-lookup"><span data-stu-id="34384-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="34384-117">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-117">Voice policy</span></span>  <br/> |<span data-ttu-id="34384-118">VoIP-Routingrichtlinie, wird zugeordnet, während der Benutzer noch lokal verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="34384-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="34384-119">Sie führen die folgenden Schritte aus, die mit der lokalen Bereitstellung während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="34384-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="34384-120">Verwenden einer globalen VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-120">Using a global voice routing policy</span></span>

<span data-ttu-id="34384-121">Bevor Sie eine globale VoIP-Routingrichtlinie für Ihr Telefonsystem in Office 365 mit lokalen PSTN Connectivity Benutzer verwenden, müssen Sie PSTN-Verwendungseinträge für die Richtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34384-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="34384-122">So werden der globalen VoIP-Routingrichtlinie PSTN-Verwendungsdatensätze zugeordnet</span><span class="sxs-lookup"><span data-stu-id="34384-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="34384-123">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="34384-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="34384-124">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="34384-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="34384-125">Fügen Sie die PSTN-verwendungsdatensätzen der Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="34384-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="34384-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="34384-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="34384-127">Erstellen einer neuen VoIP-Routingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="34384-128">So erstellen Sie eine neue VoIP-Routingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="34384-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="34384-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="34384-130">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="34384-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="34384-131">Erstellen Sie eine neuen VoIP-Routingrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="34384-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="34384-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="34384-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="34384-133">In diesem Beispiel wird eine neue VoIP-Routingrichtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="34384-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="34384-134">Zuweisen einer VoIP-Routingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="34384-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="34384-135">Unabhängig davon, ob Sie eine globale oder eine benutzerorientierte VoIP-Routingrichtlinie verwenden, durchlaufen Sie die folgenden Schritte, um einem Benutzer die Richtlinie zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="34384-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="34384-136">So ordnen Sie eine VoIP-Routingrichtlinie zu</span><span class="sxs-lookup"><span data-stu-id="34384-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="34384-137">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="34384-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="34384-138">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="34384-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="34384-139">Weisen Sie einem Benutzer eine vorhandene VoIP-Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="34384-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="34384-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="34384-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="34384-141">In diesem Beispiel wird der Benutzer mit dem Anzeigenamen „Bob Kelly“ einer zuvor erstellten VoIP-Richtlinie mit dem Namen „HybridVoice“ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="34384-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="34384-142">Weitere Informationen zur VoIP-Routingrichtlinien zurückgegeben, finden Sie unter [Erstellen oder ändern eine VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), ["New-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="34384-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  


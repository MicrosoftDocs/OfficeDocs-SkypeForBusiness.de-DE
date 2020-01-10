---
title: Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Zuweisen von E9-1-1-Standortrichtlinien zu Netzwerk Websites in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 36885fadddddd1fd0bf5ba91a6e0c30e79ef8b90
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001425"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="74147-103">Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74147-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="74147-104">Zuweisen von E9-1-1-Standortrichtlinien zu Netzwerk Websites in Skype for Business Server Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="74147-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="74147-105">In den folgenden Beispielen wird gezeigt, wie Sie die in Erstellen von [Standortrichtlinien in Skype for Business Server](create-location-policies.md) definierte **Redmond** -Standortrichtlinie zu einer vorhandenen Netzwerk Website hinzufügen und wie Sie eine neue Netzwerk Website erstellen, die die Standortrichtlinie für **Redmond** verwendet.</span><span class="sxs-lookup"><span data-stu-id="74147-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="74147-106">Details zum Arbeiten mit Netzwerk Websites finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="74147-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="74147-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="74147-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="74147-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="74147-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="74147-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="74147-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="74147-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="74147-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="74147-111">So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="74147-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="74147-112">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="74147-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="74147-113">Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="74147-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="74147-114">Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="74147-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="74147-115">So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="74147-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="74147-116">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="74147-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="74147-117">Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74147-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="74147-118">Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="74147-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```



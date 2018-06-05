---
title: Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Zuweisen von Richtlinien für E9-1-1-Speicherort zu Netzwerkstandorten in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: d167fb40e4a6318ce0621d365782cab3848cf284
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568263"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="44100-103">Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="44100-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="44100-104">Zuweisen von Richtlinien für E9-1-1-Speicherort zu Netzwerkstandorten in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="44100-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="44100-105">Die folgenden Beispiele zeigen, wie in [Erstellen von Standortrichtlinien in Skype für Business Server 2015](create-location-policies.md) zu einem vorhandenen Netzwerkstandort definiert **Redmond** Standortrichtlinie hinzufügen und wie Sie einen neuen Netzwerkstandort zu erstellen, der den Standort **Redmond** verwendet Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="44100-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="44100-106">Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der Dokumentation zu Lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="44100-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="44100-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="44100-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="44100-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="44100-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="44100-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="44100-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="44100-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="44100-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="44100-111">So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="44100-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="44100-112">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="44100-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="44100-113">Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="44100-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="44100-114">Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="44100-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="44100-115">So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu</span><span class="sxs-lookup"><span data-stu-id="44100-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="44100-116">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="44100-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="44100-117">Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="44100-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="44100-118">Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.</span><span class="sxs-lookup"><span data-stu-id="44100-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```



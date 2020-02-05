---
title: Erstellen von Netzwerk-standortübergreifenden Richtlinien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Erstellen von netzwerkinternen Richtlinien, die von Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: f24d0ad289d9388c45a5dbd9a31aa60e8c41e357
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767918"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="53070-103">Erstellen von Netzwerk-standortübergreifenden Richtlinien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="53070-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="53070-104">Erstellen von netzwerkinternen Richtlinien, die von Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53070-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="53070-105">Eine standortübergreifende Netzwerkrichtlinie definiert Bandbreiteneinschränkungen zwischen Standorten, die über direkte WAN-Verbindungen miteinander verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="53070-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53070-106">Eine Inter-Site-Netzwerkrichtlinie ist *nur* erforderlich, wenn zwischen zwei Netzwerkstandorten eine direkte Querverbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="53070-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="53070-p101">In der Region „Nordamerika“ der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten „Reno“ und „Albuquerque“. Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das Profil „20Mb_Link“ angewendet.</span><span class="sxs-lookup"><span data-stu-id="53070-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="53070-110">So erstellen Sie eine standortübergreifende Netzwerkrichtlinie</span><span class="sxs-lookup"><span data-stu-id="53070-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="53070-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="53070-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="53070-p102">Führen Sie das Cmdlet „New-CsNetworkInterSitePolicy“ aus, um für zwei Standorte mit standortübergreifender Direktverbindung standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="53070-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="53070-114">Wiederholen Sie bei Bedarf Schritt 2, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandorte mit standortübergreifender Direktverbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="53070-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="53070-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53070-115">See also</span></span>

[<span data-ttu-id="53070-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="53070-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="53070-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="53070-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="53070-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="53070-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="53070-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="53070-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

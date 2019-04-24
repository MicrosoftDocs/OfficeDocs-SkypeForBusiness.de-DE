---
title: Erstellen Sie Netzwerk Netzwerkrichtlinien in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Erstellen Sie Netzwerk standortübergreifende Richtlinien, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.
ms.openlocfilehash: 6619787bf071afe719c715de39e23b992d6e6ede
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223471"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="ca1d8-103">Erstellen Sie Netzwerk Netzwerkrichtlinien in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ca1d8-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ca1d8-104">Erstellen Sie Netzwerk standortübergreifende Richtlinien, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca1d8-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ca1d8-105">Eine standortübergreifende Netzwerkrichtlinie definiert Bandbreiteneinschränkungen zwischen Standorten, die über direkte WAN-Verbindungen miteinander verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="ca1d8-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca1d8-106">Eine standortübergreifende Netzwerkrichtlinie ist erforderlich *nur* , wenn eine standortübergreifende direktverbindung zwischen zwei Netzwerkstandorten besteht.</span><span class="sxs-lookup"><span data-stu-id="ca1d8-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="ca1d8-p101">In der Region „Nordamerika“ der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten „Reno“ und „Albuquerque“. Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das Profil „20Mb_Link“ angewendet.</span><span class="sxs-lookup"><span data-stu-id="ca1d8-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="ca1d8-110">So erstellen Sie eine standortübergreifende Netzwerkrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ca1d8-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="ca1d8-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ca1d8-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ca1d8-p102">Führen Sie das Cmdlet „New-CsNetworkInterSitePolicy“ aus, um für zwei Standorte mit standortübergreifender Direktverbindung standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ca1d8-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="ca1d8-114">Wiederholen Sie bei Bedarf Schritt 2, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandorte mit standortübergreifender Direktverbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ca1d8-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca1d8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca1d8-115">See also</span></span>

[<span data-ttu-id="ca1d8-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca1d8-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ca1d8-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca1d8-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ca1d8-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca1d8-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ca1d8-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ca1d8-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

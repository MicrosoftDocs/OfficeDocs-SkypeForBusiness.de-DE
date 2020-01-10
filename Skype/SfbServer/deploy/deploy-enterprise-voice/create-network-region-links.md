---
title: Erstellen von Links zu netzwerkregionen in Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Erstellen oder Ändern von Netzwerk Regions Verknüpfungen, die von Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 3c40488c3cbb4d5116f9b242bb198ba20f13bd58
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001735"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="b91dd-103">Erstellen von Links zu netzwerkregionen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b91dd-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="b91dd-104">Erstellen oder Ändern von Netzwerk Regions Verknüpfungen, die von Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b91dd-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="b91dd-105">Regionen in einem Netzwerk sind über physische WAN-Verbindungen miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="b91dd-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="b91dd-106">Eine Netzwerkregionenverbindung erstellt eine Verbindung zwischen zwei Regionen, die für die Anrufsteuerung (Call Admission Control, CAC) konfiguriert sind, und legt die Bandbreiteneinschränkungen für den Audio- und Videodatenverkehr zwischen diesen Regionen fest.</span><span class="sxs-lookup"><span data-stu-id="b91dd-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="b91dd-107">Die Beispieltopologie weist eine Verbindung zwischen den Regionen „North America“ und „APAC“ sowie zwischen den Regionen „EMEA“ und „APAC“ auf.</span><span class="sxs-lookup"><span data-stu-id="b91dd-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="b91dd-108">Jede dieser Regions Verknüpfungen wird durch die WAN-Bandbreite beschränkt, wie in der Tabelle Regions Link-bandbreiteninformationen beschrieben, [beispielsweise: Erfassen der Anforderungen für die Anrufsteuerung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b91dd-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b91dd-109">So erstellen Sie Netzwerk Regions Verknüpfungen mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="b91dd-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b91dd-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b91dd-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b91dd-111">Führen Sie das Cmdlet „New-CsNetworkRegionLink“ aus, um die Regionenverbindungen zu erstellen und geeignete Bandbreitenrichtlinienprofile anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b91dd-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="b91dd-112">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b91dd-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b91dd-113">So erstellen Sie Netzwerk Regions Verknüpfungen mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="b91dd-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b91dd-114">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="b91dd-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b91dd-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b91dd-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b91dd-116">Klicken Sie auf die Navigationsschaltfläche **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="b91dd-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="b91dd-117">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="b91dd-117">Click **New**.</span></span>
    
5. <span data-ttu-id="b91dd-118">Klicken Sie auf der Seite **Neue Netzwerkregionenverbindung** auf **Name** und geben Sie einen Namen für die Netzwerkregionenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="b91dd-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="b91dd-119">Klicken Sie auf **Netzwerkregion 1** und anschließend auf die Netzwerkregion in der Liste, für die eine Verbindung mit Netzwerkregion 2 erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b91dd-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="b91dd-120">Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Verbindung mit Netzwerkregion 1 erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b91dd-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="b91dd-121">Klicken Sie optional auf **Bandbreitenrichtlinie** und wählen Sie das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionenverbindung anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b91dd-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b91dd-122">Wenden Sie nur dann eine Bandbreitenrichtlinie an, wenn die Netzwerkregionenverbindung eine Bandbreiteneinschränkung aufweist und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr in dieser Verbindung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b91dd-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="b91dd-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b91dd-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="b91dd-124">Zum Abschließen der Erstellung von Netzwerkregionenverbindungen für Ihre Topologie wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="b91dd-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b91dd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b91dd-125">See also</span></span>

[<span data-ttu-id="b91dd-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b91dd-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b91dd-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b91dd-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b91dd-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b91dd-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b91dd-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b91dd-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

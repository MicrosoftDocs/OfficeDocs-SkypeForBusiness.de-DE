---
title: Erstellen von Netzwerkregionenverbindungen in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Erstellen oder Ändern von netzwerkregionenverbindungen, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.
ms.openlocfilehash: e0fbabb811ec604b3a0155074a01bc4b02bd6152
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a><span data-ttu-id="0644a-103">Erstellen von Netzwerkregionenverbindungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0644a-103">Create network region links in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0644a-104">Erstellen oder Ändern von netzwerkregionenverbindungen, die von Enterprise-VoIP-anrufsteuerung in Skype für Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0644a-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="0644a-105">Regionen in einem Netzwerk sind über physische WAN-Verbindungen miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="0644a-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="0644a-106">Eine netzwerkregionenverbindung erstellt eine Verbindung zwischen zwei Regionen für Call Admission Control (CAC) konfiguriert und die Netzwerkbandbreite ist eingeschränkt auf audio und video-Datenverkehr zwischen diesen Regionen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0644a-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="0644a-107">Die Beispieltopologie weist eine Verbindung zwischen den Regionen „North America“ und „APAC“ sowie zwischen den Regionen „EMEA“ und „APAC“ auf.</span><span class="sxs-lookup"><span data-stu-id="0644a-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="0644a-108">Diese Region links wird von WAN-Bandbreite eingeschränkt, wie beschrieben in Tabelle Bandbreiteninformationen [Beispiel: Sammeln von Anforderungen für die anrufsteuerung in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0644a-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0644a-109">Erstellen Sie netzwerkregionenverbindungen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0644a-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="0644a-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0644a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0644a-p103">Führen Sie das Cmdlet „New-CsNetworkRegionLink“ aus, um die Regionenverbindungen zu erstellen und geeignete Bandbreitenrichtlinienprofile anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0644a-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0644a-113">Erstellen Sie netzwerkregionenverbindungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0644a-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0644a-114">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0644a-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0644a-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="0644a-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="0644a-116">Klicken Sie auf die Navigationsschaltfläche **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="0644a-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="0644a-117">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="0644a-117">Click **New**.</span></span>
    
5. <span data-ttu-id="0644a-118">Klicken Sie auf der Seite **Neue Netzwerkregionenverbindung** auf **Name** und geben Sie einen Namen für die Netzwerkregionenverbindung ein.</span><span class="sxs-lookup"><span data-stu-id="0644a-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="0644a-119">Klicken Sie auf **Netzwerkregion 1** und anschließend auf die Netzwerkregion in der Liste, für die eine Verbindung mit Netzwerkregion 2 erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0644a-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="0644a-120">Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Verbindung mit Netzwerkregion 1 erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0644a-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="0644a-121">Klicken Sie optional auf **Bandbreitenrichtlinie** und wählen Sie das Bandbreitenrichtlinienprofil aus, das Sie auf die Netzwerkregionenverbindung anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0644a-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0644a-122">Wenden Sie nur dann eine Bandbreitenrichtlinie an, wenn die Netzwerkregionenverbindung eine Bandbreiteneinschränkung aufweist und Sie die Anrufsteuerung verwenden möchten, um den Mediendatenverkehr in dieser Verbindung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0644a-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="0644a-123">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0644a-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="0644a-124">Zum Abschließen der Erstellung von Netzwerkregionenverbindungen für Ihre Topologie wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="0644a-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0644a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0644a-125">See also</span></span>

#### 

[<span data-ttu-id="0644a-126">Neue CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0644a-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="0644a-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0644a-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="0644a-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0644a-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="0644a-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="0644a-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)


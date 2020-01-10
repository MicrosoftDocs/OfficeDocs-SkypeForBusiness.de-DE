---
title: Erstellen interregionaler Netzwerkrouten in Skype for Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Erstellen oder ändern Sie Netzwerk interregionale Routen, die von der Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.
ms.openlocfilehash: 6d9517796b2f418c39873850ee596a5effdba4e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001755"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="03056-103">Erstellen interregionaler Netzwerkrouten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="03056-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="03056-104">Erstellen oder ändern Sie Netzwerk interregionale Routen, die von der Enterprise-VoIP-Zulassungs Steuerung in Skype for Business Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03056-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="03056-105">Eine regionenübergreifende Netzwerkroute definiert die Route zwischen zwei Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="03056-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="03056-106">Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine regionenübergreifende Netzwerkroute erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03056-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="03056-107">So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="03056-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="03056-108">Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen, bestimmt eine regionenübergreifende Route, welchen Verknüpfungspfad die Verbindung von einer Region zur anderen nimmt.</span><span class="sxs-lookup"><span data-stu-id="03056-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="03056-109">In der Beispieltopologie müssen für jedes der drei Regionenpaare regionenübergreifende Netzwerkrouten definiert werden: „North America/EMEA“, „EMEA/APAC“ und „North America/APAC“.</span><span class="sxs-lookup"><span data-stu-id="03056-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="03056-110">So erstellen Sie Netzwerk interregionale Routen mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="03056-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="03056-111">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="03056-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03056-112">Führen Sie das Cmdlet **New-CsNetworkInterRegionRoute** aus, um die erforderlichen Routen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="03056-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="03056-113">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="03056-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="03056-114">Für die regionenübergreifende Netzwerkroute „North America/APAC“ werden zwei Netzwerkregionenverbindungen benötigt, da zwischen diesen beiden Regionen keine direkte Netzwerkregionenverbindung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="03056-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="03056-115">So erstellen Sie Netzwerk interregionale Routen mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="03056-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="03056-116">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="03056-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="03056-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="03056-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="03056-118">Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="03056-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="03056-119">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="03056-119">Click **New**.</span></span>
    
5. <span data-ttu-id="03056-120">Klicken Sie auf der Seite **Neue Regionenroute** auf **Name** und geben Sie einen Namen für die regionenübergreifende Netzwerkroute ein.</span><span class="sxs-lookup"><span data-stu-id="03056-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="03056-121">Klicken Sie auf **Netzwerkregion 1** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 2 erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="03056-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="03056-122">Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Verbindung zu Netzwerkregion 1 erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="03056-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="03056-123">Klicken Sie neben dem Feld **Netzwerkregionenverbindungen** auf **Hinzufügen** und fügen Sie eine Netzwerkregionenverbindung hinzu, die in der regionenübergreifenden Netzwerkroute verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="03056-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03056-p103">Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Für die regionenübergreifende Netzwerkroute „North America/APAC“ werden beispielsweise zwei Netzwerkregionenverbindungen benötigt, da zwischen diesen beiden Regionen keine direkte Netzwerkregionenverbindung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="03056-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="03056-126">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="03056-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="03056-127">Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere regionenübergreifende Netzwerkrouten, um die Erstellung von regionenübergreifenden Netzwerkrouten für Ihre Topologie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="03056-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="03056-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03056-128">See also</span></span>

[<span data-ttu-id="03056-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="03056-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="03056-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="03056-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="03056-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="03056-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="03056-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="03056-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

---
title: 'Lync Server 2013: Erstellen oder Ändern eines Netzwerkbereichs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="f0c64-102">Erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c64-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c64-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f0c64-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f0c64-104">*Netzwerkregionen* sind die Netzwerkhubs oder Backbones, die in der Konfiguration der Anruf Zulassungs Steuerung, E9-1-1 und medienumgehung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0c64-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="f0c64-105">Gehen Sie wie folgt vor, um netzwerkregionen zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f0c64-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="f0c64-106">Wenn Sie beispielsweise bereits netzwerkregionen für ein Sprachfeature erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0c64-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="f0c64-107">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="f0c64-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f0c64-108">Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="f0c64-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="f0c64-109">Ausführliche Informationen finden Sie unter [Konfigurieren von netzwerkregionen für CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="f0c64-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0c64-110">Alle funktionsspezifischen Anforderungen für Netzwerkbereichs Definitionen sind in den Bereitstellungsthemen für das Feature dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="f0c64-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="f0c64-111">Details zum Arbeiten mit netzwerkregionen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f0c64-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f0c64-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f0c64-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="f0c64-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f0c64-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="f0c64-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f0c64-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="f0c64-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f0c64-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="f0c64-116">Erstellen eines Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="f0c64-116">Create a Network Region</span></span>

<span data-ttu-id="f0c64-117">Erstellen Sie einen Netzwerkbereich, der von der Anrufsteuerung, E9-1-1 oder Media Bypass verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0c64-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="f0c64-118">So erstellen Sie einen Netzwerkbereich mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f0c64-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f0c64-119">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f0c64-120">Führen Sie das Cmdlet New-CsNetworkRegion aus, um Netzwerkregionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f0c64-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="f0c64-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0c64-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="f0c64-122">In diesem Beispiel wird eine Netzwerkregion NorthAmerica erstellt, die einem zentralen Standort mit der Standort-ID CHICAGO zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="f0c64-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="f0c64-123">Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="f0c64-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="f0c64-124">So erstellen Sie einen Netzwerkbereich mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f0c64-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f0c64-125">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f0c64-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f0c64-126">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f0c64-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f0c64-127">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f0c64-128">Klicken Sie auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-128">Click **Region**.</span></span>

4.  <span data-ttu-id="f0c64-129">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-129">Click **New**.</span></span>

5.  <span data-ttu-id="f0c64-130">Klicken Sie auf der Seite **Neue Region** auf **Name** und geben Sie einen Namen für die Netzwerkregion ein.</span><span class="sxs-lookup"><span data-stu-id="f0c64-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="f0c64-131">Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.</span><span class="sxs-lookup"><span data-stu-id="f0c64-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="f0c64-132">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="f0c64-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="f0c64-133">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="f0c64-134">Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="f0c64-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="f0c64-135">Ändern eines Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="f0c64-135">Modify a Network Region</span></span>

<span data-ttu-id="f0c64-136">Ändern Sie die Einstellungen für einen vorhandenen Netzwerkbereich, um Änderungen an den grundlegenden Bereichs Informationen oder Änderungen anzupassen, die für ein neues Feature erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f0c64-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="f0c64-137">So ändern Sie einen Netzwerkbereich mithilfe der lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="f0c64-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f0c64-138">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f0c64-139">Führen Sie das Cmdlet Set-CsNetworkRegion aus, um eine vorhandene Netzwerkregion zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f0c64-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="f0c64-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0c64-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="f0c64-p103">In diesem Beispiel wird die zuvor in diesem Thema erstellte Netzwerkregion „NorthAmerica“ bearbeitet, indem die Beschreibung geändert wird. Wenn für die Region „NorthAmerica“ bereits eine Beschreibung vorhanden ist, wird diese durch den neuen Wert ersetzt, andernfalls legt dieser Befehl die Beschreibung fest.</span><span class="sxs-lookup"><span data-stu-id="f0c64-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="f0c64-143">Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.</span><span class="sxs-lookup"><span data-stu-id="f0c64-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="f0c64-144">So ändern Sie einen Netzwerkbereich mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f0c64-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f0c64-145">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f0c64-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f0c64-146">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f0c64-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f0c64-147">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f0c64-148">Klicken Sie auf die Navigationsschaltfläche **Region**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="f0c64-149">Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f0c64-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="f0c64-150">Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="f0c64-151">Ändern Sie auf der Seite **Region bearbeiten** die Werte für die Einstellungen dieser Netzwerkregion wie gewünscht ab.</span><span class="sxs-lookup"><span data-stu-id="f0c64-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="f0c64-152">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f0c64-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="f0c64-153">Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="f0c64-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


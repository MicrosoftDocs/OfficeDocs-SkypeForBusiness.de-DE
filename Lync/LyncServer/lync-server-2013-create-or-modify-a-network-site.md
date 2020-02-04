---
title: 'Lync Server 2013: Erstellen oder Ändern eines Netzwerkstandorts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="d9226-102">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9226-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9226-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d9226-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d9226-104">Die Bereitstellung von Anrufannahme Steuerung (CAC), E9-1-1 und medienumgehung basiert auf der Konfiguration von *Netzwerk Websites* , die in einer netzwerkregion definiert sind und immer mit dieser verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="d9226-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="d9226-105">Eine Netzwerk Website steht für einen Zweigstellenstandort, einen Satz von Gebäuden oder einen Campus.</span><span class="sxs-lookup"><span data-stu-id="d9226-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="d9226-106">Netzwerk Websites stellen Auflistungen von Subnetzen mit ähnlicher Bandbreite dar.</span><span class="sxs-lookup"><span data-stu-id="d9226-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="d9226-107">Gehen Sie wie folgt vor, um Netzwerk Websites zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d9226-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="d9226-108">Wenn Sie beispielsweise bereits Netzwerk Websites für eine Sprachfunktion erstellt haben, müssen Sie keine neuen Netzwerk Websites erstellen. für andere Sprachfeatures werden dieselben Websites verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9226-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="d9226-109">Sie müssen jedoch möglicherweise eine vorhandene Definition eines Netzwerkstandorts ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d9226-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="d9226-110">Wenn Sie z. B. einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d9226-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9226-111">Wo Sie vorhanden sind, finden Sie spezifische Beispiele und Anforderungen für Netzwerk Websites in Bezug auf eine erweiterte Sprachfunktion in der Bereitstellungsdokumentation für die einzelnen Features:</span><span class="sxs-lookup"><span data-stu-id="d9226-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d9226-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Konfigurieren von Netzwerk Websites für CAC in lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="d9226-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="d9226-113">Details zum Arbeiten mit Netzwerk Websites finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d9226-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="d9226-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d9226-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="d9226-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d9226-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="d9226-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d9226-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="d9226-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d9226-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="d9226-118">Erstellen einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="d9226-118">Create a Network Site</span></span>

<span data-ttu-id="d9226-119">Erstellen Sie einen Netzwerkbereich, der von der Anrufsteuerung, E9-1-1 oder Media Bypass verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9226-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="d9226-120">So erstellen Sie eine Netzwerk Website mithilfe der Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d9226-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="d9226-121">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d9226-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d9226-122">Führen Sie das Cmdlet New-CsNetworkSite aus, um Netzwerkstandorte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d9226-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="d9226-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d9226-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="d9226-124">In diesem Beispiel wird ein Netzwerkstandort namens „Chicago“ erstellt, der sich in der Netzwerkregion „NorthAmerica“ befindet.</span><span class="sxs-lookup"><span data-stu-id="d9226-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9226-125">Die Netzwerkregion „NorthAmerica“ muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9226-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="d9226-126">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d9226-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="d9226-127">So erstellen Sie eine Netzwerk Website mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d9226-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d9226-128">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d9226-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9226-129">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d9226-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="d9226-130">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d9226-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="d9226-131">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="d9226-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="d9226-132">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d9226-132">Click **New**.</span></span>

5.  <span data-ttu-id="d9226-133">Klicken Sie auf der Seite **Neuer Standort** auf **Name** und geben Sie einen Namen für den Netzwerkstandort ein.</span><span class="sxs-lookup"><span data-stu-id="d9226-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="d9226-134">Klicken Sie auf **Region** und klicken Sie dann auf eine Region in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d9226-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="d9226-135">Klicken Sie optional auf **Bandbreitenrichtlinie** und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d9226-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9226-136">Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d9226-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="d9226-137">Klicken Sie optional auf **Ortungsrichtlinie** und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d9226-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9226-138">Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d9226-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="d9226-139">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="d9226-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="d9226-140">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d9226-140">Click **Commit**.</span></span>

11. <span data-ttu-id="d9226-141">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d9226-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="d9226-142">Ändern einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="d9226-142">Modify a Network Site</span></span>

<span data-ttu-id="d9226-143">Sie können einen Netzwerkbereich ändern, der von der Anrufannahme Steuerung, E9-1-1 oder Media Bypass verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9226-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="d9226-144">So ändern Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="d9226-144">To modify a network site</span></span>

1.  <span data-ttu-id="d9226-145">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d9226-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d9226-146">Führen Sie das Cmdlet Set-CsNetworkSite aus, um Netzwerkstandorte zu ändern:</span><span class="sxs-lookup"><span data-stu-id="d9226-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="d9226-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d9226-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="d9226-p104">In diesem Beispiel wird der Standort „Albuquerque“ in die Netzwerkregion „NorthAmerica“ verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet Set-CsNetworkSite mit dem Parameter BWPolicyProfileID oder LocationPolicy ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9226-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9226-p105">Wenngleich der Parameter BypassID für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d9226-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="d9226-152">Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d9226-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="d9226-153">So ändern Sie eine Netzwerk Website mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d9226-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d9226-154">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d9226-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9226-155">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d9226-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="d9226-156">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d9226-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="d9226-157">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="d9226-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="d9226-158">Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="d9226-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="d9226-159">Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="d9226-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="d9226-160">Ändern Sie auf der Seite **Standort bearbeiten** die Werte für die Einstellungen dieses Netzwerkstandorts wie gewünscht ab.</span><span class="sxs-lookup"><span data-stu-id="d9226-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="d9226-161">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d9226-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="d9226-162">Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d9226-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


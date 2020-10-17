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
ms.openlocfilehash: 60119e137851bbaa8dc7b6735202132085bb8d34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506122"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="18899-102">Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18899-102">Create or modify a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18899-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="18899-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="18899-104">Bereitstellungen mit Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung stützen sich auf die Konfiguration von *Netzwerkstandorten*, die innerhalb einer Netzwerkregion definiert und stets einer Netzwerkregion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="18899-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="18899-105">Ein Netzwerkstandort stellt einen Zweigstellenstandort, einen Gebäudekomplex oder einen Campus dar.</span><span class="sxs-lookup"><span data-stu-id="18899-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="18899-106">Netzwerkstandorte repräsentieren Sammlungen aus Subnetzen mit ähnlicher Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="18899-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="18899-p102">Verwenden Sie die folgenden Verfahren, um Netzwerkstandorte zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkstandorte für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkstandorte erstellen, da dieselben Netzwerkstandorte für weitere VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Netzwerkstandortdefinition ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie beispielsweise einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="18899-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18899-111">Spezifische Beispiele und Anforderungen für Netzwerkstandorte finden Sie ggf. in den Themen zu erweiterten VoIP-Funktionen in der Bereitstellungsdokumentation:</span><span class="sxs-lookup"><span data-stu-id="18899-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="18899-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="18899-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="18899-113">Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="18899-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="18899-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="18899-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="18899-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="18899-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="18899-116">Gruppe-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="18899-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="18899-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="18899-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="18899-118">Erstellen eines Netzwerkstandorts</span><span class="sxs-lookup"><span data-stu-id="18899-118">Create a Network Site</span></span>

<span data-ttu-id="18899-119">Erstellen Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="18899-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="18899-120">So erstellen Sie einen Netzwerkstandort mithilfe der Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="18899-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="18899-121">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="18899-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="18899-122">Führen Sie das Cmdlet "New-CsNetworkSite" aus, um Netzwerkstandorte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="18899-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="18899-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18899-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="18899-124">In diesem Beispiel wird ein Netzwerkstandort namens "Chicago" erstellt, der sich in der Netzwerkregion "NorthAmerica" befindet.</span><span class="sxs-lookup"><span data-stu-id="18899-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18899-125">Die Netzwerkregion "NorthAmerica" muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="18899-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="18899-126">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="18899-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="18899-127">So erstellen Sie einen Netzwerkstandort mithilfe der Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="18899-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="18899-128">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="18899-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18899-129">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="18899-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="18899-130">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="18899-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="18899-131">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="18899-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="18899-132">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="18899-132">Click **New**.</span></span>

5.  <span data-ttu-id="18899-133">Klicken Sie auf der Seite **Neuer Standort** auf **Name**, und geben Sie einen Namen für den Netzwerkstandort ein.</span><span class="sxs-lookup"><span data-stu-id="18899-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="18899-134">Klicken Sie auf **Region**, und klicken Sie dann auf eine Region in der Liste.</span><span class="sxs-lookup"><span data-stu-id="18899-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="18899-135">Klicken Sie optional auf **Bandbreitenrichtlinie**, und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="18899-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18899-136">Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="18899-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="18899-137">Klicken Sie optional auf **Ortungsrichtlinie**, und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="18899-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18899-138">Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="18899-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="18899-139">Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="18899-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="18899-140">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="18899-140">Click **Commit**.</span></span>

11. <span data-ttu-id="18899-141">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="18899-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="18899-142">Ändern eines Netzwerkstandorts</span><span class="sxs-lookup"><span data-stu-id="18899-142">Modify a Network Site</span></span>

<span data-ttu-id="18899-143">Ändern Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="18899-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="18899-144">So ändern Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="18899-144">To modify a network site</span></span>

1.  <span data-ttu-id="18899-145">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="18899-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="18899-146">Führen Sie das Cmdlet "Set-CsNetworkSite" aus, um Netzwerkstandorte zu ändern:</span><span class="sxs-lookup"><span data-stu-id="18899-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="18899-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="18899-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="18899-p104">In diesem Beispiel wird der Standort "Albuquerque" in die Netzwerkregion "NorthAmerica" verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet "Set-CsNetworkSite" mit dem Parameter "BWPolicyProfileID" oder "LocationPolicy" ausführen.</span><span class="sxs-lookup"><span data-stu-id="18899-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18899-p105">Wenngleich der Parameter "BypassID" für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="18899-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="18899-152">Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="18899-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="18899-153">So ändern Sie einen Netzwerkstandort mithilfe der Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="18899-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="18899-154">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="18899-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18899-155">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="18899-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="18899-156">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="18899-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="18899-157">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="18899-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="18899-158">Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="18899-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="18899-159">Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="18899-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="18899-160">Ändern Sie auf der Seite **Standort bearbeiten** die Werte für die Einstellungen dieses Netzwerkstandorts wie gewünscht ab.</span><span class="sxs-lookup"><span data-stu-id="18899-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="18899-161">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="18899-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="18899-162">Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="18899-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


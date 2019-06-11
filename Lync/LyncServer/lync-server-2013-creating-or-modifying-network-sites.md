---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk Websites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="3e52e-102">Erstellen oder Ändern von Netzwerk Websites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e52e-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e52e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="3e52e-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="3e52e-104">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="3e52e-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3e52e-105">Sie können die Microsoft lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="3e52e-106">Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="3e52e-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="3e52e-107">Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="3e52e-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="3e52e-108">In der lync Server-Systemsteuerung können Sie Netzwerk Websites erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="3e52e-109">Gehen Sie wie folgt vor, um eine Netzwerk Website zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3e52e-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="3e52e-110">Details zum Löschen einer vorhandenen Netzwerk Website finden Sie unter [Löschen einer vorhandenen Netzwerk Website in lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="3e52e-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="3e52e-111">So erstellen Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="3e52e-111">To create a network site</span></span>

1.  <span data-ttu-id="3e52e-112">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3e52e-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e52e-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e52e-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e52e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e52e-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3e52e-116">Klicken Sie auf der Seite **Website** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="3e52e-117">Geben Sie auf der **neuen Website**im Feld **Name** einen Namen für diese Website ein.</span><span class="sxs-lookup"><span data-stu-id="3e52e-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e52e-118">Websitenamen müssen innerhalb der lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3e52e-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="3e52e-119">Wählen Sie in der Dropdownliste **Region** einen Netzwerkbereich aus, der dieser Website zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3e52e-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="3e52e-120">Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe an diese Website vornehmen möchten, wählen Sie das bandbreitenrichtlinienprofil mit den entsprechenden Einstellungen in der Dropdownliste **bandbreitenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="3e52e-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e52e-121">Auf der Seite " <STRONG>Richtlinienprofil</STRONG> " der Gruppe " <STRONG>Netzwerkkonfiguration</STRONG> " können Sie die Details der verfügbaren bandbreitenrichtlinienprofile anzeigen oder ein neues bandbreitenrichtlinienprofil erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="3e52e-122">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e52e-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="3e52e-123">Optional Wenn Sie die Standorteinstellungen für diese Website angeben möchten, wählen Sie in der Dropdownliste **Standortrichtlinie** eine Standortrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="3e52e-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e52e-124">Die Standortrichtlinie weist der Website bestimmte erweiterte 9-1-1-Einstellungen (E9-1-1) und Clientstandort Einstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="3e52e-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="3e52e-125">Sie können die Details der verfügbaren Standortrichtlinien anzeigen oder eine neue Standortrichtlinie erstellen, die sich auf der Seite " <STRONG>Standortrichtlinie</STRONG> " der Gruppe " <STRONG>Netzwerkkonfiguration</STRONG> " befindet.</span><span class="sxs-lookup"><span data-stu-id="3e52e-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="3e52e-126">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-viewing-location-policy-information.md">Anzeigen von Standortrichtlinien Informationen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e52e-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="3e52e-127">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Website bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="3e52e-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="3e52e-128">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e52e-129">Wenn Sie eine neue Netzwerk Website erstellen, verwenden Sie die Tabelle <STRONG>zugeordnete</STRONG> Subnetze nicht.</span><span class="sxs-lookup"><span data-stu-id="3e52e-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="3e52e-130">Sie verknüpfen ein Subnetz mit einer Website, wenn Sie das Subnetz erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="3e52e-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="3e52e-131">Ausführliche Informationen finden Sie unter Erstellen oder Ändern von Netzwerk-Subnetzen <A href="lync-server-2013-create-or-modify-network-subnets.md">in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e52e-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="3e52e-132">So ändern Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="3e52e-132">To modify a network site</span></span>

1.  <span data-ttu-id="3e52e-133">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3e52e-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e52e-134">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e52e-135">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e52e-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e52e-136">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3e52e-137">Klicken Sie auf der Seite **Website** auf die Website, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3e52e-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="3e52e-138">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3e52e-139">Auf der Seite " **Website bearbeiten** " können Sie die Beschreibung, die Region, das bandbreitenrichtlinienprofil und die der Website zugeordnete Standortrichtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="3e52e-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="3e52e-140">Ausführliche Informationen finden Sie weiter oben in diesem Thema unter "So erstellen Sie eine Netzwerk Website".</span><span class="sxs-lookup"><span data-stu-id="3e52e-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="3e52e-141">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-141">Click **Commit**.</span></span>

<span data-ttu-id="3e52e-142">Auf dieser Seite können Sie die Tabelle **zugeordnete Subnets** nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3e52e-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="3e52e-143">Die Liste der zugeordneten Subnetze wird als Referenz bereitgestellt, damit Sie wissen, welche Subnetze betroffen sind, wenn Sie die Websiteeinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="3e52e-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="3e52e-144">So löschen Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="3e52e-144">To delete a network site</span></span>

1.  <span data-ttu-id="3e52e-145">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3e52e-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e52e-146">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e52e-147">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e52e-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e52e-148">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3e52e-149">Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3e52e-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e52e-150">Sie können mehr als eine Website gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="3e52e-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="3e52e-151">Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="3e52e-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="3e52e-152">Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3e52e-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="3e52e-153">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="3e52e-154">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e52e-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3e52e-155">Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3e52e-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="3e52e-156">Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e52e-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="3e52e-157">Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3e52e-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e52e-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e52e-158">See Also</span></span>


[<span data-ttu-id="3e52e-159">Löschen einer vorhandenen Netzwerk Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e52e-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="3e52e-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3e52e-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="3e52e-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3e52e-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="3e52e-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3e52e-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="3e52e-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3e52e-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


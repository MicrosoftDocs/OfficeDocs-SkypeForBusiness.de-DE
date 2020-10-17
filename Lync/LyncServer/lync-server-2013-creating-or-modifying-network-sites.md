---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerkstandorten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c88ca28478cbd9d38e9e85c5a852fb93b49c0df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516722"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="f4e68-102">Erstellen oder Ändern von Netzwerkstandorten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e68-102">Creating or modifying network sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e68-103">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="f4e68-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="f4e68-104">Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f4e68-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f4e68-105">Sie können die Microsoft lync Server 2013-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie Regionen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f4e68-106">Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f4e68-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f4e68-107">Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="f4e68-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f4e68-108">In der lync Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f4e68-109">Verwenden Sie das folgende Verfahren, um einen Netzwerkstandort zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f4e68-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="f4e68-110">Ausführliche Informationen zum Löschen eines vorhandenen Netzwerkstandorts finden Sie unter [Löschen eines vorhandenen Netzwerkstandorts in lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="f4e68-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="f4e68-111">So erstellen Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="f4e68-111">To create a network site</span></span>

1.  <span data-ttu-id="f4e68-112">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f4e68-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4e68-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4e68-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4e68-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4e68-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="f4e68-116">Klicken Sie auf der Seite **Standort** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="f4e68-117">Geben Sie unter **Neuer Standort** im Feld **Name** einen Namen für den Standort ein.</span><span class="sxs-lookup"><span data-stu-id="f4e68-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e68-118">Websitenamen müssen innerhalb der lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f4e68-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="f4e68-119">Wählen Sie in der Dropdownliste **Region** eine Netzwerkregion aus, die diesem Standort zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4e68-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="f4e68-120">(Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe für diesen Standort festlegen möchten, wählen Sie das Bandbreitenrichtlinienprofil mit den passenden Einstellungen in der Dropdownliste **Bandbreitenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="f4e68-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e68-121">Auf der Seite <STRONG>Richtlinienprofil</STRONG> in der Gruppe <STRONG>Netzwerkkonfiguration</STRONG> können Sie die Details der verfügbaren Bandbreitenrichtlinienprofile anzeigen oder ein neues Bandbreitenrichtlinienprofil erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="f4e68-122">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="f4e68-123">(Optional) Wenn Sie Ortungseinstellungen für diesen Standort bereitstellen möchten, wählen Sie in der Dropdownliste **Ortungsrichtlinie** eine Ortungsrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="f4e68-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e68-124">Die Ortungsrichtlinie weist dem Standort bestimmte E9-1-1- und Clientstandorteinstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="f4e68-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="f4e68-125">Auf der Seite <STRONG>Ortungsrichtlinie</STRONG> in der Gruppe <STRONG>Netzwerkkonfiguration</STRONG> können Sie die Details der verfügbaren Ortungsrichtlinien anzeigen oder eine neue Ortungsrichtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="f4e68-126">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-viewing-location-policy-information.md">Anzeigen von Informationen zu Standortrichtlinien in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="f4e68-127">(Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Standort ein, die nicht durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="f4e68-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f4e68-128">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e68-129">Beim Erstellen eines neuen Netzwerkstandorts verwenden Sie nicht die Tabelle <STRONG>Zugeordnete Subnetze</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="f4e68-130">Sie ordnen einem Standort ein Subnetz zu, wenn Sie das Subnetz erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="f4e68-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="f4e68-131">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-network-subnets.md">erstellen oder Ändern von Netzwerk Subnetzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="f4e68-132">So ändern Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="f4e68-132">To modify a network site</span></span>

1.  <span data-ttu-id="f4e68-133">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f4e68-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4e68-134">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4e68-135">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4e68-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4e68-136">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="f4e68-137">Klicken Sie auf der Seite **Standort** auf den Standort, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f4e68-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="f4e68-138">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f4e68-p107">Auf der Seite **Standort bearbeiten** können Sie die Beschreibung, die Region, das Bandbreitenrichtlinienprofil und die Ortungsrichtlinie für den Standort ändern. Ausführliche Informationen hierzu finden Sie unter "So erstellen Sie einen Netzwerkstandort" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="f4e68-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="f4e68-141">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-141">Click **Commit**.</span></span>

<span data-ttu-id="f4e68-p108">Sie können die Tabelle **Zugeordnete Subnetze** auf dieser Seite nicht ändern. Die Liste der zugeordneten Subnetze wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Subnetze sich die Änderung der Standorteinstellungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f4e68-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="f4e68-144">So löschen Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="f4e68-144">To delete a network site</span></span>

1.  <span data-ttu-id="f4e68-145">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f4e68-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4e68-146">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f4e68-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4e68-147">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4e68-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4e68-148">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="f4e68-149">Klicken Sie auf der Seite **Standort** auf den Standort, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="f4e68-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4e68-p110">Sie können mehrere Standorte in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Standorte aus. Wenn Sie alle Standorte auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="f4e68-153">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f4e68-154">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4e68-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f4e68-p111">Ein Netzwerkstandort kann nicht gelöscht werden, wenn er einem Netzwerksubnetz zugeordnet ist. Wenn Sie versuchen, einen einem Subnetz zugeordneten Standort zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob ein Standort einem Subnetz zugeordnet ist, klicken Sie auf den Standort und anschließend im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f4e68-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4e68-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4e68-158">See Also</span></span>


[<span data-ttu-id="f4e68-159">Löschen eines vorhandenen Netzwerkstandorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e68-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="f4e68-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4e68-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="f4e68-161">Gruppe-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4e68-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="f4e68-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4e68-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="f4e68-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4e68-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


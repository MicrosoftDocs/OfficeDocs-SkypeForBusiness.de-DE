---
title: Verwalten der Anrufsteuerung für Websites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Netzwerk Websites sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen.
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279543"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="67cc3-103">Verwalten der Anrufsteuerung für Standorte in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="67cc3-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="67cc3-104">Netzwerk Websites sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="67cc3-105">Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um die Anrufsteuerung für Netzwerk Websites zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="67cc3-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="67cc3-106">Konfigurieren von Netzwerkstandort Links</span><span class="sxs-lookup"><span data-stu-id="67cc3-106">Configure network site links</span></span>

<span data-ttu-id="67cc3-107">Innerhalb einer Anruf Steuerungskonfiguration können Sie netzwerkübergreifende Richtlinien erstellen, die Bandbreiteneinschränkungen zwischen Websites definieren, die direkt verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="67cc3-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="67cc3-108">Wenn Netzwerk Websites einen direkten Link verwenden, können Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen beiden Websites definiert werden.</span><span class="sxs-lookup"><span data-stu-id="67cc3-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="67cc3-109">Sie können die Skype for Business Server-Systemsteuerung nicht zum Konfigurieren von Netzwerk Website Richtlinien verwenden, dies kann nur mithilfe von Cmdlets aus der Skype for Business Server-Verwaltungsshell erfolgen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="67cc3-110">Über die Skype for Business Server-Verwaltungsshell können Sie einen Link zur Netzwerk Website (auch bekannt als netzwerkübergreifende Website Richtlinie) erstellen, ändern und entfernen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="67cc3-111">So erstellen Sie einen Netzwerkstandort Link</span><span class="sxs-lookup"><span data-stu-id="67cc3-111">To create a network site link</span></span>

1.  <span data-ttu-id="67cc3-112">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist.</span><span class="sxs-lookup"><span data-stu-id="67cc3-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="67cc3-113">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="67cc3-114">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und ersetzen Sie Werte, die für Ihre Konfiguration gültig sind:</span><span class="sxs-lookup"><span data-stu-id="67cc3-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="67cc3-115">In diesem Beispiel wird eine neue netzwerkstandortverknüpfung namens\_Reno Portland erstellt, die Bandbreiteneinschränkungen zwischen den Netzwerkstandorten Reno und Portland festlegt.</span><span class="sxs-lookup"><span data-stu-id="67cc3-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="67cc3-116">Die Netzwerk Websites und das bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="67cc3-117">Ausführliche Beschreibungen zu Parametern finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="67cc3-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="67cc3-118">Rufen Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile** auf, um eine Liste der bandbreitenrichtlinienprofile abzurufen, die auf den Link Netzwerk Website angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="67cc3-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="67cc3-119">Ausführliche Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="67cc3-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="67cc3-120">So ändern Sie einen Link für eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="67cc3-120">To modify a network site link</span></span>

1.  <span data-ttu-id="67cc3-121">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist.</span><span class="sxs-lookup"><span data-stu-id="67cc3-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="67cc3-122">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="67cc3-123">Verwenden Sie das Cmdlet " **Satz-CsNetworkInterSitePolicy** ", um die Eigenschaften einer bestimmten netzwerkstandortverknüpfung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="67cc3-124">Sie können entweder (oder beide) oder die verbundenen Websites ändern, und Sie können das dem Link zugeordnete bandbreitenrichtlinienprofil ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="67cc3-125">Nachfolgend finden Sie ein Beispiel für das Ändern des bandbreitenrichtlinienprofils einer Standort\_Verknüpfung mit dem Namen Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="67cc3-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="67cc3-126">Ausführliche Beschreibungen zu Parametern finden Sie unter [Satz-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="67cc3-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="67cc3-127">So löschen Sie einen Netzwerkstandort Link</span><span class="sxs-lookup"><span data-stu-id="67cc3-127">To delete a network site link</span></span>

1.  <span data-ttu-id="67cc3-128">Melden Sie sich bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist.</span><span class="sxs-lookup"><span data-stu-id="67cc3-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="67cc3-129">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="67cc3-130">Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy** , um einen Netzwerkstandort Link zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="67cc3-131">Im folgenden Beispiel wird der Link\_zur Portland-Netzwerk Website von Reno gelöscht:</span><span class="sxs-lookup"><span data-stu-id="67cc3-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="67cc3-132">Ausführliche Beschreibungen der Parameter finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="67cc3-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="67cc3-133">Anzeigen von Netzwerk Website Informationen</span><span class="sxs-lookup"><span data-stu-id="67cc3-133">View network site information</span></span>

<span data-ttu-id="67cc3-134">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="67cc3-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="67cc3-135">Sie können Informationen zur Netzwerk Website entweder in der Skype for Business Server-Systemsteuerung oder in der Skype for Business Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="67cc3-136">So zeigen Sie Netzwerk Website Informationen in der Skype for Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="67cc3-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="67cc3-137">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="67cc3-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67cc3-138">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="67cc3-139">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="67cc3-140">Klicken Sie auf der Seite **Website** auf die Website, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="67cc3-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="67cc3-141">Sie können nur Informationen für eine Website gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="67cc3-142">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="67cc3-143">Anzeigen von Netzwerk Website Informationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="67cc3-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="67cc3-144">Sie können Netzwerk Website Informationen mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkSite anzeigen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="67cc3-145">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="67cc3-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="67cc3-146">So zeigen Sie Netzwerk Website Informationen an</span><span class="sxs-lookup"><span data-stu-id="67cc3-146">To view network site information</span></span>

  - <span data-ttu-id="67cc3-147">Wenn Sie Informationen zu allen Ihren Netzwerk Websites anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="67cc3-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="67cc3-148">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="67cc3-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="67cc3-149">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="67cc3-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="67cc3-150">Erstellen oder Ändern von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="67cc3-150">Create or modify network sites</span></span> 

<span data-ttu-id="67cc3-151">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="67cc3-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="67cc3-152">Sie können die Skype for Business Server-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="67cc3-153">Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="67cc3-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="67cc3-154">Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="67cc3-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="67cc3-155">Über das Skype for Business Server Control Panel können Sie Netzwerk Websites erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="67cc3-156">Gehen Sie wie folgt vor, um eine Netzwerk Website zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="67cc3-157">So erstellen Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="67cc3-157">To create a network site</span></span>

1.  <span data-ttu-id="67cc3-158">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="67cc3-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67cc3-159">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="67cc3-160">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="67cc3-161">Klicken Sie auf der Seite **Website** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="67cc3-162">Geben Sie auf der **neuen Website**im Feld **Name** einen Namen für diese Website ein.</span><span class="sxs-lookup"><span data-stu-id="67cc3-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="67cc3-163">Websitenamen müssen innerhalb der Skype for Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="67cc3-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="67cc3-164">Wählen Sie in der Dropdownliste **Region** einen Netzwerkbereich aus, der dieser Website zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="67cc3-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="67cc3-165">Optional Wenn Sie Bandbreiteneinschränkungen für Audio-oder Videoanrufe an diese Website vornehmen möchten, wählen Sie das bandbreitenrichtlinienprofil mit den entsprechenden Einstellungen in der Dropdownliste **bandbreitenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="67cc3-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="67cc3-166">Sie können die Details der verfügbaren bandbreitenrichtlinienprofile anzeigen oder ein neues bandbreitenrichtlinienprofil auf der Seite **Richtlinienprofil** der Gruppe **Netzwerkkonfiguration** erstellen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="67cc3-167">Ausführliche Informationen finden Sie unter [Verwalten von Netzwerkbandbreite-Richtlinienprofilen](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="67cc3-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="67cc3-168">Optional Wenn Sie die Standorteinstellungen für diese Website angeben möchten, wählen Sie in der Dropdownliste **Standortrichtlinie** eine Standortrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="67cc3-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="67cc3-169">Die Standortrichtlinie weist der Website bestimmte erweiterte 9-1-1-Einstellungen (E9-1-1) und Clientstandort Einstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="67cc3-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="67cc3-170">Sie können die Details der verfügbaren Standortrichtlinien anzeigen oder eine neue Standortrichtlinie erstellen, die sich auf der Seite " **Standortrichtlinie** " der Gruppe " **Netzwerkkonfiguration** " befindet.</span><span class="sxs-lookup"><span data-stu-id="67cc3-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="67cc3-171">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Website bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="67cc3-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="67cc3-172">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="67cc3-173">Wenn Sie eine neue Netzwerk Website erstellen, verwenden Sie die Tabelle **zugeordnete** Subnetze nicht.</span><span class="sxs-lookup"><span data-stu-id="67cc3-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="67cc3-174">Sie verknüpfen ein Subnetz mit einer Website, wenn Sie das Subnetz erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="67cc3-175">Ausführliche Informationen finden Sie unter [Verwalten von Netzwerk](managing-network-subnets.md)-Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="67cc3-176">So ändern Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="67cc3-176">To modify a network site</span></span>

1.  <span data-ttu-id="67cc3-177">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="67cc3-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67cc3-178">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="67cc3-179">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="67cc3-180">Klicken Sie auf der Seite **Website** auf die Website, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="67cc3-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="67cc3-181">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="67cc3-182">Auf der Seite " **Website bearbeiten** " können Sie die Beschreibung, die Region, das bandbreitenrichtlinienprofil und die der Website zugeordnete Standortrichtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="67cc3-183">Ausführliche Informationen finden Sie unter [So erstellen Sie eine Netzwerk Website](#to-create-a-network-site) oben.</span><span class="sxs-lookup"><span data-stu-id="67cc3-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="67cc3-184">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-184">Click **Commit**.</span></span>

<span data-ttu-id="67cc3-185">Auf dieser Seite können Sie die Tabelle **zugeordnete Subnets** nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="67cc3-186">Die Liste der zugeordneten Subnetze wird als Referenz bereitgestellt, damit Sie wissen, welche Subnetze betroffen sind, wenn Sie die Websiteeinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="67cc3-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="67cc3-187">Löschen einer vorhandenen Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="67cc3-187">Delete an existing network site</span></span>

<span data-ttu-id="67cc3-188">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="67cc3-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="67cc3-189">Sie können die Skype for Business Server-Systemsteuerung verwenden, um Websites zu konfigurieren und Sie mit Regionen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="67cc3-190">Beispielsweise kann eine netzwerkregion für Nordamerika mit Netzwerken wie Chicago, Redmond und Vancouver verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="67cc3-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="67cc3-191">Eine CAC-Netzwerk Website muss für jede Website innerhalb einer Organisation erstellt werden, selbst wenn diese Website keine Bandbreiteneinschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="67cc3-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="67cc3-192">Über das Skype for Business Server Control Panel können Sie Netzwerk Websites erstellen, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="67cc3-193">Gehen Sie wie folgt vor, um eine vorhandene Netzwerk Website zu löschen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="67cc3-194">Details zum Erstellen oder Ändern von Netzwerk Websites finden Sie unter [Verwalten der Anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="67cc3-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="67cc3-195">So löschen Sie eine Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="67cc3-195">To delete a network site</span></span>

1.  <span data-ttu-id="67cc3-196">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="67cc3-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67cc3-197">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="67cc3-198">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="67cc3-199">Klicken Sie auf der Seite **Website** auf die Website, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="67cc3-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="67cc3-200">Sie können mehr als eine Website gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="67cc3-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="67cc3-201">Drücken Sie dazu STRG, und wählen Sie mehrere Websites aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="67cc3-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="67cc3-202">Wenn Sie alle Websites auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="67cc3-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="67cc3-203">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="67cc3-204">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67cc3-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="67cc3-205">Sie können eine Netzwerk Website nicht entfernen, wenn Sie einem Netzwerk-Subnetz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="67cc3-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="67cc3-206">Wenn Sie versuchen, eine Website zu entfernen, die einem Subnetz zugeordnet ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67cc3-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="67cc3-207">Wenn Sie feststellen möchten, ob eine Website mit Subnetzen verknüpft ist, klicken Sie auf die Website, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="67cc3-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="67cc3-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67cc3-208">See Also</span></span>


[<span data-ttu-id="67cc3-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="67cc3-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="67cc3-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="67cc3-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="67cc3-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="67cc3-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="67cc3-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="67cc3-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="67cc3-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="67cc3-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="67cc3-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="67cc3-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="67cc3-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="67cc3-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="67cc3-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="67cc3-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="67cc3-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="67cc3-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  

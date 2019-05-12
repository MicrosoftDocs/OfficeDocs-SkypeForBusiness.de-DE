---
title: Verwalten der anrufsteuerung für Standorte
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Netzwerkstandorte sind die Büros oder Speicherorte innerhalb jeder netzwerkregion der anrufsteuerung (CAC), E9-1-1 und Media Bypass Bereitstellungen aufrufen.
ms.openlocfilehash: b7d554f6c85a40c084571813c88cc1d08661fa42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913405"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="38ac2-103">Verwalten der Anrufsteuerung für Standorte in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38ac2-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="38ac2-104">Netzwerkstandorte sind die Büros oder Speicherorte innerhalb jeder netzwerkregion der anrufsteuerung (CAC), E9-1-1 und Media Bypass Bereitstellungen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="38ac2-105">Verwenden Sie die Verfahren in diesem Artikel, um die anrufsteuerung bei den Netzwerkstandorten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="38ac2-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="38ac2-106">Konfigurieren von netzwerkstandortverknüpfungen</span><span class="sxs-lookup"><span data-stu-id="38ac2-106">Configure network site links</span></span>

<span data-ttu-id="38ac2-107">Innerhalb einer Call Admission Control (, CAC) Konfiguration können Sie Netzwerk an standortübergreifende Richtlinien erstellen, die bandbreiteneinschränkungen zwischen Standorten definieren, die direkt verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="38ac2-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="38ac2-108">Wenn Netzwerkstandorten eine direkte Verknüpfung freigeben, können die Bandbreite für Audio- und videoverbindungen zwischen zwei Websites definiert werden.</span><span class="sxs-lookup"><span data-stu-id="38ac2-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="38ac2-109">Sie können die Skype Business Server-Systemsteuerung Website Netzwerkrichtlinien konfigurieren, dazu können nur mithilfe der Skype-Cmdlets für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="38ac2-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="38ac2-110">Sie können erstellen, ändern und entfernen eine netzwerkstandortverknüpfung (auch bekannt als eine standortübergreifende Netzwerkrichtlinie) aus der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="38ac2-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="38ac2-111">Erstellen Sie eine netzwerkstandortverknüpfung</span><span class="sxs-lookup"><span data-stu-id="38ac2-111">To create a network site link</span></span>

1.  <span data-ttu-id="38ac2-112">Melden Sie sich bei dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist, an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="38ac2-113">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="38ac2-114">Geben Sie über die Befehlszeile den folgenden Befehl ein, ersetzen die gültigen Werte für die Konfiguration aus:</span><span class="sxs-lookup"><span data-stu-id="38ac2-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="38ac2-115">Dieses Beispiel erstellt eine neue netzwerkstandortverknüpfung mit dem Namen Reno\_Portland, die bandbreiteneinschränkungen zwischen Reno und Portland Netzwerkstandorte festlegt.</span><span class="sxs-lookup"><span data-stu-id="38ac2-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="38ac2-116">Netzwerkstandorte und das bandbreitenrichtlinienprofil müssen vor dem Ausführen dieses Befehls bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="38ac2-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="38ac2-117">Ausführliche Beschreibung der Parameter finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="38ac2-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="38ac2-118">Um eine Liste der bandbreitenrichtlinienprofile abzurufen, die auf die netzwerkstandortverknüpfung angewendet werden können, rufen Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="38ac2-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="38ac2-119">Weitere Informationen hierzu finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="38ac2-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="38ac2-120">So ändern Sie eine netzwerkstandortverknüpfung</span><span class="sxs-lookup"><span data-stu-id="38ac2-120">To modify a network site link</span></span>

1.  <span data-ttu-id="38ac2-121">Melden Sie sich bei dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist, an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="38ac2-122">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="38ac2-123">Verwenden Sie das Cmdlet **Set-CsNetworkInterSitePolicy** , um die Eigenschaften einer bestimmten netzwerkstandortverknüpfung ändern.</span><span class="sxs-lookup"><span data-stu-id="38ac2-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="38ac2-124">Sie können einen (oder beide) ändern oder die verbundenen Websites, und Sie können das bandbreitenrichtlinienprofil, das dem Hyperlink zugeordnete ändern.</span><span class="sxs-lookup"><span data-stu-id="38ac2-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="38ac2-125">Nachfolgend finden Sie ein Beispiel zum Ändern einer Website Verknüpfung mit dem Namen "Reno" mithilfe des bandbreitenrichtlinienprofil\_Portland:</span><span class="sxs-lookup"><span data-stu-id="38ac2-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="38ac2-126">Ausführliche Beschreibung der Parameter finden Sie unter [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="38ac2-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="38ac2-127">So löschen Sie eine netzwerkstandortverknüpfung</span><span class="sxs-lookup"><span data-stu-id="38ac2-127">To delete a network site link</span></span>

1.  <span data-ttu-id="38ac2-128">Melden Sie sich bei dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist, an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="38ac2-129">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="38ac2-130">Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy** , um eine netzwerkstandortverknüpfung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="38ac2-131">Das folgende Beispiel löscht die Reno\_Portland netzwerkstandortverknüpfung:</span><span class="sxs-lookup"><span data-stu-id="38ac2-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="38ac2-132">Ausführliche Beschreibung der Parameter finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="38ac2-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="38ac2-133">Anzeigen von Informationen zu Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="38ac2-133">View network site information</span></span>

<span data-ttu-id="38ac2-134">Netzwerkstandorte sind die Niederlassungen oder Standorte innerhalb jeder Region einer anrufsteuerung (CAC) oder Enhanced 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="38ac2-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="38ac2-135">Sie können Informationen zu Netzwerkstandorten in entweder die Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="38ac2-136">Zum Anzeigen von Informationen zu Netzwerkstandorten in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="38ac2-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="38ac2-137">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38ac2-138">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="38ac2-139">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="38ac2-140">Klicken Sie auf der Seite **Website** auf der Website, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="38ac2-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="38ac2-141">Sie können nur Informationen für einen Standort zu einem Zeitpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="38ac2-142">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="38ac2-143">Anzeigen von Informationen zu Netzwerkstandorten mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="38ac2-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="38ac2-144">Sie können Informationen zu Netzwerkstandorten mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkSite anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="38ac2-145">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="38ac2-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="38ac2-146">So zeigen Sie netzwerkstandortinformationen an</span><span class="sxs-lookup"><span data-stu-id="38ac2-146">To view network site information</span></span>

  - <span data-ttu-id="38ac2-147">Anzeigen von Informationen zu allen Netzwerkstandorten, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="38ac2-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="38ac2-148">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="38ac2-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="38ac2-149">Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="38ac2-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="38ac2-150">Erstellen oder Ändern von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="38ac2-150">Create or modify network sites</span></span> 

<span data-ttu-id="38ac2-151">Netzwerkstandorte sind die Niederlassungen oder Standorte innerhalb jeder Region einer anrufsteuerung (CAC) oder Enhanced 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="38ac2-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="38ac2-152">Die Skype Business Server-Systemsteuerung können zum Konfigurieren von Websites und Regionen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="38ac2-153">Beispielsweise könnte eine netzwerkregion für Nordamerika Netzwerke Websites wie "Chicago" und "Redmond" Vancouver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="38ac2-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="38ac2-154">Ein Netzwerkstandort CAC muss für jede Website innerhalb einer Organisation erstellt werden, auch wenn diese Website keine Netzwerkbandbreite ist eingeschränkt wurde.</span><span class="sxs-lookup"><span data-stu-id="38ac2-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="38ac2-155">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern und Löschen von Netzwerk-Sites.</span><span class="sxs-lookup"><span data-stu-id="38ac2-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="38ac2-156">Verwenden Sie die folgenden Verfahren zum Erstellen oder Ändern eines Netzwerkstandorts.</span><span class="sxs-lookup"><span data-stu-id="38ac2-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="38ac2-157">So erstellen Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="38ac2-157">To create a network site</span></span>

1.  <span data-ttu-id="38ac2-158">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38ac2-159">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="38ac2-160">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="38ac2-161">Klicken Sie auf der Seite **Website** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="38ac2-162">Geben Sie unter **Neue Website**einen Namen für diese Website in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="38ac2-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="38ac2-163">Standortnamen müssen innerhalb der Skype für Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="38ac2-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="38ac2-164">Wählen Sie in der Dropdownliste **Region** eine netzwerkregion an diesem Standort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="38ac2-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="38ac2-165">(Optional) Wenn Sie die Netzwerkbandbreite ist eingeschränkt auf Audio- oder Videoinhalten Anrufe an diese Website platzieren möchten, wählen Sie das bandbreitenrichtlinienprofil mit den entsprechenden Einstellungen aus der Dropdownliste **bandbreitenrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="38ac2-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="38ac2-166">Sie können die Details zu den verfügbaren bandbreitenrichtlinienprofile anzeigen oder erstellen ein neues bandbreitenrichtlinienprofil auf der Seite **Richtlinie Profil** , der die Gruppe **Netzwerkkonfiguration** .</span><span class="sxs-lookup"><span data-stu-id="38ac2-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="38ac2-167">Weitere Informationen hierzu finden Sie unter [Verwalten von Netzwerk-bandbreitenrichtlinienprofilen](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="38ac2-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="38ac2-168">(Optional) Wenn Sie ortungseinstellungen für diese Website bereitstellen möchten, wählen Sie aus der Dropdownliste **ortungsrichtlinie** eine ortungsrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="38ac2-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="38ac2-169">Die Standortrichtlinie weist bestimmte erweiterte E9-1-1 (E9-1-1) und Client standorteinstellungen zu der Website.</span><span class="sxs-lookup"><span data-stu-id="38ac2-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="38ac2-170">Sie können die Details zu den verfügbaren Standortrichtlinien anzeigen oder erstellen eine neue ortungsrichtlinie auf der Seite **Standortrichtlinie** die Gruppe **Netzwerkkonfiguration** .</span><span class="sxs-lookup"><span data-stu-id="38ac2-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="38ac2-171">(Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu dieser Website bereitzustellen, die durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="38ac2-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="38ac2-172">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="38ac2-173">Sie verwenden die **Subnetze verknüpften** Tabelle nicht, wenn Sie einen neuen Netzwerkstandort erstellen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="38ac2-174">Sie Zuordnen eines Subnetzes zu einer Website, wenn Sie erstellen oder ändern das Subnetz.</span><span class="sxs-lookup"><span data-stu-id="38ac2-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="38ac2-175">Weitere Informationen hierzu finden Sie unter [Verwalten von Netzwerksubnetzen](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="38ac2-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="38ac2-176">So ändern Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="38ac2-176">To modify a network site</span></span>

1.  <span data-ttu-id="38ac2-177">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38ac2-178">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="38ac2-179">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="38ac2-180">Klicken Sie auf der Seite **Website** auf der Website, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="38ac2-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="38ac2-181">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="38ac2-182">Klicken Sie auf der Seite **Standort bearbeiten** können Sie die Beschreibung, Region, bandbreitenrichtlinienprofil und ortungsrichtlinie, die der Website zugeordnet ändern.</span><span class="sxs-lookup"><span data-stu-id="38ac2-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="38ac2-183">Weitere Informationen hierzu finden Sie unter [So erstellen Sie einen Netzwerkstandort](#to-create-a-network-site) oben.</span><span class="sxs-lookup"><span data-stu-id="38ac2-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="38ac2-184">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-184">Click **Commit**.</span></span>

<span data-ttu-id="38ac2-185">Die Tabelle **Zugeordnete Subnetze** auf dieser Seite können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="38ac2-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="38ac2-186">Die Liste der zugeordnete Subnetze zu Referenzzwecken bereitgestellt, sodass welche Subnetze betroffen sind, wenn Sie die Einstellungen ändern bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="38ac2-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="38ac2-187">Löschen Sie einen vorhandenen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="38ac2-187">Delete an existing network site</span></span>

<span data-ttu-id="38ac2-188">Netzwerkstandorte sind die Niederlassungen oder Standorte innerhalb jeder Region einer anrufsteuerung (CAC) oder Enhanced 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="38ac2-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="38ac2-189">Die Skype Business Server-Systemsteuerung können zum Konfigurieren von Websites und Regionen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="38ac2-190">Beispielsweise könnte eine netzwerkregion für Nordamerika Netzwerke Websites wie "Chicago" und "Redmond" Vancouver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="38ac2-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="38ac2-191">Ein Netzwerkstandort CAC muss für jede Website innerhalb einer Organisation erstellt werden, auch wenn diese Website keine Netzwerkbandbreite ist eingeschränkt wurde.</span><span class="sxs-lookup"><span data-stu-id="38ac2-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="38ac2-192">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern und Löschen von Netzwerk-Sites.</span><span class="sxs-lookup"><span data-stu-id="38ac2-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="38ac2-193">Verwenden Sie das folgende Verfahren, um einen vorhandenen Netzwerkstandort zu löschen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="38ac2-194">Ausführliche Informationen zum Erstellen oder Ändern von Netzwerkstandorten finden Sie unter [Verwalten der anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="38ac2-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="38ac2-195">So löschen Sie einen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="38ac2-195">To delete a network site</span></span>

1.  <span data-ttu-id="38ac2-196">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="38ac2-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38ac2-197">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="38ac2-198">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="38ac2-199">Klicken Sie auf der Seite **Website** auf der Website, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="38ac2-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="38ac2-200">Sie können mehrere Websites zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="38ac2-201">Zu diesem Zweck STRG-Taste gedrückt, und wählen Sie mehrere Standorte während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="38ac2-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="38ac2-202">Oder, um alle Websites auszuwählen, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="38ac2-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="38ac2-203">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="38ac2-204">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="38ac2-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="38ac2-205">Sie können einen Netzwerkstandort nicht entfernen, wenn sie ein Netzwerksubnetz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="38ac2-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="38ac2-206">Erhalten Sie eine Fehlermeldung, wenn Sie versuchen, eine Website, die ein Subnetz zugeordnet zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="38ac2-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="38ac2-207">Um herauszufinden, ob eine Website Subnetze zugeordnet ist, klicken Sie auf der Website, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="38ac2-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="38ac2-208">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38ac2-208">See Also</span></span>


[<span data-ttu-id="38ac2-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="38ac2-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="38ac2-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="38ac2-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="38ac2-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="38ac2-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="38ac2-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="38ac2-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="38ac2-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="38ac2-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="38ac2-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="38ac2-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="38ac2-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="38ac2-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="38ac2-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="38ac2-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="38ac2-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="38ac2-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  

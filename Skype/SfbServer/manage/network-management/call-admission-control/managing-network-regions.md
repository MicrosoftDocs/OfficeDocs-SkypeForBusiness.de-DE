---
title: Verwalten von netzwerkregionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Netzwerkregion * sind die Netzwerkhubs oder Backbones, die bei der Konfiguration der Anrufsteuerung, E9-1-1 und medienumgehung verwendet werden.
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817484"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="75699-103">Verwalten von Netzwerkregionen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="75699-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="75699-104">*Netzwerkregionen* sind die Netzwerkhubs oder Backbones, die in der Konfiguration der Anruf Zulassungs Steuerung, E9-1-1 und medienumgehung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75699-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="75699-105">Gehen Sie wie folgt vor, um netzwerkregionen anzuzeigen, zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="75699-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="75699-106">Wenn Sie beispielsweise bereits netzwerkregionen für ein Sprachfeature erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="75699-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="75699-107">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="75699-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="75699-108">Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="75699-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="75699-109">Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um Netzwerk Regionsinformationen anzuzeigen oder netzwerkregionen zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="75699-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="75699-110">Anzeigen von Netzwerk Regionsinformationen</span><span class="sxs-lookup"><span data-stu-id="75699-110">View network region information</span></span> 


<span data-ttu-id="75699-111">Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg.</span><span class="sxs-lookup"><span data-stu-id="75699-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="75699-112">Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="75699-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="75699-113">Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="75699-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="75699-114">Sie können die Skype for Business Server-Systemsteuerung verwenden, um netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75699-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="75699-115">Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="75699-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="75699-116">Verwenden Sie dieses Thema, um vorhandene netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75699-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="75699-117">So zeigen Sie Informationen zu einem Netzwerkbereich mit der Skype for Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="75699-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="75699-118">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="75699-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75699-119">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75699-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="75699-120">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="75699-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="75699-121">Klicken Sie auf der Seite **Region** auf den Bereich, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="75699-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="75699-122">Sie können nur jeweils einen Bereich anzeigen.</span><span class="sxs-lookup"><span data-stu-id="75699-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="75699-123">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="75699-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75699-124">Anzeigen von Netzwerk Regionsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="75699-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="75699-125">Sie können Netzwerk Regionsinformationen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegion** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="75699-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="75699-126">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="75699-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="75699-127">So zeigen Sie Netzwerkbereichs Informationen an</span><span class="sxs-lookup"><span data-stu-id="75699-127">To view network region information</span></span>

  - <span data-ttu-id="75699-128">Wenn Sie Informationen zu allen ihren netzwerkregionen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="75699-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="75699-129">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="75699-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="75699-130">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="75699-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="75699-131">Erstellen oder Ändern von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="75699-131">Create or modify network regions</span></span> 

<span data-ttu-id="75699-132">Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg.</span><span class="sxs-lookup"><span data-stu-id="75699-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="75699-133">Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="75699-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="75699-134">Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="75699-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="75699-135">Sie können die Skype for Business Server-Systemsteuerung verwenden, um netzwerkregionen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75699-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="75699-136">Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="75699-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="75699-137">In der Skype for Business Server-Systemsteuerung können Sie einen Netzwerkbereich erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="75699-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="75699-138">Verwenden Sie dieses Thema, um netzwerkregionen zu erstellen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="75699-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="75699-139">So erstellen Sie einen Netzwerkbereich</span><span class="sxs-lookup"><span data-stu-id="75699-139">To create a network region</span></span>

1.  <span data-ttu-id="75699-140">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="75699-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75699-141">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75699-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="75699-142">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="75699-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="75699-143">Klicken Sie auf der Seite **Region** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="75699-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="75699-144">Geben Sie auf der Seite **neuer Bereich** einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="75699-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="75699-145">Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="75699-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="75699-146">Wählen Sie in der Dropdownliste **Central Site** die zentrale Website für diesen Netzwerkbereich aus.</span><span class="sxs-lookup"><span data-stu-id="75699-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="75699-147">Das Kontrollkästchen **audioalternativen Pfad aktivieren** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="75699-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="75699-148">Dieses Feld bestimmt, ob Audioanrufe durch einen alternativen Pfad weitergeleitet werden, wenn im primären Pfad keine ausreichende Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="75699-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="75699-149">Deaktivieren Sie dieses Kontrollkästchen nur, wenn Sie die Verschiebung zum Internet deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="75699-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="75699-150">Wenn es sich bei ihren anrufen um Internet Anrufe handelt, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="75699-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="75699-151">Das Kontrollkästchen **Video alternativen Pfad aktivieren** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="75699-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="75699-152">Dieses Feld bestimmt, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn im primären Pfad keine ausreichende Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="75699-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="75699-153">Deaktivieren Sie dieses Kontrollkästchen nur, wenn Sie die Verschiebung zum Internet deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="75699-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="75699-154">Wenn es sich bei ihren anrufen um Internet Anrufe handelt, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="75699-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="75699-155">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu dieser Region bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="75699-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="75699-156">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="75699-156">Click **Commit**.</span></span>

<span data-ttu-id="75699-157">Die Tabelle **zugeordnete Websites** wird nicht zum Erstellen eines Netzwerkbereichs verwendet.</span><span class="sxs-lookup"><span data-stu-id="75699-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="75699-158">Sie ordnen eine Website einem Bereich zu, wenn Sie die Website erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="75699-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="75699-159">Ausführliche Informationen finden Sie unter [Verwalten der Anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="75699-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="75699-160">So ändern Sie einen Netzwerkbereich</span><span class="sxs-lookup"><span data-stu-id="75699-160">To modify a network region</span></span>

1.  <span data-ttu-id="75699-161">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="75699-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75699-162">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75699-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="75699-163">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="75699-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="75699-164">Klicken Sie auf der Seite **Region** auf den Bereich, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="75699-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="75699-165">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="75699-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="75699-166">Auf der Seite " **Bereich bearbeiten** " können Sie die Einstellungen für die Aktivierung und Deaktivierung von Audio-und Video Alternativen Pfaden ändern und die Beschreibung ändern (Einzelheiten finden Sie im Abschnitt "So erstellen Sie einen Netzwerkbereich" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="75699-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="75699-167">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="75699-167">Click **Commit**.</span></span>

<span data-ttu-id="75699-168">Auf dieser Seite können Sie die **zugehörigen Websites** nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="75699-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="75699-169">Die Liste der zugehörigen Websites wird als Referenz bereitgestellt, damit Sie wissen, welche Websites beeinträchtigt werden, wenn Sie die Regionseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="75699-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="75699-170">Löschen vorhandener netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="75699-170">Delete existing network regions</span></span> 

<span data-ttu-id="75699-171">Ein Netzwerkbereich verbindet verschiedene Teile eines Netzwerks über mehrere geographische Bereiche hinweg.</span><span class="sxs-lookup"><span data-stu-id="75699-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="75699-172">Jeder Netzwerkbereich muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="75699-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="75699-173">Der zentrale Standort ist die Datencenter-Website, auf der der bandbreitenrichtliniendienst für die Anrufannahme Steuerung (CAC) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="75699-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="75699-174">Sie können die Skype for Business Server-Systemsteuerung verwenden, um netzwerkregionen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75699-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="75699-175">Zu den netzwerkregionen gehören Einstellungen, die bestimmen, ob für Audio-und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="75699-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="75699-176">In der Skype for Business Server-Systemsteuerung können Sie einen Netzwerkbereich erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="75699-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="75699-177">Verwenden Sie dieses Thema, um vorhandene netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="75699-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="75699-178">So löschen Sie einen Netzwerkbereich</span><span class="sxs-lookup"><span data-stu-id="75699-178">To delete a network region</span></span>

1.  <span data-ttu-id="75699-179">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="75699-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75699-180">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75699-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="75699-181">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="75699-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="75699-182">Klicken Sie auf der Seite **Region** auf den Bereich, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="75699-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="75699-183">Sie können mehr als einen Bereich gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="75699-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="75699-184">Drücken Sie dazu STRG, und wählen Sie mehrere Bereiche aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="75699-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="75699-185">Wenn Sie alle Bereiche auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen** .</span><span class="sxs-lookup"><span data-stu-id="75699-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="75699-186">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="75699-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="75699-187">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="75699-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="75699-188">Eine netzwerkregion kann nicht entfernt werden, wenn Sie einer Netzwerk Website zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="75699-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="75699-189">Wenn Sie versuchen, einen Bereich zu entfernen, der einer Website zugeordnet ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75699-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="75699-190">Wenn Sie feststellen möchten, ob ein Bereich Websites zugeordnet ist, wählen Sie den Bereich aus, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="75699-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="75699-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75699-191">See Also</span></span>

[<span data-ttu-id="75699-192">Verwalten von Routen im Netzwerkbereich</span><span class="sxs-lookup"><span data-stu-id="75699-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="75699-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="75699-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="75699-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="75699-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="75699-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="75699-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="75699-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="75699-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  

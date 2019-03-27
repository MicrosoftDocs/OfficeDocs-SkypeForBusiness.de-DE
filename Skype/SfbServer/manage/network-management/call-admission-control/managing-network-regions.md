---
title: Verwalten von netzwerkregionen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Netzwerk Region * sind die Netzwerk-Hubs oder Backbones in der Konfiguration des Call Admission Control, E9-1-1 und medienumgehung verwendet.
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877629"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="27a61-103">Verwalten von Netzwerkregionen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="27a61-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="27a61-104">*Netzwerkregionen* sind die Netzwerk-Hubs oder Backbones in der Konfiguration des Call Admission Control, E9-1-1 und medienumgehung verwendet.</span><span class="sxs-lookup"><span data-stu-id="27a61-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="27a61-105">Verwenden Sie die folgenden Verfahren, um anzuzeigen, erstellen oder Ändern von netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="27a61-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="27a61-106">Angenommen, wenn Sie bereits von netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen nicht Sie neue netzwerkregionen zu erstellen; andere erweiterten Enterprise-VoIP-Funktionen werden die gleichen netzwerkregionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="27a61-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="27a61-107">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="27a61-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="27a61-108">Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="27a61-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="27a61-109">Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen von Informationen zur netzwerkregion oder erstellen, ändern oder Löschen von netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="27a61-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="27a61-110">Anzeigen von Informationen zur netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="27a61-110">View network region information</span></span> 


<span data-ttu-id="27a61-111">Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche.</span><span class="sxs-lookup"><span data-stu-id="27a61-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="27a61-112">Jeder netzwerkregion muss mit einem zentralen Standort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="27a61-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="27a61-113">Am zentrale Standort ist der Data Center-Website auf dem Call Admission Control (, CAC)-bandbreitenrichtliniendienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27a61-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="27a61-114">Sie können Skype Business Server-Systemsteuerung verwenden, um netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27a61-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="27a61-115">Netzwerkregionen umfassen Einstellungen, die bestimmen, ob alternative Pfade über das Internet für Audio- und videoverbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="27a61-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="27a61-116">Verwenden Sie dieses Thema, um vorhandene netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27a61-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="27a61-117">Zum Anzeigen von Informationen über eine netzwerkregion mit Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="27a61-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="27a61-118">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="27a61-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="27a61-119">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="27a61-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="27a61-120">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="27a61-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="27a61-121">Klicken Sie auf der Seite **Region** auf die Region, den, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="27a61-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="27a61-122">Sie können jeweils nur eine Region anzeigen.</span><span class="sxs-lookup"><span data-stu-id="27a61-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="27a61-123">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="27a61-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="27a61-124">Anzeigen von Informationen zur netzwerkregion mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="27a61-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="27a61-125">Sie können Informationen zur netzwerkregion mithilfe von Windows PowerShell und das Cmdlet **Get-CsNetworkRegion** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="27a61-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="27a61-126">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="27a61-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="27a61-127">Zum Anzeigen von Informationen zur netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="27a61-127">To view network region information</span></span>

  - <span data-ttu-id="27a61-128">Anzeigen von Informationen zu all Ihre netzwerkregionen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="27a61-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="27a61-129">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="27a61-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="27a61-130">Weitere Informationen finden Sie im Hilfethema zum [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="27a61-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="27a61-131">Erstellen oder Ändern von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="27a61-131">Create or modify network regions</span></span> 

<span data-ttu-id="27a61-132">Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche.</span><span class="sxs-lookup"><span data-stu-id="27a61-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="27a61-133">Jeder netzwerkregion muss mit einem zentralen Standort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="27a61-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="27a61-134">Am zentrale Standort ist der Data Center-Website auf dem Call Admission Control (, CAC)-bandbreitenrichtliniendienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27a61-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="27a61-135">Die Skype Business Server-Systemsteuerung können Sie netzwerkregionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="27a61-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="27a61-136">Netzwerkregionen umfassen Einstellungen, die bestimmen, ob alternative Pfade über das Internet für Audio- und videoverbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="27a61-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="27a61-137">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregion.</span><span class="sxs-lookup"><span data-stu-id="27a61-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="27a61-138">Verwenden Sie dieses Thema zum Erstellen und Ändern von netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="27a61-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="27a61-139">So erstellen Sie eine netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="27a61-139">To create a network region</span></span>

1.  <span data-ttu-id="27a61-140">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="27a61-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="27a61-141">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="27a61-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="27a61-142">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="27a61-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="27a61-143">Klicken Sie auf der Seite **Region** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="27a61-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="27a61-144">Geben Sie auf der Seite **Neue Region** einen Wert in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="27a61-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="27a61-145">Dieser Wert muss innerhalb Ihrer Skype für Business Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="27a61-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="27a61-146">Wählen Sie aus der Dropdownliste **zentraler Standort** den zentralen Standort für diese netzwerkregion aus.</span><span class="sxs-lookup"><span data-stu-id="27a61-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="27a61-147">Das Kontrollkästchen **Aktivieren audio alternativen Pfad** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="27a61-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="27a61-148">Dieses Feld bestimmt, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="27a61-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="27a61-149">Deaktivieren Sie dieses Kontrollkästchen, wenn Sie die Verschiebung an das Internet deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="27a61-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="27a61-150">Wenn Ihre Anrufe Anrufe über das Internet ist, muss dieses Kontrollkästchen aktiviert, unabhängig von den bandbreiteneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="27a61-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="27a61-151">Das Kontrollkästchen **Aktivieren video alternativen Pfad** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="27a61-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="27a61-152">Dieses Feld bestimmt, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="27a61-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="27a61-153">Deaktivieren Sie dieses Kontrollkästchen, wenn Sie die Verschiebung an das Internet deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="27a61-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="27a61-154">Wenn Ihre Anrufe Anrufe über das Internet ist, muss dieses Kontrollkästchen aktiviert, unabhängig von den bandbreiteneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="27a61-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="27a61-155">(Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu dieser Region bereitzustellen, die durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="27a61-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="27a61-156">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="27a61-156">Click **Commit**.</span></span>

<span data-ttu-id="27a61-157">Die **zugeordnete Sites** -Tabelle wird nicht für die Erstellung einer netzwerkregion verwendet.</span><span class="sxs-lookup"><span data-stu-id="27a61-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="27a61-158">Ordnen Sie eine Website einen Bereich beim Erstellen oder ändern die Website.</span><span class="sxs-lookup"><span data-stu-id="27a61-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="27a61-159">Weitere Informationen hierzu finden Sie unter [Verwalten der anrufsteuerung für Websites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="27a61-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="27a61-160">So ändern Sie eine netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="27a61-160">To modify a network region</span></span>

1.  <span data-ttu-id="27a61-161">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="27a61-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="27a61-162">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="27a61-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="27a61-163">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="27a61-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="27a61-164">Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="27a61-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="27a61-165">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="27a61-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="27a61-166">Klicken Sie auf der Seite **Region bearbeiten** können Sie die Einstellungen ändern, zum Aktivieren und Deaktivieren von Audio und Video alternative Pfade, und ändern Sie die Beschreibung (Informationen hierzu finden Sie im Abschnitt "So erstellen eine netzwerkregion" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="27a61-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="27a61-167">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="27a61-167">Click **Commit**.</span></span>

<span data-ttu-id="27a61-168">Die **zugeordnete Websites** auf dieser Seite können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="27a61-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="27a61-169">Die Liste der zugehörigen Websites ist für Verweis bereitgestellt, sodass Sie welche Websites betroffen sind kennen, wenn Sie die regionseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="27a61-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="27a61-170">Löschen von vorhandenen netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="27a61-170">Delete existing network regions</span></span> 

<span data-ttu-id="27a61-171">Eine netzwerkregion sind die verschiedenen Teile eines Netzwerks über mehrere geografische Bereiche.</span><span class="sxs-lookup"><span data-stu-id="27a61-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="27a61-172">Jeder netzwerkregion muss mit einem zentralen Standort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="27a61-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="27a61-173">Am zentrale Standort ist der Data Center-Website auf dem Call Admission Control (, CAC)-bandbreitenrichtliniendienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="27a61-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="27a61-174">Die Skype Business Server-Systemsteuerung können Sie netzwerkregionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="27a61-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="27a61-175">Netzwerkregionen umfassen Einstellungen, die bestimmen, ob alternative Pfade über das Internet für Audio- und videoverbindungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="27a61-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="27a61-176">Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregion.</span><span class="sxs-lookup"><span data-stu-id="27a61-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="27a61-177">Verwenden Sie in diesem Thema, um vorhandene netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="27a61-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="27a61-178">So löschen Sie eine netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="27a61-178">To delete a network region</span></span>

1.  <span data-ttu-id="27a61-179">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="27a61-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="27a61-180">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="27a61-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="27a61-181">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="27a61-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="27a61-182">Klicken Sie auf der Seite **Region** auf die Region, den, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="27a61-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="27a61-183">Sie können mehrere Regionen zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="27a61-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="27a61-184">Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Regionen aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="27a61-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="27a61-185">Oder, um alle Bereiche ausgewählt haben, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="27a61-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="27a61-186">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="27a61-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="27a61-187">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="27a61-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="27a61-188">Eine netzwerkregion kann nicht entfernt werden, wenn sie einen Netzwerkstandort zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="27a61-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="27a61-189">Wenn Sie versuchen, einen Bereich einer Website zugeordnet zu entfernen, erhalten Sie eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27a61-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="27a61-190">Um herauszufinden, ob ein Bereich alle Websites zugeordnet ist, wählen Sie die Region, und klicken Sie dann im Menü **Bearbeiten** auf **Details anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="27a61-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="27a61-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27a61-191">See Also</span></span>

[<span data-ttu-id="27a61-192">Verwalten von netzwerkregionsrouten</span><span class="sxs-lookup"><span data-stu-id="27a61-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="27a61-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="27a61-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="27a61-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="27a61-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="27a61-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="27a61-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="27a61-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="27a61-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  

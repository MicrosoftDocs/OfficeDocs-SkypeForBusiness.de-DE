---
title: Verwalten von Netzwerk-bandbreitenrichtlinienprofilen
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen, erstellen, ändern oder Löschen von Netzwerk-bandbreitenrichtlinienprofilen.
ms.openlocfilehash: 58a73774a55a64ac6cb81f0bdf887eb0d1493a35
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222940"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="07526-103">Verwalten von Netzwerk-bandbreitenrichtlinienprofilen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="07526-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="07526-104">Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen, erstellen, ändern oder Löschen von Netzwerk-bandbreitenrichtlinienprofilen.</span><span class="sxs-lookup"><span data-stu-id="07526-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="07526-105">Netzwerkbandbreite Richtlinie Profilinformationen anzeigen</span><span class="sxs-lookup"><span data-stu-id="07526-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="07526-106">Im Rahmen der anrufsteuerung (CAC) wird eine bandbreitenrichtlinie bandbreiteneinschränkungen für bestimmte Modalitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="07526-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="07526-107">In Skype für Business Server können nur Audio- und Videodaten Modalitäten Netzwerkbandbreite ist eingeschränkt zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="07526-108">Sie können allgemeine Netzwerkbandbreite ist eingeschränkt und Sitzung Einschränkungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="07526-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="07526-109">Die Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder Löschen eines Profils Container für diese Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="07526-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="07526-110">Jede bandbreitenrichtlinienprofil kann eine oder mehrere Netzwerkstandorte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="07526-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="07526-111">Verwenden Sie die folgenden Verfahren, um ein bandbreitenrichtlinienprofil anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="07526-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="07526-112">So zeigen Sie ein bandbreitenrichtlinienprofil an</span><span class="sxs-lookup"><span data-stu-id="07526-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="07526-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="07526-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07526-114">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="07526-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07526-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="07526-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="07526-116">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="07526-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="07526-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="07526-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07526-118">Anzeigen der Netzwerk-Bandbreite Profil Richtlinieninformationen mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="07526-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="07526-119">Netzwerkbandbreite Profile können mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkBandwidthPolicyProfile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07526-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="07526-120">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="07526-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="07526-121">So zeigen Sie Netzwerkbandbreite Richtlinie Profilinformationen an</span><span class="sxs-lookup"><span data-stu-id="07526-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="07526-122">Um Informationen über alle Ihre Richtlinienprofile anzuzeigen, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="07526-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="07526-123">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="07526-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="07526-124">Weitere Informationen finden Sie im Hilfethema zum [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="07526-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="07526-125">Erstellen oder Ändern von bandbreitenrichtlinienprofilen</span><span class="sxs-lookup"><span data-stu-id="07526-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="07526-126">Im Rahmen der anrufsteuerung (CAC) wird eine bandbreitenrichtlinie bandbreiteneinschränkungen für bestimmte Modalitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="07526-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="07526-127">In Skype für Business Server können nur Audio- und Videodaten Modalitäten Netzwerkbandbreite ist eingeschränkt zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="07526-128">Sie können allgemeine Netzwerkbandbreite ist eingeschränkt und Sitzung Einschränkungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="07526-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="07526-129">Die Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder Löschen eines Profils Container für diese Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="07526-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="07526-130">Jede bandbreitenrichtlinienprofil kann eine oder mehrere Netzwerkstandorte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="07526-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="07526-131">Verwenden Sie die folgenden Verfahren zum Erstellen oder ändern ein bandbreitenrichtlinienprofil.</span><span class="sxs-lookup"><span data-stu-id="07526-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="07526-132">Erstellen Sie ein neues bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="07526-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="07526-133">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="07526-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07526-134">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="07526-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07526-135">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="07526-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="07526-136">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="07526-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="07526-137">Geben Sie im **Neuen Bandbreitenrichtlinienprofil**in das Feld **Name** einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="07526-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="07526-138">Dieser Name muss für alle bandbreitenrichtlinienprofile eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="07526-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="07526-139">Geben Sie im Feld **audiolimit** einen numerischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="07526-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="07526-140">Dieser Wert ist die maximale Bandbreite für alle audioverbindungen, ausgedrückt in Kbit/s zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="07526-141">Geben Sie einen numerischen Wert im Feld **Grenzwert für audiositzung** .</span><span class="sxs-lookup"><span data-stu-id="07526-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="07526-142">Dieser Wert ist die maximale Bandbreite für eine einzelne audio Verbindung, ausgedrückt in Kbit/s zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="07526-143">Dieser Wert muss es sich um 40 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="07526-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="07526-144">Geben Sie einen numerischen Wert im Feld **videolimit** .</span><span class="sxs-lookup"><span data-stu-id="07526-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="07526-145">Dieser Wert ist die maximale Bandbreite für alle videoverbindungen, ausgedrückt in Kbit/s zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="07526-146">Geben Sie einen numerischen Wert im Feld **Grenzwert für videositzung** .</span><span class="sxs-lookup"><span data-stu-id="07526-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="07526-147">Dieser Wert ist die maximale Bandbreite für eine einzelne video Verbindung, ausgedrückt in Kbit/s zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="07526-148">Dieser Wert muss 100 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="07526-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="07526-149">(Optional) Geben Sie einen Wert im Feld **Beschreibung** ein, um weitere Informationen zu diesem bandbreitenrichtlinienprofil bereitzustellen, die durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="07526-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="07526-150">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="07526-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="07526-151">Erstellen ein neues bandbreitenrichtlinienprofil erzwingt nicht automatisch Bandbreite Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="07526-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="07526-152">Sie müssen zuerst das Richtlinienprofil einer Website zuordnen.</span><span class="sxs-lookup"><span data-stu-id="07526-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="07526-153">So ändern Sie ein bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="07526-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="07526-154">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="07526-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07526-155">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="07526-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07526-156">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="07526-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="07526-157">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="07526-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="07526-158">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="07526-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="07526-159">Ändern Sie auf der Seite **Bandbreitenrichtlinienprofil bearbeiten** die Felder nach Bedarf (Weitere Informationen hierzu finden Sie unter [So erstellen Sie ein neues bandbreitenrichtlinienprofil](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="07526-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="07526-160">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="07526-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="07526-161">Wenn Sie das bandbreitenrichtlinienprofil ändern, werden die bandbreiteneinschränkungen aller Netzwerkstandorte, die diesem bandbreitenrichtlinienprofil zugeordnet unmittelbar aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="07526-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="07526-162">Löschen von Netzwerk-bandbreitenrichtlinienprofilen</span><span class="sxs-lookup"><span data-stu-id="07526-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="07526-163">Im Rahmen der anrufsteuerung (CAC) wird eine bandbreitenrichtlinie bandbreiteneinschränkungen für bestimmte Modalitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="07526-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="07526-164">In Skype für Business Server können nur Audio- und Videodaten Modalitäten Netzwerkbandbreite ist eingeschränkt zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07526-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="07526-165">Sie können allgemeine Netzwerkbandbreite ist eingeschränkt und Sitzung Einschränkungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="07526-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="07526-166">Die Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder Löschen eines Profils Container für diese Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="07526-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="07526-167">Verwenden Sie die folgenden Verfahren, um ein Netzwerk-bandbreitenrichtlinienprofilen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="07526-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="07526-168">So löschen Sie ein bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="07526-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="07526-169">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="07526-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07526-170">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="07526-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07526-171">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="07526-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="07526-172">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="07526-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="07526-173">Sie können mehr als ein Profil zu einem Zeitpunkt löschen.</span><span class="sxs-lookup"><span data-stu-id="07526-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="07526-174">Zu diesem Zweck, drücken Sie STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Profile aus.</span><span class="sxs-lookup"><span data-stu-id="07526-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="07526-175">Oder, um alle Profile ausgewählt haben, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="07526-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="07526-176">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="07526-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="07526-177">Ein bandbreitenrichtlinienprofil, das einem Netzwerkstandort zugeordnet ist, kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="07526-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="07526-178">Bevor Sie das Profil löschen können, müssen Sie zuerst die Zuordnung mit den Netzwerkstandort entfernen.</span><span class="sxs-lookup"><span data-stu-id="07526-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="07526-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07526-179">See Also</span></span>

[<span data-ttu-id="07526-180">Verwalten der anrufsteuerung für Standorte</span><span class="sxs-lookup"><span data-stu-id="07526-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="07526-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="07526-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="07526-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="07526-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="07526-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="07526-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="07526-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="07526-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  


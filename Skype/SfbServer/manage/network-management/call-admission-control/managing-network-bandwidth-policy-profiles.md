---
title: Verwalten von Netzwerkbandbreite-Richtlinienprofilen
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
description: Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um Netzwerkbandbreite-Richtlinienprofile anzuzeigen, zu erstellen, zu ändern oder zu löschen.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817504"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="3ab1d-103">Verwalten von Richtlinienprofilen für die Netzwerkbandbreite in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3ab1d-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="3ab1d-104">Verwenden Sie die in diesem Artikel beschriebenen Verfahren, um Netzwerkbandbreite-Richtlinienprofile anzuzeigen, zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="3ab1d-105">Profilinformationen zu Netzwerkbandbreite-Richtlinien anzeigen</span><span class="sxs-lookup"><span data-stu-id="3ab1d-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="3ab1d-106">Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="3ab1d-107">In Skype for Business Server können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="3ab1d-108">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="3ab1d-109">Sie können das Skype for Business Server Control Panel verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="3ab1d-110">Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="3ab1d-111">Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="3ab1d-112">So zeigen Sie ein bandbreitenrichtlinienprofil an</span><span class="sxs-lookup"><span data-stu-id="3ab1d-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="3ab1d-113">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ab1d-114">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3ab1d-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="3ab1d-116">Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="3ab1d-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3ab1d-118">Anzeigen von Profilinformationen für die Netzwerkbandbreite mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3ab1d-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3ab1d-119">Netzwerkbandbreiten Profile können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkBandwidthPolicyProfile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="3ab1d-120">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="3ab1d-121">So zeigen Sie Profilinformationen zu Netzwerkbandbreiten an</span><span class="sxs-lookup"><span data-stu-id="3ab1d-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="3ab1d-122">Wenn Sie Informationen zu allen Netzwerkbandbreite-Richtlinienprofilen anzeigen möchten, geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="3ab1d-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="3ab1d-123">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="3ab1d-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="3ab1d-124">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="3ab1d-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="3ab1d-125">Erstellen oder Ändern von Bandbreitenrichtlinien Profilen</span><span class="sxs-lookup"><span data-stu-id="3ab1d-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="3ab1d-126">Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="3ab1d-127">In Skype for Business Server können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="3ab1d-128">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="3ab1d-129">Sie können das Skype for Business Server Control Panel verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="3ab1d-130">Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="3ab1d-131">Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="3ab1d-132">So erstellen Sie ein neues bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="3ab1d-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="3ab1d-133">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ab1d-134">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3ab1d-135">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="3ab1d-136">Klicken Sie auf der Seite mit den **Bandbreitenrichtlinien** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="3ab1d-137">Geben Sie in **Neues bandbreitenrichtlinienprofil**einen Namen in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="3ab1d-138">Dieser Name muss unter allen Bandbreitenrichtlinien Profilen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="3ab1d-139">Geben Sie im Feld **audiogrenze** einen numerischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="3ab1d-140">Dieser Wert ist die maximale Bandbreite, die für alle Audioverbindungen reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="3ab1d-141">Geben Sie einen numerischen Wert in das Feld " **audiositzungs Limit** " ein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="3ab1d-142">Dieser Wert ist die maximale Bandbreite, die für eine einzelne Audioverbindung reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="3ab1d-143">Dieser Wert muss 40 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="3ab1d-144">Geben Sie einen numerischen Wert in das Feld **Video Grenzwert** ein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="3ab1d-145">Dieser Wert ist die maximale Bandbreite, die für alle Videoverbindungen reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="3ab1d-146">Geben Sie einen numerischen Wert in das Feld **Video Session Limit** ein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="3ab1d-147">Dieser Wert ist die maximale Bandbreite, die für eine einzelne Videoverbindung reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="3ab1d-148">Dieser Wert muss 100 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="3ab1d-149">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu diesem bandbreitenrichtlinienprofil bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="3ab1d-150">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3ab1d-151">Durch das Erstellen eines neuen bandbreitenrichtlinienprofils werden keine Bandbreiteneinschränkungen automatisch erzwungen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="3ab1d-152">Sie müssen zuerst das Richtlinienprofil einer Website zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="3ab1d-153">So ändern Sie ein bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="3ab1d-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="3ab1d-154">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ab1d-155">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3ab1d-156">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="3ab1d-157">Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="3ab1d-158">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3ab1d-159">Ändern Sie auf der Seite **bandbreitenrichtlinienprofil bearbeiten** die Felder nach Bedarf (Details finden Sie unter so wird es gemacht: [Erstellen eines neuen bandbreitenrichtlinienprofils](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="3ab1d-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="3ab1d-160">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3ab1d-161">Wenn Sie das bandbreitenrichtlinienprofil ändern, werden die Bandbreiteneinschränkungen für alle Netzwerk Websites, die diesem bandbreitenrichtlinienprofil zugeordnet sind, sofort aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="3ab1d-162">Löschen von Netzwerkbandbreite-Richtlinienprofilen</span><span class="sxs-lookup"><span data-stu-id="3ab1d-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="3ab1d-163">Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="3ab1d-164">In Skype for Business Server können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="3ab1d-165">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="3ab1d-166">Sie können das Skype for Business Server Control Panel verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="3ab1d-167">Gehen Sie wie folgt vor, um ein Netzwerkband breiten Richtlinienprofil zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="3ab1d-168">So löschen Sie ein bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="3ab1d-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="3ab1d-169">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3ab1d-170">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3ab1d-171">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="3ab1d-172">Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3ab1d-173">Sie können mehr als ein Profil gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="3ab1d-174">Drücken Sie dazu STRG, und wählen Sie mehrere Profile aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="3ab1d-175">Wenn Sie alle Profile auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alles auswählen** .</span><span class="sxs-lookup"><span data-stu-id="3ab1d-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="3ab1d-176">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="3ab1d-177">Sie können ein bandbreitenrichtlinienprofil, das einer Netzwerk Website zugeordnet ist, nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="3ab1d-178">Sie müssen zuerst die Zuordnung zur Netzwerk Website entfernen, bevor Sie das Profil löschen können.</span><span class="sxs-lookup"><span data-stu-id="3ab1d-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="3ab1d-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ab1d-179">See Also</span></span>

[<span data-ttu-id="3ab1d-180">Verwalten der Anrufsteuerung für Websites</span><span class="sxs-lookup"><span data-stu-id="3ab1d-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="3ab1d-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3ab1d-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="3ab1d-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3ab1d-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="3ab1d-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3ab1d-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="3ab1d-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3ab1d-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  


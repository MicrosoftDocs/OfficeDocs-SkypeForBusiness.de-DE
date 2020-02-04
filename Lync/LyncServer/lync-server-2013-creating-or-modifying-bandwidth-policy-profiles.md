---
title: 'Lync Server 2013: Erstellen oder Ändern von Bandbreitenrichtlinien Profilen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="3d90a-102">Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d90a-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d90a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="3d90a-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="3d90a-104">Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="3d90a-105">In Microsoft lync Server 2013 können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3d90a-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="3d90a-106">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="3d90a-107">Sie können die lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="3d90a-108">Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="3d90a-109">Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3d90a-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="3d90a-110">Informationen zum Löschen eines bandbreitenrichtlinienprofils finden Sie unter [Löschen von Netzwerkbandbreite-Richtlinienprofilen in lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3d90a-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="3d90a-111">So erstellen Sie ein neues bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="3d90a-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="3d90a-112">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3d90a-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d90a-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d90a-114">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3d90a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3d90a-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3d90a-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="3d90a-116">Klicken Sie auf der Seite mit den **Bandbreitenrichtlinien** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="3d90a-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="3d90a-117">Geben Sie in **Neues bandbreitenrichtlinienprofil**einen Namen in das Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="3d90a-118">Dieser Name muss unter allen Bandbreitenrichtlinien Profilen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="3d90a-119">Geben Sie im Feld **audiogrenze** einen numerischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="3d90a-120">Dieser Wert ist die maximale Bandbreite, die für alle Audioverbindungen reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3d90a-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="3d90a-121">Geben Sie einen numerischen Wert in das Feld " **audiositzungs Limit** " ein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="3d90a-122">Dieser Wert ist die maximale Bandbreite, die für eine einzelne Audioverbindung reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3d90a-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="3d90a-123">Dieser Wert muss 40 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="3d90a-124">Geben Sie einen numerischen Wert in das Feld **Video Grenzwert** ein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="3d90a-125">Dieser Wert ist die maximale Bandbreite, die für alle Videoverbindungen reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3d90a-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="3d90a-126">Geben Sie einen numerischen Wert in das Feld **Video Session Limit** ein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="3d90a-127">Dieser Wert ist die maximale Bandbreite, die für eine einzelne Videoverbindung reserviert werden soll, ausgedrückt in Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="3d90a-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="3d90a-128">Dieser Wert muss 100 oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="3d90a-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="3d90a-129">Optional Geben Sie im Feld **Beschreibung** einen Wert ein, um weitere Informationen zu diesem bandbreitenrichtlinienprofil bereitzustellen, die nicht allein durch den Namen ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="3d90a-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="3d90a-130">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3d90a-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d90a-131">Durch das Erstellen eines neuen bandbreitenrichtlinienprofils werden keine Bandbreiteneinschränkungen automatisch erzwungen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="3d90a-132">Sie müssen zuerst das Richtlinienprofil einer Website zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="3d90a-133">Details zum Zuordnen eines Richtlinienprofils zu einer Website finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">erstellen oder Ändern von Netzwerk Websites in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d90a-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="3d90a-134">So ändern Sie ein bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="3d90a-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="3d90a-135">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="3d90a-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d90a-136">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d90a-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d90a-137">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3d90a-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3d90a-138">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3d90a-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="3d90a-139">Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3d90a-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="3d90a-140">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3d90a-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3d90a-141">Ändern Sie auf der Seite **bandbreitenrichtlinienprofil bearbeiten** die Felder nach Bedarf (Details finden Sie im Abschnitt "So erstellen Sie ein bandbreitenrichtlinienprofil" weiter oben in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="3d90a-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="3d90a-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3d90a-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d90a-143">Wenn Sie das bandbreitenrichtlinienprofil ändern, werden die Bandbreiteneinschränkungen für alle Netzwerk Websites, die diesem bandbreitenrichtlinienprofil zugeordnet sind, sofort aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3d90a-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d90a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d90a-144">See Also</span></span>


[<span data-ttu-id="3d90a-145">Löschen von Netzwerkbandbreite-Richtlinienprofilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d90a-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="3d90a-146">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d90a-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="3d90a-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3d90a-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="3d90a-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3d90a-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="3d90a-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3d90a-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


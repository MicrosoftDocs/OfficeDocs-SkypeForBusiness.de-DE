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
ms.openlocfilehash: e884a564859396dab19ad8b18c6cf33a54a626e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="67ac1-102">Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ac1-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67ac1-103">_**Letztes Änderungsstand des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="67ac1-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="67ac1-104">Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="67ac1-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="67ac1-105">In Microsoft lync Server 2013 können nur Audio-und Video Modalitäten Bandbreiteneinschränkungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="67ac1-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="67ac1-106">Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="67ac1-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="67ac1-107">Sie können das lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="67ac1-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="67ac1-108">Jedes Bandbreitenrichtlinienprofil kann mindestens einem Netzwerkstandort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="67ac1-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="67ac1-109">Erstellen oder ändern Sie mithilfe der folgenden Verfahren ein Bandbreitenrichtlinienprofil.</span><span class="sxs-lookup"><span data-stu-id="67ac1-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="67ac1-110">Informationen zum Löschen eines bandbreitenrichtlinienprofils finden Sie unter [Löschen von Richtlinienprofilen für die Netzwerkbandbreite in lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="67ac1-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="67ac1-111">So erstellen Sie ein neues Bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="67ac1-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="67ac1-112">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="67ac1-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67ac1-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67ac1-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67ac1-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="67ac1-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67ac1-115">Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="67ac1-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="67ac1-116">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="67ac1-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="67ac1-p103">Geben Sie im Abschnitt **Neues Bandbreitenrichtlinienprofil** im Feld **Name** einen Namen ein. Dieser Name muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="67ac1-p103">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="67ac1-p104">Geben Sie im Feld **Audiolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Audioverbindungen in KBit/s fest.</span><span class="sxs-lookup"><span data-stu-id="67ac1-p104">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="67ac1-p105">Geben Sie im Feld **Audiositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Audioverbindung in KBit/s fest. Dieser Wert muss auf mindestens 40 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="67ac1-p105">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="67ac1-p106">Geben Sie im Feld **Videolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Videoverbindungen in KBit/s fest.</span><span class="sxs-lookup"><span data-stu-id="67ac1-p106">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="67ac1-p107">Geben Sie im Feld **Videositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Videoverbindung in KBit/s fest. Dieser Wert muss auf mindestens 100 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="67ac1-p107">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="67ac1-129">(Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Bandbreitenrichtlinienprofil ein, die nicht durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="67ac1-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="67ac1-130">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="67ac1-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67ac1-131">Beim Erstellen eines neuen Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen nicht automatisch erzwungen.</span><span class="sxs-lookup"><span data-stu-id="67ac1-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="67ac1-132">Sie müssen das Richtlinienprofil zunächst einem Standort zuordnen.</span><span class="sxs-lookup"><span data-stu-id="67ac1-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="67ac1-133">Ausführliche Informationen zum Zuordnen eines Richtlinienprofils zu einer Website finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">erstellen oder Ändern von Netzwerkstandorten in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="67ac1-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="67ac1-134">So ändern Sie ein Bandbreitenrichtlinienprofil</span><span class="sxs-lookup"><span data-stu-id="67ac1-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="67ac1-135">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="67ac1-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67ac1-136">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67ac1-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67ac1-137">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="67ac1-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67ac1-138">Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="67ac1-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="67ac1-139">Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Bandbreitenrichtlinienprofil, das geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="67ac1-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="67ac1-140">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="67ac1-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="67ac1-141">Ändern Sie auf der Seite **Bandbreitenrichtlinienprofil bearbeiten** die gewünschten Felder (ausführliche Informationen finden Sie im Abschnitt "So erstellen Sie ein neues Bandbreitenrichtlinienprofil" weiter oben in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="67ac1-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="67ac1-142">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="67ac1-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67ac1-143">Beim Ändern des Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen aller Netzwerkstandorte, die diesem Bandbreitenrichtlinienprofil zugeordnet sind, umgehend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="67ac1-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67ac1-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67ac1-144">See Also</span></span>


[<span data-ttu-id="67ac1-145">Löschen von Richtlinienprofilen für Netzwerkbandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ac1-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="67ac1-146">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ac1-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="67ac1-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="67ac1-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="67ac1-148">Gruppe-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="67ac1-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="67ac1-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="67ac1-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


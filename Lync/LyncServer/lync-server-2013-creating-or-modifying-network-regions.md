---
title: 'Lync Server 2013: Erstellen oder Ändern von netzwerkregionen'
description: 'Lync Server 2013: Erstellen oder Ändern von netzwerkregionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02a041272f0df27d2133ca26096caeb01816c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544031"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="a90e7-103">Erstellen oder Ändern von netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a90e7-103">Creating or modifying network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a90e7-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a90e7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a90e7-105">Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt.</span><span class="sxs-lookup"><span data-stu-id="a90e7-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a90e7-106">Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="a90e7-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="a90e7-107">Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a90e7-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="a90e7-108">Sie können lync Server-Systemsteuerung zum Konfigurieren von netzwerkregionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a90e7-108">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="a90e7-109">Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a90e7-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="a90e7-110">Im lync Server-Systemsteuerung können Sie eine netzwerkregion erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="a90e7-110">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="a90e7-111">Verwenden Sie dieses Thema zum Erstellen und Ändern von Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="a90e7-111">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="a90e7-112">Ausführliche Informationen zum Löschen vorhandener netzwerkregionen finden Sie unter [Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="a90e7-112">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="a90e7-113">So erstellen Sie eine Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="a90e7-113">To create a network region</span></span>

1.  <span data-ttu-id="a90e7-114">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a90e7-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a90e7-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a90e7-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a90e7-116">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a90e7-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a90e7-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="a90e7-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="a90e7-118">Klicken Sie auf der Seite **Region** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a90e7-118">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="a90e7-119">Geben Sie auf der Seite **Neue Region** im Feld **Name** einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="a90e7-119">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="a90e7-120">Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="a90e7-120">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="a90e7-121">Wählen Sie in der Dropdownliste **Zentraler Standort** den zentralen Standort für diese Netzwerkregion aus.</span><span class="sxs-lookup"><span data-stu-id="a90e7-121">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="a90e7-p104">Das Kontrollkästchen **Alternativen Audiopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="a90e7-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="a90e7-p105">Das Kontrollkästchen **Alternativen Videopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="a90e7-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="a90e7-130">(Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu dieser Region ein, die nicht durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="a90e7-130">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="a90e7-131">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a90e7-131">Click **Commit**.</span></span>

<span data-ttu-id="a90e7-132">Die Tabelle **Zugeordnete Standorte** wird zum Erstellen einer Netzwerkregion nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a90e7-132">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="a90e7-133">Sie ordnen einer Region einen Standort zu, wenn Sie den Standort erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="a90e7-133">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="a90e7-134">Ausführliche Informationen finden Sie unter [erstellen oder Ändern von Netzwerkstandorten in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="a90e7-134">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="a90e7-135">So ändern Sie eine Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="a90e7-135">To modify a network region</span></span>

1.  <span data-ttu-id="a90e7-136">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a90e7-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a90e7-137">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a90e7-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a90e7-138">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a90e7-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a90e7-139">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="a90e7-139">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="a90e7-140">Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="a90e7-140">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="a90e7-141">Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="a90e7-141">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a90e7-142">Auf der Seite **Region bearbeiten** können Sie die Einstellungen zum Aktivieren und Deaktivieren von alternativen Pfaden für Audio und Video ändern, und Sie können die Beschreibung bearbeiten (ausführliche Informationen finden Sie unter "So erstellen Sie eine Netzwerkregion" weiter oben in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="a90e7-142">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="a90e7-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a90e7-143">Click **Commit**.</span></span>

<span data-ttu-id="a90e7-p108">Sie können die Option **Zugeordnete Standorte** auf dieser Seite nicht ändern. Die Liste der zugeordneten Standorte wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Standorte sich die Änderung der Regioneneinstellungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a90e7-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a90e7-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a90e7-146">See Also</span></span>


[<span data-ttu-id="a90e7-147">Löschen vorhandener netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a90e7-147">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="a90e7-148">Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a90e7-148">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="a90e7-149">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a90e7-149">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="a90e7-150">Gruppe-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a90e7-150">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="a90e7-151">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a90e7-151">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="a90e7-152">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a90e7-152">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


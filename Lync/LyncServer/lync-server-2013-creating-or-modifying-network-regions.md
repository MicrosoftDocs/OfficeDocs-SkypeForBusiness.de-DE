---
title: 'Lync Server 2013: Erstellen oder Ändern von netzwerkregionen'
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
ms.openlocfilehash: 04f85e4546d8cfa3154c2fc5a87676ff0377795b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="f2177-102">Erstellen oder Ändern von netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2177-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2177-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f2177-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f2177-104">Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt.</span><span class="sxs-lookup"><span data-stu-id="f2177-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f2177-105">Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="f2177-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="f2177-106">Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2177-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="f2177-107">Sie können lync Server-Systemsteuerung zum Konfigurieren von netzwerkregionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2177-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="f2177-108">Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="f2177-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="f2177-109">Im lync Server-Systemsteuerung können Sie eine netzwerkregion erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="f2177-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="f2177-110">Verwenden Sie dieses Thema zum Erstellen und Ändern von Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="f2177-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="f2177-111">Ausführliche Informationen zum Löschen vorhandener netzwerkregionen finden Sie unter [Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="f2177-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="f2177-112">So erstellen Sie eine Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="f2177-112">To create a network region</span></span>

1.  <span data-ttu-id="f2177-113">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f2177-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2177-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2177-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2177-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f2177-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2177-116">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="f2177-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="f2177-117">Klicken Sie auf der Seite **Region** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="f2177-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="f2177-118">Geben Sie auf der Seite **Neue Region** im Feld **Name** einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="f2177-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="f2177-119">Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f2177-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="f2177-120">Wählen Sie in der Dropdownliste **Zentraler Standort** den zentralen Standort für diese Netzwerkregion aus.</span><span class="sxs-lookup"><span data-stu-id="f2177-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="f2177-p104">Das Kontrollkästchen **Alternativen Audiopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="f2177-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="f2177-p105">Das Kontrollkästchen **Alternativen Videopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="f2177-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="f2177-129">(Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu dieser Region ein, die nicht durch den Namen allein vermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="f2177-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f2177-130">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f2177-130">Click **Commit**.</span></span>

<span data-ttu-id="f2177-131">Die Tabelle **Zugeordnete Standorte** wird zum Erstellen einer Netzwerkregion nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2177-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="f2177-132">Sie ordnen einer Region einen Standort zu, wenn Sie den Standort erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="f2177-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="f2177-133">Ausführliche Informationen finden Sie unter [erstellen oder Ändern von Netzwerkstandorten in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="f2177-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="f2177-134">So ändern Sie eine Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="f2177-134">To modify a network region</span></span>

1.  <span data-ttu-id="f2177-135">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f2177-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2177-136">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2177-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2177-137">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f2177-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2177-138">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="f2177-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="f2177-139">Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f2177-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="f2177-140">Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="f2177-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f2177-141">Auf der Seite **Region bearbeiten** können Sie die Einstellungen zum Aktivieren und Deaktivieren von alternativen Pfaden für Audio und Video ändern, und Sie können die Beschreibung bearbeiten (ausführliche Informationen finden Sie unter "So erstellen Sie eine Netzwerkregion" weiter oben in diesem Thema).</span><span class="sxs-lookup"><span data-stu-id="f2177-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="f2177-142">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f2177-142">Click **Commit**.</span></span>

<span data-ttu-id="f2177-p108">Sie können die Option **Zugeordnete Standorte** auf dieser Seite nicht ändern. Die Liste der zugeordneten Standorte wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Standorte sich die Änderung der Regioneneinstellungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="f2177-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2177-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2177-145">See Also</span></span>


[<span data-ttu-id="f2177-146">Löschen vorhandener netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2177-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="f2177-147">Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2177-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="f2177-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2177-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="f2177-149">Gruppe-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2177-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="f2177-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2177-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="f2177-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f2177-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Aktivieren der Netzwerkmedien Umgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a269f22eabc294af45697ab1bd2c0eabe4b5aad6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ab3d9-102">Aktivieren der Netzwerkmedien Umgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3d9-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab3d9-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ab3d9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ab3d9-104">Die Einstellungen für die medienumgehung gelten global für eine Microsoft lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="ab3d9-105">Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="ab3d9-106">Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planning for Media Bypass in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt Planning.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="ab3d9-107">Sie können die medienumgehung im lync Server-Systemsteuerung aktivieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="ab3d9-108">So aktivieren und konfigurieren Sie die Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="ab3d9-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="ab3d9-109">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab3d9-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ab3d9-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ab3d9-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ab3d9-112">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="ab3d9-p103">Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".</span><span class="sxs-lookup"><span data-stu-id="ab3d9-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="ab3d9-115">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="ab3d9-116">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** auf das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="ab3d9-117">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ab3d9-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="ab3d9-118">**Immer umgehen**   wählen Sie diese Option aus, um die medienumgehung für alle Anrufe zu versuchen.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="ab3d9-119">Diese Option ist nicht verfügbar, wenn die Anrufsteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="ab3d9-120">Ist die Anrufsteuerung nicht aktiviert, wählen Sie diese Option in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="ab3d9-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="ab3d9-121">Es besteht keine Notwendigkeit zur Bandbreitensteuerung.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="ab3d9-122">Es ist keine fein abgestimmte Konfiguration erforderlich, mit der die Anforderung einer Medienumgehung erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="ab3d9-123">Zwischen Gateways und Clients ist vollständige Konnektivität gegeben.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="ab3d9-124">**Verwenden von Websites und Regions Konfiguration**   wenn die Anrufsteuerung aktiviert ist, ist diese Option standardmäßig aktiviert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="ab3d9-125">Ist diese Option ausgewählt, wird anhand der Standorte und Regionen in der Netzwerkkonfiguration ermittelt, ob eine Medienumgehung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="ab3d9-126">Wenn Sie diese Option auswählen, können Sie eine Umgehung für Standorte aktivieren, die nicht zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="ab3d9-127">Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die mit einer bestimmten Region verknüpft sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die mit derselben Region verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="ab3d9-128">Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die mit den Zweigstandorten verknüpften Subnetze angeben, statt sämtliche, mit allen Standorten verknüpfte Subnetze angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="ab3d9-129">Es wird empfohlen, das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte** nicht zu aktivieren, wenn die Anrufsteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="ab3d9-130">Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ab3d9-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab3d9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab3d9-131">See Also</span></span>


[<span data-ttu-id="ab3d9-132">Deaktivieren der Netzwerkmedien Umgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3d9-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="ab3d9-133">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3d9-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="ab3d9-134">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3d9-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


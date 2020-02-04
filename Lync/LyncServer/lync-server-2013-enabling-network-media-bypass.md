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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="bc566-102">Aktivieren der Netzwerkmedien Umgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc566-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc566-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bc566-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bc566-104">Medienumgehungseinstellungen gelten global für eine Microsoft lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="bc566-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="bc566-105">Die medienumgehung ermöglicht Anrufe, den Vermittlungs Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="bc566-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="bc566-106">Ausführliche Informationen zur Verwendung der medienumgehung finden Sie unter [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt Planung.</span><span class="sxs-lookup"><span data-stu-id="bc566-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="bc566-107">Sie können die medienumgehung in der lync Server-Systemsteuerung aktivieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bc566-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="bc566-108">So aktivieren und konfigurieren Sie die medienumgehung</span><span class="sxs-lookup"><span data-stu-id="bc566-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="bc566-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="bc566-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bc566-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bc566-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bc566-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bc566-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bc566-112">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="bc566-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="bc566-113">Klicken Sie auf der Seite **Global** auf die **globale** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bc566-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="bc566-114">Es gibt immer nur eine Konfiguration, und Sie wird immer als "Global" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bc566-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="bc566-115">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="bc566-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="bc566-116">Klicken Sie auf der Seite **globale Einstellungen bearbeiten** auf das Kontrollkästchen **medienumgehung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="bc566-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="bc566-117">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="bc566-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="bc566-118">**Immer umgehen**   wählen Sie diese Option aus, um bei allen Anrufen medienumgehung zu versuchen.</span><span class="sxs-lookup"><span data-stu-id="bc566-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="bc566-119">Diese Option steht nicht zur Verfügung, wenn die Anrufsteuerung (Call Admission Control, CAC) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bc566-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="bc566-120">Wenn CAC nicht aktiviert ist, wählen Sie diese Option in den folgenden Fällen aus:</span><span class="sxs-lookup"><span data-stu-id="bc566-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="bc566-121">Die Bandbreitensteuerung ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc566-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="bc566-122">Es besteht keine Notwendigkeit für eine fein abgestimmte Konfiguration, um festzustellen, wann eine Umgehung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="bc566-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="bc566-123">Es besteht eine vollständige Konnektivität zwischen Gateways und Clients.</span><span class="sxs-lookup"><span data-stu-id="bc566-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="bc566-124">**Verwenden von Websites und der Regions Konfiguration**   wenn CAC aktiviert ist, ist diese Option standardmäßig aktiviert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bc566-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="bc566-125">Wenn diese Option ausgewählt ist, werden Netzwerk Konfigurations Websites und-Regionen verwendet, um zu ermitteln, wann eine medienumgehung möglich ist.</span><span class="sxs-lookup"><span data-stu-id="bc566-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="bc566-126">Wenn Sie diese Option auswählen, können Sie die Umgehung für Websites aktivieren, die nicht zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bc566-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="bc566-127">Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Websites aktivieren** nur, wenn Sie über eine oder mehrere große Websites verfügen, die dem gleichen Bereich zugeordnet sind, die keine Bandbreiteneinschränkungen aufweisen (beispielsweise eine große zentrale Website), und Sie verfügen auch über einige Verzweigungs Websites, die dem gleichen Bereich zugeordnet sind, für den es keine Bandbreiteneinschränkungen gibt.</span><span class="sxs-lookup"><span data-stu-id="bc566-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="bc566-128">Wenn Sie die Umgehung für nicht zugeordnete Websites aktivieren, wird die Konfiguration optimiert, da Sie nur die Subnetze angeben, die den Zweigstellen zugeordnet sind, anstatt alle Subnetze anzugeben, die allen Websites zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bc566-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="bc566-129">Wir empfehlen, dass Sie das Kontrollkästchen **Bypass für nicht zugeordnete Websites aktivieren** nicht aktivieren, wenn CAC aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bc566-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="bc566-130">Klicken Sie auf **Commit** , um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bc566-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc566-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc566-131">See Also</span></span>


[<span data-ttu-id="bc566-132">Deaktivieren der Netzwerkmedien Umgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc566-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="bc566-133">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc566-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="bc566-134">Planung der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc566-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


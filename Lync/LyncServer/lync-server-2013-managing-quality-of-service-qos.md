---
title: 'Lync Server 2013: Verwalten der Dienstqualität (Quality of Service, QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b6661bb9e34db11099bc0f1a7526ba23792198
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="e87ff-102">Verwalten der Dienstqualität (Quality of Service, QoS) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e87ff-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e87ff-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="e87ff-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="e87ff-p101">Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird. QoS kommt am häufigsten in Netzwerken mit beschränkter Bandbreite zum Einsatz, bei denen eine große Anzahl Netzwerkpakete um eine relativ geringe Bandbreite konkurrieren, Die Dienstqualität stellt für Administratoren eine Möglichkeit dar, um Paketen mit Audio- oder Videodaten höhere Prioritäten zuzuweisen. Durch die Zuweisung einer höheren Priorität zu diesen Paketen kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen ausgeführt werden als Netzwerksitzungen, in denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen erfolgen. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e87ff-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e87ff-p102">In der Regel wird die Dienstqualität nur auf Kommunikationssitzungen innerhalb Ihres internen Netzwerks angewendet. Beim Implementieren von QoS konfigurieren Sie die Server und Router zwar für die Unterstützung der Paketmarkierung, Sie konfigurieren diese Geräte jedoch für die Unterstützung der Paketmarkierung auf eine bestimmte Art und Weise. Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird. Selbst wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass sie auf dieselbe Art und Weise wie der Dienst in Ihrem Netzwerk konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e87ff-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="e87ff-112">Für Microsoft lync Server 2013 ist keine Dienstqualität erforderlich. Wenn Sie QoS derzeit nicht verwenden, ist es nicht erforderlich, den Dienst vor der Installation von lync Server 2013 zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e87ff-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="e87ff-113">Wenn in Ihrem Netzwerk eine erhebliche Menge an Paketverlusten auftritt, empfiehlt es sich, dieses Problem zu beheben, indem Sie zusätzliche Bandbreite hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e87ff-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="e87ff-114">Wenn keine weitere Bandbreite hinzugefügt werden kann, sollten Sie stattdessen die Quality of Service implementieren.</span><span class="sxs-lookup"><span data-stu-id="e87ff-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="e87ff-115">Lync Server 2013 bietet eine umfassende Unterstützung für die Dienstqualität: Das bedeutet, dass Organisationen, die bereits QoS verwenden, problemlos lync Server in Ihre vorhandene Netzwerkinfrastruktur integrieren können.</span><span class="sxs-lookup"><span data-stu-id="e87ff-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="e87ff-116">Um dies zu tun, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="e87ff-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="e87ff-117">[Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="e87ff-118">Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e87ff-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="e87ff-119">Obwohl Sie lync Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, können Sie das Produkt in der Regel nicht zum Ändern der von diesen Geräten verwendeten DSCP-Codes verwenden.</span><span class="sxs-lookup"><span data-stu-id="e87ff-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="e87ff-120">[Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="e87ff-121">Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video.</span><span class="sxs-lookup"><span data-stu-id="e87ff-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="e87ff-122">Mit lync Server 2013 Sie die Dienstqualität nicht aktivieren oder deaktivieren, indem Sie beispielsweise einen Eigenschaftswert auf "true" oder "false" festlegen.</span><span class="sxs-lookup"><span data-stu-id="e87ff-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="e87ff-123">Stattdessen wird die Dienstqualität durch die Konfiguration von Portbereichen und die anschließende Erstellung und Anwendung einer Gruppenrichtlinie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e87ff-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="e87ff-124">Wenn Sie sich später dazu entschließen, QoS nicht zu verwenden, können Sie die Dienstqualität einfach durch Entfernen der entsprechenden Gruppenrichtlinienobjekte "deaktivieren".</span><span class="sxs-lookup"><span data-stu-id="e87ff-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="e87ff-125">[Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="e87ff-126">Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e87ff-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="e87ff-127">[Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="e87ff-128">Diese Portbereiche gelten nur für Clientcomputer und stimmen in der Regel nicht mit den auf Ihren Servern konfigurierten Portbereichen überein.</span><span class="sxs-lookup"><span data-stu-id="e87ff-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="e87ff-129">[Konfigurieren einer Dienst Qualitätsrichtlinie in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="e87ff-130">Mithilfe dieser Richtlinien werden die DSCP-Codes ermittelt, die auf verschiedene Pakettypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e87ff-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="e87ff-131">[Konfigurieren einer Dienst Qualitätsrichtlinie für Ihre a/V-Edgeserver in lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="e87ff-132">Dieser Vorgang sollte nur für die interne Seite Ihrer Edgeserver ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e87ff-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="e87ff-133">Die Ursache dafür ist, dass die Dienstqualität nicht für die Verwendung im Internet, sondern in Ihrem internen Netzwerk konzipiert ist.</span><span class="sxs-lookup"><span data-stu-id="e87ff-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="e87ff-134">[Konfigurieren von Quality of Service Policies in lync Server 2013 für Clients, die auf Windows 7 oder Windows 8 auszuführen](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)sind.</span><span class="sxs-lookup"><span data-stu-id="e87ff-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="e87ff-135">Beachten Sie, dass Microsoft lync Server 2013 QoS für andere Windows-Betriebssysteme wie Windows Vista oder Windows XP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e87ff-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="e87ff-136">[Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition Geräten in lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="e87ff-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="e87ff-137">Standardmäßig ist QoS für lync Phone Edition-Geräte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e87ff-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="e87ff-138">Sie können jedoch den DSCP-Standardwert ändern, um sicherzustellen, dass für alle Audiopakete in Ihrer Organisation derselbe DSCP-Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e87ff-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e87ff-139">Wenn Sie Microsoft Windows Server 2012 oder Windows Server 2012 R2 verwenden, interessieren Sie sich möglicherweise für die neuen Windows PowerShell-Cmdlets, die für die Verwaltung der Dienstqualität auf dieser Plattform zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e87ff-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="e87ff-140">Weitere Informationen finden Sie unter Network Quality of Service-Cmdlets in Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)unter.</span><span class="sxs-lookup"><span data-stu-id="e87ff-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


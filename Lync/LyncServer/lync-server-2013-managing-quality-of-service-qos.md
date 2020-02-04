---
title: 'Lync Server 2013: Verwalten von Quality of Service (QoS)'
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
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="6af6a-102">Verwalten von QoS (Quality of Service) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af6a-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af6a-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6af6a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6af6a-104">Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um ein optimales Endbenutzererlebnis für Audio-und Videokommunikation zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="6af6a-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="6af6a-105">QoS wird am häufigsten in Netzwerken verwendet, in denen die Bandbreite begrenzt ist: da eine große Anzahl von Netzwerkpaketen für einen relativ geringen Anteil an verfügbarer Bandbreite konkurrieren, bietet die Dienstqualität eine Möglichkeit für Administratoren, Paketen höhere Prioritäten zuzuweisen. Durchführen von Audio-oder Videodaten.</span><span class="sxs-lookup"><span data-stu-id="6af6a-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="6af6a-106">Wenn Sie diesen Paketen eine höhere Priorität geben, werden die Audio-und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechung abgeschlossen, als Netzwerksitzungen, die Dinge wie Dateiübertragungen, Webbrowser oder Datenbanksicherungen betreffen.</span><span class="sxs-lookup"><span data-stu-id="6af6a-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="6af6a-107">Das liegt daran, dass für Netzwerkpakete, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden, die Priorität "Best Effort" zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6af6a-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6af6a-108">In der Regel gilt die Dienstqualität nur für Kommunikationssitzungen in Ihrem internen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="6af6a-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="6af6a-109">Wenn Sie QoS implementieren, konfigurieren Sie Ihre Server und Router so, dass die Paket Kennzeichnung unterstützt wird. Sie können diese Geräte jedoch so konfigurieren, dass die Paket Kennzeichnung auf eine bestimmte Weise unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6af6a-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="6af6a-110">Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6af6a-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="6af6a-111">Auch wenn Quality wenn Service in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS auf die gleiche Weise konfiguriert wird, wie Sie den Dienst in Ihrem Netzwerk konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="6af6a-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="6af6a-112">Microsoft lync Server 2013 erfordert keine Dienstqualität; Wenn Sie derzeit keine QoS verwenden, müssen Sie den Dienst nicht installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="6af6a-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="6af6a-113">Wenn Sie eine beträchtliche Menge an Paketverlust in Ihrem Netzwerk erleben, empfiehlt es sich, dieses Problem zu beheben, indem Sie zusätzliche Bandbreite hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6af6a-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="6af6a-114">Wenn das Hinzufügen von mehr Bandbreite nicht möglich ist, sollten Sie stattdessen Quality of Service implementieren.</span><span class="sxs-lookup"><span data-stu-id="6af6a-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="6af6a-115">Lync Server 2013 bietet umfassende Unterstützung für die Dienstqualität: Dies bedeutet, dass Organisationen, die bereits QoS verwenden, lync Server problemlos in Ihre vorhandene Netzwerkinfrastruktur integrieren können.</span><span class="sxs-lookup"><span data-stu-id="6af6a-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="6af6a-116">Dazu müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="6af6a-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="6af6a-117">[Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="6af6a-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="6af6a-118">Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6af6a-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="6af6a-119">Obwohl Sie lync Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, können Sie das Produkt in der Regel nicht zum Ändern der DSCP-Codes verwenden, die von diesen Geräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6af6a-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="6af6a-120">[Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6af6a-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="6af6a-121">Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video.</span><span class="sxs-lookup"><span data-stu-id="6af6a-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="6af6a-122">Mit lync Server 2013 können Sie die Dienstqualität nicht aktivieren oder deaktivieren, indem Sie beispielsweise einen Eigenschaftswert auf "wahr" oder "falsch" festlegen.</span><span class="sxs-lookup"><span data-stu-id="6af6a-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="6af6a-123">Stattdessen aktivieren Sie die Dienstqualität, indem Sie Portbereiche konfigurieren und dann Gruppenrichtlinien erstellen und anwenden.</span><span class="sxs-lookup"><span data-stu-id="6af6a-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="6af6a-124">Wenn Sie sich später entschließen, QoS zu verwenden, können Sie die Qualität des Diensts einfach deaktivieren, indem Sie die entsprechenden Gruppenrichtlinienobjekte entfernen.</span><span class="sxs-lookup"><span data-stu-id="6af6a-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="6af6a-125">[Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)</span><span class="sxs-lookup"><span data-stu-id="6af6a-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="6af6a-126">Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die der anderen Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6af6a-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="6af6a-127">[Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)</span><span class="sxs-lookup"><span data-stu-id="6af6a-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="6af6a-128">Diese Portbereiche gelten nur für Clientcomputer und sind in der Regel nicht identisch mit den Portbereichen, die auf Ihren Servern konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="6af6a-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="6af6a-129">[Konfigurieren einer Quality of Service-Richtlinie in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6af6a-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="6af6a-130">Diese Richtlinien bestimmen die DSCP-Codes, die auf unterschiedliche Pakettypen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6af6a-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="6af6a-131">[Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver in lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)</span><span class="sxs-lookup"><span data-stu-id="6af6a-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="6af6a-132">Dies sollte nur für die interne Seite Ihrer Edgeserver erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6af6a-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="6af6a-133">Das liegt daran, dass Quality of Service für die Verwendung in Ihrem internen Netzwerk und nicht im Internet vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="6af6a-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="6af6a-134">[Konfigurieren von Dienst Qualitätsrichtlinien in lync Server 2013 für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)</span><span class="sxs-lookup"><span data-stu-id="6af6a-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="6af6a-135">Beachten Sie, dass Microsoft lync Server 2013 QoS für andere Windows-Betriebssysteme wie Windows Vista oder Windows XP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6af6a-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="6af6a-136">[Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition-Geräten in lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)</span><span class="sxs-lookup"><span data-stu-id="6af6a-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="6af6a-137">Standardmäßig ist QoS für lync Phone Edition-Geräte aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6af6a-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="6af6a-138">Möglicherweise möchten Sie jedoch den standardmäßigen DSCP-Wert ändern, um sicherzustellen, dass alle Audiopakete in Ihrer Organisation denselben DSCP-Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="6af6a-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6af6a-139">Wenn Sie Microsoft Windows Server 2012 oder Windows Server 2012 R2 verwenden, interessieren Sie sich möglicherweise für den neuen Satz von Windows PowerShell-Cmdlets, die für die Verwaltung der Dienstqualität auf dieser Plattform zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="6af6a-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="6af6a-140">Weitere Informationen finden Sie unter Network Quality of Service-Cmdlets in Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)unter.</span><span class="sxs-lookup"><span data-stu-id="6af6a-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


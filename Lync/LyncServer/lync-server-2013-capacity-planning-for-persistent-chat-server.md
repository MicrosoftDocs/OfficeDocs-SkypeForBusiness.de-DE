---
title: 'Lync Server 2013: Kapazitätsplanung für beständigen Chat Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="addb4-102">Kapazitätsplanung für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="addb4-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="addb4-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="addb4-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="addb4-104">Der beständige Chat Server kann mehr Benutzer-Echtzeitchats durchführen, die für zukünftiges abrufen und suchen beibehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="addb4-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="addb4-105">Im Gegensatz zu Gruppen-Sofortnachrichten (im), die im Postfach eines Benutzers gespeichert werden, wenn der Konversations Verlauf konfiguriert ist, bleibt eine dauerhafte Chat Server Sitzung länger geöffnet, und der Inhalt wird auf einem Server zusammen mit den Nachrichten, Dateien, URLs und anderen Daten gespeichert, die Teil einer laufende Unterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="addb4-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="addb4-106">Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung auf die Bereitstellung des beständigen Chat Servers.</span><span class="sxs-lookup"><span data-stu-id="addb4-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="addb4-107">Dieses Thema enthält Details zu unterstützten Topologien und Kapazitäts Planungstabellen für beständige Chat Server, mit denen Sie die beste Konfiguration für Ihre Bereitstellung ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="addb4-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="addb4-108">Darüber hinaus wird beschrieben, wie Sie die Bereitstellung beständiger Chat Server am besten verwalten, die zu Höchstzeiten eine größere Kapazität erfordern.</span><span class="sxs-lookup"><span data-stu-id="addb4-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="addb4-109">Informationen zum Herunterladen des [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)beständigen Chat Servers finden Sie unter "Microsoft lync Server 13-beständiger Chat Server" unter.</span><span class="sxs-lookup"><span data-stu-id="addb4-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="addb4-110">Details zum Installieren des beständigen Chat Servers finden Sie unter [Installieren des beständigen Chat Servers in lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) und [Konfigurieren des beständigen Chat Servers in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="addb4-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="addb4-111">Support Tools wie das lync Server-Planungs Tool können Sie bei der Kapazitätsplanung weiter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="addb4-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="addb4-112">Details zum Planungs Tool finden Sie unter [Starten des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="addb4-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="addb4-113">Unterstützte Topologien für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="addb4-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="addb4-114">Sie können den Server für beständigen Chat in Pools mit einem oder mehreren Servern und mit einer Topologie mit einem Pool oder mehreren Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="addb4-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="addb4-115">Wir unterstützen nun auch den Server für beständigen Chat auf dem Standard Edition-Server für neue lync Server 2013-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="addb4-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="addb4-116">Allerdings sind Leistung und Skalierbarkeit davon betroffen, und da es für diese neue Bereitstellung keine Option für die Hochverfügbarkeit gibt, erwarten wir, dass Sie diese in erster Linie zum Nachweis des Konzepts, der Evaluierung usw. verwenden.</span><span class="sxs-lookup"><span data-stu-id="addb4-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="addb4-117">Weitere Informationen zu beiden Topologien finden Sie unter <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planen des beständigen Chat Servers in lync Server 2013</A> in dieser Dokumentation und <A href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des beständigen Chat Servers in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="addb4-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="addb4-118">Topologie mit einem Server</span><span class="sxs-lookup"><span data-stu-id="addb4-118">Single-Server Topology</span></span>

<span data-ttu-id="addb4-119">Die Mindestkonfiguration und einfachste Bereitstellung für beständigen Chat Server ist eine einzelne Front-End-Server Topologie des beständigen Chat Servers.</span><span class="sxs-lookup"><span data-stu-id="addb4-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="addb4-120">Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der beständige Chat Server ausgeführt wird (wobei optional der Kompatibilitätsdienst ausgeführt wird, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server-Datenbank hostet, als auch die SQL Server-Datenbank zum Speichern des Kompatibilitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="addb4-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="addb4-121">Sie können einem beständigen Chat Serverpool, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="addb4-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="addb4-122">Wir empfehlen die Verwendung der Pooltopologie mit mehreren Servern, auch wenn Sie einen einzelnen Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="addb4-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="addb4-123">Dies ist so, dass Sie später weitere Server hinzufügen können, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="addb4-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="addb4-124">Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen beständigen Chat Server-Front-End-Server mit Compliance.</span><span class="sxs-lookup"><span data-stu-id="addb4-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="addb4-125">**Einzelner beständiger Chat Server**</span><span class="sxs-lookup"><span data-stu-id="addb4-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="addb4-126">![Topologie mit einem Server mit Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")</span><span class="sxs-lookup"><span data-stu-id="addb4-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="addb4-127">Topologie mit mehreren Servern</span><span class="sxs-lookup"><span data-stu-id="addb4-127">Multiple-Server Topology</span></span>

<span data-ttu-id="addb4-128">Um eine größere Kapazität und Zuverlässigkeit bereitzustellen, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planen des beständigen Chat Servers in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="addb4-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="addb4-129">Die Topologie mit mehreren Servern kann bis zu vier aktive Computer umfassen, auf denen der beständige Chat Server ausgeführt wird (für hoch Verfügbarkeits-und Disaster Recovery-Konfigurationen sind bis zu acht möglich, aber nur vier können aktiv sein und die restlichen vier im Standbymodus).</span><span class="sxs-lookup"><span data-stu-id="addb4-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="addb4-130">Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem beständigen Chat Serverpool mit 4 Servern verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="addb4-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="addb4-131">Eine Topologie mit mehreren Servern entspricht der Topologie mit einem Server, mit der Ausnahme, dass mehrere Server den persistenten Chat Server hosten und höher skalieren können.</span><span class="sxs-lookup"><span data-stu-id="addb4-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="addb4-132">Mehrere Computer, auf denen der beständige Chat Server ausgeführt wird, sollten sich in derselben Active Directory-Domänendienst Domäne wie lync Server und dem Kompatibilitätsdienst befinden.</span><span class="sxs-lookup"><span data-stu-id="addb4-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="addb4-133">Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der beständige Chat Server, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="addb4-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="addb4-134">**Mehrere beständige Chat Server**</span><span class="sxs-lookup"><span data-stu-id="addb4-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="addb4-135">![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")</span><span class="sxs-lookup"><span data-stu-id="addb4-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="addb4-136">In einer persistent Chat Server-Bereitstellung mit vier Servern, bei der 80.000-Benutzer gleichzeitig bei und mithilfe des beständigen Chats angemeldet werden können, wird die Auslastung gleichmäßig bei 20.000-Benutzern pro Server verteilt.</span><span class="sxs-lookup"><span data-stu-id="addb4-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="addb4-137">Wenn ein Server nicht mehr zur Verfügung steht, verlieren die Benutzer, die mit diesem Server verbunden sind, den Zugriff auf den beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="addb4-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="addb4-138">Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server wieder verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="addb4-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="addb4-139">Je nach dem Umfang des beständigen Chat-Datenverkehrs im Netzwerk kann diese Übertragung einige Minuten oder länger dauern.</span><span class="sxs-lookup"><span data-stu-id="addb4-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="addb4-140">Da jeder der verbleibenden Server möglicherweise so viele wie 30.000-Benutzer hostet, empfehlen wir, dass Sie den nicht verfügbaren Server so schnell wie möglich wiederherstellen, um Leistungsprobleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="addb4-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="addb4-141">Andernfalls können Sie einen anderen beständigen Chat Server mithilfe des Topologie-Generators oder des Windows PowerShell-Cmdlets, " **CsPersistentChatActiveServer**", verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="addb4-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="addb4-142">Kapazitätsplanung für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="addb4-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="addb4-143">Die folgenden Tabellen können Ihnen bei der Kapazitätsplanung für beständigen Chat Server helfen.</span><span class="sxs-lookup"><span data-stu-id="addb4-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="addb4-144">Sie modellieren, wie sich verschiedene Einstellungen für beständigen Chat Server auf die Kapazitäts Funktionen auswirken.</span><span class="sxs-lookup"><span data-stu-id="addb4-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="addb4-145">Planen der maximalen Kapazität für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="addb4-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="addb4-146">Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="addb4-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="addb4-147">Beispiel für beständigen Chat Server Pool mit maximaler Kapazität</span><span class="sxs-lookup"><span data-stu-id="addb4-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="addb4-148">Aktive persistent-Chat-Dienstinstanzen</span><span class="sxs-lookup"><span data-stu-id="addb4-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="addb4-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="addb4-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-150">Dienstinstanzen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="addb4-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="addb4-151"><em>8 (4 muss inaktiv sein; nur maximal 4 kann aktiv sein)</em></span><span class="sxs-lookup"><span data-stu-id="addb4-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-152">Aktive verbundene Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="addb4-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="addb4-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-154">Gesamtzahl der bereitgestellten Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="addb4-155">150,000</span><span class="sxs-lookup"><span data-stu-id="addb4-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-156">Anzahl der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="addb4-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="addb4-157">120,000</span><span class="sxs-lookup"><span data-stu-id="addb4-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="addb4-158">Im vorangehenden Beispiel soll der Plan die maximale Anzahl von Benutzern unterstützen, die der beständige Chat Server zulässt: vier Server/Instanzen des beständigen Chat Diensts (können vier weitere passive Server mit beständigem Chat Server für hohe Verfügbarkeit und Disaster Recovery) und 20.000-Benutzer pro Server für insgesamt 80.000 aktive Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="addb4-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="addb4-159">Kapazitätsplanung zum Verwalten des Zugriffs auf beständigen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="addb4-160">Die folgende Beispieltabelle kann Ihnen bei der Planung der Verwaltung des beständigen Chatrooms in einem Server Pool für beständigen Chat helfen.</span><span class="sxs-lookup"><span data-stu-id="addb4-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="addb4-161">Verwalten des Access-Beispiels für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="addb4-162">Kleine Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="addb4-163">Mittlere Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="addb4-164">Große Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="addb4-165">Gesamt</span><span class="sxs-lookup"><span data-stu-id="addb4-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="addb4-166">Größe der Chatrooms (Anzahl der verbundenen Benutzer)</span><span class="sxs-lookup"><span data-stu-id="addb4-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="addb4-167">30 pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="addb4-168">150 pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="addb4-169">16.000 pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-170">Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-171">32,000</span><span class="sxs-lookup"><span data-stu-id="addb4-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="addb4-172">1,067</span><span class="sxs-lookup"><span data-stu-id="addb4-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="addb4-173">10</span><span class="sxs-lookup"><span data-stu-id="addb4-173">10</span></span></p></td>
<td><p><span data-ttu-id="addb4-174">33,077</span><span class="sxs-lookup"><span data-stu-id="addb4-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-175">% der Chatrooms als Auditorium verwendet</span><span class="sxs-lookup"><span data-stu-id="addb4-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="addb4-176">1 %</span><span class="sxs-lookup"><span data-stu-id="addb4-176">1%</span></span></p></td>
<td><p><span data-ttu-id="addb4-177">1 %</span><span class="sxs-lookup"><span data-stu-id="addb4-177">1%</span></span></p></td>
<td><p><span data-ttu-id="addb4-178">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-179">% der Chatrooms sind offen</span><span class="sxs-lookup"><span data-stu-id="addb4-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="addb4-180">3%</span><span class="sxs-lookup"><span data-stu-id="addb4-180">3%</span></span></p></td>
<td><p><span data-ttu-id="addb4-181">3%</span><span class="sxs-lookup"><span data-stu-id="addb4-181">3%</span></span></p></td>
<td><p><span data-ttu-id="addb4-182">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-183">Offene Chatrooms (ohne explizite Mitgliedschaft)</span><span class="sxs-lookup"><span data-stu-id="addb4-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="addb4-184">960</span><span class="sxs-lookup"><span data-stu-id="addb4-184">960</span></span></p></td>
<td><p><span data-ttu-id="addb4-185">32</span><span class="sxs-lookup"><span data-stu-id="addb4-185">32</span></span></p></td>
<td><p><span data-ttu-id="addb4-186">5</span><span class="sxs-lookup"><span data-stu-id="addb4-186">5</span></span></p></td>
<td><p><span data-ttu-id="addb4-187">997</span><span class="sxs-lookup"><span data-stu-id="addb4-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-188">Nicht offene Chatrooms (herkömmliche Chatrooms mit expliziter Mitgliedschaft)</span><span class="sxs-lookup"><span data-stu-id="addb4-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="addb4-189">31,040</span><span class="sxs-lookup"><span data-stu-id="addb4-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="addb4-190">1.035</span><span class="sxs-lookup"><span data-stu-id="addb4-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="addb4-191">5</span><span class="sxs-lookup"><span data-stu-id="addb4-191">5</span></span></p></td>
<td><p><span data-ttu-id="addb4-192">32,080</span><span class="sxs-lookup"><span data-stu-id="addb4-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-193">Auditorium-Chatrooms (zusätzlicher Zugang für Referenten)</span><span class="sxs-lookup"><span data-stu-id="addb4-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="addb4-194">0</span><span class="sxs-lookup"><span data-stu-id="addb4-194">0</span></span></p></td>
<td><p><span data-ttu-id="addb4-195">32</span><span class="sxs-lookup"><span data-stu-id="addb4-195">32</span></span></p></td>
<td><p><span data-ttu-id="addb4-196">5</span><span class="sxs-lookup"><span data-stu-id="addb4-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-197">Über direkte Mitgliedschaft verwaltete Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="addb4-198">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-198">50%</span></span></p></td>
<td><p><span data-ttu-id="addb4-199">10%</span><span class="sxs-lookup"><span data-stu-id="addb4-199">10%</span></span></p></td>
<td><p><span data-ttu-id="addb4-200">0%</span><span class="sxs-lookup"><span data-stu-id="addb4-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-201">Von Benutzergruppen verwaltete Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="addb4-202">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-202">50%</span></span></p></td>
<td><p><span data-ttu-id="addb4-203">90%</span><span class="sxs-lookup"><span data-stu-id="addb4-203">90%</span></span></p></td>
<td><p><span data-ttu-id="addb4-204">100%</span><span class="sxs-lookup"><span data-stu-id="addb4-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-205">Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Chatrooms (nicht explizit angegeben)</span><span class="sxs-lookup"><span data-stu-id="addb4-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="addb4-206">0</span><span class="sxs-lookup"><span data-stu-id="addb4-206">0</span></span></p></td>
<td><p><span data-ttu-id="addb4-207">0</span><span class="sxs-lookup"><span data-stu-id="addb4-207">0</span></span></p></td>
<td><p><span data-ttu-id="addb4-208">0</span><span class="sxs-lookup"><span data-stu-id="addb4-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-209">Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-210">30</span><span class="sxs-lookup"><span data-stu-id="addb4-210">30</span></span></p></td>
<td><p><span data-ttu-id="addb4-211">150</span><span class="sxs-lookup"><span data-stu-id="addb4-211">150</span></span></p></td>
<td><p><span data-ttu-id="addb4-212">16,000</span><span class="sxs-lookup"><span data-stu-id="addb4-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-213">Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht offene Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-214">3</span><span class="sxs-lookup"><span data-stu-id="addb4-214">3</span></span></p></td>
<td><p><span data-ttu-id="addb4-215">5</span><span class="sxs-lookup"><span data-stu-id="addb4-215">5</span></span></p></td>
<td><p><span data-ttu-id="addb4-216">10</span><span class="sxs-lookup"><span data-stu-id="addb4-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-217">Benutzer und Benutzergruppen in der Managerliste der einzelnen Chatrooms (für offene und nicht offene Chatrooms)</span><span class="sxs-lookup"><span data-stu-id="addb4-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="addb4-218">6</span><span class="sxs-lookup"><span data-stu-id="addb4-218">6</span></span></p></td>
<td><p><span data-ttu-id="addb4-219">6</span><span class="sxs-lookup"><span data-stu-id="addb4-219">6</span></span></p></td>
<td><p><span data-ttu-id="addb4-220">6</span><span class="sxs-lookup"><span data-stu-id="addb4-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-221">Benutzer und Benutzergruppen in der Referentenliste der einzelnen Auditorium-Chatrooms (für offene und nicht offene Chatrooms)</span><span class="sxs-lookup"><span data-stu-id="addb4-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="addb4-222">6</span><span class="sxs-lookup"><span data-stu-id="addb4-222">6</span></span></p></td>
<td><p><span data-ttu-id="addb4-223">6</span><span class="sxs-lookup"><span data-stu-id="addb4-223">6</span></span></p></td>
<td><p><span data-ttu-id="addb4-224">6</span><span class="sxs-lookup"><span data-stu-id="addb4-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-225">Benutzerbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-226">465,600</span><span class="sxs-lookup"><span data-stu-id="addb4-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="addb4-227">15,520</span><span class="sxs-lookup"><span data-stu-id="addb4-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-228">Benutzergruppenbasierte Mitgliedschaftsentitäten in allen nicht offenen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-229">46,560</span><span class="sxs-lookup"><span data-stu-id="addb4-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="addb4-230">4656</span><span class="sxs-lookup"><span data-stu-id="addb4-230">4656</span></span></p></td>
<td><p><span data-ttu-id="addb4-231">50</span><span class="sxs-lookup"><span data-stu-id="addb4-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-232">Benutzer- und benutzergruppenbasierte Entitäten für alle Auditorium-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-233">0</span><span class="sxs-lookup"><span data-stu-id="addb4-233">0</span></span></p></td>
<td><p><span data-ttu-id="addb4-234">192</span><span class="sxs-lookup"><span data-stu-id="addb4-234">192</span></span></p></td>
<td><p><span data-ttu-id="addb4-235">50</span><span class="sxs-lookup"><span data-stu-id="addb4-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-236">Benutzer- und benutzergruppenbasierte Managerentitäten für alle Chatroom-Managerlisten</span><span class="sxs-lookup"><span data-stu-id="addb4-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="addb4-237">192,000</span><span class="sxs-lookup"><span data-stu-id="addb4-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="addb4-238">6,400</span><span class="sxs-lookup"><span data-stu-id="addb4-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="addb4-239">60</span><span class="sxs-lookup"><span data-stu-id="addb4-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-240">Aktive Benutzer pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="addb4-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="addb4-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="addb4-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-243"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="addb4-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-244">Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="addb4-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="addb4-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="addb4-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="addb4-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-249">Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="addb4-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="addb4-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="addb4-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-252"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="addb4-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-253">Von Benutzergruppen verwaltete Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="addb4-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="addb4-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="addb4-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="addb4-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-257">Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-258">155,200</span><span class="sxs-lookup"><span data-stu-id="addb4-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="addb4-259">5173</span><span class="sxs-lookup"><span data-stu-id="addb4-259">5173</span></span></p></td>
<td><p><span data-ttu-id="addb4-260">68</span><span class="sxs-lookup"><span data-stu-id="addb4-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-261">Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-262">465,600</span><span class="sxs-lookup"><span data-stu-id="addb4-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="addb4-263">77,600</span><span class="sxs-lookup"><span data-stu-id="addb4-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="addb4-264">72,000</span><span class="sxs-lookup"><span data-stu-id="addb4-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-265">Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="addb4-266">6</span><span class="sxs-lookup"><span data-stu-id="addb4-266">6</span></span></p></td>
<td><p><span data-ttu-id="addb4-267">6</span><span class="sxs-lookup"><span data-stu-id="addb4-267">6</span></span></p></td>
<td><p><span data-ttu-id="addb4-268">6</span><span class="sxs-lookup"><span data-stu-id="addb4-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-269">Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten aller Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="addb4-270">192,000</span><span class="sxs-lookup"><span data-stu-id="addb4-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="addb4-271">6400</span><span class="sxs-lookup"><span data-stu-id="addb4-271">6400</span></span></p></td>
<td><p><span data-ttu-id="addb4-272">60</span><span class="sxs-lookup"><span data-stu-id="addb4-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-273">Zugriffssteuerungseinträge</span><span class="sxs-lookup"><span data-stu-id="addb4-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="addb4-274">704,160</span><span class="sxs-lookup"><span data-stu-id="addb4-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="addb4-275">26,768</span><span class="sxs-lookup"><span data-stu-id="addb4-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="addb4-276">160</span><span class="sxs-lookup"><span data-stu-id="addb4-276">160</span></span></p></td>
<td><p><span data-ttu-id="addb4-277">731,088</span><span class="sxs-lookup"><span data-stu-id="addb4-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-278">Maximale Anzahl von Zugriffssteuerungseinträgen</span><span class="sxs-lookup"><span data-stu-id="addb4-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="addb4-279">2,000,000</span><span class="sxs-lookup"><span data-stu-id="addb4-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="addb4-280">Wenn Sie im vorangehenden Beispiel die beständigen Chat Server gemäß den empfohlenen Richtlinien bereitstellen, können Sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern mit aktivierter Kompatibilität verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="addb4-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="addb4-281">In diesem Beispiel werden Chatrooms in kleine (30 aktive gleichzeitige Benutzer), mittelgroße (150 aktive Benutzer) und große Chatrooms (16.000 aktive Benutzer) unterteilt.</span><span class="sxs-lookup"><span data-stu-id="addb4-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="addb4-282">Die Anzahl der Chatrooms einer bestimmten Größe wird basierend auf der Gesamtzahl der folgenden Werte berechnet:</span><span class="sxs-lookup"><span data-stu-id="addb4-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="addb4-283">Aktive Benutzer im System</span><span class="sxs-lookup"><span data-stu-id="addb4-283">Active users in the system</span></span>

  - <span data-ttu-id="addb4-284">Aktive Benutzer in Chatrooms der jeweiligen Größe</span><span class="sxs-lookup"><span data-stu-id="addb4-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="addb4-285">Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt</span><span class="sxs-lookup"><span data-stu-id="addb4-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="addb4-p111">Die vorstehende Tabelle zur Kapazitätsplanung gibt für jeden Chatroom die Anzahl von Zugriffssteuerungseinträgen an, die dem jeweiligen Chatroom zugeordnet sind. Dies umfasst die Einträge, die dem Chatroom direkt zugewiesen sind. Sie können den Zugriff auf einzelne Chatrooms über Zugriffssteuerungslisten steuern. Darüber hinaus können Sie den Zugriff auf Kategorieebene steuern. In einer Zugriffssteuerungsliste kann es sich bei einem einzelnen Zugriffssteuerungseintrag entweder um eine Benutzergruppe (z. B. eine Sicherheitsgruppe oder Verteilerliste) oder einen einzelnen Benutzer handeln. Sie können Zugriffssteuerungseinträge für Manager, Referenten und Mitglieder eines Chatrooms definieren.</span><span class="sxs-lookup"><span data-stu-id="addb4-p111">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room. You can control access to individual chat rooms by using access control lists (ACLs). You can also control access at the category level. In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user. You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="addb4-p112">Bedenken Sie bei der Planung Ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl von zulässigen Zugriffssteuerungseinträgen zwei Millionen beträgt. Wenn die berechnete Anzahl von Zugriffssteuerungseinträgen eine Million überschreitet, kann die Leistung signifikant beeinträchtigt werden. Um dieses Problem zu verhindern, sollten Sie wenn möglich sicherstellen, dass Ihre Zugriffssteuerungseinträge keine einzelnen Benutzer, sondern Benutzergruppen umfassen.</span><span class="sxs-lookup"><span data-stu-id="addb4-p112">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million. If the calculated access control entries exceed 2 million, server performance could degrade significantly. To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="addb4-294">Kapazitätsplanung für die Verwaltung des Chatroom-Zugriffs per Einladung</span><span class="sxs-lookup"><span data-stu-id="addb4-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="addb4-295">Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um zu verstehen, wie viele Einladungen der beständige Chat Server in der persistenten Chat Datenbank erstellt und speichert, wenn er zum Senden von Einladungen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="addb4-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="addb4-296">Sie können Einladungen für die Kategorie verwalten, indem Sie die **Kategorie Einstellungen für Chatrooms** in der lync Server-Systemsteuerung verwenden oder das Windows PowerShell-Cmdlet " **csPersistentChatCategory**" verwenden.</span><span class="sxs-lookup"><span data-stu-id="addb4-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="addb4-297">Sie können Einladungen in einem Chatroom verwalten (entsprechend der Kategorie), indem Sie die vom lync-Client gestartete **Raum Verwaltungs** Seite verwenden oder ein Windows PowerShell-Cmdlet, " **csPersistentChatRoom**", verwenden.</span><span class="sxs-lookup"><span data-stu-id="addb4-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="addb4-298">Für die Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass die **Einladungsoption** auf der Seite mit den **Chatroomeinstellungen** für 50 % aller Chatrooms auf **Ja** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="addb4-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="addb4-299">Wenn der berechnete Wert für die Anzahl von Einladungen, die der Server generiert, eine Million überschreitet, kann die Serverleistung signifikant beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="addb4-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="addb4-300">Um dieses Problem zu vermeiden, stellen Sie sicher, dass Sie die Anzahl der Chatrooms minimieren, die zum Senden von Einladungen konfiguriert sind, oder die Anzahl der Benutzer einschränken, die an Chatrooms teilnehmen können, die zum Senden von Einladungen konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="addb4-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="addb4-301">Beispiel für Chatroom-Zugriff per Einladung</span><span class="sxs-lookup"><span data-stu-id="addb4-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="addb4-302">Kleine Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="addb4-303">Mittlere Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="addb4-304">Große Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="addb4-305">Gesamt</span><span class="sxs-lookup"><span data-stu-id="addb4-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="addb4-306">Benutzer, die auf den Chatroom zugreifen können</span><span class="sxs-lookup"><span data-stu-id="addb4-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="addb4-307">30 pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="addb4-308">150 pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="addb4-309">16.000 pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-310">Prozentsatz an Chatrooms mit Einladung</span><span class="sxs-lookup"><span data-stu-id="addb4-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="addb4-311">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-311">50%</span></span></p></td>
<td><p><span data-ttu-id="addb4-312">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-312">50%</span></span></p></td>
<td><p><span data-ttu-id="addb4-313">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-314">Für das Senden von Einladungen konfigurierte Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="addb4-315"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="addb4-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="addb4-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="addb4-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-318">Benutzer, die auf den Chatroom zugreifen können</span><span class="sxs-lookup"><span data-stu-id="addb4-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="addb4-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="addb4-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="addb4-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="addb4-321"><em>16,000</em></span><span class="sxs-lookup"><span data-stu-id="addb4-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-322">Vom beständigen Chat Server generierte Einladungen</span><span class="sxs-lookup"><span data-stu-id="addb4-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="addb4-323">960,000</span><span class="sxs-lookup"><span data-stu-id="addb4-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="addb4-324">120,000</span><span class="sxs-lookup"><span data-stu-id="addb4-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="addb4-325">80,000</span><span class="sxs-lookup"><span data-stu-id="addb4-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="addb4-326">1,160,000</span><span class="sxs-lookup"><span data-stu-id="addb4-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-327">Maximal zulässige Anzahl von Einladungen</span><span class="sxs-lookup"><span data-stu-id="addb4-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="addb4-328">2,000,000</span><span class="sxs-lookup"><span data-stu-id="addb4-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-329">Modell 1: Start mit der erwarteten Anzahl an Nachrichten pro Chatroom und Tag</span><span class="sxs-lookup"><span data-stu-id="addb4-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-330">Chatrate pro Chatroom (pro Tag)</span><span class="sxs-lookup"><span data-stu-id="addb4-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="addb4-331">50</span><span class="sxs-lookup"><span data-stu-id="addb4-331">50</span></span></p></td>
<td><p><span data-ttu-id="addb4-332">500</span><span class="sxs-lookup"><span data-stu-id="addb4-332">500</span></span></p></td>
<td><p><span data-ttu-id="addb4-333">100</span><span class="sxs-lookup"><span data-stu-id="addb4-333">100</span></span></p></td>
<td><p><span data-ttu-id="addb4-334">650</span><span class="sxs-lookup"><span data-stu-id="addb4-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-335">Chatrate (pro Sekunde) für alle Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-336">55.56</span><span class="sxs-lookup"><span data-stu-id="addb4-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="addb4-337">18.52</span><span class="sxs-lookup"><span data-stu-id="addb4-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="addb4-338">0.03</span><span class="sxs-lookup"><span data-stu-id="addb4-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="addb4-339">74</span><span class="sxs-lookup"><span data-stu-id="addb4-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-340">Modell 2: Start mit der Anzahl an veröffentlichten Nachrichten pro Benutzer und Tag</span><span class="sxs-lookup"><span data-stu-id="addb4-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-341">Chatrate pro Benutzer und Tag</span><span class="sxs-lookup"><span data-stu-id="addb4-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="addb4-342">15</span><span class="sxs-lookup"><span data-stu-id="addb4-342">15</span></span></p></td>
<td><p><span data-ttu-id="addb4-343">5</span><span class="sxs-lookup"><span data-stu-id="addb4-343">5</span></span></p></td>
<td><p><span data-ttu-id="addb4-344">0.1</span><span class="sxs-lookup"><span data-stu-id="addb4-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="addb4-345">20</span><span class="sxs-lookup"><span data-stu-id="addb4-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-346">Chatrate pro Chatroom (pro Tag)</span><span class="sxs-lookup"><span data-stu-id="addb4-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="addb4-347">38</span><span class="sxs-lookup"><span data-stu-id="addb4-347">38</span></span></p></td>
<td><p><span data-ttu-id="addb4-348">375</span><span class="sxs-lookup"><span data-stu-id="addb4-348">375</span></span></p></td>
<td><p><span data-ttu-id="addb4-349">800</span><span class="sxs-lookup"><span data-stu-id="addb4-349">800</span></span></p></td>
<td><p><span data-ttu-id="addb4-350">1,213</span><span class="sxs-lookup"><span data-stu-id="addb4-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-351">Chatrate (pro Sekunde) für alle Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-352">41.67</span><span class="sxs-lookup"><span data-stu-id="addb4-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="addb4-353">13.89</span><span class="sxs-lookup"><span data-stu-id="addb4-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="addb4-354">0.28</span><span class="sxs-lookup"><span data-stu-id="addb4-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="addb4-355">56</span><span class="sxs-lookup"><span data-stu-id="addb4-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="addb4-356">Benutzermodell für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="addb4-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="addb4-357">In der folgenden Tabelle wird das Benutzermodell für den beständigen Chat Server beschrieben.</span><span class="sxs-lookup"><span data-stu-id="addb4-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="addb4-358">Dieses Modell bildet die Grundlage für die Kapazitätsplanungsanforderungen und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.</span><span class="sxs-lookup"><span data-stu-id="addb4-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="addb4-359">Benutzermodell für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="addb4-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="addb4-360">Anzahl der aktiven verbundenen Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="addb4-361">80,000</span><span class="sxs-lookup"><span data-stu-id="addb4-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-362">Anzahl der Server Dienstinstanzen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="addb4-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="addb4-363">4</span><span class="sxs-lookup"><span data-stu-id="addb4-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-364">Umfang kleiner Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-365">30 Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-366">Umfang mittelgroßer Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-367">150 Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-368">Umfang großer Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-369">16.000 Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-370">Gesamtzahl der Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-371">33,077</span><span class="sxs-lookup"><span data-stu-id="addb4-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-372">Anzahl kleiner Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-373">32,000</span><span class="sxs-lookup"><span data-stu-id="addb4-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-374">Anzahl mittelgroßer Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-375">1,067</span><span class="sxs-lookup"><span data-stu-id="addb4-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-376">Anzahl großer Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-377">10</span><span class="sxs-lookup"><span data-stu-id="addb4-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-378">Gesamtzahl der Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-379">16</span><span class="sxs-lookup"><span data-stu-id="addb4-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-380">Anzahl kleiner Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-381">12</span><span class="sxs-lookup"><span data-stu-id="addb4-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-382">Anzahl mittelgroßer Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-383">2</span><span class="sxs-lookup"><span data-stu-id="addb4-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-384">Anzahl großer Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-385">2</span><span class="sxs-lookup"><span data-stu-id="addb4-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-386">Anzahl der betretenen Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-387">24</span><span class="sxs-lookup"><span data-stu-id="addb4-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-388">Maximale Beitrittsrate</span><span class="sxs-lookup"><span data-stu-id="addb4-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="addb4-389">10/s</span><span class="sxs-lookup"><span data-stu-id="addb4-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-390">Gesamtchatrate</span><span class="sxs-lookup"><span data-stu-id="addb4-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="addb4-391">24/s</span><span class="sxs-lookup"><span data-stu-id="addb4-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-392">Chatrate für kleine Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="addb4-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-394">Chatrate für mittelgroße Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="addb4-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-396">Chatrate für große Chatrooms</span><span class="sxs-lookup"><span data-stu-id="addb4-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="addb4-397">~0.15/second</span><span class="sxs-lookup"><span data-stu-id="addb4-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-398">Prozentsatz der Chatrooms, die für Einladungen konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="addb4-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="addb4-399">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-400">Prozentsatz der direkten Mitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="addb4-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="addb4-401">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-402">Prozentsatz der Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="addb4-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="addb4-403">50%</span><span class="sxs-lookup"><span data-stu-id="addb4-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-404">Durchschnittliche Anzahl von Vorgänger Verbindungen in Active Directory-Domänendiensten</span><span class="sxs-lookup"><span data-stu-id="addb4-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="addb4-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="addb4-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-406">Anzahl abonnierter Kontakte pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-407">80</span><span class="sxs-lookup"><span data-stu-id="addb4-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-408">Durchschnittliche Anzahl von Endpunkten pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-409">1.5</span><span class="sxs-lookup"><span data-stu-id="addb4-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-410">Durchschnittliche Anzahl von sichtbaren Chatrooms pro Endpunkt</span><span class="sxs-lookup"><span data-stu-id="addb4-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="addb4-411">1.5</span><span class="sxs-lookup"><span data-stu-id="addb4-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-412">Durchschnittliche Anzahl von sichtbaren Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-413">2,25 (50 % für 1 Chatroom und 50 % für 2 Chatrooms); bis zu 6 Chatrooms offen, ein Chatroom pro Bildschirm</span><span class="sxs-lookup"><span data-stu-id="addb4-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-414">Anzahl von Teilnehmern, die pro Intervall abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="addb4-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="addb4-415">25 pro sichtbarem Chatroom</span><span class="sxs-lookup"><span data-stu-id="addb4-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-416">Länge des Abrufintervalls</span><span class="sxs-lookup"><span data-stu-id="addb4-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="addb4-417">5 Minuten</span><span class="sxs-lookup"><span data-stu-id="addb4-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-418">Anzahl von Teilnehmern, die pro Sekunde abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="addb4-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="addb4-419">15,000</span><span class="sxs-lookup"><span data-stu-id="addb4-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="addb4-420">Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer</span><span class="sxs-lookup"><span data-stu-id="addb4-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="addb4-421">6</span><span class="sxs-lookup"><span data-stu-id="addb4-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="addb4-422">Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="addb4-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="addb4-423">133.33</span><span class="sxs-lookup"><span data-stu-id="addb4-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


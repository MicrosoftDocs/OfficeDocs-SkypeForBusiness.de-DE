---
title: 'Lync Server 2013: Kapazitätsplanung für den Server für beständigen Chat'
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
ms.openlocfilehash: 5c6bb3c7dcd8d03ffb0a57fb165fe1dba4ee933d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512802"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="322e7-102">Kapazitätsplanung für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="322e7-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="322e7-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="322e7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="322e7-104">Der Server für beständigen Chat kann mehr Benutzer-Echtzeitchats ausführen, die für den zukünftigen Abruf und die Suche beibehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="322e7-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="322e7-105">Im Gegensatz zur Gruppe Instant Messaging (im), die im Postfach eines Benutzers gespeichert wird, wenn der Unterhaltungsverlauf konfiguriert ist, bleibt eine Serversitzung für beständigen Chat länger geöffnet, und der Inhalt wird auf einem Server zusammen mit den Nachrichten, Dateien, URLs und anderen Daten gespeichert, die Teil einer laufenden Unterhaltung sind.</span><span class="sxs-lookup"><span data-stu-id="322e7-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="322e7-106">Die Kapazitätsplanung ist ein wichtiger Bestandteil der Vorbereitung der Bereitstellung des Servers für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="322e7-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="322e7-107">Dieses Thema enthält Details zu unterstützten Topologien und Kapazitäts Planungstabellen für beständigen Chat Server, mit denen Sie die beste Konfiguration für Ihre Bereitstellung bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="322e7-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="322e7-108">Außerdem wird beschrieben, wie Sie Server Bereitstellungen mit persistentem Chat am besten verwalten, die zu Spitzenzeiten eine höhere Kapazität erfordern.</span><span class="sxs-lookup"><span data-stu-id="322e7-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="322e7-109">Informationen zum Herunterladen von persistent Chat Server finden Sie unter "Microsoft lync Server 13 persistent Chat Server" unter [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) .</span><span class="sxs-lookup"><span data-stu-id="322e7-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="322e7-110">Ausführliche Informationen zum Installieren des Servers für beständigen Chat finden Sie unter [Installing persistent Chat Server in lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) und [Configuring persistent Chat Server in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="322e7-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="322e7-111">Support Tools wie lync Server Planungs Tool können Ihnen bei der Kapazitätsplanung behilflich sein.</span><span class="sxs-lookup"><span data-stu-id="322e7-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="322e7-112">Ausführliche Informationen zum Planungs Tool finden Sie unter [Beginn des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="322e7-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="322e7-113">Unterstützte Topologien für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="322e7-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="322e7-114">Sie können den Server für beständigen Chat in Pools mit einem oder mehreren Servern und mit einer Topologie mit einem oder mehreren Pools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="322e7-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="322e7-115">Wir unterstützen nun auch den Server für beständigen Chat auf Standard Edition-Server für neue lync Server 2013-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="322e7-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="322e7-116">Leistung und Skalierung sind jedoch betroffen, und da es für diese neue Bereitstellung keine Option für hohe Verfügbarkeit gibt, erwarten wir, dass Sie dies in erster Linie für die Machbarkeitsstudie, Evaluierung usw. verwenden.</span><span class="sxs-lookup"><span data-stu-id="322e7-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="322e7-117">Weitere Details zu beiden Topologien finden Sie unter <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent Chat Server in lync Server 2013</A> in dieser Dokumentationsgruppe und <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent Chat Server in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="322e7-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="322e7-118">Einzelservertopologie</span><span class="sxs-lookup"><span data-stu-id="322e7-118">Single-Server Topology</span></span>

<span data-ttu-id="322e7-119">Die minimale Konfiguration und die einfachste Bereitstellung für den Server für beständigen Chat ist ein einzelner Server für beständigen Chat Front-End-Server Topologie.</span><span class="sxs-lookup"><span data-stu-id="322e7-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="322e7-120">Für diese Bereitstellung ist ein einzelner Server erforderlich, auf dem der Server für beständigen Chat ausgeführt wird (optional wird der Kompatibilitätsdienst ausgeführt, wenn die Kompatibilität aktiviert ist), ein Server, der sowohl die SQL Server Datenbank hostet, als auch die erforderliche Kompatibilität, die SQL Server Datenbank zum Speichern der Kompatibilitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="322e7-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="322e7-121">Sie können keinem Serverpool für beständigen Chat, der als Einzel Server Bereitstellung im Topologie-Generator gestartet wird, keine weiteren Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="322e7-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="322e7-122">Es wird empfohlen, die Topologie mit mehreren Server Pools zu verwenden, auch wenn Sie einen einzelnen Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="322e7-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="322e7-123">Dies bedeutet, dass Sie später weitere Server hinzufügen können, falls dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="322e7-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="322e7-124">Die folgende Abbildung zeigt alle erforderlichen und optionalen Komponenten einer Topologie für einen einzelnen Server für beständigen Chat Front-End-Server mit Compliance.</span><span class="sxs-lookup"><span data-stu-id="322e7-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="322e7-125">**Einzelner dauerhafter Chatserver**</span><span class="sxs-lookup"><span data-stu-id="322e7-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="322e7-126">![Topologie mit einem Server mit Kompatibilitätsdienst](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie mit einem Server mit Kompatibilitätsdienst")</span><span class="sxs-lookup"><span data-stu-id="322e7-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="322e7-127">Topologie mit mehreren Servern</span><span class="sxs-lookup"><span data-stu-id="322e7-127">Multiple-Server Topology</span></span>

<span data-ttu-id="322e7-128">Um eine höhere Kapazität und Zuverlässigkeit zu bieten, können Sie eine Topologie mit mehreren Servern bereitstellen, wie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="322e7-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="322e7-129">Die Topologie mit mehreren Servern kann bis zu vier aktive Computer mit persistent Chat Server umfassen (Hochverfügbarkeit und Notfall Wiederherstellungs Konfigurationen ermöglichen bis zu acht, aber nur vier können aktiv sein und die restlichen vier im Standbymodus).</span><span class="sxs-lookup"><span data-stu-id="322e7-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="322e7-130">Jeder Server kann bis zu 20.000 gleichzeitige Benutzer unterstützen, für insgesamt 80.000 gleichzeitige Benutzer, die mit einem Serverpool für beständigen Chat mit 4 Servern verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="322e7-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="322e7-131">Eine Topologie mit mehreren Servern ist identisch mit der Einzelservertopologie, mit dem Unterschied, dass mehrere Server den Server für beständigen Chat hosten und höher skalieren können.</span><span class="sxs-lookup"><span data-stu-id="322e7-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="322e7-132">Mehrere Computer mit persistent Chat Server sollten sich in derselben Active Directory-Domänendienste Domäne wie lync Server und dem Kompatibilitätsdienst befinden.</span><span class="sxs-lookup"><span data-stu-id="322e7-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="322e7-133">Die folgende Abbildung zeigt alle Komponenten einer Topologie mit mehreren Servern mit mehreren Computern, auf denen der Server für beständigen Chat, der optionale Kompatibilitätsdienst und eine separate Kompatibilitätsdatenbank läuft.</span><span class="sxs-lookup"><span data-stu-id="322e7-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="322e7-134">**Mehrere dauerhafte Chatserver**</span><span class="sxs-lookup"><span data-stu-id="322e7-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="322e7-135">![Topologie mit mehreren Servern](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie mit mehreren Servern")</span><span class="sxs-lookup"><span data-stu-id="322e7-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="322e7-136">In einer Bereitstellung mit vier Servern für beständigen Chat, bei der 80.000 Benutzer gleichzeitig bei und mit dem beständigen Chat angemeldet werden können, wird die Last gleichmäßig auf 20.000 Benutzer pro Server verteilt.</span><span class="sxs-lookup"><span data-stu-id="322e7-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="322e7-137">Wenn ein Server nicht mehr verfügbar ist, verlieren die Benutzer, die mit diesem Server verbunden sind, Ihren Zugriff auf den Server für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="322e7-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="322e7-138">Die getrennten Benutzer werden automatisch an die übrigen Server übergeben, bis der ausgefallene Server erneut verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="322e7-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="322e7-139">In Abhängigkeit von der Menge des beständigen Chat Datenverkehrs im Netzwerk kann diese Übertragung einige Minuten oder länger dauern.</span><span class="sxs-lookup"><span data-stu-id="322e7-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="322e7-140">Da jeder der verbleibenden Server möglicherweise so viele wie 30.000-Benutzer hostet, wird empfohlen, den nicht verfügbaren Server so schnell wie möglich wiederherzustellen, um Leistungsprobleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="322e7-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="322e7-141">Andernfalls können Sie einen weiteren Server für beständigen Chat mithilfe des Topologie-Generators oder des Windows PowerShell **-Cmdlets festlegen-CsPersistentChatActiveServer**verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="322e7-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="322e7-142">Kapazitätsplanung für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="322e7-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="322e7-143">Die folgenden Tabellen können Ihnen bei der Kapazitätsplanung für den Server für beständigen Chat helfen.</span><span class="sxs-lookup"><span data-stu-id="322e7-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="322e7-144">Sie modellieren, wie sich verschiedene Einstellungen für den Server für beständigen Chat auf Kapazitäts Funktionen auswirken</span><span class="sxs-lookup"><span data-stu-id="322e7-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="322e7-145">Planen der maximalen Kapazität für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="322e7-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="322e7-146">Ermitteln Sie anhand der folgenden Beispieltabelle die Anzahl von Benutzern, die Sie unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="322e7-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="322e7-147">Beispiel für den Server Pool für beständigen Chat mit maximaler Kapazität</span><span class="sxs-lookup"><span data-stu-id="322e7-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322e7-148">Aktive persistent Chat-Dienstinstanzen</span><span class="sxs-lookup"><span data-stu-id="322e7-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="322e7-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="322e7-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-150">Dienstinstanzen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="322e7-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="322e7-151"><em>8 (4 muss inaktiv sein; nur maximal 4 kann aktiv sein)</em></span><span class="sxs-lookup"><span data-stu-id="322e7-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-152">Aktive Benutzer verbunden</span><span class="sxs-lookup"><span data-stu-id="322e7-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="322e7-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="322e7-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-154">Gesamtanzahl der Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="322e7-155">150.000</span><span class="sxs-lookup"><span data-stu-id="322e7-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-156">Anzahl der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="322e7-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="322e7-157">120.000</span><span class="sxs-lookup"><span data-stu-id="322e7-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="322e7-158">Im vorherigen Beispiel soll die maximale Anzahl von Benutzern unterstützt werden, die der Server für beständigen Chat zulässt: vier Server/Instanzen des Diensts für beständigen Chat (können vier weitere passive Server mit persistent Chat Server für hohe Verfügbarkeit und Notfallwiederherstellung) und 20.000 Benutzer pro Server für insgesamt 80.000 aktive Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="322e7-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="322e7-159">Kapazitätsplanung für die Verwaltung des Zugriffs auf beständigen Chatroom</span><span class="sxs-lookup"><span data-stu-id="322e7-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="322e7-160">Die folgende Beispieltabelle hilft Ihnen bei der Planung der Verwaltung des Zugriffs auf beständigen Chatrooms in einem Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="322e7-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="322e7-161">Beispiel für die Verwaltung des Chatroomzugriffs</span><span class="sxs-lookup"><span data-stu-id="322e7-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="322e7-162">Kleine Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="322e7-163">Mittlere Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="322e7-164">Große Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="322e7-165">Gesamt</span><span class="sxs-lookup"><span data-stu-id="322e7-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322e7-166">Größe der Chatrooms (Anzahl der miteinander verbundenen Benutzer)</span><span class="sxs-lookup"><span data-stu-id="322e7-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="322e7-167">30 pro Zimmer</span><span class="sxs-lookup"><span data-stu-id="322e7-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="322e7-168">150 pro Zimmer</span><span class="sxs-lookup"><span data-stu-id="322e7-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="322e7-169">16.000 pro Zimmer</span><span class="sxs-lookup"><span data-stu-id="322e7-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-170">Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-171">32.000</span><span class="sxs-lookup"><span data-stu-id="322e7-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="322e7-172">1.067</span><span class="sxs-lookup"><span data-stu-id="322e7-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="322e7-173">10 </span><span class="sxs-lookup"><span data-stu-id="322e7-173">10</span></span></p></td>
<td><p><span data-ttu-id="322e7-174">33.077</span><span class="sxs-lookup"><span data-stu-id="322e7-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-175">% der Räume, die Auditorium sind</span><span class="sxs-lookup"><span data-stu-id="322e7-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="322e7-176">1</span><span class="sxs-lookup"><span data-stu-id="322e7-176">1%</span></span></p></td>
<td><p><span data-ttu-id="322e7-177">1</span><span class="sxs-lookup"><span data-stu-id="322e7-177">1%</span></span></p></td>
<td><p><span data-ttu-id="322e7-178">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-179">% der geöffneten Räume</span><span class="sxs-lookup"><span data-stu-id="322e7-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="322e7-180">3</span><span class="sxs-lookup"><span data-stu-id="322e7-180">3%</span></span></p></td>
<td><p><span data-ttu-id="322e7-181">3</span><span class="sxs-lookup"><span data-stu-id="322e7-181">3%</span></span></p></td>
<td><p><span data-ttu-id="322e7-182">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-183">Offene Räume (keine explizite Mitgliedschaft)</span><span class="sxs-lookup"><span data-stu-id="322e7-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="322e7-184">960</span><span class="sxs-lookup"><span data-stu-id="322e7-184">960</span></span></p></td>
<td><p><span data-ttu-id="322e7-185">32</span><span class="sxs-lookup"><span data-stu-id="322e7-185">32</span></span></p></td>
<td><p><span data-ttu-id="322e7-186">5 </span><span class="sxs-lookup"><span data-stu-id="322e7-186">5</span></span></p></td>
<td><p><span data-ttu-id="322e7-187">997</span><span class="sxs-lookup"><span data-stu-id="322e7-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-188">Nicht geöffnete Räume (reguläre Räume mit expliziter Mitgliedschaft)</span><span class="sxs-lookup"><span data-stu-id="322e7-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="322e7-189">31.040</span><span class="sxs-lookup"><span data-stu-id="322e7-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="322e7-190">1,035</span><span class="sxs-lookup"><span data-stu-id="322e7-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="322e7-191">5 </span><span class="sxs-lookup"><span data-stu-id="322e7-191">5</span></span></p></td>
<td><p><span data-ttu-id="322e7-192">32.080</span><span class="sxs-lookup"><span data-stu-id="322e7-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-193">Auditoriumräume (zusätzlicher Referenten Eintrag)</span><span class="sxs-lookup"><span data-stu-id="322e7-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="322e7-194">0</span><span class="sxs-lookup"><span data-stu-id="322e7-194">0</span></span></p></td>
<td><p><span data-ttu-id="322e7-195">32</span><span class="sxs-lookup"><span data-stu-id="322e7-195">32</span></span></p></td>
<td><p><span data-ttu-id="322e7-196">5 </span><span class="sxs-lookup"><span data-stu-id="322e7-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-197">Durch direkte Mitgliedschaft verwaltete Räume</span><span class="sxs-lookup"><span data-stu-id="322e7-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="322e7-198">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-198">50%</span></span></p></td>
<td><p><span data-ttu-id="322e7-199">10 %</span><span class="sxs-lookup"><span data-stu-id="322e7-199">10%</span></span></p></td>
<td><p><span data-ttu-id="322e7-200">0 %</span><span class="sxs-lookup"><span data-stu-id="322e7-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-201">Von Benutzergruppen verwaltete Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="322e7-202">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-202">50%</span></span></p></td>
<td><p><span data-ttu-id="322e7-203">90 %</span><span class="sxs-lookup"><span data-stu-id="322e7-203">90%</span></span></p></td>
<td><p><span data-ttu-id="322e7-204">100 %</span><span class="sxs-lookup"><span data-stu-id="322e7-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-205">Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für offene Räume (nicht explizit angegeben)</span><span class="sxs-lookup"><span data-stu-id="322e7-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="322e7-206">0</span><span class="sxs-lookup"><span data-stu-id="322e7-206">0</span></span></p></td>
<td><p><span data-ttu-id="322e7-207">0</span><span class="sxs-lookup"><span data-stu-id="322e7-207">0</span></span></p></td>
<td><p><span data-ttu-id="322e7-208">0</span><span class="sxs-lookup"><span data-stu-id="322e7-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-209">Benutzer in der Mitgliederliste der einzelnen Chatrooms für nicht offene Räume</span><span class="sxs-lookup"><span data-stu-id="322e7-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-210">30</span><span class="sxs-lookup"><span data-stu-id="322e7-210">30</span></span></p></td>
<td><p><span data-ttu-id="322e7-211">150</span><span class="sxs-lookup"><span data-stu-id="322e7-211">150</span></span></p></td>
<td><p><span data-ttu-id="322e7-212">16.000</span><span class="sxs-lookup"><span data-stu-id="322e7-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-213">Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms für nicht offene Räume</span><span class="sxs-lookup"><span data-stu-id="322e7-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-214">3</span><span class="sxs-lookup"><span data-stu-id="322e7-214">3</span></span></p></td>
<td><p><span data-ttu-id="322e7-215">5 </span><span class="sxs-lookup"><span data-stu-id="322e7-215">5</span></span></p></td>
<td><p><span data-ttu-id="322e7-216">10 </span><span class="sxs-lookup"><span data-stu-id="322e7-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-217">Benutzer und Benutzergruppen in den Manager Listen der einzelnen Chatrooms (für offene und nicht offene Räume)</span><span class="sxs-lookup"><span data-stu-id="322e7-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="322e7-218">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-218">6</span></span></p></td>
<td><p><span data-ttu-id="322e7-219">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-219">6</span></span></p></td>
<td><p><span data-ttu-id="322e7-220">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-221">Benutzer und Benutzergruppen in den Referentenlisten der einzelnen Auditorium-Chatrooms (für offene und nicht offene Räume)</span><span class="sxs-lookup"><span data-stu-id="322e7-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="322e7-222">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-222">6</span></span></p></td>
<td><p><span data-ttu-id="322e7-223">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-223">6</span></span></p></td>
<td><p><span data-ttu-id="322e7-224">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-225">Benutzerbasierte Mitgliedschafts Entitäten in allen nicht offenen Räumen</span><span class="sxs-lookup"><span data-stu-id="322e7-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-226">465.600</span><span class="sxs-lookup"><span data-stu-id="322e7-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="322e7-227">15.520</span><span class="sxs-lookup"><span data-stu-id="322e7-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-228">Benutzergruppen basierte Mitgliedschafts Entitäten in allen nicht offenen Räumen</span><span class="sxs-lookup"><span data-stu-id="322e7-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-229">46.560</span><span class="sxs-lookup"><span data-stu-id="322e7-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="322e7-230">4656</span><span class="sxs-lookup"><span data-stu-id="322e7-230">4656</span></span></p></td>
<td><p><span data-ttu-id="322e7-231">50</span><span class="sxs-lookup"><span data-stu-id="322e7-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-232">Benutzer und Benutzergruppen basierte Entitäten in allen Auditorium-Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-233">0</span><span class="sxs-lookup"><span data-stu-id="322e7-233">0</span></span></p></td>
<td><p><span data-ttu-id="322e7-234">192</span><span class="sxs-lookup"><span data-stu-id="322e7-234">192</span></span></p></td>
<td><p><span data-ttu-id="322e7-235">50</span><span class="sxs-lookup"><span data-stu-id="322e7-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-236">Benutzer und Benutzergruppen basierte Manager-Entitäten in allen Chatrooms-Manager Listen</span><span class="sxs-lookup"><span data-stu-id="322e7-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="322e7-237">192.000</span><span class="sxs-lookup"><span data-stu-id="322e7-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="322e7-238">6.400</span><span class="sxs-lookup"><span data-stu-id="322e7-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="322e7-239">60</span><span class="sxs-lookup"><span data-stu-id="322e7-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-240">Aktive Benutzer pro Chatroom</span><span class="sxs-lookup"><span data-stu-id="322e7-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="322e7-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="322e7-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="322e7-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-243"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="322e7-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-244">Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="322e7-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="322e7-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="322e7-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="322e7-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-249">Benutzergruppen in der Mitgliederliste der einzelnen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="322e7-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="322e7-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="322e7-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-252"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="322e7-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-253">Von Benutzergruppen verwaltete Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="322e7-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="322e7-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="322e7-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="322e7-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-257">Benutzergruppenbasierte Mitgliedschaftsentitäten in allen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-258">155.200</span><span class="sxs-lookup"><span data-stu-id="322e7-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="322e7-259">5173</span><span class="sxs-lookup"><span data-stu-id="322e7-259">5173</span></span></p></td>
<td><p><span data-ttu-id="322e7-260">68</span><span class="sxs-lookup"><span data-stu-id="322e7-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-261">Benutzerbasierte Mitgliedschaftsentitäten in allen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-262">465.600</span><span class="sxs-lookup"><span data-stu-id="322e7-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="322e7-263">77.600</span><span class="sxs-lookup"><span data-stu-id="322e7-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="322e7-264">72.000</span><span class="sxs-lookup"><span data-stu-id="322e7-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-265">Benutzer und Benutzergruppen in den Manager-, Referenten- und Bereichslisten der einzelnen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="322e7-266">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-266">6</span></span></p></td>
<td><p><span data-ttu-id="322e7-267">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-267">6</span></span></p></td>
<td><p><span data-ttu-id="322e7-268">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-269">Benutzer und Benutzergruppen in allen Manager-, Referenten-und Bereichslisten für Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="322e7-270">192.000</span><span class="sxs-lookup"><span data-stu-id="322e7-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="322e7-271">6400</span><span class="sxs-lookup"><span data-stu-id="322e7-271">6400</span></span></p></td>
<td><p><span data-ttu-id="322e7-272">60</span><span class="sxs-lookup"><span data-stu-id="322e7-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-273">Zugriffssteuerungseinträge</span><span class="sxs-lookup"><span data-stu-id="322e7-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="322e7-274">704.160</span><span class="sxs-lookup"><span data-stu-id="322e7-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="322e7-275">26.768</span><span class="sxs-lookup"><span data-stu-id="322e7-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="322e7-276">160</span><span class="sxs-lookup"><span data-stu-id="322e7-276">160</span></span></p></td>
<td><p><span data-ttu-id="322e7-277">731.088</span><span class="sxs-lookup"><span data-stu-id="322e7-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-278">Maximale Anzahl von Zugriffssteuerungseinträgen</span><span class="sxs-lookup"><span data-stu-id="322e7-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="322e7-279">2 Millionen</span><span class="sxs-lookup"><span data-stu-id="322e7-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="322e7-280">Wenn Sie im vorherigen Beispiel die Server für beständigen Chat gemäß den empfohlenen Richtlinien bereitstellen, können Sie bis zu 80.000 aktive Benutzer in einem Pool mit vier Servern mit aktivierter Kompatibilität verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="322e7-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="322e7-281">In diesem Beispiel werden Chatrooms kategorisiert, die als klein (30 aktive Benutzer zu einem bestimmten Zeitpunkt), mittlere (150 aktive Benutzer) und groß (16.000 aktive Benutzer) kategorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="322e7-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="322e7-282">Die Anzahl von Chatrooms einer bestimmten Größe wird basierend auf der Gesamtzahl der folgenden Elemente berechnet:</span><span class="sxs-lookup"><span data-stu-id="322e7-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="322e7-283">Aktive Benutzer im System</span><span class="sxs-lookup"><span data-stu-id="322e7-283">Active users in the system</span></span>

  - <span data-ttu-id="322e7-284">Aktive Benutzer in Chatrooms der jeweiligen Größe</span><span class="sxs-lookup"><span data-stu-id="322e7-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="322e7-285">Chatrooms der jeweiligen Größe, die ein einzelner Benutzer betritt</span><span class="sxs-lookup"><span data-stu-id="322e7-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="322e7-286">Für jeden Chatroom gibt die vorhergehende Kapazitätsplanungstabelle die Anzahl der Zugriffssteuerungseinträge an, die dem Chatroom zugeordnet sind, einschließlich der Einträge, die direkt dem Chatroom zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="322e7-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="322e7-287">Sie können den Zugriff auf einzelne Chatrooms mithilfe von Zugriffssteuerungslisten (Access Control Lists, ACLs) steuern.</span><span class="sxs-lookup"><span data-stu-id="322e7-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="322e7-288">Sie können den Zugriff auch auf Kategorienebene steuern.</span><span class="sxs-lookup"><span data-stu-id="322e7-288">You can also control access at the category level.</span></span> <span data-ttu-id="322e7-289">In einer ACL kann ein einzelner Zugriffssteuerungseintrag entweder eine Benutzergruppe sein (beispielsweise eine Sicherheitsgruppe, eine Verteilerliste oder ein einzelner Benutzer).</span><span class="sxs-lookup"><span data-stu-id="322e7-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="322e7-290">Sie können Zugriffssteuerungseinträge für Chatroom-Manager, Referenten und Mitglieder definieren.</span><span class="sxs-lookup"><span data-stu-id="322e7-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="322e7-291">Beachten Sie bei der Planung ihrer Strategie für die Verwaltung von Chatrooms, dass die Gesamtzahl der zulässigen Zugriffssteuerungseinträge 2 Millionen ist.</span><span class="sxs-lookup"><span data-stu-id="322e7-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="322e7-292">Wenn die berechneten Zugriffssteuerungseinträge 2 Millionen überschreiten, kann sich die Serverleistung erheblich vermindern.</span><span class="sxs-lookup"><span data-stu-id="322e7-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="322e7-293">Um dieses Problem zu vermeiden, stellen Sie nach Möglichkeit sicher, dass Ihre Zugriffssteuerungseinträge Benutzergruppen und nicht einzelne Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="322e7-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="322e7-294">Kapazitätsplanung für die Verwaltung des Chatroomzugriffs über eine Einladung</span><span class="sxs-lookup"><span data-stu-id="322e7-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="322e7-295">Sie können die folgende Tabelle zur Kapazitätsplanung verwenden, um die Anzahl der Einladungen zu verstehen, die der Server für beständigen Chat erstellt und in der Datenbank für beständigen Chat gespeichert wird, wenn er zum Senden von Einladungen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="322e7-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="322e7-296">Sie können Einladungen für die Kategorie verwalten, indem Sie auf der Seite mit den **Chatroom-Kategorieeinstellungen** im lync Server-Systemsteuerung oder mithilfe des Cmdlets Windows PowerShell **festlegen-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="322e7-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="322e7-297">Sie können Einladungen in einem Chatroom verwalten (entsprechend der Vorgehensweise der Kategorie), indem Sie die auf dem lync-Client gestartete **Raum Verwaltungs** Seite oder mithilfe eines Windows PowerShell-Cmdlets **festlegen-csPersistentChatRoom**verwenden.</span><span class="sxs-lookup"><span data-stu-id="322e7-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="322e7-298">Bei den Beispieldaten in der folgenden Tabelle wird davon ausgegangen, dass die Option **Einladungen** auf der Seite **chatroomeinstellungen** für 50 Prozent aller Chatrooms auf **Ja**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="322e7-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="322e7-299">Wenn der berechnete Wert für die Anzahl von Einladungen, die vom Server generiert werden, 1 Million überschreitet, kann sich die Serverleistung erheblich vermindern.</span><span class="sxs-lookup"><span data-stu-id="322e7-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="322e7-300">Um dieses Problem zu vermeiden, müssen Sie die Anzahl der Chatrooms minimieren, die zum Senden von Einladungen konfiguriert sind, oder die Anzahl der Benutzer einschränken, die Chatrooms beitreten können, die zum Senden von Einladungen konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="322e7-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="322e7-301">Beispiel für den Chatroomzugriff über eine Einladung</span><span class="sxs-lookup"><span data-stu-id="322e7-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="322e7-302">Kleine Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="322e7-303">Mittlere Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="322e7-304">Große Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="322e7-305">Gesamt</span><span class="sxs-lookup"><span data-stu-id="322e7-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322e7-306">Benutzer, die auf Chatroom zugreifen können</span><span class="sxs-lookup"><span data-stu-id="322e7-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="322e7-307">30 pro Zimmer</span><span class="sxs-lookup"><span data-stu-id="322e7-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="322e7-308">150 pro Zimmer</span><span class="sxs-lookup"><span data-stu-id="322e7-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="322e7-309">16.000 pro Zimmer</span><span class="sxs-lookup"><span data-stu-id="322e7-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-310">Prozentsatz der Räume mit Einladungen</span><span class="sxs-lookup"><span data-stu-id="322e7-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="322e7-311">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-311">50%</span></span></p></td>
<td><p><span data-ttu-id="322e7-312">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-312">50%</span></span></p></td>
<td><p><span data-ttu-id="322e7-313">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-314">Für das Senden von Einladungen konfigurierte Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="322e7-315"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="322e7-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="322e7-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="322e7-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-318">Benutzer, die auf den Chatroom zugreifen können</span><span class="sxs-lookup"><span data-stu-id="322e7-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="322e7-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="322e7-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="322e7-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="322e7-321"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="322e7-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-322">Vom Server für beständigen Chat generierte Einladungen</span><span class="sxs-lookup"><span data-stu-id="322e7-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="322e7-323">960.000</span><span class="sxs-lookup"><span data-stu-id="322e7-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="322e7-324">120.000</span><span class="sxs-lookup"><span data-stu-id="322e7-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="322e7-325">80,000</span><span class="sxs-lookup"><span data-stu-id="322e7-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="322e7-326">1.160.000</span><span class="sxs-lookup"><span data-stu-id="322e7-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-327">Maximal zulässige Anzahl von Einladungen</span><span class="sxs-lookup"><span data-stu-id="322e7-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="322e7-328">2 Millionen</span><span class="sxs-lookup"><span data-stu-id="322e7-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-329">Modell 1 – beginnen mit der erwarteten Anzahl von Nachrichten pro Raum pro Tag</span><span class="sxs-lookup"><span data-stu-id="322e7-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-330">Chat Rate pro Zimmer (pro Tag)</span><span class="sxs-lookup"><span data-stu-id="322e7-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="322e7-331">50</span><span class="sxs-lookup"><span data-stu-id="322e7-331">50</span></span></p></td>
<td><p><span data-ttu-id="322e7-332">500</span><span class="sxs-lookup"><span data-stu-id="322e7-332">500</span></span></p></td>
<td><p><span data-ttu-id="322e7-333">100</span><span class="sxs-lookup"><span data-stu-id="322e7-333">100</span></span></p></td>
<td><p><span data-ttu-id="322e7-334">650</span><span class="sxs-lookup"><span data-stu-id="322e7-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-335">Chatrate (pro Sekunde) in allen Räumen</span><span class="sxs-lookup"><span data-stu-id="322e7-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-336">55,56</span><span class="sxs-lookup"><span data-stu-id="322e7-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="322e7-337">18,52</span><span class="sxs-lookup"><span data-stu-id="322e7-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="322e7-338">0,03</span><span class="sxs-lookup"><span data-stu-id="322e7-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="322e7-339">74</span><span class="sxs-lookup"><span data-stu-id="322e7-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-340">Modell 2 – Start mit der Anzahl von Nachrichten, die pro Benutzer pro Tag bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="322e7-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-341">Chat Rate pro Benutzer pro Tag</span><span class="sxs-lookup"><span data-stu-id="322e7-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="322e7-342">15 </span><span class="sxs-lookup"><span data-stu-id="322e7-342">15</span></span></p></td>
<td><p><span data-ttu-id="322e7-343">5 </span><span class="sxs-lookup"><span data-stu-id="322e7-343">5</span></span></p></td>
<td><p><span data-ttu-id="322e7-344">0,1</span><span class="sxs-lookup"><span data-stu-id="322e7-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="322e7-345">20</span><span class="sxs-lookup"><span data-stu-id="322e7-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-346">Chat Rate pro Zimmer (pro Tag)</span><span class="sxs-lookup"><span data-stu-id="322e7-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="322e7-347">38</span><span class="sxs-lookup"><span data-stu-id="322e7-347">38</span></span></p></td>
<td><p><span data-ttu-id="322e7-348">375</span><span class="sxs-lookup"><span data-stu-id="322e7-348">375</span></span></p></td>
<td><p><span data-ttu-id="322e7-349">800</span><span class="sxs-lookup"><span data-stu-id="322e7-349">800</span></span></p></td>
<td><p><span data-ttu-id="322e7-350">1.213</span><span class="sxs-lookup"><span data-stu-id="322e7-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-351">Chatrate (pro Sekunde) in allen Räumen</span><span class="sxs-lookup"><span data-stu-id="322e7-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-352">41,67</span><span class="sxs-lookup"><span data-stu-id="322e7-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="322e7-353">13,89</span><span class="sxs-lookup"><span data-stu-id="322e7-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="322e7-354">0,28</span><span class="sxs-lookup"><span data-stu-id="322e7-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="322e7-355">56</span><span class="sxs-lookup"><span data-stu-id="322e7-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="322e7-356">Server Leistung für beständigen Chat-Benutzermodell</span><span class="sxs-lookup"><span data-stu-id="322e7-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="322e7-357">In der folgenden Tabelle wird das Benutzermodell für den Server für beständigen Chat beschrieben.</span><span class="sxs-lookup"><span data-stu-id="322e7-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="322e7-358">Sie bildet die Grundlage für die Kapazitäts Planungsanforderungen und stellt eine typische Organisation mit 80.000 gleichzeitigen Benutzern auf vier Servern dar.</span><span class="sxs-lookup"><span data-stu-id="322e7-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="322e7-359">Server Leistung für beständigen Chat-Benutzermodell</span><span class="sxs-lookup"><span data-stu-id="322e7-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322e7-360">Anzahl der verbundenen aktiven Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="322e7-361">80,000</span><span class="sxs-lookup"><span data-stu-id="322e7-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-362">Anzahl der Server Dienstinstanzen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="322e7-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="322e7-363">4 </span><span class="sxs-lookup"><span data-stu-id="322e7-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-364">Umfang kleiner Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-365">30 Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-366">Umfang mittelgroßer Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-367">150 Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-368">Umfang großer Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-369">16.000 Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-370">Gesamtzahl von Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-371">33.077</span><span class="sxs-lookup"><span data-stu-id="322e7-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-372">Anzahl von kleinen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-373">32.000</span><span class="sxs-lookup"><span data-stu-id="322e7-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-374">Anzahl von mittelgroßen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-375">1.067</span><span class="sxs-lookup"><span data-stu-id="322e7-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-376">Anzahl von großen Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-377">10 </span><span class="sxs-lookup"><span data-stu-id="322e7-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-378">Gesamtzahl von Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-379">16 </span><span class="sxs-lookup"><span data-stu-id="322e7-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-380">Anzahl von kleinen Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-381">12 </span><span class="sxs-lookup"><span data-stu-id="322e7-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-382">Anzahl von mittelgroßen Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-383">2</span><span class="sxs-lookup"><span data-stu-id="322e7-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-384">Anzahl von großen Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-385">2</span><span class="sxs-lookup"><span data-stu-id="322e7-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-386">Anzahl der hinzugefügten Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-387">24</span><span class="sxs-lookup"><span data-stu-id="322e7-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-388">Maximale Beitrittsrate</span><span class="sxs-lookup"><span data-stu-id="322e7-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="322e7-389">10/Sekunde</span><span class="sxs-lookup"><span data-stu-id="322e7-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-390">Gesamtchatrate</span><span class="sxs-lookup"><span data-stu-id="322e7-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="322e7-391">24/Sekunde</span><span class="sxs-lookup"><span data-stu-id="322e7-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-392">Chatrate für kleine Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-393">0.00/Second</span><span class="sxs-lookup"><span data-stu-id="322e7-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-394">Chatrate für mittelgroße Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-395">1.67/Sekunde</span><span class="sxs-lookup"><span data-stu-id="322e7-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-396">Chatrate für große Chatrooms</span><span class="sxs-lookup"><span data-stu-id="322e7-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="322e7-397">~ 0.15/Second</span><span class="sxs-lookup"><span data-stu-id="322e7-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-398">Prozentsatz von Chatrooms, die für Einladungen konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="322e7-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="322e7-399">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-400">Prozentsatz von direkten Mitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="322e7-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="322e7-401">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-402">Prozentsatz von Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="322e7-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="322e7-403">50%</span><span class="sxs-lookup"><span data-stu-id="322e7-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-404">Durchschnittliche Anzahl von Vorgänger Zuordnungen in Active Directory-Domänendienste</span><span class="sxs-lookup"><span data-stu-id="322e7-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="322e7-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="322e7-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-406">Anzahl von abonnierten Kontakten pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-407">80</span><span class="sxs-lookup"><span data-stu-id="322e7-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-408">Durchschnittliche Anzahl der Endpunkte pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-409">1,5</span><span class="sxs-lookup"><span data-stu-id="322e7-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-410">Durchschnittliche Anzahl von sichtbaren Chatrooms pro Endpunkt</span><span class="sxs-lookup"><span data-stu-id="322e7-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="322e7-411">1,5</span><span class="sxs-lookup"><span data-stu-id="322e7-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-412">Durchschnittliche Anzahl von sichtbaren Chatrooms pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-413">2,25 (50% für 1 Zimmer und 50% für 2 Zimmer); Bis zu 6 geöffnete Zimmer, eine pro Monitor</span><span class="sxs-lookup"><span data-stu-id="322e7-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-414">Anzahl von Teilnehmern, die pro Intervall abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="322e7-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="322e7-415">25 pro sichtbarem Chatroom</span><span class="sxs-lookup"><span data-stu-id="322e7-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-416">Länge des Abrufintervalls</span><span class="sxs-lookup"><span data-stu-id="322e7-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="322e7-417">5 Minuten</span><span class="sxs-lookup"><span data-stu-id="322e7-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-418">Anzahl von Teilnehmern, die pro Sekunde abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="322e7-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="322e7-419">15,000</span><span class="sxs-lookup"><span data-stu-id="322e7-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322e7-420">Anzahl von Änderungen des Anwesenheitsstatus pro Stunde und Benutzer</span><span class="sxs-lookup"><span data-stu-id="322e7-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="322e7-421">6 </span><span class="sxs-lookup"><span data-stu-id="322e7-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322e7-422">Anzahl von Änderungen des Anwesenheitsstatus pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="322e7-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="322e7-423">133,33</span><span class="sxs-lookup"><span data-stu-id="322e7-423">133.33</span></span></p></td>
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


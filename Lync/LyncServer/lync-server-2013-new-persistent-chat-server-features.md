---
title: 'Lync Server 2013: Neue Funktionen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d5cd0b8197b64abfc0761dfb333f338b507ff7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="03b1f-102">Neue Funktionen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03b1f-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03b1f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="03b1f-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="03b1f-104">Lync Server 2013, beständiger Chat Server ermöglicht Ihnen, an mehrteiligen, themenbasierten Konversationen teilzunehmen, die im Laufe der Zeit fortbestehen.</span><span class="sxs-lookup"><span data-stu-id="03b1f-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="03b1f-105">Der beständige Chat Server kann Ihrer Organisation helfen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="03b1f-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="03b1f-106">Verbessern der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams</span><span class="sxs-lookup"><span data-stu-id="03b1f-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="03b1f-107">Erweitern des Informations Bewusstseins und der Teilnahme</span><span class="sxs-lookup"><span data-stu-id="03b1f-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="03b1f-108">Verbessern der Kommunikation mit ihrer erweiterten Organisation</span><span class="sxs-lookup"><span data-stu-id="03b1f-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="03b1f-109">Reduzieren der Informationsüberlastung</span><span class="sxs-lookup"><span data-stu-id="03b1f-109">Reduce information overload</span></span>

  - <span data-ttu-id="03b1f-110">Verbessern des Informations Bewusstseins</span><span class="sxs-lookup"><span data-stu-id="03b1f-110">Improve information awareness</span></span>

  - <span data-ttu-id="03b1f-111">Verbessern der Verbreitung wichtiger Kenntnisse und Informationen</span><span class="sxs-lookup"><span data-stu-id="03b1f-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="03b1f-112">Lync Server 2013, beständiger Chat Server steht in Microsoft Office 365 nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="03b1f-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="03b1f-113">Zu diesem Zeitpunkt steht er nur für lokale lync 2013-Kunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="03b1f-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="03b1f-114">In lync 2013 ist die Funktionalität des beständigen Chats in den lync 2013-Client integriert.</span><span class="sxs-lookup"><span data-stu-id="03b1f-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="03b1f-115">Daher haben Benutzer Zugriff auf Instant Messaging/Anwesenheit, Audio/Video, Konferenzen und beständigen Chat alle im lync 2013-Client.</span><span class="sxs-lookup"><span data-stu-id="03b1f-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="03b1f-116">Weitere Informationen zum lync 2013-Client finden Sie unter <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span><span class="sxs-lookup"><span data-stu-id="03b1f-116">For more information about the Lync 2013 client, see <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="03b1f-117">In diesem Thema werden die Funktionsänderungen zwischen der neuen Version von lync Server 2013, dem beständigen Chat Server und der vorherigen Version (Microsoft lync Server 2010, Gruppen Chat) beschrieben, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="03b1f-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="03b1f-118">Bereitstelleneiner administrativen Funktionalität in der lync Server-Systemsteuerung und eliminieren des Administrator Tools für Gruppenchats</span><span class="sxs-lookup"><span data-stu-id="03b1f-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="03b1f-119">Integrieren von Konfigurationseinstellungen für beständigen Chat Server in den Topologie-Generator durch Eliminierung des Gruppen-Chat-Konfigurationstools</span><span class="sxs-lookup"><span data-stu-id="03b1f-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="03b1f-120">Einfache Migration und Upgrade von vorherigen Versionen des beständigen Chat Servers</span><span class="sxs-lookup"><span data-stu-id="03b1f-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="03b1f-121">Bereitstellen von Hochverfügbarkeits-und Disaster Recovery-Lösungen</span><span class="sxs-lookup"><span data-stu-id="03b1f-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="03b1f-122">Weitere Informationen zur neuesten Version des beständigen Chat Servers finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="03b1f-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="03b1f-123">In <http://go.microsoft.com/fwlink/p/?linkid=270945> der Hilfe für beständigen Chat finden Sie eine detaillierte Liste der beständigen Chat Features, ihre Funktionsweise und ihre Verwendung während des beständigen Chat Servers.</span><span class="sxs-lookup"><span data-stu-id="03b1f-123">The Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="03b1f-124">Der [Server für die Planung des beständigen Chats in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation, [Bereitstellen des beständigen Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in der Bereitstellungsdokumentation, [Migration von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppen-Chat mit lync Server 2013, beständiger Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in der Migrationsdokumentation und [Verwalten von lync Server 2013, beständiger Chat Server](managing-lync-server-2013-persistent-chat-server.md) in der Betriebsdokumentation, die alle Anleitungen für Einrichten des beständigen Chat Servers</span><span class="sxs-lookup"><span data-stu-id="03b1f-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="03b1f-125">Mit der Datei "beständiger Chat Server Documentation. msi" (Windows Installer-Datei) können Benutzer auf eine umfassende offlinedokumentation über den Server für beständigen Chat zugreifen.</span><span class="sxs-lookup"><span data-stu-id="03b1f-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="03b1f-126">Änderungen an wichtigen Topologien für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="03b1f-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="03b1f-127">Die folgenden allgemeinen Änderungen für beständigen Chat Server sind:</span><span class="sxs-lookup"><span data-stu-id="03b1f-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="03b1f-128">Der beständige Chat Server ist nun eine Serverrolle.</span><span class="sxs-lookup"><span data-stu-id="03b1f-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="03b1f-129">In Microsoft lync Server 2010 war der Gruppen-Chat Server eine vertrauenswürdige Anwendung eines Drittanbieters für Microsoft lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="03b1f-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="03b1f-130">Beständiger Chat kann ihrer lync Server 2013-Topologie mithilfe des Topologie-Generators hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="03b1f-131">In lync Server 2013 wird die Funktion des beständigen Chat Servers mithilfe von drei neuen Serverrollen implementiert:</span><span class="sxs-lookup"><span data-stu-id="03b1f-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="03b1f-132">**PersistentChatService:** Dies ist die Front-End-Rolle für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="03b1f-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="03b1f-133">In Standard Edition-Bereitstellungen wird die Server Dienst Rolle des beständigen Chats auf dem Standard Edition-Server, der von Bootstrapper bereitgestellt wird, wie jede andere lync-Serverrolle verwendet.</span><span class="sxs-lookup"><span data-stu-id="03b1f-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="03b1f-134">In Enterprise Edition-Bereitstellungen wird die Funktion des beständigen Chats auf eigenständigen Computern nach Bootstrapper wie jede andere lync-Server Rolle bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="03b1f-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="03b1f-135">**PersistentChatStore:** Back-End-Server, der der Inhaltsdatenbank für beständigen Chat entspricht, in der alle Chatinhalte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="03b1f-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="03b1f-136">**PersistentChatComplianceStore:** Back-End-Server Rolle, die der Compliance-Datenbank für beständigen Chat entspricht, in der alle Compliance-Ereignisse gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="03b1f-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="03b1f-137">Diese Serverrollen für beständigen Chat sind optional und werden nur von Kunden installiert, die umfassende Funktionen für den beständigen Chat Server wünschen.</span><span class="sxs-lookup"><span data-stu-id="03b1f-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="03b1f-138">Die Rolle **PersistentChatComplianceStore** ist nur erforderlich, wenn Sie die Compliance für beständigen Chat bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="03b1f-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="03b1f-139">Die **PersistentChatService** -Rolle führt zwei Dienste aus:</span><span class="sxs-lookup"><span data-stu-id="03b1f-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="03b1f-140">Beständiger Chat Dienst</span><span class="sxs-lookup"><span data-stu-id="03b1f-140">Persistent Chat service</span></span>

  - <span data-ttu-id="03b1f-141">Kompatibilitätsdienst für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="03b1f-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="03b1f-142">Wenn diese Dienste auf jedem beständigen Chat Server ausgeführt werden, bietet diese Dienste in einem persistenten Chat Serverpool eine höhere Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="03b1f-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="03b1f-143">Um den Dateiupload und-Download in beständige Chatrooms zu unterstützen, enthält der beständige Chat Server zudem einen Webdienst.</span><span class="sxs-lookup"><span data-stu-id="03b1f-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="03b1f-144">Zuvor war dieser Dienst auf dem Server für beständigen Chat, dem Front-End-Server und den erforderlichen Internet Informationsdiensten (IIS) installiert, um als Voraussetzung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="03b1f-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="03b1f-145">Im lync Server 2013-Server für beständigen Chat befindet sich der Web Servicedatei Upload/-Download mit dem lync Server 2013-Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="03b1f-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="03b1f-146">Als Nebeneffekt ist Internet Information Services (IIS) nicht mehr eine Voraussetzung für beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="03b1f-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="03b1f-147">Der Webdienst für Datei Upload/-Download wird im Internet Informationsdienste (IIS)-Manager als **PersistentChat** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="03b1f-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="03b1f-148">Die <STRONG>PersistentChatService</STRONG> -Rolle kann nur auf dem gleichen Server wie ein lync Server&nbsp;2013-Front-End-Server ausgeführt werden, wenn der Front&nbsp;-End-Server ein Standard Edition-Front-End-Server ist.</span><span class="sxs-lookup"><span data-stu-id="03b1f-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="03b1f-149">Die <STRONG>PersistentChatService</STRONG> -Rolle kann nicht unabhängig von einem lync Server&nbsp;2013-Front-End-Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="03b1f-150">Sie kann nur im Kontext einer lync Server 2013-Bereitstellung installiert werden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="03b1f-151">Im beständigen Chat Server wurde der Suchdienst eliminiert.</span><span class="sxs-lookup"><span data-stu-id="03b1f-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="03b1f-152">In lync Server 2010, Gruppen-Chat, wurde der Nachschlage Dienst auf jedem Front-End-Server des Gruppen-Chat Servers ausgeführt und auf einen der Kanalserver geroutet.</span><span class="sxs-lookup"><span data-stu-id="03b1f-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="03b1f-153">Lync Server 2013 basiert auf dem Routing mithilfe von Kontaktobjekten, wobei jeder beständige Chat Serverpool durch ein Kontaktobjekt dargestellt wird, das von den lync Server-Front-End-Servern zum Identifizieren und Weiterleiten von Anforderungen an einen geeigneten beständigen Chat Serverpool verwendet wird, und einer der Computer, auf dem der beständige Chat Server im Pool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03b1f-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="03b1f-154">In lync Server 2013 sind Kompatibilitätsdienst Änderungen vorhanden:</span><span class="sxs-lookup"><span data-stu-id="03b1f-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="03b1f-155">In lync Server 2010 wurde der Kompatibilitätsdienst eigenständig (nicht in der Lage) und nur auf einem einzelnen Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03b1f-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="03b1f-156">Der Kompatibilitätsdienst wird nun neben dem beständigen Chatdienst auf allen Front-End-Servern des beständigen Chats ausgeführt und bietet dadurch eine höhere Verfügbarkeit in einem persistenten Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="03b1f-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="03b1f-157">Ein einzelner Kompatibilitätsadapter kann so konfiguriert werden, dass Daten aus der Kompatibilitätsdatenbank und einem anderen System (XML-Datei, Exchange-gehostete Archive usw.) extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="03b1f-158">Der beständige Chat Server enthält einen XML-Adapter.</span><span class="sxs-lookup"><span data-stu-id="03b1f-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="03b1f-159">Die Warteschlange für Message Queuing (auch als MSMQ bezeichnet), die vom beständigen Chatdienst und dem Kompatibilitätsdienst auf jedem beständigen Chat Server-Front-End-Server freigegeben wird, ist jetzt eine private Warteschlange, die nur von den beiden Diensten freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="03b1f-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="03b1f-160">Alle Konformitäts Dienste schreiben in dieselbe Compliance-Back-End-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="03b1f-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="03b1f-161">Sie haben auch alle aus dieser Datenbank gelesen, um die Daten an Ihre Instanz des Adapters zu senden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="03b1f-162">Der Compliance-Back-End-Server wird als neue Back-End-Serverrolle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="03b1f-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03b1f-163">Wie in früheren Versionen werden alle Kompatibilitätsdaten nur einmal verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="03b1f-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="03b1f-164">Die Daten können von allen Adapter Instanzen verarbeitet werden, die vom Kompatibilitätsdienst aufgerufen werden, der auf den verschiedenen lync Server 2013-, persistent Chat Server-Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03b1f-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="03b1f-165">In einem beständigen Chat Server können alle Adapter Instanzen die Daten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="03b1f-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03b1f-166">Informationen zum Installieren von Message Queuing finden Sie unter <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Installieren von Betriebssystemen und der erforderlichen Software auf Servern für lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="03b1f-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="03b1f-167">In lync Server 2013 gibt es Verbesserungen bei der Hochverfügbarkeits-und Disaster Recovery:</span><span class="sxs-lookup"><span data-stu-id="03b1f-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="03b1f-168">Verbesserungen bei hoher Verfügbarkeit: die SQL Server-Spiegelung wird verwendet, um eine höhere Verfügbarkeit für die Inhaltsdatenbank des beständigen Chat Servers und die Datenbank für beständigen Chat in einem Rechenzentrum (in-Site) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="03b1f-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="03b1f-169">Verbesserungen bei der Disaster Recovery: der beständige Chat Server unterstützt eine ausgestreckte Pool Architektur, die es ermöglicht, einen einzelnen beständigen Chat Serverpool über zwei Standorte (also einen einzigen logischen Pool in der Topologie) zu dehnen, wobei die Server im Pool physisch befindet sich über zwei Standorte).</span><span class="sxs-lookup"><span data-stu-id="03b1f-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="03b1f-170">Der SQL Server-Protokollversand wird für die websiteübergreifende Notfallwiederherstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="03b1f-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="03b1f-171">Weitere Informationen zu Hochverfügbarkeits-und Disaster Recovery finden Sie unter Konfigurieren des beständigen [Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="03b1f-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="03b1f-172">Wichtige Änderungen bei der Verwaltung und Verwaltung für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="03b1f-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="03b1f-173">Lync Server 2013 hat das Verwalten und Verwalten von beständigen Chat Servern vereinfacht, indem Sie Folgendes bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="03b1f-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="03b1f-174">Einheitliche Verwaltung und Verwaltung</span><span class="sxs-lookup"><span data-stu-id="03b1f-174">Unified administration and management.</span></span> <span data-ttu-id="03b1f-175">Lync Server 2013 vereinfacht das Verwalten und Verwalten des beständigen Chat Servers mithilfe von Tools, die lync-Administratoren bereits vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="03b1f-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="03b1f-176">Der Server für beständigen Chat umfasst eine Benutzeroberflächen-Administratoroberfläche, die in die lync Server-Systemsteuerung integriert ist und Leistungsprobleme mit den vorherigen Versionen der Benutzeroberfläche des Gruppen-Chat Servers behebt.</span><span class="sxs-lookup"><span data-stu-id="03b1f-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="03b1f-177">Darüber hinaus enthält der Server für beständigen Chat eine Sammlung von Windows PowerShell-Cmdlets zum Verwalten und verwalten beständiger Chat Server Kategorien, beständiger Chatrooms (einschließlich Löschen von Räumen und bereinigen veralteter Inhalte) sowie Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="03b1f-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="03b1f-178">Vereinfachtes Verwaltungsmodell</span><span class="sxs-lookup"><span data-stu-id="03b1f-178">Simplified administration model.</span></span> <span data-ttu-id="03b1f-179">Lync Server 2013 hat das Server Modell für beständigen Chat geändert und vereinfacht, indem es die folgenden wichtigen Kundenanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="03b1f-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="03b1f-180">Entfernen Sie die komplexen geschachtelten Hierarchien von Bereichen und Kategorien.</span><span class="sxs-lookup"><span data-stu-id="03b1f-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="03b1f-181">Unterstützung zum Definieren von Verweigerungslisten sowie zulässiger Listen (Bereiche) für aktuelle MindAlign-Kunden, die beabsichtigen, zum Server für beständigen Chat zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="03b1f-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="03b1f-182">Worin unterscheiden sich die Benutzerrollen aus früheren Gruppen-Chat Server Versionen?</span><span class="sxs-lookup"><span data-stu-id="03b1f-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="03b1f-183">Lync Server 2010, Gruppen-Chat hatte eine Benutzeradministratorrolle, eine Chatroom-Administratorrolle und eine lync Server-Administratorrolle, die Add-Ins verwalten konnte. beständiger Chat Server bietet einfach eine permanente Chat Administratorrolle (ähnlich wie andere lync Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC)).</span><span class="sxs-lookup"><span data-stu-id="03b1f-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="03b1f-184">Jeder, der Mitglied dieser RBAC-Rolle ist, kann Chatrooms, Add-Ins und Kategorien verwalten (und dadurch den Benutzer Zugriff für diese Kategorien gewinnen) und die Konfiguration des beständigen Chat Server Pools.</span><span class="sxs-lookup"><span data-stu-id="03b1f-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="03b1f-185">Welche Unterschiede gibt es zu Chatroom-Kategorien aus früheren Gruppen-Chat Server Versionen?</span><span class="sxs-lookup"><span data-stu-id="03b1f-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="03b1f-186">Chatroom-Kategorien können nicht mehr geschachtelt werden, und die Stammkategorie kann nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="03b1f-187">AllowedMembers/DeniedMembers enthalten einen Bereich, der in Legacy Gruppen-Chat Server Versionen verwendet wurde (mit der Ausnahme, dass die Angabe einer verweigerten Liste nicht unterstützt wurde).</span><span class="sxs-lookup"><span data-stu-id="03b1f-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="03b1f-188">Bereiche können nicht mehr überschrieben werden, da es keine geschachtelten Kategorien gibt.</span><span class="sxs-lookup"><span data-stu-id="03b1f-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="03b1f-189">Ein Administrator für beständigen Chat in lync Server 2013 kann Chatroom-Kategorien erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="03b1f-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="03b1f-190">Im Rahmen des Erstellens und Verwaltens von Chatroom-Kategorien kann ein beständiger Chat-Administrator Prinzipale (Active Directory-Gruppen/-Container/-Benutzer) konfigurieren, die Zugriff auf Mitglieder/Ersteller von Chatrooms einer bestimmten Kategorie haben.</span><span class="sxs-lookup"><span data-stu-id="03b1f-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="03b1f-191">Ein Administrator des beständigen Chats kann auch DeniedMembers zu einer Kategorie hinzufügen, und diese werden explizite Ausnahmen für die zulässige Liste.</span><span class="sxs-lookup"><span data-stu-id="03b1f-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="03b1f-192">Einträge unter „DeniedMembers“ haben Vorrang vor Einträgen unter „AllowedMembers“.</span><span class="sxs-lookup"><span data-stu-id="03b1f-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="03b1f-193">Was unterscheidet sich von den Chatroom-Eigenschaften aus früheren Gruppen-Chat Server Versionen?</span><span class="sxs-lookup"><span data-stu-id="03b1f-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="03b1f-194">Ein neues Konzept offener Chatrooms ist in lync Server 2013, beständiger Chat Server, vorhanden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="03b1f-195">Alle zulässigen Mitglieder können dem Chatroom beitreten, ohne eine exklusive Mitgliedschaft zu haben.</span><span class="sxs-lookup"><span data-stu-id="03b1f-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="03b1f-196">Die folgenden Chatroom-Eigenschaften, die in früheren Versionen des beständigen Chat Servers enthalten waren, wurden eliminiert:</span><span class="sxs-lookup"><span data-stu-id="03b1f-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="03b1f-197">Thema: ein Raum hat jetzt nur eine Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="03b1f-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="03b1f-198">Neue Mitgliederliste erstellen: auf dem Server für beständigen Chat beginnen alle Chatrooms mit einer leeren Mitgliedschaft (und können eine Mitgliedschaft maximieren, die den zulässigen Mitgliedern entspricht).</span><span class="sxs-lookup"><span data-stu-id="03b1f-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="03b1f-199">Dateiupload: verwendet als eine Einstellung pro Chatroom, um zu steuern, ob Dateiupload/-Downloads zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="03b1f-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="03b1f-200">Damit wird nun nur die Kategorieebene festgesetzt und gilt für alle Räume in dieser Kategorie.</span><span class="sxs-lookup"><span data-stu-id="03b1f-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="03b1f-201">Chat-Protokoll: verwendet als eine Einstellung pro Chatroom, um zu steuern, ob das Chat-Protokoll aktiviert wurde, aber jetzt nur auf der Kategorieebene festgelegt ist und für alle Räume in dieser Kategorie gilt.</span><span class="sxs-lookup"><span data-stu-id="03b1f-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="03b1f-202">Einladungen: ein Raum erbt immer die Einstellung Einladungen für die Kategorie; oder es kann auf dem Raum ausgeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="03b1f-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="03b1f-203">Ein Raum kann Einladungen nicht aktivieren, wenn die Kategorie zuvor auf Einladungen aus eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="03b1f-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="03b1f-204">Was unterscheidet sich von den Richtlinien aus früheren Gruppen-Chat Server Versionen?</span><span class="sxs-lookup"><span data-stu-id="03b1f-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="03b1f-205">Der Server für beständigen Chat hat eine neue lync-Richtlinie mit beständigem Chat, pro Benutzer/Pool/Website/globale Einstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="03b1f-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="03b1f-206">Im lync 2013-Client ist die Umgebung für beständigen Chat nur für Benutzer verfügbar, die durch Richtlinie für beständigen Chat aktiviert sind (entweder direkt oder über die Einstellung Pool/Website/Global).</span><span class="sxs-lookup"><span data-stu-id="03b1f-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="03b1f-207">In früheren Versionen des Gruppen Chat Servers wurden keine Richtlinien in die lync-Server Richtlinien integriert.</span><span class="sxs-lookup"><span data-stu-id="03b1f-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="03b1f-208">Auf der Basis pro Benutzer und pro Kategorie/Raum können Sie mithilfe des Features "Dateien pro Benutzer **hochladen** " einen Benutzer Administrator, einen Chatroom-Administrator oder die Möglichkeit zum Hochladen von Dateien durch den Benutzer festlegen.</span><span class="sxs-lookup"><span data-stu-id="03b1f-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="03b1f-209">Die **Datei Upload** -Funktion des beständigen Chat Servers ist nur pro Kategorie.</span><span class="sxs-lookup"><span data-stu-id="03b1f-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="03b1f-210">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="03b1f-210">Logging</span></span>

<span data-ttu-id="03b1f-211">Die Protokollierung für den Server für beständigen Chat und System Center Operations Manager ist in die lync Server 2013-Ablaufverfolgungsprotokollierung integriert.</span><span class="sxs-lookup"><span data-stu-id="03b1f-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03b1f-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03b1f-212">See Also</span></span>


[<span data-ttu-id="03b1f-213">Planen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03b1f-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


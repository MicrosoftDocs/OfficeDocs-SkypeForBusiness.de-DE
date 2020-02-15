---
title: 'Lync Server 2013: Funktionsweise des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad299ffbe351ff8e8356c535baccf65c00cf0644
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="34a91-102">Funktionsweise von persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34a91-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34a91-103">_**Letztes Änderungsstand des Themas:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="34a91-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="34a91-104">Lync Server 2013 können Sie mit dem Server für beständigen Chat an mehrteiligen, themenbasierten Unterhaltungen teilnehmen, die im Laufe der Zeit beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="34a91-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="34a91-105">Der Server für beständigen Chat kann Ihrer Organisation dabei helfen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="34a91-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="34a91-106">Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams</span><span class="sxs-lookup"><span data-stu-id="34a91-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="34a91-107">Förderung von Informationsbewusstsein und aktiver Teilnahme</span><span class="sxs-lookup"><span data-stu-id="34a91-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="34a91-108">Verbesserung der Kommunikation über alle Unternehmensbereiche hinweg</span><span class="sxs-lookup"><span data-stu-id="34a91-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="34a91-109">Verringerung der Informationsüberlastung</span><span class="sxs-lookup"><span data-stu-id="34a91-109">Reduce information overload</span></span>

  - <span data-ttu-id="34a91-110">Verbesserung des Informationsbewusstseins</span><span class="sxs-lookup"><span data-stu-id="34a91-110">Improve information awareness</span></span>

  - <span data-ttu-id="34a91-111">Gezielte Weitergabe wichtigen Wissens und wichtiger Informationen</span><span class="sxs-lookup"><span data-stu-id="34a91-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="34a91-112">Sie können den Server für beständigen Chat mit lync Server 2013 als optionale Rolle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="34a91-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="34a91-113">Die Dienste für beständigen Chat werden in einem dedizierten Pool ausgeführt, und ein Server Pool für beständigen Chat hängt von einem lync Server Pool ab, um Nachrichten an ihn weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="34a91-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="34a91-114">Clients verwenden eXtensible Chat Communication Over SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="34a91-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="34a91-115">Die lync Server-Front-End-Server sind so konfiguriert, dass der Datenverkehr an einen Server Pool für beständigen Chat weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="34a91-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="34a91-116">Allgemeine Architektur</span><span class="sxs-lookup"><span data-stu-id="34a91-116">High-Level Architecture</span></span>

<span data-ttu-id="34a91-117">Die folgenden Diagramme bieten allgemeine Perspektiven der Architektur und der Dienste für den Server für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="34a91-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="34a91-118">**Allgemeine Architektur der permanenten Chatserver**</span><span class="sxs-lookup"><span data-stu-id="34a91-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="34a91-119">![Server Architektur für beständigen Chat.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Server Architektur für beständigen Chat.")</span><span class="sxs-lookup"><span data-stu-id="34a91-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="34a91-120">**Allgemeine Dienste der permanenten Chatserver**</span><span class="sxs-lookup"><span data-stu-id="34a91-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="34a91-121">![Server Komponenten für beständigen Chat.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Server Komponenten für beständigen Chat.")</span><span class="sxs-lookup"><span data-stu-id="34a91-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="34a91-122">Auf den Front-End-Servern für beständigen Chat Server werden zwei Dienste ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="34a91-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="34a91-123">Beständiger Chat (Kanal)</span><span class="sxs-lookup"><span data-stu-id="34a91-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="34a91-124">Compliance</span><span class="sxs-lookup"><span data-stu-id="34a91-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="34a91-125">Beständiger Chat- (Kanal-) Dienst</span><span class="sxs-lookup"><span data-stu-id="34a91-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="34a91-126">Der Dienst für beständigen Chat (Kanal) ist der Hauptdienst, der für den Server für beständigen Chat verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="34a91-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="34a91-127">Dieser Dienst bietet folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="34a91-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="34a91-128">Annahme eingehender Nachrichten</span><span class="sxs-lookup"><span data-stu-id="34a91-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="34a91-129">Registrieren und Auflisten von Online-Teilnehmern in einem beständigen Chatroom</span><span class="sxs-lookup"><span data-stu-id="34a91-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="34a91-130">Neuübermittlung von Nachrichten an andere Abonnenten des Kanals</span><span class="sxs-lookup"><span data-stu-id="34a91-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="34a91-131">Implementierung der Logik zur Kanalverwaltung, Chatroomeinladung, Suche und Benachrichtigungen über neue Inhalte</span><span class="sxs-lookup"><span data-stu-id="34a91-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="34a91-132">Der Dienst für beständigen Chat (Kanal) speichert und greift auf Chatroom-Inhalte und andere Systemmetadaten (Autorisierungsregeln usw.) mithilfe des Speichers für beständigen Chat zu.</span><span class="sxs-lookup"><span data-stu-id="34a91-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="34a91-133">In diesem Dienst werden Dateien gespeichert, die in Chatrooms im Dateispeicher für beständigen Chat hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="34a91-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="34a91-134">Kompatibilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="34a91-134">Compliance Service</span></span>

<span data-ttu-id="34a91-135">Der Kompatibilitätsdienst ist eine optionale Komponente des Servers für beständigen Chat und ist für das Archivieren von Chat Inhalten und Ereignissen im Compliance-Speicher für beständigen Chat verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="34a91-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="34a91-136">Wenn Ihre Organisation über Regelungen verfügt, bei denen die Aktivität für beständigen Chat archiviert werden muss, können Sie den optionalen Kompatibilitätsdienst für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="34a91-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="34a91-137">Der Kompatibilitätsdienst wird auf jedem Server für beständigen Chat in einem Pool für beständigen Chat installiert.</span><span class="sxs-lookup"><span data-stu-id="34a91-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="34a91-138">Bei der Konfiguration von beständigen Chat Servern werden Benutzeraktivitäten wie das Hinzufügen und verlassen von Räumen sowie das Veröffentlichen und Lesen von Nachrichten aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="34a91-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="34a91-139">Der Kompatibilitätsdienst speichert Dateien, die im Compliance-Dateispeicher für beständigen Chat archiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="34a91-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="34a91-140">Webdienste für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="34a91-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="34a91-141">Auf den lync Server-Front-End-Servern werden zwei Dienste ausgeführt, die von Internet Information Services (IIS) abhängen und als Webkomponenten implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="34a91-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="34a91-142">**Webdienste für beständigen Chat für Datei Upload/-Download** Verantwortlich für das Veröffentlichen und Abrufen von Dateien aus Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="34a91-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="34a91-143">**Webdienste für beständigen Chat für die Chat Raumverwaltung** Verantwortlich für die Bereitstellung von Benutzern, die ihre Chatrooms verwalten und neue Chatrooms erstellen können.</span><span class="sxs-lookup"><span data-stu-id="34a91-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="34a91-144">Wie fange ich mit dem Server für beständigen Chat an?</span><span class="sxs-lookup"><span data-stu-id="34a91-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="34a91-145">Der Server für beständigen Chat ist eine optionale Serverrolle in der lync Server 2013 Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="34a91-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="34a91-146">Wenn Sie die Server Rolle "persistent Chat" installieren, können alle Benutzer, die über eine Richtlinie eines Administrators aktiviert wurden, den beständigen Chat mit dem lync 2013-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="34a91-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="34a91-147">Ausführliche Informationen zum Bereitstellen des Servers für beständigen Chat und zur Aktivierung der Funktionen durch Richtlinien finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="34a91-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="34a91-148">Ausführliche Informationen zum Konfigurieren von Einstellungen für die Bereitstellung von persistent Chat Server finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Managing lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="34a91-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="34a91-149">Ausführliche Informationen zum Aktivieren von Benutzern durch Richtlinien, sodass Sie Funktionen für beständigen Chat in lync 2013-Client nutzen können, finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Managing lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="34a91-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="34a91-150">Wenn Sie die Compliance für beständigen Chat bereitgestellt haben, finden Sie weitere Informationen zum Konfigurieren von Einstellungen für die Kompatibilität unter [Managing lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) .</span><span class="sxs-lookup"><span data-stu-id="34a91-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="34a91-151">Anruf Flüsse für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="34a91-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="34a91-152">Der Client für beständigen Chat kommuniziert mithilfe von XCCOS mit dem Dienst für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="34a91-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="34a91-153">Die folgenden Sequenzen beschreiben den Anmeldevorgang und ein typisches Szenario beim Abonnieren eines Raums und beim Veröffentlichen einer Nachricht.</span><span class="sxs-lookup"><span data-stu-id="34a91-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="34a91-154">Anmelden</span><span class="sxs-lookup"><span data-stu-id="34a91-154">Sign-in</span></span>

<span data-ttu-id="34a91-155">Das folgende Anruffluss Diagramm und die folgenden Schritte beschreiben den Anmeldevorgang.</span><span class="sxs-lookup"><span data-stu-id="34a91-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="34a91-156">**Anruffluss für den Client für beständigen Chat**</span><span class="sxs-lookup"><span data-stu-id="34a91-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="34a91-157">![Anruffluss Diagramm für beständigen Chat Server.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Anruffluss Diagramm für beständigen Chat Server.")</span><span class="sxs-lookup"><span data-stu-id="34a91-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="34a91-158">Der Client für beständigen Chat sendet zunächst einen SIP subscribe, um das in-Band-Dokument vom Server abzurufen.</span><span class="sxs-lookup"><span data-stu-id="34a91-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="34a91-159">Dieses Dokument gibt an, ob der beständige Chat für den Benutzer und die Liste der SIP-URIs für den Server Pool für beständigen Chat aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="34a91-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="34a91-160">Der Client für beständigen Chat sendet eine SIP INVITE-Nachricht an den SIP-URI des Servers für beständigen Chat, den Sie im vorherigen Schritt erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="34a91-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="34a91-161">Die Invite-Sequenz wird von 200 OK und ACK gefolgt, und der Client für beständigen Chat hat jetzt eine SIP-Sitzung mit einem Server Endpunkt für beständigen Chat geöffnet.</span><span class="sxs-lookup"><span data-stu-id="34a91-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="34a91-162">Folglich kommuniziert der Client für beständigen Chat mit dem Server für beständigen Chat, indem SIP-Info Nachrichten gesendet werden, die entweder Chat Nachrichten oder Befehle enthalten, die den Server anfordern, eine Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="34a91-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="34a91-163">Alle diese Nachrichten werden mit 200 OK oder 503 Dienst nicht verfügbar (das heißt, im Falle einer schweren Serverlast) bestätigt.</span><span class="sxs-lookup"><span data-stu-id="34a91-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="34a91-164">Wenn der Client eine 503-Antwort erhält, wird die Nachricht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="34a91-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="34a91-165">(In diesem Beispiel ist keine 503-Antwort enthalten.) Wenn der Server die Nachricht oder den Befehl akzeptiert und 200 OK sendet, stellt er eine Antwort an den Client in Form einer separaten SIP-INFO-Nachricht bereit.</span><span class="sxs-lookup"><span data-stu-id="34a91-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="34a91-166">Diese Antwort enthält einen Verweis auf den ursprünglichen Befehl.</span><span class="sxs-lookup"><span data-stu-id="34a91-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="34a91-167">Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **getServerInfo** enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="34a91-168">Der Server für beständigen Chat antwortet mit einer neuen SIP-INFO-Nachricht, die Informationen zur Konfiguration des beständigen Chat Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="34a91-169">Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **GetAssociations** enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="34a91-170">Der Server für beständigen Chat antwortet mit einer neuen SIP-INFO-Nachricht, die die Liste der Räume enthält, in denen der Benutzer Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="34a91-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="34a91-171">Der Client für beständigen Chat wiederholt den Befehl, um die Liste der Räume abzurufen, von denen der Benutzer ein Vorgesetzter ist.</span><span class="sxs-lookup"><span data-stu-id="34a91-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="34a91-172">Der Client für beständigen Chat Ruft die Liste der befolgten Räume aus dem Dokument "Presence" ab, wobei jeder gefolgte Raum durch eine Kategorie "roomSetting" dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="34a91-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="34a91-173">Der Beitritt zu allen Räumen, denen der Benutzer folgt, geschieht durch eine einzige SIP INFO-Nachricht, die den XCCOS-Befehl **bjoin** mit der Liste der Raum-URIs enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="34a91-174">Da die Liste der Räume, denen der Benutzer folgt, auf dem Server gespeichert ist, verfügt jeder Client auf jedem Computer für die angegebene Benutzer-URI über dieselbe Liste der Räume, denen der Benutzer folgt.</span><span class="sxs-lookup"><span data-stu-id="34a91-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="34a91-175">Der Client für beständigen Chat behält auch die Liste der geöffneten Räume (falls diese Option vom Benutzer aktiviert ist) in der Registrierung des lokalen Computers bei und verbindet jeden dieser Räume bei der Anmeldung, indem er eine SIP-INFO-Nachricht sendet, die den XCCOS- **Join** -Befehl für jeden geöffneten Raum enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="34a91-176">Da diese Liste in der Registrierung aufbewahrt wird, kann Sie in zwei auf unterschiedlichen Computern ausgeführten Clients für beständigen Chat unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="34a91-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="34a91-177">Für jeden beigefügten Chatroom sendet der Client für beständigen Chat eine SIP-INFO-Nachricht, die den Befehl XCCOS **bccontext** enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="34a91-178">Der Server für beständigen Chat antwortet mit einer neuen SIP-INFO-Nachricht, die die neueste Chat Nachricht im Chatroom enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="34a91-179">Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die einen XCCOS- **GetInv** (also, Get-Einladungs Befehl) enthält, um neue Raum Einladungen anzufordern, die der Client noch nicht gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="34a91-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="34a91-180">In einer separaten SIP-INFO-Nachricht gibt der Server für beständigen Chat eine Liste dieser Räume zurück.</span><span class="sxs-lookup"><span data-stu-id="34a91-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="34a91-181">Abonnieren eines Raums und Veröffentlichen einer Nachricht</span><span class="sxs-lookup"><span data-stu-id="34a91-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="34a91-182">Das folgende Anruffluss Diagramm und die folgenden Schritte beschreiben ein typisches Raum Abonnement und ein Nachrichten Post Szenario.</span><span class="sxs-lookup"><span data-stu-id="34a91-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="34a91-183">**Beständiger Chat-Client Raum Abonnement und Nachrichten Übermittlungs Anruffluss**</span><span class="sxs-lookup"><span data-stu-id="34a91-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="34a91-184">![Szenario für Raum Abonnements und Nachrichten Bereitstellung.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Szenario für Raum Abonnements und Nachrichten Bereitstellung.")</span><span class="sxs-lookup"><span data-stu-id="34a91-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="34a91-185">Im Client für beständigen Chat klickt user1 auf **einem Chatroom beitreten**, klickt auf **Suche**und gibt dann einige Suchkriterien ein.</span><span class="sxs-lookup"><span data-stu-id="34a91-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="34a91-186">Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **chansrch** (Raumsuche) enthält, sowie die Suchkriterien.</span><span class="sxs-lookup"><span data-stu-id="34a91-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="34a91-187">Der Server für beständigen Chat fragt die Back-End-Datenbank ab und antwortet in einer neuen SIP-INFO-Nachricht, die eine Liste der verfügbaren Räume enthält, die den Suchkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="34a91-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="34a91-188">Benutzer1 wählt den Chatroom aus, den er betreten möchte, und klickt auf **Diesem Raum folgen**.</span><span class="sxs-lookup"><span data-stu-id="34a91-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="34a91-189">Der Client für beständigen Chat sendet beständigen Chat Server eine SIP-INFO-Nachricht, die den XCCOS- **Join** -Befehl und die Raum-ID des Chatrooms enthält, den der Benutzer ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="34a91-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="34a91-190">Der Server für beständigen Chat antwortet mit einer SIP-INFO-Nachricht, die die Bereitstellung von Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="34a91-191">Der persistent Chat-Client sendet beständigen Chat Server eine SIP-INFO-Nachricht, die den XCCOS **bccontext** -Befehl (Backchat-Kontext) enthält.</span><span class="sxs-lookup"><span data-stu-id="34a91-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="34a91-192">Der Server für beständigen Chat Ruft den Chatverlauf ab und gibt ihn in einer separaten SIP-INFO-Nachricht an den Client für beständigen Chat zurück.</span><span class="sxs-lookup"><span data-stu-id="34a91-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="34a91-193">An diesem Punkt betritt der Benutzer den Chatroom und ist bereit zur Teilnahme.</span><span class="sxs-lookup"><span data-stu-id="34a91-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="34a91-194">Benutzer1 gibt eine neue Nachricht ein und klickt anschließend auf **Senden**.</span><span class="sxs-lookup"><span data-stu-id="34a91-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="34a91-195">Der Client für beständigen Chat sendet die Nachricht in einem SIP-Info-XCCOS- **grpchat** -Befehl an den Chatroom.</span><span class="sxs-lookup"><span data-stu-id="34a91-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="34a91-196">Der Server für beständigen Chat speichert eine Kopie dieser neuen Nachricht in der Back-End-Datenbank des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="34a91-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="34a91-197">Der Server für beständigen Chat sendet eine separate Kopie der **grpchat** -Nachricht für SIP-Informationen XCCOS an Benutzer2, die bereits in den Chatroom eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="34a91-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="34a91-198">Compliance-Anruf Flüsse für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="34a91-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="34a91-199">Der Server für beständigen Chat verwendet Message Queuing (auch als MSMQ bezeichnet) und eine zusätzliche Kompatibilitätsdatenbank (mgccomp), um Kompatibilitätsdaten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="34a91-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="34a91-200">Als Beispiel dafür, wie Kompatibilitätsereignisse verarbeitet werden, beschreibt die folgende Ereignissequenz, wie ein Ereignis "Veröffentlichen einer Nachricht" verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="34a91-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="34a91-201">Ein Benutzer schreibt eine Nachricht in einem Chatroom.</span><span class="sxs-lookup"><span data-stu-id="34a91-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="34a91-202">Der Server für beständigen Chat platziert Informationen in Bezug auf das Ereignis in einer privaten Message Queuing-Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="34a91-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="34a91-203">Compliance-Server für beständigen Chat liest dieses Ereignis aus der Warteschlange und platziert es zur späteren Verarbeitung in der mgccomp-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="34a91-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="34a91-204">Der Kompatibilitätsserver für beständigen Chat verarbeitet regelmäßig eine Reihe von Ereignissen in der Datenbank und sendet Sie zur Verarbeitung an den Kompatibilitätsadapter für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="34a91-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="34a91-205">Wenn der Adapter die Daten erfolgreich verarbeitet, löscht der Kompatibilitätsserver für beständigen Chat die Ereignisse aus der mgccomp-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="34a91-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


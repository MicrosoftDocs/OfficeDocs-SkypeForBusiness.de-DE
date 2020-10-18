---
title: Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language)
description: Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d844acf542546a668c4fc086a07cd6a7bb4a8f5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577071"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="5f3c2-103">Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f3c2-103">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f3c2-104">_**Letztes Änderungsstand des Themas:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="5f3c2-104">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="5f3c2-105">Eine MSPL-Serveranwendung (Microsoft SIP Processing Language) ist eine nur-Skript-Anwendung, die anstelle des Microsoft lync 2010 API eine Skriptsprache verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-105">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="5f3c2-106">MSPL ermöglicht eine genauere Steuerung des Filter- und Proxyverhaltens und bietet eine Funktion zum Weiterleiten bestimmter Nachrichten an transaktionsbasierte SIP-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-106">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="5f3c2-107">MSPL wird insbesondere zum Filtern und Weiterleiten von SIP-Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-107">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="5f3c2-108">MSPL-Anwendungen werden im gleichen Prozess wie das User Services-Modul ausgeführt, während ein auf dem lync 2010 API basierendes Programm in einem separaten Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-108">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="5f3c2-109">Sie können die Seite **Serveranwendung** in der **topologiegruppe** lync Server-Systemsteuerung verwenden, um eine Liste der MSPL-Serveranwendungen anzuzeigen, die auf Front-End-Servern in ihrer lync Server 2013 Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-109">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="5f3c2-110">Die Liste zeigt die für jeden Pool verfügbaren Skripts und gibt an, ob diese aktiviert oder kritisch sind.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-110">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="5f3c2-111">Die Skripts werden in der Reihenfolge ihrer Auflistung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-111">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="5f3c2-112">Die folgenden Skripts sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5f3c2-112">These scripts include the following:</span></span>

  - <span data-ttu-id="5f3c2-p103">ClientVersionFilter ermöglicht Administratoren, die von einem Pool unterstützte Version der Clients anzugeben. Mit dem Clientversionsfilter kann die Clientversion überprüft und dann entweder die Anmeldung des Clients verhindert oder dem Benutzer eine Meldung angezeigt werden, dass eine nicht unterstützte Clientversion verwendet wird. Der Clientversionsfilter kann auch so konfiguriert werden, dass dem Benutzer eine Meldung mit der URL der aktuellen herunterladbaren Version des Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="5f3c2-116">TranslationService wandelt eine von einem Benutzer gewählte Nummer entsprechend den vom Administrator festgelegten Normalisierungsregeln in eine E.164-Nummer um.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-116">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="5f3c2-117">Ausführliche Informationen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="5f3c2-117">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="5f3c2-118">IncomingFederation erzwingt Verbundvalidierung auf Mandantenebene für Nachrichten zwischen Mandanten und aus externen Bereitstellungen eingehende Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-118">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="5f3c2-p105">Bei UserServices handelt es sich um die SIP-Registrierungs-, Anwesenheits- und Konferenzkomponente eines Front-End-Servers. Dieses Skript stellt integrierte Sofortnachrichten-, Anwesenheits- und Konferenzfunktionen auf Basis des SIP-Proxys bereit.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="5f3c2-121">InterClusterRouting sorgt für das Routing von Anrufen beim primären Registrierungspool des Anrufempfängers.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-121">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="5f3c2-122">Ausführliche Informationen finden Sie unter [Front-End-Server VoIP-Komponenten für lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="5f3c2-122">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="5f3c2-123">IIMFilter (Intelligent im Filter) blockiert Nachrichten, die klickable URLs enthalten oder die versuchen, Dateiübertragungen zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-123">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="5f3c2-124">IIMFilter überprüft auch die Client Version im Namen des Servers.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-124">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="5f3c2-125">IIMFilter betrifft Dateiübertragungen, die entweder mit lync Server oder Communicator initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-125">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="5f3c2-126">Standardmäßig sind die Klick fähigen Links deaktiviert, indem Sie vor dem ersten Zeichen des Links ein Unterstrichzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-126">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="5f3c2-127">Ein Administrator kann dieses Verhalten so ändern, dass der Link blockiert wird, sodass Nachrichten, die Klick Bare URLs enthalten oder die versuchen, eine Dateiübertragung zu initiieren, vom Server blockiert werden, um die beabsichtigten Ziele zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-127">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="5f3c2-128">IIMFilter ist auf allen Servern installiert, auf denen lync Server mit Ausnahme von Proxy Servern und Archivierungsservern betrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-128">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="5f3c2-129">UserPinService wird verwendet, um die persönlichen Identifikationsnummern (PINs) für Einwahlkonferenzen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-129">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="5f3c2-130">DefaultRouting ist die standardmäßige Routing Anwendung für Server, auf denen lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-130">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="5f3c2-131">Diese Anwendung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-131">It is enabled by default.</span></span> <span data-ttu-id="5f3c2-132">Die Routinganwendung wird auf allen Standard Edition- und Enterprise Edition-Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-132">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="5f3c2-p109">Mit ExumRouting werden Anrufe von Exchange Server Unified Messaging (UM) weitergeleitet. ExumRouting ermittelt bei Eingang einer neuen Voicemailnachricht den geeigneten Exchange UM-Server zum Weiterleiten des Anrufs. Mit ExumRouting werden zudem einige weitere Integrationsaspekte von Exchange UM behandelt, u. a. die Weiterleitung an eine automatische Telefonzentrale und der Teilnehmerzugriff.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="5f3c2-p110">OutboundRouting ermittelt das Gateway, das einen Anruf gemäß der gewählten Nummer und der Wählberechtigungen des Benutzers an eine Telefonnummer weiterleitet. OutboundRouting leitet Anrufe auch um, wenn ein Gateway einen Anruf nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="5f3c2-138">QoEAgent empfängt über SIP SERVICE-Anforderungen QoE-Datenberichte (Quality of Experience) von Endpunkten und sendet die Daten unter Verwendung von HTTP POST an die Zielwarteschlange auf dem Monitoring Server oder an Empfänger eines Drittanbieters.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-138">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="5f3c2-139">Ausführliche Informationen finden Sie unter [Deploying Monitoring in lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="5f3c2-139">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="5f3c2-140">OutgoingFederation erzwingt Verbundvalidierung auf Mandantenebene für Nachrichten an eine gezielte externe Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-140">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="5f3c2-141">AcpRouting leitet die für den Audiokonferenzanbieter bestimmten INVITE-Anforderungen an das Gateway des Audiokonferenzanbieters weiter.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-141">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="5f3c2-142">Auf Edgeservern werden die folgenden Skripts ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="5f3c2-142">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="5f3c2-143">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="5f3c2-143">IIMFilter</span></span>

  - <span data-ttu-id="5f3c2-144">OptionsHandler beantwortet eingehende OPTIONS-Anforderungen mit **200 OK**, wenn die Anforderung für den aktuellen Server bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-144">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="5f3c2-145">Dies wird für die Topologievalidierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f3c2-145">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5f3c2-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f3c2-146">See Also</span></span>


[<span data-ttu-id="5f3c2-147">Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f3c2-147">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="5f3c2-148">Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f3c2-148">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


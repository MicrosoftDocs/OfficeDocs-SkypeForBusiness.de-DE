---
title: Lync Server 2013 Server Rollen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="d9105-102">Server Rollen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9105-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9105-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d9105-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="d9105-104">Jeder Server, auf dem lync Server ausgeführt wird, führt mindestens eine *Serverrolle*aus.</span><span class="sxs-lookup"><span data-stu-id="d9105-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="d9105-105">Eine Serverrolle ist eine definierte Gruppe von lync Server Funktionalitäten, die von diesem Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="d9105-106">Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d9105-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="d9105-107">Installieren Sie lediglich die Serverrollen, die erforderliche Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d9105-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="d9105-108">Selbst wenn Sie mit den Serverrollen in lync Server nicht vertraut sind, kann das Planungs Tool Sie auf der Grundlage der gewünschten Features zur optimalen Lösung für die bereitzustellenden Server führen.</span><span class="sxs-lookup"><span data-stu-id="d9105-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="d9105-109">Dieser Abschnitt bietet eine kurze Übersicht über die Serverrollen und die allgemeinen Funktionen, die diese bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="d9105-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="d9105-110">Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="d9105-110">Standard Edition Server</span></span>

  - <span data-ttu-id="d9105-111">Front-End-Server und Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="d9105-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="d9105-112">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="d9105-112">Edge Server</span></span>

  - <span data-ttu-id="d9105-113">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="d9105-113">Mediation Server</span></span>

  - <span data-ttu-id="d9105-114">Director</span><span class="sxs-lookup"><span data-stu-id="d9105-114">Director</span></span>

  - <span data-ttu-id="d9105-115">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="d9105-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="d9105-116">Beständiger Chatspeicher (Back-End-Server für beständigen Chat)</span><span class="sxs-lookup"><span data-stu-id="d9105-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="d9105-117">Kompatibilitätsspeicher für beständigen Chat (Back-End-Server zur Kompatibilität für beständigen Chat)</span><span class="sxs-lookup"><span data-stu-id="d9105-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="d9105-118">Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen *Pools* mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9105-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="d9105-119">Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="d9105-120">Bei den meisten pooltypen in lync Server müssen Sie einen Lastenausgleich bereitstellen, um den Datenverkehr zwischen den verschiedenen Servern im Pool zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="d9105-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="d9105-121">Lync Server unterstützt sowohl Domain Name System (DNS) Lastenausgleich als auch Hardwaregeräte zum Lastenausgleich.</span><span class="sxs-lookup"><span data-stu-id="d9105-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="d9105-122">Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="d9105-122">Standard Edition Server</span></span>

<span data-ttu-id="d9105-123">Der Standard Edition-Server eignet sich für kleine Organisationen und für Pilotprojekte großer Organisationen.</span><span class="sxs-lookup"><span data-stu-id="d9105-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="d9105-124">Viele der Features von lync Server, einschließlich der erforderlichen Datenbanken, können auf einem einzelnen Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="d9105-125">Auf diese Weise können Sie lync Server Funktionalität zu niedrigeren Kosten Nutzen, jedoch keine echte Hochverfügbarkeitslösung anbieten.</span><span class="sxs-lookup"><span data-stu-id="d9105-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="d9105-126">Standard Edition-Server können Sie Instant Messaging (Sofortnachrichten), Anwesenheitsinformationen, Konferenzen und Enterprise-VoIP verwenden, die alle auf einem einzigen Server auszuführen sind.</span><span class="sxs-lookup"><span data-stu-id="d9105-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="d9105-127">Verwenden Sie lync Server Enterprise Edition für eine hoch verfügbare Lösung.</span><span class="sxs-lookup"><span data-stu-id="d9105-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="d9105-128">Front-End-Server und Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="d9105-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="d9105-129">In lync Server Enterprise Edition ist der Front-End-Server die Haupt Server Rolle und führt viele grundlegende lync Server Funktionen aus.</span><span class="sxs-lookup"><span data-stu-id="d9105-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="d9105-130">Die Front-End-Server, zusammen mit den Back-End-Servern, sind die einzigen Server Rollen, die in einer lync Server Enterprise Edition-Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d9105-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="d9105-p106">Bei einem *Front-End-Pool* handelt es sich um einen Satz von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d9105-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="d9105-133">Der Front-End-Server bietet u. a. die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="d9105-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="d9105-134">Benutzerauthentifizierung und -registrierung</span><span class="sxs-lookup"><span data-stu-id="d9105-134">User authentication and registration</span></span>

  - <span data-ttu-id="d9105-135">Anwesenheitsinformationen und Visitenkartenaustausch</span><span class="sxs-lookup"><span data-stu-id="d9105-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="d9105-136">Adressbuchdienste und Verteilerlistenerweiterung</span><span class="sxs-lookup"><span data-stu-id="d9105-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="d9105-137">Sofortnachrichtenfunktionalität, einschließlich Sofortnachrichtenkonferenzen mit mehreren Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="d9105-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="d9105-138">Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="d9105-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="d9105-139">Anwendungshosting für beide Anwendungen, die in lync Server enthalten sind (beispielsweise Konferenzzentrale und Reaktionsgruppenanwendung) und Anwendungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="d9105-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="d9105-140">Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="d9105-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="d9105-141">Diese Informationen liefern Metriken zur Qualität der Medien (Audio und Video), die Ihr Netzwerk für Enterprise-VoIP-Anrufe und A/V-Konferenzen durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d9105-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="d9105-142">Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.</span><span class="sxs-lookup"><span data-stu-id="d9105-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="d9105-143">Optional eine Archivierung der Sofortnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="d9105-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="d9105-144">Ausführliche Informationen finden Sie unter [Planning for Archiving in lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d9105-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="d9105-145">In lync Server 2010 und früheren Versionen waren Überwachung und Archivierung getrennte Server Rollen, die nicht auf Front-End-Server nebeneinander standen.</span><span class="sxs-lookup"><span data-stu-id="d9105-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="d9105-146">Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="d9105-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="d9105-p109">Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.</span><span class="sxs-lookup"><span data-stu-id="d9105-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="d9105-149">Darüber hinaus wird in einer Front-End-Pool in der Bereitstellung auch der *zentrale Verwaltungs Server*ausgeführt, der grundlegende Konfigurationsdaten für alle Server verwaltet und bereitstellt, auf denen lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d9105-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="d9105-150">Der zentrale Verwaltungs Server bietet auch lync Server-Verwaltungsshell-und Dateiübertragungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d9105-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="d9105-151">Bei den Back-End-Servern handelt es sich um Datenbankserver mit Microsoft SQL Server, die die Datenbankdienste für die Front-End-Pool bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d9105-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="d9105-152">Die Back-End-Server dienen als Sicherungsspeicher für die Benutzer-und Konferenzdaten des Pools und sind die primären Speicher für andere Datenbanken wie die Reaktionsgruppen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d9105-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="d9105-153">Sie können einen einzelnen Back-End-Server verwenden, aber eine Lösung, die SQL Server Spiegelung verwendet, wird für ein Failover empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d9105-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="d9105-154">Back-End-Server führen keine lync Server Software aus.</span><span class="sxs-lookup"><span data-stu-id="d9105-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9105-155">Es wird nicht empfohlen, abstimmen lync Server Datenbanken mit anderen Datenbanken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9105-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="d9105-156">Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="d9105-157">Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.</span><span class="sxs-lookup"><span data-stu-id="d9105-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="d9105-158">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="d9105-158">Edge Server</span></span>

<span data-ttu-id="d9105-159">Edgeserver ermöglicht Ihren Benutzern die Kommunikation und Zusammenarbeit mit Benutzern außerhalb der Firewalls der Organisation.</span><span class="sxs-lookup"><span data-stu-id="d9105-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="d9105-160">Zu diesen externen Benutzern können die eigenen Benutzer der Organisation gehören, die derzeit extern arbeiten, Benutzer aus Verbundpartner Organisationen und externe Benutzer, die eingeladen wurden, an Konferenzen teilzunehmen, die in ihrer lync Server-Bereitstellung gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="d9105-161">Edgeserver ermöglicht auch die Konnektivität mit öffentlichen Instant Messaging-Verbindungs Diensten, einschließlich Windows Live,\!AOL, Yahoo und Google Talk.</span><span class="sxs-lookup"><span data-stu-id="d9105-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d9105-162">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d9105-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d9105-163">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d9105-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d9105-164">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="d9105-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="d9105-165">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="d9105-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d9105-166">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="d9105-166">has been announced.</span></span> <span data-ttu-id="d9105-167">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d9105-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d9105-168">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d9105-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d9105-169">Messenger.</span><span class="sxs-lookup"><span data-stu-id="d9105-169">Messenger.</span></span> <span data-ttu-id="d9105-170">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d9105-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d9105-171">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="d9105-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d9105-172">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d9105-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d9105-173">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="d9105-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d9105-174">Bei der Bereitstellung des Edgeservers werden außerdem die Mobilitätsdienste aktiviert, mit denen die Lync-Funktionalität auf mobilen Geräten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d9105-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="d9105-175">Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen ausführen wie Senden und Empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit.</span><span class="sxs-lookup"><span data-stu-id="d9105-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="d9105-176">Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.</span><span class="sxs-lookup"><span data-stu-id="d9105-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="d9105-177">Das Mobilitätsfeature unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d9105-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="d9105-178">Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d9105-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="d9105-179">Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist.</span><span class="sxs-lookup"><span data-stu-id="d9105-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="d9105-180">Sie können diese XMPP-Komponenten so konfigurieren, dass Ihre lync Server 2013-Benutzer Kontakte von XMPP-basierten Partnern (wie Google Talk) für Chatnachrichten und Anwesenheitsinformationen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d9105-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="d9105-181">Ausführliche Informationen finden Sie unter [Planning for external User Access in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d9105-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="d9105-182">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="d9105-182">Mediation Server</span></span>

<span data-ttu-id="d9105-183">Vermittlungsserver ist eine notwendige Komponente für die Implementierung von Enterprise-VoIP und Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="d9105-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="d9105-184">Vermittlungsserver übersetzt das signalisieren und in einigen Konfigurationen Medien zwischen der internen lync Server-Infrastruktur und einem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage oder einem SIP-Trunk (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="d9105-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="d9105-185">Sie können den Vermittlungsserver gemeinsam mit dem Front-End-Sever auf demselben Server oder getrennt in einem eigenständigen Vermittlungsserverpool ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9105-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="d9105-186">Ausführliche Informationen finden Sie unter [Vermittlungsserver-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d9105-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="d9105-187">Director</span><span class="sxs-lookup"><span data-stu-id="d9105-187">Director</span></span>

<span data-ttu-id="d9105-188">Directors können lync Server Benutzeranforderungen authentifizieren, aber keine Benutzerkonten zu Hause oder Anwesenheits-oder Konferenzdienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d9105-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="d9105-189">Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d9105-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="d9105-190">Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="d9105-191">Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="d9105-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="d9105-192">Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="d9105-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="d9105-193">Server Rollen für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="d9105-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="d9105-p121">Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d9105-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="d9105-198">Server, auf denen lync Server Standard Edition ausgeführt wird, können auch beständigen Chat auf demselben Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="d9105-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="d9105-199">Sie können den Front-End-Server für beständigen Chat nicht mit Enterprise Edition-Front-End-Server collocate.</span><span class="sxs-lookup"><span data-stu-id="d9105-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="d9105-200">Ausführliche Informationen finden Sie unter [Planning for persistent Chat Server in lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d9105-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9105-201">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9105-201">See Also</span></span>


[<span data-ttu-id="d9105-202">Vermittlungsserver Komponente in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9105-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="d9105-203">Planen der Archivierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9105-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="d9105-204">Planen des Zugriffs durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9105-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="d9105-205">Szenarien für den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9105-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="d9105-206">Planen von Servern für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9105-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


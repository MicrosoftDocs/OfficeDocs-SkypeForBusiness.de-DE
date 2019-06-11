---
title: 'Lync Server 2013: Einführung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a><span data-ttu-id="36dcc-102">Einführung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36dcc-102">Introduction to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36dcc-103">_**Letztes Änderungsdatum des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="36dcc-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="36dcc-104">Lync Server 2013 und seine Client Software, wie lync 2013, ermöglichen es Ihren Benutzern, auf neue Weise eine Verbindung herzustellen und unabhängig von ihrem physikalischen Standort in Verbindung zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="36dcc-104">Lync Server 2013 and its client software, such as Lync 2013, enable your users to connect in new ways and to stay connected, regardless of their physical location.</span></span> <span data-ttu-id="36dcc-105">Lync und lync Server vereinen die unterschiedlichen Möglichkeiten, wie Personen in einer einzelnen Clientschnittstelle kommunizieren, als einheitliche Plattform bereitgestellt werden und über eine einzige Verwaltungsinfrastruktur verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="36dcc-105">Lync and Lync Server bring together the different ways that people communicate in a single client interface, are deployed as a unified platform, and are administered through a single management infrastructure.</span></span>

<span data-ttu-id="36dcc-106">Diese Tabelle und die folgenden Abschnitte veranschaulichen die wichtigsten Funktionsgruppen oder *Arbeits*Auslastungen, die lync Server für Ihre Benutzer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="36dcc-106">This table and the following sections illustrate the major feature sets, or *workloads*, that Lync Server provides for your users.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36dcc-107">Workload</span><span class="sxs-lookup"><span data-stu-id="36dcc-107">Workload</span></span></th>
<th><span data-ttu-id="36dcc-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36dcc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36dcc-109">Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="36dcc-109">IM and presence</span></span></p></td>
<td><p><span data-ttu-id="36dcc-110">Instant Messaging (im) und Anwesenheitsinformationen helfen Ihren Benutzern, sich gegenseitig effizient und effektiv zu finden und zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="36dcc-110">Instant messaging (IM) and presence help your users find and communicate with one another efficiently and effectively.</span></span></p>
<p><span data-ttu-id="36dcc-111">Chat bietet eine Instant Messaging-Plattform mit Konversationsprotokoll und unterstützt die Konnektivität öffentlicher Chats mit Benutzern öffentlicher Chat Netzwerke wie MSN/Windows Live, Yahoo!, AOL und Google Talk.</span><span class="sxs-lookup"><span data-stu-id="36dcc-111">IM provides an instant messaging platform with conversation history, and supports public IM connectivity with users of public IM networks such as MSN/Windows Live, Yahoo!, AOL, and Google Talk.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="36dcc-112">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="36dcc-112">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="36dcc-113">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="36dcc-113">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="36dcc-114">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="36dcc-114">Messenger until the service shut down date.</span></span> <span data-ttu-id="36dcc-115">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="36dcc-115">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="36dcc-116">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="36dcc-116">has been announced.</span></span> <span data-ttu-id="36dcc-117">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="36dcc-117">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="36dcc-118">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="36dcc-118">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="36dcc-119">Messenger.</span><span class="sxs-lookup"><span data-stu-id="36dcc-119">Messenger.</span></span> <span data-ttu-id="36dcc-120">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="36dcc-120">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="36dcc-121">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="36dcc-121">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="36dcc-122">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36dcc-122">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="36dcc-123">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-123">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div>
<p><span data-ttu-id="36dcc-124">Anwesenheitsinformationen und zeigt die persönliche Verfügbarkeit und Bereitschaft des Benutzers zur Kommunikation über die Verwendung von allgemeinen Zuständen wie " <strong>verfügbar</strong> " oder " <strong>beschäftigt</strong>" sowie detailliertere Zustände wie " <strong>seien Sie gleich zurück</strong> " und "nicht stören" an. <strong> </strong>.</span><span class="sxs-lookup"><span data-stu-id="36dcc-124">Presence establishes and displays a user’s personal availability and willingness to communicate through the use of common states such as <strong>Available</strong> or <strong>Busy</strong>, as well as more detailed states such as <strong>Be Right Back</strong> and <strong>Do Not Disturb</strong>.</span></span> <span data-ttu-id="36dcc-125">Diese umfangreichen Anwesenheitsinformationen ermöglichen es anderen Benutzern, sofort effektive Kommunikationsentscheidungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-125">This rich presence information enables other users to immediately make effective communication choices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36dcc-126">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="36dcc-126">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="36dcc-127">Lync Server bietet Unterstützung für Chat Konferenzen, Audiokonferenzen, Webkonferenzen, Videokonferenzen und Anwendungsfreigabe sowohl für geplante als auch für spontane Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-127">Lync Server includes support for IM conferencing, audio conferencing, web conferencing, video conferencing, and application sharing, for both scheduled and impromptu meetings.</span></span> <span data-ttu-id="36dcc-128">Alle diese Besprechungstypen werden mit einem einzelnen Client unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36dcc-128">All these meeting types are supported with a single client.</span></span> <span data-ttu-id="36dcc-129">Lync Server unterstützt auch Einwahlkonferenzen, damit Benutzer von PSTN-Telefonen (Public Switched Telephone Network) am Audioteil von Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="36dcc-129">Lync Server also supports dial-in conferencing so that users of public switched telephone network (PSTN) phones can participate in the audio portion of conferences.</span></span></p>
<p><span data-ttu-id="36dcc-130">Konferenzen können nahtlos in Echtzeit geändert und vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="36dcc-130">Conferences can seamlessly change and grow in real time.</span></span> <span data-ttu-id="36dcc-131">So kann beispielsweise eine einzelne Konferenz nur als Sofortnachricht zwischen wenigen Benutzern beginnen und zu einer Audiokonferenz mit Desktopfreigabe und einer größeren Zielgruppe sofort, einfach und ohne Unterbrechung des Konversations Flusses eskaliert werden.</span><span class="sxs-lookup"><span data-stu-id="36dcc-131">For example, a single conference can start as just instant messages between a few users, and escalate to an audio conference with desktop sharing and a larger audience instantly, easily, and without interrupting the conversation flow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36dcc-132">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="36dcc-132">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="36dcc-133"><em>Enterprise</em> -VoIP ist das VoIP-Angebot (Voice over Internet Protocol) in lync Server.</span><span class="sxs-lookup"><span data-stu-id="36dcc-133"><em>Enterprise Voice</em> is the Voice over Internet Protocol (VoIP) offering in Lync Server.</span></span> <span data-ttu-id="36dcc-134">Sie bietet eine Sprachoption zum verbessern oder ersetzen herkömmlicher PBX-Systeme (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="36dcc-134">It delivers a voice option to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="36dcc-135">Zusätzlich zu den vollständigen Telefoniefunktionen einer IP-Telefonanlage ist Enterprise-VoIP mit umfangreichen Anwesenheitsfunktionen, Chats, Zusammenarbeit und Besprechungen integriert.</span><span class="sxs-lookup"><span data-stu-id="36dcc-135">In addition to the complete telephony capabilities of an IP PBX, Enterprise Voice is integrated with rich presence, IM, collaboration, and meetings.</span></span> <span data-ttu-id="36dcc-136">Funktionen wie Anrufannahme, halten, fortsetzen, übertragen, weiterleiten und umleiten werden direkt unterstützt, während personalisierte Kurzwahl-Tasten durch Kontaktlisten ersetzt werden und die automatische Sprechanlage durch Chat ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="36dcc-136">Features such as call answer, hold, resume, transfer, forward and divert are supported directly, while personalized speed dialing keys are replaced by Contacts lists, and automatic intercom is replaced with IM.</span></span></p>
<p><span data-ttu-id="36dcc-137">Enterprise-VoIP unterstützt eine höhere Verfügbarkeit durch Anrufsteuerung (Anrufannahme Steuerung), Überlebensfähigkeit von Zweigstellen und erweiterte Optionen für die Datensicherheit.</span><span class="sxs-lookup"><span data-stu-id="36dcc-137">Enterprise Voice supports high availability through call admission control (CAC), branch office survivability, and extended options for data resiliency.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36dcc-138">Unterstützung für Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="36dcc-138">Support for remote users</span></span></p></td>
<td><p><span data-ttu-id="36dcc-139">Sie können vollständige lync Server-Funktionen für Benutzer bereitstellen, die sich derzeit außerhalb der Firewalls Ihrer Organisation <em></em> befinden, indem Sie Server mit dem Namen Edgeserver bereitstellen, um eine Verbindung für diese Remotebenutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-139">You can provide full Lync Server functionality for users who are currently outside your organization’s firewalls by deploying servers called <em>Edge Servers</em> to provide a connection for these remote users.</span></span> <span data-ttu-id="36dcc-140">Diese Remotebenutzer können mithilfe eines PCs, auf dem lync 2013 installiert ist, dem Smartphone oder einem Webinterface eine Verbindung mit Konferenzen herstellen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-140">These remote users can connect to conferences by using a personal computer with Lync 2013 installed, the phone, or a web interface.</span></span></p>
<p><span data-ttu-id="36dcc-141">Durch die Bereitstellung von Edgeserver <em></em> können Sie auch mit Partner-oder Anbieter Organisationen zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="36dcc-141">Deploying Edge Servers also enables you to <em>federate</em> with partner or vendor organizations.</span></span> <span data-ttu-id="36dcc-142">Eine Verbundbeziehung ermöglicht es Ihren Benutzern, Verbundbenutzer in ihre Kontaktlisten zu versetzen, Anwesenheitsinformationen und Sofortnachrichten mit diesen Benutzern zu austauschen und Sie zu Audioanrufen, Videoanrufen und Konferenzen einzuladen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-142">A federated relationship enables your users to put federated users on their Contacts lists, exchange presence information and instant messages with these users, and invite them to audio calls, video calls, and conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36dcc-143">Support für mobile Clients</span><span class="sxs-lookup"><span data-stu-id="36dcc-143">Mobile client support</span></span></p></td>
<td><p><span data-ttu-id="36dcc-144">Außerdem können Ihre Benutzer mit den lync Server-Mobilitätsdiensten auf die lync-Funktionalität zugreifen, wenn Sie unterstützte Apple IOS-, Android-, Windows Phone-oder Nokia Mobile-Geräte verwenden und solche Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten ausführen. und Anwesenheitsanzeige.</span><span class="sxs-lookup"><span data-stu-id="36dcc-144">Additionally, with Lync Server mobility services, your users can access Lync functionality when using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices and perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="36dcc-145">Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit anzurufen, eine Rufnummer zu erreichen, Voicemail und verpasste Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-145">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="36dcc-146">Push-Benachrichtigungen werden auch für mobile Geräte unterstützt, die Anwendungen, die im Hintergrund ausgeführt werden, nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-146">Push notifications are also supported for mobile devices that do not support applications running in the background.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36dcc-147">Integration mit anderen Produkten</span><span class="sxs-lookup"><span data-stu-id="36dcc-147">Integration with other products</span></span></p></td>
<td><p><span data-ttu-id="36dcc-148">Lync Server ist in mehrere andere Produkte integriert, um Ihren Benutzern und Administratoren zusätzliche Vorteile zu bieten.</span><span class="sxs-lookup"><span data-stu-id="36dcc-148">Lync Server integrates with several other products to provide additional benefits to your users and administrators.</span></span></p>
<p><span data-ttu-id="36dcc-149">Besprechungstools sind in Outlook integriert, damit die Organisatoren eine Besprechung planen oder eine spontane Konferenz mit einem einzigen Mausklick starten können, damit Sie den Teilnehmern einfach beitreten können.</span><span class="sxs-lookup"><span data-stu-id="36dcc-149">Meeting tools are integrated into Outlook to enable organizers to schedule a meeting or start an impromptu conference with a single click and make it just as easy for attendees to join.</span></span></p>
<p><span data-ttu-id="36dcc-150">Anwesenheitsinformationen sind in Outlook und SharePoint integriert.</span><span class="sxs-lookup"><span data-stu-id="36dcc-150">Presence information is integrated into Outlook and SharePoint.</span></span></p>
<p><span data-ttu-id="36dcc-151">Exchange Unified Messaging (um) bietet mehrere Integrationsfeatures.</span><span class="sxs-lookup"><span data-stu-id="36dcc-151">Exchange Unified Messaging (UM) provides several integration features.</span></span> <span data-ttu-id="36dcc-152">Benutzer können sehen, ob Sie über neue Voicemails in lync Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-152">Users can see if they have new voice mail within Lync Server.</span></span> <span data-ttu-id="36dcc-153">Sie können in der Outlook-Nachricht auf eine Wiedergabe-Schaltfläche klicken, um die Voicemail zu hören, oder eine Transkription der Voicemail in der Benachrichtigungsmeldung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-153">They can click a play button in the Outlook message to hear the audio voice mail, or view a transcription of the voice mail in the notification message.</span></span></p>
<p><span data-ttu-id="36dcc-154">Darüber hinaus ermöglicht das Ausführen von lync Server 2013 mit Exchange 2013 verschiedene neue Features, wie beispielsweise ein einheitlicher Kontaktspeicher, auf den Clients beider Produkte zugreifen können, sowie Fotos mit hoher Auflösung für Kontakte, die in der Exchange 2013-Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="36dcc-154">Additionally, running Lync Server 2013 with Exchange 2013 enables several new features such as a unified contact store which can be accessed by clients of both products, as well as high-resolution photos for contacts which are stored in the Exchange 2013 database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36dcc-155">Einfache Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="36dcc-155">Simple deployment</span></span></p></td>
<td><p><span data-ttu-id="36dcc-156">Um Ihnen beim Planen und Bereitstellen von Servern und Clients zu helfen, stellt lync Server den Topologie-Generator bereit.</span><span class="sxs-lookup"><span data-stu-id="36dcc-156">To help you plan and deploy your servers and clients, Lync Server provides the Topology Builder.</span></span></p>
<p><span data-ttu-id="36dcc-157">Der Topologie-Generator ist eine Installationskomponente von lync Server.</span><span class="sxs-lookup"><span data-stu-id="36dcc-157">Topology Builder is an installation component of Lync Server.</span></span> <span data-ttu-id="36dcc-158">Sie verwenden den Topologie-Generator zum Erstellen, anpassen und Veröffentlichen Ihrer geplanten Topologie.</span><span class="sxs-lookup"><span data-stu-id="36dcc-158">You use Topology Builder to create, adjust and publish your planned topology.</span></span> <span data-ttu-id="36dcc-159">Darüber hinaus wird Ihre Topologie überprüft, bevor Sie mit Server Installationen beginnen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-159">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="36dcc-160">Wenn Sie lync Server auf einzelnen Servern installieren, wird der Server von dem Installationsprogramm wie in der Topologie weitergeleitet bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="36dcc-160">When you install Lync Server on individual servers, the installation program deploys the server as directed in the topology.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36dcc-161">Einfache Verwaltung</span><span class="sxs-lookup"><span data-stu-id="36dcc-161">Simple management</span></span></p></td>
<td><p><span data-ttu-id="36dcc-162">Nachdem Sie lync Server bereitgestellt haben, bietet es die folgenden leistungsfähigen und optimierten Verwaltungstools:</span><span class="sxs-lookup"><span data-stu-id="36dcc-162">After you deploy Lync Server, it offers the following powerful and streamlined management tools:</span></span></p>
<ul>
<li><p><span data-ttu-id="36dcc-163">Zentrales Konfigurationsmanagement, mit dem Sie Änderungen zentral verwalten und diese schnell auf die gesamte Bereitstellung replizieren können.</span><span class="sxs-lookup"><span data-stu-id="36dcc-163">Central configuration management, which enables you to manage changes centrally and have them replicated quickly to the entire deployment.</span></span></p></li>
<li><p><span data-ttu-id="36dcc-164">Lync Server Control Panel, eine Web-basierte grafische Benutzeroberfläche für Administratoren.</span><span class="sxs-lookup"><span data-stu-id="36dcc-164">Lync Server Control Panel, a web-based graphical user interface for administrators.</span></span> <span data-ttu-id="36dcc-165">Mit dieser webbasierten Benutzeroberfläche können lync Server-Administratoren ihre Systeme von einem beliebigen Standort im Unternehmensnetzwerk aus verwalten, ohne dass spezielle Verwaltungssoftware auf ihren Computern installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="36dcc-165">With this web-based UI, Lync Server administrators can manage their systems from anywhere on the corporate network, without needing specialized management software installed on their computers.</span></span></p></li>
<li><p><span data-ttu-id="36dcc-166">Befehlszeilen-Verwaltungstool der lync Server-Verwaltungsshell, das auf der Windows PowerShell-Befehlszeilenschnittstelle basiert.</span><span class="sxs-lookup"><span data-stu-id="36dcc-166">Lync Server Management Shell command-line management tool, which is based on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="36dcc-167">Es bietet einen umfassenden Befehlssatz für die Verwaltung aller Aspekte des Produkts und ermöglicht es lync Server-Administratoren, sich wiederholende Aufgaben mithilfe eines vertrauten Tools zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="36dcc-167">It provides a rich command set for administration of all aspects of the product, and enables Lync Server administrators to automate repetitive tasks using a familiar tool.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36dcc-168">Während die Chat-und Anwesenheitsfeatures automatisch in jeder lync Server-Bereitstellung installiert werden, können Sie auswählen, ob Konferenz, Enterprise-VoIP und Remotebenutzerzugriff bereitgestellt werden sollen, um die Bereitstellung an die Anforderungen Ihrer Organisation anzupassen.</span><span class="sxs-lookup"><span data-stu-id="36dcc-168">While the IM and presence features are automatically installed in every Lync Server deployment, you can choose whether to deploy conferencing, Enterprise Voice, and remote user access, to tailor your deployment to your organization’s needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36dcc-169">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="36dcc-169">In This Section</span></span>

  - [<span data-ttu-id="36dcc-170">Chat und Anwesenheit in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36dcc-170">IM and presence in Lync Server 2013</span></span>](lync-server-2013-im-and-presence.md)

  - [<span data-ttu-id="36dcc-171">Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36dcc-171">Conferencing in Lync Server 2013</span></span>](lync-server-2013-conferencing.md)

  - [<span data-ttu-id="36dcc-172">Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36dcc-172">Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice.md)

  - [<span data-ttu-id="36dcc-173">Skalierbarkeit mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36dcc-173">Scalability with Lync Server 2013</span></span>](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


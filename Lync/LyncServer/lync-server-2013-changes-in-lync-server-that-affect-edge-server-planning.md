---
title: 'Lync Server 2013: Änderungen in Lync Server, die die Planung für Edgeserver betreffen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="5882f-102">Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen</span><span class="sxs-lookup"><span data-stu-id="5882f-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5882f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5882f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5882f-104">Lync Server 2013 führt neue Features ein, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern.</span><span class="sxs-lookup"><span data-stu-id="5882f-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="5882f-105">Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die Dienste, die für Ihre Organisation verfügbar sind, besser zu integrieren und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="5882f-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="5882f-106">Es folgt eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013-Edgeserver-Diensten auswirken können.</span><span class="sxs-lookup"><span data-stu-id="5882f-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="5882f-107">Unterstützung für IPv6-Adressierung</span><span class="sxs-lookup"><span data-stu-id="5882f-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="5882f-108">Lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver-Dienste.</span><span class="sxs-lookup"><span data-stu-id="5882f-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="5882f-109">Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edge-Server-Konfiguration über die IP-Adressenkonfiguration im Topologie-Generator verwenden.</span><span class="sxs-lookup"><span data-stu-id="5882f-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="5882f-110">Darüber hinaus unterstützt das Extensible Messaging and Presence Protocol (XMPP) IPv6.</span><span class="sxs-lookup"><span data-stu-id="5882f-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="5882f-111">Es ist keine zusätzliche Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5882f-111">No additional configuration is required.</span></span> <span data-ttu-id="5882f-112">Wenn IPv6 in der Topologie konfiguriert ist, wird in XMPP IPv6 (sofern erforderlich) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5882f-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="5882f-113">Eine zusätzliche Anforderung zur Unterstützung von IPv6 in lync Server 2013 ist das Erstellen von Domänennamen-Systemdaten Sätzen für Datensätze, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5882f-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="5882f-114">IPv6 DNS verwendet Hosteinträge, die als **AAAA** definiert sind und als "Quad-A" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="5882f-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="5882f-115">Andere Datensatztypen sind mit Ihren IPv4-Pendants konsistent.</span><span class="sxs-lookup"><span data-stu-id="5882f-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="5882f-116">Unterstützung für die Bereitstellung von Extensible Messaging and Presence Protocol (XMPP)</span><span class="sxs-lookup"><span data-stu-id="5882f-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="5882f-117">Edgeserver führt einen vollständig integrierten XMPP-Proxy (auf den Edgeserver bereitgestellt) und ein XMPP-Gateway (bereitgestellt auf Ihren Front-End-Servern) ein.</span><span class="sxs-lookup"><span data-stu-id="5882f-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="5882f-118">Sie können die XMPP-Föderation als optionale Komponente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5882f-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="5882f-119">Durch Hinzufügen und Konfigurieren des XMPP-Proxys und des XMPP-Gateways können Sie Ihren Microsoft lync 2013-Benutzern das Hinzufügen von Kontakten aus XMPP-basierten Partnern für Sofortnachrichten (im) und Anwesenheitsfunktionen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5882f-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5882f-120">Derzeit bieten die XMPP-Dienste in Edgeserver nur Chatnachrichten und Anwesenheitsinformationen zwischen lync Server-Clients und XMPP-basierten Kontakten.</span><span class="sxs-lookup"><span data-stu-id="5882f-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="5882f-121">Darüber hinaus wird XMPP nur an einer einzigen Website gehostet.</span><span class="sxs-lookup"><span data-stu-id="5882f-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5882f-p106">Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5882f-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="5882f-124">Unterstützung für die rollende Audio/Video-Authentifizierung und Server-zu-Server-Authentifizierungszertifikate</span><span class="sxs-lookup"><span data-stu-id="5882f-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="5882f-125">Ein Zertifikat wird verwendet, um Token zu generieren, die für Clients und andere Verbraucher des A/V-Authentifizierungsdiensts und für die Server-zu-Server-Authentifizierung ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5882f-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="5882f-126">Das Audio/Video-Authentifizierungszertifikat ist vom Typ *AudioVideoAuthentication* und das Server-zu-Server-Authentifizierungszertifikat vom Typ *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="5882f-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="5882f-127">Bei der Audio-und Video Authentifizierung werden Token zur Authentifizierung von Port Zuordnungsanforderungen verwendet, und die Token werden bis zu 8 Stunden zwischengespeichert – die Standardlebensdauer des Tokens.</span><span class="sxs-lookup"><span data-stu-id="5882f-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="5882f-128">Im Normalbetrieb ist dies eine sehr zuverlässige Methode zum Erstellen und Verteilen von Authentifizierungs Material an die a/V-Consumer.</span><span class="sxs-lookup"><span data-stu-id="5882f-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="5882f-129">Zertifikate weisen jedoch eine begrenzte Lebensdauer auf und verfallen mit einem vordefinierten Datum und einer vordefinierten Uhrzeit (basierend auf dem Erstellungsdatum und den Richtlinien, die bei der Zertifizierungsstelle, die das Zertifikat erstellt hat, in der Regel 2 Jahre für diesen Zertifikattyp) erzwungen wurden.</span><span class="sxs-lookup"><span data-stu-id="5882f-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="5882f-130">Wenn das Zertifikat abläuft, werden alle Token, die vom abgelaufenen Zertifikat erstellt und von Consumern zwischengespeichert wurden, ungültig.</span><span class="sxs-lookup"><span data-stu-id="5882f-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="5882f-131">Alle Versuche, ein Token zu verwenden, das mit einem abgelaufenen Zertifikat erstellt wurde, können zu fehlgeschlagenen Medien Relay-Zuweisungen führen, und alle aktuellen Audio/Video-Sitzungen schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="5882f-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="5882f-132">Der Client muss ein neues Token erwerben, das von einem gültigen Zertifikat erstellt wurde, um die normale Audio-und Video Funktionalität fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5882f-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="5882f-133">Die Server-zu-Server-Authentifizierung wird von einem globalen Zertifikat verwaltet, das angefordert und auf alle Server in der Bereitstellung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5882f-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="5882f-134">Das Zertifikat ist für die Authentifizierung von Servern in lync Server 2013 sowie für die Authentifizierung bei Exchange 2013 und Microsoft SharePoint Server 2013 verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="5882f-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="5882f-135">Weitere Informationen zur Funktionsweise der Server-zu-Server-Authentifizierung finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="5882f-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="5882f-136">Ein sehr wichtiger Unterschied zwischen dem Authentifizierungsprozess für Audio/Video und dem Server-zu-Server-Authentifizierungsprozess ist die Lebensdauer der Authentifizierung oder Tokens.</span><span class="sxs-lookup"><span data-stu-id="5882f-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="5882f-137">Bei der Audio/Video-Authentifizierung läuft die Authentifizierung nach acht Stunden ab.</span><span class="sxs-lookup"><span data-stu-id="5882f-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="5882f-138">Die Server-zu-Server-Authentifizierung hat eine Lebensdauer von 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="5882f-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="5882f-139">Sie müssen für jeden der Zertifikattypen entsprechend planen.</span><span class="sxs-lookup"><span data-stu-id="5882f-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="5882f-140">Neu bei lync Server 2013 ist die Möglichkeit, ein Ersatz-Audio/Video-Authentifizierungszertifikat und ein Server-zu-Server-Authentifizierungszertifikat im Vorfeld des Ablaufs des aktuellen Zertifikats zu inszenieren.</span><span class="sxs-lookup"><span data-stu-id="5882f-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="5882f-141">Das neue Zertifikat wird dann zum Generieren neuer Token oder neuer Authentifizierungsanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5882f-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="5882f-142">das alte Zertifikat bleibt jedoch erhalten, um die aktuellen Sitzungen und Authentifizierungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5882f-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="5882f-143">Dadurch wird verhindert, dass nahezu alle Fehler aufgrund von Token-und Zertifikat ablaufen effektiv verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="5882f-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="5882f-144">Details zu diesem Feature und zur Konfiguration finden Sie unter Staging von [AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="5882f-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="5882f-145">Geringere Abhängigkeit von der Cookie-basierten Affinität</span><span class="sxs-lookup"><span data-stu-id="5882f-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="5882f-146">In früheren Versionen von lync Server und Office Communications Server wurde die Cookie-basierte Affinität von den Webdiensten verwendet, um sicherzustellen, dass der Client-und Webdienste-Sitzungszustand beibehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="5882f-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="5882f-147">Lync Server 2013-Webdienste verwenden einen integrierten Affinitäts Mechanismus, der die meisten Anforderungen für die Cookie-basierte Affinität beseitigt.</span><span class="sxs-lookup"><span data-stu-id="5882f-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5882f-148">Der Mobile Microsoft lync 2010-Client muss weiterhin eine auf Cookies basierende Affinität verwenden und erfordert die Konfiguration von Cookie-basierter Affinität, bis Sie alle Clients auf den bevorstehenden Microsoft lync Mobile-Client migriert haben (das Datum der Veröffentlichung, das noch nicht festgelegt wurde).</span><span class="sxs-lookup"><span data-stu-id="5882f-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="5882f-149">Details zur Cookie-basierten Affinität in lync Server 2013 finden Sie unter [Komponenten, die für den Zugriff durch externe Benutzer in lync Server 2013 erforderlich](lync-server-2013-components-required-for-external-user-access.md)sind.</span><span class="sxs-lookup"><span data-stu-id="5882f-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="5882f-150">Verbesserungen bei AutoErmittlung</span><span class="sxs-lookup"><span data-stu-id="5882f-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="5882f-151">Das Feature AutoErmittlung in lync Server 2013 ermöglicht es Clients, zusätzliche Features zu finden, die für die Kommunikation zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5882f-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="5882f-152">Die AutoErmittlung wurde erstmals im kumulativen Update für lync Server 2010: November 2011 für Mobilität und Microsoft lync 2010 Mobile eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5882f-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="5882f-153">Das Feature AutoErmittlung (auch bekannt durch die DNS-Eintragsnamen LyncDiscover und LyncDiscoverInternal) ermöglicht es Clients, Mobilitätsdienste (für Microsoft lync 2010 Mobile-Clients), die Microsoft lync Web App und den lync Web Scheduler zu finden und zu verwenden sowie Kommunikation mit Microsoft Exchange Server und SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="5882f-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="5882f-154">AutoErmittlung wird als normaler Teil der Einrichtung und Bereitstellung Ihrer Infrastruktur und lync Server 2013-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="5882f-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="5882f-155">Der Topologie-Generator und der lync Server-Bereitstellungs-Assistent eliminieren die meisten Konfigurationsaufgaben, die im kumulativen Update für lync Server 2010: November 2011 erforderlich waren.</span><span class="sxs-lookup"><span data-stu-id="5882f-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="5882f-156">Dienste für mobile Clients</span><span class="sxs-lookup"><span data-stu-id="5882f-156">Services for Mobile Clients</span></span>

<span data-ttu-id="5882f-157">In dem kumulativen Update für lync Server 2010: November 2011, Mobilitätsdienste in lync Server 2013, mit denen Mobiltelefone mit lync Mobile-und Tablet-Geräten mit unterstützten Apple IOS-, Android-, Windows Phone-oder Nokia-mobilen Geräten ausgeführt werden können Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen.</span><span class="sxs-lookup"><span data-stu-id="5882f-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="5882f-158">Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit zu anrufen, eine Rufnummer zu erreichen, Voicemail und Benachrichtigungen über verpasste Anrufe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5882f-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5882f-159">Die Mobilitätsdienste verwenden den Reverse-Proxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5882f-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="5882f-160">Für Edgeserver sind keine Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5882f-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="5882f-161">Minimal benötigen Sie ausgehende SIP/TCP/5061from auf dem Server, auf dem der lync Server Access Edge-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5882f-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="5882f-162">Director-Rolle ist optional</span><span class="sxs-lookup"><span data-stu-id="5882f-162">Director Role is Optional</span></span>

<span data-ttu-id="5882f-163">Die Rolle des Director-Servers in der lync Server 2013-Topologie wurde nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="5882f-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="5882f-164">Sie hostet weiterhin Webdienste, authentifiziert eingehende Benutzeranforderungen und leitet externe Benutzer an deren Home-Pool weiter.</span><span class="sxs-lookup"><span data-stu-id="5882f-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="5882f-165">Wenn der Director von einer empfohlenen Rolle in eine optionale Rolle geändert wird, beabsichtigt Microsoft nicht, den Wert des Directors zu schmälern.</span><span class="sxs-lookup"><span data-stu-id="5882f-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="5882f-166">Das Ziel besteht darin, die Serveranzahl und andere Hardwareanforderungen (beispielsweise Hardwarelastenausgleichs für den Director) zu verringern, ohne die Features und Funktionen zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="5882f-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="5882f-167">Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können, ohne dass dies Auswirkungen auf die bereitgestellten Dienste hat, können Sie Directors bereitstellen, wenn Sie sich dafür entscheiden.</span><span class="sxs-lookup"><span data-stu-id="5882f-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="5882f-168">Sie können den Director sicher ausschließen, dass der Front-End-Server die gleichen Dienste anstelle eines Directors bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5882f-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


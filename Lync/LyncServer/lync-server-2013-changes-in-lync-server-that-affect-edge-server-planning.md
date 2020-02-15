---
title: 'Lync Server 2013: Änderungen an lync Server, die sich auf die Edgeserver Planung auswirken'
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
ms.openlocfilehash: c859df611ea2ad33b36bb7392dfcf2e2b9c5ae94
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="98fbf-102">Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken</span><span class="sxs-lookup"><span data-stu-id="98fbf-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98fbf-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="98fbf-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="98fbf-104">In lync Server 2013 werden neue Features vorgestellt, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern.</span><span class="sxs-lookup"><span data-stu-id="98fbf-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="98fbf-105">Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die für Ihre Organisation verfügbaren Dienste besser zu integrieren und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="98fbf-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="98fbf-106">Im folgenden finden Sie eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013 Edgeserver Diensten auswirken können.</span><span class="sxs-lookup"><span data-stu-id="98fbf-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="98fbf-107">Unterstützung für IPv6-Adressierung</span><span class="sxs-lookup"><span data-stu-id="98fbf-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="98fbf-108">Lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver Dienste.</span><span class="sxs-lookup"><span data-stu-id="98fbf-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="98fbf-109">Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edgeserver Konfiguration über die IP-Adresskonfiguration im Topologie-Generator verwenden.</span><span class="sxs-lookup"><span data-stu-id="98fbf-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="98fbf-110">Außerdem wird IPv6 auch vom XMPP-Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98fbf-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="98fbf-111">Zusätzliche Konfigurationsschritte sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98fbf-111">No additional configuration is required.</span></span> <span data-ttu-id="98fbf-112">Wenn IPv6 in der Topologie konfiguriert ist, wird es (wo erforderlich) von XMPP genutzt.</span><span class="sxs-lookup"><span data-stu-id="98fbf-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="98fbf-113">Eine zusätzliche Anforderung zur Unterstützung von IPv6 in lync Server 2013 besteht darin, Domänennamen-Systemeinträge für Datensätze zu erstellen, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="98fbf-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="98fbf-114">IPv6-DNS arbeitet mit Host-Einträgen, die als **AAAA** ("Quad-A") definiert werden.</span><span class="sxs-lookup"><span data-stu-id="98fbf-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="98fbf-115">Andere Typen von Einträgen entsprechen ihren IPv4-Gegenstücken.</span><span class="sxs-lookup"><span data-stu-id="98fbf-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="98fbf-116">Unterstützung für XMPP-Bereitstellung (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="98fbf-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="98fbf-117">Edgeserver stellt einen vollständig integrierten XMPP-Proxy (auf den Edgeserver bereitgestellt) und ein XMPP-Gateway (bereitgestellt auf Ihren Front-End-Servern) vor.</span><span class="sxs-lookup"><span data-stu-id="98fbf-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="98fbf-118">Sie können einen XMPP-Verbund als optionale Komponente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="98fbf-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="98fbf-119">Indem Sie den XMPP-Proxy und das XMPP-Gateway hinzufügen und konfigurieren, können Sie Ihren Microsoft lync 2013 Benutzern das Hinzufügen von Kontakten aus XMPP-basierten Partnern für Chatnachrichten und Anwesenheit ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="98fbf-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98fbf-120">Derzeit stellen die XMPP-Dienste in Edgeserver nur Chatnachrichten und Anwesenheitsinformationen zwischen lync Server-Clients und XMPP-basierten Kontakten bereit.</span><span class="sxs-lookup"><span data-stu-id="98fbf-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="98fbf-121">Außerdem wird XMPP nur an einem einzigen Standort gehostet.</span><span class="sxs-lookup"><span data-stu-id="98fbf-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98fbf-122">Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98fbf-122">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="98fbf-123">Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="98fbf-123">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="98fbf-124">Unterstützung für parallele Audio-/Video-Authentifizierung und Server-zu-Server-Authentifizierungszertifikate</span><span class="sxs-lookup"><span data-stu-id="98fbf-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="98fbf-p107">Ein Zertifikat wird zum Generieren von Token verwendet, die für Clients und andere Abnehmer des A/V-Authentifizierungsdiensts und für die Server-zu-Server-Kommunikation ausgestellt werden. Das Audio-/Video-Authentifizierungszertifikat hat den Typ *AudioVideoAuthentication*, und das Server-zu-Server-Authentifizierungszertifikat ist vom Typ *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="98fbf-p107">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication. The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="98fbf-p108">Bei der Audio-/Video-Authentifizierung dienen Token zum Authentifizieren von Portzuordnungsanforderungen, wobei die Token für bis zu acht Stunden zwischengespeichert werden (was die standardmäßige Lebensdauer des Token ist). Im normalen Betrieb ist das eine sehr zuverlässige Methode zum Erstellen und Weitergeben von Authentifizierungsmaterialien an die A/V-Abnehmer. Zertifikate haben jedoch eine begrenzte Lebenszeit und laufen zu einem vorab festgelegten Zeitpunkt ab (je nach dem Erstellungsdatum und den umgesetzten Richtlinien bei der CA, die das Zertifikat erstellt hat – bei Zertifikaten dieses Typs für gewöhnlich 2 Jahre). Bei Ablauf des Zertifikats werden alle damit erstellten und von Abnehmern zwischengespeicherten Token ungültig. Alle Versuche, ein Token zu verwenden, das mit einem abgelaufenen Zertifikat erstellt wurde, würden zu Fehlern bei Media-Relay-Zuordnungen und aktuellen Audio-/Videositzungen führen. Um den normalen Audio-/Videobetrieb wieder aufzunehmen, müsste der Client ein neues Token abrufen, das mit einem gültigen Zertifikat erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="98fbf-p108">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token. Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers. However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate). When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid. Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail. The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="98fbf-133">Die Server-zu-Server-Authentifizierung erfolgt mithilfe eines globalen Zertifikats, das für alle Server in der Bereitstellung angefordert und übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="98fbf-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="98fbf-134">Das Zertifikat ist für die Authentifizierung von Servern in lync Server 2013 sowie für die Authentifizierung bei Exchange 2013 und Microsoft SharePoint Server 2013 verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="98fbf-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="98fbf-135">Weitere Informationen zur Funktionsweise der Server-zu-Server-Authentifizierung finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="98fbf-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="98fbf-136">Ein sehr wichtiger Unterschied zwischen dem Audio-/Video-Authentifizierungsprozess und dem Server-zu-Server-Authentifizierungsprozess besteht in der Lebensdauer der Authentifizierung oder Token.</span><span class="sxs-lookup"><span data-stu-id="98fbf-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="98fbf-137">Bei Audio-/Video-Authentifizierung läuft die Authentifizierung nach 8 Stunden ab.</span><span class="sxs-lookup"><span data-stu-id="98fbf-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="98fbf-138">Die Server-zu-Server-Authentifizierung hat eine Lebensdauer von 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="98fbf-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="98fbf-139">Das müssen Sie bei Ihren Planungen entsprechend berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="98fbf-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="98fbf-140">Neu für lync Server 2013 ist die Möglichkeit, ein Ersatz-Audio/Video-Authentifizierungszertifikat und ein Server-zu-Server-Authentifizierungszertifikat im Vorfeld des Ablaufs des aktuellen Zertifikats zu inszenieren.</span><span class="sxs-lookup"><span data-stu-id="98fbf-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="98fbf-141">Das neue Zertifikat wird dann zum Generieren neuer Tokens oder neuer Authentifizierungsanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="98fbf-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="98fbf-142">behält jedoch das alte Zertifikat für die Überprüfung der aktuellen Sitzungen und Authentifizierungen bei..</span><span class="sxs-lookup"><span data-stu-id="98fbf-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="98fbf-143">Dadurch werden nahezu alle Fehler aufgrund von Token-und Zertifikat Ablauf wirksam verhindert.</span><span class="sxs-lookup"><span data-stu-id="98fbf-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="98fbf-144">Ausführliche Informationen zu diesem Feature und zu seiner Konfiguration finden Sie unter [Staging AV and OAuth certificates in lync Server 2013 using-Roll in CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="98fbf-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="98fbf-145">Geringere Abhängigkeit von Cookie-basierter Affinität</span><span class="sxs-lookup"><span data-stu-id="98fbf-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="98fbf-146">In früheren Versionen von lync Server und Office Communications Server wurde die Cookie-basierte Affinität von den Webdiensten verwendet, um sicherzustellen, dass der Client-und Webdienst Sitzungszustand beibehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="98fbf-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="98fbf-147">Lync Server 2013-Webdienste verwenden einen integrierten Affinitäts Mechanismus, der die meisten Anforderungen an die Cookie-basierte Affinität eliminiert.</span><span class="sxs-lookup"><span data-stu-id="98fbf-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="98fbf-148">Der Microsoft lync 2010 Mobile-Client muss weiterhin eine Cookie-basierte Affinität verwenden und eine Konfiguration der Cookie-basierten Affinität erfordern, bis Sie alle Clients zum bevorstehenden Microsoft lync Mobile-Client migriert haben (Veröffentlichungsdatum noch nicht festgelegt).</span><span class="sxs-lookup"><span data-stu-id="98fbf-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="98fbf-149">Ausführliche Informationen zur Cookie-basierten Affinität in lync Server 2013 finden Sie unter [für den Zugriff durch externe Benutzer in lync Server 2013 erforderliche Komponenten](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="98fbf-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="98fbf-150">Verbesserungen bei der AutoErmittlungs-Funktion</span><span class="sxs-lookup"><span data-stu-id="98fbf-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="98fbf-151">Das Auto Ermittlungs Feature in lync Server 2013 ermöglicht Clients das Auffinden zusätzlicher Features, die für die Kommunikation verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="98fbf-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="98fbf-152">Die AutoErmittlung wurde erstmals im kumulativen Update für lync Server 2010: November 2011 für Mobilität und Microsoft lync 2010 Mobile eingeführt.</span><span class="sxs-lookup"><span data-stu-id="98fbf-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="98fbf-153">Das Auto Ermittlungs Feature (auch bekannt durch die DNS-Eintragsnamen LyncDiscover und "lyncdiscoverinternal") ermöglicht Clients das Auffinden und Verwenden von Mobilitätsdiensten (für Microsoft lync 2010 Mobile Clients), die Microsoft lync Web App und den lync-Webplaner sowie Kommunikation mit Exchange Server und SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="98fbf-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="98fbf-154">Die AutoErmittlung wird als normaler Teil des Setups und der Bereitstellung Ihrer Infrastruktur und lync Server 2013 Server installiert.</span><span class="sxs-lookup"><span data-stu-id="98fbf-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="98fbf-155">Mit dem Topologie-Generator und dem lync Server-Bereitstellungs-Assistenten werden die meisten Konfigurationsaufgaben beseitigt, die im kumulativen Update für lync Server 2010 erforderlich waren: November 2011.</span><span class="sxs-lookup"><span data-stu-id="98fbf-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="98fbf-156">Dienste für mobile Clients</span><span class="sxs-lookup"><span data-stu-id="98fbf-156">Services for Mobile Clients</span></span>

<span data-ttu-id="98fbf-157">Im kumulativen Update für lync Server 2010: November 2011 wurden Mobilitätsdienste in lync Server 2013 für Mobiltelefone, auf denen lync Mobile und Tablet-Geräte mit unterstützten Apple IOS-, Android-, Windows Phone-oder Nokia-Mobilgeräten ausgeführt werden, für die Ausführung von Aktivitäten wie das Senden und empfangen von Chatnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen.</span><span class="sxs-lookup"><span data-stu-id="98fbf-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="98fbf-158">Zudem unterstützen Mobilgeräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftlich Anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.</span><span class="sxs-lookup"><span data-stu-id="98fbf-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98fbf-159">Die Mobilitätsdienste verwenden den Reverseproxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="98fbf-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="98fbf-160">Änderungen an Edgeservern sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98fbf-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="98fbf-161">Minimal benötigen Sie ausgehende SIP/TCP/5061from auf dem Server, auf dem die lync Server Zugriffs-Edgedienst läuft.</span><span class="sxs-lookup"><span data-stu-id="98fbf-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="98fbf-162">Director-Rolle ist optional</span><span class="sxs-lookup"><span data-stu-id="98fbf-162">Director Role is Optional</span></span>

<span data-ttu-id="98fbf-163">Die Rolle des Director-Servers in der lync Server 2013-Topologie wurde nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="98fbf-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="98fbf-164">Er hostet weiterhin Webdienste, authentifiziert vorab eingehende Benutzeranfragen und leitet externe Benutzer zu deren Home-Pool.</span><span class="sxs-lookup"><span data-stu-id="98fbf-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="98fbf-165">Wenn Sie den Director von einer empfohlenen Rolle in eine optionale Rolle ändern, beabsichtigt Microsoft nicht, den Wert des Directors zu verringern.</span><span class="sxs-lookup"><span data-stu-id="98fbf-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="98fbf-166">Das Ziel besteht darin, die Anzahl von Servern und andere Hardwareanforderungen zu reduzieren (beispielsweise Hardwarelastenausgleich für den Director), ohne dass Features und Funktionen beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="98fbf-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="98fbf-167">Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können und keine Auswirkungen auf die bereitgestellten Dienste haben, können Sie Directors bereitstellen, wenn Sie sich für entscheiden.</span><span class="sxs-lookup"><span data-stu-id="98fbf-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="98fbf-168">Sie können den Director sicher mit Sicherheit ausschließen, dass die Front-End-Server dieselben Dienste anstelle eines Directors bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="98fbf-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


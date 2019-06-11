---
title: 'Lync Server 2013: Konfigurationsanforderungen für Reverse-Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="b8f6b-102">Konfigurationsanforderungen für den Reverse Proxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8f6b-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8f6b-103">_**Letztes Änderungsdatum des Themas:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="b8f6b-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="b8f6b-104">Lync Server 2013 erlegt den externen Clients einige Anforderungen auf, die an die externen Webdienste weitergegeben werden, die auf dem Director, Director-Pool, Front-End-Server oder Front-End-Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="b8f6b-105">Der Reverse-Proxy ist auch für die Veröffentlichung des Office Web Apps-Servers verantwortlich, wenn Sie Ihren Benutzern Konferenzen anbieten.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8f6b-106">Lync Server 2013 gibt keinen bestimmten Reverse-Proxy an, den Sie verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="b8f6b-107">Lync Server 2013 definiert nur betriebliche Anforderungen, die der Reverse-Proxy erfüllen muss.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="b8f6b-108">In der Regel kann der umgekehrte Proxy, den Sie bereits in Ihrer Infrastruktur bereitgestellt haben, die Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="b8f6b-109">Reverse Proxy-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8f6b-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="b8f6b-110">Die funktionsvorgänge, die lync Server 2013 von einem Reverse-Proxy erwartet, sind:</span><span class="sxs-lookup"><span data-stu-id="b8f6b-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="b8f6b-111">Verwenden Sie Secure Socket Layer (SSL) und TLS (Transport Layer Security) mithilfe von Zertifikaten, die von einer öffentlichen Zertifizierungsstelle zum Herstellen einer Verbindung mit den veröffentlichten externen Webdiensten des Director-, Director-Pools, Front-End-Servers oder Front-End-Pools erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="b8f6b-112">Der Director und der Front-End-Server können in einem Lastenausgleichspool mithilfe von Hardwarelastenausgleichs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="b8f6b-113">In der Lage, interne Websites mithilfe von Zertifikaten für die Verschlüsselung zu veröffentlichen oder Sie bei Bedarf über ein unverschlüsseltes Mittel zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="b8f6b-114">Sie können eine intern gehostete Website extern mit einem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="b8f6b-115">Kann alle Inhalte der gehosteten Website veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="b8f6b-116">Standardmäßig können Sie die \*\* / \*\* von den meisten Webservern erkannte Direktive verwenden, um "alle Inhalte auf dem Webserver veröffentlichen" zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="b8f6b-117">Sie können die Direktive auch ändern, beispielsweise **/UWCA/\***, was bedeutet, dass "alle Inhalte unter dem virtuellen Verzeichnis Ucwa veröffentlicht werden".</span><span class="sxs-lookup"><span data-stu-id="b8f6b-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="b8f6b-118">Muss konfigurierbar sein, damit SSL (Secure Sockets Layer) und/oder TLS-Verbindungen (Transport Layer Security) mit Clients erforderlich sind, die Inhalte von einer veröffentlichten Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="b8f6b-119">Sie müssen Zertifikate mit San-Einträgen (Subject Alternative Name) akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="b8f6b-120">Muss in der Lage sein, die Bindung eines Zertifikats an einen Listener oder eine Schnittstelle zu ermöglichen, über die der FQDN des externen Webdiensts aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="b8f6b-121">Listenerkonfigurationen sind Schnittstellen vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="b8f6b-122">Viele Listener können in einer einzelnen Schnittstelle konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="b8f6b-123">Muss für die Konfiguration der Hostheader Behandlung zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="b8f6b-124">Häufig muss der vom anfordernden Client gesendete ursprüngliche Hostheader transparent übergeben werden, anstatt vom Reverse-Proxy geändert zu werden.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="b8f6b-125">Bridging des SSL-und TLS-Datenverkehrs von einem extern definierten Port (beispielsweise TCP 443) zu einem anderen definierten Port (beispielsweise TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="b8f6b-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="b8f6b-126">Der Reverse-Proxy entschlüsselt das Paket möglicherweise beim Empfang und verschlüsselt das Paket beim Senden erneut.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="b8f6b-127">Bridging des unverschlüsselten TCP-Datenverkehrs von einem Port (beispielsweise TCP 80) zu einem anderen (beispielsweise TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="b8f6b-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="b8f6b-128">Erlauben Sie die Konfiguration von oder akzeptieren Sie die NTLM-Authentifizierung, keine Authentifizierung und Pass-Through-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b8f6b-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


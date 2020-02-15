---
title: 'Lync Server 2013: Konfigurationsanforderungen für Reverse Proxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efa0124bb66974755a7cae0ab799dc66cc48fd1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="54f73-102">Konfigurationsanforderungen für Reverse Proxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f73-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f73-103">_**Letztes Änderungsstand des Themas:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="54f73-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="54f73-104">Lync Server 2013 auferlegt eine Reihe von Anforderungen für die Kommunikation vom externen Client, die dann an die externen Webdienste übergeben werden, die auf dem Director, Directorpool, Front-End-Server oder Front-End-Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="54f73-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="54f73-105">Der Reverseproxy ist auch für die Veröffentlichung des Office-webapps-Servers zuständig, wenn Sie den Benutzern Konferenzen anbieten.</span><span class="sxs-lookup"><span data-stu-id="54f73-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54f73-106">In lync Server 2013 wird kein bestimmter Reverseproxy angegeben, den Sie verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="54f73-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="54f73-107">In lync Server 2013 werden nur die betrieblichen Anforderungen definiert, die der Reverseproxy in der Lage sein muss.</span><span class="sxs-lookup"><span data-stu-id="54f73-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="54f73-108">In der Regel können der Reverseproxy, den Sie bereits in Ihrer Infrastruktur bereitgestellt haben, die Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="54f73-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="54f73-109">Reverseproxyanforderungen</span><span class="sxs-lookup"><span data-stu-id="54f73-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="54f73-110">Bei den Funktions Vorgängen, die von einem Reverseproxy erwartet werden, handelt es sich um folgende Aufgaben: lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f73-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="54f73-111">Verwenden Sie SSL (Secure Socket Layer) und TLS (Transport Layer Security) mithilfe von Zertifikaten, die von einer öffentlichen Zertifizierungsstelle erworben wurden, um eine Verbindung mit den veröffentlichten externen Webdiensten des Directors, Directorpool, Front-End-Server oder Front-End-Pool herzustellen.</span><span class="sxs-lookup"><span data-stu-id="54f73-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="54f73-112">Der Director und der Front-End-Server können sich in einem Lastenausgleichspool mit Hardwarelastenausgleich befinden.</span><span class="sxs-lookup"><span data-stu-id="54f73-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="54f73-113">Die Möglichkeit, interne Websites mit Zertifikaten für die Verschlüsselung zu veröffentlichen oder Sie bei Bedarf über einen unverschlüsselten Weg zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="54f73-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="54f73-114">Kann eine intern gehostete Website extern mithilfe eines vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="54f73-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="54f73-115">Alle Inhalte der gehosteten Website können veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="54f73-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="54f73-116">Standardmäßig können Sie die \*\* / \*\* von den meisten Webservern erkannte Direktive verwenden, um "alle Inhalte auf dem Webserver veröffentlichen" zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="54f73-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="54f73-117">Sie können die Direktive auch ändern, beispielsweise **/UWCA/\***, was bedeutet "Veröffentlichen aller Inhalte unter dem virtuellen Verzeichnis Ucwa".</span><span class="sxs-lookup"><span data-stu-id="54f73-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="54f73-118">Muss konfigurierbar sein, damit Secure Sockets Layer (SSL) und/oder TLS-Verbindungen (Transport Layer Security) mit Clients erforderlich sind, die Inhalte von einer veröffentlichten Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="54f73-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="54f73-119">Zertifikate mit den Einträgen des alternativen Antragstellernamens müssen akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="54f73-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="54f73-120">Muss in der Lage sein, das Binden eines Zertifikats an einen Listener oder eine Schnittstelle zuzulassen, über die der FQDN der externen Webdienste aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="54f73-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="54f73-121">Listener-Konfigurationen sind Schnittstellen vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="54f73-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="54f73-122">Viele Listener können auf einer einzigen Schnittstelle konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="54f73-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="54f73-123">Die Konfiguration der Hostheader Behandlung muss zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="54f73-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="54f73-124">Häufig muss der vom anfordernden Client gesendete ursprüngliche Hostheader transparent übergeben werden, anstatt vom Reverseproxy geändert zu werden.</span><span class="sxs-lookup"><span data-stu-id="54f73-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="54f73-125">Überbrückung von SSL-und TLS-Datenverkehr von einem extern definierten Port (beispielsweise TCP 443) an einen anderen definierten Port (beispielsweise TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="54f73-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="54f73-126">Der Reverseproxy kann das Paket beim Empfang entschlüsseln und dann das Paket beim Senden erneut verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="54f73-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="54f73-127">Überbrückung von unverschlüsseltem TCP-Datenverkehr von einem Port (beispielsweise TCP 80) an einen anderen (beispielsweise TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="54f73-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="54f73-128">Zulassen der Konfiguration von, oder akzeptieren, NTLM-Authentifizierung, keine Authentifizierung und Pass-Through-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="54f73-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


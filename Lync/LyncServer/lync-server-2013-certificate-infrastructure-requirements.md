---
title: 'Lync Server 2013: Anforderungen in Bezug auf die Zertifikatsinfrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="7aaf8-102">Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aaf8-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aaf8-103">_**Letztes Änderungsdatum des Themas:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="7aaf8-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="7aaf8-104">Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS-und MTLS-Verbindungen (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="7aaf8-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="7aaf8-105">Lync Server verwendet Zertifikate für die folgenden Zwecke:</span><span class="sxs-lookup"><span data-stu-id="7aaf8-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="7aaf8-106">TLS-Verbindungen zwischen Client und Server</span><span class="sxs-lookup"><span data-stu-id="7aaf8-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="7aaf8-107">MTLS-Verbindungen zwischen Servern</span><span class="sxs-lookup"><span data-stu-id="7aaf8-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="7aaf8-108">Föderation mithilfe der automatischen DNS-Ermittlung von Partnern</span><span class="sxs-lookup"><span data-stu-id="7aaf8-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="7aaf8-109">Zugriff von Remotebenutzern auf Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="7aaf8-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="7aaf8-110">Zugriff externer Benutzer auf Audio/Video-Sitzungen (A/V), Anwendungsfreigabe und Konferenzen</span><span class="sxs-lookup"><span data-stu-id="7aaf8-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="7aaf8-111">Mobile Anforderungen mithilfe der automatischen Ermittlung von Webdiensten</span><span class="sxs-lookup"><span data-stu-id="7aaf8-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="7aaf8-112">Für lync Server gelten die folgenden allgemeinen Voraussetzungen:</span><span class="sxs-lookup"><span data-stu-id="7aaf8-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="7aaf8-113">Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="7aaf8-114">Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="7aaf8-115">Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="7aaf8-116">Lync Server 2013 unterstützt die SHA-1-und SHA-2-Suite von Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Anforderungen des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="7aaf8-117">Informationen zur Unterstützung des Betriebs [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)Systems finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7aaf8-118">Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei der Anmeldung und Problemen mit der Anrufweiterleitung führen. </span><span class="sxs-lookup"><span data-stu-id="7aaf8-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="7aaf8-119">Die automatische Registrierung wird für interne Server unterstützt, auf denen lync Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="7aaf8-120">Die automatische Registrierung wird für lync Server Edge-Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="7aaf8-121">Wenn Sie eine webbasierte Zertifikatanforderung an eine Windows Server 2003-Zertifizierungsstelle übermitteln, müssen Sie Sie von einem Computer übermitteln, auf dem Windows Server 2003 mit SP2 oder Windows XP ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="7aaf8-122">Beachten Sie, dass KB922706 zwar Unterstützung für das Beheben von Problemen beim Registrieren von webzertifikaten für eine Windows Server 2003 Certificate Services-Webregistrierung bietet, es jedoch nicht möglich ist, Windows Server 2008, Windows Vista oder Windows 7 zu verwenden, um eine Zertifikat von einer Windows Server 2003-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="7aaf8-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="7aaf8-123">Es werden Verschlüsselungsschlüssellängen von 1.024, 2.048 und 4.096 Bit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="7aaf8-124">Empfohlen werden Schlüssellängen ab 2.048 Bit.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="7aaf8-125">Der Standard-Digest-oder Hash-Signaturalgorithmus ist RSA.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="7aaf8-126">Die Algorithmen\_ECDH P256,\_ECDH P384 und ECDH\_P521 werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7aaf8-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="7aaf8-127">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7aaf8-127">In This Section</span></span>

  - [<span data-ttu-id="7aaf8-128">Anforderungen an Zertifikate für interne Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aaf8-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="7aaf8-129">Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aaf8-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="7aaf8-130">Zertifikatanforderungen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aaf8-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="7aaf8-131">Zertifikatanforderungen für die Mobilität in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aaf8-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


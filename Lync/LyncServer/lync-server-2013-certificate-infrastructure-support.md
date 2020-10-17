---
title: Unterstützung von lync Server 2013 Zertifikatinfrastruktur
description: Lync Server 2013 Unterstützung der Zertifikatinfrastruktur.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544231"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="7baa7-103">Unterstützung der Zertifikatinfrastruktur in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7baa7-103">Certificate infrastructure support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7baa7-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7baa7-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7baa7-105">Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von TLS (Transport Layer Security) und MTLS-Verbindungen (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="7baa7-105">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="7baa7-106">Standardmäßig ist lync Server 2013 für die Verwendung von TLS für Client-zu-Server-Verbindungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="7baa7-106">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="7baa7-107">MTLS wird für Verbindungen zwischen Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="7baa7-107">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="7baa7-108">MTLS-Zertifikate müssen von vertrauenswürdigen Zertifizierungsstellen (Certification Authorities, CAS) für lync Server 2013 ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7baa7-108">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="7baa7-109">Lync Server unterstützt Zertifikate, die von folgenden CAS ausgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="7baa7-109">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="7baa7-110">Zertifikate, die von einer internen Zertifizierungsstelle ausgestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="7baa7-110">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="7baa7-111">Die Windows Server 2003-Betriebssystem-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="7baa7-111">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="7baa7-112">Die Windows Server 2008-Betriebssystem-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="7baa7-112">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="7baa7-113">Die Windows Server 2008 R2-Betriebssystem-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="7baa7-113">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="7baa7-114">Die Windows Server 2012-Betriebssystem-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="7baa7-114">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="7baa7-115">Die Windows Server 2012 R2-Betriebssystem-Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="7baa7-115">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="7baa7-116">Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden</span><span class="sxs-lookup"><span data-stu-id="7baa7-116">Certificates issued from a public CA</span></span>

<span data-ttu-id="7baa7-117">Für die Kommunikation mit anderen Anwendungen und Servern wie Exchange 2013 ist ein Zertifikat erforderlich, das von den anderen Anwendungen und Produkten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7baa7-117">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="7baa7-118">Für das 2013-Release, lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, wird das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7baa7-118">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="7baa7-119">Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7baa7-119">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="7baa7-120">Für Verbindungen von Clients, die Windows 7 Betriebssystem, Windows Server 2008 R2-Betriebssystem und Microsoft Office Communicator 2007 Phone Edition ausführen, enthält lync Server 2013 Unterstützung für (jedoch nicht erforderliche) Zertifikate, die mit der kryptografischen Hashfunktion von SHA-256 signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7baa7-120">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="7baa7-121">Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.</span><span class="sxs-lookup"><span data-stu-id="7baa7-121">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="7baa7-122">Ausführliche Informationen zu den Zertifikatanforderungen finden Sie unter [Certificate Infrastructure Requirements for lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7baa7-122">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="7baa7-123">Ausführliche Informationen zur Verwendung von Platzhalterzeichen mit Zertifikaten finden Sie unter [Wildcard Certificate Support in lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7baa7-123">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


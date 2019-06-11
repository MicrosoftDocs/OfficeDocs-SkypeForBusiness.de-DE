---
title: 'Lync Server 2013: Unterstützung der Zertifikatinfrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13e04e2e6746dac9c40eaa6df0c3b33d52c6a547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="76dfd-102">Unterstützung der Zertifikatinfrastruktur in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76dfd-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76dfd-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="76dfd-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="76dfd-104">Lync Server 2013 erfordert eine Public Key-Infrastruktur (PKI) zur Unterstützung von Transport Layer Security (TLS)-und MTLS-Verbindungen (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="76dfd-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="76dfd-105">Standardmäßig ist lync Server 2013 für die Verwendung von TLS für Client-zu-Server-Verbindungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="76dfd-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="76dfd-106">MTLS wird für Verbindungen zwischen Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="76dfd-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="76dfd-107">MTLS-Zertifikate müssen von vertrauenswürdigen Zertifizierungsstellen (CAS) für lync Server 2013 ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="76dfd-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="76dfd-108">Lync Server unterstützt Zertifikate, die von den folgenden CAS ausgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="76dfd-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="76dfd-109">Zertifikate, die von einer internen Zertifizierungsstelle ausgestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="76dfd-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="76dfd-110">Die Windows Server 2003-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="76dfd-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="76dfd-111">Die Windows Server 2008-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="76dfd-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="76dfd-112">Die Windows Server 2008 R2-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="76dfd-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="76dfd-113">Die Windows Server 2012-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="76dfd-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="76dfd-114">Die Windows Server 2012 R2-Betriebssystem Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="76dfd-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="76dfd-115">Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden</span><span class="sxs-lookup"><span data-stu-id="76dfd-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="76dfd-116">Die Kommunikation mit anderen Anwendungen und Servern, wie etwa Exchange 2013, erfordert ein Zertifikat, das von den anderen Anwendungen und Produkten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="76dfd-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="76dfd-117">Für die 2013-Version unterstützen lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="76dfd-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="76dfd-118">Ausführliche Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76dfd-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="76dfd-119">Für Verbindungen von Clients unter dem BetriebssystemWindows 7, Windows Server 2008 R2 und Microsoft Office Communicator 2007 Phone Edition umfasst lync Server 2013 Unterstützung für (aber nicht erforderliche) Zertifikate, die mit dem SHA-256 signiert wurden. kryptografische Hashfunktion.</span><span class="sxs-lookup"><span data-stu-id="76dfd-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="76dfd-120">Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="76dfd-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="76dfd-121">Details zu den Zertifikatanforderungen finden Sie unter [Zertifikatsinfrastruktur Anforderungen für lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="76dfd-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="76dfd-122">Ausführliche Informationen zur Verwendung von Platzhaltern mit Zertifikaten finden Sie unter Unterstützung für [Platzhalterzertifikate in lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="76dfd-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


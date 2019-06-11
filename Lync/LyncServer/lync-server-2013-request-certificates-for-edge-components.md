---
title: 'Lync Server 2013: Anfordern von Zertifikaten für Edgekomponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e848e5fb8ea120bab2251dff776e2c9c27eacca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="0327d-102">Anfordern von Zertifikaten für Edgekomponenten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0327d-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0327d-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0327d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0327d-104">Die für die Unterstützung des Zugriffs durch externe Benutzer erforderlichen Zertifikate umfassen Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden, sowie Zertifikate, die von einer internen Unternehmenszertifizierungsstelle ausgestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="0327d-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="0327d-105">Zertifikate, die für die externe Schnittstelle des Edge-Servers und des Reverse-Proxys erforderlich sind, müssen von einer öffentlichen Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0327d-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="0327d-106">Für die interne Schnittstelle erforderliche Zertifikate können entweder von einer öffentlichen Zertifizierungsstelle oder einer internen Unternehmenszertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0327d-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="0327d-107">Es wird empfohlen, eine interne Windows Server 2008-Zertifizierungsstelle, Windows Server 2008 R2 ca, Windows Server 2012 ca oder Windows Server 2012 R2 ca zum Erstellen dieser Zertifikate zu verwenden, um die Kosten für die Verwendung öffentlicher Zertifikate zu sparen.</span><span class="sxs-lookup"><span data-stu-id="0327d-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0327d-108">Es kann einige Zeit dauern, bis Zertifikatanforderungen, insbesondere Anforderungen an öffentliche Zertifizierungsstellen, verarbeitet werden, daher sollten Sie Zertifikate für Ihre Edgeserver früh genug anfordern, um sicherzustellen, dass Sie verfügbar sind, wenn Sie die Bereitstellung Ihrer Edgeserver-Komponenten starten.</span><span class="sxs-lookup"><span data-stu-id="0327d-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="0327d-109">Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0327d-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0327d-110">Obwohl Sie eine öffentliche Zertifizierungsstelle für das interne Edge-Zertifikat verwenden können, empfiehlt es sich, stattdessen eine interne Unternehmenszertifizierungsstelle für diese anderen Zertifikate zu verwenden, um die Kosten für Zertifikate zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="0327d-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="0327d-111">Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0327d-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0327d-112">Wenn Sie einen Edgeserver installieren, enthält Setup einen Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten vereinfacht, wie im Abschnitt <A href="lync-server-2013-set-up-edge-certificates.md">Einrichten von Edge-Zertifikaten für lync Server 2013</A> beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0327d-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="0327d-113">Wenn Sie vor der Installation eines Edge-Servers Zertifikate anfordern möchten (beispielsweise um Zeit während der eigentlichen Bereitstellung von Edge-Server-Komponenten zu sparen), können Sie dies mit internen Servern tun, sofern Sie sicherstellen, dass die Zertifikate exportierbar sind und alle Erforderlicher Betreff-alternativer Name</span><span class="sxs-lookup"><span data-stu-id="0327d-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="0327d-114">In dieser Dokumentation werden keine Verfahren für die Verwendung interner Server zum Anfordern von Zertifikaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0327d-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="0327d-115">Anfordern von Zertifikaten von einer öffentlichen Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="0327d-115">Request certificates from a public CA</span></span>

<span data-ttu-id="0327d-116">Für die Bereitstellung von Edge-Servern ist ein einzelnes öffentliches Zertifikat für die externen Schnittstellen von Edgeserver erforderlich, das für den Access Edge-Dienst, den Webkonferenz-Edgedienst und für einen/V-Authentifizierungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0327d-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="0327d-117">Dieses Zertifikat muss über einen exportierbaren privaten Schlüssel verfügen, um sicherzustellen, dass der A/V-Authentifizierungsdienst die gleichen Schlüssel auf allen Edge-Servern in einem Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="0327d-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="0327d-118">Der Reverse-Proxy, der mit Microsoft Internet Security and Acceleration (ISA) Server 2006 oder Microsoft Forefront Threat Management Gateway 2010 verwendet wird, erfordert ebenfalls ein öffentliches Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="0327d-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="0327d-119">Anfordern von Zertifikaten von einer internen Unternehmenszertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="0327d-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="0327d-120">Die für die interne Edge-Schnittstelle erforderlichen Zertifikate können entweder von einer öffentlichen Zertifizierungsstelle (Certification Authority, ca) oder einer internen Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0327d-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="0327d-121">Sie können eine interne Unternehmenszertifizierungsstelle verwenden, um die Kosten für Zertifikate zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="0327d-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="0327d-122">Wenn in Ihrer Organisation eine interne Zertifizierungsstelle bereitgestellt wurde, sollten die Zertifikate für den internen Edge von der internen Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0327d-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="0327d-123">Durch die Verwendung einer internen Unternehmenszertifizierungsstelle für interne Zertifikate können die Kosten für Zertifikate reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="0327d-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="0327d-124">Eine Zusammenfassung der Zertifikatanforderungen für Edge-Komponenten finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0327d-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="0327d-125">Informationen zum Verwenden einer öffentlichen Zertifizierungsstelle zum Abrufen von Zertifikaten finden Sie unter [anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="0327d-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="0327d-126">Details zum anfordern, installieren und Zuweisen von Zertifikaten finden Sie unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0327d-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Anfordern von Zertifikaten für Edge-Komponenten'
description: 'Lync Server 2013: Anfordern von Zertifikaten für Edge-Komponenten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579011"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="31b41-103">Anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31b41-103">Request certificates for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31b41-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="31b41-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="31b41-105">Die erforderlichen Zertifikate für die Unterstützung des Zugriffs durch externe Benutzer umfassen Zertifikate, die von einer öffentlichen Zertifizierungsstelle ausgestellt wurden, sowie Zertifikate, die von einer internen Unternehmenszertifizierungsstelle ausgestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="31b41-105">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="31b41-106">Zertifikate, die für die externe Schnittstelle von Edgeserver und des Reverseproxys erforderlich sind, müssen von einer öffentlichen Zertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="31b41-106">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="31b41-107">Die für die interne Schnittstelle benötigten Zertifikate können entweder von einer öffentlichen oder von einer internen Unternehmenszertifizierungsstelle ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="31b41-107">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="31b41-108">Es wird empfohlen, eine interne Windows Server 2008 Zertifizierungsstelle, Windows Server 2008 R2 Zertifizierungsstelle, Windows Server 2012 Zertifizierungsstelle oder Windows Server 2012 R2-Zertifizierungsstelle zum Erstellen dieser Zertifikate zu verwenden, um die Kosten der Verwendung öffentlicher Zertifikate zu sparen.</span><span class="sxs-lookup"><span data-stu-id="31b41-108">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="31b41-109">Da die Verarbeitung von Zertifikatanforderungen (insbesondere bei Anforderungen an öffentliche Zertifizierungsstellen) mit einem gewissen Zeitaufwand verbunden sein kann, sollten Sie die Zertifikate für Ihre Edgeserver frühzeitig anfordern, um ihre Verfügbarkeit sicherzustellen, wenn Sie mit der Bereitstellung Ihrer Edgeserverkomponenten beginnen.</span><span class="sxs-lookup"><span data-stu-id="31b41-109">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="31b41-110">Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for external User Access in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31b41-110">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="31b41-111">Wenngleich Sie eine öffentliche Zertifizierungsstelle für das interne Edgezertifikat verwenden können, wird die Verwendung einer internen Unternehmenszertifizierungsstelle für diese anderen Zertifikate empfohlen, um die Kosten für Zertifikate zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="31b41-111">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="31b41-112">Eine Zusammenfassung der Zertifikatanforderungen für Edgeserver finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="31b41-112">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31b41-113">Wenn Sie ein Edgeserver installieren, enthält das Setup einen Zertifikat-Assistenten, der die Aufgaben zum anfordern, zuweisen und Installieren von Zertifikaten erleichtert, wie im Abschnitt <A href="lync-server-2013-set-up-edge-certificates.md">Einrichten von Edge-Zertifikaten für lync Server 2013</A> beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31b41-113">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="31b41-114">Wenn Sie vor der Installation eines Edgeserver Zertifikate anfordern möchten (beispielsweise um Zeit bei der tatsächlichen Bereitstellung von Edgeserver Komponenten zu sparen), können Sie dies mithilfe von internen Servern tun, solange Sie sicherstellen, dass die Zertifikate exportierbar sind und alle erforderlichen alternativen Antragstellernamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="31b41-114">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="31b41-115">In dieser Dokumentation werden keine Verfahren für die Verwendung interner Server zum Anfordern von Zertifikaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="31b41-115">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="31b41-116">Anfordern von Zertifikaten von einer öffentlichen Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="31b41-116">Request certificates from a public CA</span></span>

<span data-ttu-id="31b41-117">Für die Edgeserver-Bereitstellung ist ein einzelnes öffentliches Zertifikat für die externen Schnittstellen von Edgeserver erforderlich, das für die Zugriffs-Edgedienst, die Webkonferenz-Edgedienst und für den a/V-Authentifizierungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31b41-117">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="31b41-118">Dieses Zertifikat muss über einen exportierbaren privaten Schlüssel verfügen, um sicherzustellen, dass der A/V-Authentifizierungsdienst dieselben Schlüssel auf allen Edgeserver in einem Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="31b41-118">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="31b41-119">Für den Reverseproxy, der mit ISA (Microsoft Internet Security and Acceleration Server) 2006 oder Microsoft Forefront Threat Management Gateway 2010 verwendet wird, ist ebenfalls ein öffentliches Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31b41-119">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="31b41-120">Anfordern von Zertifikaten von einer internen Unternehmenszertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="31b41-120">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="31b41-p106">Die für die interne Edgeschnittstelle benötigten Zertifikate können entweder von einer öffentlichen oder von einer internen Zertifizierungsstelle ausgestellt werden. Mithilfe einer internen Unternehmenszertifizierungsstelle können Sie die Kosten für Zertifikate minimieren. Wenn in Ihrer Organisation eine interne Zertifizierungsstelle bereitgestellt wurde, sollten die Zertifikate für die interne Edgeschnittstelle durch die interne Zertifizierungsstelle ausgegeben werden. Das Verwenden einer internen Unternehmenszertifizierungsstelle für interne Zertifikate kann zu einer erheblichen Senkung der Kosten für Zertifikate beitragen.</span><span class="sxs-lookup"><span data-stu-id="31b41-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="31b41-125">Eine Zusammenfassung der Zertifikatanforderungen für Edge-Komponenten finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="31b41-125">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="31b41-126">Ausführliche Informationen zur Verwendung einer öffentlichen Zertifizierungsstelle zum Abrufen von Zertifikaten finden Sie unter [anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="31b41-126">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="31b41-127">Ausführliche Informationen zum anfordern, installieren und Zuweisen von Zertifikaten finden Sie unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="31b41-127">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


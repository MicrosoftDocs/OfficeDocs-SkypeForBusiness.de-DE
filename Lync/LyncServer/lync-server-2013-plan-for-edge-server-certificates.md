---
title: 'Lync Server 2013: Planen von Edgeserver Zertifikaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e2cf257b3bc6a17377ca5649307e4b2ba7bb5c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a><span data-ttu-id="869d3-102">Planen von Edgeserver Zertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="869d3-102">Plan for Edge Server certificates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="869d3-103">_**Letztes Änderungsstand des Themas:** 2012-11-05_</span><span class="sxs-lookup"><span data-stu-id="869d3-103">_**Topic Last Modified:** 2012-11-05_</span></span>

<span data-ttu-id="869d3-104">Die Erstellung von Zertifikaten für Edge wird in lync Server 2013 vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="869d3-104">Certificate creation for Edge is simplified in Lync Server 2013.</span></span>

<span data-ttu-id="869d3-105">**Flussdiagramm für Zertifikate für Edgeserver**</span><span class="sxs-lookup"><span data-stu-id="869d3-105">**Certificates Flow Chart for Edge Server**</span></span>

<span data-ttu-id="869d3-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span><span class="sxs-lookup"><span data-stu-id="869d3-106">![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")</span></span>

<span data-ttu-id="869d3-107">Erstellen Sie ein einzelnes öffentliches Zertifikat, stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel definiert ist, und weisen Sie ihn dem folgenden Edgeserver externe Schnittstellen mit dem Zertifikat-Assistenten zu:</span><span class="sxs-lookup"><span data-stu-id="869d3-107">Create a single public certificate, ensure that you have an exportable private key defined for the certificate, and assign it to the following Edge Server external interfaces using the certificate wizard:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="869d3-108">Platzhalterzertifikate werden in lync Server nicht unterstützt, es sei denn, es wird verwendet, um die einfachen URLs über den Reverseproxy zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="869d3-108">Wildcard certificates are not supported in Lync Server, except where used to summarize the Simple URLs through the reverse proxy.</span></span> <span data-ttu-id="869d3-109">Sie müssen eindeutige Alternative Antragstellernamen (SANs) für jeden SIP-Domänennamen, Webkonferenz-Edgedienst, A/V-Edgedienst und XMPP-Domäne definieren, die von Ihrer Bereitstellung angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="869d3-109">You must define distinct subject alternate names (SANs) for each SIP domain name, Web Conferencing Edge service, A/V Edge service and XMPP domain offered by your deployment.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="869d3-110">In lync Server 2013 eingeführt, erfordert das Staging von Audio/Video-Authentifizierungszertifikaten im Vorfeld der Ablaufzeit des aktuellen Zertifikats einige zusätzliche Planungsschritte.</span><span class="sxs-lookup"><span data-stu-id="869d3-110">Introduced in Lync Server 2013, staging Audio/Video Authentication certificates in advance of the expiration time of the current certificate requires some additional planning.</span></span> <span data-ttu-id="869d3-111">Anstelle eines Zertifikats mit mehreren Zwecken für die externe Edge-Schnittstelle benötigen Sie zwei Zertifikate, eine der Zugriffs-Edgedienst und Webkonferenz-Edgedienst und ein Zertifikat für die A/V-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="869d3-111">Instead of one certificate with multiple purposes for the external Edge interface, you will require two certificates, one assigned to the Access Edge service and Web Conferencing Edge service, and one certificate for the A/V Edge service.</span></span> <span data-ttu-id="869d3-112">Weitere Informationen finden Sie unter <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in lync Server 2013 using-Roll in Sets-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="869d3-112">For additional details, see <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</A></span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="869d3-113">Im Fall eines Pools von Edgeserver exportieren Sie das Zertifikat mit dem privaten Schlüssel für jeden Edgeserver und weisen das Zertifikat jedem Edgeserver Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="869d3-113">In the event of a pool of Edge Servers, you export the certificate with the private key to each Edge Server and assign the certificate to each Edge Server service.</span></span> <span data-ttu-id="869d3-114">Tun Sie dasselbe für das interne Edgeserver Zertifikat, exportieren Sie das Zertifikat mit dem privaten Schlüssel, und weisen Sie jede interne Edge-Schnittstelle zu.</span><span class="sxs-lookup"><span data-stu-id="869d3-114">Do the same for the internal Edge Server certificate, exporting the certificate with the private key and assigning to each internal Edge interface.</span></span>



</div>

  - <span data-ttu-id="869d3-115">Stellen Sie sicher, dass für das Zertifikat ein exportierbarer privater Schlüssel zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="869d3-115">Ensure that you have an exportable private key assigned for the certificate</span></span>

  - <span data-ttu-id="869d3-116">Zugriffs-Edgedienst (als SIP- **Zugriffs-Edge extern** im Zertifikat-Assistenten bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="869d3-116">Access Edge service (referred to as **SIP Access Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="869d3-117">Webkonferenz-Edgedienst (als **Webkonferenz-Edge extern** im Zertifikat-Assistenten bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="869d3-117">Web Conferencing Edge service (referred to as **Web Conferencing Edge External** in the certificate wizard)</span></span>

  - <span data-ttu-id="869d3-118">A/v-Authentifizierungsdienst (als **a/v-Edge extern** im Zertifikat-Assistenten bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="869d3-118">A/V Authentication service (referred to as **A/V Edge External** in the certificate wizard)</span></span>

<span data-ttu-id="869d3-119">Erstellen Sie ein einzelnes internes Zertifikat mit exportier barem privaten Schlüssel, kopieren Sie es, und weisen Sie es jedem der Edgeserver internen Schnittstellen zu:</span><span class="sxs-lookup"><span data-stu-id="869d3-119">Create a single internal certificate with exportable private key, copy and assign it to each of the Edge Server internal interfaces:</span></span>

  - <span data-ttu-id="869d3-120">Edgeserver (wird im Zertifikat-Assistenten als **interner Edge** bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="869d3-120">Edge Server (referred to as **Edge Internal** in the certificate wizard)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="869d3-121">Es ist möglich, separate und unterschiedliche Zertifikate für jeden Edgeserver Dienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="869d3-121">It is possible to use separate and distinct certificates for each Edge Server service.</span></span> <span data-ttu-id="869d3-122">Ein guter Grund für die Auswahl separater Zertifikate besteht darin, dass Sie das neue Feature für das parallele Zertifikat für das A/V-Edgedienst Zertifikat verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="869d3-122">A good reason to choose separate certificates is if you want to use the new rolling certificate feature for the A/V Edge service certificate.</span></span> <span data-ttu-id="869d3-123">Im Fall dieser Funktion wird das Entkoppeln des A/V-Edgedienst Zertifikats von der Zugriffs-Edgedienst und Webkonferenz-Edgedienst empfohlen.</span><span class="sxs-lookup"><span data-stu-id="869d3-123">In the case of this feature, decoupling the A/V Edge service certificate from the Access Edge service and Web Conferencing Edge service is recommended.</span></span> <span data-ttu-id="869d3-124">Wenn Sie für jeden Dienst separate Zertifikate anfordern, erwerben und zuweisen möchten, müssen Sie anfordern, dass der private Schlüssel für die A/V-Edgedienst exportierbar ist (wiederum ist dies der a/v-Authentifizierungsdienst), und weisen Sie das gleiche Zertifikat der externen a/v-Edge-Schnittstelle auf jeder Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="869d3-124">If you choose to request, acquire and assign separate certificates for each service, you must request that the private key be exportable for the A/V Edge service (again, this is in actuality the A/V Authentication service) and assign the same certificate to the A/V Edge External interface on each Edge Server.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="869d3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="869d3-125">See Also</span></span>


[<span data-ttu-id="869d3-126">Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Roll in der Gruppe CsCertificate</span><span class="sxs-lookup"><span data-stu-id="869d3-126">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[<span data-ttu-id="869d3-127">Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken</span><span class="sxs-lookup"><span data-stu-id="869d3-127">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


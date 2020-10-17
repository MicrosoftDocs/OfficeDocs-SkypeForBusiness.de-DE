---
title: 'Lync Server 2013: Planen der AutoErmittlung'
description: 'Lync Server 2013: Planen der AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544631"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="7f605-103">Planen der AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f605-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f605-104">_**Letztes Änderungsstand des Themas:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="7f605-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="7f605-105">Die AutoErmittlung wurde für lync Server im kumulativen Update für lync Server 2010: November 2011 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7f605-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="7f605-106">Der primäre Zweck für diese anfängliche Implementierung der AutoErmittlung bestand darin, einen Mittel für lync Mobile zum Auffinden des mobilitätsdiensts (MCX) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7f605-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="7f605-107">Der AutoErmittlungsdienst in lync Server 2013 ist jetzt ein Dienst, der von allen Clients zum Auffinden von Server-und Benutzerdiensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f605-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="7f605-108">Der Microsoft lync Server 2013 AutoErmittlungsdienst wird auf Directors und Front-End-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f605-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7f605-109">Ein besseres technisches Verständnis der AutoErmittlung und der Kommunikation mit den Clients finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Understanding AutoErmittlung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7f605-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="7f605-110">Mobilität ist nach wie vor ein klares Szenario, und für die Mobilitätsdienste ist noch eine spezielle Planung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f605-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="7f605-111">Weitere Informationen finden Sie unter <A href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7f605-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7f605-112">Wenn die AutoErmittlung in lync Server 2010 eingeführt wurde, mussten Kompromisse eingegangen werden, um einen Dienst zu implementieren, der potenzielle Zertifikat Änderungen an vorhandenen Server Bereitstellungen erforderlich machte.</span><span class="sxs-lookup"><span data-stu-id="7f605-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="7f605-113">Die AutoErmittlung kann über Port TCP 443 für HTTPS oder über Port TCP 80 für HTTP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f605-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="7f605-114">Wenn die Entscheidung für die Verwendung von HTTPS getroffen wurde, mussten Zertifikate für Reverse-Proxies, Directors und Front-End-Server erneut ausgestellt werden, um die erforderlichen `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` DNS-Einträge zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7f605-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="7f605-115">Wenn die Entscheidung für die Verwendung von http getroffen wurde, könnte die erneute Ausstellung von Zertifikaten vermieden werden, indem DNS-CNAME-Einträge (oder Alias) verwendet werden, um vorhandene Namen für die Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f605-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="7f605-116">Die Verwendung von http hat bedeutet, dass die anfängliche Kommunikation unverschlüsselt war.</span><span class="sxs-lookup"><span data-stu-id="7f605-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="7f605-117">Da lync Server 2013 AutoErmittlung für alle Clients verwendet, besteht das Hauptszenario darin, ausschließlich HTTPS zu verwenden und Zertifikate mit lyncdiscover zu erstellen.\<domain\></span><span class="sxs-lookup"><span data-stu-id="7f605-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="7f605-118">im Rahmen der Konfiguration von Reverse-Proxys, Directors und Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="7f605-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="7f605-119">Wenn Sie die AutoErmittlung in einer aktualisierten Bereitstellung von lync Server 2010 implementieren, können Sie http verwenden, um die Neuausstellung von Zertifikaten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7f605-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="7f605-120">Anleitungen für beide Szenarien finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="7f605-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f605-121">Die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein <EM>lyncdiscover enthalten. &lt; sipdomain " &gt; </EM> -Eintrag für jede SIP-Domäne in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7f605-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="7f605-122">Ausführliche Informationen zu den Einträgen für alternative Antragstellernamen, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-AutoErmittlung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7f605-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f605-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7f605-123">In This Section</span></span>

  - [<span data-ttu-id="7f605-124">Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f605-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="7f605-125">Port Zusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f605-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="7f605-126">DNS-Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f605-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="7f605-127">Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f605-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


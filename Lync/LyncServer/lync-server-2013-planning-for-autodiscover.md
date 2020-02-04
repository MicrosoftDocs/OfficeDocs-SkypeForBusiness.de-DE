---
title: 'Lync Server 2013: Planen der AutoErmittlung'
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
ms.openlocfilehash: 709b27059e1908a45b4b473f5380215bbd499d27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d0e93-102">Planen der AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e93-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0e93-103">_**Letztes Änderungsdatum des Themas:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="d0e93-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="d0e93-104">Die AutoErmittlung wurde für lync Server im kumulativen Update für lync Server 2010: November 2011 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d0e93-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="d0e93-105">Der Hauptzweckdieser anfänglichen Implementierung der AutoErmittlung war die Bereitstellungeines Mittel für lync Mobile zum Auffinden des mobilitätsdiensts (Mobility Service, MCX).</span><span class="sxs-lookup"><span data-stu-id="d0e93-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="d0e93-106">Der AutoErmittlungsdienst in lync Server 2013 ist jetzt ein Dienst, der von allen Clients zum Auffinden von Server-und Benutzerdiensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0e93-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="d0e93-107">Der Microsoft lync Server 2013-AutoErmittlungsdienst wird auf Directors und Front-End-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0e93-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d0e93-108">Ein besseres technisches Verständnis der AutoErmittlung und der Informationen, die Clients mitgeteilt werden, finden Sie unter <A href="lync-server-2013-understanding-autodiscover.md">Grundlegendes zu AutoErmittlung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0e93-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="d0e93-109">Mobilität ist nach wie vor ein eindeutiges Szenario, und die Mobilitätsdienste erfordern noch einige besondere Planungen.</span><span class="sxs-lookup"><span data-stu-id="d0e93-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="d0e93-110">Weitere Informationen finden Sie unter <A href="lync-server-2013-planning-for-mobility.md">Planen der Mobilität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0e93-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d0e93-111">Wenn AutoErmittlung in lync Server 2010 eingeführt wurde, gab es Kompromisse, die erforderlich sind, um einen Dienst zu implementieren, der potenzielle Zertifikat Änderungen an vorhandenen Server Bereitstellungen erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="d0e93-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="d0e93-112">AutoErmittlung kann über Port TCP 443 für HTTPS oder über Port TCP 80 für HTTP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0e93-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="d0e93-113">Wenn die Entscheidung zur Verwendung von HTTPS getroffen wurde, mussten Zertifikate für Reverse-Proxies, Directors und Front-End-Server erneut ausgestellt werden, um die erforderlichen `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` DNS-Einträge aufnehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="d0e93-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="d0e93-114">Wenn es sich um die Verwendung von http handelt, kann die erneute Ausstellung von Zertifikaten mithilfe von DNS-CNAME-Einträgen (oder Alias) verhindert werden, um vorhandene Namen auf den Zertifikaten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d0e93-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="d0e93-115">Die Verwendung von http bedeutete, dass die anfängliche Kommunikation unverschlüsselt war.</span><span class="sxs-lookup"><span data-stu-id="d0e93-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="d0e93-116">Da lync Server 2013 die AutoErmittlung für alle Clients verwendet, besteht das Hauptszenario darin, nur HTTPS zu verwenden und Zertifikate mit lyncdiscover zu erstellen. \<Domäne\> als Teil der Konfiguration von Reverse-Proxies, Directors und Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="d0e93-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="d0e93-117">Wenn Sie die AutoErmittlung in einer aktualisierten Bereitstellung von lync Server 2010 implementieren, möchten Sie möglicherweise http verwenden, um die erneute Ausstellung von Zertifikaten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d0e93-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="d0e93-118">Anleitungen für beide Szenarien finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="d0e93-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0e93-119">Die Liste Subject Alternative Name für Zertifikate, die von der externen Webdienste-Veröffentlichungsregel verwendet werden, muss eine <EM>lyncdiscover enthalten.&lt; sipdomain&gt; </EM> -Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d0e93-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="d0e93-120">Details zu den Einträgen des alternativen betreffs, die für Directors, Front-End-Server und Reverse-Proxies erforderlich sind, finden Sie unter <A href="lync-server-2013-certificate-summary-autodiscover.md">Zertifikats Zusammenfassung – AutoErmittlung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d0e93-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0e93-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d0e93-121">In This Section</span></span>

  - [<span data-ttu-id="d0e93-122">Zertifikatzusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e93-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="d0e93-123">Port Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e93-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="d0e93-124">DNS-Zusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e93-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="d0e93-125">Hybrid-und Split-Domain-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e93-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


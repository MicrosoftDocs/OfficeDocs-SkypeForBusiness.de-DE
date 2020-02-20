---
title: 'Lync Server 2013: direkte SIP-Bereitstellungsoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d3d51c8323ab448951255ac9f7cf8d284896ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="5f2b1-102">Direkte SIP-Bereitstellungsoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f2b1-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f2b1-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5f2b1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5f2b1-104">Dieses Thema enthält Beispiel Topologien für die Bereitstellung von direkten SIP-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="5f2b1-105">Lync Server eigenständig</span><span class="sxs-lookup"><span data-stu-id="5f2b1-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="5f2b1-106">Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie lync Server 2013 als einzige Telefonielösung für einen Teil oder die gesamte Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="5f2b1-107">In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:</span><span class="sxs-lookup"><span data-stu-id="5f2b1-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="5f2b1-108">**Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und Enterprise-VoIP inkrementell in kleineren Gruppen oder Teams in Ihrer Organisation einführen möchten.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="5f2b1-109">**Lync Server nur-VoIP-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einem Standort erwägen, der über keine herkömmliche Telefonie-Infrastruktur verfügt.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="5f2b1-110">Inkrementelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5f2b1-110">Incremental Deployment</span></span>

<span data-ttu-id="5f2b1-111">Bei der inkrementellen Bereitstellung ist lync Server 2013 die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Nebenstellenanlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="5f2b1-112">Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, IP-Telefonie mithilfe von kontrollierten Pilotprogrammen in Ihr Unternehmen einzuführen.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="5f2b1-113">Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications bedient werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Nebenstellenanlage verbleiben.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="5f2b1-114">Bei Bedarf können zusätzliche Arbeitsgruppen zu Enterprise-VoIP migriert werden.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="5f2b1-115">Die inkrementelle Option wird empfohlen, wenn Sie über klar definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen haben und sich für eine zentralisierte Verwaltung eignen.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="5f2b1-116">Diese Option ist auch dann wirksam, wenn Sie über Teams oder Abteilungen verfügen, die sich über große geografische Bereiche verteilen, wobei die Einsparungen bei den Gebühren für Ferngespräche beträchtlich sein können.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="5f2b1-117">Diese Option ist tatsächlich nützlich, um virtuelle Teams zu erstellen, deren Mitglieder sich möglicherweise auf der ganzen Welt verteilen.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="5f2b1-118">Sie können solche Teams in einer schnellen Reaktion auf wechselnde Geschäftsanforderungen erstellen, ändern oder auflösen.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="5f2b1-119">In der folgenden Abbildung ist die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="5f2b1-120">Dies ist die empfohlene Topologie für die inkrementelle Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="5f2b1-121">**Option für die inkrementelle Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="5f2b1-121">**Incremental deployment option**</span></span>

<span data-ttu-id="5f2b1-122">![Diagramm zur Abteilungs Migrations Option](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramm zur Abteilungs Migrations Option")</span><span class="sxs-lookup"><span data-stu-id="5f2b1-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f2b1-123">Wenn Sie Ihre lync Server-Bereitstellung mit einem zertifizierten direkten SIP-Partner verbinden, ist ein PSTN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Nebenstellenanlage nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="5f2b1-124">Eine Liste mit zertifizierten Direct SIP-Partnern finden Sie auf <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>der Website Microsoft Unified Communications Open Interoperability Program unter.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5f2b1-125">Für den in dieser Abbildung gezeigten Medienpfad ist die medienumgehung aktiviert (empfohlene Konfiguration).</span><span class="sxs-lookup"><span data-stu-id="5f2b1-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="5f2b1-126">Wenn Sie die medienumgehung deaktivieren, wird der Medienpfad durch den Vermittlungsserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="5f2b1-127">In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="5f2b1-128">Ein PSTN-Gateway verbindet die VoIP-fähige Arbeitsgruppe (Voice over Internet Protocol) mit der Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="5f2b1-129">Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remote Arbeitsthreads, kommunizieren über das IP-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="5f2b1-130">Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="5f2b1-131">Anrufe von Kollegen, die sich noch im PBX-System oder von Anrufern im PSTN befinden, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an lync Server weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="5f2b1-132">Es gibt zwei Empfohlene Konfigurationen für die Anbindung von Enterprise-VoIP an eine vorhandene PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="5f2b1-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="5f2b1-133">Enterprise-VoIP hinter der Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="5f2b1-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="5f2b1-134">Wenn Enterprise-VoIP hinter der Nebenstellenanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Nebenstellenanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet und Anrufe an PBX-Benutzer an die Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="5f2b1-135">Enterprise-VoIP vor der Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="5f2b1-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="5f2b1-136">Wenn Enterprise-VoIP vor der Nebenstellenanlage bereitgestellt wird, werden alle Anrufe an das PSTN-Gateway geleitet, das Anrufe für Enterprise-VoIP-Benutzer an lync Server weiterleitet und PBX-Benutzer zur Nebenstellenanlage aufruft.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="5f2b1-137">Anrufe an das PSTN sowohl von Enterprise-VoIP-als auch von PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="5f2b1-138">In der folgenden Tabelle sind die vor-und Nachteile dieser Konfiguration aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="5f2b1-139">Vor-und Nachteile der Bereitstellung von Enterprise-VoIP vor der Nebenstellenanlage</span><span class="sxs-lookup"><span data-stu-id="5f2b1-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f2b1-140">Vorteile</span><span class="sxs-lookup"><span data-stu-id="5f2b1-140">Advantages</span></span></th>
<th><span data-ttu-id="5f2b1-141">Nachteile</span><span class="sxs-lookup"><span data-stu-id="5f2b1-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f2b1-142">PBX bedient weiterhin Benutzer, die nicht für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="5f2b1-143">Vorhandene Gateways unterstützen möglicherweise nicht die gewünschten Features oder Kapazitäten.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b1-144">PBX verarbeitet alle älteren Geräte.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="5f2b1-145">Erfordert einen trunk vom Gateway zur Nebenstellenanlage und vom Gateway zum Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="5f2b1-146">Möglicherweise benötigen Sie weitere Trunks vom Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2b1-147">Enterprise-VoIP-Benutzer behalten dieselben Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="5f2b1-148">Lync Server nur-VoIP-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5f2b1-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="5f2b1-149">Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine umfassende VoIP-Lösung zu implementieren, ohne sich Gedanken über die Integration von Nebenstellenanlagen oder die erhebliche Bereitstellung und Wartung machen zu müssen. Kosten einer IP-PBX-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="5f2b1-150">Diese Lösung unterstützt sowohl vor-Ort-als auch Remote-Arbeitskräfte.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="5f2b1-151">In dieser Bereitstellung werden alle Anrufe über das IP-Netzwerk weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="5f2b1-152">Anrufe an das PSTN werden an das entsprechende PSTN-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="5f2b1-153">Lync 2013 oder lync Phone Edition dient als Softphone.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="5f2b1-154">Die Remote Anrufsteuerung ist nicht verfügbar und unnötig, da es keine Nebenstellentelefone gibt, die von Benutzern gesteuert werden können.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="5f2b1-155">Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f2b1-156">Zusätzlich zur Netzwerkinfrastruktur, die zur Unterstützung von lync Server 2013 erforderlich ist, kann eine nur-VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="5f2b1-157">In der folgenden Abbildung ist eine typische Topologie für eine reine VoIP-Bereitstellung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="5f2b1-158">**Reine VoIP-Bereitstellung (Option)**</span><span class="sxs-lookup"><span data-stu-id="5f2b1-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="5f2b1-159">![Greenfidle-Bereitstellungsoption](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle-Bereitstellungsoption")</span><span class="sxs-lookup"><span data-stu-id="5f2b1-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f2b1-160">Für den in dieser Abbildung gezeigten Medienpfad ist die medienumgehung aktiviert (empfohlene Konfiguration).</span><span class="sxs-lookup"><span data-stu-id="5f2b1-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="5f2b1-161">Wenn Sie die medienumgehung deaktivieren, wird der Medienpfad durch den Vermittlungsserver weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5f2b1-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


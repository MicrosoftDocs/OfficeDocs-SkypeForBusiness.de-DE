---
title: 'Lync Server 2013: Optionen für Bereitstellungen mit direkten SIP-Verbindungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="7d881-102">Optionen für Bereitstellungen mit direkten SIP-Verbindungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d881-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d881-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7d881-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7d881-104">In diesem Thema finden Sie Beispiel Topologien für die Bereitstellung direkter SIP-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="7d881-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="7d881-105">Lync Server eigenständig</span><span class="sxs-lookup"><span data-stu-id="7d881-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="7d881-106">Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie lync Server 2013 als einzige Telefonlösung für einen Teil oder eine ganze Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d881-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="7d881-107">This section describes the following deployments in detail:</span><span class="sxs-lookup"><span data-stu-id="7d881-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="7d881-108">**Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und beabsichtigen, Enterprise-VoIP inkrementell für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einzuführen.</span><span class="sxs-lookup"><span data-stu-id="7d881-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="7d881-109">**Reine lync Server-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einer Website erwägen, die keine herkömmliche Telefonie-Infrastruktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="7d881-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="7d881-110">Incremental Deployment</span><span class="sxs-lookup"><span data-stu-id="7d881-110">Incremental Deployment</span></span>

<span data-ttu-id="7d881-111">Bei der inkrementellen Bereitstellung ist lync Server 2013 die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Telefonanlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d881-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="7d881-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span><span class="sxs-lookup"><span data-stu-id="7d881-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="7d881-113">Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Telefonanlage verbleiben.</span><span class="sxs-lookup"><span data-stu-id="7d881-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="7d881-114">Zusätzliche Arbeitsgruppen können nach Bedarf in Enterprise-VoIP migriert werden.</span><span class="sxs-lookup"><span data-stu-id="7d881-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="7d881-p103">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management. This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant. In fact, this option is useful for creating virtual teams whose members may be scattered across the globe. You can create, modify, or disband such teams in rapid response to shifting business requirements.</span><span class="sxs-lookup"><span data-stu-id="7d881-p103">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management. This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant. In fact, this option is useful for creating virtual teams whose members may be scattered across the globe. You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="7d881-119">Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="7d881-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="7d881-120">This is the recommended topology for incremental deployment.</span><span class="sxs-lookup"><span data-stu-id="7d881-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="7d881-121">**Incremental deployment option**</span><span class="sxs-lookup"><span data-stu-id="7d881-121">**Incremental deployment option**</span></span>

<span data-ttu-id="7d881-122">![Diagramm zur Option] für die Abteilungs Migration (images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramm zur Option") für die Abteilungs Migration</span><span class="sxs-lookup"><span data-stu-id="7d881-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d881-123">Wenn Sie Ihre lync Server-Bereitstellung mit einem zertifizierten direkten SIP-Partner verbinden, ist kein PSTN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Telefonanlage erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d881-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="7d881-124">Eine Liste der zertifizierten Direct SIP-Partner finden Sie auf <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>der Microsoft Unified Communications Open Interoperability Program-Website unter.</span><span class="sxs-lookup"><span data-stu-id="7d881-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7d881-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span><span class="sxs-lookup"><span data-stu-id="7d881-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="7d881-126">Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d881-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="7d881-127">In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d881-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="7d881-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span><span class="sxs-lookup"><span data-stu-id="7d881-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="7d881-129">Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeitern, kommunizieren über das IP-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="7d881-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="7d881-130">Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d881-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="7d881-131">Anrufe von Kollegen, die sich noch im PBX-System befinden, oder von Anrufern im PSTN, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an den lync-Server für das Routing weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="7d881-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="7d881-132">Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP zu einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Telefonanlage und Enterprise-VoIP vor der Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="7d881-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="7d881-133">Enterprise Voice Behind the PBX</span><span class="sxs-lookup"><span data-stu-id="7d881-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="7d881-134">Wenn Enterprise-VoIP hinter der Telefonanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Telefonanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet, und Anrufe an PBX-Benutzer an die Telefonanlage.</span><span class="sxs-lookup"><span data-stu-id="7d881-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="7d881-135">Enterprise Voice in Front of the PBX</span><span class="sxs-lookup"><span data-stu-id="7d881-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="7d881-136">Wenn Enterprise-VoIP vor der Telefonanlage bereitgestellt wird, kommen alle Anrufe an das PSTN-Gateway, das Anrufe an Enterprise-VoIP-Benutzer an den lync-Server weiterleitet und für PBX-Benutzer an die Telefonanlage anruft.</span><span class="sxs-lookup"><span data-stu-id="7d881-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="7d881-137">Anrufe an das PSTN von Enterprise-VoIP-und PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d881-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="7d881-138">The following table shows the advantages and disadvantages of this configuration.</span><span class="sxs-lookup"><span data-stu-id="7d881-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="7d881-139">Vor-und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Telefonanlage</span><span class="sxs-lookup"><span data-stu-id="7d881-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d881-140">Advantages</span><span class="sxs-lookup"><span data-stu-id="7d881-140">Advantages</span></span></th>
<th><span data-ttu-id="7d881-141">Disadvantages</span><span class="sxs-lookup"><span data-stu-id="7d881-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d881-142">PBX bietet weiterhin Benutzern, die nicht für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7d881-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="7d881-143">Existing gateways may not support the features or capacity that you want.</span><span class="sxs-lookup"><span data-stu-id="7d881-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d881-144">PBX handles all earlier devices.</span><span class="sxs-lookup"><span data-stu-id="7d881-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="7d881-145">Erfordert einen trunk vom Gateway zur Telefonanlage und vom Gateway zum Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="7d881-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="7d881-146">You may need more trunks from the service provider.</span><span class="sxs-lookup"><span data-stu-id="7d881-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d881-147">Enterprise-VoIP-Benutzer behalten die gleichen Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="7d881-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="7d881-148">Nur-VoIP-Bereitstellung von lync Server</span><span class="sxs-lookup"><span data-stu-id="7d881-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="7d881-149">Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine vollständige VoIP-Lösung zu implementieren, ohne sich um die Integration von Telefonanlagen zu kümmern oder um eine beträchtliche Bereitstellung und Wartung zu vermeiden. Kosten einer IP-PBX-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="7d881-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="7d881-150">This solution supports both on-site and remote workers.</span><span class="sxs-lookup"><span data-stu-id="7d881-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="7d881-151">In this deployment, all calls are routed over the IP network.</span><span class="sxs-lookup"><span data-stu-id="7d881-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="7d881-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span><span class="sxs-lookup"><span data-stu-id="7d881-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="7d881-153">Lync 2013 oder lync Phone Edition dient als Softphone.</span><span class="sxs-lookup"><span data-stu-id="7d881-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="7d881-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span><span class="sxs-lookup"><span data-stu-id="7d881-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="7d881-155">Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7d881-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d881-156">Zusätzlich zur Netzwerkinfrastruktur, die für die Unterstützung von lync Server 2013 erforderlich ist, kann eine reine VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d881-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="7d881-157">The following figure shows a typical topology for a VoIP-only deployment.</span><span class="sxs-lookup"><span data-stu-id="7d881-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="7d881-158">**VoIP-only deployment option**</span><span class="sxs-lookup"><span data-stu-id="7d881-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="7d881-159">![Greenfidle-Bereitstellungsoption] (images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle-Bereitstellungsoption")</span><span class="sxs-lookup"><span data-stu-id="7d881-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d881-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span><span class="sxs-lookup"><span data-stu-id="7d881-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="7d881-161">Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d881-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


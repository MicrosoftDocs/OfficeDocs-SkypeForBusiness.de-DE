---
title: 'Lync Server 2013: DNS-Zusammenfassung für Reverseproxy'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="82031-102">DNS-Zusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82031-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82031-103">_**Letztes Änderungsdatum des Themas:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="82031-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="82031-104">Sie konfigurieren zwei Netzwerkadapter in Ihrem Reverse-Proxy wie folgt:</span><span class="sxs-lookup"><span data-stu-id="82031-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="82031-105">Anforderungen des Reverse Proxy-Netzwerkadapters</span><span class="sxs-lookup"><span data-stu-id="82031-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="82031-106">Beispiel für **einen Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="82031-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="82031-107">Interne Schnittstelle mit zugewiesenem 172.25.33.40</span><span class="sxs-lookup"><span data-stu-id="82031-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="82031-108">Es wurde kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="82031-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="82031-109">Stellen Sie sicher, dass eine Route aus dem Netzwerk mit der internen Reverse Proxy-Schnittstelle zu allen Netzwerken vorhanden ist, die lync Server-Front-End-Pool Server enthalten (beispielsweise von 172.25.33.0 zu 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="82031-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="82031-110">Beispiel für **Netzwerkadapter 2 (externe Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="82031-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="82031-111">Diesem Netzwerkadapter wird mindestens eine öffentliche IP-Adresse zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="82031-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="82031-112">Gateway wird definiert, um auf den Router oder die integrierte Firewall im äußeren Umkreis zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="82031-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="82031-113">(10.45.16.1 in den Szenario-Beispielen)</span><span class="sxs-lookup"><span data-stu-id="82031-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="82031-114">Für Reverse-Proxy erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="82031-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82031-115">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="82031-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="82031-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="82031-116">FQDN</span></span></th>
<th><span data-ttu-id="82031-117">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="82031-117">IP address</span></span></th>
<th><span data-ttu-id="82031-118">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="82031-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82031-119">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="82031-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="82031-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82031-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="82031-121">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="82031-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="82031-122">Externe Webdienste aus der internen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="82031-122">External web services from the internal deployment.</span></span> <span data-ttu-id="82031-123">Zusätzliche Datensätze können für alle Pools und Einzelserver für alle SIP-Domänen definiert und erstellt werden, die diesen Reverseproxy verwenden, und hat externe Webdienste definiert.</span><span class="sxs-lookup"><span data-stu-id="82031-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82031-124">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="82031-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="82031-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82031-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="82031-126">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="82031-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="82031-127">Externe Webdienste für die Directors-oder Director-Pools in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="82031-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="82031-128">Sie können beliebig viele Directors definieren, da es verschiedene Directors gibt, die möglicherweise anderen SIP-Domänen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="82031-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="82031-129">Das Definieren der DNS-Einträge für und die Veröffentlichung der Directors ist weder der Front-End-Pool noch die Entscheidung des Regisseurs.</span><span class="sxs-lookup"><span data-stu-id="82031-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="82031-130">Sie müssen sowohl den Director als auch den Front-End-Pool externer Webdienste definieren und veröffentlichen, wenn Sie Directors verwenden.</span><span class="sxs-lookup"><span data-stu-id="82031-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="82031-131">Bestimmte Datenverkehrstypen (für Authentifizierung und andere Verwendungszwecke) werden zuerst an den Director gesendet, wenn er in der Topologie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="82031-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82031-132">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="82031-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="82031-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82031-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="82031-134">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="82031-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="82031-135">Extern veröffentlichte Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="82031-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82031-136">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="82031-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="82031-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82031-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="82031-138">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="82031-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="82031-139">Extern veröffentlichte Konferenzen</span><span class="sxs-lookup"><span data-stu-id="82031-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82031-140">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="82031-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="82031-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82031-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="82031-142">Zugeordneter Listener für Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="82031-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="82031-143">Office Web Apps Server wird intern oder im Umkreis bereitgestellt und für den Zugriff auf externe Clients veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="82031-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82031-144">Externer DNS/A</span><span class="sxs-lookup"><span data-stu-id="82031-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="82031-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82031-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="82031-146">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="82031-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="82031-147">Lync erkennt externen Eintrag für extern veröffentlichte AutoErmittlung und umfasst Mobilität, Microsoft lync Web App und Scheduler Web App</span><span class="sxs-lookup"><span data-stu-id="82031-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


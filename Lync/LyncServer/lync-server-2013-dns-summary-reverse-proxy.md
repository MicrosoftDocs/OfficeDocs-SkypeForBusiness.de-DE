---
title: 'Lync Server 2013: DNS-Zusammenfassung-Reverseproxy'
description: 'Lync Server 2013: DNS Summary-Reverse Proxy.'
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
ms.openlocfilehash: dc2d806893786a11317be1eff9bfdc08c9230bf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544791"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="31fee-103">DNS-Zusammenfassung-Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31fee-103">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31fee-104">_**Letztes Änderungsstand des Themas:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="31fee-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="31fee-105">Sie können die zwei Netzwerkadapter auf Ihrem Reverseproxy folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="31fee-105">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="31fee-106">Netzwerkadapteranforderungen für Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="31fee-106">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="31fee-107">Beispiel **Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="31fee-107">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="31fee-108">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.40.</span><span class="sxs-lookup"><span data-stu-id="31fee-108">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="31fee-109">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="31fee-109">No default gateway is defined.</span></span>
    
    <span data-ttu-id="31fee-110">Stellen Sie sicher, dass es eine Route aus dem Netzwerk mit der internen Reverseproxy-Schnittstelle zu Netzwerken gibt, die lync Server Front-End-Pool-Server enthalten (beispielsweise von 172.25.33.0 zu 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="31fee-110">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="31fee-111">Beispiel **Netzwerkadapter 2 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="31fee-111">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="31fee-112">Diesem Netzwerkadapter ist mindestens eine öffentliche IP-Adresse zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="31fee-112">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="31fee-p101">Das Gateway ist so definiert, dass es auf den Router oder die integrierte Firewall in Ihrem äußeren Umkreis zeigt (10.45.16.1 in den Szenariobeispielen).</span><span class="sxs-lookup"><span data-stu-id="31fee-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="31fee-115">Für Reverseproxy erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="31fee-115">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31fee-116">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="31fee-116">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="31fee-117">FQDN</span><span class="sxs-lookup"><span data-stu-id="31fee-117">FQDN</span></span></th>
<th><span data-ttu-id="31fee-118">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="31fee-118">IP address</span></span></th>
<th><span data-ttu-id="31fee-119">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="31fee-119">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31fee-120">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="31fee-120">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="31fee-121">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31fee-121">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31fee-122">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31fee-122">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="31fee-p102">Externe Webdienste aus der internen Bereitstellung. Zusätzliche Einträge können definiert und für alle Pools und einzelne Server für eine beliebige SIP-Domäne konfiguriert werden, die diesen Reverseproxy verwendet und für die externe Webdienste definiert sind.</span><span class="sxs-lookup"><span data-stu-id="31fee-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fee-125">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="31fee-125">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="31fee-126">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31fee-126">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31fee-127">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31fee-127">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="31fee-128">Externe Webdienste für die Directors-oder Director-Pools in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="31fee-128">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="31fee-129">Sie können beliebig viele Directors definieren, da es verschiedene Directors gibt, von denen möglicherweise anderen SIP-Domänen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="31fee-129">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="31fee-130">Das Definieren der DNS-Einträge für und das Veröffentlichen der Directors ist weder die Front-End-Pool noch die Entscheidung des Direktors.</span><span class="sxs-lookup"><span data-stu-id="31fee-130">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="31fee-131">Sie müssen sowohl die Director-als auch die Front-End-Pool externen Webdienste definieren und veröffentlichen, wenn Sie Directors verwenden.</span><span class="sxs-lookup"><span data-stu-id="31fee-131">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="31fee-132">Bestimmte Datenverkehrstypen (für Authentifizierung und andere Zwecke) werden zuerst an den Director gesendet, wenn Sie in der Topologie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="31fee-132">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fee-133">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="31fee-133">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="31fee-134">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31fee-134">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31fee-135">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31fee-135">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="31fee-136">Extern veröffentlichte Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="31fee-136">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fee-137">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="31fee-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="31fee-138">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31fee-138">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31fee-139">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31fee-139">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="31fee-140">Extern veröffentlichte Konferenzen</span><span class="sxs-lookup"><span data-stu-id="31fee-140">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fee-141">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="31fee-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="31fee-142">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31fee-142">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31fee-143">Zugewiesener Listener für Office-webapps Server</span><span class="sxs-lookup"><span data-stu-id="31fee-143">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="31fee-144">Office-webapps-Server, der intern oder im Umkreis bereitgestellt und für den externen Clientzugriff veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="31fee-144">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fee-145">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="31fee-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="31fee-146">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="31fee-146">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="31fee-147">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31fee-147">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="31fee-148">Externer Eintrag für lync Discover für extern veröffentlichte AutoErmittlung und umfasst Mobility, Microsoft lync Web App und Scheduler-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="31fee-148">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


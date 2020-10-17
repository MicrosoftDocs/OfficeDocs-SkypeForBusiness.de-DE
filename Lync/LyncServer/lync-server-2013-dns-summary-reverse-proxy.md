---
title: 'Lync Server 2013: DNS-Zusammenfassung-Reverseproxy'
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
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532142"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="c5a70-102">DNS-Zusammenfassung-Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a70-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5a70-103">_**Letztes Änderungsstand des Themas:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="c5a70-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="c5a70-104">Sie können die zwei Netzwerkadapter auf Ihrem Reverseproxy folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c5a70-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="c5a70-105">Netzwerkadapteranforderungen für Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="c5a70-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="c5a70-106">Beispiel **Netzwerkadapter 1 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="c5a70-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="c5a70-107">Interne Schnittstelle mit zugewiesener Adresse 172.25.33.40.</span><span class="sxs-lookup"><span data-stu-id="c5a70-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="c5a70-108">Es ist kein Standardgateway definiert.</span><span class="sxs-lookup"><span data-stu-id="c5a70-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="c5a70-109">Stellen Sie sicher, dass es eine Route aus dem Netzwerk mit der internen Reverseproxy-Schnittstelle zu Netzwerken gibt, die lync Server Front-End-Pool-Server enthalten (beispielsweise von 172.25.33.0 zu 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="c5a70-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="c5a70-110">Beispiel **Netzwerkadapter 2 (interne Schnittstelle)**</span><span class="sxs-lookup"><span data-stu-id="c5a70-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="c5a70-111">Diesem Netzwerkadapter ist mindestens eine öffentliche IP-Adresse zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c5a70-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="c5a70-p101">Das Gateway ist so definiert, dass es auf den Router oder die integrierte Firewall in Ihrem äußeren Umkreis zeigt (10.45.16.1 in den Szenariobeispielen).</span><span class="sxs-lookup"><span data-stu-id="c5a70-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="c5a70-114">Für Reverseproxy erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="c5a70-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a70-115">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="c5a70-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c5a70-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="c5a70-116">FQDN</span></span></th>
<th><span data-ttu-id="c5a70-117">IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a70-117">IP address</span></span></th>
<th><span data-ttu-id="c5a70-118">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="c5a70-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a70-119">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="c5a70-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c5a70-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5a70-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5a70-121">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c5a70-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="c5a70-p102">Externe Webdienste aus der internen Bereitstellung. Zusätzliche Einträge können definiert und für alle Pools und einzelne Server für eine beliebige SIP-Domäne konfiguriert werden, die diesen Reverseproxy verwendet und für die externe Webdienste definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c5a70-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a70-124">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="c5a70-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c5a70-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5a70-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5a70-126">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c5a70-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="c5a70-127">Externe Webdienste für die Directors-oder Director-Pools in Ihrer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="c5a70-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="c5a70-128">Sie können beliebig viele Directors definieren, da es verschiedene Directors gibt, von denen möglicherweise anderen SIP-Domänen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c5a70-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="c5a70-129">Das Definieren der DNS-Einträge für und das Veröffentlichen der Directors ist weder die Front-End-Pool noch die Entscheidung des Direktors.</span><span class="sxs-lookup"><span data-stu-id="c5a70-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="c5a70-130">Sie müssen sowohl die Director-als auch die Front-End-Pool externen Webdienste definieren und veröffentlichen, wenn Sie Directors verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5a70-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="c5a70-131">Bestimmte Datenverkehrstypen (für Authentifizierung und andere Zwecke) werden zuerst an den Director gesendet, wenn Sie in der Topologie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c5a70-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a70-132">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="c5a70-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c5a70-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5a70-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5a70-134">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c5a70-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="c5a70-135">Extern veröffentlichte Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="c5a70-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a70-136">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="c5a70-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c5a70-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5a70-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5a70-138">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c5a70-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="c5a70-139">Extern veröffentlichte Konferenzen</span><span class="sxs-lookup"><span data-stu-id="c5a70-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a70-140">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="c5a70-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c5a70-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5a70-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5a70-142">Zugewiesener Listener für Office-webapps Server</span><span class="sxs-lookup"><span data-stu-id="c5a70-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="c5a70-143">Office-webapps-Server, der intern oder im Umkreis bereitgestellt und für den externen Clientzugriff veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="c5a70-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a70-144">Externer DNS-Eintrag/A</span><span class="sxs-lookup"><span data-stu-id="c5a70-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c5a70-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5a70-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c5a70-146">Zugewiesener Listener für extern veröffentlichte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c5a70-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="c5a70-147">Externer Eintrag für lync Discover für extern veröffentlichte AutoErmittlung und umfasst Mobility, Microsoft lync Web App und Scheduler-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="c5a70-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


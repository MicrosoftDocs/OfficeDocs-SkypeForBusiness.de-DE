---
title: 'Lync Server 2013: Zertifikatzusammenfassung-Reverseproxy'
description: 'Lync Server 2013: Zertifikatzusammenfassung-Reverseproxy.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572301"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="74970-103">Zertifikatzusammenfassung-Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74970-103">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74970-104">_**Letztes Änderungsstand des Themas:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="74970-104">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="74970-105">Die Zertifikatanforderungen für den Reverseproxy sind wesentlich einfacher als für die Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="74970-105">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="74970-106">Das bereitgestellte Flussdiagramm stellt die erforderlichen Anforderungen dar.</span><span class="sxs-lookup"><span data-stu-id="74970-106">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="74970-107">In der begleitenden Tabelle werden typische Zertifikatsantrags Teller Namen und alternative Antragstellernamen im Zusammenhang mit den Szenarien dargestellt, die wir in den Edgeserver Diskussionen überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="74970-107">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="74970-108">Weitere Informationen zu den Edgeserver Szenarien finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="74970-108">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="74970-109">**Flussdiagramm für Zertifikate für Reverse-Proxy**</span><span class="sxs-lookup"><span data-stu-id="74970-109">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="74970-110">![Flussdiagramm für Zertifikate für Edgeserver](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Flussdiagramm für Zertifikate für Edgeserver")</span><span class="sxs-lookup"><span data-stu-id="74970-110">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="74970-111">Reverse Proxy: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74970-111">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74970-112">Komponente</span><span class="sxs-lookup"><span data-stu-id="74970-112">Component</span></span></th>
<th><span data-ttu-id="74970-113">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="74970-113">Subject name</span></span></th>
<th><span data-ttu-id="74970-114">Alternativer Antragstellername (San)/Order</span><span class="sxs-lookup"><span data-stu-id="74970-114">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="74970-115">Kommentare</span><span class="sxs-lookup"><span data-stu-id="74970-115">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74970-116">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="74970-116">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="74970-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-117">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="74970-118">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-118">webext.contoso.com</span></span></p>
<p><span data-ttu-id="74970-119">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-119">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="74970-120">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-120">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="74970-121">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-121">meet.contoso.com</span></span></p>
<p><span data-ttu-id="74970-122">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-122">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="74970-123">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-123">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="74970-124">(Optional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="74970-124">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="74970-125">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle und mit der Server-EKU ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="74970-125">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="74970-126">Zu den Diensten gehören Adressbuchdienst, Expansion von Verteilergruppen für Office-Webanwendungen für Konferenzen und Veröffentlichungsregeln für lync-IP-Geräte.</span><span class="sxs-lookup"><span data-stu-id="74970-126">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="74970-127">Alternative Antragstellernamen:</span><span class="sxs-lookup"><span data-stu-id="74970-127">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="74970-128">Externer Webdienste FQDN für Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="74970-128">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="74970-129">Externer Webdienste FQDN für Director oder Directorpool</span><span class="sxs-lookup"><span data-stu-id="74970-129">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="74970-130">Einwahlkonferenz</span><span class="sxs-lookup"><span data-stu-id="74970-130">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="74970-131">Veröffentlichungsregel für Online Besprechungen</span><span class="sxs-lookup"><span data-stu-id="74970-131">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="74970-132">Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="74970-132">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="74970-133">Lyncdiscover (AutoErmittlung)</span><span class="sxs-lookup"><span data-stu-id="74970-133">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="74970-134">Der optionale Platzhalter ersetzt "Meet" und "Dialin San".</span><span class="sxs-lookup"><span data-stu-id="74970-134">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


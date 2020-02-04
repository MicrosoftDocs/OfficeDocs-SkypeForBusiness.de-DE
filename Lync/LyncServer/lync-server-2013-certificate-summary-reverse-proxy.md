---
title: 'Lync Server 2013: Zertifikatzusammenfassung für Reverseproxy'
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
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="5bffd-102">Zertifikatzusammenfassung für Reverseproxy in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bffd-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bffd-103">_**Letztes Änderungsdatum des Themas:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="5bffd-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="5bffd-104">Die Zertifikatanforderungen für den Reverse-Proxy sind viel einfacher als die für die Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="5bffd-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="5bffd-105">Das bereitgestellte Flussdiagramm stellt die erforderlichen Anforderungen dar.</span><span class="sxs-lookup"><span data-stu-id="5bffd-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="5bffd-106">In der zugehörigen Tabelle werden typische Namen für Zertifikats Subjekte und andere Alternative Namen in Bezug auf die Szenarien vorgestellt, die in den Edge-Server-Diskussionen besprochen wurden.</span><span class="sxs-lookup"><span data-stu-id="5bffd-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="5bffd-107">Weitere Informationen zu den Edge-Server-Szenarien finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5bffd-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="5bffd-108">**Flussdiagramm für Zertifikate für den Reverse-Proxy**</span><span class="sxs-lookup"><span data-stu-id="5bffd-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="5bffd-109">![Flussdiagramm für Zertifikate für Edgeserver](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Flussdiagramm für Zertifikate für Edgeserver")</span><span class="sxs-lookup"><span data-stu-id="5bffd-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="5bffd-110">Reverse Proxy: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bffd-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bffd-111">Komponente</span><span class="sxs-lookup"><span data-stu-id="5bffd-111">Component</span></span></th>
<th><span data-ttu-id="5bffd-112">Name des Antragstellers</span><span class="sxs-lookup"><span data-stu-id="5bffd-112">Subject name</span></span></th>
<th><span data-ttu-id="5bffd-113">Subject Alternative Name (San)/Order</span><span class="sxs-lookup"><span data-stu-id="5bffd-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="5bffd-114">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5bffd-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bffd-115">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="5bffd-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="5bffd-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5bffd-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="5bffd-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="5bffd-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="5bffd-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="5bffd-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="5bffd-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="5bffd-123">(Optional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="5bffd-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5bffd-124">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle und mit der Server-EKU ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5bffd-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="5bffd-125">Zu den Diensten gehören der Adressbuchdienst, die Expansion der Verteilergruppe in Office Web Apps für Konferenzen und die Veröffentlichungsregeln für lync-IP-Geräte.</span><span class="sxs-lookup"><span data-stu-id="5bffd-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="5bffd-126">Der Alternative Antragstellername umfasst:</span><span class="sxs-lookup"><span data-stu-id="5bffd-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="5bffd-127">FQDN für externe Webdienste für Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="5bffd-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="5bffd-128">FQDN des externen Webdiensts für Director oder Director-Pool</span><span class="sxs-lookup"><span data-stu-id="5bffd-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="5bffd-129">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="5bffd-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="5bffd-130">Veröffentlichungsregel für Online Besprechungen</span><span class="sxs-lookup"><span data-stu-id="5bffd-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="5bffd-131">Office Web Apps für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="5bffd-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="5bffd-132">Lyncdiscover (AutoErmittlung)</span><span class="sxs-lookup"><span data-stu-id="5bffd-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="5bffd-133">Der optionale Platzhalter ersetzt sowohl Meet als auch Dialin San</span><span class="sxs-lookup"><span data-stu-id="5bffd-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


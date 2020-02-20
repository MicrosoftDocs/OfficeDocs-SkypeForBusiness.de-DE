---
title: 'Lync Server 2013: Zertifikatzusammenfassung-Reverseproxy'
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
ms.openlocfilehash: e5691b20031d9998877a64f34f6578b654494a99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="add56-102">Zertifikatzusammenfassung-Reverseproxy in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="add56-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="add56-103">_**Letztes Änderungsstand des Themas:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="add56-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="add56-104">Die Zertifikatanforderungen für den Reverseproxy sind wesentlich einfacher als für die Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="add56-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="add56-105">Das bereitgestellte Flussdiagramm stellt die erforderlichen Anforderungen dar.</span><span class="sxs-lookup"><span data-stu-id="add56-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="add56-106">In der begleitenden Tabelle werden typische Zertifikatsantrags Teller Namen und alternative Antragstellernamen im Zusammenhang mit den Szenarien dargestellt, die wir in den Edgeserver Diskussionen überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="add56-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="add56-107">Weitere Informationen zu den Edgeserver Szenarien finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="add56-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="add56-108">**Flussdiagramm für Zertifikate für Reverse-Proxy**</span><span class="sxs-lookup"><span data-stu-id="add56-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="add56-109">![Flussdiagramm für Zertifikate für Edgeserver](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Flussdiagramm für Zertifikate für Edgeserver")</span><span class="sxs-lookup"><span data-stu-id="add56-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="add56-110">Reverse Proxy: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="add56-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="add56-111">Komponente</span><span class="sxs-lookup"><span data-stu-id="add56-111">Component</span></span></th>
<th><span data-ttu-id="add56-112">Antragstellername</span><span class="sxs-lookup"><span data-stu-id="add56-112">Subject name</span></span></th>
<th><span data-ttu-id="add56-113">Alternativer Antragstellername (San)/Order</span><span class="sxs-lookup"><span data-stu-id="add56-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="add56-114">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="add56-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="add56-115">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="add56-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="add56-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="add56-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="add56-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="add56-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="add56-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="add56-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="add56-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="add56-123">(Optional):\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="add56-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="add56-124">Das Zertifikat muss von einer öffentlichen Zertifizierungsstelle und mit der Server-EKU ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="add56-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="add56-125">Zu den Diensten gehören Adressbuchdienst, Expansion von Verteilergruppen für Office-Webanwendungen für Konferenzen und Veröffentlichungsregeln für lync-IP-Geräte.</span><span class="sxs-lookup"><span data-stu-id="add56-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="add56-126">Alternative Antragstellernamen:</span><span class="sxs-lookup"><span data-stu-id="add56-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="add56-127">Externer Webdienste FQDN für Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="add56-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="add56-128">Externer Webdienste FQDN für Director oder Directorpool</span><span class="sxs-lookup"><span data-stu-id="add56-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="add56-129">Einwahlkonferenz</span><span class="sxs-lookup"><span data-stu-id="add56-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="add56-130">Veröffentlichungsregel für Online Besprechungen</span><span class="sxs-lookup"><span data-stu-id="add56-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="add56-131">Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="add56-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="add56-132">Lyncdiscover (AutoErmittlung)</span><span class="sxs-lookup"><span data-stu-id="add56-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="add56-133">Der optionale Platzhalter ersetzt "Meet" und "Dialin San".</span><span class="sxs-lookup"><span data-stu-id="add56-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


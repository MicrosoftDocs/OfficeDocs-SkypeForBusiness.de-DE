---
title: 'Lync Server 2013: Port Zusammenfassung-AutoErmittlung'
description: 'Lync Server 2013: Port Summary – AutoErmittlung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543141"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="ba57a-103">Port Zusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba57a-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba57a-104">_**Letztes Änderungsstand des Themas:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="ba57a-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="ba57a-105">Der lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann, wenn er in DNS mit den `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` Hosteinträgen veröffentlicht wird, von Clients zum Auffinden von lync Server Features verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba57a-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="ba57a-106">Damit Mobile Geräte, die lync Mobile ausführen, die AutoErmittlung verwenden, müssen Sie möglicherweise zuerst die Liste alternativer Zertifikatsantrags Teller Namen auf einem beliebigen Director ändern und Front-End-Server den AutoErmittlungsdienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="ba57a-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="ba57a-107">Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba57a-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="ba57a-108">Die Entscheidung, ob Listen für alternative Antragstellernamen in umgekehrten Proxys verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder an Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="ba57a-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="ba57a-109">**Veröffentlicht am Port 80**     Für mobile Geräte sind keine Zertifikat Änderungen erforderlich, wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ba57a-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="ba57a-110">Dies liegt daran, dass Mobile Geräte, auf denen lync läuft, extern auf den Reverseproxy auf Port 80 zugreifen und dann an Port 8080 intern an einen Director oder Front-End-Server weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ba57a-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="ba57a-111">**Veröffentlicht am Port 443**     Die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss einen `lyncdiscover.<sipdomain>` Eintrag für jede SIP-Domäne in Ihrer Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="ba57a-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ba57a-112">Für neue Installationen oder Upgrades von lync Server 2010, in denen Sie Mobility bereitgestellt haben, haben Sie entweder Port 80 für die AutoErmittlung des mobilitätsdiensts oder erneute Zertifikate mit dem richtigen Antragstellernamen und den alternativen Antragstellernamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba57a-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="ba57a-113">Überprüfen Sie die Zertifikate auf Ihrem Director und Front-End-Server, um zu bestätigen, welchen Pfad Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ba57a-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="ba57a-114">Firewalldetails für Reverseproxyserver: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba57a-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba57a-115">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="ba57a-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba57a-116">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ba57a-116">Source IP Address</span></span></th>
<th><span data-ttu-id="ba57a-117">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ba57a-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="ba57a-118">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="ba57a-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba57a-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ba57a-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ba57a-120">Beliebig</span><span class="sxs-lookup"><span data-stu-id="ba57a-120">Any</span></span></p></td>
<td><p><span data-ttu-id="ba57a-121">Reverseproxylistener</span><span class="sxs-lookup"><span data-stu-id="ba57a-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ba57a-122">Optional Umleitung zu HTTPS, wenn der Benutzer http://publishedSiteFQDN eingibt &lt; &gt; .</span><span class="sxs-lookup"><span data-stu-id="ba57a-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="ba57a-123">Auch erforderlich, wenn Office-webapps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet werden, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="ba57a-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba57a-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba57a-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba57a-125">Beliebig</span><span class="sxs-lookup"><span data-stu-id="ba57a-125">Any</span></span></p></td>
<td><p><span data-ttu-id="ba57a-126">Reverseproxylistener</span><span class="sxs-lookup"><span data-stu-id="ba57a-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="ba57a-127">Adressbuch Downloads, Adressbuch-Webabfragedienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräteaktualisierungen, Gruppenerweiterung, Office-Webanwendungen für Konferenzen, Einwahlkonferenzen und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="ba57a-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="ba57a-128">Firewalldetails für Reverseproxyserver: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba57a-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba57a-129">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="ba57a-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba57a-130">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ba57a-130">Source IP Address</span></span></th>
<th><span data-ttu-id="ba57a-131">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ba57a-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="ba57a-132">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="ba57a-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba57a-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="ba57a-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="ba57a-134">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba57a-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ba57a-135">Front-End-Server, Front-End-Pool, Director, Directorpool, Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="ba57a-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ba57a-136">Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="ba57a-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="ba57a-137">Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="ba57a-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba57a-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ba57a-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ba57a-139">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba57a-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="ba57a-140">Front-End-Server, Front-End-Pool, Director, Directorpool, Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="ba57a-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="ba57a-141">Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="ba57a-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


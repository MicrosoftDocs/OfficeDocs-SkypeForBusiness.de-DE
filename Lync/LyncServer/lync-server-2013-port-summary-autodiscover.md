---
title: 'Lync Server 2013: Port Zusammenfassung-AutoErmittlung'
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
ms.openlocfilehash: 93750418bce8ea98d0cee385232bc09bb0bd63bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="c0326-102">Port Zusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0326-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0326-103">_**Letztes Änderungsstand des Themas:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="c0326-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="c0326-104">Der lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann, wenn `lyncdiscover.<domain>` er `lyncdiscoverinternal.<domain>` in DNS mit den und Hosteinträgen veröffentlicht wird, von Clients zum Auffinden von lync Server Features verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0326-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="c0326-105">Damit Mobile Geräte, die lync Mobile ausführen, die AutoErmittlung verwenden, müssen Sie möglicherweise zuerst die Liste alternativer Zertifikatsantrags Teller Namen auf einem beliebigen Director ändern und Front-End-Server den AutoErmittlungsdienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="c0326-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="c0326-106">Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0326-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="c0326-107">Die Entscheidung, ob Listen für alternative Antragstellernamen in umgekehrten Proxys verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder an Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="c0326-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="c0326-108">**Veröffentlicht auf Port 80**   für mobile Geräte sind keine Zertifikat Änderungen erforderlich, wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c0326-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="c0326-109">Dies liegt daran, dass Mobile Geräte, auf denen lync läuft, extern auf den Reverseproxy auf Port 80 zugreifen und dann an Port 8080 intern an einen Director oder Front-End-Server weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c0326-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="c0326-110">**Veröffentlicht am Port 443**   die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für `lyncdiscover.<sipdomain>` externe Webdienste verwendet werden, muss einen Eintrag für jede SIP-Domäne in Ihrer Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0326-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0326-111">Für neue Installationen oder Upgrades von lync Server 2010, in denen Sie Mobility bereitgestellt haben, haben Sie entweder Port 80 für die AutoErmittlung des mobilitätsdiensts oder erneute Zertifikate mit dem richtigen Antragstellernamen und den alternativen Antragstellernamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0326-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="c0326-112">Überprüfen Sie die Zertifikate auf Ihrem Director und Front-End-Server, um zu bestätigen, welchen Pfad Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c0326-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="c0326-113">Firewalldetails für Reverseproxyserver: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0326-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0326-114">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c0326-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c0326-115">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c0326-115">Source IP Address</span></span></th>
<th><span data-ttu-id="c0326-116">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c0326-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="c0326-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0326-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0326-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c0326-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c0326-119">Any</span><span class="sxs-lookup"><span data-stu-id="c0326-119">Any</span></span></p></td>
<td><p><span data-ttu-id="c0326-120">Reverseproxylistener</span><span class="sxs-lookup"><span data-stu-id="c0326-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="c0326-121">Optional Umleitung zu HTTPS, wenn der Benutzer http://&lt;publishedSiteFQDN&gt;eingibt.</span><span class="sxs-lookup"><span data-stu-id="c0326-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="c0326-122">Auch erforderlich, wenn Office-webapps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet werden, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="c0326-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0326-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c0326-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c0326-124">Any</span><span class="sxs-lookup"><span data-stu-id="c0326-124">Any</span></span></p></td>
<td><p><span data-ttu-id="c0326-125">Reverseproxylistener</span><span class="sxs-lookup"><span data-stu-id="c0326-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="c0326-126">Adressbuch Downloads, Adressbuch-Webabfragedienst, AutoErmittlung, Clientupdates, Besprechungsinhalte, Geräteaktualisierungen, Gruppenerweiterung, Office-Webanwendungen für Konferenzen, Einwahlkonferenzen und Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="c0326-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="c0326-127">Firewalldetails für Reverseproxyserver: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0326-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0326-128">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c0326-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c0326-129">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c0326-129">Source IP Address</span></span></th>
<th><span data-ttu-id="c0326-130">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c0326-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="c0326-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0326-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0326-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="c0326-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="c0326-133">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0326-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="c0326-134">Front-End-Server, Front-End-Pool, Director, Directorpool, Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="c0326-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="c0326-135">Erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte, auf denen lync ausgeführt wird, in Situationen verwendet wird, in denen die Organisation das Zertifikat für die Veröffentlichungsregel für externe Webdienste nicht ändern möchte.</span><span class="sxs-lookup"><span data-stu-id="c0326-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="c0326-136">Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="c0326-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0326-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c0326-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c0326-138">Interne Reverseproxyschnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0326-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="c0326-139">Front-End-Server, Front-End-Pool, Director, Directorpool, Office-Webanwendungen für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="c0326-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="c0326-140">Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="c0326-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


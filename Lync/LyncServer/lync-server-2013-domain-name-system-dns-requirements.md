---
title: 'Lync Server 2013: DNS-Anforderungen (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771bf78f8477008345422cc61f63202c58fcdd14
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="d09cf-102">DNS-Anforderungen (Domain Name System) für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d09cf-103">_**Letztes Änderungsdatum des Themas:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="d09cf-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="d09cf-104">Zum Bereitstellen von lync Server müssen Sie DNS-Einträge (Domain Name System) erstellen, die die Ermittlung von Clients und Servern ermöglichen, und optional die Unterstützung für die automatische Clientanmeldung, wenn Ihre Organisation Sie unterstützen möchte.</span><span class="sxs-lookup"><span data-stu-id="d09cf-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="d09cf-105">Lync Server verwendet DNS wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d09cf-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="d09cf-106">Ermitteln interner Server oder Pools für die Server-zu-Server-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="d09cf-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="d09cf-107">Damit Clients den Front-End-Pool oder den Standard Edition-Server ermitteln können, der für verschiedene SIP-Transaktionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d09cf-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="d09cf-108">Wenn Sie Unified Communications-Geräten (UC) zulassen möchten, die nicht angemeldet sind, um den Front-End-Pool oder den Standard Edition-Server mit dem Geräte Update-Webdienst zu entdecken, beziehen Sie Updates, und senden Sie Protokolle.</span><span class="sxs-lookup"><span data-stu-id="d09cf-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="d09cf-109">Damit externe Server und Clients eine Verbindung mit Edgeserver oder dem HTTP-Reverseproxy für Sofortnachrichten (im) oder Konferenzen herstellen können.</span><span class="sxs-lookup"><span data-stu-id="d09cf-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="d09cf-110">So ermöglichen Sie externen UC-Geräten das Herstellen einer Verbindung mit dem Geräte Update-Webdienst über Edgeserver oder den HTTP-Reverseproxy und Abrufen von Updates</span><span class="sxs-lookup"><span data-stu-id="d09cf-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="d09cf-111">Damit Mobile Clients automatisch Webdienste-Ressourcen ermitteln können, ohne dass die Benutzer URLs in den Geräteeinstellungen manuell eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="d09cf-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d09cf-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d09cf-112">In This Section</span></span>

  - [<span data-ttu-id="d09cf-113">Ermitteln von DNS-Anforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="d09cf-114">DNS-Anforderungen für Front-End-Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="d09cf-115">DNS-Anforderungen für Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="d09cf-116">DNS-Anforderungen für einfache URLs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="d09cf-117">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="d09cf-118">DNS-Anforderungen für Mobilität mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="d09cf-119">DNS-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d09cf-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


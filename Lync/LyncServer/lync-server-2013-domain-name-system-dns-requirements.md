---
title: 'Lync Server 2013: Domain Name System (DNS) Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="069cb-102">Domain Name System (DNS) Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="069cb-103">_**Letztes Änderungsstand des Themas:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="069cb-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="069cb-104">Um lync Server bereitzustellen, müssen Sie Domain Name System (DNS) Datensätze erstellen, die die Ermittlung von Clients und Servern ermöglichen, und optional die Unterstützung für die automatische Clientanmeldung, wenn Ihre Organisation Sie unterstützen möchte.</span><span class="sxs-lookup"><span data-stu-id="069cb-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="069cb-105">Lync Server verwendet DNS auf folgende Weise:</span><span class="sxs-lookup"><span data-stu-id="069cb-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="069cb-106">Zum Erkennen interner Server oder Pools für die Kommunikation zwischen Servern.</span><span class="sxs-lookup"><span data-stu-id="069cb-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="069cb-107">Damit Clients die Front-End-Pool oder Standard Edition-Server finden, die für verschiedene SIP-Transaktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="069cb-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="069cb-108">Wenn Sie UC-Geräte (Unified Communications) zulassen möchten, die nicht angemeldet sind, können Sie die Front-End-Pool oder Standard Edition-Server ausgeführten Geräte Update-Webdienst ermitteln, Updates abrufen und Protokolle senden.</span><span class="sxs-lookup"><span data-stu-id="069cb-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="069cb-109">Damit externe Server und Clients eine Verbindung mit Edgeserver oder dem HTTP-Reverseproxy für Instant Messaging (Sofortnachrichten) oder Konferenzen herstellen können.</span><span class="sxs-lookup"><span data-stu-id="069cb-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="069cb-110">Damit externe UC-Geräte über Edgeserver oder den HTTP-Reverseproxy eine Verbindung mit dem Geräte Update-Webdienst herstellen und Updates abrufen können.</span><span class="sxs-lookup"><span data-stu-id="069cb-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="069cb-111">Damit mobile Clients automatisch Webdienstressourcen ermitteln können, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="069cb-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="069cb-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="069cb-112">In This Section</span></span>

  - [<span data-ttu-id="069cb-113">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="069cb-114">DNS-Anforderungen für Front-End-Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="069cb-115">DNS-Anforderungen für Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="069cb-116">DNS-Anforderungen für einfache URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="069cb-117">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="069cb-118">DNS-Anforderungen für die Mobilität mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="069cb-119">DNS-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="069cb-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


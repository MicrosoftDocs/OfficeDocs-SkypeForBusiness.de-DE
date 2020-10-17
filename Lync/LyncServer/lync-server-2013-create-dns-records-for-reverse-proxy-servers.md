---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverse-Proxy Server'
description: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverse-Proxy Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef785ebbd7160274b631a2d2b6b1f1dcc866e5fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562281"
---
# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="29919-103">Erstellen von DNS-Einträgen für Reverse-Proxy Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29919-103">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29919-104">_**Letztes Änderungsstand des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="29919-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="29919-105">Erstellen Sie externe DNS-A-Einträge, die auf die öffentliche externe Schnittstelle des ISA (Microsoft Internet Security and Acceleration Server) 2006 SP1, Forefront Threat Management Gateway 2010-Servers oder des Internet Information Server-Anwendungs Anforderungs Routings, wie unter [configure DNS for Edge Support in lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md)beschrieben, verweist.</span><span class="sxs-lookup"><span data-stu-id="29919-105">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="29919-106">Sie benötigen DNS-Einträge für die FQDN des externen Webdiensts für jeden Pool, den Director (oder Directorpool) und jede einfache URL.</span><span class="sxs-lookup"><span data-stu-id="29919-106">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="29919-107">Für die minimalen DNS-Einträge für die Clientauflösung für Reverseproxy müssen die folgenden Einträge erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="29919-107">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="29919-108">Host (A)-Eintrag (e), der die veröffentlichten externen Webdienste für Directors und Director-Pools definiert (beispielsweise **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="29919-108">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="29919-109">Host (A)-Eintrag (e), der die veröffentlichten externen Webdienste für externe Webdienste definiert, die in allen Front-End-Pools und Standard Edition-Server Rollen gehostet werden (beispielsweise **Webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="29919-109">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="29919-110">Host (A)-Einträge für einfache URLs (beispielsweise **dialin.contoso.com** und **meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="29919-110">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="29919-111">Host (A)-Eintrag für den externen lync Discover-Eintrag und bietet auch einen Zeiger auf die AutoErmittlung für alle Webanwendungen, einschließlich lync Web App, Scheduler und Mobilität (beispielsweise **lyncdiscover.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="29919-111">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="29919-112">Host Einträge (A) für die Office-webapps-Server-URL (beispielsweise **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="29919-112">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="29919-113">Ausführliche Informationen finden Sie unter [DNS Summary-Reverse Proxy in lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="29919-113">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


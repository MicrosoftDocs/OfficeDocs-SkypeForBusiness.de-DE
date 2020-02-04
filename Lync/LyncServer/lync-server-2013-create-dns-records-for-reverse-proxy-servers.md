---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für Reverseproxyserver'
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
ms.openlocfilehash: 0f85b222688dcefd45030f2c05f7b59ce45ec0ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a><span data-ttu-id="60caf-102">Erstellen von DNS-Einträgen für Reverseproxyserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60caf-102">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60caf-103">_**Letztes Änderungsdatum des Themas:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="60caf-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="60caf-104">Erstellen Sie externe DNS-A-Einträge, die auf die öffentliche externe Schnittstelle Ihres Microsoft Internet Security and Acceleration (ISA)-Servers 2006 SP1, Forefront Threat Management Gateway 2010 Server oder Internet Information Server-Anwendungs Anforderungs Routing verweisen, wie unter [Konfigurieren von DNS für Edge-Unterstützung in lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60caf-104">Create external DNS A records that point to the public external interface of your Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server or Internet Information Server Application Request Routing, as described in [Configure DNS for edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md).</span></span> <span data-ttu-id="60caf-105">Sie benötigen DNS-Einträge für die FQDNs des externen Webdiensts für jeden Pool, den Director-(oder Director-Pool) und jede einfache URL.</span><span class="sxs-lookup"><span data-stu-id="60caf-105">You need DNS records for the external Web Service FQDNs for each pool, the Director (or Director pool), and each simple URL.</span></span>

<span data-ttu-id="60caf-106">Die Mindest-DNS-Einträge für die Clientauflösung des Reverse-Proxys müssen die folgenden Einträge erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="60caf-106">The minimum DNS records for client resolution to the reverse proxy, the following records must be created:</span></span>

  - <span data-ttu-id="60caf-107">Host (A)-Datensätze, die die veröffentlichten externen Webdienste für Directors-und Director-Pools definieren (beispielsweise **webdirext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="60caf-107">Host (A) record(s) that define the published external web services for Directors and Director pools (for example, **webdirext.contoso.com**)</span></span>

  - <span data-ttu-id="60caf-108">Host (A)-Datensätze, die die veröffentlichten externen Webdienste für externe Webdienste definieren, die auf allen Front-End-Pools und Standard Edition-Serverrollen gehostet werden (beispielsweise **Webext.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="60caf-108">Host (A) record(s) that define the published external web services for external web services hosted on the any Front End pools and Standard Edition server roles (for example, **webext.contoso.com**)</span></span>

  - <span data-ttu-id="60caf-109">Host (A)-Einträge für die einfachen URLs (beispielsweise **dialin.contoso.com** und **Meet.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="60caf-109">Host (A) records for the Simple URLs (for example, **dialin.contoso.com** and **meet.contoso.com**)</span></span>

  - <span data-ttu-id="60caf-110">Host (A)-Eintrag für den lync-Ermittlungs externen Eintrag und bietet auch einen Zeiger auf die AutoErmittlung für alle Web-Apps, einschließlich lync Web App, Scheduler und Mobilität (beispielsweise **lyncdiscover.contoso.com**).</span><span class="sxs-lookup"><span data-stu-id="60caf-110">Host (A) record for the Lync Discover External record, and also provides pointer to AutoDiscover for all Web apps, including the Lync Web App, scheduler and Mobility (for example, **lyncdiscover.contoso.com**)</span></span>

  - <span data-ttu-id="60caf-111">Host (A)-Einträge für die Office Web Apps-Server-URL (beispielsweise **officewebapp01.contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="60caf-111">Host (A) records for the Office Web Apps Server URL (for example **officewebapp01.contoso.com**)</span></span>

<span data-ttu-id="60caf-112">Ausführliche Informationen finden Sie unter [DNS Summary – Reverse Proxy in lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="60caf-112">For details, see [DNS summary - Reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


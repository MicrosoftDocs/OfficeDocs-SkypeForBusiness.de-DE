---
title: 'Lync Server 2013: IP-und Netzwerkprotokollunterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d413c53f8f6600170cf7ec7bfdcca8b052101eca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="bebab-102">IP-und Netzwerkprotokollunterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bebab-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bebab-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="bebab-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="bebab-104">Lync Server 2013 unterstützt die folgenden IP-und Netzwerkprotokolle:</span><span class="sxs-lookup"><span data-stu-id="bebab-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="bebab-105">**IP-Protokolle.**    Lync Server 2013 unterstützt entweder IP Version 4 (IPv4) oder IP Version 6 (IPv6) für das Server Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="bebab-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bebab-106">Lync Server 2013 können in einem Netzwerk mit aktiviertem dualen IP-Stack funktionieren.</span><span class="sxs-lookup"><span data-stu-id="bebab-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="bebab-107">**SIP-Transport Protokolle.**    Im Allgemeinen kann SIP mindestens drei Transporttypen verwenden: UDP (User Datagram Protocol), TCP (Transmission Control Protocol) und TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="bebab-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="bebab-108">In der standardmäßigen SIP-Transportkonfiguration wird TLS über TCP ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bebab-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="bebab-109">TLS wird im lync Server 2013 Netzwerk verwendet.</span><span class="sxs-lookup"><span data-stu-id="bebab-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="bebab-110">Am Rand des Netzwerks können lync Server 2013 über TCP zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bebab-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="bebab-111">Lync Server 2013 unterstützt UDP nicht für den SIP-Transport, da es nicht die Mindestanforderungen für die Sicherheit, Zuverlässigkeit und Skalierbarkeit von Unternehmenskommunikation erfüllt.</span><span class="sxs-lookup"><span data-stu-id="bebab-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="bebab-112">Ausführliche Informationen finden Sie im NextHop-Blog Artikel "zu UDP oder nicht zu UDP, das ist die Frage" unter [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span><span class="sxs-lookup"><span data-stu-id="bebab-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bebab-113">Der Inhalt jedes Blogs und die dazugehörige URL kann ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bebab-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>


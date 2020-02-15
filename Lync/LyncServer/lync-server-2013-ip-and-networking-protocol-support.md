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
ms.openlocfilehash: 8a9792ea8365dcd8941b831c43ab0406f9e33b90
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>IP-und Netzwerkprotokollunterstützung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Lync Server 2013 unterstützt die folgenden IP-und Netzwerkprotokolle:

  - **IP-Protokolle.**    Lync Server 2013 unterstützt entweder IP Version 4 (IPv4) oder IP Version 6 (IPv6) für das Server Netzwerk.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 können in einem Netzwerk mit aktiviertem dualen IP-Stack funktionieren.

    
    </div>

  - **SIP-Transport Protokolle.**    Im Allgemeinen kann SIP mindestens drei Transporttypen verwenden: UDP (User Datagram Protocol), TCP (Transmission Control Protocol) und TLS (Transport Layer Security). In der standardmäßigen SIP-Transportkonfiguration wird TLS über TCP ausgeführt. TLS wird im lync Server 2013 Netzwerk verwendet. Am Rand des Netzwerks können lync Server 2013 über TCP zusammenarbeiten. Lync Server 2013 unterstützt UDP nicht für den SIP-Transport, da es nicht die Mindestanforderungen für die Sicherheit, Zuverlässigkeit und Skalierbarkeit von Unternehmenskommunikation erfüllt. Ausführliche Informationen finden Sie im NextHop-Blog Artikel "zu UDP oder nicht zu UDP, das ist die Frage" unter [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).
    
    <div>
    

    > [!NOTE]  
    > Der Inhalt jedes Blogs und die dazugehörige URL kann ohne vorherige Ankündigung geändert werden.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>


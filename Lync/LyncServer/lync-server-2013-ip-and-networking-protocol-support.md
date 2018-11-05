---
title: 'Lync Server 2013: IP- und Netzwerkprotokollunterstützung'
TOCTitle: IP- und Netzwerkprotokollunterstützung
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412848(v=OCS.15)
ms:contentKeyID: 49295113
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IP- und Netzwerkprotokollunterstützung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 unterstützt die folgenden IP- und Netzwerkprotokolle:

  - **IP-Protokolle.**  Lync Server 2013 unterstützt entweder IPv4 (IP Version 4) oder IPv6 (IP Version 6) für das Servernetzwerk.
    

    > [!NOTE]
    > Lync Server 2013 kann in einem Netzwerk mit aktiviertem dualem&nbsp;IP-Stapel funktionieren.



  - **SIP Transport Protocols.**   Im Allgemeinen kann SIP mindestens drei Transporttypen verwenden: UDP (User Datagram Protocol), TCP (Transmission Control Protocol) und TLS (Transport Layer Security). In der standardmäßigen SIP-Transportkonfiguration wird TLS über TCP ausgeführt. TLS wird innerhalb des Lync Server 2013-Netzwerks verwendet. Am Netzwerkedge nutzt Lync Server 2013 TCP. Lync Server 2013 bietet keine Unterstützung von UDP für den SIP-Transport, da es die Mindestanforderungen für die Kommunikationssicherheit, Zuverlässigkeit und Skalierbarkeit in Unternehmen nicht erfüllt. Genauere Informationen finden Sie im NextHop-Blogartikel "To UDP, or not to UDP, that is the question," unter [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).
    

    > [!NOTE]
    > Die Inhalte der Blogs und die zugehörige URL können ohne vorherige Ankündigung geändert werden.



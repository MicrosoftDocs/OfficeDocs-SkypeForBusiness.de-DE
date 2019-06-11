---
title: 'Lync Server 2013: Richtlinien für die Integration lokaler Unified Messaging-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15973bf2055339e375e4aecc7cfd1f61ac205dbb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Im Folgenden sind Richtlinien und bewährte Methoden aufgeführt, die Sie beim Bereitstellen von Enterprise-VoIP berücksichtigen sollten:

<div>


> [!IMPORTANT]  
> Exchange Unified Messaging (um) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.



</div>

  - Bereitstellen eines lync Server 2013 Standard Edition-Servers oder eines Front-End-Pools Details zur Installation finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

  - Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.

  - Stellen Sie die Exchange-Postfachserverrollen in jeder Exchange Unified Messaging (um)-Gesamtstruktur bereit, in der Sie die Benutzer für Exchange um aktivieren möchten. Ausführliche Informationen zum Installieren von Exchange-Serverrollen finden Sie in der Dokumentation zu Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Exchange Unified Messaging (um) installiert ist, ist es für die Verwendung eines selbstsignierten Zertifikats konfiguriert.<BR>Das selbstsignierte Zertifikat ermöglicht lync Server 2013 und Exchange um jedoch nicht, sich gegenseitig zu vertrauen, weshalb es notwendig ist, ein separates Zertifikat von einer Zertifizierungsstelle anzufordern, der beide Server Vertrauen.

    
    </div>

  - Wenn lync Server 2013 und Exchange um in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013-Gesamtstruktur und der lync Server 2013-Gesamtstruktur vertrauen, um jeder Exchange-Gesamtstruktur zu vertrauen. Darüber hinaus können Sie die Exchange um-Einstellungen der Benutzer für die Benutzerobjekte in der lync Server 2013-Gesamtstruktur festlegen, indem Sie in der Regel ein Skript oder ein Gesamtstrukturübergreifendes Tool verwenden, beispielsweise Identity Lifecycle Manager (ILM).

  - Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.

  - Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.

  - Wenn Sie eine frühere Exchange-Version als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, koordinieren Sie die Namen für Exchange um SIP-URI-Wählpläne und Enterprise-VoIP-Wählpläne.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Bereitstellen redundanter Exchange UM-Server

<div>


> [!IMPORTANT]  
> Wir empfehlen, dass Sie mindestens zwei Server bereitstellen, auf denen Exchange um-Dienste für jeden Exchange um-SIP-URI-Wählplan ausgeführt wird, den Sie für Ihre Organisation konfigurieren. Zusätzlich zu einer höheren Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit. Bei einem Serverfehler kann lync Server 2013 so konfiguriert werden, dass ein Failover zu einem anderen Server ausgeführt wird.



</div>

Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.

**Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange um-Beispiel 1] (images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange um-Beispiel 1")

In Beispiel 1 sind die Exchange UM-Server 1 und 2 im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Bei einem Exchange UM-Ausfall in Tukwila sollten die DNS-A-Einträge für die Server 1 und 2 so konfiguriert sein, dass sie auf den Server 3 bzw. 4 zeigen. Bei einem Exchange UM-Ausfall in Dublin sollten die DNS-A-Einträge für die Server 3 und 4 so konfiguriert sein, dass sie auf den Server 1 bzw. 2 zeigen.

<div>


> [!NOTE]  
> In Beispiel 1 sollten Sie zudem auf jedem Exchange UM-Server eins der folgenden Zertifikate zuweisen: 
> <UL>
> <LI>
> <P>Verwenden Sie ein Zertifikat mit einem Platzhalter im alternativen Antragstellernamen.</P>
> <LI>
> <P>Tragen Sie die vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der einzelnen Exchange UM-Server als alternativen Antragstellernamen ein.</P></LI></UL>



</div>

**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange um-Beispiel 2] (images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange um-Beispiel 2")

In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.

Details zum Aktivieren oder Deaktivieren von Unified Messaging auf Exchange 2013 finden Sie unter "Integration von Exchange 2013 um mit lync Server" unter [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).

Details zum Aktivieren oder Deaktivieren von Unified Messaging auf Microsoft Exchange Server 2010 finden Sie unter:

  - "Unified Messaging auf Exchange 2010 aktivieren" unter [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).

  - "Unified Messaging auf Exchange 2010 deaktivieren" unter [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


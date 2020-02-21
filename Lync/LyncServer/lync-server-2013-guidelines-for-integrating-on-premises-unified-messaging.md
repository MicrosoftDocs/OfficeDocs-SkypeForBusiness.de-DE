---
title: 'Lync Server 2013: Richtlinien für die Integration von lokalen Unified Messaging-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d6fc97a0b8c96758344dea12a0720d5ad049ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Richtlinien für die Integration von lokalen Unified Messaging-und lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-25_

Im folgenden sind Richtlinien und bewährte Methoden für die Bereitstellung von Enterprise-VoIP zu berücksichtigen:

<div>


> [!IMPORTANT]  
> Exchange Unified Messaging (um) unterstützt IPv6 nur, wenn Sie auch UCMA 4 verwenden.



</div>

  - Bereitstelleneiner lync Server 2013 Standard Edition-Server oder eines Front-End-Pool. Ausführliche Informationen zur Installation finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

  - Besprechen Sie mit den Exchange-Administratoren, wer welche Aufgaben ausführt, um eine reibungslose und erfolgreiche Integration sicherzustellen.

  - Stellen Sie die Exchange-Postfachserverrollen in jeder Exchange Unified Messaging (um) Gesamtstruktur bereit, in der Sie Benutzer für Exchange um aktivieren möchten. Ausführliche Informationen zum Installieren von Exchange-Serverrollen finden Sie in der Microsoft Exchange Server 2013 Dokumentation.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Exchange Unified Messaging (um) installiert ist, ist es für die Verwendung eines selbstsignierten Zertifikats konfiguriert.<BR>Das selbstsignierte Zertifikat ermöglicht jedoch nicht, dass lync Server 2013 und Exchange um einander vertrauen, weshalb es erforderlich ist, ein separates Zertifikat von einer Zertifizierungsstelle anzufordern, der beide Server Vertrauen.

    
    </div>

  - Wenn lync Server 2013 und Exchange um in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013 Gesamtstruktur und der lync Server 2013 Gesamtstruktur als vertrauenswürdig eingestuft wird. Legen Sie außerdem die Exchange um Einstellungen der Benutzer für die Benutzerobjekte in der lync Server 2013 Gesamtstruktur fest, in der Regel mithilfe eines Skripts oder eines gesamtstrukturübergreifenden Tools wie Identity Lifecycle Manager (ILM).

  - Installieren Sie bei Bedarf die Exchange-Verwaltungskonsole zur Verwaltung Ihrer Unified Messaging-Server.

  - Beziehen Sie gültige Rufnummern für Outlook Voice Access und für die automatische Telefonzentrale.

  - Wenn Sie eine Version von Exchange um früher als Microsoft Exchange Server 2010 Service Pack 1 (SP1) verwenden, koordinieren Sie die Namen für Exchange um SIP-URI-Wählpläne und Enterprise-VoIP-Wähl Pläne.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Bereitstellen redundanter Exchange UM-Server

<div>


> [!IMPORTANT]  
> Es wird empfohlen, mindestens zwei Server bereitzustellen, auf denen Exchange um Dienste für alle Exchange um SIP-URI-Wähleinstellungen, die Sie für Ihre Organisation konfigurieren, durchführen. Neben der erweiterten Kapazität bietet die Bereitstellung redundanter Server eine hohe Verfügbarkeit. Bei einem Serverausfall können lync Server 2013 so konfiguriert werden, dass ein Failover auf einen anderen Server ausgeführt wird.



</div>

Die folgenden Beispielkonfigurationen bieten Ausfallsicherheit für Exchange UM.

**Beispiel 1: Exchange UM-Ausfallsicherheit**

![Exchange um Beispiel 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange um Beispiel 1")

In Beispiel 1 sind Exchange um Server 1 und 2 im Rechenzentrum von Tukwila aktiviert, und Exchange um Server 3 und 4 sind im Dublin-Rechenzentrum aktiviert. Bei einem Exchange um Ausfall in Tukwila sollte die Domain Name System (DNS) A-Einträge für Server 1 und 2 so konfiguriert werden, dass Sie auf Server 3 und 4 verweist. Bei einem Exchange um Ausfall in Dublin sollten die DNS-A-Einträge für Server 3 und 4 so konfiguriert werden, dass Sie auf Server 1 und 2 verweist.

<div>


> [!NOTE]  
> In Beispiel 1 sollten Sie zudem auf jedem Exchange UM-Server eins der folgenden Zertifikate zuweisen: 
> <UL>
> <LI>
> <P>Verwenden Sie ein Zertifikat mit einem Platzhalter im alternativen Antragstellernamen.</P>
> <LI>
> <P>Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der vier Exchange um Server im San ein.</P></LI></UL>



</div>

**Beispiel 2: Exchange UM-Ausfallsicherheit**

![Exchange um Beispiel 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange um Beispiel 2")

In Beispiel 2 sind die Exchange UM-Server 1 und 2 bei normalen Betriebsbedingungen im Rechenzentrum "Tukwila" aktiviert, die Exchange UM-Server 3 und 4 im Rechenzentrum "Dublin". Alle vier Server sind in den SIP-URI-Wähleinstellungen der Benutzer in Tukwila enthalten, die Server 3 und 4 sind deaktiviert. Wenn Exchange UM z. B. in Tukwila ausfällt, sollten die Exchange UM-Server 1 und 2 deaktiviert und die Exchange UM-Server 3 und 4 aktiviert werden, damit der Exchange UM-Datenverkehr in Tukwila an die Server in Dublin geroutet wird.

Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging für Exchange 2013 finden Sie unter "integrieren Exchange 2013 um mit lync Server" unter [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).

Ausführliche Informationen zum Aktivieren oder Deaktivieren von Unified Messaging für Microsoft Exchange Server 2010 finden Sie unter:

  - "Aktivieren von Unified Messaging bei Exchange 2010" [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418)unter.

  - "Deaktivieren von Unified Messaging auf Exchange 2010" [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416)unter.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellungsprozess für die Integration von lokalen Unified Messaging-und lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


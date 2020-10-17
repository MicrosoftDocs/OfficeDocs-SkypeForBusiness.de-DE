---
title: Lync Server 2013 technische Anforderungen für IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3484dd6ff1404d5d2a4adf77c4ab27a5a29e66b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533812"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Technische Anforderungen für IPv6 in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

Wenn Sie lync Server 2013 für IPv6 konfigurieren möchten, sollten Sie die folgenden Anforderungen berücksichtigen:

  - Um IPv6-Adressen mit lync Server zu verwenden, müssen Sie DNS-Einträge (Domain Name System) für Datensätze erstellen, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen. IPv6-DNS verwendet Host-AAAA-Einträge (Quad-A). Wenn Sie sowohl IPv4 als auch IPv6 in Ihrer Bereitstellung verwenden, empfiehlt es sich, sowohl Host A-Einträge für IPv4 als auch Host-AAAA-Einträge für IPv6 zu konfigurieren und zu verwalten. Selbst wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die weiterhin IPv4 verwenden.
    
    Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen. Wenn der Client oder Server IPv6 nicht verwendet, wird auf den Datensatz nicht verwiesen. Übergangstechnologien entscheiden über den zu verwendenden Datensatz basierend auf der Konfiguration und den Richtlinien für die Übergangstechnologie.

  - Jede IPv6-Adresse verfügt über einen Bereich. Die drei Bereiche, die Sie für die IPv6-Adressierung verwenden können, sind globale IPv6-Adressen (vergleichbar mit öffentlichen IPv4-Adressen), eindeutige lokale IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und lokale IPv6-Linkadressen (ähnlich wie bei automatischen privaten IP-Adressen in Windows Server für IPv4). Alle Server in einem Pool sollten über IPv6-Adressen mit demselben Bereich verfügen.

<div>


> [!IMPORTANT]  
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internet Anbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server-Ebene und auf der lync Server 2013 Ebene zuweisen, erwartungsgemäß funktionieren. Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie unter den Links am Ende dieses Themas.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[IP-Adressierungs Architektur der Version 6](https://tools.ietf.org/html/rfc4291)  
[Globales Unicast-Adress Format in IPv6](https://tools.ietf.org/html/rfc3587)  
[Eindeutige lokale IPv6-Unicast-Adressen](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


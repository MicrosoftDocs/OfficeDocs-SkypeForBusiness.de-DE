---
title: Lync Server 2013 Anforderungen für den Lastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54e1e8e130374e296d18680cf5d82001e55b68af
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lastenausgleichsanforderungen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Wenn Sie über Front-End-Pools, Director-Pools oder Edgeserver Pools verfügen, müssen Sie den Lastenausgleich für diese Pools bereitstellen. Beim Lastenausgleich wird der Datenverkehr auf die Server in einem Pool verteilt.

Lync Server 2013 unterstützt zwei Arten von Lastenausgleichslösungen für den Client-zu-Server-Datenverkehr: Domain Name System (DNS) Lastenausgleich und Hardwarelastenausgleich. Der DNS-Lastenausgleich bietet mehrere Vorteile, einschließlich einer einfacheren Verwaltung, einer effizienteren Problembehandlung und der Möglichkeit, einen Großteil des lync Server Datenverkehrs von möglichen Problemen mit dem Hardwarelastenausgleich zu isolieren.

Entscheiden Sie, welche Lösung für den Lastenausgleich für die einzelnen Pools in der Bereitstellung jeweils geeignet ist, und beachten Sie dabei die folgenden Einschränkungen:

  - Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.

  - Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.

Weitere Informationen zum Auswählen einer Lösung für das Hardwaregerät zum Lastenausgleich finden Sie unter [Hardware Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Beispielsweise ist das Konfigurieren des Hardwarelastenausgleichs einfacher, da nur der HTTP-und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle durch den DNS-Lastenausgleich verwaltet werden. Ausführliche Informationen finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md).

Für den Server-zu-Server-Datenverkehr verwendet lync Server 2013 einen Topologie-fähigen Lastenausgleich. Die Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs der Server in der Topologie zu erhalten und den Datenverkehr automatisch an die Server zu verteilen. Administratoren müssen diese Art von Lastenausgleich nicht einrichten oder verwalten.

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr auf einem bestimmten Computer blockieren müssen, reicht es nicht aus, die IP-Adresseinträge aus dem Pool-FQDN einfach zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.

</div>

<span> </span>

</div>

</div>

</div>


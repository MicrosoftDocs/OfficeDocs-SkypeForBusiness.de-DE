---
title: Anforderungen des lync Server 2013-Lastenausgleichs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Anforderungen an den Lastenausgleich für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Wenn Sie über Front-End-Pools, Director-Pools oder Edge-Server-Pools verfügen, müssen Sie den Lastenausgleich für diese Pools bereitstellen. Beim Lastenausgleich wird der Datenverkehr auf die Server in einem Pool verteilt.

Lync Server 2013 unterstützt zwei Arten von Lastenausgleichslösungen für Client-zu-Server-Datenverkehr: Domain Name System (DNS)-Lastenausgleich und Hardwarelastenausgleich. Der DNS-Lastenausgleich bietet mehrere Vorteile, darunter einfachere Verwaltung, effizientere Problembehandlung und die Möglichkeit, einen Großteil ihres lync Server-Datenverkehrs von möglichen Problemen mit dem Hardwarelastenausgleich zu isolieren.

Entscheiden Sie, welche Lösung für den Lastenausgleich für die einzelnen Pools in der Bereitstellung jeweils geeignet ist, und beachten Sie dabei die folgenden Einschränkungen:

  - Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.

  - Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.

Weitere Informationen zum Auswählen einer Lösung für den Hardware Lastenausgleich finden Sie unter [Hardwareanforderungen für den Lastenausgleich für lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Ein Beispiel hierfür ist, dass ausschließlich der HTTP- und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle vom DNS-Lastenausgleich verwaltet werden. Ausführliche Informationen finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md).

Für den Server-zu-Server-Datenverkehr verwendet lync Server 2013 den Topologie-bezogenen Lastenausgleich. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen und den Datenverkehr automatisch auf die Server zu verteilen. Administratoren müssen diese Art des Lastenausgleichs weder konfigurieren noch verwalten.

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Überlegungen zu Migration und Koexistenz für IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf7e062a7a96f6f7aca642298471b0a8cf8adaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Überlegungen zu Migration und Koexistenz für IPv6 in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-14_

IP Version 6 (IPv6) wird auf lync Server 2010 oder Office Communications Server nicht unterstützt. Für Pilot Zwecke können Sie lync Server 2010 und lync Server 2013 Dual-Stack-Koexistenz testen. Es wird empfohlen, alle Pools für einen bestimmten zentralen Standort auf lync Server 2013 zu aktualisieren, bevor Sie IPv6 (Dual-Stack-Netzwerk) für einen der Pools aktivieren. Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Pool nur mit IPv6 in Ihrer Testumgebung zum Testen einrichten.

Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:

  - Lync Server 2013-, lync Server 2010-und Office Communications Server 2007 R2 Pools im IPv4-Modus, die mit lync Server 2013 im Dual-Stack-Modus nebeneinander stehen.

  - Lync Server 2013 Pool im reinen IPv6-Modus, wenn der nur-IPv6-Pool isoliert ist.

</div>

<span> </span>

</div>

</div>

</div>


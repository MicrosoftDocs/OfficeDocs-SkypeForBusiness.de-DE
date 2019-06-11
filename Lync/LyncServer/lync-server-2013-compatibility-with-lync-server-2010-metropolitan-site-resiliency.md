---
title: Lync Server 2013-Kompatibilität mit der Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3079f05d9860fd659d19df7b71ee633c0cea3fe2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Ausfallsicherheit für innerstädtische Standorte in Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-19_

Die für lync Server 2010 unterstützte Lösung für die Stabilität der Metropolitan-Website wird für lync Server 2013 nicht unterstützt. Diese Lösung umfasst einen einzigen Front-End-Pool über zwei Rechenzentren im gleichen Ballungsraum.

Die Resilienz-Lösung für Metropolitan Site wurde entwickelt, um den Verlust eines vollständigen Rechenzentrums zu beheben. Wenn Sie Ihren Pool über zwei Rechenzentren spannen, stellen Sie normalerweise die Hälfte Ihrer Front-Ends in einem Rechenzentrum und die andere Hälfte in das zweite Rechenzentrum. Wenn Sie ein gesamtes Rechenzentrum verlieren, haben Sie die Hälfte der Front-End-Server verloren. Dies kann zu Problemen mit dem neuen verteilten Systemmodell für Front-End-Pools in lync Server 2013 führen. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>


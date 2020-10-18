---
title: Lync Server 2013 Kompatibilität mit lync Server 2010 Ausfallsicherheit von großstädtischen Standorten
description: Lync Server 2013 Kompatibilität mit lync Server 2010 Ausfallsicherheit von großstädtischen Standorten.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec72f261ac593b24bad13dcd400f495ba7ba0722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576931"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Ausfallsicherheit für lync Server 2010 Metropole-Standort

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-19_

Die für lync Server 2010 unterstützte Lösung für die Ausfallsicherheit von Metropolitan Site wird für lync Server 2013 nicht unterstützt. Diese Lösung beinhaltete einen einzelnen Front-End-Pool, der zwei Rechenzentren im selben innerstädtischen Gebiet umfasst.

Die ausfallsicherheitslösung für den Standort Metropolitan Site wurde entwickelt, um den Verlust eines vollständigen Datencenters wiederherzustellen. Wenn Sie Ihren Pool über zwei Rechenzentren hinweg überspannen, setzen Sie normalerweise die Hälfte Ihrer Front-Ends in ein Datencenter und die andere Hälfte in das zweite Datencenter. Wenn Sie ein gesamtes Rechenzentrum verlieren, haben Sie die Hälfte Ihrer Front-End-Server verloren. Dies kann Probleme mit dem neuen Modell für verteilte Systeme für Front-End-Pools in lync Server 2013 verursachen. Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>


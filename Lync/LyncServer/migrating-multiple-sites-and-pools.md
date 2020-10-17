---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95f38ab0adc1457abee7cdd90e8f385f7176ce3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527362"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Lync Server 2013 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Vorgang der Migration mehrerer Pools von lync Server 2010 zu lync Server 2013 erfordert folgende Überlegungen:

1.  Nachdem Sie einen lync Server 2013 Pilot-Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode für die Überprüfung der Funktionalität der Benutzer. Nachdem Sie beispielsweise einen Benutzer in den Pilot Pool verschoben haben, überprüfen Sie, ob die konferenzrichtlinie des Benutzers in lync Server 2013 verschoben wurde.

2.  Nachdem Sie eine Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.

3.  Nachdem Sie die Verbund Routen von lync Server 2010-Edgeserver zu den Pilot lync Server 2013-Edgeserver gewechselt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.

4.  Nachdem Sie alle Benutzer und nicht-Benutzer Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der lync Server 2010 Pool leer ist.

5.  Nachdem Sie überprüft haben, dass der lync Server 2010 Pool leer ist, können Sie den Pool deaktivieren.
    
    Ausführliche Informationen zum Deaktivieren des Legacy lync Server 2010 Pools und der Server finden Sie unter [Phase 8: decommission Legacy Pools](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>


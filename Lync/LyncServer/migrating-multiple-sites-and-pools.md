---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Lync Server 2013 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools. Der Vorgang zum Migrieren mehrerer Pools von lync Server 2010 zu lync Server 2013 erfordert die folgenden Überlegungen:

1.  Nach der Bereitstellungeines lync Server 2013-pilotpools müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode zum Überprüfen der Funktionalität der Benutzer. Wenn Sie beispielsweise einen Benutzer in den Pilot Pool verschieben, überprüfen Sie, ob die konferenzrichtlinie des Benutzers nach lync Server 2013 verschoben wurde.

2.  Nachdem Sie einen Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.

3.  Nachdem Sie die Verbund Routen von lync Server 2010-Edgeserver auf die Pilot-Edgeserver von lync Server 2013 umgestellt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.

4.  Nachdem Sie alle Benutzer und nicht-Benutzer-Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der lync Server 2010-Pool leer ist.

5.  Nachdem Sie überprüft haben, dass der lync Server 2010-Pool leer ist, können Sie den Pool deaktivieren.
    
    Details zum Deaktivieren des Legacy-lync Server 2010-Pools und-Servers finden Sie unter [Phase 8: Legacy-Pools der decommission-Version](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>


---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-26_

Lync Server 2013 unterstützt die Bereitstellung mehrerer Standorte und mehrerer Pools. Der Vorgang zum Migrieren mehrerer Pools von Office Communications Server 2007 R2 zu lync Server 2013 erfordert die folgenden Überlegungen:

1.  Nach der Bereitstellungeines lync Server 2013-pilotpools müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode zum Überprüfen der Funktionalität der Benutzer.

2.  Nachdem Sie einen Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.

3.  Nachdem Sie die Verbund Routen von Office Communications Server 2007 R2-Edgeserver auf die Pilot-Edgeserver von lync Server 2013 umgestellt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.

4.  Nachdem Sie alle Benutzer und nicht-Benutzer-Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Office Communications Server 2007 R2-Pool leer ist.

5.  Nachdem Sie überprüft haben, dass der 2007 R2-Pool von Office Communications Server leer ist, können Sie den Pool deaktivieren.
    
    Details zum Deaktivieren des Legacy-Pools und der Server für Office Communications Server 2007 R2 finden Sie unter [Phase 10: Legacy Website](phase-10-decommission-legacy-site.md)der decommission.

</div>

<span> </span>

</div>

</div>

</div>


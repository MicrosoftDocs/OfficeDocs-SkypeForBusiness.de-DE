---
title: Migrieren von mehreren Standorten und Pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6efbad7107109096a5f17d82912353e6f8a1a14a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrieren von mehreren Standorten und Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-26_

Lync Server 2013 unterstützt Bereitstellungen mit mehreren Standorten und mehreren Pools. Der Vorgang der Migration mehrerer Pools von Office Communications Server 2007 R2 zu lync Server 2013 erfordert folgende Überlegungen:

1.  Nachdem Sie einen lync Server 2013 Pilot-Pool bereitgestellt haben, müssen Sie eine Teilmenge der Pilotbenutzer definieren, die in den lync Server 2013-Pool verschoben werden, und eine Methode für die Überprüfung der Funktionalität der Benutzer.

2.  Nachdem Sie eine Edgeserver im Pilot Pool bereitgestellt haben, müssen Sie überprüfen, ob externe Benutzer mit dem lync Server 2013-Pool kommunizieren können.

3.  Nachdem Sie die Verbund Routen von Office Communications Server 2007 R2-Edgeserver zu den Pilot lync Server 2013-Edgeserver gewechselt haben, müssen Sie überprüfen, ob Verbundbenutzer mit dem lync Server 2013-Pool kommunizieren können.

4.  Nachdem Sie alle Benutzer und nicht-Benutzer Kontaktobjekte verschoben haben, müssen Sie überprüfen, ob der Office Communications Server 2007 R2 Pool leer ist.

5.  Nachdem Sie überprüft haben, dass der Office Communications Server 2007 R2 Pool leer ist, können Sie den Pool deaktivieren.
    
    Ausführliche Informationen zum Deaktivieren des Legacy Office Communications Server 2007 R2 Pools und der Server finden Sie unter [Phase 10: decommission Legacy Site](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>


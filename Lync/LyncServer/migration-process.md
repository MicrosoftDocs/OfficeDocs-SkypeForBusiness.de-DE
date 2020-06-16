---
title: Migrationsprozess
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a31a127ef3a37ed366117247dd68c192d19e691
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Migrationsprozess

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist die parallele Migration. In diesem Thema wird beschrieben, warum Sie die parallele Migration verwenden sollten und auch Informationen zum Testen der Koexistenz enthält.

<div>

## <a name="side-by-side-migration"></a>Parallele Migration

Am besten wenden Sie für jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 neben einem entsprechenden Server bereit, auf dem lync Server 2010 ausgeführt wird, und übertragen anschließend Vorgänge auf den neuen Server. Wenn ein Rollback auf lync Server 2010 erforderlich ist, müssen Sie nur die Vorgänge zurück auf die ursprünglichen Server verschieben. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.

</div>

<div>

## <a name="coexistence-testing"></a>Koexistenztest

Nachdem Sie lync Server 2013 parallel mit lync Server 2010 bereitgestellt haben, stellt die Bereitstellung einen Testzustand der Koexistenz von lync Server 2013 und lync Server 2010 dar. In diesem Status ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden können, jeder Standort verwalten werden kann und die Clients mit Benutzern der aktuellen und der Vorgängerversion kommunizieren können. Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert. In der Regel besteht die Testphase der Koexistenz während der Pilottests von lync Server 2013. Ältere Benutzer werden für einen bestimmten Zeitraum in lync Server 2013 verschoben, um sicherzustellen, dass Anwendungskompatibilität und Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von lync Server 2010 werden zurückgezogen.

</div>

</div>

<span> </span>

</div>

</div>

</div>


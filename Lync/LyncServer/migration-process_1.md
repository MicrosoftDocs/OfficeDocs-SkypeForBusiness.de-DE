---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc0620b2de14c56a6886a70cd7b977046828786
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Migrationsvorgang

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-24_

Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist die parallele Migrationsprozedur. In diesem Thema wird beschrieben, weshalb Sie die parallele Migration verwenden sollten, und es enthält zudem Informationen über die Koexistenz.

<div>

## <a name="side-by-side-migration"></a>Parallele Migration

Am besten wenden Sie für nahezu jede Migration das Verfahren der parallelen Migration an. Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 neben einem entsprechenden Server bereit, auf dem Office Communications Server 2007 R2 ausgeführt wird, und Sie können dann Vorgänge auf den neuen Server übertragen. Wenn ein Rollback auf Office Communications Server 2007 R2 erforderlich ist, müssen Sie nur die Vorgänge zurück auf die ursprünglichen Server verschieben. Bedenken Sie, dass in diesem Fall neue Besprechungen, die mit aktualisierten Clients geplant wurden, nicht funktionieren und dass auch für die Clients ein Downgrade erforderlich wäre.

</div>

<div>

## <a name="coexistence-testing"></a>Koexistenztest

Nachdem Sie lync Server 2013 parallel mit Office Communications Server 2007 R2 bereitgestellt haben, stellt die Topologie einen Testzustand der Koexistenz von lync Server 2013 und Office Communications Server 2007 R2 dar. In diesem Zustand ist es wichtig zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können. Vor dem Migrieren aller Benutzer sollten Sie unbedingt den Status jeder Bereitstellung festgestellt und sich vergewissert haben, dass jede Bereitstellung ordnungsgemäß funktioniert. In der Regel besteht die Testphase der Koexistenz während der Pilottests von lync Server 2013. Ältere Benutzer werden für einen bestimmten Zeitraum in lync Server 2013 verschoben, um sicherzustellen, dass Anwendungskompatibilität und Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von Office Communications Server 2007 R2 werden zurückgezogen.

</div>

</div>

<span> </span>

</div>

</div>

</div>


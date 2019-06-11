---
title: Migrationsvorgang
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Migrationsvorgang

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Das empfohlene und unterstützte Migrationsverfahren für lync Server 2013 ist das parallele Migrationsverfahren. In diesem Thema wird beschrieben, warum Sie eine parallele Migration verwenden sollten, und Sie enthält auch Informationen zur Koexistenz.

<div>

## <a name="side-by-side-migration"></a>Parallele Migration

In fast jeder Migration sollten Sie den parallelen Migrationspfad verwenden. Bei einer parallelen Migration stellen Sie einen neuen Server mit lync Server 2013 zusammen mit einem entsprechenden Server bereit, auf dem Office Communications Server 2007 R2 ausgeführt wird, und Sie können dann Vorgänge auf den neuen Server übertragen. Wenn ein Rollback zu Office Communications Server 2007 R2 erforderlich ist, müssen Sie die Vorgänge nur zurück zu den ursprünglichen Servern verschieben. Beachten Sie, dass in dieser Situation alle neuen Besprechungen, die mit aktualisierten Clients geplant sind, nicht funktionieren, und die Clients müssten ebenfalls heruntergestuft werden.

</div>

<div>

## <a name="coexistence-testing"></a>Koexistenz testen

Nachdem Sie lync Server 2013 parallel zu Office Communications Server 2007 R2 bereitgestellt haben, stellt die Topologie einen Teststatus für die Koexistenz von lync Server 2013 und Office Communications Server 2007 R2 dar. In diesem Zustand ist es wichtig, zu testen und sicherzustellen, dass Dienste gestartet werden, jeder Standort verwaltet werden kann und Clients mit aktuellen und älteren Benutzern kommunizieren können. Vor der Migration aller Benutzer ist es sehr wichtig, dass Sie den Zustand jeder Bereitstellung verstehen und sicherstellen, dass jede Bereitstellung funktionsfähig ist und ordnungsgemäß funktioniert. In der Regel ist die Koexistenz Testphase während des Pilottests von lync Server 2013 vorhanden. Ältere Benutzer werden für einen bestimmten Zeitraum nach lync Server 2013 verschoben, um sicherzustellen, dass die Anwendungskompatibilität und die Features und Funktionen ordnungsgemäß funktionieren. Nach Pilottests werden Benutzer und Anwendungen in die Produktionsversion von lync Server 2013 verschoben, und die Legacy Pools und-Anwendungen von Office Communications Server 2007 R2 werden eingestellt.

</div>

</div>

<span> </span>

</div>

</div>

</div>


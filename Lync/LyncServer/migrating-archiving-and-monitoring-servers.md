---
title: Migrieren von Archivierungsservern und Monitoring Servern
description: Migrieren von Archivierungs-und Monitoring Servern.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabd16fd38dbf463a4bc608fe77368e781571fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565381"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungsservern und Monitoring Servern

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Wenn Sie Archivierungsserver und Monitoring Server in ihrer lync Server 2010 Umgebung bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013 Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration die Archivierung und Überwachung zu Ihrem lync Server 2013 Pilot-Pool hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.

Wenn Sie während des Migrationsvorgangs Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:

  - Das Archivieren von Daten und Überwachungsdaten wird nicht in die lync Server 2013-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebsetzung der Vorversionsumgebung sichern, sind Bestandteil der aufgezeichneten Aktivitäten der Lync Server 2010-Umgebung.

  - Die lync Server 2010 Version von Archivierungsserver und Monitoring Server kann nur einem lync Server 2010 Front-End-Pool zugeordnet werden. In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in die lync Server 2013 Front-End-Pool integriert sind.

  - Während der Koexistenz Ihrer Legacy-und lync Server 2013-Bereitstellungen werden die lync Server 2010-Version von Archivierungsserver und Monitoring Server Daten für Benutzer sammeln, die in lync Server 2010 Pools verwaltet werden. Archivierung und Überwachung in lync Server 2013 Sammeln von Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.
    
    <div>
    

    > [!NOTE]  
    > Während der Migrationsphase, in der Sie weiterhin den Legacy-Edgeserver mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die lync Server 2010-Version von Archivierungsserver weiterhin Daten für Benutzer, die in lync Server 2010 Pools verwaltet werden, und archiviert in lync Server 2013 sammelt Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.

    
    </div>

  - Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit der Archivierung und Überwachung in lync Server 2013 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung mit lync Server 2013 integrieren müssen.

</div>

<span> </span>

</div>

</div>

</div>


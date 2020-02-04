---
title: Migrieren von Archivierungsservern und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungsservern und Monitoring Servern

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Wenn Sie den Archivierungsserver und den Monitoring Server in ihrer lync Server 2010-Umgebung bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch dem lync Server 2013-Pilot Pool Archivierungs-und Überwachungsvorgänge hinzufügen, bevor Sie migrieren, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.

Wenn Sie während des Migrationsprozesses Archivierungs-und Überwachungsfunktionen wünschen, sollten Sie die folgenden Aspekte berücksichtigen:

  - Archivierungsdaten und Überwachungsdaten werden nicht in die lync Server 2013-Bereitstellung verschoben. Die Daten, die Sie vor dem Stilllegen der Legacyumgebung sichern, sind Ihr Aktivitätsverlauf in der lync Server 2010-Umgebung.

  - Die lync Server 2010-Version des Archivierungsservers und des Überwachungsservers kann nur einem lync Server 2010-Front-End-Pool zugeordnet werden. In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in den Front-End-Pool von lync Server 2013 integriert sind.

  - In der Zeit, in der Ihre Legacy-und lync Server 2013-Bereitstellungen koexistieren, sammeln die lync Server 2010-Version des Archivierungsservers und des Überwachungsservers Daten für Benutzer, die in lync Server 2010-Pools verwaltet werden. Archivierung und Überwachung in lync Server 2013 sammeln Daten für Benutzer, die in lync Server 2013-Pools verwaltet werden.
    
    <div>
    

    > [!NOTE]  
    > Während der Migrationsphase, wenn Sie Ihren Legacy-Edgeserver weiterhin mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die lync Server 2010-Version des Archivierungsservers weiterhin Daten für Benutzer, die in lync Server 2010-Pools und-Archivierung in lync Server 2013 verwaltet werden. sammelt Daten für Benutzer, die in lync Server 2013-Pools verwaltet werden.

    
    </div>

  - Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit der Archivierung und Überwachung in lync Server 2013 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Lösung eines Drittanbieters in lync Server 2013 integrieren müssen.

</div>

<span> </span>

</div>

</div>

</div>


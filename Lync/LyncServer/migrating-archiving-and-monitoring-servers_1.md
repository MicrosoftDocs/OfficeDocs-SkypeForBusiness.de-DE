---
title: Migrieren von Archivierungsservern und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847110"
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

Wenn Sie den Archivierungsserver und den Monitoring Server in Ihrem Office Communications Server 2007 R2 bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration dem Pilot Pool Archivierungs-und Überwachungsdienste hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.

Wenn Sie die Archivierungs-und Überwachungsfunktionen während der Migration und Koexistenzphase nutzen möchten, sollten Sie die folgenden Aspekte berücksichtigen:

  - Archivierungsdaten und Überwachungsdaten werden nicht in die lync Server 2013-Bereitstellung verschoben. Die Daten, die Sie vor dem Stilllegen der Legacyumgebung sichern, sind Ihr Aktivitätsverlauf in Office Communications Server 2007 R2.

  - Die Office Communications Server 2007 R2-Version des Archivierungsservers und des Überwachungsservers können nur mit einem Office Communications Server 2007 R2-Front-End-Pool verknüpft werden. In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in den Front-End-Pool von lync Server 2013 integriert sind.

  - In der Zeit, in der Ihre Legacy-und lync Server 2013-Bereitstellungen koexistieren, sammeln die Office Communications Server 2007 R2-Version des Archivierungsservers und des Überwachungsservers Daten für Benutzer, die in Office Communications Server 2007 R2-Pools verwaltet werden. Die lync Server 2013-Version des Archivierungsservers und des Überwachungsservers sammeln Daten für Benutzer, die in lync Server 2013-Pools verwaltet werden.
    
    <div>
    

    > [!NOTE]  
    > Während der Migrationsphase, wenn Sie Ihren Legacy-Edgeserver weiterhin mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die Office Communications Server 2007 R2-Version des Archivierungsservers weiterhin Daten für Benutzer, die sich auf Office Communications Server 2007 befinden. R2-Pools und die lync Server 2013-Version des Archivierungsservers sammelt Daten für Benutzer, die in lync Server 2013-Pools verwaltet werden.

    
    </div>

  - Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit dem Archivierungsserver und dem Überwachungsserver verwenden, wenden Sie sich an Ihren Anbieter, wenn Sie wissen möchten, wann und wie Sie die Lösung eines Drittanbieters in lync Server 2013 integrieren müssen.

</div>

<span> </span>

</div>

</div>

</div>


---
title: Migrieren von Archivierungs-und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67896576fce21eea630533a5826bbcbc53392fa0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrieren von Archivierungs-und Monitoring Servern

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Wenn Sie Archivierungsserver und Monitoring Server in Ihrem Office Communications Server 2007 R2 bereitgestellt haben, können Sie diese Server in ihrer lync Server 2013 Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs- und Überwachungsfunktionen in Ihrer Organisation jedoch entscheidend sind, sollten Sie Ihrem Pilotpool vor der Migration Archivierungsserver und Monitoring Server hinzufügen, damit diese Funktionen auch während des Migrationsvorgangs zur Verfügung stehen.

Wenn Sie während der Phase der Migration und Koexistenz Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:

  - Das Archivieren von Daten und Überwachungsdaten wird nicht in die lync Server 2013-Bereitstellung verschoben. Die Daten, die Sie vor der Außerbetriebnahme der Vorgänger Umgebung sichern, sind Ihre Aktivitätshistorie im Office Communications Server 2007 R2.

  - Die Office Communications Server 2007 R2 Version von Archivierungsserver und Monitoring Server kann nur einem Office Communications Server 2007 R2 Front-End-Pool zugeordnet werden. In lync Server 2013 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in die lync Server 2013 Front-End-Pool integriert sind.

  - Während der Koexistenz Ihrer Legacy-und lync Server 2013-Bereitstellungen werden die Office Communications Server 2007 R2-Version von Archivierungsserver und Monitoring Server Daten für Benutzer sammeln, die in Office Communications Server 2007 R2 Pools verwaltet werden. Die lync Server 2013 Version von Archivierungsserver und Monitoring Server sammeln von Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.
    
    <div>
    

    > [!NOTE]  
    > Während der Migrationsphase, in der Sie weiterhin den Legacy-Edgeserver mit dem neuen lync Server 2013-Pilot Pool verwenden, sammelt die Office Communications Server 2007 R2-Version von Archivierungsserver weiterhin Daten für Benutzer, die in Office Communications Server 2007 verwaltet werden. R2-Pools und die lync Server 2013 Version von Archivierungsserver sammelt Daten für Benutzer, die in lync Server 2013 Pools verwaltet werden.

    
    </div>

  - Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit Archivierungsserver und Monitoring Server verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung mit lync Server 2013 integrieren müssen.

</div>

<span> </span>

</div>

</div>

</div>


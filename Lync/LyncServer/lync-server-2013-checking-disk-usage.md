---
title: 'Lync Server 2013: Überprüfen der Datenträgerverwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8532b15ac45033d966c772e6ab23403d709ed790
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Überprüfen der Datenträgerverwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-30_

Festplatten sind ein wichtiger Bestandteil der lync Server 2013-Bereitstellung. Ohne ausreichend freies Festplattenvolume kann weder das Betriebssystem noch die lync Server 2013 Datenbanken ordnungsgemäß funktionieren. Sie müssen die Statistiken für lync Server 2013 Back-End-Datenbanken täglich überwachen, um sicherzustellen, dass auf den Servern nicht genügend Speicherplatz zur Verfügung steht und dass Sie nach Bedarf Speicherressourcen hinzufügen können.

Neben der Überprüfung des Speicherplatzes auf Datenträgern, die das Betriebssystem, die Programmdateien, die Datenbank und die Transaktionsprotokolle (lync Server 2013 Back-End) hosten, sollten Sie auch die Verwendung des Dateisystems überwachen, das Speicherplatz für Dateifreigaben enthält, die die folgenden wichtigen Daten

  - Besprechungsinhalte

  - Metadaten für Besprechungsinhalte

  - Erfüllen von Kompatibilitäts Protokollen

  - Anwendungsdatendatei (intern von der Anwendungsserverkomponente verwendet)

  - Group Chat Server-Webdienst und Compliance-Ordner (zum Speichern von Dateien, die in den Gruppenchat-Webdienst hochgeladen wurden)

  - XML-Dateien für Gruppenchat-Konformität (mit Gruppenchat-Kompatibilitäts Einträgen)

  - Aktualisieren von Dateien (für den Geräteaktualisierungsdienst)

  - Adressbuchdateien

Lync Server 2013 benötigt auf der Festplatte Speicherplatz zum Speichern der Datenbanken und Transaktionsprotokolle sowie der zuvor aufgeführten Dateien auf Dateifreigaben.

Sie sollten den Speicherplatz regelmäßig überwachen, um sicherzustellen, dass die lync Server 2013-Bereitstellung aufgrund unzureichender Speicherressourcen nicht beeinträchtigt wird.

Vergleichen und verwalten Sie statistische Informationen über den verfügbaren Speicherplatz auf jedem lync Server 2013 Volume und das erwartete Wachstum der Datenbanken und Transaktionsprotokolldateien. Dies hilft bei der Kapazitätsplanung und beim Hinzufügen von Speicher, wenn die Speicherressourcen benötigt werden.

Zur Unterstützung der Problembehandlung und Notfall Wiederherstellungssituationen wird empfohlen, dass verfügbarer freier Speicherplatz mindestens 110% der Größe der Datenbank entspricht oder größer ist.

Sie können den freien Speicherplatz auf der Festplatte mithilfe der folgenden Methoden überprüfen:

1.  **System Center Operations Manager**   System Center Operations Manager kann verwendet werden, um Administratoren zu warnen, wenn der Speicherplatz auf dem Volume eingeschränkt ist.

2.  ****   Durch Ausführen eines Skripts wird der Speicherplatz durch Ausführen eines Skripts überwacht, das Ihnen eine Nachricht sendet, wenn der verfügbare Festplattenspeicherplatz unter 20 Prozent liegt. Ein Beispielskript im Microsoft Script Center auf TechNet finden Sie unter:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows-Explorer**   verwenden Sie Windows-Explorer, um auf Datenträgern auf Volumes zu suchen, in denen lync Server 2013 Protokolle und Datenbanken gespeichert sind.

</div>

<span> </span>

</div>

</div>

</div>


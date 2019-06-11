---
title: 'Lync Server 2013: Überprüfen der Datenträgerverwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791f4a0f9db56c38c837fa77b443d5aa6de74bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Überprüfen der Datenträgerverwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-30_

Festplatten-Laufwerke sind eine wichtige Komponente der lync Server 2013-Bereitstellung. Ohne ausreichend freien Festplattenspeicher können weder das Betriebssystem noch die lync Server 2013-Datenbanken ordnungsgemäß funktionieren. Sie müssen die lync Server 2013-Datenbankstatistik für die Back-End-Datenbank täglich überwachen, um sicherzustellen, dass auf den Servern nicht genügend Speicherplatz vorhanden ist, und um sich vorzubereiten, wie erforderlich Speicherressourcen hinzuzufügen.

Neben der Überprüfung des Speicherplatzes auf Festplatten, die das Betriebssystem, die Programmdateien, die Datenbank und die Transaktionsprotokolle (lync Server 2013-Back-End) hosten, sollten Sie auch die Verwendung des Dateisystems überwachen, das Speicherplatz für Dateifreigaben enthält, die die folgenden wichtigen Daten enthalten: Daten

  - Besprechungsinhalte

  - Metadaten für Besprechungsinhalte

  - Kompatibilitäts Protokolle für Besprechungen

  - Anwendungsdaten Dateien (intern von der Anwendungsserverkomponente verwendet)

  - Web Service-und Compliance-Ordner für Gruppen-Chat Server (zum Speichern von Dateien, die in den Gruppen-Chat-Webdienst hochgeladen wurden)

  - XML-Dateien für Gruppen-Chat-Compliance (mit Gruppen-Chat-Konformitäts Einträgen)

  - Aktualisieren von Dateien (für den Geräteaktualisierungsdienst)

  - Adressbuchdateien

Lync Server 2013 benötigt Festplattenspeicher, um die Datenbanken und Transaktionsprotokolle zusätzlich zu den zuvor aufgelisteten Dateien auf Dateifreigaben zu speichern.

Sie sollten den Speicherplatz regelmäßig überwachen, um sicherzustellen, dass die lync Server 2013-Bereitstellung aufgrund unzureichender Speicherressourcen nicht beeinträchtigt wird.

Vergleichen und verwalten Sie statistische Informationen zu dem verfügbaren Speicherplatz auf den einzelnen lync Server 2013-Volumes und dem erwarteten Wachstum der Datenbanken und Transaktionsprotokolldateien. Dies hilft bei der Kapazitätsplanung und beim Hinzufügen von Speicher, wenn die Speicherressourcen erforderlich sind.

Zur Unterstützung von Problemen bei der Problembehandlung und Notfallwiederherstellung empfiehlt es sich, den verfügbaren freien Speicherplatz gleich oder größer als 110 Prozent der Datenbankgröße zu haben.

Sie können den freien Speicherplatz überprüfen, indem Sie die folgenden Methoden verwenden:

1.  **System Center Operations Manager**   System Center Operations Manager kann verwendet werden, um Administratoren zu warnen, wenn der Speicherplatz für Volumes begrenzt ist.

2.  **Beim Ausführen eines Skripts**   wird der Speicherplatz durch Ausführen eines Skripts überwacht, das Ihnen eine Nachricht sendet, wenn der verfügbare Festplattenspeicherplatz unter 20 Prozent fällt. Sie können ein Beispielskript im Microsoft Script Center auf TechNet finden, indem Sie Folgendes untersuchen:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows**   -Explorer verwenden Sie den Windows-Explorer, um den Speicherplatz auf Volumes zu überprüfen, die lync Server 2013-Protokolle und-Datenbanken speichern.

</div>

<span> </span>

</div>

</div>

</div>


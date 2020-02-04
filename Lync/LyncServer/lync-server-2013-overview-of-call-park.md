---
title: 'Lync Server 2013: Übersicht über den Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Übersicht über den Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Mit der lync Server 2013-Anwendung Parken können Enterprise-VoIP-Benutzer eine der folgenden Aktionen ausführen:

  - Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.

  - Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).

  - Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.

Wenn ein Benutzer einen Anruf parkt, übergibt lync Server den Anruf an eine temporäre Nummer, die so genannte *Orbit*, in der der Anruf gehalten wird, bis er abgerufen wird, oder es wird ein Timeout festgestellt. Lync Server sendet die Umlaufbahn an den Benutzer, der den Anruf abgestellt hat. Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster „Unterhaltung“ klicken.

Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster „Unterhaltung“ geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.

Da Umlaufbahn Bereiche global eindeutig sind, ist es möglich, Anrufe von jeder lync Server-Website oder einem PBX-Telefon abzurufen, wenn Routing entsprechend konfiguriert ist. Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat. Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde. Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird. Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen. Wenn der Anruf entgegengenommen oder die Verbindung unterbrochen wird, wird der Orbit erneut freigegeben.

Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren. Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln, also solche, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet. Jeder Front-End-Pool verfügt über eine Anruf Park Tabelle auf dem entsprechenden Back-End-Server, der zum Verwalten von Anrufen dient, die auf dem Pool abgestellt werden. Die Liste der Umlaufbahn Bereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Umlaufbahnen an den Ziel Pool verwendet. Jeder lync-Server Pool, in dem die Anwendung für das Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen. Umlaufbahn Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.

Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.

<div>


> [!NOTE]  
> Angepasste Musik-in-situ-Dateien für den Parken von Anrufen werden nicht im Rahmen des lync Server 2013-Wiederherstellungsprozesses gesichert und gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden. Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.



</div>

Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente. Wenn Sie Enterprise-VoIP bereitstellen, wird die Anwendung für den Anruf Park automatisch installiert und aktiviert. Bevor Sie den Anruf Park verwenden können, muss der Enterprise Voice-Administrator ihn aber über die VoIP-Richtlinie konfigurieren und für die Benutzer aktivieren.

</div>

<span> </span>

</div>

</div>

</div>


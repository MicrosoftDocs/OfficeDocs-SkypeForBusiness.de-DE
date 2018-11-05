---
title: 'Lync Server 2013: Übersicht über das Parken von Anrufen'
TOCTitle: Übersicht über das Parken von Anrufen
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205124(v=OCS.15)
ms:contentKeyID: 49294841
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Die Lync Server 2013Anwendung zum Parken von Anrufen bietet Enterprise-VoIP-Benutzern folgende Möglichkeiten:

  - Halten eines Anrufs und anschließendes Entgegennehmen des Anrufs am selben oder an einem anderen Telefon.

  - Halten eines Anrufs, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übergeben (z. B. die Vertriebsabteilung oder ein Lagerort mit einem Telefon im öffentlichen Bereich).

  - Halten eines Anrufs, um weitere Anrufe an einem Telefon entgegennehmen zu können.

Wenn ein Benutzer einen Anruf parkt, leitet Lync Server den Anruf an eine temporäre Nummer (einen sogenannten *Orbit* ) weiter, um den Anruf zu halten, bis er entgegengenommen wird oder ein Timeout auftritt. Lync Server sendet den Orbit an den Benutzer, der den Anruf geparkt hat. Zum Wiederaufnehmen des geparkten Anrufs kann der Benutzer die Orbitnummer wählen oder auf den Orbitlink oder die Schaltfläche im Fenster "Unterhaltung" klicken.

Der Benutzer, der einen Anruf geparkt hat, kann einen anderen Benutzer mithilfe eines externen Mechanismus (beispielsweise über eine Sofortnachricht oder ein Paging-System) über die Orbitnummer informieren, damit dieser Benutzer den Anruf entgegennehmen kann. Der Benutzer, der den Anruf geparkt hat, kann das Fenster "Unterhaltung" geöffnet lassen, um eine Benachrichtigung zu erhalten, sobald der Anruf entgegengenommen wurde.

Da Orbitbereiche eindeutig sind, können Anrufe von einem beliebigen Lync Server-Standort oder Nebenstellentelefon wiederaufgenommen werden, wenn das Routing entsprechend konfiguriert ist. Wenn der Anruf innerhalb einer konfigurierbaren Zeitdauer nicht wiederaufgenommen wird, wird er erneut an den Benutzer zurückgegeben, der den Anruf geparkt hat. Wenn dieser Benutzer den Anruf nicht beantwortet, wird er an ein Fallbackziel übergeben (z. B. einen Agent), sofern dies konfiguriert wurde. Sie können konfigurieren, wie oft das Telefon erneut läutet (ein- bis zehnmal), bevor der Anruf weitergeleitet wird. Wenn ein weitergeleiteter Anruf nicht entgegengenommen wird, wird die Verbindung unterbrochen. Wird der Anruf entgegengenommen oder die Verbindung unterbrochen, wird der Orbit erneut freigegeben.

Wenn Sie die Funktion zum Parken von Anrufen bereitstellen, müssen Sie Durchwahlnummernbereiche zum Parken von Anrufen reservieren. Bei diesen Durchwahlnummern muss es sich um virtuelle Durchwahlnummern handeln: Durchwahlnummern, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbittabelle für das Parken von Anrufen mit den Durchwahlnummernbereichen und geben an, welcher Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche verarbeitet. Jeder Front-End-Pool verfügt über eine Tabelle für das Parken von Anrufen auf dem zugehörigen Back-End-Server, der zum Verwalten von Anrufen verwendet wird, die im Pool geparkt werden. Die Liste der Orbitbereiche wird im zentraler Verwaltungsspeicher gespeichert und für das Routing von Orbits an den Zielpool verwendet. Jeder Lync Server-Pool, in dem die Anwendung zum Parken von Anrufen bereitgestellt und konfiguriert ist, kann über einen oder mehrere Orbitbereiche verfügen. Orbitbereiche müssen innerhalb der Lync Server-Bereitstellung eindeutig sein.

Sie können darüber hinaus weitere Einstellungen für das Parken von Anrufen konfigurieren, wie z. B., an welches Ziel Anrufe bei einem Timeout umgeleitet werden und ob für den Anrufer Musik wiedergegeben wird, während der Anruf geparkt ist. Außerdem können Sie die Musikdatei angeben, die beim Parken des Anrufs wiedergegeben wird.


> [!NOTE]
> Angepasste Musikdateien für geparkte Anrufe werden im Rahmen des Notfallwiederherstellungsprozesses von Lync Server 2013 nicht gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt oder gelöscht werden. Bewahren Sie stets eine separate Sicherungskopie der für geparkte Anrufe hochgeladenen angepassten Musikdateien auf.



Die Anwendung zum Parken von Anrufen ist eine Enterprise-VoIP-Komponente. Bei der Bereitstellung von Enterprise-VoIP wird die Anwendung zum Parken von Anrufen automatisch installiert und aktiviert. Bevor Sie die Funktion zum Parken von Anrufen verwenden können, muss der Enterprise-VoIP-Administrator die Anwendung jedoch konfigurieren und über eine VoIP-Richtlinie für Benutzer aktivieren.


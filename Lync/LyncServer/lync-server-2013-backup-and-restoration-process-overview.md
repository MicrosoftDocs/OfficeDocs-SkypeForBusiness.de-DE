---
title: Übersicht über den Sicherungs- und Wiederherstellungsvorgang
TOCTitle: Übersicht über den Sicherungs- und Wiederherstellungsvorgang
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202192(v=OCS.15)
ms:contentKeyID: 52056473
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über den Sicherungs- und Wiederherstellungsvorgang

 

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Dieser Abschnitt enthält eine Übersicht über den Sicherungs- und Wiederherstellungsprozess in Lync Server 2013. Sie können unabhängig vom Standort für alle Standard Edition-Server und Enterprise Edition-Server dasselbe Verfahren anwenden.

In der Regel funktioniert die Sicherungsprozess folgendermaßen:

  - Sie erstellen auf einem eigenständigen Computer, der nicht Teil eines Pools ist, einen Sicherungsspeicherort als freigegebenen Ordner. Auf den Speicherort der Sicherung wird in **$Backup** verwiesen.

  - Sie sichern regelmäßig und nach einem Zeitplan alle Lync Server-Datenbanken und alle in beschriebenen [Anforderungen für die Sicherung und Wiederherstellung: Daten](lync-server-2013-backup-and-restoration-requirements-data.md) Dateispeicher, indem Sie die unter [Sichern von Lync Server](lync-server-2013-backing-up-lync-server.md) beschriebenen Verfahren ausführen. Der zentralen Verwaltungsspeicher enthält alle Servereinstellungen und Konfigurationen.

  - Bei jedem Ausführen einer nachfolgenden Sicherung erstellen Sie einen neuen freigegebenen Ordner und ändern den Pfad, auf den **$Backup** verweist.

In der Regel funktioniert der Wiederherstellungsprozess folgendermaßen:

  - Bei einem Fehler oder Ausfall stellen Sie die Daten am Speicherort, auf den **$Backup** verweist, auf neuen oder bereinigten Computern wieder her.
    

    > [!IMPORTANT]
    > Mit diesem Wiederherstellungsprozess werden Daten nicht auf einem Server im aktuellen Zustand wiederhergestellt. Der Prozess erfordert einen bereinigten oder neuen Server.



  - Damit Ihre Benutzer- und Konferenzinformationen bis zum Zeitpunkt des Ausfalls wiederhergestellt werden können, können Sie eine Notfallwiederherstellungstopologie mit Front-End-Paarpoolen implementieren, so wie in [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md) beschrieben. Abgesehen von dieser Option unterstützt Lync Server nur das einfache Wiederherstellungsmodell für Datenbanken. Mit dem einfachen Wiederherstellungsmodell wird die letzte vollständige Sicherung von Datenbanken wiederhergestellt. Das heißt, der Zustand einer Datenbank beim Auftreten eines Fehlers oder zu einem bestimmten Zeitpunkt kann nicht wiederhergestellt werden. Für viele Organisationen ist das einfache Wiederherstellungsmodell optimal, da die Lync Server-Back-End-Datenbank ("RTCXDS.mdf") tatsächlich kleiner als die Transaktionsprotokolldateien ist und auch erheblich kleiner als die der branchenüblichen Datenbankanwendungen ist.

  - Alle DNS-Konfigurationen (Domain Name System), DHCP-Konfigurationen (Dynamic Host Configuration Protocol), Domänennamen, Computer-FQDNs (vollqualifizierte Domänennamen), Dateispeicherpfade usw. müssen zum Zeitpunkt der Wiederherstellung dieselben wie zum Zeitpunkt der Sicherung sein.

Wenn ein Server ausfällt, auf dem Lync Server ausgeführt wird, beinhaltet die Wiederherstellung folgende Schritte:

  - Installieren Sie das Betriebssystem auf einem neuen oder bereinigten Computer mit demselben FQDN wie der ausgefallene Computer.

  - Installieren Sie die Zertifikate neu.

  - Wenn auf dem Server eine Datenbank gehostet wurde, installieren Sie Microsoft SQL Server 2012 oder Microsoft SQL Server 2008 R2.

  - Im Allgemeinen sollten Sie Topologie-Generator ausführen, um die Datenbank zu erstellen und installieren und Zugriffssteuerungslisten (ACLs) einrichten, wenn auf Server eine Datenbank gehostet wurde.

  - Wenn auf dem Server eine Serverrolle gehostet wurde, führen Sie immer die Schritte 1 bis 4 des Lync Server-Bereitstellungs-Assistenten aus, um die lokalen Konfigurationsdateien und die Serverrollenkomponenten zu installieren, Zertifikate zuzuweisen und die Dienste zu starten.
    

    > [!NOTE]
    > Wenn auf dem Server eine mit der Serverrolle verbundene Datenbank gehostet wurde, wird die Datenbank durch Ausführen des Schritts&nbsp;2 des Lync Server-Bereitstellungs-Assistenten wiederhergestellt.



  - Wenn auf dem Server eine Datenbank gehostet wurde, stellen Sie die gesicherten Daten wieder her.


---
title: 'Lync Server 2013: Definieren und Konfigurieren der Topologie'
TOCTitle: Definieren und Konfigurieren der Topologie
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398339(v=OCS.15)
ms:contentKeyID: 49294000
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren und Konfigurieren der Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-14_

Zur Definition und Konfiguration Ihrer Topologie verwenden Sie den Topologie-Generator. Zur Verwendung des Topologie-Generators müssen Sie kein Mitglied der lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten (z. B. "Domänen-Admins") sein. Sie können die Topologie als Standardbenutzer definieren. Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll. Sie haben folgende Möglichkeiten:

  - Herunterladen der Topologie aus einer vorhandenen Bereitstellung

  - Öffnen der Topologie aus einer lokalen Datei

  - Neue Topologie

Wenn Sie bereits eine Topologie definiert und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen. Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab. Diese Option sollte immer gewählt werden, wenn Sie über einen vorhandenen zentralen Verwaltungsspeicher verfügen.

Wenn Sie keinen zentralen Verwaltungsspeicher eingerichtet haben und eine zuvor gespeicherte Konfiguration bearbeiten möchten, sollten Sie die Topologie aus einer lokalen Datei öffnen. Bei dieser Datei handelt es sich um die Konfigurationsdatei, die in einer vorherigen Sitzung gespeichert wurde. Diese Option kann zum Bearbeiten der zuvor gespeicherten Topologie verwendet werden.


> [!WARNING]
> Wenn Sie bereits eine Topologie veröffentlicht haben, sollten Sie keine lokale Konfigurationsdatei laden. Laden Sie die Topologie in diesem Fall aus einer vorhandenen Bereitstellung herunter.



Wählen Sie die Option zum Erstellen einer neuen Topologie, um eine neue Topologie im Topologie-Generator zu erstellen. Ein zuvor gespeicherter Entwurf wird nur überschrieben, wenn Sie die neue Topologie unter demselben Dateinamen speichern wie die in einer vorherigen Entwurfssitzung erstellte Topologie.

Bei jeder dieser Optionen werden Sie zur Angabe eines Speicherorts für die Topologie-Generator-Konfigurationsdatei aufgefordert. Die Datei kann an einem lokalen Speicherort, an einem gemeinsam genutzten Speicherort auf einer bereits eingerichteten Dateifreigabe oder auf einem Wechselmedium gespeichert werden.

## In diesem Abschnitt

  - [Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung in Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Auswählen des zentralen Verwaltungsservers in Lync Server 2013](lync-server-2013-select-the-central-management-server.md)


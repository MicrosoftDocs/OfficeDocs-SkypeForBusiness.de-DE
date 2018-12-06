---
title: 'Lync Server 2013: Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition'
TOCTitle: Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398102(v=OCS.15)
ms:contentKeyID: 49293040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-11-11_

In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die in einer Lync Server 2013-Front-End-Poolbereitstellung verbunden werden können.

## Serverrollen

In Lync Server 2013 sind der A/V-Konferenzdienst, der Vermittlungsdienst, die Überwachung und die Archivierung auf dem Front-End-Server verbunden, aber es sind zusätzliche Konfigurationsschritte für deren Aktivierung erforderlich. Falls Sie den Vermittlungsserver nicht mit dem Front-End-Server verbinden möchten, können Sie ihn als eigenständigen Vermittlungsserver auf einem separaten Computer bereitstellen.

Sie können einen vertrauenswürdigen Anwendungsserver mit dem Front-End-Server verbinden.

Die folgenden Serverrollen müssen auf jeweils einem separaten Computer bereitgestellt werden:

  - Director

  - Edgeserver

  - Vermittlungsserver (sofern nicht gemeinsam mit dem Front-End-Server ausgeführt)

  - Office Web Apps-Server

Sie können die Beständiger Chat-Serverrolle nicht mit dem Front-End-Server verbinden.

## Datenbanken

Sie können jede der folgenden Datenbanken auf demselben Datenbankserver ausführen:

  - Back-End-Datenbank

  - Überwachungsdatenbank

  - Archivierungsdatenbank

  - Datenbank für Beständiger Chat

  - Konformitätsdatenbank für Beständiger Chat

Sie können beliebige oder alle dieser Datenbanken in einer einzigen Instanz von SQL Server ausführen oder jeweils eine separate Instanz von SQL Server verwenden. Dabei gelten folgende Beschränkungen:

  - Jede Instanz von SQL Server kann nur eine Back-End-Datenbank, eine Überwachungsdatenbank, eine Archivierungsdatenbank, eine Datenbank für Beständiger Chat und eine Konformitätsdatenbank für Beständiger Chat enthalten.

  - Der Datenbankserver unterstützt nur jeweils einen Front-End-Pool, eine Archivierungsbereitstellung und eine Überwachungsbereitstellung. Dabei spielt es keine Rolle, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

Das Verbinden einer Dateifreigabe mit den Datenbanken ist möglich, wie weiter unten in diesem Abschnitt beschrieben.


> [!NOTE]
> In Lync Server 2013 können Sie den Archivierungsspeicher für einige oder alle Benutzer der Bereitstellung in den Exchange 2013-Speicher integrieren. Sie können keine Server, auf denen Lync Server oder Komponenten ausgeführt werden, auf denselben Servern wie den Exchange-Speicher bereitstellen.




> [!IMPORTANT]
> Obwohl die Kollokation (Verbindung) von Datenbanken unterstützt wird, kann die Größe der Datenbanken schnell anwachsen. Wenn Sie z.&nbsp;B. in Erwägung ziehen, die Archivierungsserverdatenbank mit anderen Datenbanken zu verbinden, müssen Sie beachten, dass beim Archivieren der Nachrichten von mehreren Benutzern der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß sein kann. Aus diesem Grund wird das Verbinden mehrerer Datenbanken nicht empfohlen, vor allem für die Archivierungsdatenbank, die Datenbank für Beständiger Chat oder die Konformitätsdatenbank für Beständiger Chat mit der Back-End-Datenbank.



## Dateifreigabe

Die Dateifreigabe kann auf einem separaten Server oder auf demselben Server wie folgende Server ausgeführt werden:

  - Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

  - Archivierungsdatenbank

  - Überwachungsdatenbank

  - Datenbank für Beständiger Chat

  - Konformitätsdatenbank für Beständiger Chat

Eine einzelne Dateifreigabe kann für mehrere Front-End-Pools und Standard Edition-Server (am gleichen Standort) verwendet werden.


> [!NOTE]
> In Lync Server 2013 wird für die Überwachung und Archivierung die Lync Server-Dateifreigabe als Front-End-Server verwendet.



## Weitere Komponenten

Sie können einen Reverseproxyserver, der keine Lync Server 2013-Komponente ist, aber in der Bereitstellung benötigt wird, wenn die Freigabe von Webinhalten für Verbundbenutzer unterstützt werden soll, nicht mit einer Lync Server 2013-Serverrolle verbinden. Allerdings können Sie Reverseproxyunterstützung für eine Lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung auf einem vorhandenen Reverseproxyserver in Ihrer Organisation konfigurieren, der für andere Anwendungen genutzt wird.

Mit einer Exchange Unified Messaging (UM)-Komponente oder SharePoint-Komponente kann keine SharePoint Server-Rolle verbunden werden.


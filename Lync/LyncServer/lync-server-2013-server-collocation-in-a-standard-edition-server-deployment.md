---
title: 'Lync Server 2013: Gemeinsames Ausführen von Servern in einer Standard Edition-Serverbereitstellung'
TOCTitle: Gemeinsames Ausführen von Servern in einer Standard Edition-Serverbereitstellung
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398131(v=OCS.15)
ms:contentKeyID: 49293076
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gemeinsames Ausführen von Servern in einer Standard Edition-Serverbereitstellung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-01-20_

In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer Serverbereitstellung mit Lync Server 2013 Standard Edition verbinden können.

## Serverrollen

Unter Lync Server 2013 werden der A/V-Konferenzdienst, der Vermittlungsdienst, die Überwachung und Archivierung auf dem Standard Edition-Server verbunden, zur Aktivierung sind jedoch zusätzliche Konfigurationsschritte erforderlich. Sie können den Vermittlungsdienst auf verschiedenen Servern bereitstellen.

Sie können einen vertrauenswürdigen Andwendungsserver mit einem Standard Edition-Server verbinden.

Die folgenden Serverrollen müssen auf jeweils einem separaten Computer bereitgestellt werden:

  - Director

  - Edgeserver

  - Vermittlungsserver (sofern nicht gemeinsam mit dem Standard Edition-Server ausgeführt)

  - Office Web Apps-Server

## Datenbanken

Die SQL Server Express-Back-End-Datenbank wird standardmäßig mit dem Standard Edition-Server verbunden. Sie kann nicht auf einen separaten Computer verschoben werden. Ferner ist es bis auf eine Ausnahme nicht möglich, andere Datenbanken mit dem Standard Edition-Server zu verbinden. Wenn Sie den Server für beständigen Chat auf einem Standard Edition-Server einsetzen, werden die Datenbank für beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat auf demselben Standard Edition-Server verbunden.

Sie können jede der folgenden Datenbanken mit einem einzigen Datenbankserver verbinden:

  - Überwachungsdatenbank

  - Archivierungsdatenbank

  - Eine Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool

Sie können diese Datenbanken einzeln oder alle in einer einzigen SQL-Instanz verbinden oder für jede eine separate SQL-Instanz verwenden, wobei folgende Beschränkungen gelten:

  - Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank (für einen Enterprise Edition-Front-End-Pool), eine einzige Überwachungsdatenbank, eine einzige Archivierungsdatenbank, eine einzige Datenbank für beständigen Chat und eine einzige Kompatibilitätsdatenbank für beständigen Chat enthalten.

  - Der Datenbankserver kann nicht mehr als einen Enterprise Edition-Front-End-Pool, einen Archivierungsserver, einen Überwachungsserver, eine einzelne Datenbank für Beständiger Chat und eine einzelne Kompatibilitätsdatenbank für Beständiger Chat unterstützen. Er kann aber jeweils einen bzw. eine davon unterstützen, unabhängig davon, ob die Datenbanken dieselbe SQL Server-Instanz oder separate SQL Server-Instanzen verwenden.

Das Verbinden einer Dateifreigabe mit den Datenbanken ist möglich, wie weiter unten in diesem Abschnitt beschrieben.


> [!NOTE]
> Unter Lync Server 2013 können Sie den Überwachungs- und Archivierungsspeicher in den Exchange 2013-Speicher für einige oder alle Benutzer in der Bereitstellung integrieren. Sie können keine Server mit Lync Server oder Komponenten auf denselben Servern wie der Exchange-Speicher bereitstellen.




> [!IMPORTANT]
> Die gemeinsame Ausführung von Datenbanken wird zwar unterstützt, die Datenbanken können jedoch schnell wachsen. Wenn Sie beispielsweise in Erwägung ziehen, die Archivierungsdatenbank mit anderen Datenbanken zu verbinden, müssen Sie beachten, dass beim Archivieren der Nachrichten von mehreren Benutzern der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß sein kann. Aus diesem Grund wird das Verbinden mehrerer Datenbanken, insbesondere der Archivierungsdatenbank, der Datenbank für Beständiger Chat und der Kompatibilitätsdatenbank für Beständiger Chat, mit der Back-End-Datenbank eines Enterprise-Pools nicht empfohlen.



## Dateifreigaben

Die Dateifreigabe kann auf einem separaten Server oder auf demselben Server wie folgende Server ausgeführt werden:

  - Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

  - Archivierungsdatenbank

  - Überwachungsdatenbank

  - Datenbank für Beständiger Chat

  - Konformitätsdatenbank für Beständiger Chat

Eine einzelne Dateifreigabe kann für mehrere Front-End-Pools und Standard Edition-Server (am gleichen Standort) verwendet werden.


> [!NOTE]
> Unter Lync Server 2013 wird von der Überwachung und der Archivierung die Lync Server-Dateifreigabe als Standard Edition-Server verwendet.



## Weitere Komponenten

Sie können einen Reverseproxyserver, der keine Lync Server 2013-Komponente ist, aber in der Bereitstellung benötigt wird, wenn die Freigabe von Webinhalten für Verbundbenutzer unterstützt werden soll, nicht mit einer Lync Server 2013-Serverrolle verbinden. Allerdings können Sie Reverseproxyunterstützung für eine Lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung auf einem vorhandenen Reverseproxyserver in Ihrer Organisation konfigurieren, der für andere Anwendungen genutzt wird.

Mit einer Exchange UM-Komponente oder SharePoint-Komponente kann keine Lync Server 2013-Rolle verbunden werden.


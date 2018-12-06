---
title: Einrichten des Speichers für die Archivierung
TOCTitle: Einrichten des Speichers für die Archivierung
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205392(v=OCS.15)
ms:contentKeyID: 49295937
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten des Speichers für die Archivierung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Der Archivierungsspeicher für Lync Server 2013 umfasst Folgendes:

  - **Datenspeicher**   Der Datenspeicher wird zum Speichern von Instant Messaging-Inhalten benötigt.

  - **Dateispeicher**   Der Dateispeicher wird zum Speichern von Konferenzinhalten (Besprechungsinhalten) benötigt.

## Einrichten des Datenspeichers

Die Anforderungen für das Einrichten des Datenspeichers für die Archivierung in Lync Server 2013 richten sich danach, wie Sie Archivierungsdaten speichern möchten:

  - Lync Server 2013-Archivierung mit der Exchange-Bereitstellung integrieren, um Archivierungsdaten mithilfe des Exchange-Speichers speichern zu können.

  - Separate SQL Server-Datenbankserver einrichten, um Archivierungsdaten zu speichern.

## Einrichten des Exchange-Speichers für Archivierungsdaten

Wenn Sie Exchange für die Speicherung von Archivierungsdaten einrichten möchten, muss in der Exchange-Bereitstellung Exchange 2013 ausgeführt werden. Außerdem müssen Benutzerpostfächer auf dem Exchange 2013-Server verwaltet werden, und deren Postfächer müssen im Compliance-Archiv gespeichert werden. Ausführliche Informationen zum Konfigurieren von Exchange 2013 finden Sie in der Produktdokumentation zu Exchange.

## Einrichten von Datenbankservern mit SQL Server für die Speicherung von Archivierungsdaten

Für die Archivierung in Lync Server 2013 ist es erforderlich, dass die SQL Server-Datenbanksoftware die archivierten Daten speichert, es sei denn, Sie integrieren die Bereitstellung mit Exchange.

Für SQL\&nbsp;Server-Archivierungsdatenbanken müssen Sie SQL Server auf dem Computer installieren, der die Archivierungsdatenbank hosten wird. Sie können dazu die gleiche SQL-Instanz verwenden, die auf für die Back-End-Datenbank eines Front-End-Pools verwendet wird. Für bestmögliche Leistung sollte die Archivierungsdatenbank auf einem Computer bereitgestellt werden, der vom zentralen Verwaltungsspeicher getrennt ist. Ausführliche Informationen zum gemeinsamen Ausführen von Lync Server 2013-Komponenten finden Sie unter [Unterstützte Serverzusammenstellungen in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.

Auf jedem Datenbankserver muss eine unterstützte Version von SQL Server ausgeführt werden. Weitere Informationen zu den unterstützten Versionen finden Sie unter [Technische Anforderungen für die Archivierung in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in der Planungsdokumentation.

Sie müssen die SQL Server-Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren. Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (**LcsLog**) beim Veröffentlichen der Topologie erstellen. Sie können die Datenbank auch später erstellen, z.\&nbsp;B. im Rahmen des Installationsverfahrens. Ausführliche Informationen zu SQL Server finden Sie im SQL\&nbsp;Server TechCenter unter [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x407).


> [!NOTE]
> Vergewissern Sie sich, dass der Starttyp des SQL Server-Agent-Diensts „Automatisch“ ist und der SQL Server-Agent-Dienst für die SQL-Instanz mit den Archivierungsdatenbanken ausgeführt wird, damit die SQL Server-Wartungsaufträge für die Standardarchivierung plangemäß unter der Kontrolle des SQL Server-Agent-Diensts ausgeführt können.



## Einrichten des Dateispeichers

Die Archivierung verwendet die Lync Server 2013-Dateifreigabe, die Sie beim Einrichten des Front-End-Pools oder des Standard Edition-Servers angegeben haben. Die für die Archivierung verwendete Dateifreigabe kann nicht geändert werden. Ausführliche Informationen zu den unterstützten Dateispeichersystemen finden Sie unter [Dateispeicherunterstützung in Lync Server 2013](lync-server-2013-file-storage-support.md) in der Unterstützungsdokumentation.


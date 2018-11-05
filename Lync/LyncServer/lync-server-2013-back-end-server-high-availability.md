---
title: 'Lync Server 2013: Hohe Verfügbarkeit von Back-End-Servern'
TOCTitle: Hohe Verfügbarkeit von Back-End-Servern
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205248(v=OCS.15)
ms:contentKeyID: 49295342
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-08-12_

Wenn Sie hohe Verfügbarkeit für Ihre Back-End-Server sicherstellen möchten, können Sie entweder synchrone SQL-Spiegelung oder synchrones SQL-Clustering verwenden. Ein Verwenden von einer dieser Lösungen ist optional, wird aber empfohlen, um die Geschäftskontinuität Ihrer Organisation aufrechtzuerhalten. Die asynchrone SQL-Spiegelung wird für hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013 nicht unterstützt. In diesem Dokument steht, sofern nicht anders angegeben, SQL-Spiegelung für die synchrone SQL-Spiegelung.

SQL-Spiegelung können Sie problemlos mit Topologie-Generator einrichten. Zum Einrichten von SQL-Failoverclustering müssen Sie SQL Server verwenden.

Wenn Sie SQL-Spiegelung oder SQL-Clustering in einem Pool verwenden, der zur Notfallwiederherstellung mit einem anderen Front-End-Pool gekoppelt ist, müssen Sie in beiden Pools dieselbe Lösung für hohe Back-End-Verfügbarkeit verwenden. Sie dürfen keinen Pool, in dem SQL-Spiegelung verwendet wird, mit einem Pool koppeln, in dem SQL-Clustering verwendet.

Wenn Sie SQL-Spiegelung bereitstellen, werden alle Lync Server-Datenbanken im Pool gespiegelt, wozu auch der zentralen Verwaltungsspeicher gehört, falls er sich in diesem Pool befindet, sowie die Datenbank der Reaktionsgruppenanwendung und die Datenbank für die Anwendung zum Parken von Anrufen, falls diese Anwendungen im Pool ausgeführt werden.

Bei der SQL-Spiegelung müssen Sie keinen gemeinsam genutzten Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher.

Sie können die SQL-Spiegelung mit oder ohne einen Spiegelungszeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.

Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar.

Weitere Informationen zur Unterstützung von SQL-Spiegelung finden Sie unter [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md). Ausführlichere Informationen zum Bereitstellen von SQL-Clustering finden Sie unter [Konfigurieren von SQL Server-Clustering](lync-server-2013-configure-sql-server-clustering.md).

## Wiederherstellungszeit für automatisches Failover des Back-End-Servers mit SQL-Spiegelung

Für automatisches Back-End-Failover mit SQL-Spiegelung wird ein Zielwert von 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) angestrebt. Aufgrund der synchronen SQL-Spiegelung wird nicht von einem Datenverlust bei Ausfällen von Back-End-Servern ausgegangen, außen in seltenen Fällen, wenn sowohl der Front-End-Server als auch der Back-End-Server beim Verschieben von Daten zwischen diesen Servern gleichzeitig ausfällt. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.

## Benutzerfreundlichkeit beim Ausfall eines Back-End-Servers mit SQL-Spiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.

Wenn Sie SQL-Spiegelung verwenden und einen Spiegelungszeugen konfiguriert haben und der Prinzipalserver ausfällt, erfolgt das Failover des Back-End-Servers automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.

Wenn kein Spiegelungszeuge konfiguriert ist, dauert es eine Weile, bis der Administrator das Failover manuell auslöst. Während dieses Zeitraums können aktive Benutzer betroffen sein. Sie setzen ihre Sitzungen etwa 30 Minuten lang wie gewohnt fort. Falls der primäre Server dann immer noch nicht wiederhergestellt ist oder ein Administrator kein Failover zum Sicherungsserver vorgenommen hat, werden die Benutzer auf den Ausfallsicherheitsmodus umgestellt. Dies bedeutet, dass sie keine Aufgaben ausführen können, die eine dauerhafte Änderung in Lync Server erfordern (z. B. das Hinzufügen eines Kontakts).

Wenn Sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen, oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.


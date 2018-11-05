---
title: 'Lync Server 2013: Erforderliche Ressourcen für den Server für beständigen Chat'
TOCTitle: Erforderliche Ressourcen
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205211(v=OCS.15)
ms:contentKeyID: 49295239
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erforderliche Ressourcen für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-02-05_

Hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat erfordert zusätzliche Ressourcen über das hinaus, was normalerweise für den Vollbetrieb benötigt wird. Bevor Sie Server für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung konfigurieren, sollten Sie sicherstellen, dass die folgenden Ressourcen zusätzlich zu den für den Standardbetrieb von Server für beständigen Chat erforderlichen Ressourcen vorhanden sind. Zusätzliche Konfigurationsinformationen finden Sie unter [Konfigurieren des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Eine dedizierte Datenbankinstanz im selben physischen Rechenzentrum, in dem sich auch das Front-End des Server für beständigen Chat-Diensts befindet. Diese Datenbank dient als SQL Server-Spiegel für die primäre Beständiger Chat-Datenbank. Bestimmen Sie optional einen zusätzlichen SQL Server als Spiegelungszeuge, falls Sie ein automatisches Failover zur Spiegeldatenbank wünschen.

  - Eine dedizierte Datenbankinstanz im anderen physischen Rechenzentrum. Diese Datenbank dient als sekundäre Datenbank des SQL Server-Protokollversands für die Datenbank im primären Rechenzentrum.

  - Eine dedizierte Datenbankinstanz, die als SQL Server-Spiegel für die sekundäre Datenbank dient. Bestimmen Sie optional einen zusätzlichen SQL Server als Spiegelungszeuge. Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.

  - Falls die Server für beständigen Chat-Kompatibilität aktiviert ist, sind drei zusätzliche dedizierte Datenbankinstanzen erforderlich. Deren Verteilung ist mit der weiter oben beschriebenen Beständiger Chat-Datenbank identisch. Während die Kompatibilitätsdatenbank dieselbe SQL Server-Instanz wie die Beständiger Chat-Datenbank verwenden kann, empfehlen wir für hohe Verfügbarkeit und Notfallwiederherstellung eigenständige Instanzen.

  - Sie müssen eine Dateifreigabe erstellen und den Transaktionsprotokollen für den SQL Server-Protokollversand zuweisen. Alle SQL-Server in beiden Rechenzentren, auf denen Beständiger Chat-Datenbanken ausgeführt werden, müssen Lese-/Schreibzugriff auf diese Dateifreigabe haben. Diese Freigabe wird nicht als Teil einer FileStore-Rolle definiert.

  - Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server-Transaktionsprotokolle dient, welche aus der Dateifreigabe des primären Servers kopiert werden.

In den folgenden Abbildungen sind Konfigurationsbeispiele für den gesamten Serverpool für beständigen Chat in den beiden erweiterten Pooltopologien veranschaulicht:

  - Erweiterter Serverpool für beständigen Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.

  - Erweiterter Serverpool für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.

In der folgenden Abbildung ist eine erweiterte Serverpool für beständigen Chat-Topologie dargestellt, bei der die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.

**Erweiterter Pool mit Servern für beständigten Chat, bei dem die Geolocation der Rechenzentren eine hohe Bandbreite bzw. eine geringe Wartezeit aufweist.**

![HBW-Konfiguration für Serverpool für beständigen Chat (Test)](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "HBW-Konfiguration für Serverpool für beständigen Chat (Test)")

In der folgenden Abbildung ist eine erweiterte Serverpool für beständigen Chat-Topologie dargestellt, bei der die Geolocation der Rechenzentren eine niedrige Bandbreite bzw. eine lange Wartezeit aufweist.

**Erweiterter Pool mit Servern für beständigen Chat, bei dem die Geolocation der Rechenzentren eine geringe Bandbreite bzw. eine lange Wartezeit aufweist.**

![LBW-Konfiguration für Serverpool für beständigen Chat (Test)](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "LBW-Konfiguration für Serverpool für beständigen Chat (Test)")


---
title: 'Lync Server 2013: Planen der Bildung von Front-End-Poolpaaren'
TOCTitle: Planen der Bildung von Front-End-Poolpaaren
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205293(v=OCS.15)
ms:contentKeyID: 49295430
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen der Bildung von Front-End-Poolpaaren in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Für die optimale Notfallwiederherstellung in Lync Server 2013 sollten Sie Front-End-Poolpaare an zwei geografisch unterschiedlichen Orten bereitstellen. Jeder Standort enthält einen Front-End-Pool, für den es einen entsprechenden Front-End-Pool am anderen Standort gibt. Beide Standorte sind aktiv, und der Sicherungsdienst von Lync Server ermöglicht die Datenreplikation in Echtzeit, damit die Pools synchronisiert bleiben. Beim Sicherungsdienst handelt es sich um ein neues Feature in Lync Server 2013, das die Notfallwiederherstellungslösung unterstützt. Es wird auf einem Front-End-Pool installiert, wenn Sie dem Pool einen anderen Front-End-Pool gegenüberstellen.

Falls der Pool an einem Standort ausfällt, können Sie für die Benutzer ein Failover von diesem Pool auf den Pool am anderen Standort vornehmen, von dem dann für alle Benutzer in beiden Pools Dienste bereitgestellt werden. Aus Kapazitätsplanungsgründen sollte bei einem Notfall jeder Pool in der Lage sein, die Arbeitsauslastung aller Benutzer in beiden Pools zu bewältigen.

## In diesem Abschnitt

  - [Unterstützte Optionen und bewährte Methoden für das Einrichten von Poolpaaren in Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Beziehungen von Sicherungsregistrierungsstellen in Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Wiederherstellungsdauer bei einem Failover und Failback eines Pools in Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Failover des zentralen Verwaltungsspeichers in Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Datensicherheit beim Bilden von Front-End-Poolpaaren in Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)


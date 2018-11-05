---
title: 'Lync Server 2013: Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts'
TOCTitle: Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts in Lync Server 2013
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49891017
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-12_

In diesem Abschnitt finden Sie Verfahren für Notfallwiederherstellungsvorgänge sowie für die Verwaltung des Sicherungsdienstes, der die Daten in einem Front-End-Poolpaar synchronisiert.

Bei den Notfallwiederherstellungsverfahren, sowohl für Failover als auch für Failback, handelt es sich um manuelle Methoden. Tritt ein Notfall ein, muss der Administrator die Failoverprozeduren manuell aufrufen. Gleiches gilt für den Failback nach der Reparatur des Pools.

Bei den Notfallwiederherstellungsverfahren in diesem Abschnitt wird Folgendes vorausgesetzt:

  - Sie haben eine Bereitstellung mit paarweise angeordneten Front-End-Pools, die sich an unterschiedlichen Standorten befinden, wie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md) beschrieben. Der Sicherungsdienst ist in diesem Poolpaar ausgeführt worden, um die Pools synchron zu halten.

  - Wenn der zentralen Verwaltungsspeicher in einem der beiden Pools gehostet wird, wird er in beiden paarweise angeordneten Pools installiert und ausgeführt, wobei einer dieser Pools den aktiven Master hostet und der andere das Standbysystem.


> [!IMPORTANT]
> In den folgenden Verfahren bezeichnet der <EM>PoolFQDN</EM> -Parameter den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools, der von dem Notfall betroffen ist, und nicht den Pool, aus dem betroffene Benutzer umgeleitet werden. Für die gleiche Gruppe von betroffenen Benutzern bezeichnet er den gleichen Pool sowohl in Failover- als auch in Failback-Cmdlets (d. h. den Pool, in dem die Benutzer verwaltet wurden, bevor der Failover eintrat).<BR>Nehmen wir beispielsweise an, für alle Benutzer, die in einem Pool P1 verwaltet werden, wurde ein Failover zum Sicherungspool P2 durchgeführt. Möchte der Administrator nun alle Benutzer, die derzeit von P2 bedient werden, zu P1 verschieben, muss er die folgenden Schritte ausführen: 
> <OL>
> <LI>
> <P>Mithilfe des Failback-Cmdlets einen Failback aller Benutzer, die ursprünglich auf P1 verwaltet wurden, von P2 zu P1 ausführen. In diesem Fall ist der <EM>PoolFQDN</EM> der FQDN von P1.</P>
> <LI>
> <P>Mithilfe des Failover-Cmdlets einen Failover aller Benutzer, die ursprünglich auf P2 verwaltet wurden, zu P1 ausführen. In diesem Fall ist der <EM>PoolFQDN</EM> der FQDN von P2.</P>
> <LI>
> <P>Wenn der Administrator später einen Failback dieser P2-Benutzer zurück zu P2 ausführen möchte, ist der <EM>PoolFQDN</EM> der FQDN von P2.</P></LI></OL>Beachten Sie, dass der obige Schritt 1 vor Schritt 2 ausgeführt werden muss, um die Poolintegrität aufrecht zu erhalten. Wenn Sie zuerst Schritt 2 auszuführen versuchen, tritt beim Cmdlet von Schritt 2 ein Fehler auf.



## In diesem Abschnitt

  - [Konfigurieren und Überwachen des Sicherungsdiensts in Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Ausführen eines Failovers für einen Pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Ausführen eines Failbacks für einen Pool in Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Ausführen eines Failovers für eine gespiegelte Datenbank in Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts in Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

## Siehe auch

#### Konzepte

[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)


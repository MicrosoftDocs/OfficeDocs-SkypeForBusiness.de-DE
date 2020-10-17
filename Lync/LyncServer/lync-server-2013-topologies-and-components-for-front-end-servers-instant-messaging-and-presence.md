---
title: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit'
description: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550291"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-10-24_

Für Instant Messaging (IM) und Anwesenheit sind nur diese Komponenten erforderlich:

  - Die Front-End- oder Standard Edition-Server Ihrer Organisation. Instant Messaging- und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert.

  - Ein Lastenausgleichsmodul, wenn Sie über ein Enterprise Edition-Front-End-Pool verfügen. Weitere Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planen der Bereitstellung von Front-End-Pools

In lync Server 2013 wurde Front-End-Pool Architektur geändert, und diese Änderungen wirken sich auf die Planung und Wartung Ihrer Front-End-Pools aus.

Es wird empfohlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server umfassen. In lync Server verwendet die Architektur von Front-End-Pools ein Modell für verteilte Systeme, wobei die Daten der einzelnen Benutzer auf drei Front-End-Servern im Pool aufbewahrt werden. Weitere Informationen zu dieser neuen Architektur finden Sie unter [Topologie-Änderungen in lync Server 2013](lync-server-2013-topology-changes.md).

Wenn Sie keine drei Enterprise Edition-Front-End-Server bereitstellen möchten und eine Notfallwiederherstellung wünschen, sollten Sie lync Server Standard Edition verwenden und zwei Pools mit einer gepaarten Sicherungsbeziehung erstellen. Dadurch wird eine Notfallwiederherstellungslösung mit nur zwei Servern bereitgestellt. Weitere Informationen zu Hochverfügbarkeit und Notfall Wiederherstellungs Topologien und-Features finden Sie unter [Planning for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

Für Front-End-Pools befolgen Sie die Richtlinien in diesem Abschnitt.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Sicherstellen, dass die Pools funktionsfähig sind

Mit dem neuen verteilten Modell für Front-End-Pools müssen bestimmte Nummern der Server eines Pools aktiv sein, damit der Pool funktioniert. Es gibt zwei Verlust Modi für einen Pool.

  - Quorum Verlust auf Routing Gruppenebene, der durch nicht genügend Replikatserver für eine bestimmte Routinggruppe verursacht wird. Eine Routinggruppe ist eine Aggregation einer Gruppe von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: eine primäre und zwei sekundäre.

  - Quorum Verlust auf Poolebene, verursacht werden, wenn nicht genügend Seed-Server im Pool ausgeführt werden.

<div>

## <a name="routing-group-level-quorum-loss"></a>Quorum Verlust auf Routing Gruppenebene

Wenn Sie ein neues Front-End-Pool zum ersten Mal starten, ist es wichtig, dass 85% der Serverbetriebs bereit sind, wie in der folgenden Tabelle dargestellt. Wenn weniger Server aktiv sind, können die Dienste möglicherweise in den Startzustand verfallen, und der Pool wird möglicherweise nicht gestartet.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtanzahl der Server im Pool</th>
<th>Anzahl der Server, die ausgeführt werden müssen, damit der Pool beim ersten Mal gestartet wird</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10 </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10 </p></td>
</tr>
</tbody>
</table>


Bei jedem nachfolgenden Start des Pools sollten 85% der Server gestartet werden (siehe obige Tabelle). Wenn diese Anzahl von Servern nicht gestartet werden kann (es können jedoch genügend Server gestartet werden, damit Sie nicht auf der Ebene des Quorums auf der Poolebene sind), können Sie das Cmdlet **Reset-CsPoolRegistrarState – resettype QuorumLossRecovery** verwenden, um zu ermöglichen, dass der Pool von diesem Quorum Verlust auf Routinggruppen Ebene wiederhergestellt wird und Fortschritte macht. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Da lync Server die primäre SQL-Datenbank als Zeuge verwendet, wenn Sie die primäre Datenbank Herunterfahren und zur Spiegelkopie wechseln und genügend Front-End-Server herunterfahren, sodass nicht genügend entsprechend der oben aufgeführten Tabelle ausgeführt wird, wird der gesamte Pool nach unten gehen. Weitere Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/?linkid=393672">Datenbank-Spiegelungs Zeuge</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Quorum Verlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann es nicht auf dem Quorum Verlust auf Poolebene liegen. Wenn die Anzahl der Server, die in der folgenden Tabelle aufgeführt sind, unter die Funktionsebene fällt, werden die restlichen Server im Pool alle lync Server Dienste beenden. Beachten Sie, dass die Nummern in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool aktiv sind.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtanzahl der Front-End-Server im Pool</th>
<th>Anzahl der Server, die für die korrekte Funktionsweise des Pools ausgeführt werden müssen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Any 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Beliebige 3</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>Beliebige 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>4 der ersten 7 Server</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>5 der ersten 9 Server</p></td>
</tr>
</tbody>
</table>


In der obigen Tabelle sind die "ersten Server" die Server, die zunächst chronologisch aufgelegt wurden, als der Pool zum ersten Mal gestartet wurde. Zum bestimmen dieser Server können Sie das Cmdlet **Get-CsComputer** mit der Option **– poolfqdn "** verwenden. Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der Sie in der Topologie angezeigt werden, und diejenigen, die sich oben in der Liste befinden, sind die ersten Server.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Front-End-Pools mit zwei Front-End-Servern

Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Sollten Sie einen solchen Pool aber doch einmal erstellen müssen, halten Sie sich an folgende Richtlinien:

  - Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.

  - Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
      - Die bewährte Methode besteht darin, beide Front-End-Server gleichzeitig neu zu starten.
    
      - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
      - Falls Sie sie nicht in dieser Reihenfolge neu starten können, führen Sie das folgende Cmdlet aus, bevor Sie den Pool wieder hochfahren:
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte zum Sicherstellen der Funktionsweise von Pools

Sie sollten sich einige andere Faktoren ansehen, um sicherzustellen, dass Ihre Front-End-Pools funktionsfähig bleiben.

  - Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.

  - Wenn Sie eine Paarbeziehung zwischen diesem Pool und einem anderen Pool zum Zwecke der Notfallwiederherstellung konfigurieren, müssen Sie nach dem Erstellen dieser Beziehung sichergehen, dass in diesem Pool zu irgendeinem Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, damit Daten korrekt mit dem Sicherungspool synchronisiert werden. Weitere Informationen zu Pool Kopplung und Notfall Wiederherstellungsfeatures finden Sie unter [Planning for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Verbessern der Zuverlässigkeit von Pool Upgrades

Wenn Sie die Server in einem Front-End-Pool aktualisieren oder patchen müssen, befolgen Sie den in [Upgrade-oder Update-Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)angezeigten Workflow sowie die folgenden Richtlinien:

  - Wenn Sie für Upgrades von einer Upgrade-Domäne zu einer anderen wechseln (nach dem Workflow beim [Upgrade oder Aktualisieren der Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), verwenden Sie das Cmdlet **Get-cspoolupgradereadinessstate "** , und überprüfen Sie den Status bereit. Wenn Sie eine Wartezeit von 20 Minuten zwischen jeder Upgrade-Domäne hinzufügen, nachdem Sie "Ready" erreicht hat, werden die Upgrades zuverlässiger. Wenn es während dieser 20 Minuten **nicht** mehr verfügbar ist, starten Sie den 20-minütigen Timer neu. Außerdem können Sie das Cmdlet **Get-CsPoolFabricState** vor und nach dem Start des 20-minütigen Intervalls ausführen und sicherstellen, dass keine Änderungen an den Vorwahlen und an den Hilfsgruppen von Routinggruppen vorgenommen werden.

  - Wechseln Sie nicht zur nächsten Upgrade-Domäne, wenn einer der Server in der letzten gepatchten Upgrade-Domäne festgesteckt oder nicht neu gestartet wird. Dies gilt auch, wenn einer der Server innerhalb eines Upgrades nicht gestartet werden kann. Führen **Sie Get-CsPoolFabricState** aus, um sicherzustellen, dass alle Routinggruppen über eine primäre und mindestens eine sekundäre Gruppe verfügen. Dadurch wird bestätigt, ob alle Benutzer über Dienst verfügen.

  - Wenn einige Benutzer über Dienste verfügen und andere nicht, führen **Sie Get-CsPoolFabricState** mit der Option – verbose aus, um nach Routinggruppen mit fehlenden Replikaten zu suchen. Starten Sie den gesamten Pool nicht als ersten Schritt zur Problembehandlung neu. Weitere Informationen zu diesem Cmdlet finden Sie unter [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Stellen Sie sicher, dass alle Instanzen der Ereignisanzeige oder der System Monitor Fenster für Windows Fabric-Installationen/-Deinstallationen geschlossen sind.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Ändern der Konfiguration eines Front-End-Pools

Wenn Sie in einem Pool Front-End-Server hinzufügen oder entfernen und die neue Topologie dann veröffentlichen, halten Sie folgende Richtlinien ein:

  - Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.

  - Wenn während der Konfigurationsänderung der gesamte Pool heruntergefahren war, führen Sie nach dem Veröffentlichen der Topologie das folgende Cmdlet aus:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Wenn ein Front-End-Server ausfällt und über mehrere Tage hinweg wahrscheinlich nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, sobald er wieder verfügbar ist.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


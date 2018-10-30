---
title: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit'
TOCTitle: Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412996(v=OCS.15)
ms:contentKeyID: 49295851
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für Chat und Anwesenheit sind nur diese Komponenten erforderlich:

  - Die Front-End- oder Standard Edition-Server Ihrer Organisation. Instant Messaging- und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert.

  - Ein Gerät zum Lastenausgleich, wenn Sie einen Enterprise Edition- Front-End-Pool haben. Weitere Informationen finden Sie unter [Anforderungen an den Lastenausgleich für Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

## Planen der Bereitstellung von Front-End-Pools

In Lync Server 2013 hat sich die Architektur von Front-End-Pools geändert und diese Änderungen wirken sich auf die Planung und Verwaltung von Front-End-Poolss aus.

Wir empfehlen, dass alle Enterprise Edition- Front-End-Poolss mindestens drei Front-End-Server enthalten. In Lync Server wird in der Architektur von Front-End-Poolss ein Modell mit verteilten Systemen verwendet. Dabei werden die Daten der einzelnen Benutzer auf drei Front-End-Servern im Pool aufbewahrt. Weitere Informationen zu dieser neuen Architektur finden Sie unter [Topologieänderungen in Lync Server 2013](lync-server-2013-topology-changes.md).

Wenn Sie keine drei Enterprise Edition- Front-End-Server bereitstellen wollen und eine Notfallwiederherstellung brauchen, empfehlen wir Ihnen, Lync ServerStandard Edition zu verwenden und zwei Pools mit paarweiser Sicherungsbeziehung zu erstellen. Damit lässt sich die bestmögliche Lösung für die Notfallwiederherstellung mit nur zwei Servern realisieren. Weitere Informationen zu Topologien und Features für hohe Verfügbarkeit und Notfallwiederherstellung finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Planen der Verwaltung von Front-End-Pools

Befolgen Sie für Front-End-Pools die Richtlinien in diesem Abschnitt.

## Sicherstellen, dass Pools funktionsbereit sind

Mit dem neuen verteilten Modell für Front-End-Pools muss eine bestimmte Anzahl der Server eines Pools aktiv sein, damit der Pool funktioniert. Für einen Pool gibt es zwei Verlustmodi:

  - Quorumverlust auf Routinggruppenebene, der verursacht wird, wenn nicht genügend Replikatserver für eine bestimmte Routinggruppe vorhanden sind. Eine Routinggruppe ist eine Aggregation einer Sammlung von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: ein primäres und zwei sekundäre.

  - Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Seedserver im Pool aktiv sind.

## Quorumverlust auf Routinggruppenebene

Wenn Sie einen neuen Front-End-Pool zum ersten Mal starten, ist es wichtig, dass 85 % der Server aktiv sind, wie in der folgenden Tabelle gezeigt. Sind weniger Server aktiv, bleiben die Dienste möglicherweise im Startstatus hängen und der Pool wird nicht gestartet.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtzahl der Server im Pool</th>
<th>Anzahl der Server, die aktiv sein müssen, damit der Pool zum ersten Mal gestartet wird</th>
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
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>10</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10</p></td>
</tr>
</tbody>
</table>


Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorstehenden Tabelle gezeigt). Wenn diese Anzahl von Servern nicht gestartet werden kann (aber ausreichend Server gestartet werden können, damit kein Quoromverlust auf Poolebene auftritt), können Sie das Cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** verwenden, damit der Pool aus diesem Quorumverlust auf Routinggruppenebene wiederhergestellt werden und Fortschritte machen kann. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsPoolRegistrarState).


> [!NOTE]
> Da Lync Server die primäre SQL-Datenbank als Zeuge verwendet, fällt der gesamte Pool aus, wenn Sie die primäre Datenbank herunterfahren, zur Spiegelkopie wechseln und ausreichend Front-End-Server herunterfahren, sodass nicht genügend gemäß der vorstehenden Tabelle aktiv sind. Weitere Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=393672">Datenbank-Spiegelungszeuge</A>.



## Quorumverlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, darf kein Quorumverlust auf Poolebene bestehen. Unterschreitet die Anzahl der aktiven Server die in der folgenden Tabelle gezeigte Funktionsebene, halten die im Pool verbleibenden Server alle Lync Server-Dienste an. Beachten Sie, dass die in der folgenden Tabelle gezeigten Zahlen voraussetzen, dass die Back-End-Server im Pool aktiv sind.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtzahl der Front-End-Server in dem Pool</th>
<th>Anzahl der Server, die aktiv sein müssen, damit der Pool funktioniert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Beliebige 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Beliebige 3</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>Beliebige 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>Beliebige 4 der ersten 7 Server</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>Beliebige 5 der ersten 9 Server</p></td>
</tr>
</tbody>
</table>


In der vorstehenden Tabelle sind die "ersten Server" die Server, die, in chronologischer Reihenfolge, zuerst hochgefahren wurden, als der Pool zum ersten Mal gestartet wurde. Sie können diese Server mit dem Cmdlet **Get-CsComputer** mit der Option **–PoolFqdn** bestimmen. Mit diesem Cmdlet werden die Server in der Reihenfolge angezeigt, in der sie in der Topologie angezeigt werden. Dabei sind die Server im oberen Bereich der Liste die ersten Server.

## Front-End-Pools mit zwei Front-End-Servern

Das Bereitstellen eines Front-End-Pools, der nur zwei Front-End-Server enthält, wird nicht empfohlen. Sollten Sie einen solchen Pool aber doch einmal erstellen müssen, halten Sie sich an folgende Richtlinien:

  - Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den ausgefallenen Server so schnell wie möglich wieder in Betrieb zu bekommen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.

  - Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
      - Die bewährte Methode besteht darin, beide Front-End-Server gleichzeitig neu zu starten.
    
      - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
      - Falls Sie sie nicht in dieser Reihenfolge neu starten können, führen Sie das folgende Cmdlet aus, bevor Sie den Pool wieder hochfahren:
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

## Zusätzliche Schritte, um sicherzustellen, dass Pools funktionsbereit sind

Sie sollten auf eine Reihe anderer Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsbereit bleiben.

  - Wenn Sie das erste Mal Benutzer in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server aktiv sind.

  - Wenn Sie eine Paarbeziehung zwischen diesem Pool und einem anderen Pool zum Zwecke der Notfallwiederherstellung konfigurieren, müssen Sie nach dem Erstellen dieser Beziehung sichergehen, dass in diesem Pool zu irgendeinem Zeitpunkt drei Front-End-Server gleichzeitig ausgeführt werden, damit Daten korrekt mit dem Sicherungspool synchronisiert werden. Weitere Informationen zum Einrichten von Poolpaaren und zu Features für die Notfallwiederherstellung finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Verbessern der Zuverlässigkeit von Poolupgrades

Wenn Sie ein Upgrade durchführen oder die Server in einem Front-End-Pool patchen müssen, befolgen Sie den Workflow unter [Upgraden oder Updaten von Front-End-Servern in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) und die folgenden Richtlinien:

  - Wenn Sie bei Upgrades von einer Upgradedomäne zu einer anderen wechseln (beim Befolgen des Workflows unter [Upgraden oder Updaten von Front-End-Servern in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), verwenden Sie das Cmdlet **Get-CsPoolUpgradeReadinessState** und prüfen, ob der Zustand "Bereit" ist. Wenn Sie zwischen jeder Upgradedomäne zusätzliche 20 Minuten warten, nachdem der Zustand "Bereit" erreicht wurde, werden die Upgrades zuverlässiger. Falls während dieser 20 Minuten der Zustand zu **Nicht bereit** wechselt, starten Sie die 20-minütige Wartezeit erneut. Sie können außerdem vor und nach Beginn des 20-Minuten-Intervalls das Cmdlet **Get-CsPoolFabricState** ausführen und sicherstellen, dass keine Änderungen an den primären und sekundären Routinggruppen erfolgt sind.

  - Wechseln Sie nicht zur nächsten Upgradedomäne, wenn einer der Server in der zuletzt gepatchten Upgradedomäne hängen bleibt oder nicht neu gestartet wird. Dies gilt auch, wenn einer der Server innerhalb eines Upgrades nicht gestartet werden kann. Führen Sie **Get-CsPoolFabricState** aus, um sicherzustellen, dass alle Routinggruppen über einen primären und mindestens einen sekundären Server verfügen. Damit wird bestätigt, ob für alle Benutzer ein Dienst verfügbar ist.

  - Wenn einige Benutzer über einen Dienst verfügen und andere nicht, führen Sie **Get-CsPoolFabricState** mit der Option "–Verbose" aus, um zu prüfen, ob Routinggruppen vorhanden sind, denen Replikate fehlen. Starten Sie nicht den gesamten Pool als ersten Problembehandlungsschritt neu. Weitere Informationen zu diesem Cmdlet finden Sie unter [Get-CsPoolFabricState](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPoolFabricState).

  - Stellen Sie sicher, dass alle Instanzen der Ereignisanzeige und der Leistungsüberwachung beim Installieren/Deinstallieren von Windows Fabric geschlossen sind.

## Ändern der Konfiguration eines Front-End-Pools

Wenn Sie in einem Pool Front-End-Server hinzufügen oder entfernen und die neue Topologie dann veröffentlichen, halten Sie folgende Richtlinien ein:

  - Nachdem die neue Topologie veröffentlicht worden ist, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.

  - Wenn während der Konfigurationsänderung der gesamte Pool heruntergefahren war, führen Sie nach dem Veröffentlichen der Topologie das folgende Cmdlet aus:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Wenn ein Front-End-Server ausfällt und über mehrere Tage hinweg wahrscheinlich nicht ersetzt werden kann, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server der Topologie hinzu, sobald er wieder verfügbar ist.


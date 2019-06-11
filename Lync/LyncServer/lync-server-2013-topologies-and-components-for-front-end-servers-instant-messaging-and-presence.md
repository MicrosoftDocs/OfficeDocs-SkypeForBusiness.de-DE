---
title: 'Lync Server 2013: Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologien und Komponenten für Front-End-Server, Chat und Anwesenheit in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-10-24_

Für Chat und Anwesenheit sind nur diese Komponenten erforderlich:

  - Die Front-End-Server Ihrer Organisation oder Standard Edition-Server. Chat und Anwesenheitsfunktionen sind auf diesen Servern immer aktiviert.

  - Ein Lastenausgleich, wenn Sie einen Enterprise Edition-Front-End-Pool haben. Weitere Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planen der Bereitstellung von Front-End-Pools

In lync Server 2013 hat sich die Architektur des Front-End-Pools geändert, und diese Änderungen beeinflussen, wie Sie Ihre Front-End-Pools planen und verwalten sollten.

Wir empfehlen, dass alle Ihre Enterprise Edition-Front-End-Pools mindestens drei Front-End-Server enthalten. In lync Server verwendet die Architektur der Front-End-Pools ein Modell mit verteilten Systemen, wobei die Daten jedes Benutzers auf drei Front-End-Servern im Pool aufbewahrt werden. Weitere Informationen zu dieser neuen Architektur finden Sie unter [Topologie-Änderungen in lync Server 2013](lync-server-2013-topology-changes.md).

Wenn Sie keine drei Enterprise Edition-Front-End-Server bereitstellen möchten und eine Disaster Recovery wünschen, empfehlen wir die Verwendung von lync Server Standard Edition und das Erstellen von zwei Pools mit einer gekoppelten Sicherungsbeziehung. Dadurch wird eine Disaster Recovery-Lösung mit nur zwei Servern bereitgestellt. Weitere Informationen zu Hochverfügbarkeits-und Disaster Recovery-Topologien und-Features finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planen der Verwaltung von Front-End-Pools

Befolgen Sie für Front-End-Pools die Richtlinien in diesem Abschnitt.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Sicherstellen, dass Pools funktionsfähig sind

Mit dem neuen verteilten Modell für Front-End-Pools müssen bestimmte Nummern der Server eines Pools ausgeführt werden, damit der Pool funktioniert. Es gibt zwei Verlust Modi für einen Pool

  - Quorumverlust auf Routinggruppenebene, wenn nicht genügend Replikatserver für eine bestimmte Routinggruppe vorhanden sind. Eine Routinggruppe ist eine Aggregation einer Gruppe von Benutzern, die im Pool verwaltet werden. Jede Routinggruppe verfügt über drei Replikate im Pool: eine primäre und zwei Sekundär Gruppen.

  - Quorumverlust auf Poolebene, der verursacht wird, wenn nicht genügend Seedserver im Pool aktiv sind.

<div>

## <a name="routing-group-level-quorum-loss"></a>Quorumverlust auf Routinggruppenebene

Wenn Sie einen neuen Front-End-Pool zum ersten Mal starten, ist es wichtig, dass wie in der folgenden Tabelle gezeigt 85 % der Server aktiv sind. Wenn weniger Server aktiv sind, bleiben die Dienste möglicherweise im Startstatus hängen und der Pool wird nicht gestartet.


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


Bei jedem nachfolgenden Start des Pools sollten 85 % der Server gestartet werden (wie in der vorstehenden Tabelle gezeigt). Wenn diese Anzahl von Servern nicht gestartet werden kann (aber ausreichend Server gestartet werden können, damit kein Quorumverlust auf Poolebene auftritt), können Sie das Cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** verwenden, damit der Pool aus diesem Quorumverlust auf Routinggruppenebene wiederhergestellt werden und sich aufbauen kann. Weitere Informationen zur Verwendung dieses Cmdlets finden Sie unter [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Da lync Server die primäre SQL-Datenbank als Zeuge verwendet, wenn Sie die primäre Datenbank Herunterfahren und zur Spiegelungskopie wechseln und genügend Front-End-Server herunterfahren, sodass nicht genügend entsprechend der vorhergehenden Tabelle ausgeführt wird, wird der gesamte Pool heruntergefahren. Weitere Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/?linkid=393672">Daten Bank Spiegelungs Zeuge</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Quorumverlust auf Poolebene

Damit ein Front-End-Pool überhaupt funktioniert, kann er keinen Quorum Verlust auf Poolebene aufweisen. Wenn die Anzahl der ausgeführten Server unter die Funktionsebene fällt, wie in der folgenden Tabelle dargestellt, beenden die restlichen Server im Pool alle lync Server-Dienste. Beachten Sie, dass die Zahlen in der folgenden Tabelle davon ausgehen, dass die Back-End-Server im Pool ausgeführt werden.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gesamtzahl der Front-End-Server im Pool</th>
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


In der vorstehenden Tabelle sind die "ersten Server" die Server, die in chronologischer Reihenfolge beim ersten Start des Pools aufgeholt wurden. Um diese Server zu ermitteln, können Sie das Cmdlet " **Get-CsComputer** " mit der Option " **– PoolFqdn** " verwenden. Dieses Cmdlet zeigt die Server in der Reihenfolge an, in der Sie in der Topologie angezeigt werden, und die oben in der Liste sind die ersten Server.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Front-End-Pools mit zwei Front-End-Servern

Wir empfehlen nicht die Bereitstellungeines Front-End-Pools, in dem nur zwei Front-End-Server enthalten sind. Wenn Sie einen solchen Pool überhaupt bereitstellen müssen, befolgen Sie diese Richtlinien:

  - Wenn einer der beiden Front-End-Server ausfällt, sollten Sie versuchen, den fehlerhaften Server so schnell wie möglich wieder aufzunehmen. Entsprechend sollten Sie, wenn Sie einen der beiden Server upgraden müssen, diesen Server so bald wie möglich nach Abschluss des Upgrades wieder online schalten.

  - Falls Sie aus irgendeinem Grund beide Server gleichzeitig herunterfahren müssen, führen Sie nach Beendigung der Downtime für den Pool folgende Schritte durch:
    
      - Die bewährte Vorgehensweise besteht darin, beide Front-End-Server gleichzeitig neu zu starten.
    
      - Ist dies nicht möglich, sollten Sie sie in der umgekehrten Reihenfolge wieder hochfahren, in der sie heruntergefahren wurden.
    
      - Wenn Sie Sie nicht in dieser Reihenfolge sichern können, verwenden Sie das folgende Cmdlet, bevor Sie den Pool sichern:.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Zusätzliche Schritte, um sicherzustellen, dass Pools funktionsfähig sind

Sie sollten auf eine Reihe anderer Faktoren achten, um sicherzustellen, dass Ihre Front-End-Pools funktionsbereit bleiben.

  - Wenn Sie Benutzer zum ersten Mal in den Pool verschieben, stellen Sie sicher, dass mindestens drei der Front-End-Server ausgeführt werden.

  - Wenn Sie eine Kopplungs Beziehung zwischen diesem Pool und einem anderen Pool für Disaster Recovery-Zwecke einrichten, müssen Sie nach dem Einrichten dieser Beziehung sicherstellen, dass dieser Pool drei Front-End-Server hat, die zu einem bestimmten Zeitpunkt gleichzeitig ausgeführt werden, damit Sie ordnungsgemäß synchronisiert werden. Daten mit dem Sicherungspool. Weitere Informationen zu Pool-Kopplungs-und Disaster Recovery-Features finden Sie unter [Planen von Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Verbessern der Zuverlässigkeit von Pool-Upgrades

Wenn Sie die Server in einem Front-End-Pool aktualisieren oder patchen müssen, folgen Sie dem Workflow, der unter [Upgrade-oder Update-Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)angezeigt wird, und den folgenden Richtlinien:

  - Wenn Sie für Upgrades von einer Upgrade-Domäne zu einem anderen wechseln (nach dem Workflow bei der [Aktualisierung oder Aktualisierung der Front-End-Server in lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), verwenden Sie das Cmdlet **Get-CsPoolUpgradeReadinessState** , und überprüfen Sie den Status bereit. Das Hinzufügen eines 20-minütigen Wartens zwischen jeder Upgrade-Domäne, nachdem es "Ready" erreicht hat, macht die Upgrades zuverlässiger. Wenn es während dieser 20 Minuten **nicht bereit** ist, starten Sie den 20-minütigen Timer erneut. Darüber hinaus können Sie das Cmdlet " **Get-CsPoolFabricState** " vor und nach dem Start des 20-minütigen Intervalls ausführen und sicherstellen, dass keine Änderungen an den Vorwahlen und Sekundär Personen von Routinggruppen vorgenommen wurden.

  - Wechseln Sie nicht zur nächsten Upgrade-Domäne, wenn einer der Server in der letzten gepatchten Upgrade-Domäne hängen bleibt oder nicht neu gestartet wird. Dies gilt auch, wenn einer der Server in einem Upgrade nicht gestartet werden kann. Führen **Sie Get-CsPoolFabricState** aus, um sicherzustellen, dass alle Routinggruppen über eine primäre und mindestens eine sekundäre Gruppe verfügen. Dadurch wird bestätigt, ob alle Benutzer über einen Dienst verfügen.

  - Wenn einige Benutzer über einen Dienst verfügen und andere dies nicht tun, führen **Sie Get-CsPoolFabricState** mit der Option – verbose aus, um nach Routinggruppen zu suchen, die fehlende Replikate aufweisen. Starten Sie den gesamten Pool nicht als ersten Schritt zur Problembehandlung neu. Weitere Informationen zu diesem Cmdlet finden Sie unter [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Stellen Sie sicher, dass alle Instanzen der Ereignisanzeige oder des Leistungsmonitors für Windows Fabric-Installationen/-Deinstallationen geschlossen sind.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Ändern der Konfiguration eines Front-End-Pools

Wenn Sie einem Pool Front-End-Server hinzufügen oder aus dem Pool entfernen und dann die neue Topologie veröffentlichen, befolgen Sie diese Richtlinien:

  - Nachdem die neue Topologie veröffentlicht wurde, müssen Sie jeden Front-End-Server im Pool neu starten. Starten Sie die Server einen nach dem anderen neu.

  - Wenn der gesamte Pool während der Konfigurationsänderung inaktiv war, führen Sie nach der Veröffentlichung der neuen Topologie das folgende Cmdlet aus:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Wenn ein Front-End-Server ausfällt und für ein paar Tage oder mehr wahrscheinlich nicht ersetzt wird, entfernen Sie den Server aus der Topologie. Fügen Sie den neuen Front-End-Server zur Topologie hinzu, wenn er wieder verfügbar ist.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


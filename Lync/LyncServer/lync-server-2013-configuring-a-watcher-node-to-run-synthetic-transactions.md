---
title: 'Lync Server 2013: Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107803caba66c19ec852d4c077e69aec5f7cf5ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Konfigurieren eines Watcher-Knotens zum Ausführen synthetischer Transaktionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-07_

Nachdem die System Center-Agentdateien installiert wurden, müssen Sie im nächsten Schritt den Watcher-Knoten selbst konfigurieren. Die Schritte zum Konfigurieren eines Watcher-Knotens hängen davon ab, ob sich der Computer mit dem Watcher-Knoten innerhalb oder außerhalb Ihrs Umkreisnetzwerks befindet.

Beim Konfigurieren eines Watcher-Knotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. Lync Server 2013 können Sie eine von zwei Authentifizierungsmethoden auswählen: vertrauenswürdige Server-oder Anmelde Informations Authentifizierung. Die Unterschiede zwischen diesen beiden Methoden werden in der folgenden Tabelle erläutert:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Konfiguration</th>
<th>Beschreibung</th>
<th>Unterstützte Standorte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vertrauenswürdiger Server</p></td>
<td><p>Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.</p>
<p>Diese Methode eignet sich für Administratoren, die es vorziehen, ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Watcher-Knoten zu verwalten.</p></td>
<td><p>Innerhalb des Unternehmens.</p>
<p>Beachten Sie, dass sich bei dieser Methode der Watcher-Knoten in derselben Domäne wie die überwachten Pools befinden muss. Falls sich der Watcher-Knoten und die überwachten Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Authentifizierung mit Anmeldeinformationen.</p></td>
</tr>
<tr class="even">
<td><p>Authentifizierung mit Anmeldeinformationen</p></td>
<td><p>Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Watcher-Knoten gespeichert.</p>
<p>Dieser Modus erfordert einen höheren Kennwortverwaltungsaufwand, ist aber die einzige Option für Watcher-Knoten außerhalb des Unternehmens. Diese Watcher-Knoten können nicht als Endpunkt, der bezüglich der Authentifizierung vertrauenswürdig ist, betrachtet werden.</p></td>
<td><p>Außerhalb des Unternehmens.</p>
<p>Innerhalb des Unternehmens.</p></td>
</tr>
</tbody>
</table>


Sie sollten auch überprüfen, ob Ihre Firewall eingehende Regeln für sowohl MonitoringHost. exe als auch PowerShell. exe aufweist. Wenn diese Prozesse durch die Firewall blockiert werden, tritt bei ihren synthetischen Transaktionen ein Fehler 504 (Servertimeout) auf.

</div>

<span> </span>

</div>

</div>

</div>


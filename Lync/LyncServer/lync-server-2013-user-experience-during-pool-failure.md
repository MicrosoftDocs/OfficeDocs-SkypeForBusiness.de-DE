---
title: Lync Server 2013 Benutzererfahrung beim Pool Ausfall
description: Lync Server 2013 Benutzererfahrung beim Pool Ausfall.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569791"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Benutzererfahrung beim Pool Fehler in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Wenn für einen Pool ein Failover vorgenommen wurde, werden alle Benutzer des betroffenen Pools gezwungen, sich abzumelden und sich beim Sicherungspool anzumelden. Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus. Im Ausfall Sicherheitsmodus können Benutzer keine Aufgaben ausführen, die eine beständige Änderung auf lync Server verursachen würden, beispielsweise das Hinzufügen eines Kontakts. Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.

Sämtliche Sitzungen, über die ein Benutzer verfügt, während ein Pool ausfällt, werden unterbrochen, und der Benutzer muss diese Sitzungen wiederherstellen, um nach dem Failover fortzufahren.

Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Home-Pool wiederhergestellt wird, kann der Administrator über ein Failback diese Benutzer wieder über ihren ursprünglichen Home-Pool verarbeiten.

Hinweis in lync 2013 wird die Datenbank des Standort Informationsservers nicht in den Sicherungspool repliziert. Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.

<div>

## <a name="user-experience-during-failover"></a>Benutzerfreundlichkeit während des Failovers

Befindet sich ein Benutzer in einem ausfallenden Pool, wird der Benutzer abgemeldet. Sämtliche Peer-zu-Peer-Sitzungen, an denen der Benutzer teilgenommen hat, werden abgebrochen, wie auch die von diesem Benutzer organisierten Konferenzen. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Nur dann sind Benutzer in der Lage, neue Sitzungen zu erstellen oder vorherige Sitzungen wiederherzustellen.

</div>

<div>

## <a name="user-experience-during-failback"></a>Benutzerfreundlichkeit während des Failbacks

Pool-Failbacks können auftreten, während der betroffene Benutzer an einem Sicherungspool angemeldet ist und der Benutzer während des Failbacks weiterhin angemeldet ist und arbeitet. Hinweis: Es dauert mehrere Minuten, bis der Failback-Prozess abgeschlossen ist.  Zur Orientierung: Erwartungsgemäß dauert ein Pool mit 20.000 Benutzern bis zu 60 Minuten.

Die folgenden Tabellen zeigen ausführlichere Informationen darüber, wie ein Benutzer mit einem lync 2013-Client oder einem Microsoft lync 2010-Client während und nach dem Failback betroffen ist und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit diesem interagieren, der zurückgeschlagen wird. Benutzer mit Microsoft Office Communicator 2007 R2 Clients können sich erst anmelden, wenn der Front-End-Pool vollständig zurückgetreten ist.)

Der Begriff *betroffener Benutzer* bezieht sich auf sämtliche Benutzer, bei denen beim Home-Pool ein Failover auftrat und die daher vom Sicherungspool verarbeitet werden. Definitionsgemäß sind sämtliche Benutzer, die ursprünglich auf dem Sicherungspool verwaltet wurden, keine betroffenen Benutzer.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Benutzerfreundlichkeit für einen betroffenen Benutzer für einen in einem Failback befindlichen Pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzerstatus oder -aufgabe</th>
<th>Während des Failbacks</th>
<th>Nach abgeschlossenem Failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Benutzerstatus des bereits angemeldeten Benutzers</p></td>
<td><p>Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.</p></td>
<td><p>Benutzer bleibt angemeldet und wechselt in den regulären Modus.</p></td>
</tr>
<tr class="even">
<td><p>Neuer Benutzer meldet sich an</p></td>
<td><p>Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.</p></td>
<td><p>Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.</p></td>
</tr>
<tr class="odd">
<td><p>Vom betroffenen Benutzer organisierte laufende Konferenz</p></td>
<td><p>Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.</p></td>
<td><p>Alle Modalitäten funktionieren jetzt. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</p></td>
</tr>
<tr class="even">
<td><p>Vom nicht betroffenen Benutzer organisierte laufende Konferenz</p></td>
<td><p>Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist darauf beschränkt, was er im Ausfallsicherheitsmodus ausführen kann.</p></td>
<td><p>Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.</p></td>
</tr>
<tr class="odd">
<td><p>Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen</p></td>
<td><p>Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.</p></td>
<td><p>Für alle Modalitäten verfügbar.</p></td>
</tr>
<tr class="even">
<td><p>Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird</p></td>
<td><p>Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.</p></td>
<td><p>Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus, und Anwesenheitsänderungen werden nun reflektiert.</p></td>
</tr>
<tr class="odd">
<td><p>Verfügbarkeit von Kontaktlisten und Adressbuchdienst</p></td>
<td><p>Nicht verfügbar</p></td>
<td><p>Available</p></td>
</tr>
<tr class="even">
<td><p>Alle Peer-zu-Peer-Sitzungen und -modalitäten</p></td>
<td><p>Available</p></td>
<td><p>Available</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Benutzerfreundlichkeit für einen in einem nicht betroffenen Pool verwalteten Benutzer während eines Failbacks eines anderen Pools

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzeraufgabe</th>
<th>Während des Failbacks</th>
<th>Nach abgeschlossenem Failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anwesenheitsinformationen des betroffenen Benutzers anzeigen</p></td>
<td><p>Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.</p></td>
<td><p>In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.</p></td>
</tr>
<tr class="even">
<td><p>Von betroffenen Benutzern organisierte laufende Konferenzen</p></td>
<td><p>Alle Modalitäten der Konferenz werden abgebrochen</p></td>
<td><p>Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</p></td>
</tr>
<tr class="odd">
<td><p>Von nicht betroffenen Benutzern organisierte laufende Konferenzen</p></td>
<td><p>Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.</p></td>
<td><p>Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.</p></td>
</tr>
<tr class="even">
<td><p>Alle Peer-zu-Peer-Sitzungen und -modalitäten</p></td>
<td><p>Available</p></td>
<td><p>Available</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


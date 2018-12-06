---
title: 'Lync Server 2013: Abläufe für Benutzer während des Ausfalls eines Pools'
TOCTitle: Abläufe für Benutzer während des Ausfalls eines Pools
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205184(v=OCS.15)
ms:contentKeyID: 49295128
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Abläufe für Benutzer während des Ausfalls eines Pools in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn für einen Pool ein Failover vorgenommen wurde, werden alle Benutzer des betroffenen Pools gezwungen, sich abzumelden und sich beim Sicherungspool anzumelden. Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus. Im Ausfallsicherheitsmodus können Benutzer keine Aufgaben ausführen, die eine dauerhafte Änderung auf Lync Server zur Folge hätte, beispielsweise das Hinzufügen eines Kontakts. Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.

Sämtliche Sitzungen, über die ein Benutzer verfügt, während ein Pool ausfällt, werden unterbrochen, und der Benutzer muss diese Sitzungen wiederherstellen, um nach dem Failover fortzufahren.

Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Home-Pool wiederhergestellt wird, kann der Administrator über ein Failback diese Benutzer wieder über ihren ursprünglichen Home-Pool verarbeiten.

Hinweis: In Lync 2013 wird die Location Information Server-Datenbank nicht in den Sicherungspool repliziert. Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.

## Benutzerfreundlichkeit während des Failovers

Befindet sich ein Benutzer in einem ausfallenden Pool, wird der Benutzer abgemeldet. Sämtliche Peer-zu-Peer-Sitzungen, an denen der Benutzer teilgenommen hat, werden abgebrochen, wie auch die von diesem Benutzer organisierten Konferenzen. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Nur dann sind Benutzer in der Lage, neue Sitzungen zu erstellen oder vorherige Sitzungen wiederherzustellen.

## Benutzerfreundlichkeit während des Failbacks

Pool-Failbacks können auftreten, während der betroffene Benutzer an einem Sicherungspool angemeldet ist und der Benutzer während des Failbacks weiterhin angemeldet ist und arbeitet. Hinweis: Es dauert mehrere Minuten, bis der Failback-Prozess abgeschlossen ist.  Zur Orientierung: Erwartungsgemäß dauert ein Pool mit 20.000 Benutzern bis zu 60 Minuten.

In den folgenden Tabellen sind detailliertere Informationen darüber enthalten, wie ein Benutzer mit einem Lync 2013-Client oder einem Microsoft Lync 2010-Client bei und nach einem Failback betroffen ist und auch wie Benutzer in anderen Pools einen Benutzer, für dessen Pool ein Failback ausgeführt wird, sehen und mit diesem interagieren. Benutzer mit Microsoft Office Communicator 2007 R2-Clients können sich nicht anmelden, bis für den Front-End-Pool ein vollständiges Failback ausgeführt wurde.

Der Begriff *betroffener Benutzer* bezieht sich auf sämtliche Benutzer, bei denen beim Home-Pool ein Failover auftrat und die daher vom Sicherungspool verarbeitet werden. Definitionsgemäß sind sämtliche Benutzer, die ursprünglich auf dem Sicherungspool verwaltet wurden, keine betroffenen Benutzer.

### Benutzerfreundlichkeit für einen betroffenen Benutzer für einen in einem Failback befindlichen Pool

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
<td><p>Von betroffenen Benutzern organisierte laufende Konferenzen</p></td>
<td><p>Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.</p></td>
<td><p>Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.</p></td>
</tr>
<tr class="even">
<td><p>Von nicht betroffenen Benutzern organisierte laufende Konferenzen</p></td>
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
<td><p>Verfügbar</p></td>
</tr>
<tr class="even">
<td><p>Alle Peer-zu-Peer-Sitzungen und -modalitäten</p></td>
<td><p>Verfügbar</p></td>
<td><p>Verfügbar</p></td>
</tr>
</tbody>
</table>


### Benutzerfreundlichkeit für einen in einem nicht betroffenen Pool verwalteten Benutzer während eines Failbacks eines anderen Pools

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
<td><p>Verfügbar</p></td>
<td><p>Verfügbar</p></td>
</tr>
</tbody>
</table>


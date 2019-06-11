---
title: Lync Server 2013-Benutzererfahrung beim Pool Fehler
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca33dc8f77ac697b7eea9cc89fee9aa401318566
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Benutzererfahrung beim Pool Fehler in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Wenn ein Pool fehlerhaft ist, müssen sich alle Benutzer des betroffenen Pools abmelden und sich dann beim Sicherungspool anmelden. Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus. Im Resilienz-Modus können Benutzer keine Aufgaben ausführen, die zu einer dauerhaften Änderung auf lync Server führen, wie etwa das Hinzufügen eines Kontakts. Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.

Alle Sitzungen, die ein Benutzer hat, wenn der Pool ausfällt, werden gestört, und der Benutzer muss diese Sitzungen nach einem Failover erneut einrichten, um fortzufahren.

Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Home-Pool wiederhergestellt wird, kann der Administrator diese Benutzer zurückschlagen, um von Ihrem ursprünglichen privaten Pool gewartet zu werden.

Hinweis in lync 2013 wird die Standort Informations Server-Datenbank nicht in den Sicherungspool repliziert. Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.

<div>

## <a name="user-experience-during-failover"></a>Benutzerfreundlichkeit während eines Failovers

Wenn sich ein Benutzer in einem Pool befindet, der fehlschlägt, wird der Benutzer abgemeldet. Jede Peer-to-Peer-Sitzung, an der der Benutzer teilgenommen hat, wird beendet, ebenso wie Konferenzen, die von diesem Benutzer organisiert werden. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Nur dann kann der Benutzer neue Sitzungen einrichten oder frühere Sitzungen wiederherstellen.

</div>

<div>

## <a name="user-experience-during-failback"></a>Benutzerfreundlichkeit während des Failback

Pool-Failbacks können auftreten, wenn der betroffene Benutzer während des Failbacks weiterhin an einem Sicherungspool angemeldet ist und arbeitet. Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nimmt.Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.

In den folgenden Tabellen werden weitere Details dazu angezeigt, wie ein Benutzer mit einem lync 2013-Client oder einem Microsoft lync 2010-Client während und nach dem Failback betroffen ist, und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit ihm interagieren, der wieder fehlerhaft ist. Benutzer mit Microsoft Office Communicator 2007 R2-Clients können sich erst anmelden, wenn der Front-End-Pool komplett Fehler zurück ist.)

Der Begriff *betroffener Benutzer* bezieht sich auf sämtliche Benutzer, bei denen ein Failover im Home-Pool aufgetreten ist und die daher vom Sicherungspool verarbeitet werden. Definitionsgemäß ist jeder Benutzer, der ursprünglich im Sicherungspool beheimatet ist, kein betroffener Benutzer.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Benutzererfahrung eines betroffenen Benutzers bei einem Pool in Failback

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
<td><p>Neuer Benutzer meldet sich an.</p></td>
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
<td><p>Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist auf die Aktionen beschränkt, die er im Ausfallsicherheitsmodus ausführen kann.</p></td>
<td><p>Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.</p></td>
</tr>
<tr class="odd">
<td><p>Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen</p></td>
<td><p>Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.</p></td>
<td><p>Für alle Modalitäten verfügbar.</p></td>
</tr>
<tr class="even">
<td><p>Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird</p></td>
<td><p>Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.</p></td>
<td><p>Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus. Anwesenheitsänderungen werden nun reflektiert.</p></td>
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


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Benutzererfahrung mit einem verwalteten Benutzer in einem nicht betroffenen Pool während eines Failbacks eines anderen Pools

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
<td><p>Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.</p></td>
<td><p>Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.</p></td>
</tr>
<tr class="even">
<td><p>Alle Peer-zu-Peer-Sitzungen und -modalitäten</p></td>
<td><p>Verfügbar</p></td>
<td><p>Verfügbar</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: UCWA-Ereignisse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>UCWA-Ereignisse in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 verwendet das Unified Communications Web API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontakt suchen bis zur Aktualisierung der Anwesenheitsinformationen für mobile Clients.

In UCWA werden Datensätze des Betriebsverhaltens als Ereignistypen Information, Warnung und Fehler geschrieben. In der folgenden Tabelle werden die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ereignis-ID</th>
<th>Ereignistyp</th>
<th>Zusammenfassung</th>
<th>Ursache und Lösung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Informations</p></td>
<td><p>UCWA initialisiert</p></td>
<td><p>Nicht zutreffend</p>
<p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Fehler</p></td>
<td><p>UCWA bei der Initialisierung ist eine unerwartete Ausnahme aufgetreten</p></td>
<td><p>Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.</p>
<p>Überprüfen Sie die Ausnahmedetails im zugeordneten Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Fehler</p></td>
<td><p>UCWA hat eine nicht behandelte Ausnahme gefunden</p></td>
<td><p>Eine unbehandelte Ausnahme ist aufgetreten.</p>
<p>Starten Sie den Server neu. Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Fehler</p></td>
<td><p>Zugriff auf Exchange für HD-Foto nicht möglich</p></td>
<td><p>Die Verbindung mit Exchange ist nicht verfügbar.</p>
<p>Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Zugriff auf Exchange für HD-Foto</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Fehler</p></td>
<td><p>Zugriff auf Exchange für Kontakt Suche nicht möglich</p></td>
<td><p>Die Verbindung mit Exchange ist nicht verfügbar.</p>
<p>Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Suchen des Kontakts in Exchange</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Warnung</p></td>
<td><p>Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</p></td>
<td><p>Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</p>
<p>Überprüfen der Clients auf unnötige Abonnements</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Warnung</p></td>
<td><p>Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</p></td>
<td><p>Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</p>
<p>Überprüfen der Clients auf unnötige Abonnements</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Fehler</p></td>
<td><p>Inband-Daten können nicht abgerufen werden</p></td>
<td><p>Inband-Daten können nicht abgerufen werden</p>
<p>Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Fehler</p></td>
<td><p>Anwesenheit kann nicht abonniert werden</p></td>
<td><p>Anwesenheit kann nicht abonniert werden</p>
<p>Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Fehler</p></td>
<td><p>Fehler beim Registrieren des Endpunkts</p></td>
<td><p>Fehler beim Registrieren des Endpunkts</p>
<p>Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Fehler</p></td>
<td><p>IM MCU ist nicht verfügbar</p></td>
<td><p>IM MCU ist nicht verfügbar</p>
<p>Überprüfen, ob im MCU ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Sofortnachrichten-MCU</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Fehler</p></td>
<td><p>AV MCU ist nicht verfügbar</p></td>
<td><p>AV MCU ist nicht verfügbar</p>
<p>Prüfen, ob AV MCU ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AV MCU</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Fehler</p></td>
<td><p>Da MCU nicht verfügbar ist</p></td>
<td><p>Da MCU nicht verfügbar ist</p>
<p>Anzeigen, ob as MCU ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AS MCU</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Fehler</p></td>
<td><p>Data MCU ist nicht verfügbar</p></td>
<td><p>Data MCU ist nicht verfügbar</p>
<p>Überprüfen, ob Data MCU ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Data MCU</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Fehler</p></td>
<td><p>Teilnahme an Chat MCU nicht möglich</p></td>
<td><p>Teilnahme an Chat MCU nicht möglich</p>
<p>Überprüfen, ob im MCU ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Fehler</p></td>
<td><p>Beitritt zur AV MCU nicht möglich</p></td>
<td><p>Beitritt zur AV MCU nicht möglich</p>
<p>Prüfen, ob AV MCU ausgeführt wird</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Fehler</p></td>
<td><p>Beitritt zur MCU nicht möglich</p></td>
<td><p>Beitritt zur MCU nicht möglich</p>
<p>Anzeigen, ob as MCU ausgeführt wird</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Fehler</p></td>
<td><p>Beitreten zu Daten-MCU nicht möglich</p></td>
<td><p>Beitreten zu Daten-MCU nicht möglich</p>
<p>Überprüfen, ob Data MCU ausgeführt wird</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Fehler</p></td>
<td><p>Zugriff auf Active Directory für Foto nicht möglich</p></td>
<td><p>Die Verbindung mit Active Directory ist nicht verfügbar.</p>
<p>Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Informations</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Zugriff auf Active Directory für Foto</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Warnung</p></td>
<td><p>Deserialisierung nicht möglich</p></td>
<td><p>Deserialisierung nicht möglich</p>
<p>Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


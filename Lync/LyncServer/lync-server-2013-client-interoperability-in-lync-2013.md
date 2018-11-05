---
title: 'Lync Server 2013: Clientinteroperabilität in Lync 2013'
TOCTitle: Clientinteroperabilität in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204672(v=OCS.15)
ms:contentKeyID: 49293187
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clientinteroperabilität in Lync 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-03-04_

In diesem Thema wird die Fähigkeit von Microsoft Lync Server 2013-Clients beschrieben, parallel mit Clients aus früheren Versionen Lync Server und Office Communications Server ausgeführt zu werden und mit diesen zu interagieren.

## Server- und Clientkompatibilität

Die folgende Tabelle zeigt die unterstützten Kombinationen von Clientversionen und Serverversionen. Diese Tabelle gibt an, ob die Anmeldung unterstützt wird, wenn der Client versucht, eine Verbindung mit dem angegebenen Server herzustellen. Lync Server 2013 unterstützt die früheren Clientversionen. Außerdem unterstützt Lync Server 2010 im Gegensatz zu früheren Versionen die neuen Lync 2013-Clients. Dadurch können Organisationen, die ein Upgrade von Lync Server 2010 durchführen, neue Clients unabhängig von Lync Server-Upgrades einführen.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt5</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010-Vermittlung</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010-Gruppenchat</p></td>
<td><p>Unterstützt1</p></td>
<td><p>Unterstützt2</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010-Teilnehmer</p></td>
<td><p>Nicht unterstützt3</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperabel4</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2-Vermittlung</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Windows Store-App für Lync</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
</tbody>
</table>


1Ausführliche Informationen finden Sie unter [Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010 war die Gruppenchatfunktionalität über den Gruppenchatserver verfügbar, eine eine vertrauenswürdige Anwendung eines Drittanbieters für Lync Server 2010. Lync 2013-Clients sind nicht mit Lync Server 2010-Gruppenchat kompatibel.

3Lync Web App 2013 bietet jetzt eine umfassende Besprechungsfunktionalität mit Computeraudio- und Videofunktionen und wird als Ersatz für Lync 2010-Teilnehmer angesehen. Lync 2010-Teilnehmer stellt nur dann eine Verbindung mit Lync Server 2013 her, wenn Sie mit einem nicht unterstützten Browser (Internet Explorer 6 oder Internet Explorer 7) und Windows XP arbeiten.

4Die Anwesenheits- und Chatfeatures in Office Communicator 2007 R2 sind mit Lync Server 2013 kompatibel, nicht jedoch die Konferenzfeatures. Während der Migration von Office Communications Server 2007 R2 eignet sich Office Communicator 2007 R2 für Anwesenheits- und Chatinteroperabilität, Benutzer sollten jedoch Lync Web App 2013 verwenden, um an Lync Server 2013-Besprechungen teilzunehmen.

5 Informationen zu Einschränkungen finden Sie unter „Unterstützung von Konferenzfeatures für Lync 2013 Clients in Lync Server 2010-Besprechungen“ später in diesem Thema.

## Interoperabilität zwischen Clients

Ab der Version Lync Server 2013 können verschiedene Clientversionen sowohl in Peer-zu-Peer- und Konferenzszenarien nahtlos interagieren. In diesem Abschnitt wird die Verfügbarkeit von Features behandelt, wenn Benutzer mit anderen Benutzern interagieren, die verschiedene Client- und Serverversionen verwenden.

## Peer-zu-Peer-Featureunterstützung

Peer-zu-Peer-Features werden für Benutzer unterstützt, die auf verschiedenen Versionen des Servers verwaltet werden und verschiedene Clientversionen verwenden. Die Endbenutzererfahrung und die verfügbaren Features sind mit den Fähigkeiten des Clients des Benutzers und der Version des Servers, auf dem der Benutzer angemeldet ist, konsistent. Anders ausgedrückt:

  - Wenn ein Benutzer mit einem älteren Client bei Lync Server 2013 angemeldet ist, steht ihm seine gewohnte Benutzeroberfläche zur Verfügung. Die neuen in Lync Server 2013 eingeführten Features werden erst nach einem Upgrade des Clients des Benutzers verfügbar, beispielsweise Videokatalogansicht, HD-Video, PowerPoint-Freigabe und die Option, alle Audio- und Videodateien für Teilnehmer bei Besprechungszugang stummzuschalten. Die neuen Funktionen sind unter [Neue Konferenzfunktionen in Lync Server 2013](lync-server-2013-new-conferencing-features.md) und [Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) aufgeführt.

  - Wenn ein Benutzer mit einem Lync 2013-Client bei Lync Server 2010 angemeldet ist, werden neue von Lync Server 2010 unterstützte Features erst verfügbar, wenn der Benutzer zu Lync Server 2013 migriert wird.

In der folgenden Tabelle wird die Featureverfügbarkeit bei Peer-zu-Peer-Sitzungen verglichen, in denen der Client entweder bei Lync Server 2013 oder Lync Server 2010 angemeldet ist.


> [!NOTE]
> Lync Web App und Lync 2010-Teilnehmer sind nur Clients für Besprechungen und sind in dieser Tabelle nicht enthalten.




<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Chatnachrichten</th>
<th>Anwesenheit</th>
<th>VoIP</th>
<th>Video</th>
<th>Anwendungsfreigabe</th>
<th>Dateiübertragung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010-Vermittlung</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja1</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>Öffentliche Instant Messaging-Dienstanbieter (AOL, Yahoo!)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Öffentliche Instant Messaging-Dienstanbieter (MSN, Windows Live Messenger)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Instant Messaging-Diensten („PIC USL“) nicht mehr neu erworben werden und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrunde liegende Vereinbarung nicht verlängert wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync-Standard-Clientzugriffslizenz (CAL). Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



1 In Office Communicator 2007 R2 ist nur Desktopfreigabe (keine Programmfreigabe) verfügbar.

## Unterstützung für Konferenzfeatures für Lync 2013-Clients in Lync Server 2010-Besprechungen

Wenn Benutzer an Lync Server 2010-Besprechungen mit einem Lync 2013-Client teilnehmen, haben Sie Zugriff auf Lync 2013-Clientfeatures mit den folgenden Ausnahmen:

  - Bei den Verwaltungsoptionen für **Teilnehmer**, auf die zugegriffen werden kann, indem Sie im Besprechungsfenster auf das Symbol für Personen zeigen, funktioniert die Option **Kein Besprechungs-Chat** nicht.

  - In Videokonferenzen funktioniert die Katalogansicht nicht. Der Benutzer sieht nur den aktiven und nicht alle Sprecher. In der Liste mit Optionen für **Ein Layout auswählen** ist **Katalogansicht** nicht verfügbar.

  - Die Teilnehmerliste wird in Videokonferenzen standardmäßig angezeigt.

  - Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Teilnehmerverwaltungsoptionen **Videospotlight sperren** und **An Katalog anheften** nicht verfügbar.

## Unterstützung für Konferenzfeatures in Lync Server 2013-Besprechungen

Lync Server 2013 bietet neue Konferenzfunktionen, die Benutzern zu Verfügung stehen, nachdem ihre Konten zu Lync Server 2013 verschoben wurden und sie sich mit dem Lync 2013-Client anmelden. Beispiele für neue Funktionen sind die Videokatalogansicht, HD-Video, PowerPoint-Freigabe und die Option, alle Audio- und Videodateien bei Besprechungszugang stummzuschalten. Die neuen Funktionen sind unter [Neue Konferenzfunktionen in Lync Server 2013](lync-server-2013-new-conferencing-features.md) und [Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) aufgeführt.

In Lync Server 2013-Besprechungen werden bestimmte Konferenzfeatures für Benutzer unterstützt, die auf verschiedenen Versionen des Servers verwaltet werden und verschiedene Clients und Clientversionen verwenden. Wenn ein Client einer Lync Server 2013-Besprechung beitritt, haben Benutzer Zugriff auf die in dieser Tabelle aufgeführten Features und Fähigkeiten.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Peer-zu-Peer-Chatnachrichten</th>
<th>VoIP</th>
<th>Video</th>
<th>Anwendungsfreigabe</th>
<th>PowerPoint</th>
<th>Dateiübertragung</th>
<th>Whiteboard</th>
<th>Umfragen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja2</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja3</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R24</p></td>
<td><p>Ja</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


1 In Office Communicator 2007 R2 ist nur Desktopfreigabe (keine Programmfreigabe) verfügbar.

2Lync Server 2013 verwendet einen aktualisierten Mechanismus für das Hochladen von PowerPoint-Dateien. Lync Web App-Benutzer, die einer Besprechung beitreten, die ursprünglich in Lync Server 2010 geplant wurde, können PowerPoint-Präsentationen anzeigen und darin navigieren, aber keine PowerPoint-Dateien hochladen.

3 Wurde die Besprechung in Lync Server 2013 geplant und wurden PowerPoint-Folien von einem Lync 2013-Client hochgeladen, haben Lync 2010-Benutzer nur Anzeigezugriff auf die Folien. Wurden die PowerPoint-Folien dagegen von einem Lync 2010-Benutzer hochgeladen, können Lync Server 2013-Benutzer Folien anzeigen und ändern sowie, sofern Office Web Apps Server konfiguriert ist, auf neue Funktionen zugreifen (etwa Anzeige mit höherer Auflösung, Animationen, Folienübergänge und eingebettetes Video). Weitere Informationen hierzu finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4Die Anwesenheits- und Chatfeatures in Office Communicator 2007 R2 sind mit Lync Server 2013 kompatibel, nicht jedoch die Konferenzfeatures. Während der Migration von Office Communications Server 2007 R2 eignet sich Office Communicator 2007 R2 für Anwesenheits- und Chatinteroperabilität, Benutzer sollten jedoch Lync Web App 2013 verwenden, um an Lync Server 2013-Besprechungen teilzunehmen.

## Unterstützung von Planungs-Add-Ins

Die Serverunterstützung für verschiedene Planungs-Add-Ins ist mit der Server- und Clientversionskompatibilität konsistent. Im Allgemeinen werden die folgenden Planungs-Add-Ins in Lync Server 2013 unterstützt. Frühere Versionen von Add-Ins bieten jedoch keine neuen Lync 2013-Add-In-Features wir z. B. die Option zum Stummschalten von Audio und Video für Teilnehmer beim Besprechungsbeitritt.

  - **Onlinebesprechungs-Add-In für Lync 2013**   Bietet dieselben Features wir das Onlinebesprechungs-Add-In für Lync 2010 und verfügt zusätzlich über Stummschaltungssteuerung für Teilnehmer; so können Besprechungsorganisatoren Konferenzen planen, bei denen Audio und Video der Teilnehmer standardmäßig stummgeschaltet sind. Administratoren können auch die Besprechungseinladungen der Organisation anpassen, indem ein benutzerdefiniertes Logo, eine Support-URL, eine URL zum rechtlichen Haftungsausschluss oder ein benutzerdefinierter Fußzeilentext hinzugefügt werden.

  - **Onlinebesprechungs-Add-In für Lync 2010**   Bietet die Planung von Lync-Besprechungen und entfernt die Möglichkeit zum Planen von Office Live Meeting-Konferenzen.

  - **Konferenz-Add-In für Office Communicator 2007 R2**   Bietet die Planung von Office Live Meeting- und Office Communicator 2007 R2-Konferenzen. 


> [!NOTE]
> Live Meeting-Konferenzen können in Lync Server 2013 nicht geplant werden.




<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Planungsclient</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Onlinebesprechungs-Add-In für Lync 2013 (kann mit Office 2013, Outlook 2010 und Outlook 2007 verwendet werden)</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt (neue Add-In-Features nicht verfügbar)</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web Scheduler</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Onlinebesprechungs-Add-In für Lync 2010</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Konferenz-Add-In für Office Communicator 2007 R2</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
</tbody>
</table>


## Unterstützung für Besprechungsbeitritt

Alle von Lync Server 2013 unterstützten Clients können Lync 2013-Besprechungen beitreten. Da es sich bei Lync Web App um eine Webkomponente des Servers handelt, wird in Fällen, bei denen Lync Web App zum Beitreten zu einer Lync Server 2013-Besprechung verwendet wird, immer die neuere Version von Lync Web App verwendet.

Lync 2013-Clients können auf Lync 2010 und Office Communications Server 2007 R2 gehosteten Besprechungen mit reduzierter Funktionalität beitreten. Features innerhalb von Besprechungen werden durch die Version des Servers eingeschränkt, der die Besprechung hostet.

## Siehe auch

#### Konzepte

[Anforderungen für Lync Windows Store-App](lync-server-2013-lync-windows-store-app-requirements.md)  
[Neue Konferenzfunktionen in Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)


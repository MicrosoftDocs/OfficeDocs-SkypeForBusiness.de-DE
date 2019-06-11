---
title: 'Lync Server 2013: Clientinteroperabilität in Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Clientinteroperabilität in Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-03-04_

In diesem Thema wird erläutert, wie Microsoft lync Server 2013-Clients mit Clients aus früheren Versionen von lync Server und Office Communications Server koexistieren und mit ihnen interagieren können.

<div>

## <a name="server-and-client-compatibility"></a>Server-und Client Kompatibilität

In der folgenden Tabelle sind die unterstützten Kombinationen von Clientversionen und Server Versionen aufgeführt. Diese Tabelle gibt an, ob die Anmeldung unterstützt wird, wenn der Client versucht, eine Verbindung mit dem angegebenen Server herzustellen. Lync Server 2013 unterstützt die vorherige Client Version. Im Gegensatz zu früheren Versionen unterstützt lync Server 2010 die neuen lync 2013-Clients. Dadurch können Organisationen, die von lync Server 2010 upgraden, neue Clients unabhängig von lync Server-Upgrades bereitstellen.


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
<td><p>Supported5</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010-Vermittlung</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010-Gruppenchat</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010-Teilnehmer</p></td>
<td><p>Nicht Supported3</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2-Vermittlung</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Windows Store-App für Lync</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
</tbody>
</table>


Informationen zu 1Für finden Sie unter [Migration von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppenchat zu lync Server 2013, beständiger Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2in Microsoft lync Server 2010, die Gruppen-Chatfunktionalität war mit dem Gruppen-Chat Server, einer vertrauenswürdigen Drittanbieteranwendung für lync Server 2010, verfügbar. Lync 2013-Clients sind nicht mit lync Server 2010, Gruppen-Chat, kompatibel.

3Lync Web App 2013 bietet nun eine vollständige Besprechungs Erfahrung, einschließlich Computer Audio und-Video, und gilt als Ersatz für lync 2010 Attendee. Lync 2010 Attendee stellt nur dann eine Verbindung mit lync Server 2013 her, wenn Sie einen nicht unterstützten Browser verwenden (Internet Explorer 6 oder Internet Explorer 7) und Windows XP.

4Die-Anwesenheits-und Chat Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfeatures jedoch nicht. Während der Migration von Office Communications Server 2007 R2 eignet sich Office Communicator 2007 R2 für Anwesenheits-und Chat Interoperabilität, doch Benutzer sollten lync Web App 2013 verwenden, um an lync Server 2013-Besprechungen teilzunehmen.

5 Einschränkungen finden Sie unter "Konferenz Feature-Unterstützung für lync 2013-Clients in lync Server 2010-Besprechungen" weiter unten in diesem Thema.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilität zwischen Clients

Mit der Version lync Server 2013 können verschiedene Clientversionen nahtlos in Peer-zu-Peer-und Konferenzszenarien interagieren. In diesem Abschnitt wird die Verfügbarkeit von Features erläutert, wenn Benutzer mit anderen Benutzern interagieren, die unterschiedliche Versionen von Clients und Servern verwenden.

<div>

## <a name="peer-to-peer-feature-support"></a>Unterstützung von Peer-zu-Peer-Features

Peer-zu-Peer-Features werden für Benutzer unterstützt, die in unterschiedlichen Versionen des Servers unterschiedliche Clientversionen verwenden. Die Benutzeroberfläche und die verfügbaren Features stehen im Einklang mit den Funktionen des Benutzer Clients und der Version des Servers, bei dem der Benutzer angemeldet ist. Anders ausgedrückt:

  - Wenn ein Benutzer bei lync Server 2013 mit einem älteren Client angemeldet ist, verfügt der Benutzer über die gleiche Erfahrung, die er verwendet. Keines der neuen Features, die in lync Server 2013 eingeführt wurden, wird verfügbar sein, bis der Client des Benutzers aktualisiert wird. Beispiele sind Video Katalogansicht, HD-Video, aktualisierte PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videoanrufe nach dem Besprechungseintrag. Die neuen Features werden in den [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.

  - Wenn ein Benutzer bei lync Server 2010 mit einem lync 2013-Client angemeldet ist, stehen alle neuen Features, die nicht von lync Server 2010 unterstützt werden, erst zur Verfügung, wenn der Benutzer zu lync Server 2013 verschoben wird.

In der folgenden Tabelle wird die Verfügbarkeit von Features in Peer-to-Peer-Sitzungen verglichen, bei denen der Client entweder bei lync Server 2013 oder lync Server 2010 angemeldet ist.

<div>


> [!NOTE]  
> Lync Web App und lync 2010 Attendee sind Besprechungs reine Clients, die nicht in dieser Tabelle enthalten sind.



</div>


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
<th>Instant Messaging</th>
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
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td></td>
<td></td>
<td></td>
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
<td><p>Öffentlicher Chat (AOL, Yahoo!)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Öffentlicher Chat (MSN, Windows Live Messenger)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public Chat-Benutzerabonnementlizenz (PIC USL) nicht mehr für den Kauf für neue oder erneuernde Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger bis zum Shutdown-Datum des Diensts. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für die öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine pro Benutzer/Monat-Abonnementlizenz, die für lync Server oder Office Communications Server für die Föderation mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung nicht verlängert werden sollte.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen über Chat und Sprache zu erreichen.</P></LI></UL>



</div>

1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.

<div>


> [!NOTE]  
> Die Desktop Freigabe zwischen Office Communicator 2007 R2 und Skype for Business 2015 kann nicht vom neueren Client initiiert werden, wenn die Benutzeroberfläche des Skype for Business 2015-Clients erzwungen wird.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Unterstützung von Konferenzfeatures für lync 2013-Clients in lync Server 2010-Besprechungen

Wenn Benutzer mit einem lync 2013-Client an lync Server 2010-Besprechungen teilnehmen, können Sie mit den folgenden Ausnahmen auf lync 2013-Clientfeatures zugreifen:

  - In den Verwaltungsoptionen für **Teilnehmer** , auf die durch zeigen auf das Symbol "Personen" im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechung im Chat** .

  - Die Katalogansicht funktioniert in Videokonferenzen nicht. Der Benutzer sieht nur den aktiven Lautsprecher und nicht alle Lautsprecher. In der Liste der Optionen zum **Wählen eines Layouts** steht die **Katalogansicht** nicht zur Verfügung.

  - Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.

  - Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Optionen für das **Video Spotlight** und die **PIN-zu-Katalog** -Teilnehmer-Verwaltung Sperren nicht verfügbar.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Unterstützung von Konferenzfeatures in lync Server 2013-Besprechungen

Lync Server 2013 bietet neue Konferenzfeatures, die Benutzern zur Verfügung stehen, nachdem Ihre Konten nach lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden. Beispiele sind Video Katalogansicht, HD-Video, PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videoanrufe nach dem Besprechungseintrag. Die neuen Features werden in den [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.

In lync Server 2013-Besprechungen werden bestimmte Konferenzfeatures für Benutzer unterstützt, die in unterschiedlichen Versionen des Servers verwaltet werden und unterschiedliche Clients und Clientversionen verwenden. Wenn Clients an einer lync Server 2013-Besprechung teilnehmen, haben Benutzer Zugriff auf die Features und Funktionen, die in dieser Tabelle gezeigt werden.


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
<th>Peer-zu-Peer-Chat</th>
<th>VoIP</th>
<th>Video</th>
<th>Anwendungsfreigabe</th>
<th>PowerPoint</th>
<th>Dateiübertragung</th>
<th>Whiteboard</th>
<th>Abruf</th>
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
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>Ja</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.

2 lync Server 2013 verwendet einen aktualisierten Mechanismus zum Hochladen von PowerPoint-Dateien. Lync Web App-Benutzer, die an einer Besprechung teilnehmen, die ursprünglich auf lync Server 2010 geplant war, können PowerPoint-Präsentationen anzeigen und darin navigieren, jedoch keine PowerPoint-Dateien hochladen.

3 Wenn die Besprechung auf lync Server 2013 geplant war und PowerPoint-Folien von einem lync 2013-Client hochgeladen wurden, haben lync 2010-Benutzer nur Zugriff auf die Folien. Wenn umgekehrt die PowerPoint-Folien von einem lync 2010-Benutzer hochgeladen wurden, können lync Server 2013-Benutzer die Ansicht und Folien anzeigen und, wenn der Office Web Apps-Server konfiguriert ist, auf neue Funktionen zugreifen, beispielsweise Anzeige mit höherer Auflösung, Animationen, Folienübergänge und Eingebettetes Video. Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4Die-Anwesenheits-und Chat Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfeatures jedoch nicht. Während der Migration von Office Communications Server 2007 R2 eignet sich Office Communicator 2007 R2 für Anwesenheits-und Chat Interoperabilität, doch Benutzer sollten lync Web App 2013 verwenden, um an lync Server 2013-Besprechungen teilzunehmen.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Planen der Add-in-Unterstützung

Die Server Unterstützung für die verschiedenen Terminplan-Add-Ins ist mit der Kompatibilität zwischen Server-und Clientversionen konsistent. Im Allgemeinen werden die folgenden Planungs-Add-Ins in lync Server 2013 unterstützt. In früheren Versionen von Add-Ins werden jedoch keine neuen lync 2013-Add-in-Features bereitgestellt, wie beispielsweise die Option zum stumm schalten aller Teilnehmer-Audio-und-Videoanrufe nach dem Besprechungseintrag.

  - **Das Online Besprechungs-Add-in für lync 2013**   bietet dieselben Features wie das Online Besprechungs-Add-in für lync 2010 mit dem Hinzufügen von Steuerelementen für Teilnehmer-stumm Schaltungen, mit denen Besprechungsorganisatoren Konferenzen planen können, in denen Teilnehmer-Audio und-Video stumm geschaltet sind. Standard. Administratoren können die Besprechungseinladungen des Unternehmens auch anpassen, indem Sie ein benutzerdefiniertes Logo, eine Support-URL, eine URL zur rechtlichen Verzichtserklärung oder einen benutzerdefinierten Fußzeilentext hinzufügen.

  - **Das Online Besprechungs-Add-in für lync 2010**   bietet Zeitplanung für lync-Besprechungen und entfernt die Möglichkeit zum Planen von Office Live Meeting-Konferenzen.

  - **Das Office Communicator 2007 R2 Conferencing-Add-in**   bietet Terminplanung für Office Live Meeting-Konferenzen und Office Communicator 2007 R2-Konferenzen. 

<div>


> [!NOTE]  
> Live Meeting-Konferenzen können auf lync Server 2013 nicht geplant werden.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Terminplanungs-Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Online Besprechungs-Add-in für lync 2013 (kann mit Office 2013, Outlook 2010 und Outlook 2007 verwendet werden)</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt (neue Add-in-Features sind nicht verfügbar)</p></td>
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
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2-Konferenz-Add-in</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt </p></td>
<td><p>Unterstützt</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Unterstützung für die Teilnahme an Besprechungen

Alle Clients, die von lync Server 2013 unterstützt werden, dürfen an lync 2013-Besprechungen teilnehmen. Da es sich bei lync Web App um eine Webkomponente des Servers handelt, wird in den Fällen, in denen lync Web App für die Teilnahme an einer lync Server 2013-Besprechung verwendet wird, immer die neuere Version von lync Web App verwendet.

Lync 2013-Clients können an Besprechungen teilnehmen, die in lync 2010 und Office Communications Server 2007 R2 mit skalierten Funktionen gehostet werden. In-Meeting-Features sind durch die Version des Servers, auf dem die Besprechung gehostet wird, limitiert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Windows Store-App-Anforderungen für lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Neue Konferenzfunktionen in Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Neue Funktionen für Clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


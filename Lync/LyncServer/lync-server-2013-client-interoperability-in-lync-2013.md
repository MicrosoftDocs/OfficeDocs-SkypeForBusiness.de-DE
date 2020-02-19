---
title: 'Lync Server 2013: Client Interoperabilität in lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a4616cbe9519a8196ce78e35f21c673a0d2c95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Client Interoperabilität in lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-03-04_

In diesem Thema wird erläutert, wie Microsoft lync Server 2013 Clients in früheren Versionen von lync Server und Office Communications Server nebeneinander bestehen und mit Clients interagieren können.

<div>

## <a name="server-and-client-compatibility"></a>Server-und Client Kompatibilität

In der folgenden Tabelle ist aufgeführt, welche Kombinationen von Client- und Serverversionen unterstützt werden. Diese Tabelle gibt an, ob die Anmeldung unterstützt wird, wenn der Client versucht, eine Verbindung mit dem angezeigten Server herzustellen. Lync Server 2013 unterstützt die vorherige Client Version. Im Gegensatz zu früheren Versionen unterstützt lync Server 2010 auch die neuen lync 2013-Clients. Auf diese Weise können Organisationen, die ein Upgrade von lync Server 2010 durchführen, neue Clients unabhängig von lync Server Upgrades Ausrollen.


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
<td><p>Unterstützt</p></td>
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
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Gruppen Chat</p></td>
<td><p>Unterstützt1</p></td>
<td><p>Unterstützt2</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Nicht Supported3</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
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
<td><p>Lync Windows Store-App</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
</tbody>
</table>


Details zu 1Für finden Sie unter [Migration from lync Server 2010, Group Chat oder Office Communications Server 2007 R2 Group Chat to lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2in Microsoft lync Server 2010 war die gruppenchatfunktion mit dem Gruppenchat Server, einer vertrauenswürdigen Drittanbieteranwendung für lync Server 2010, verfügbar. Lync 2013 Clients sind nicht mit lync Server 2010, Gruppen Chat, kompatibel.

3Lync-Webanwendung 2013 bietet nun eine umfassende Besprechungs Erfahrung, einschließlich Computer-Audio und-Video, und gilt als Ersatz für lync 2010 Attendee. Lync 2010 Attendee stellt nur dann eine Verbindung mit lync Server 2013 her, wenn Sie einen nicht unterstützten Browser (Internet Explorer 6 oder Internet Explorer 7) und Windows XP verwenden.

4Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht. Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.

5 Informationen zu Einschränkungen finden Sie unter "Unterstützung von Konferenzfeatures für lync 2013 Clients in lync Server 2010 Besprechungen" weiter unten in diesem Thema.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilität zwischen Clients

Mit der lync Server 2013-Version können verschiedene Clientversionen nahtlos in Peer-zu-Peer-und Konferenzszenarien interagieren. In diesem Abschnitt wird die Verfügbarkeit von Features erläutert, wenn Benutzer mit anderen Benutzern interagieren, die unterschiedliche Versionen von Clients und Servern verwenden.

<div>

## <a name="peer-to-peer-feature-support"></a>Unterstützung von Peer-zu-Peer-Funktionen

Peer-to-Peer-Funktionen werden für Benutzer unterstützt, die in verschiedenen Versionen des Servers verwaltet werden und unterschiedliche Clientversionen verwenden. Die Endbenutzeroberfläche und die verfügbaren Features stehen im Einklang mit den Funktionen des Clients des Benutzers und der Version des Servers, bei dem der Benutzer angemeldet ist. Anders ausgedrückt:

  - Wenn ein Benutzer bei lync Server 2013 mit einem älteren Client angemeldet ist, hat der Benutzer die gleiche Erfahrung wie er verwendet wird. Keines der in lync Server 2013 eingeführten neuen Features ist verfügbar, bis der Client des Benutzers aktualisiert wird. Beispiele hierfür sind Video Galerie-Ansicht, HD-Video, aktualisierte PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videodaten beim Besprechungseintrag. Die neuen Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.

  - Wenn ein Benutzer bei lync Server 2010 mit einem lync 2013-Client angemeldet ist, sind alle neuen Features, die nicht von lync Server 2010 unterstützt werden, erst verfügbar, wenn der Benutzer zu lync Server 2013 verschoben wird.

In der folgenden Tabelle wird die Verfügbarkeit von Features in Peer-to-Peer-Sitzungen verglichen, in denen der Client entweder lync Server 2013 oder lync Server 2010 angemeldet ist.

<div>


> [!NOTE]  
> Lync Web App und lync 2010 Attendee sind Besprechungs bezogene Clients, die nicht in dieser Tabelle enthalten sind.



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
<td><p>Lync 2010 Attendant</p></td>
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
<td><p>Yes1</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="even">
<td><p>Öffentliche Chatnachrichten (AOL, Yahoo!)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Öffentliche Chatnachrichten (MSN, Windows Live Messenger)</p></td>
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
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger bis zum Datum der Beendigung des Diensts. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>..</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</P></LI></UL>



</div>

1 in Office Communicator 2007 R2 steht nur die Desktopfreigabe (und nicht die Programmfreigabe) zur Verfügung.

<div>


> [!NOTE]  
> Die Desktop Freigabe zwischen Office Communicator 2007 R2 und Skype for Business 2015 kann nicht vom neueren Client initiiert werden, wenn die Skype for Business 2015 Client-Benutzeroberfläche erzwungen wird.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Unterstützung von Konferenzfeatures für lync 2013 Clients in lync Server 2010 Besprechungen

Wenn Benutzer lync Server 2010 Besprechungen mit einem lync 2013-Clientteil nehmen, haben Sie Zugriff auf lync 2013-Clientfeatures mit den folgenden Ausnahmen:

  - In den Verwaltungsoptionen für **Teilnehmer** , auf die durch den Hinweis auf das Symbol Personen im Besprechungsfenster zugegriffen werden kann, funktioniert die Option **keine Besprechungs-Chat** Funktion nicht.

  - Die Katalogansicht funktioniert nicht in Videokonferenzen. Der Benutzer sieht anstelle aller Lautsprecher nur den aktiven Lautsprecher. In der Liste der Optionen zum **Auswählen eines Layouts** ist die **Katalogansicht** nicht verfügbar.

  - Die Teilnehmerliste wird standardmäßig in Videokonferenzen angezeigt.

  - Wenn Sie mit der rechten Maustaste auf einen Benutzer in der Teilnehmerliste klicken, sind die Verwaltungsoptionen **Video Spotlight** und **PIN-an-Katalog** -Teilnehmerverwaltung Sperren nicht verfügbar.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Unterstützung von Konferenzfeatures in lync Server 2013 Besprechungen

Lync Server 2013 stellt neue Konferenzfeatures bereit, die Benutzern zur Verfügung stehen, nachdem Ihre Konten in lync Server 2013 verschoben wurden und sich mit dem lync 2013-Client anmelden. Beispiele hierfür sind Video Galerie-Ansicht, HD-Video, PowerPoint-Freigabe und die Option zum stumm schalten aller Teilnehmer-Audio-und-Videodaten beim Besprechungseintrag. Die neuen Features werden in [neuen Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md) und Neuerungen [für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)erläutert.

In lync Server 2013 Besprechungen werden bestimmte Konferenzfeatures für Benutzer unterstützt, die in unterschiedlichen Versionen des Servers verwaltet werden und unterschiedliche Clients und Clientversionen verwenden. Wenn Clients an einer lync Server 2013 Besprechung teilnehmen, haben Benutzer Zugriff auf die in dieser Tabelle gezeigten Features und Funktionen.


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
<th>Abrufen</th>
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
<td><p>Yes3</p></td>
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

2 lync Server 2013 verwendet einen aktualisierten Mechanismus für das Hochladen von PowerPoint-Dateien. Lync Web App Benutzer, die einer Besprechung beitreten, die ursprünglich auf lync Server 2010 geplant war, können PowerPoint-Präsentationen anzeigen und navigieren, jedoch keine PowerPoint-Dateien hochladen.

3 Wenn die Besprechung in lync Server 2013 geplant wurde und PowerPoint-Folien von einem lync 2013-Client hochgeladen wurden, verfügen lync 2010 Benutzer über einen schreibgeschützten Zugriff auf die Folien. Wenn umgekehrt die PowerPoint-Folien von einem lync 2010-Benutzer hochgeladen wurden, können lync Server 2013 Benutzer anzeigen und Folien und, falls Office-webapps-Server konfiguriert ist, auf neue Funktionen wie höhere Auflösung, Animationen, Folienübergänge und Eingebettetes Video. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

4Die-Anwesenheits-und Chat-Features in Office Communicator 2007 R2 sind mit lync Server 2013 kompatibel, die Konferenzfunktionen jedoch nicht. Während der Migration von Office Communications Server 2007 R2 ist Office Communicator 2007 R2 für die Interoperabilität von Anwesenheits-und Chatfunktionen geeignet, aber Benutzer sollten lync Web App 2013 verwenden, um lync Server 2013 Besprechungen beizutreten.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Planen der Add-in-Unterstützung

Die Server Unterstützung für die unterschiedlichen Planungs-Add-Ins ist konsistent mit der Server-und Client Versionskompatibilität. Im Allgemeinen werden die folgenden Planungs-Add-Ins in lync Server 2013 unterstützt. In früheren Versionen von Add-Ins werden jedoch keine neuen lync 2013-Add-in-Features bereitgestellt, wie beispielsweise die Option zum stumm schalten aller Teilnehmer-Audio-und-Videos beim Besprechungseintrag.

  - **Das Online-Besprechungs-Add-in für lync 2013**   bietet dieselben Features wie das Online-Besprechungs-Add-in für lync 2010, wobei die Teilnehmer-stumm Schaltungs Steuerelemente hinzugefügt werden, mit deren Hilfe Besprechungsorganisatoren Konferenzen planen können, für die die Teilnehmer-Audio und-Videostandard mäßig stumm geschaltet sind. Administratoren können die Besprechungseinladungen der Organisation auch anpassen, indem Sie ein benutzerdefiniertes Logo, eine Support-URL, eine URL für einen rechtlichen Haftungsausschluss oder benutzerdefinierter Fußzeilentext hinzufügen.

  - **Das Online-Besprechungs-Add-in für lync 2010**   bietet Zeitpläne für lync-Besprechungen und entfernt die Möglichkeit, Office Live Meeting Konferenzen zu planen.

  - **Office Communicator 2007 R2 Konferenz-Add-in**   bietet Zeitplanung für Office Live Meeting Konferenzen und Office Communicator 2007 R2 Konferenzen. 

<div>


> [!NOTE]  
> Live Meeting Konferenzen können nicht für lync Server 2013 geplant werden.



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
<th>Planen des Clients</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Online-Besprechungs-Add-in für lync 2013 (kann mit Office 2013, Outlook 2010 und Outlook 2007 verwendet werden)</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt (neue Add-in-Features nicht verfügbar)</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013-Webplaner</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Online-Besprechungs-Add-in für lync 2010</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2-Konferenz-Add-in</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Unterstützung für den Beitritt zu Besprechungen

Alle von lync Server 2013 unterstützten Clients dürfen lync 2013 Besprechungen beitreten. Da lync Web App eine Webkomponente des Servers ist, wird in Fällen, in denen lync Web App für den Beitritt zu einer lync Server 2013 Besprechung verwendet wird, die neuere Version von lync Web App immer verwendet.

Lync 2013 Clients können Besprechungen, die auf lync 2010 gehostet werden, und Office Communications Server 2007 R2 mit heruntergestuften Funktionen verbinden. In-Meeting-Features sind durch die Version des Servers, auf dem die Besprechung gehostet wird, limitiert.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Windows Store-App-Anforderungen für lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Neue Konferenzfeatures in lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Neuerungen für Clients in lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


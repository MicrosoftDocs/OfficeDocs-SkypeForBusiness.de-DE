---
title: 'Lync Server 2013: Benutzermodelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a5f110e6b2badd5b0651a2ad32860f421fab167
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508732"
---
# <a name="user-models-in-lync-server-2013"></a>Benutzermodelle in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die hier beschriebenen Benutzermodelle bilden die Grundlage für die Kapazitäts Planungs Messungen und-Empfehlungen, die unter [Kapazitätsplanung für lync Server 2013 mithilfe der Benutzermodelle](lync-server-2013-capacity-planning-using-the-user-models.md)beschrieben werden.

<div>

## <a name="lync-server-2013-user-models"></a>Lync Server 2013-Benutzermodelle

In der folgenden Tabelle wird das Benutzermodell für die Registrierung, Kontakte, Chatnachrichten und Anwesenheitsinformationen für lync Server 2013 beschrieben.

### <a name="environment-and-registration-user-model"></a>Benutzermodell für Umgebung und Registrierung

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bereitstellungsgröße und Verteilung</p></td>
<td><p>Es wird eine große Bereitstellung mit drei zentralen Standorten und einem Front-End-Pool pro Standort modelliert.</p></td>
</tr>
<tr class="even">
<td><p>Prozentsatz an Active Directory-Benutzern</p></td>
<td><p>Es wird davon ausgegangen, dass 70% aller Active Directory-Benutzer in der Organisation für lync Server aktiviert sind. 80% dieser aktivierten Benutzer sind bei lync Server jeden Tag angemeldet (80% Gleichzeitigkeit). Die gleichzeitigen Benutzer sind die Grundlage für die weiteren Zahlenangaben in diesem Abschnitt.</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory-Änderungen</p></td>
<td><p>Es wird davon ausgegangen, dass 0,5% der Gesamtbenutzer in Active Directory jede Woche für lync erstellt und aktiviert werden und dass 0,5% der Gesamtbenutzer pro Woche von Active Directory und von lync deaktiviert sind. Für 5 % der Benutzer wird jede Woche mindestens ein Active Directory-Attribut geändert.</p></td>
</tr>
<tr class="even">
<td><p>Active Directory-Verteilergruppen</p></td>
<td><p>Es wird davon ausgegangen, dass die Anzahl der Active Directory-Verteilergruppen in der Organisation dreimal die Anzahl aller Benutzer in Active Directory ist. Die Verteilergruppen haben folgende Größe:</p>
<ul>
<li><p>64 % umfassen 2-30 Benutzer</p></li>
<li><p>13 % umfassen 31-50 Benutzer</p></li>
<li><p>10 % umfassen 51-100 Benutzer</p></li>
<li><p>13 % umfassen 101-500 Benutzer</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VoIP-Benutzer (Voice over IP)</p></td>
<td><p>60% der lync Server Benutzer sind für Unified Communications (UC) aktiviert (das heißt, die Telefonnummern befinden sich im Besitz von lync Server).</p></td>
</tr>
<tr class="even">
<td><p>Verteilung registrierter Clients</p></td>
<td><p>65% der Clients führen lync 2013 Software aus, einschließlich lync und lync Phone Edition.</p>
<p>30% der Clients mit Client Software aus einer früheren Version von lync.</p>
<p>5% der Clients verwenden lync Web App.</p>
<p>Wenn die Mobilität aktiviert ist, wird davon ausgegangen, dass 40% der Benutzer die Mobilität gleichzeitig mit den anderen zuvor zitierten registrierten Clientoptionen verwenden. In diesem Fall beträgt das mpop-Verhältnis (Multiple Points of Presence) des Clients 1:1.9. Wenn Mobility deaktiviert ist, beträgt das mpop-Verhältnis 1:1.5.</p></td>
</tr>
<tr class="odd">
<td><p>Verteilung von Remotebenutzern</p></td>
<td><p>70 % der Benutzer verbinden sich intern.</p>
<p>30 % der Benutzer stellen über einen Edgeserver und einen Director eine Verbindung her.</p></td>
</tr>
<tr class="even">
<td><p>Verteilung von Kontakten</p></td>
<td><p>Die maximale Anzahl von Kontakten eines Benutzers beträgt 1.000. Weniger als 1 % der Benutzer verfügen über 1.000 Kontakte. Weniger als 25 % der Benutzer verfügen über 100 Kontakte oder mehr.</p>
<p>Benutzer, die mit einem öffentlichen Netz verbunden sind, verfügen über durchschnittlich 80 Kontakte. Für diese Benutzer gilt Folgendes:</p>
<ul>
<li><p>50 % der Kontakte befinden sich innerhalb der Organisation. 10 % dieser Benutzer sind Remotebenutzer, die sich von außerhalb der Firewall verbinden.</p></li>
<li><p>40 % der Kontakte sind Benutzer einer öffentlichen Cloud (z. B. Benutzer von AOL, Yahoo! oder Google Talk).</p></li>
<li><p>10 % der Kontakte sind Benutzer von Verbundpartnern.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>


</div></li>
</ul>
<p>Benutzer ohne Verbindung mit einem öffentlichen Netz verfügen über durchschnittlich 50 Kontakte. Für diese Benutzer gilt Folgendes:</p>
<ul>
<li><p>80 % der Kontakte befinden sich innerhalb der Organisation. 10 % dieser Benutzer sind Remotebenutzer, die sich von außerhalb der Firewall verbinden.</p></li>
<li><p>20 % der Kontakte sind Benutzer von Verbundpartnern.</p>
<p>Jeder Benutzer weist 1 Verteilergruppe in seiner Kontaktliste auf. Für Leistungstest wird davon ausgegangen, dass Verteilergruppen immer erweitert werden.</p></li>
</ul>
<p>25 % der Kontakte eines Benutzers verwenden XMPP.</p></td>
</tr>
<tr class="odd">
<td><p>Sitzungszeit</p></td>
<td><p>Eine durchschnittliche Benutzeranmeldesitzung dauert 12 Stunden. Sämtliche Benutzer melden sich innerhalb von 120 Minuten nach dem Sitzungsstart an.</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>Benutzermodell für Chat und Anwesenheit

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Peer-zu-Peer-Chatsitzungen</p></td>
<td><p>Jeder Benutzer verfügt über durchschnittlich sechs Peer-zu-Peer-Chatsitzungen pro Tag.</p>
<p>10 Chatnachrichten pro Sitzung.</p>
<p>Jede Nachricht wird durch zwei SIP-Info-Nachrichten und 2 SIP 200 OK-Nachrichten (für die Status anzeigen wie " &lt; Name &gt; is Typing") abgeglichen.</p></td>
</tr>
<tr class="even">
<td><p>Abfrage von Anwesenheitsinformationen</p></td>
<td><p>Insgesamt wird von durchschnittlich 60 Abfragen von Anwesenheitsinformationen pro Benutzer und Stunde ausgegangen. Für jeden Benutzer wird von folgenden Durchschnittswerten ausgegangen:</p>
<ul>
<li><p>Eine Abfrage pro Tag für die Anwesenheitsinformationen von Benutzern auf der Registerkarte Organisation (nicht jedoch von Benutzern in der Kontaktliste) des Benutzers. Die durchschnittliche Anzahl von Benutzern auf der Registerkarte Organisation eines Benutzers, bei denen es sich nicht um Kontakte handelt, beträgt 15 Benutzer. Zwei Anzeigevorgänge für Visitenkarten pro Tag.</p></li>
<li><p>Eine Abfrage von Anwesenheitsinformationen, sobald der Benutzer einen anderen Benutzer anklickt, um eine Unterhaltung zu beginnen (diese Aktion erfolgt schätzungsweise einmal pro Stunde).</p></li>
<li><p>Sechs Suchvorgänge für Benutzer pro Stunde. Jedes Mal, wenn eine Suche ausgeführt wird, wird eine Stapelabfrage an alle Benutzer in der Suchergebnisliste gesendet. Es wird von einer durchschnittlichen Größe von 20 Suchergebnissen ausgegangen. Falls die Suchergebnisse weiterhin auf dem Bildschirm angezeigt werden, wird die Stapelabfrage alle 5 Minuten aktualisiert. Es wird von zwei derartigen Aktualisierungen pro Stunde ausgegangen.</p></li>
<li><p>Wenn der Benutzer eine E-Mail in Outlook öffnet bzw. eine Vorschau anzeigt, werden die Anwesenheitsinformationen für die Benutzer in den Feldern An: und CC: der E-Mail abgefragt (dieser Vorgang erfolgt schätzungsweise bei fünf E-Mails pro Stunde und für vier Benutzer pro E-Mail).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Anwesenheitsabonnements</p></td>
<td><p>Wenn ein Benutzer einen anderen Benutzer als Kontakt hinzufügt, <em>abonniert</em> der erste Benutzer fünf Kategorien von Informationen zum zweiten Benutzer. Aktualisierungen dieser Informationskategorien werden automatisch an den ersten Benutzer gesendet.</p>
<p>Für jeden Client wird eine einzige Stapelabonnementanforderung gesendet, um den Anwesenheitsstatus von durchschnittlich 40 Kontakten abzurufen, mit zusätzlich 40 Dialogen zum Abrufen von Anwesenheitsinformationen für Partnerkontakte.</p>
<p>Die Anwesenheitsinformationen für Mitglieder einer erweiterten Verteilergruppe werden über beständige Anwesenheitsabonnements ermittelt, nicht über Abrufe, und werden als 1 Erweiterung pro Benutzer für jeweils 2 Stunden modelliert.</p>
<p><em>Kurze Abonnements</em> werden verwendet, wenn sich ein Benutzer anmeldet, wenn ein Stapelabonnement für alle Kontakte des Benutzers vorhanden ist und wenn sich der Benutzer bald abmeldet. Es wird von 6 kurzen Abonnements pro Benutzer und Stunde ausgegangen, wobei jedes Abonnement 10 Minuten dauert.</p></td>
</tr>
<tr class="even">
<td><p>Veröffentlichung der Anwesenheit</p></td>
<td><p>Der Anwesenheitsstatus wird durchschnittlich viermal pro Benutzer und Stunde veröffentlicht, mit einer maximalen Anzahl von 6 Veröffentlichungen pro Benutzer und Stunde.</p></td>
</tr>
<tr class="odd">
<td><p>Größe des Anwesenheitsdokuments</p></td>
<td><p>Bei einem vollständigen Anwesenheitsdokument wird von einer durchschnittlichen Größe von 4 KB ausgegangen, mit einer maximalen Größe von 25 KB.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle wird das Benutzermodell für die Adressbuchverwendung beschrieben.

### <a name="address-book-usage-user-model"></a>Benutzermodell für die Adressbuchverwendung

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Adressbuchsuchmodus</th>
<th>Verwendung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nur Adressbuchwebabfrage (alle Abfragen werden vom Adressbuch-Webabfragedienst ausgeführt)</p></td>
<td><p>Vier Präfixabfragen pro Benutzer und Tag.</p>
<p>60 exakte Suchabfragen pro Benutzer und Tag. 40 % dieser Abfragen werden als Batchabfragen ausgeführt, mit durchschnittlich 20 Kontakten pro Abfrage. Die übrigen 60 % der Abfragen werden für einen einzelnen Kontakt ausgeführt.</p>
<p>25 Fotoabfragen pro Benutzer und Tag. 24 Abfragen für ein einzelnes Foto, die verbleibende Abfrage wird als Batchabfrage mit durchschnittlich 20 Kontakten ausgeführt.</p>
<p>Eine Suchabfrage für die gesamte Organisation pro Benutzer und Tag.</p></td>
</tr>
<tr class="even">
<td><p>Im gemischten Modus werden sowohl die Adressbuchdatei als auch Webabfragen verwendet. Dies ist der Standardmodus.</p></td>
<td><p>Nur zwei Abfragetypen werden über das Netzwerk ausgeführt, die Suchabfragen für Fotos und für die gesamte Organisation.</p>
<p>25 Fotoabfragen pro Benutzer und Tag. 24 Abfragen für ein einzelnes Foto, die verbleibende Abfrage wird als Batchabfrage mit durchschnittlich 20 Kontakten ausgeführt.</p>
<p>Eine Suchabfrage für die gesamte Organisation pro Benutzer und Tag.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle ist das Konferenzmodell beschrieben.

### <a name="conferencing-model"></a>Konferenzmodell

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Geplante Besprechungen im Vergleich zu &quot; sofort &quot; Besprechungen</p></td>
<td><p>60 % geplant, 40 % ungeplant.</p>
<p>Bei den geplanten Besprechungen wird von 80 % zugewiesenen Konferenzen ausgegangen, wobei es sich um Instanzen von wiederkehrenden Konferenzen handelt. 10 % sind einmalige offene Besprechungen, 8% sind einmalige anonyme Besprechungen, und 2 % sind einmalige geschlossene Besprechungen.</p></td>
</tr>
<tr class="even">
<td><p>Verteilung von Konferenzclients</p></td>
<td><p>Für geplante Besprechungen:</p>
<ul>
<li><p>65% der Konferenzbenutzer verwenden lync 2013.</p></li>
<li><p>5% der Konferenzbenutzer verwenden Microsoft lync Web App.</p></li>
<li><p>30% der Konferenzbenutzer verwenden frühere Clients, einschließlich Microsoft lync 2010, Office Communicator 2007 R2, Office Communicator 2007 und Microsoft Office Communicator Web Access (Version 2007).</p></li>
</ul>
<p>Für ungeplante Besprechungen:</p>
<ul>
<li><p>70% der Konferenzbenutzer verwenden lync 2013.</p></li>
<li><p>30% der Konferenzbenutzer verwenden frühere Clients, einschließlich Microsoft lync 2010, Office Communicator 2007 R2, Office Communicator 2007 und Microsoft Office Communicator Web Access (Version 2007).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Gleichzeitigkeit von Besprechungen</p></td>
<td><p>5 % der Benutzer befinden sich während der Arbeitszeiten in Konferenzen. Bei einem Pool mit 80.000 Benutzern können sich daher bis zu 4.000 Benutzer gleichzeitig in Konferenzen befinden.</p></td>
</tr>
<tr class="even">
<td><p>Verteilung der Audiofunktion in Besprechungen</p></td>
<td><p>40 % Kombination aus VoIP-Audio- und Einwahlkonferenzen, mit einem Verhältnis von 3:1 von VoIP-Benutzern zu Einwahlbenutzern.</p>
<p>35 % nur VoIP-Audio.</p>
<p>15 % nur Audio bei Einwahlkonferenzen.</p>
<p>10 % ohne Audio (reine Chatkonferenzen mit durchschnittlich fünf gesendeten Nachrichten pro Benutzer).</p></td>
</tr>
<tr class="odd">
<td><p>Medienmix für Konferenzen</p></td>
<td><p>Bei 75 % der Konferenzen handelt es sich um Webkonferenzen mit Audio sowie einigen anderen Methoden für die Zusammenarbeit.</p>
<p>Für diesen Konferenzen werden die folgenden weiteren Methoden für die Zusammenarbeit genutzt:</p>
<div>

> [!NOTE]  
> Die Summe dieser Zahlen beträgt mehr als 100 %, da in einer Konferenz mehrere Methoden zur Zusammenarbeit verwendet werden können.


</div>
<ul>
<li><p>50 % nutzen zusätzlich die Anwendungsfreigabe. Es wird davon ausgegangen, dass ein Benutzer Daten mit maximal 1,1 MB pro Sekunde sendet.</p></li>
<li><p>50 % nutzen zusätzlich Chatdienste (mit durchschnittlich zwei Chatnachrichten pro Benutzer).</p></li>
<li><p>20 % nutzen zusätzlich die Datenzusammenarbeit, einschließlich PowerPoint oder Whiteboard. Dabei werden pro Konferenz durchschnittlich zwei PowerPoint-Dateien mit einer durchschnittlichen Größe von 10 MB (ohne eingebettetes Video) oder 30 MB (mit eingebettetem Video) präsentiert. Durchschnittlich 20 Anmerkungen pro Whiteboard.</p></li>
<li><p>20 % nutzen zusätzlich die Videofunktion. 70 % dieser Benutzer nehmen an Konferenzen teil, für die Mehrfachansicht-Video aktiviert ist, wobei jeder Benutzer 2 bis 3 Videostreams empfängt.</p></li>
<li><p>15 % fügen freigegebene Notizen hinzu.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Verteilung der Konferenzteilnehmer</p></td>
<td><p>50 % interne, authentifizierte Benutzer.</p>
<p>25 % authentifizierte Benutzer mit Remotezugriff.</p>
<p>15 % anonyme Benutzer.</p>
<p>10 % Partnerbenutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Verteilung für den Besprechungsbeitritt</p></td>
<td><p>Für die Benutzer wird simuliert, dass sie der Besprechung innerhalb der ersten 5 Minuten beitreten.</p></td>
</tr>
</tbody>
</table>


In regulären Front-End-Pools hat lync Server 2013 eine maximal unterstützte Besprechungsgröße von 250 Benutzern. Jeder Pool kann zu einem bestimmten Zeitpunkt eine Besprechung mit 250 Benutzern hosten. Während eine Besprechung dieser Größe stattfindet, kann der Pool zusätzlich weitere kleinere Konferenzen hosten. Darüber hinaus können Sie Besprechungen mit bis zu 1000 Benutzern unterstützen, indem Sie einen Pool speziell zum Hosten dieser Besprechungen einrichten. Ausführliche Informationen finden Sie unter [Support für umfangreiche Besprechungen in lync Server 2013](lync-server-2013-support-for-large-meetings.md).

Konferenzen wurden wie folgt simuliert:

  - 85 % der Konferenzen wiesen vier Teilnehmer auf.

  - 10 % der Konferenzen wiesen sechs Teilnehmer auf.

  - 5 % der Konferenzen wiesen elf Teilnehmer auf.

  - Eine große Konferenz mit 250 Benutzern.

Die folgende Tabelle enthält ausführliche Informationen zum Benutzermodell für Konferenzen mit Einwahlbenutzern.

### <a name="dial-in-conferencing-user-model"></a>Benutzermodell für Einwahlkonferenzen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Authentifiziert/anonym</p></td>
<td><p>70 % der Anrufer treten anonym bei und werden zur Aufzeichnung ihres Namens aufgefordert.</p></td>
</tr>
<tr class="even">
<td><p>Anrufdauer und Wartemusik</p></td>
<td><p>Durchschnittliche Anrufdauer ohne Wartemusik: 50 Sekunden.</p>
<p>Für 50 % der Einwahlbenutzer wird Wartemusik wiedergegeben (durchschnittlich 5 Minuten).</p></td>
</tr>
<tr class="odd">
<td><p>DTMF (Dual-Tone Multifrequency, Mehrfrequenzverfahren)</p></td>
<td><p>15 % der Konferenzen, auf die ausschließlich per Einwahl zugegriffen wird, werden per Telefon geleitet. 10 % der gemischten Konferenzen, an denen Einwahlbenutzer teilnehmen, werden ebenfalls per Telefon geleitet.</p>
<p>20 % der Konferenzleiter (per Telefon) nutzen 2 DTMF-Befehle pro Konferenz.</p></td>
</tr>
<tr class="even">
<td><p>Sprache von Ansagen</p></td>
<td><p>Bei Simulationen wird Englisch als Ansagensprache verwendet.</p></td>
</tr>
</tbody>
</table>


Die folgende Tabelle enthält ausführliche Informationen zum Benutzermodell für die Konferenzlobby.

### <a name="conference-lobby-user-model"></a>Benutzermodell für die Konferenzlobby

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anzahl von Benutzern in der Lobby</p></td>
<td><p>5 % der Einwahlbenutzer betreten zunächst die Lobby, 25 % der anderen Benutzer werden zunächst in die Lobby weitergeleitet.</p></td>
</tr>
<tr class="even">
<td><p>Zulassen von Benutzern aus der Lobby</p></td>
<td><p>Bei Simulationen wurden alle Benutzer vom Referenten zugelassen, bevor ein Clienttimeout auftritt.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle ist das Benutzermodell für andere Peer-zu-Peer-Sitzungen beschrieben.

### <a name="peer-to-peer-sessions-user-model"></a>Benutzermodell für Peer-zu-Peer-Sitzungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>Jeder Benutzer nimmt an fünf Peer-zu-Peer-Anwendungsfreigabesitzungen pro Monat teil (durchschnittlich 0,25 Sitzungen pro Tag).</p></td>
</tr>
<tr class="even">
<td><p>Dateiübertragung</p></td>
<td><p>Jeder Benutzer nimmt (im Rahmen einer Chatsitzung) an einer Peer-zu-Peer-Dateiübertragungssitzung pro Monat teil (durchschnittlich 0,05 Sitzungen pro Tag). Die durchschnittliche Größe der in einer Sitzung übertragenen Dateien beträgt 1 MB.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle wird das Benutzermodell für Richtlinien beschrieben.

### <a name="policies-user-model"></a>Benutzermodell für Richtlinien

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategorie</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konferenz-, Anwesenheits- und Archivierungsrichtlinien</p></td>
<td><p>Es wird von einer globalen Richtlinie, zehn Konferenzrichtlinien, vier Archivierungsrichtlinien und zehn Anwesenheitsrichtlinien ausgegangen.</p></td>
</tr>
<tr class="even">
<td><p>VoIP-Richtlinie</p></td>
<td><p>Es wird von einer globalen Richtlinie und zwei Richtlinien pro Standort ausgegangen. 100 % der Standorte verfügen über eine Standortrichtlinie, und 30 % der Benutzer ist eine benutzerbasierte Richtlinie zugewiesen. Pro Standort wird von einem Wählplan und zwei Routen ausgegangen.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>Spitzenzeiten

Die Spitzenauslastung für Peer-zu-Peer-Sitzungen wird basierend auf der Anzahl von Anrufversuchen (Busy Hour Call Attempts, BHCA) zu Spitzenzeiten berechnet. Für diesen Begriff aus der VoIP-Branche wird davon ausgegangen, dass 50 % aller Anrufe an einem Tag innerhalb von 20 % der Gesamtzeit getätigt werden. Der BHCA-Wert wird mithilfe der folgenden Formel berechnet:

`BHCA=(total calls * 0.5) / 1.6`

Zur Simulation von Spitzenzeiten wurden in Leistungstests VoIP- und andere Peer-zu-Peer-Sitzungen bei einer Spitzenauslastung mit einer Dauer von mindestens 1,6 Stunden pro Tag ausgeführt.

Für die Spitzenauslastung bei Konferenzen wird davon ausgegangen, dass 75 % aller Konferenzen an einem achtstündigen Arbeitstag innerhalb von vier Stunden zu Spitzenzeiten stattfinden. Für diese Spitzenzeiten wird das 1,5-Fache der durchschnittlichen Konferenzauslastung verzeichnet.

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>Enterprise-VoIP-Anrufe

Für Enterprise-VoIP-Anrufe gelten die folgenden Annahmen:

  - 50% der Benutzer sind für Enterprise-VoIP aktiviert, und 60% dieser Benutzer sind für PSTN-Anrufe aktiviert.

  - Jeder dieser Benutzer, für den PSTN-Anrufe aktiviert sind, tätigt 4 PSTN-Anrufe in Spitzenzeiten. Jeder Anruf dauert 3 Minuten.

  - 65 % dieser PST-VoIP-Anrufe verwenden die Medienumgehung.

</div>

<div>

## <a name="mobility"></a>Mobilität

Es wird davon ausgegangen, dass für 40 % der registrierten Benutzer die Mobilität aktiviert ist. Für jeden Benutzer mit aktivierter Mobilität wird davon ausgegangen, dass sich die Aktivität des mobilen Clients zur Aktivität der anderen MPOP-Instanzen für diesen Benutzer summiert. Mit Ausnahme von Konferenzinteraktionen, für die der Mobilitätsclient einfach ein weiterer Clienttyp ist, der für die Teilnahme an Konferenzen verwendet werden kann.

</div>

<div>

## <a name="persistent-chat"></a>Beständiger Chat

Es wird davon ausgegangen, dass 25 % der registrierten Benutzer an Sitzungen für beständigen Chat beteiligt sind, wobei Folgendes gilt:

  - Durchschnittlich 1,5 Chatrooms pro Benutzer

  - Jeder Chatroom führt zu 12 Abrufanforderungen pro Stunde, mit einem Zielwert von durchschnittlich je 10 Benutzern

</div>

<div>

## <a name="response-group-and-call-park"></a>Reaktionsgruppe und Parken von Anrufen

Es wird davon ausgegangen, dass 0,15 % der registrierten Benutzer Reaktionsgruppen angehören. Außerdem wird davon ausgegangen, dass 0,02 % der registrierten Benutzer zu einem bestimmten Zeitpunkt Anrufe parken.

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Einführung'
TOCTitle: Einführung in Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398795(v=OCS.15)
ms:contentKeyID: 49294860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einführung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Lync Server 2013 und die zugehörige Clientsoftware, beispielsweise Lync 2013, bieten Benutzern neue Möglichkeiten, miteinander in Verbindung zu treten und in Verbindung zu bleiben - unabhängig von ihrem physischen Standort. Mit Lync und Lync Server werden verschiedene Möglichkeiten der Kommunikation in einer einzelnen Benutzeroberfläche kombiniert, als einheitliche Plattform bereitgestellt und über eine einzige Verwaltungsinfrastruktur verwaltet.

In dieser Tabelle und den folgenden Abschnitten werden die Hauptfunktionen oder *Arbeitsauslastungen* beschrieben, die Lync Server Ihren Benutzern bietet.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Arbeitsauslastung</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Instant Messaging und Anwesenheit</p></td>
<td><p>Instant Messaging und Anwesenheitsinformationen unterstützen Benutzer bei der effizienten Suche und Kommunikation.</p>
<p>Die Chatnachrichtenfunktion bietet eine Instant Messaging-Plattform mit Unterhaltungsverlauf und unterstützt Verbindungen mit öffentlichen Chatdiensten für Benutzer öffentlicher Chatnetzwerke wie z. B. MSN/Windows Live, Yahoo!, AOL und Google Talk.</p>
<div>

> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>


</div>
<p>Anhand von Anwesenheitsinformationen wird die persönliche Verfügbarkeit und Bereitschaft eines Benutzers zur Kommunikation widergespiegelt, beispielsweise mithilfe von gängigen Statuswerten wie <strong>Verfügbar</strong> oder <strong>Beschäftigt</strong> oder ausführlicheren Statuswerten, wie <strong>Bin gleich zurück</strong> und <strong>Nicht stören</strong> . Anhand dieser Anwesenheitsinformationen können andere Benutzer sofort effektive Kommunikationsentscheidungen treffen.</p></td>
</tr>
<tr class="even">
<td><p>Konferenzen</p></td>
<td><p>Lync Server bietet Unterstützung für Chatkonferenzen, Audiokonferenzen, Webkonferenzen, Videokonferenzen und Anwendungsfreigabe, sowohl für geplante als auch für spontane Besprechungen. Sämtliche dieser Besprechungstypen werden mit einem einzigen Client unterstützt. Lync Server bietet außerdem Unterstützung für Einwahlkonferenzen, sodass Benutzer mit Festnetztelefonen (Public Switched Telephone Network, PSTN) an der Audioübertragung einer Konferenz teilnehmen können.</p>
<p>Konferenzen können nahtlos geändert und in Echtzeit ausgeweitet werden. Beispielsweise kann eine einzelne Konferenz lediglich als Austausch von Chatnachrichten zwischen einigen wenigen Benutzern beginnen und sich zu einer Audiokonferenz mit Desktopfreigabe und einem größeren Publikum entwickeln - sofort, einfach, und ohne Unterbrechung der Unterhaltung.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP</p></td>
<td><p><em>Enterprise-VoIP</em> ist die VoIP-Funktion (Voice over Internet Protocol) in Lync Server. Sie bietet eine Sprachoption zum Erweitern oder Ersetzen herkömmlicher Nebenstellensysteme (Private Branch Exchange, PBX). Zusätzlich zu den umfangreichen Telefoniefunktionen einer IP-Nebenstellenanlage bietet Enterprise-VoIP zahlreiche integrierte Funktionen für Anwesenheitsstatus, Instant Messaging, Zusammenarbeit und Besprechungen. Funktionen wie beispielsweise das Beantworten, Halten, Wiederaufnehmen, Übergeben, Weiter- und Umleiten von Anrufen werden direkt unterstützt, während personalisierte Schnellwahltasten durch Kontaktlisten und die automatische Gegensprechanlage durch Chatnachrichten ersetzt werden.</p>
<p>Enterprise-VoIP unterstützt Hochverfügbarkeit durch Anrufsteuerung, grundlegende Telefondienste für Zweigstellen (Survivable Branch Appliances) und erweiterte Optionen für die Ausfallsicherheit von Daten.</p></td>
</tr>
<tr class="even">
<td><p>Unterstützung für Remotebenutzer</p></td>
<td><p>Sie können vollständige Lync Server-Funktionalität für Benutzer bereitstellen, die sich zurzeit außerhalb der Organisationsfirewall befinden, indem Sie sogenannte <em>Edgeserver</em> zur Verbindungsherstellung für diese Remotebenutzer einsetzen. Diese Remotebenutzer können über einen PC mit Lync 2013, über das Telefon oder eine Webschnittstelle an Konferenzen teilnehmen.</p>
<p>Die Bereitstellung von Edgeservern ermöglicht das Einrichten eines <em>Partnerverbunds</em> mit Partner- oder Lieferantenorganisationen. Eine Partnerverbundbeziehung ermöglicht Ihren Benutzern, Partnerbenutzer zu ihren Kontaktlisten hinzuzufügen, Anwesenheitsinformationen und Chatnachrichten mit diesen Benutzern auszutauschen und sie zu Audioanrufen, Videoanrufen und Konferenzen einzuladen.</p></td>
</tr>
<tr class="odd">
<td><p>Unterstützung für mobile Clients</p></td>
<td><p>Zusätzlich zu den Lync Server-Mobilitätsdiensten können Ihre Benutzer auf Lync-Funktionen zugreifen, wenn unterstützte Geräte eingesetzt werden (Apple iOS, Android, Windows Phone oder Nokia): Aktionen wie das Senden und Empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit durchführen. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftlich Anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Es werden auch Pushbenachrichtigungen für mobile Geräte unterstützt, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen.</p></td>
</tr>
<tr class="even">
<td><p>Integration in andere Produkte</p></td>
<td><p>Lync Server ermöglicht eine Integration in andere Produkte, um Ihren Benutzern und Administratoren zusätzliche Vorteile zu bieten.</p>
<p>Besprechungstools werden in Outlook integriert, um Besprechungsorganisatoren die Planung von Besprechungen oder das Abhalten spontaner Besprechungen mit nur einem Klick zu ermöglichen - ebenso wie die Teilnehmer ebenfalls mit nur einem Klick einer Besprechung beitreten können.</p>
<p>Anwesenheitsinformationen sind in Outlook und SharePoint integriert.</p>
<p>Exchange Unified Messaging (UM) bietet verschiedene Integrationsfunktionen. Benutzer können in Lync Server sehen, ob sie neue Voicemailnachrichten erhalten haben. Sie können auf eine Wiedergabeschaltfläche in der Outlook-Nachricht klicken, um die Audiovoicemail abzuhören, oder eine Transkription der Voicemailnachricht als Benachrichtigung anzeigen.</p>
<p>Das Ausführen von Lync Server 2013 mit Exchange 2013 aktiviert außerdem verschiedene neue Funktionen, wie den einheitlichen Kontaktspeicher, auf den Clients beider Produkte zugreifen können, sowie hochauflösende Fotos für Kontakte, die in der Exchange 2013-Datenbank gespeichert werden.</p></td>
</tr>
<tr class="odd">
<td><p>Einfache Bereitstellung</p></td>
<td><p>Zur einfacheren Planung und Bereitstellung Ihrer Server und Clients bietet Lync Server den Topologie-Generator.</p>
<p></p>
<p>Der Topologie-Generator ist eine Installationskomponente von Lync Server. Sie verwenden den Topologie-Generator, um Ihre geplante Topologie zu erstellen, anzupassen und zu veröffentlichen. Darüber hinaus überprüft der Topologie-Generator Ihre Topologie, bevor Sie mit den Serverinstallationen beginnen. Wenn Sie Lync Server auf einzelnen Servern installieren, stellt das Installationsprogramm die Server wie in der Topologie angegeben bereit.</p></td>
</tr>
<tr class="even">
<td><p>Einfache Verwaltung</p></td>
<td><p>Nach der Bereitstellung von Lync Server stehen Ihnen die folgenden leistungsstarken Tools für eine optimale Verwaltung zur Verfügung:</p>
<ul>
<li><p>Zentrale Konfigurationsverwaltung, mit der Sie Änderungen zentral verwalten und diese schnell für die gesamte Bereitstellung replizieren können.</p></li>
<li><p>Die Lync Server-Systemsteuerung, eine webbasierte grafische Benutzeroberfläche für Administratoren. Mit dieser webbasierten Benutzeroberfläche können Lync Server-Administratoren ihre Systeme von einem beliebigen Standort im Unternehmensnetzwerk verwalten, ohne dass auf ihren Computern eine spezielle Verwaltungssoftware installiert werden muss.</p></li>
<li><p>Die Lync Server-Verwaltungsshell, ein Befehlszeilentool, das auf der Windows PowerShell-Befehlszeilenschnittstelle basiert. Es bietet einen umfangreichen Befehlssatz für die Verwaltung aller Produktaspekte und ermöglicht Lync Server-Administratoren die Automatisierung wiederholt ausgeführter Aufgaben mit einem vertrauten Tool.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Während die Instant Messaging- und Anwesenheitsfunktionen automatisch für jede Lync Server-Bereitstellung installiert werden, können Sie entscheiden, ob Konferenzfunktion, Enterprise-VoIP und Remotebenutzerzugriff bereitgestellt werden, um die Bereitstellung genau an die Anforderungen Ihrer Organisation anzupassen.

## In diesem Abschnitt

  - [Chat und Anwesenheit in Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Konferenzen in Lync Server 2013](lync-server-2013-conferencing.md)

  - [Enterprise-VoIP in Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Skalierbarkeit mit Lync Server 2013](lync-server-2013-scalability.md)


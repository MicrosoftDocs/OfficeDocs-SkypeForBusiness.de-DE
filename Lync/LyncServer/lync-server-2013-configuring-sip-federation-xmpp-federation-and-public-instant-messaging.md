---
title: 'Lync Server 2013: Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat'
TOCTitle: Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205134(v=OCS.15)
ms:contentKeyID: 49294999
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Mithilfe von Verbünden, Verbindungen mit öffentlichen Instant Messaging-Diensten und XMPP (Extensible Messaging and Presence Protocol) wird eine andere Klasse externer Benutzer definiert - Verbundbenutzer. Die Benutzer einer Lync Server-Verbundbereitstellung oder einer XMPP-Bereitstellung haben Zugriff auf beschränkte Dienste und werden durch die externe Bereitstellung authentifiziert. Remotebenutzer sind Mitglieder Ihrer Lync Server-Bereitstellung, und sie haben Zugriff auf alle Dienste, die durch die Bereitstellung angeboten werden.


> [!NOTE]
> Für AOL und Yahoo! wurde die Einstellung des Diensts für Juni 2014 angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.



Bei der Verbindung mit öffentlichen Instant Messaging-Diensten handelt es sich um einen speziellen Typ des Verbunds, der einem Lync Server-Client den Zugriff auf konfigurierte Partner des öffentlichen Instant Messaging-Diensts mit dem Lync 2013 ermöglicht. Die aktuellen Partner für Verbindungen mit öffentlichen Instant Messaging-Diensten lauten wie folgt:

  - America Online

  - Windows Live

  - Yahoo\!

Mithilfe einer Konfiguration der Verbindungen mit öffentlichen Instant Messaging-Diensten können Lync-Benutzer wie folgt auf Benutzer von Verbindungen mit öffentlichen Instant Messaging-Diensten zugreifen:

  - Instant Messaging und Anwesenheit

  - Sichtbarkeit von Kontakten für Verbindungen mit öffentlichen Instant Messaging-Diensten im Lync-Client

  - Chatnachrichtenunterhaltungen zwischen Personen mit Kontakten

  - Audio- und Videoanrufe mit Windows Live-Benutzern

Mithilfe des Lync Server-Verbunds wird eine Vereinbarung zwischen Ihrer Lync Server-Bereitstellung und anderen Bereitstellungen von Office Communications Server 2007 R2 oder Lync Server definiert. Mithilfe einer Lync Server-Verbundkonfiguration können Lync-Benutzer wie folgt auf Verbundbenutzer zugreifen:

  - Instant Messaging und Anwesenheit

  - Erstellung von Verbundkontakten im Lync-Client

Mithilfe des XMPP-Verbunds wird eine externe Bereitstellung definiert, die auf dem Extensible Messaging and Presence Protocol basiert. Mithilfe einer XMPP-Konfiguration können Lync-Benutzer wie foglt auf zulässige XMPP-Domänenbenutzer zugreifen:

  - Instant Messaging und Anwesenheit - nur zwischen Personen

  - Erstellung von XMPP-Verbundkontakten im Lync-Client


> [!IMPORTANT]
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



## Externer Edgeserver-Verbund, Verbindungen für öffentliche Instant Messaging-Diensten und Bereitstellungsprozess für XMPP-Benutzer


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Berechtigungen</th>
<th>Dokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bestimmen Sie die Optionen, die der vorhandenen Edgebereitstellung hinzugefügt werden sollen</p></td>
<td><p>Führen Sie den Topologie-Generator aus, um die Edgeservereinstellungen zu bearbeiten und die Topologie zu erstellen und zu veröffentlichen. Die vorhandene Edgetopologie repliziert Ändeurngen vom zentralen Verwaltungsspeicher auf den Edgeserver.</p></td>
<td><p>Gruppe &quot;Domänen-Admins&quot; und Gruppe &quot;RTCUniversalServerAdmins&quot;</p>
<div>

> [!NOTE]
> Sie können eine Topologie unter Verwendung eines Kontos bearbeiten, das Mitglied der lokalen Benutzergruppe ist. Für die Veröffentlichung einer Topologie ist jedoch ein Konto erforderlich, das Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" ist.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge- und Director-Topologie in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Bereiten Sie das Setup vor</p></td>
<td><ol>
<li><p>Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</p></li>
<li><p>Konfigurieren Sie interne und externe DNS-Einträge, um die Verbindung mit öffentlichen Instant Messaging-Diensten, Lync-Verbünde und XMPP-Verbünde zu unterstützen</p></li>
<li><p>Konfigurieren Sie Ports und Protokolle an der Firewall für die Unterstützung der von Ihnen bereitgestellten Verbundtypen</p></li>
<li><p>Fordern Sie öffentliche Zertifikate an, und installieren Sie sie. Die zum Anfordern von Zertifikaten erforderliche Zeit hängt davon ab, welche Zertifizierungstelle das Zeritfikat ausstellt. Dieser Schritt ist an dieser Stelle in der Bereitstellung optional. Wenn Sie diesen Schritt nicht zu diesem Zeitpunkt ausführen, müssen Sie dies bei der Edgeserverkonfiguration tun. Der Edgeserverdienst kann erst gestartet werden, nachdem die Zertifikate angefordert wurden</p></li>
</ol>
<p></p></td>
<td><p>Wie für Ihre Organisation angemessen, da diese Rollen normalerweise unter zahlreichen Arbeitsgruppen aufgeteilt werden</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planen für SIP-, XMPP-Partnerverbund und öffentliche Chats in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Richten Sie Edgeserver für Verbundszenarien ein</p></td>
<td><ol>
<li><p>Transportieren Sie die exportierte Topologiekonfigurationsdatei zu den einzelnen Edgeservern, oder schließen Sie die Replikation ab</p></li>
<li><p>Führen Sie den Bereitstellungs-Assistenten erneut aus, um Unterstützungskomponenten für den Verbund zu installieren</p></li>
<li><p>Konfigurieren Sie die Edgeserver</p></li>
<li><p>Fordern Sie für jeden Edgeserver Zertifikate an, und installieren Sie sie</p></li>
<li><p>Starten Sie die Edgeserverdienste neu</p></li>
</ol></td>
<td><p>Gruppe Administratoren</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Einrichten eines Lync-Partnerverbunds in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Einrichten der öffentlichen Chatkonnektivität in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Einrichten eines XMPP-Partnerverbunds in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Unterstützung des externen Benutzerzugriffs.</p></td>
<td><ol>
<li><p>Verwenden Sie den externen Benutzerzugriff für Lync Server-Systemsteuerung</p></li>
<li><p>Konfigurieren Sie die Richtlinie für den externen Zugriff, um die Kommunikation mit Verbundbenutzern oder öffentlichen Benutzern zu ermöglichen</p></li>
<li><p>Konfigurieren Sie SIP-Verbunddomänen für die Zulassung oder Blockierung von Domänen</p></li>
<li><p>Aktivieren Sie SIP-Verbundanbieter für Anbieter von Verbindungen mit öffentlichen Instant Messaging-Diensten</p></li>
<li><p>Konfigurieren Sie XMPP-Verbundpartner nach XMPP-Domäne</p></li>
</ol></td>
<td><p>Gruppe RTCUniversalServerAdmins oder Benutzerkonto mit zugewiesener Rolle CSAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen Sie die Edgeserverkonfiguration</p></td>
<td><p>Überprüfen Sie die Serverbindung und Replikation von Konfigurationsdaten von internen Servern</p></td>
<td><p>Für die Überprüfung der Replikation, der Gruppe &quot;RTCUniversalServerAdmins&quot; oder des Benutzerkontos, das der Rolle &quot;CSAdministrator&quot; zugeordnet ist. Für die Überprüfung der Benutzerkonnektivität, ein Benutzer für jeden Verbundbenutzertyp</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edgebereitstellung in Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</a></p></td>
</tr>
</tbody>
</table>


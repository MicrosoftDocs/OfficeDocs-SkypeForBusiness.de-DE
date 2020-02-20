---
title: Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und öffentlicher Chatnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d21f2c094eb7b5c342c31387b6732a2565f01197
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Chatnachrichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Mithilfe von Verbünden, Verbindungen mit öffentlichen Sofortnachrichtendiensten und XMPP (Extensible Messaging and Presence Protocol) wird eine andere Klasse externer Benutzer definiert – Verbundbenutzer. Benutzer einer Verbund lync Server-Bereitstellung oder der XMPP-Bereitstellung haben Zugriff auf eine beschränkte Anzahl von Diensten und werden von der externen Bereitstellung authentifiziert. Remote Benutzer sind Mitglieder ihrer lync Server-Bereitstellung und haben Zugriff auf alle Dienste, die von Ihrer Bereitstellung angeboten werden.

<div>


> [!NOTE]
> Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.



</div>

Die Verbindung mit öffentlichen Instant Messaging-Diensten ist ein spezieller Verbundtyp, mit dem ein lync Server-Client mit dem lync 2013 auf konfigurierte öffentliche Chatpartner zugreifen kann. Die aktuellen Partner für Verbindungen mit öffentlichen Sofortnachrichtendiensten lauten wie folgt:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

Mithilfe einer Konfiguration der Verbindungen mit öffentlichen Sofortnachrichtendiensten können Lync-Benutzer wie folgt auf Benutzer von Verbindungen mit öffentlichen Sofortnachrichtendiensten zugreifen:

  - Sofortnachrichten und Anwesenheit

  - Sichtbarkeit von Kontakten für Verbindungen mit öffentlichen Sofortnachrichtendiensten im Lync-Client

  - Sofortnachrichtenunterhaltungen zwischen Personen mit Kontakten

  - Audio- und Videoanrufe mit Windows Live-Benutzern

Mithilfe des Lync Server-Verbunds wird eine Vereinbarung zwischen Ihrer Lync Server-Bereitstellung und anderen Bereitstellungen von Office Communications Server 2007 R2 oder Lync Server definiert. Mithilfe einer Lync Server-Verbundkonfiguration können Lync-Benutzer wie folgt auf Verbundbenutzer zugreifen:

  - Instant Messaging und Anwesenheit

  - Erstellung von Verbundkontakten im Lync-Client

Mithilfe des XMPP-Verbunds wird eine externe Bereitstellung definiert, die auf dem Extensible Messaging and Presence Protocol basiert. Mithilfe einer XMPP-Konfiguration können Lync-Benutzer wie foglt auf zulässige XMPP-Domänenbenutzer zugreifen:

  - Instant Messaging und Anwesenheit – nur zwischen Personen

  - Erstellung von XMPP-Verbundkontakten im Lync-Client

<div>


> [!IMPORTANT]
> Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Externer Edgeserver-Verbund, Verbindungen für öffentliche Sofortnachrichtendienste und Bereitstellungsprozess für XMPP-Benutzer


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
<td><p>Führen Sie den Topologie-Generator aus, um Edgeserver Einstellungen zu bearbeiten und die Topologie zu erstellen und zu veröffentlichen. Durch Ihre vorhandene Edge-Topologie werden Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver repliziert.</p></td>
<td><p>Gruppe "Domänen-Admins" und Gruppe "RTCUniversalServerAdmins"</p>



> [!NOTE]
> Sie können eine Topologie unter Verwendung eines Kontos bearbeiten, das Mitglied der lokalen Benutzergruppe ist. Für die Veröffentlichung einer Topologie ist jedoch ein Konto erforderlich, das Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" ist.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge-und Director-Topologie in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Bereiten Sie das Setup vor</p></td>
<td><ol>
<li><p>Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</p></li>
<li><p>Konfigurieren Sie interne und externe DNS-Einträge, um die Verbindung mit öffentlichen Sofortnachrichtendiensten, Lync-Verbünde und XMPP-Verbünde zu unterstützen</p></li>
<li><p>Konfigurieren Sie Ports und Protokolle an der Firewall für die Unterstützung der von Ihnen bereitgestellten Verbundtypen</p></li>
<li><p>Fordern Sie öffentliche Zertifikate an, und installieren Sie sie. Die zum Anfordern von Zertifikaten erforderliche Zeit hängt davon ab, welche Zertifizierungstelle das Zeritfikat ausstellt. Dieser Schritt ist an dieser Stelle in der Bereitstellung optional. Wenn Sie diesen Schritt nicht zu diesem Zeitpunkt ausführen, müssen Sie dies bei der Edgeserverkonfiguration tun. Der Edgeserverdienst kann erst gestartet werden, nachdem die Zertifikate angefordert wurden</p></li>
</ol></td>
<td><p>Wie für Ihre Organisation angemessen, da diese Rollen normalerweise unter zahlreichen Arbeitsgruppen aufgeteilt werden</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</a></p></td>
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
<td><p>Administratorgruppe</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Einrichten von lync Federation in lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Einrichten der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Einrichten des XMPP-Verbunds in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Unterstützung des externen Benutzerzugriffs.</p></td>
<td><ol>
<li><p>Verwenden des lync Server-Systemsteuerung Zugriffs durch externe Benutzer</p></li>
<li><p>Konfigurieren Sie die Richtlinie für den externen Zugriff, um die Kommunikation mit Verbundbenutzern oder öffentlichen Benutzern zu ermöglichen</p></li>
<li><p>Konfigurieren Sie SIP-Verbunddomänen für die Zulassung oder Blockierung von Domänen</p></li>
<li><p>Aktivieren Sie SIP-Verbundanbieter für Anbieter von Verbindungen mit öffentlichen Sofortnachrichtendiensten</p></li>
<li><p>Konfigurieren Sie XMPP-Verbundpartner nach XMPP-Domäne</p></li>
</ol></td>
<td><p>Gruppe "RTCUniversalServerAdmins" oder Benutzerkonto, das der Rolle "CSAdministrator" zugeordnet ist</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen Sie die Edgeserverkonfiguration</p></td>
<td><p>Überprüfen Sie die Serverbindung und Replikation von Konfigurationsdaten von internen Servern</p></td>
<td><p>Für die Überprüfung der Replikation, der Gruppe "TCUniversalServerAdmins" oder des Benutzerkontos, das der Rolle "CSAdministrator" zugeordnet ist. Für die Überprüfung der Benutzerkonnektivität, ein Benutzer für jeden Verbundbenutzertyp</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edge-Bereitstellung in lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


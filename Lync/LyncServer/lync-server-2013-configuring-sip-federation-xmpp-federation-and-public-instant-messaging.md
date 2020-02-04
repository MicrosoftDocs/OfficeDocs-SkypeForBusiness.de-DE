---
title: Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat
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
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Föderation, öffentliche Instant Messaging-Konnektivität und XMPP (Extensible Messaging and Presence Protocol) definieren eine andere Klasse externer Benutzer – Föderationsbenutzer. Benutzer einer Föderations-lync Server-Bereitstellung oder XMPP-Bereitstellung haben Zugriff auf eine begrenzte Anzahl von Diensten und werden von der externen Bereitstellung authentifiziert. Remote Benutzer sind Mitglieder ihrer lync Server-Bereitstellung und haben Zugriff auf alle Dienste, die von Ihrer Bereitstellung angeboten werden.

<div>


> [!NOTE]
> Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.



</div>

Die öffentliche Instant Messaging-Konnektivität ist ein spezieller Föderations, mit dem ein lync Server-Client über lync 2013 auf konfigurierte öffentliche Instant Messaging-Partner zugreifen kann. Die aktuellen öffentlichen Instant Messaging-Verbindungspartner sind:

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

Eine öffentliche Instant Messaging-Verbindungskonfiguration ermöglicht lync-Benutzern den Zugriff auf öffentliche Instant Messaging-Konnektivitäts-Benutzer durch:

  - Chat und Anwesenheit

  - Sichtbarkeit der öffentlichen Chat-Verbindungs Kontakte in lync-Client

  - Chat Unterhaltungen für Personen mit Kontakten

  - Audio-und Videoanrufe mit Windows Live-Benutzern

Der lync Server-Verbund definiert eine Vereinbarung zwischen Ihrer lync Server-Bereitstellung und anderen Office Communications Server 2007 R2-oder lync Server-Bereitstellungen. Eine lync Server-Verbund Konfiguration ermöglicht lync-Benutzern den Zugriff auf Verbundbenutzer durch:

  - Chat und Anwesenheit

  - Erstellen von verbundkontakten im lync-Client

Die XMPP-Föderation definiert eine externe Bereitstellung auf der Grundlage des erweiterbaren Messaging-und Anwesenheits Protokolls. Eine XMPP-Konfiguration ermöglicht lync-Benutzern den Zugriff auf zulässige XMPP-Domänenbenutzer durch:

  - Chat und Anwesenheit – nur Person zu Person

  - Erstellen von XMPP-verbundkontakten im lync-Client

<div>


> [!IMPORTANT]
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Edge-Server-externer Verbund, öffentliche Instant Messaging-Konnektivität und Bereitstellungsprozess für XMPP-Benutzer


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
<td><p>Bestimmen der Optionen, die der vorhandenen Edge-Bereitstellung hinzugefügt werden sollen</p></td>
<td><p>Führen Sie den Topologie-Generator aus, um die Edge-Server Einstellungen zu bearbeiten und die Topologie zu erstellen und zu veröffentlichen. Durch Ihre vorhandene Edge-Topologie werden Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver repliziert.</p></td>
<td><p>Gruppe "Domänen-Admins" und RTCUniversalServerAdmins-Gruppe</p>



> [!NOTE]
> Sie können eine Topologie mit einem Konto bearbeiten, das ein Mitglied der Gruppe "lokale Benutzer" ist, aber die Veröffentlichung einer Topologie erfordert ein Konto, das ein Mitglied der Gruppe "Domain Admins" und der Gruppe "RTCUniversalServerAdmins" ist.

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge- und Director-Topologie in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vorbereiten des Setups</p></td>
<td><ol>
<li><p>Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</p></li>
<li><p>Konfigurieren interner und externer DNS-Einträge zur Unterstützung der öffentlichen Instant Messaging-Konnektivität, lync Federation und XMPP Federation</p></li>
<li><p>Konfigurieren von Ports und Protokollen in der Firewall zur Unterstützung der von Ihnen bereitgestellten Föderations Typen</p></li>
<li><p>Abrufen und installieren öffentlicher Zertifikate. Die zum Abrufen von Zertifikaten erforderliche Zeit hängt davon ab, welche Zertifizierungsstelle das Zertifikat ausgibt. Dieser Schritt ist an diesem Punkt in der Bereitstellung optional. Wenn Sie diesen Schritt an diesem Punkt nicht ausführen, müssen Sie dies während der Edgeserver-Konfiguration tun. Der Edge-Server Dienst kann erst gestartet werden, nachdem Zertifikate abgerufen wurden.</p></li>
</ol></td>
<td><p>Entsprechend Ihrer Organisation, da diese Rollen in der Regel auf zahlreiche Arbeitsgruppen aufgeteilt sind</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Einrichten von Edgeserver für Verbundszenarien</p></td>
<td><ol>
<li><p>Transportieren der exportierten Topologie-Konfigurationsdatei auf jeden Edgeserver oder zulassen der vollständigen Replikation</p></li>
<li><p>Erneutes Ausführen des Bereitstellungs-Assistenten, um unterstützende Komponenten für den Verbund zu installieren</p></li>
<li><p>Konfigurieren der Edgeserver</p></li>
<li><p>Anfordern und Installieren von Zertifikaten für jeden Edgeserver</p></li>
<li><p>Starten Sie die Edge-Server Dienste neu</p></li>
</ol></td>
<td><p>Gruppe "Administratoren"</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Einrichten eines Lync-Partnerverbunds in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Einrichten der öffentlichen Chatkonnektivität in Lync Server 2013</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Einrichten eines XMPP-Partnerverbunds in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Unterstützung für den Zugriff durch externe Benutzer.</p></td>
<td><ol>
<li><p>Verwenden des externen Benutzerzugriffs in der lync Server-Systemsteuerung</p></li>
<li><p>Konfigurieren der Richtlinie für den externen Zugriff, um die Kommunikation mit Verbundbenutzern oder öffentlichen Benutzern zu ermöglichen</p></li>
<li><p>Konfigurieren von SIP-Verbunddomänen zum Zulassen oder Blockieren von Domänen</p></li>
<li><p>Aktivieren von SIP-Verbund Anbietern für öffentliche Instant Messaging-Verbindungsanbieter</p></li>
<li><p>Konfigurieren von XMPP-Verbundpartnern pro XMPP-Domäne</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins-Gruppe oder ein Benutzerkonto, das der CSAdministrator-Rolle zugewiesen ist</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Edgeserver-Konfiguration</p></td>
<td><p>Überprüfen der Serverkonnektivität und Replikation von Konfigurationsdaten von internen Servern</p></td>
<td><p>Zur Überprüfung der Replikation, der RTCUniversalServerAdmins-Gruppe oder des Benutzerkontos, das der CSAdministrator-Verb Verifizierung der Benutzerkonnektivität zugewiesen ist, wird ein Benutzer für jeden Typ von Verbundbenutzer</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edgebereitstellung in Lync Server 2013</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Beispiel für eine XMPP-Konfiguration in Lync Server 2013 – XMPP-Partnerverbund mit Google Talk</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


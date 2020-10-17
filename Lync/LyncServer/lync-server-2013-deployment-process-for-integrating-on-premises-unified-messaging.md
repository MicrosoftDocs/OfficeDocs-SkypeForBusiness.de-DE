---
title: Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Funktionen
description: Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Funktionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1b8f528edb970893198ed06b821535a398f09d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569521"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Bereitstellungsprozess für die Integration von lokalen Unified Messaging-und lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-12-17_

Wenn Sie Exchange Unified Messaging (um) mit lync Server 2013 integrieren möchten, müssen Sie die in diesem Thema beschriebenen Aufgaben ausführen. Stellen Sie außerdem sicher, dass Sie die in [Richtlinien für die Integration lokaler Unified Messaging und lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)beschriebenen bewährten Methoden für die Planung und Bereitstellung lesen. In diesem Thema wird davon ausgegangen, dass Sie lync Server 2013 mit einem zusammengefassten Vermittlungsserver bereitgestellt haben und Benutzer für lync Server 2013 aktiviert haben, aber nicht unbedingt, dass Sie alle Bereitstellungs-und Konfigurationsschritte zur Aktivierung von Enterprise-VoIP ausgeführt haben, wie unter [Deploying Enterprise Voice in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation beschrieben.

<div>

## <a name="unified-messaging-integration-process"></a>Integrationsprozess für Unified Messaging (UM)

<div>


> [!IMPORTANT]
> Es ist wichtig, dass Sie sich mit den Exchange-Administratoren Ihrer Organisation abstimmen, um die Aufgaben zu bestätigen, die von Ihnen durchgeführt werden, um eine reibungslose und erfolgreiche Integration zu ermöglichen.



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
<th>Phase</th>
<th>Schritte</th>
<th>Erforderliche Gruppen und Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stellen Sie eine der folgenden Exchange-Versionen bereit:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) oder neuestes Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 oder neuestes Service Pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Wenn Sie Microsoft Exchange Server 2013 verwenden, installieren Sie die folgenden Exchange Server Rollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</p>
<ul>
<li><p>Clientzugriff</p></li>
<li><p>Postfach</p></li>
</ul>
<p>Wenn Microsoft Exchange Server 2013 und Exchange Unified Messaging (um) in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013 Gesamtstruktur vertraut.</p>
<p>Wenn Sie Exchange 2010 verwenden, installieren Sie die folgenden Exchange Server Rollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</p>
<ul>
<li><p>Unified Messaging</p></li>
<li><p>Hub-Transport</p></li>
<li><p>Clientzugriff</p></li>
<li><p>Postfach</p></li>
</ul>
<p>Wenn lync Server 2013 und Exchange Unified Messaging (um) in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013 Gesamtstruktur vertraut.</p></td>
<td><p>Organisations-Admins (wenn es sich um den ersten Exchange Server in der Organisation handelt)</p>
<p>– ODER –</p>
<p>Exchange-Organisationsadministrator (wenn es sich nicht um den ersten Exchange Server in der Organisation handelt)</p></td>
<td><p>Weitere Informationen finden Sie in der Dokumentation zur jeweiligen Version von Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 Bereitstellungsdokumentation unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> .</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 oder neueste Service Pack-Bereitstellungsdokumentation unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> .</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 Planung und Bereitstellung bei <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> .</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installieren Sie Zertifikate.</p></td>
<td><p>Herunterladen und Installieren von Zertifikaten für jeden Exchange um Server von einer vertrauenswürdigen Stammzertifizierungsstelle (Certification Authority, ca). Die Zertifikate sind für MTLS (Mutual Transport Level Security) zwischen den Servern mit Exchange um und lync Server 2013 erforderlich.</p></td>
<td><p>Administratoren</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft</a></p></td>
</tr>
<tr class="odd">
<td><p>Erstellen und konfigurieren Sie einen neuen Exchange um SIP-Wähleinstellungen.</p></td>
<td><p>Erstellen Sie auf dem Exchange um Server einen SIP-Wählplan basierend auf den spezifischen Bereitstellungsanforderungen Ihrer Organisation.</p></td>
<td><p>Exchange-Organisationsadministrator</p></td>
<td><p>Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden Sie unter &quot; Erstellen eines Unified Messaging-SIP-URI-Wähl Plans unter &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> .</p>
<p>Informationen zum Exchange 2010 oder neuesten Service Pack finden Sie unter &quot; Erstellen eines um-Wähl Plans &quot; unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> .</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified Messaging unter <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie Sicherheitseinstellungen für den Exchange um SIP-Wählplan.</p></td>
<td><p>Um Enterprise-VoIP-Datenverkehr zu verschlüsseln, konfigurieren Sie die Sicherheitseinstellungen im Exchange um SIP-Wählplan als <strong>SIP-gesichert</strong> oder <strong>abgesichert</strong>. Dies ist ein besonders wichtiger Schritt, wenn Sie lync Phone Edition-Geräte in Ihrer Umgebung bereitgestellt oder geplant haben. Damit lync Phone Edition-Geräte in einer Umgebung mit Exchange um Integration funktionieren, müssen lync Server Verschlüsselungseinstellungen mit den Sicherheitseinstellungen für den Exchange um Wählplan übereinstimmen. Ausführliche Informationen zu diesem Thema finden Sie in der Bereitstellungsdokumentation.</p></td>
<td><p>Exchange-Organisationsadministrator</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013</a></p>
<p>Informationen zu Exchange 2007 SP1 oder zum neuesten Service Pack finden Sie unter auch:</p>
<p>&quot;Konfigurieren der Sicherheit für einen Unified Messaging &quot; -Wählplan unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> .</p>
<p>Informationen zu Exchange 2010 oder neuestes Service Pack finden Sie auch hier:</p>
<p>&quot;Konfigurieren Sie VoIP-Sicherheit für einen um &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> -Wählplan.</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified Messaging unter <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="odd">
<td><p>Fügen Sie dem Exchange um SIP-Wähleinstellungen Unified Messaging-Server hinzu.</p></td>
<td><p>Wenn Sie einen neu installierten Unified Messaging-Server zur Entgegennahme und Verarbeitung eingehender Anrufe aktivieren möchten, müssen Sie den Unified Messaging-Server einem Satz mit UM-Wähleinstellungen hinzufügen. In diesem Fall fügen Sie den Server dem Exchange um SIP-Wähleinstellungen hinzu.</p></td>
<td><p>Administratoren</p>
<p>Exchange-Serveradministratoren</p></td>
<td><p>Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden Sie unter &quot; Hinzufügen von Unified Messaging-Server zu Wähleinstellungen unter &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> .</p>
<p>Informationen zum Exchange 2010 oder neuesten Service Pack finden Sie unter &quot; anzeigen oder Konfigurieren der Eigenschaften eines um &quot; -Servers unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> .</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified Messaging unter <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie Postfächer mit SIP-Adressen.</p></td>
<td><p>Weisen Sie den Postfächern von Enterprise-VoIP-Benutzern, die Exchange um-Features verwenden werden, SIP-Adressen zu.</p></td>
<td><p>Lync Server 2013 Administrator</p>
<p>Exchange-Empfängeradministrator</p></td>
<td><p>Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden Sie unter &quot; hinzufügen, entfernen oder Ändern einer SIP-Adresse für einen UM-Enabled-Benutzer &quot; unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> .</p>
<p>Informationen zum Exchange 2010 oder neuesten Service Pack finden Sie unter &quot; Ändern einer SIP-Adresse für einen UM-Enabled-Benutzer &quot; unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> .</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified Messaging unter <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="odd">
<td><p>Führen Sie das Skript "exchucutil.ps1" aus.</p></td>
<td><p>Öffnen Sie auf dem Server, auf dem Exchange um Dienste ausgeführt werden, das Exchange-Verwaltungsshell, und führen Sie das exchucutil.ps1-Skript aus, das Folgendes ausführt:</p>
<ul>
<li><p>Erteilt lync Server 2013 Berechtigung zum Lesen von Exchange um Active Directory-Domänendienste-Objekten, insbesondere die SIP-Wählpläne, die in der vorherigen Aufgabe erstellt wurden.</p></li>
<li><p>Erstellt ein Unified Messaging-IP-Gateway-Objekt in Active Directory für jeden lync Server 2013 Enterprise Edition-Pool oder Standard Edition-Server, der Benutzer hostet, die für Enterprise-VoIP aktiviert sind.</p></li>
<li><p>Erstellt für jedes Gateway eine Exchange um Sammelanschluss Gruppe. Die Pilot-ID des Sammelanschlusses ist der Name der Wähleinstellungen, die dem entsprechenden Gateway zugeordnet sind. Es muss sich um eine 1:1-Zuordnung handeln, wenn mehrere Sätze mit Wähleinstellungen verwendet werden.</p></li>
</ul></td>
<td><p>Exchange-Organisationsadministrator</p>
<p>Exchange-Empfängeradministrator</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von lync Server 2013 Wählplänen</p></td>
<td><p>Wenn Sie in Exchange 2007 SP1 oder das neueste Service Pack oder Exchange 2010 integrieren möchten, erstellen Sie einen neuen Enterprise-VoIP-Wählplan mit einem Namen, der dem vollqualifizierten Domänennamen (FQDN) des Exchange um Wähl Plans entspricht.</p>



> [!NOTE]
> Dies müssen Sie für die einzelnen um-Wähleinstellungen durchführen.


<p>Wenn Sie in Exchange 2010 SP1 integrieren, müssen Sie sicherstellen, dass geeignete Einstellungen für Enterprise-VoIP-Unternehmen auf globaler/Standortebene oder auf Poolebene konfiguriert wurden.</p>



> [!NOTE]
> Wenn Sie in Exchange 2010 SP1 integrieren, müssen die lync Server Wähleinstellungen und Exchange um Namen für den SIP-Wählplan nicht übereinstimmen.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Konfigurieren von Wählplänen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Führen Sie das Exchange um-integrationstool aus.</p></td>
<td><p>Führen Sie auf der lync Server 2013 <strong>ocsumutil.exe</strong>aus, die:</p>
<ul>
<li><p>Erstellen von Kontaktobjekten für Teilnehmerzugriff und automatische Telefonzentrale.</p></li>
<li><p>Überprüft, ob ein Enterprise-VoIP-Wählplan mit einem Namen vorhanden ist, der mit dem FQDN des Exchange um Wähl Plans übereinstimmt. Wenn Sie Exchange 2010 SP1 oder höher ausführen, müssen die Namen der Wähleinstellungen nicht übereinstimmen, und Sie können die Warnung des Tools zu diesem Thema ignorieren.</p></li>
</ul>
<p>Dieses Tool scannt die Active Directory auf Exchange um Einstellungen und ermöglicht es dem lync Server 2013 Administrator, Kontaktobjekte anzuzeigen, zu erstellen und zu bearbeiten.</p></td>
<td><p>RTCUniversalServerAdmins <em>und</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Zur erfolgreichen Ausführung von "ocsumutil.exe" muss der Benutzer beiden dieser Gruppe angehören.





> [!NOTE]
> Zum Erstellen von Kontaktobjekten muss der Benutzer, der "ocsumutil.exe" ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden. Diese Berechtigung kann durch Ausführen des Cmdlets <STRONG>Grant-CsOUPermission</STRONG> erteilt werden. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Führen Sie bei Bedarf weitere Schritte zur Enterprise-VoIP-Konfiguration aus.</p></td>
<td><p>Wenn Sie nicht bereits Enterprise-VoIP-Einstellungen für Ihre Server oder Benutzer konfiguriert haben, führen Sie eine oder mehrere der folgenden Aufgaben aus:</p>
<ul>
<li><p>Bereitstellen und Konfigurieren</p>
<p>PSTN-Gateways (Public Switched Telephone Network) und Vermittlungsserver</p></li>
<li><p>Definieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und ausgehenden Anrufrouten</p></li>
<li><p>Aktivieren von Benutzern für Enterprise-VoIP</p></li>
<li><p>(Optional) Konfigurieren von Wähleinstellungen für bestimmte Benutzer</p></li>
</ul>
<p>Je nach aktivierten Enterprise-VoIP-Funktionen ist möglicherweise die Ausführung weiterer Konfigurationsschritte erforderlich.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Siehe die Themen in den folgenden Abschnitten:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Aktivieren Sie Enterprise-VoIP-Benutzer für Exchange um.</p></td>
<td><p>Stellen Sie auf dem Exchange um Server sicher, dass eine Unified Messaging-Postfachrichtlinie erstellt wurde und dass jeder Benutzer über eine eindeutige Durchwahlnummer verfügt, und aktivieren Sie dann den Benutzer für Unified Messaging.</p></td>
<td><p>Exchange-Empfängeradministrator</p></td>
<td><p>Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden Sie unter &quot; Aktivieren eines Benutzers für Unified Messaging &quot; unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> .</p>
<p>Informationen zum Exchange 2010 oder neuesten Service Pack finden Sie unter &quot; Aktivieren eines Benutzers für Unified Messaging &quot; unter <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> .</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified Messaging unter <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten'
TOCTitle: Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425737(v=OCS.15)
ms:contentKeyID: 49293466
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie Exchange Unified Messaging (UM) in Lync Server 2013 integrieren möchten, müssen Sie die in diesem Thema beschriebenen Aufgaben ausführen. Lesen Sie außerdem die bewährten Methoden für die Planung und Bereitstellung, die unter [Richtlinien für die Integration lokaler Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md) erklärt werden. In diesem Thema wird davon ausgegangen, dass Sie Lync Server 2013 mit einem verbundenen Vermittlungsserver bereitgestellt und Benutzer für Lync Server 2013 aktiviert haben. Sie müssen aber nicht unbedingt alle Bereitstellungs- und Konfigurationsschritte zur Aktivierung von Enterprise-VoIP ausgeführt haben, wie unter [Bereitstellen von Enterprise-VoIP in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation beschrieben.

## Integrationsprozess für Unified Messaging (UM)


> [!IMPORTANT]
> Es ist wichtig, dass Sie sich bezüglich der durchzuführenden Aufgaben mit den Exchange-Administratoren in Ihrer Organisation absprechen, um eine nahtlose und erfolgreiche Integration sicherzustellen.




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
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) bzw. aktuelles Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 oder neuestes Service Pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Wenn Sie Microsoft Exchange Server 2013 verwenden, installieren Sie die folgenden Exchange Server-Rollen entweder in derselben Gesamtstruktur oder in einer anderen Gesamtstruktur als Lync Server 2013:</p>
<ul>
<li><p>Clientzugriff</p></li>
<li><p>Postfach</p></li>
</ul>
<p>Wenn Microsoft Exchange Server 2013 und Exchange Unified Messaging (UM) in unterschiedlichen Gesamtstrukturen installiert werden, muss für jede Exchange-Gesamtstruktur eine Vertrauensbeziehung mit der Lync Server 2013-Gesamtstruktur eingerichtet werden.</p>
<p>Wenn Sie Exchange 2010 verwenden, installieren Sie die folgenden Exchange Server-Rollen entweder in derselben Gesamtstruktur oder in einer anderen Gesamtstruktur als Lync Server 2013:</p>
<ul>
<li><p>Unified Messaging</p></li>
<li><p>Hub-Transport</p></li>
<li><p>Clientzugriff</p></li>
<li><p>Postfach</p></li>
</ul>
<p>Wenn Lync Server 2013 und Exchange Unified Messaging (UM) in unterschiedlichen Gesamtstrukturen installiert werden, muss für jede Exchange-Gesamtstruktur eine Vertrauensbeziehung mit der Lync Server 2013-Gesamtstruktur eingerichtet werden.</p></td>
<td><p>Organisations-Admins (wenn es sich um den ersten Exchange Server in der Organisation handelt)</p>
<p>- oder -</p>
<p>Exchange-Organisationsadministrator (wenn es sich nicht um den ersten Exchange Server in der Organisation handelt)</p></td>
<td><p>Weitere Informationen finden Sie in der Dokumentation zur jeweiligen Version von Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Bereitstellungsdokumentation zu Exchange Server 2007 <a href="http://go.microsoft.com/fwlink/p/?linkid=268694" class="uri">http://go.microsoft.com/fwlink/p/?linkid=268694</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>Bereitstellungsdokumentation zu Exchange 2010 oder neuestem Service Pack <a href="http://go.microsoft.com/fwlink/p/?linkid=268695" class="uri">http://go.microsoft.com/fwlink/p/?linkid=268695</a>.</p>
</dd>
<dt><span></span></dt>
<dd><p>Planung und Bereitstellung von Microsoft Exchange Server 2013<a href="http://go.microsoft.com/fwlink/p/?linkid=266569" class="uri">http://go.microsoft.com/fwlink/p/?linkid=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installieren Sie Zertifikate.</p></td>
<td><p>Laden Sie für alle Exchange UM-Server Zertifikate von einer vertrauenswürdigen Stammzertifizierungsstelle herunter, und installieren Sie die Zertifikate. Die Zertifikate sind erforderlich, damit TLS mit gegenseitiger Authentifizierung (Mutual Transport Layer Security, MTLS) zwischen den Exchange UM- und Lync Server 2013-Servern konfiguriert werden kann.</p></td>
<td><p>Administratoren</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird</a></p></td>
</tr>
<tr class="odd">
<td><p>Erstellen und konfigurieren Sie einen neuen Satz mit Exchange UM-SIP-Wähleinstellungen.</p></td>
<td><p>Erstellen Sie auf dem Exchange UM-Server einen SIP-Wählplan, der auf den spezifischen Bereitstellungsanforderungen Ihrer Organisation basiert.</p></td>
<td><p>Exchange-Organisationsadministrator</p></td>
<td><p>Informationen zur Vorgehensweise für Exchange 2007 SP1 oder neuestes Service Pack finden Sie auf der Seite &quot;Erstellen eines SIP-URI-Wählplans für Unified Messaging&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268632" class="uri">http://go.microsoft.com/fwlink/p/?linkid=268632</a>.</p>
<p>Informationen zur Vorgehensweise für Exchange 2010 oder neuestes Service Pack finden Sie auf der Seite &quot;Erstellen von UM-Wähleinstellungen&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?LinkId=268674</a>.</p>
<p>Schauen Sie für Exchange 2013 unter „Unified Messaging“ nach (<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>).</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie Sicherheitseinstellungen für die Exchange UM-SIP-Wähleinstellungen.</p></td>
<td><p>Konfigurieren Sie zum Verschlüsseln des Enterprise-VoIP-Datenverkehrs die Sicherheitseinstellungen für den Exchange UM-SIP-Wählplan mit der Option <strong>SIPSecured</strong> oder <strong>Secured</strong>. Dies ist ein besonders wichtiger Schritt, wenn Sie Lync Phone Edition-Geräte in Ihrer Umgebung bereitgestellt haben oder den Einsatz dieser Geräte planen. Damit Lync Phone Edition-Geräte in einer Umgebung mit Exchange UM-Integration funktionieren, müssen die Lync Server-Verschlüsselungseinstellungen mit den Sicherheitseinstellungen im Exchange UM-Wählplan übereinstimmen. Ausführliche Informationen zu diesem Thema finden Sie in der Bereitstellungsdokumentation.</p></td>
<td><p>Exchange-Organisationsadministrator</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging auf Microsoft Exchange</a></p>
<p>Weitere Informationen zu Exchange 2007 SP1 oder neuestes Service Pack finden Sie außerdem hier:</p>
<p>&quot;Konfigurieren der Sicherheitseinstellungen für einen Unified Messaging-Wählplan&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268696" class="uri">http://go.microsoft.com/fwlink/p/?linkid=268696</a>.</p>
<p></p>
<p>Informationen zu Exchange 2010 oder neuestes Service Pack finden Sie auch hier:</p>
<p>&quot;Konfigurieren von VoIP-Sicherheit in UM-Wähleinstellungen&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=1268697">http://go.microsoft.com/fwlink/p/?linkid=268697</a>.</p>
<p></p>
<p>Schauen Sie für Exchange 2013 unter „Unified Messaging“ nach (<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>).</p></td>
</tr>
<tr class="odd">
<td><p>Fügen Sie den Exchange UM-SIP-Wähleinstellungen Unified Messaging-Server hinzu.</p></td>
<td><p>Wenn Sie einen neu installierten Unified Messaging-Server zur Entgegennahme und Verarbeitung eingehender Anrufe aktivieren möchten, müssen Sie den Unified Messaging-Server einem Satz mit UM-Wähleinstellungen hinzufügen. Fügen Sie in diesem Fall den Server zu den Exchange UM-SIP-Wähleinstellungen hinzu.</p></td>
<td><p>Administratoren</p>
<p>Exchange-Serveradministratoren</p></td>
<td><p>Informationen zur Vorgehensweise für Exchange 2007 SP1 oder neuestes Service Pack finden Sie auf der Seite &quot;Hinzufügen eines Unified Messaging-Servers zu einem Wählplan&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268681" class="uri">http://go.microsoft.com/fwlink/p/?linkid=268681</a>.</p>
<p>Informationen zur Vorgehensweise für Exchange 2010 oder neuestes Service Pack finden Sie auf der Seite &quot;Anzeigen oder Konfigurieren der Eigenschaften eines UM-Servers&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268682" class="uri">http://go.microsoft.com/fwlink/p/?linkid=268682</a>.</p>
<p></p>
<p>Schauen Sie für Exchange 2013 unter „Unified Messaging“ nach (<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>).</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie Postfächer mit SIP-Adressen.</p></td>
<td><p>Weisen Sie den Postfächern aller Enterprise-VoIP-Benutzer, die Exchange UM-Funktionen nutzen, SIP-Adressen zu.</p></td>
<td><p>Lync Server 2013-Administrator</p>
<p>Exchange-Empfängeradministrator</p></td>
<td><p>Informationen zur Vorgehensweise für Exchange 2007 SP1 oder neuestes Service Pack finden Sie auf der Seite &quot;Hinzufügen, Entfernen oder Ändern einer SIP-Adresse für einen UM-aktivierten Benutzer&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</p>
<p>Informationen zur Vorgehensweise für Exchange 2010 oder neuestes Service Pack finden Sie auf der Seite &quot;Ändern einer SIP-Adresse für einen UM-aktivierten Benutzer&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</p>
<p></p>
<p>Schauen Sie für Exchange 2013 unter „Unified Messaging“ nach (<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>).</p></td>
</tr>
<tr class="odd">
<td><p>Führen Sie das Skript &quot;exchucutil.ps1&quot; aus.</p></td>
<td><p>Öffnen Sie auf dem Server, auf dem die Exchange UM-Dienste ausgeführt werden, die Exchange-Verwaltungsshell, und führen Sie das Skript <strong>exchucutil.ps1</strong> aus. Dieses Skript führt folgende Aktionen durch:</p>
<ul>
<li><p>Erteilen von Lync Server 2013-Berechtigungen für Exchange UM-Objekte in Active Directory-Domänendienste, insbesondere für die in der vorherigen Aufgabe erstellten SIP-Wählpläne.</p></li>
<li><p>Erstellen eines Unified Messaging-IP-Gatewayobjekts in Active Directory für jeden Lync Server 2013 Enterprise Edition-Pool oder Standard Edition-Server, der für Enterprise-VoIP aktivierte Benutzer hostet.</p></li>
<li><p>Erstellen eines Exchange UM-Sammelanschlusses für jedes Gateway. Die Pilot-ID des Sammelanschlusses ist der Name der Wähleinstellungen, die dem entsprechenden Gateway zugeordnet sind. Es muss sich um eine 1:1-Zuordnung handeln, wenn mehrere Sätze mit Wähleinstellungen verwendet werden.</p></li>
</ul></td>
<td><p>Exchange-Organisationsadministrator</p>
<p>Exchange-Empfängeradministrator</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging auf Microsoft Exchange</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie Lync Server 2013-Wählpläne.</p></td>
<td><p>Wenn Sie eine Integration in Exchange 2007 SP1 oder neuestes Service Pack oder Exchange 2010 planen, erstellen Sie einen neuen Enterprise-VoIP-Wählplan, dessen Name mit dem vollqualifizierten Domänennamen (FQDN) des Enterprise-VoIP-Wählplans übereinstimmt.</p>
<div>

> [!NOTE]
> Sie müssen dies für jeden UM-Wählplan durchführen.


</div>
<p>Wenn Sie eine Integration in Exchange 2010 SP1 beabsichtigen, stellen Sie sicher, dass geeignete auf globaler, Standort- oder Poolebene geltende Enterprise-VoIP-Wählpläne konfiguriert wurden.</p>
<div>

> [!NOTE]
> Wenn Sie eine Integration in Exchange 2010 SP1 planen, müssen die Namen des Lync Server-Wählplans und des Exchange UM-SIP-Wählplans nicht übereinstimmen.


</div></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Konfigurieren von Wählplänen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Führen Sie das Exchange UM-Integrationstool aus.</p></td>
<td><p>Führen Sie auf dem Lync Server 2013 die ausführbare Datei <strong>ocsumutil.exe</strong> aus. Dieses Tool führt folgende Aufgaben aus:</p>
<ul>
<li><p>Erstellen von Kontaktobjekten für Teilnehmerzugriff und automatische Telefonzentrale.</p></li>
<li><p>Überprüfen, ob ein Enterprise-VoIP-Wählplan vorhanden sind, dessen Name mit dem FQDN des Exchange UM-Wählplans übereinstimmt. Wenn Sie Exchange 2010 SP1 oder höher ausführen, müssen die Namen der Wählpläne nicht übereinstimmen, und Sie können entsprechende Warnungen des Tools ignorieren.</p></li>
</ul>
<p>Dieses Tool untersucht Active Directory auf Exchange UM-Einstellungen und ermöglicht es dem Lync Server 2013-Administrator, Kontaktobjekte anzuzeigen, zu erstellen und zu bearbeiten.</p></td>
<td><p>RTCUniversalServerAdmins <em>und</em> RTCUniversalUserAdmins</p>
<div>

> [!IMPORTANT]
> Zur erfolgreichen Ausführung von "ocsumutil.exe" muss der Benutzer beiden dieser Gruppe angehören.


</div>
<div>

> [!NOTE]
> Zum Erstellen von Kontaktobjekten muss der Benutzer, der <STRONG>ocsumutil.exe</STRONG> ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden. Diese Berechtigungen können mit dem Cmdlet <STRONG>Grant-CsOUPermission</STRONG> gewährt werden. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.


</div></td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Führen Sie bei Bedarf weitere Schritte zur Enterprise-VoIP-Konfiguration aus.</p></td>
<td><p>Wenn Sie nicht bereits Enterprise-VoIP-Einstellungen für Ihre Server oder Benutzer konfiguriert haben, führen Sie eine oder mehrere der folgenden Aufgaben aus:</p>
<ul>
<li><p>Bereitstellen und Konfigurieren</p>
<p>PSTN-Gateways und Vermittlungsservern</p></li>
<li><p>Definieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und ausgehenden Anrufrouten</p></li>
<li><p>Aktivieren von Benutzern für Enterprise-VoIP</p></li>
<li><p>(Optional) Konfigurieren von Wähleinstellungen für bestimmte Benutzer</p></li>
</ul>
<p>Je nach aktivierten Enterprise-VoIP-Funktionen ist möglicherweise die Ausführung weiterer Konfigurationsschritte erforderlich.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Siehe die Themen in den folgenden Abschnitten:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Aktivieren Sie Enterprise-VoIP-Benutzer für Exchange UM.</p></td>
<td><p>Überprüfen Sie auf dem Exchange UM-Server, ob eine Unified Messaging-Postfachrichtlinie erstellt und jedem Benutzer eine eindeutige Durchwahlnummer zugewiesen wurde. Aktivieren Sie den Benutzer anschließend für Unified Messaging.</p></td>
<td><p>Exchange-Empfängeradministrator</p></td>
<td><p>Informationen zur Vorgehensweise für Exchange 2007 SP1 oder neuestes Service Pack finden Sie auf der Seite &quot;Aktivieren eines Benutzers für Unified Messaging&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Informationen zur Vorgehensweise für Exchange 2010 oder neuestes Service Pack finden Sie auf der Seite &quot;Aktivieren eines Benutzers für Unified Messaging&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</p>
<p></p>
<p>Schauen Sie für Exchange 2013 unter „Unified Messaging“ nach (<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>).</p></td>
</tr>
</tbody>
</table>


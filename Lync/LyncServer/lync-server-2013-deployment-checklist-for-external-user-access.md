---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer'
TOCTitle: Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425910(v=OCS.15)
ms:contentKeyID: 49293786
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bevor Sie Ihr Umkreisnetzwerk bereitstellen und die Unterstützung für externe Benutzer implementieren, müssen Sie bereits Ihre internen Microsoft Lync Server 2013-Server bereitgestellt haben, einschließlich eines Front-End-Pools oder eines Standard Edition-Servers. Wenn Sie die Bereitstellung der optionalen Directors in Ihrem internen Netzwerk planen, sollten Sie diese ebenfalls vor den Edgeservern bereitstellen. Ausführliche Informationen zum Director-Bereitstellungsprozess finden Sie unter [Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

Microsoft Lync Server 2013 umfasst zwei Tools für eine vereinfachte Planung und Bereitstellung von internen Servern und Edgeservern. Veröffentlichen Sie nach dem Abschließen der Topologie die resultierende Topologiedefinition in Ihrer Produktionsumgebung. Um diese Aufgabe ausführen zu können, müssen Sie Mitglied der Gruppe **Domänen-Admins** und der Gruppe **RTCUniversalServerAdmins** sein.

  - Das **Planungstool**Office Communications Server 2007 R2 umfasste ein Planungstool und ein Edgeplanungstool, das Ihnen eine vereinfachte Erstellung des Topologieentwurfs ermöglichte. In Lync Server 2010 wurden diese zwei Tools zu einem einzigen Planungstool zusammengefasst, das zusätzliche Funktionen bietet, beispielsweise das Sammeln geplanter Benutzerzahlen, VoIP-Anforderungen, Zugriffstypen externer Benutzer und Partnerverbundoptionen. Außerdem können Sie die Netzwerkparameter Ihrer Infrastruktur planen, beispielsweise IP-Adressen, Lastenausgleichstypen und andere Überlegungen für das Umkreisnetzwerk.

  - Der Topologie-Generator Lync Server 2013  Topologie-Generator unterstützt Sie bei der Definition Ihrer Topologie und ihrer Komponenten. Das Topologie-Generator ist Voraussetzung für die Bereitstellung von Servern mit Lync Server 2013. Topologie-Generator veröffentlicht die Ergebnisse in einem zentralen Verwaltungsspeicher, der zur Konfiguration aller Server mit Lync Server 2013 in Ihrer Organisation verwendet wird. Sie können Lync Server 2013 nicht ohne Verwendung von Topologie-Generator auf Servern installieren.

Wenn Sie die Edgetopologie in der Planungsphase entworfen haben (einschließlich Ausführung des Topologie-Generators zum Definieren der Edgetopologie), können Sie die Ergebnisse verwenden, um mit der Edgeserverbereitstellung zu beginnen. Wenn Sie die Erstellung Ihrer Edgetopologie noch nicht abgeschlossen haben oder die zuvor angegebenen Informationen ändern möchten, müssen Sie die Schritte des Topologie-Generators zunächst abschließen, bevor Sie mit anderen Bereitstellungsschritten fortfahren können. Ausführliche Informationen zum Erstellen Ihrer Topologie finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Ausführliche Informationen zum Planungstool und zum Topologie-Generator finden Sie unter [Beginnen des Planungsprozesses für Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.

Die folgende Tabelle zeigt eine Übersicht über den Bereitstellungsprozess für Edgeserver. Unter [Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) finden Sie die Planungsentscheidungen, die vor der Bereitstellung des Zugriffs für externe Benutzer erforderlich sind.


> [!WARNING]
> Die Informationen in der folgenden Tabelle gelten für eine neue Bereitstellung. Wenn Sie Edgeserver in einer Lync Server 2010-, Office Communications Server 2007 R2- oder Office Communications Server 2007-Umgebung bereitgestellt haben, finden Sie unter <A href="migration.md">Migration</A> ausführliche Informationen über die Migration zu Lync Server 2013. Für Versionen vor Office Communications Server 2007 R2, Office Communications Server 2007, Live Communications Server 2005 und Live Communications Server 2003 eingeschlossen, wird eine Migration nicht unterstützt.



Halten Sie sich bei der Bereitstellung des Umkreisnetzwerks und der Edgeserver an folgende Richtlinien, um sowohl die Leistung und Sicherheit der Edgeserver zu erhöhen als auch die Bereitstellung zu erleichtern:

  - Stellen Sie Edgeserver erst bereit, nachdem Sie Lync Server 2013 innerhalb Ihrer Organisation getestet und deren ordnungsgemäßen Betrieb sichergestellt haben.

  - Es wird empfohlen, die Edgeserver nicht in einer Domäne, sondern in einer Arbeitsgruppe bereitzustellen. Dies vereinfacht die Installation und vermeidet eine Verbindung zwischen Active Directory-Domänendiensten (AD DS) und dem Umkreisnetzwerk. Eine Verbindung zwischen AD DS und dem Umkreisnetzwerk kann ein erhebliches Sicherheitsproblem darstellen.

  - Ein Edgeserver kann einer Domäne hinzugefügt werden, die sich ganz im Umkreisnetzwerk befindet. Dies wird jedoch nicht empfohlen. Ein Edgeserver, der Teil der internen Domäne ist, verletzt die Grenzen des vertrauenswürdigen Netzwerks, wobei das Internet die am wenigsten vertrauenswürdige Zone, das Umkreisnetzwerk vertrauenswürdiger als das Internet und das interne Netzwerk am vertrauenswürdigsten ist. Ein Edgeserver, der Mitglied der Domäne ist, ist automatisch ein Teil des vertrauenswürdigsten Netzwerks, befindet sich jedoch in einem weniger vertrauenswürdigen Netzwerk (dem Umkreisnetzwerk).

## Bereitstellungsprozess für Edgeserver


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
<td><p>Erstellen Sie die geeignete Edgetopologie, und ermitteln Sie die geeigneten Komponenten.</p></td>
<td><ul>
<li><p>Führen Sie den Topologie-Generator aus, um Einstellungen für Edgeserver zu konfigurieren und die Topologie zu erstellen und zu veröffentlichen. Verwenden Sie dann die Lync Server-Verwaltungsshell zum Exportieren der Topologiekonfigurationsdatei.</p></li>
</ul>
<p></p></td>
<td><p>Gruppe <strong>Domänen-Admins</strong> und Gruppe <strong>RTCUniversalServerAdmins</strong> oder <strong>CsAdmins</strong></p>
<div>

> [!NOTE]
> Sie können eine Topologie unter Verwendung eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, für die Veröffentlichung einer Topologie ist jedoch ein Konto erforderlich, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> und der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge- und Director-Topologie in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Bereiten Sie das Setup vor.</p></td>
<td><ol>
<li><p>Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</p></li>
<li><p>Konfigurieren Sie IP-Adressen (IPv4 und IPv6, falls verwendet) für die internen und die öffentlichen Netzwerkschnittstellen auf jedem Edgeserver.</p></li>
<li><p>Konfigurieren Sie interne und externe DNS-Einträge (Host A und AAAA für IPv4 und IPv6), einschließlich Konfiguration des DNS-Suffixes auf dem Computer, der als Edgeserver bereitgestellt werden soll.</p></li>
<li><p>(Optional) Erstellen und installieren Sie öffentliche Zertifikate. Die zum Anfordern von Zertifikaten erforderliche Zeit richtet sich nach der Zertifizierungsstelle, die das Zertifikat ausgibt. Wenn Sie diesen Schritt jetzt überspringen, müssen Sie ihn während der Installation der Edgeserver ausführen. Die Edgeserverdienste können erst gestartet werden, wenn Zertifikate angefordert und installiert wurden.</p></li>
<li><p>Konfigurieren Sie die Unterstützung zur Verbindung mit öffentlichen Instant Messaging-Diensten, wenn Ihre Bereitstellung eine Kommunikation mit Benutzern von Windows Live, AOL oder Yahoo! unterstützen soll.</p>
<div>

> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>


</div></li>
<li><p>Konfigurieren Sie die Unterstützung von XMPP und die Unterstützung des Partnerverbunds für Office Communications Server 2007-, Office Communications Server 2007 R2- und Lync Server 2010-Partner, falls Ihre Bereitstellung diese verwendet.</p></li>
<li><p>Konfigurieren Sie die Firewalls.</p></li>
</ol></td>
<td><p>Je nach Organisationsanforderungen</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Richten Sie den Reverseproxy ein.</p></td>
<td><ul>
<li><p>Richten Sie den Reverseproxy (beispielsweise für Microsoft Forefront Threat Management Gateway 2010 oder Microsoft Internet Security and Acceleration Server (ISA) mit Service Pack 1) im Umkreisnetzwerk ein, fordern Sie die benötigten öffentlichen Zertifikate an, und konfigurieren Sie die Webveröffentlichungsregeln auf dem Reverseproxyserver.</p>
<p>Bereiten Sie den Reverseproxy für Mobilitätsdienste vor, falls Sie Mobilität eingeplant haben und die Mobilitätsdienste im Front-End-Pool oder auf dem Standard Edition-Server bereitstellen.</p></li>
</ul></td>
<td><p>Gruppe <strong>Administratoren</strong> oder Reverseproxy-Administrator</p></td>
<td><p></p>
<p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverseproxyservern für Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Richten Sie einen Director ein (optional).</p></td>
<td><ul>
<li><p>(Optional) Installieren und konfigurieren Sie einen oder mehrere Director-Server im internen Netzwerk.</p></li>
</ul></td>
<td><p>Gruppe <strong>Administratoren</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Einrichten des Directors in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Richten Sie die Edgeserver ein.</p></td>
<td><ol>
<li><p>Installieren Sie die erforderliche Software.</p></li>
<li><p>Übertragen Sie die exportierte Topologiekonfigurationsdatei auf jeden Edgeserver.</p></li>
<li><p>Installieren Sie die Lync Server 2013-Software auf jedem Edgeserver.</p></li>
<li><p>Konfigurieren Sie die Edgeserver.</p></li>
<li><p>Fordern Sie Zertifikate für alle Edgeserver an, und installieren Sie sie.</p></li>
<li><p>Starten Sie die Edgeserverdienste.</p></li>
</ol></td>
<td><p>Gruppe <strong>Administratoren</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Einrichten von Edgeservern in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Bereitstellung für den Zugriff durch externe Benutzer</p></td>
<td><ol>
<li><p>Verwenden Sie die Lync Server-Systemsteuerung, um die Unterstützung folgender Funktionen zu konfigurieren (sofern gewünscht):</p>
<ul>
<li><p>Mediarelay</p></li>
<li><p>Partnerverbundroute</p></li>
<li><p>Remotebenutzerzugriff</p></li>
<li><p>Partnerverbund mit Lync Server, Office Communications Server und Live Communications Server</p></li>
<li><p>Verbindung mit öffentlichen Instant Messaging-Diensten</p></li>
<li><p>XMPP-Verbund</p></li>
<li><p>Anonyme Benutzer</p></li>
</ul></li>
<li><p>Konfigurieren Sie Benutzerkonten für Remotebenutzerzugriff, Partnerverbund, die Verbindung mit öffentlichen Instant Messaging-Diensten, XMPP und die Unterstützung anonymer Benutzer (sofern gewünscht)</p></li>
</ol></td>
<td><p>Gruppe <strong>RTCUniversalServerAdmins</strong> oder Benutzerkonto mit zugewiesener Rolle <strong>CSAdministrator</strong></p>
<p></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen Sie Ihre Edgeserverkonfiguration.</p></td>
<td><ol>
<li><p>Überprüfen Sie die Serverkonnektivität, und stellen Sie sicher, dass die Replikation der Konfigurationsdaten interner Server ordnungsgemäß funktioniert.</p></li>
<li><p>Stellen Sie sicher, dass externe Benutzer eine Verbindung herstellen können - Remotebenutzer, Benutzer in Partnerdomänen, Benutzer öffentlicher Instant Messaging-Dienste und anonyme Benutzer eingeschlossen (je nach Anforderungen für Ihre Bereitstellung).</p></li>
<li><p>Überprüfen Sie Konfiguration und Kommunikation mithilfe der Lync Server-Remoteverbindungsanalyse <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Konfiguration der Fehlersuche und Hilfe bei Kommunikationsproblemen</p></li>
</ol></td>
<td><p>Zum Überprüfen der Replikation: Gruppe <strong>RTCUniversalServerAdmins</strong> oder Benutzerkonto mit zugewiesener Rolle <strong>CSAdministrator</strong></p>
<p>Zum Überprüfen der Benutzerkonnektivität: Ein Benutzer für jede Art von externem Zugriff, der unterstützt wird</p>
<p>Remotebenutzer</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edgebereitstellung in Lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
</tbody>
</table>


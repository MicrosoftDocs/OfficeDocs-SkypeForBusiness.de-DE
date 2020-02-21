---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f2897434eb275b82ef9ab4ef78e32e99e8d0a5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-04_

Bevor Sie Ihr Umkreisnetzwerk bereitstellen und die Unterstützung für externe Benutzer implementieren, müssen Sie Ihre Microsoft lync Server 2013 internen Server bereits bereitgestellt haben, einschließlich einer Front-End-Pool oder einer Standard Edition-Server. Wenn Sie die optionalen Directors in Ihrem internen Netzwerk bereitstellen möchten, sollten Sie Sie auch vor dem Bereitstellen von Edgeserver bereitstellen. Ausführliche Informationen zum Bereitstellungsprozess für Director finden Sie unter [Scenarios for the Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

Microsoft lync Server 2013 enthält Tools zur Erleichterung der Planung und Bereitstellung von internen Servern und Edgeserver. Veröffentlichen Sie nach dem Abschließen der Topologie die resultierende Topologiedefinition in Ihrer Produktionsumgebung. Um diese Aufgabe ausführen zu können, müssen Sie Mitglied der Gruppe **Domänen-Admins** und der Gruppe **RTCUniversalServerAdmins** sein.

  - **Planungs**   Tool Office Communications Server 2007 R2 ein Planungstool und ein Edge-Planungstool enthalten, mit deren Hilfe Sie das Topologie-Design vereinfachen können. In lync Server 2010 wurden diese beiden Tools zu einem einzigen Planungs Tool zusammengefasst, das zusätzliche Features und Funktionen wie das Sammeln geplanter Benutzeranzahl, Sprachanforderungen, Zugriffstypen für externe Benutzer und Verbund Optionen aufweist. Darüber hinaus können Sie die Netzwerkparameter Ihrer Infrastruktur wie IP-Adressen, Lastenausgleichs Typen und andere Aspekte des Umkreisnetzwerks planen.

  - **Topologie-Generator**   lync Server 2013 Topologie-Generator unterstützt Sie bei der Definition Ihrer Topologie und Komponenten. Der Topologie-Generator ist für die Bereitstellung von Servern erforderlich, auf denen lync Server 2013 ausführt. Der Topologie-Generator veröffentlicht die Ergebnisse in einem zentralen Verwaltungsspeicher, der verwendet wird, um alle Server zu konfigurieren, auf denen lync Server 2013 in Ihrer Organisation läuft. Sie können lync Server 2013 nicht auf Servern ohne Verwendung des Topologie-Generators installieren.

Wenn Sie Ihre Edge-Topologie während des Planungsprozesses entworfen haben, einschließlich der Ausführung des Topologie-Generators zur Definition ihrer Edge-Topologie, können Sie diese Ergebnisse verwenden, um die Edgeserver-Bereitstellung zu starten. Wenn Sie die Edge-Topologie zuvor nicht fertig erstellt haben oder die zuvor angegebenen Informationen ändern möchten, müssen Sie den Topologie-Generator ausführen, bevor Sie mit anderen Bereitstellungsschritten fortfahren. Ausführliche Informationen zum Erstellen Ihrer Topologie finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Ausführliche Informationen zum Planungs Tool und zum Topologie-Generator finden Sie unter [Beginn des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.

Die folgende Tabelle zeigt eine Übersicht über den Bereitstellungsprozess für Edgeserver. Informationen zum Überprüfen der Planungsentscheidungen, die vor der Bereitstellung des Zugriffs durch externe Benutzer getroffen werden müssen, finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> Die Informationen in der folgenden Tabelle gelten für eine neue Bereitstellung. Wenn Sie Edgeserver in einer lync Server 2010-, Office Communications Server 2007 R2-oder Office Communications Server 2007-Umgebung bereitgestellt haben, finden Sie weitere Informationen zum Migrieren zu lync Server 2013 in der <A href="migration.md">Migration</A> . Die Migration wird von keiner Version vor Office Communications Server 2007 R2 unterstützt, einschließlich Office Communications Server 2007, Live Communications Server 2005 und Live Communications Server 2003.



</div>

Halten Sie sich bei der Bereitstellung des Umkreisnetzwerks und der Edgeserver an folgende Richtlinien, um sowohl die Leistung und Sicherheit der Edgeserver zu erhöhen als auch die Bereitstellung zu erleichtern:

  - Stellen Sie Edgeserver erst bereit, nachdem Sie den Betrieb von lync Server 2013 in Ihrer Organisation getestet und überprüft haben.

  - Es wird empfohlen, die Edgeserver nicht in einer Domäne, sondern in einer Arbeitsgruppe bereitzustellen. Dies vereinfacht die Installation und vermeidet eine Verbindung zwischen Active Directory-Domänendiensten (AD DS) und dem Umkreisnetzwerk. Eine Verbindung zwischen AD DS und dem Umkreisnetzwerk kann ein erhebliches Sicherheitsproblem darstellen.

  - Ein Edgeserver kann einer Domäne hinzugefügt werden, die sich ganz im Umkreisnetzwerk befindet. Dies wird jedoch nicht empfohlen. Ein Edgeserver, der Teil der internen Domäne ist, verletzt die Grenzen des vertrauenswürdigen Netzwerks, wobei das Internet die am wenigsten vertrauenswürdige Zone, das Umkreisnetzwerk vertrauenswürdiger als das Internet und das interne Netzwerk am vertrauenswürdigsten ist. Ein Edgeserver, der Mitglied der Domäne ist, ist automatisch ein Teil des vertrauenswürdigsten Netzwerks, befindet sich jedoch in einem weniger vertrauenswürdigen Netzwerk (dem Umkreisnetzwerk).

<div>

## <a name="deployment-process-for-edge-servers"></a>Bereitstellungsprozess für Edgeserver


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
<li><p>Führen Sie den Topologie-Generator aus, um Edgeserver Einstellungen zu konfigurieren und die Topologie zu erstellen und zu veröffentlichen, und verwenden Sie dann lync Server-Verwaltungsshell, um die Topologie-Konfigurationsdatei zu exportieren.</p></li>
</ul></td>
<td><p>Gruppe " <strong>Domänen-Admins</strong> " und <strong>RTCUniversalServerAdmins</strong> oder <strong>CsAdmins</strong> -Gruppe</p>
<div>

> [!NOTE]  
> Sie können eine Topologie unter Verwendung eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, für die Veröffentlichung einer Topologie ist jedoch ein Konto erforderlich, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> und der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge-und Director-Topologie in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
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
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>


</div></li>
<li><p>Bereitstellen von Unterstützung für die XMPP-und Verbundunterstützung für Office Communications Server 2007, Office Communications Server 2007 R2 lync Server 2010 Partner, wenn Ihre Bereitstellung diese verwendet</p></li>
<li><p>Konfigurieren Sie die Firewalls.</p></li>
</ol></td>
<td><p>Je nach Organisationsanforderungen</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Richten Sie den Reverseproxy ein.</p></td>
<td><ul>
<li><p>Richten Sie den Reverseproxy ein (beispielsweise für Microsoft Forefront Threat Management Gateway 2010 oder ISA (Microsoft Internet Security and Acceleration Server) mit Service Pack 1) im Umkreisnetzwerk, beziehen Sie die erforderlichen öffentlichen Zertifikate, und konfigurieren Sie die Webveröffentlichungsregeln auf dem Reverse-Proxy Server.</p>
<p>Bereiten Sie den Reverseproxy für Mobilitätsdienste vor, falls Sie Mobilität eingeplant haben und die Mobilitätsdienste im Front-End-Pool oder auf dem Standard Edition-Server bereitstellen.</p></li>
</ul></td>
<td><p>Gruppe <strong>Administratoren</strong> oder Reverseproxy-Administrator</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Richten Sie einen Director ein (optional).</p></td>
<td><ul>
<li><p>(Optional) Installieren und konfigurieren Sie einen oder mehrere Director-Server im internen Netzwerk.</p></li>
</ul></td>
<td><p>Gruppe <strong>Administratoren</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Einrichten des Directors in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Richten Sie die Edgeserver ein.</p></td>
<td><ol>
<li><p>Installieren Sie die erforderliche Software.</p></li>
<li><p>Übertragen Sie die exportierte Topologiekonfigurationsdatei auf jeden Edgeserver.</p></li>
<li><p>Installieren Sie die lync Server 2013 Software auf jeder Edgeserver.</p></li>
<li><p>Konfigurieren Sie die Edgeserver.</p></li>
<li><p>Fordern Sie Zertifikate für alle Edgeserver an, und installieren Sie sie.</p></li>
<li><p>Starten Sie die Edgeserverdienste.</p></li>
</ol></td>
<td><p>Gruppe <strong>Administratoren</strong></p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Einrichten von Edge-Servern in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Bereitstellung für den Zugriff durch externe Benutzer</p></td>
<td><ol>
<li><p>Verwenden Sie die lync Server-Systemsteuerung, um die Unterstützung für jede der folgenden Einstellungen zu konfigurieren (sofern zutreffend):</p>
<ul>
<li><p>Mediarelay</p></li>
<li><p>Partnerverbundroute</p></li>
<li><p>Remotebenutzerzugriff</p></li>
<li><p>Partnerverbund mit lync Server, Office Communications Server und Live Communications Server</p></li>
<li><p>Verbindung mit öffentlichen Instant Messaging-Diensten</p></li>
<li><p>XMPP-Verbund</p></li>
<li><p>Anonyme Benutzer</p></li>
</ul></li>
<li><p>Konfigurieren Sie Benutzerkonten für Remotebenutzerzugriff, Partnerverbund, die Verbindung mit öffentlichen Instant Messaging-Diensten, XMPP und die Unterstützung anonymer Benutzer (sofern gewünscht)</p></li>
</ol></td>
<td><p>Gruppe <strong>RTCUniversalServerAdmins</strong> oder Benutzerkonto mit zugewiesener Rolle <strong>CSAdministrator</strong></p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen Sie Ihre Edgeserverkonfiguration.</p></td>
<td><ol>
<li><p>Überprüfen Sie die Serverkonnektivität, und stellen Sie sicher, dass die Replikation der Konfigurationsdaten interner Server ordnungsgemäß funktioniert.</p></li>
<li><p>Stellen Sie sicher, dass externe Benutzer eine Verbindung herstellen können – Remotebenutzer, Benutzer in Partnerdomänen, Benutzer öffentlicher Instant Messaging-Dienste und anonyme Benutzer eingeschlossen (je nach Anforderungen für Ihre Bereitstellung).</p></li>
<li><p>Überprüfen der Konfiguration und der Kommunikation mit dem lync Server Remote Connectivity Analyzer<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Konfiguration der Fehlersuche und Hilfe bei Kommunikationsproblemen</p></li>
</ol></td>
<td><p>Zum Überprüfen der Replikation: Gruppe <strong>RTCUniversalServerAdmins</strong> oder Benutzerkonto mit zugewiesener Rolle <strong>CSAdministrator</strong></p>
<p>Zum Überprüfen der Benutzerkonnektivität: Ein Benutzer für jede Art von externem Zugriff, der unterstützt wird</p>
<p>Remotebenutzer</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edge-Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


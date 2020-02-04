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
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-04_

Bevor Sie Ihr Umkreisnetzwerk bereitstellen und die Unterstützung für externe Benutzer implementieren, müssen Sie Ihre Microsoft lync Server 2013-internen Server bereits bereitgestellt haben, einschließlich eines Front-End-Pools oder eines Standard Edition-Servers. Wenn Sie beabsichtigen, die optionalen Directors in Ihrem internen Netzwerk bereitzustellen, sollten Sie diese vor der Bereitstellung von Edgeserver auch bereitstellen. Details zum Director-Bereitstellungsprozess finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

Microsoft lync Server 2013 umfasst Tools zur Vereinfachung der Planung und Bereitstellung von internen Servern und Edgeserver. Veröffentlichen Sie nach Abschluss der Topologie die resultierende Topologie-Definition in Ihrer Produktionsumgebung. Zu diesem Zweck müssen Sie Mitglied der Gruppe "Domänen- **Admins** " und der Gruppe " **RTCUniversalServerAdmins** " sein.

  - **Planungs**   Tool Office Communications Server 2007 R2 enthielt ein Planungstool und ein Edge-Planning-Tool, mit dem Sie den Topologie-Entwurf vereinfachen können. In lync Server 2010 wurden diese beiden Tools zu einem einzigen Planungs Tool kombiniert, das zusätzliche Features und Funktionen aufweist, wie etwa das Sammeln geplanter Benutzeranzahl, Sprachanforderungen, Zugriffstypen für externe Benutzer und Verbund Optionen. Darüber hinaus können Sie die Netzwerkparameter Ihrer Infrastruktur wie IP-Adressen, Lastenausgleichsmodul Typen und andere Aspekte des Umkreisnetzwerks planen.

  - **Topology Builder**   lync Server 2013 Topology Builder unterstützt Sie beim Definieren Ihrer Topologie und Komponenten. Der Topologie-Generator ist für die Bereitstellung von Servern mit lync Server 2013 unerlässlich. Der Topologie-Generator veröffentlicht die Ergebnisse in einem zentralen Verwaltungsspeicher, der zum Konfigurieren aller Server mit lync Server 2013 in Ihrer Organisation verwendet wird. Sie können lync Server 2013 nicht auf Servern installieren, ohne den Topology Builder verwenden zu müssen.

Wenn Sie Ihre Edge-Topologie während des Planungsprozesses entworfen haben, einschließlich der Ausführung des Topologie-Generators zum Definieren Ihrer Edge-Topologie, können Sie diese Ergebnisse verwenden, um die Edge-Server-Bereitstellung zu starten. Wenn Sie die Erstellung Ihrer Edge-Topologie zuvor nicht abgeschlossen haben oder die zuvor angegebenen Informationen ändern möchten, müssen Sie die Ausführung des Topologie-Generators beenden, bevor Sie mit anderen Bereitstellungsschritten fortfahren. Ausführliche Informationen zum Erstellen Ihrer Topologie finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

Details zum Planungs Tool und zum Topologie-Generator finden Sie unter [Starten des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.

Die folgende Tabelle enthält eine Übersicht über den Edge Server-Bereitstellungsprozess. Informationen zu den Planungsentscheidungen, die vor der Bereitstellung des Zugriffs auf externe Benutzer getroffen werden müssen, finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

<div>


> [!WARNING]  
> Die Informationen in der folgenden Tabelle konzentrieren sich auf eine neue Bereitstellung. Wenn Sie Edgeserver in einer lync Server 2010, Office Communications Server 2007 R2 oder Office Communications Server 2007-Umgebung bereitgestellt haben, finden Sie Informationen zum Migrieren zu lync Server 2013 in der <A href="migration.md">Migration</A> . Die Migration wird von keiner Version vor Office Communications Server 2007 R2 unterstützt, einschließlich Office Communications Server 2007, Live Communications Server 2005 und Live Communications Server 2003.



</div>

Zum Verbessern der Leistung und Sicherheit von Edge-Servern und zur Vereinfachung der Bereitstellung wenden Sie die folgenden bewährten Methoden an, wenn Sie das Umkreisnetzwerk und die Edgeserver bereitstellen:

  - Stellen Sie Edgeserver erst bereit, nachdem Sie den Betrieb von lync Server 2013 in Ihrer Organisation getestet und überprüft haben.

  - Es wird empfohlen, Edgeserver in einer Arbeitsgruppe statt in einer Domäne bereitzustellen. Dadurch wird die Installation vereinfacht, und Active Directory-Domänendienste (AD DS) sind außerhalb des Umkreisnetzwerks. Das Auffinden von AD DS im Umkreisnetzwerk kann ein erhebliches Sicherheitsrisiko darstellen.

  - Das beitreten zu einem Edgeserver zu einer Domäne, die sich vollständig im Umkreisnetzwerk befindet, wird unterstützt, aber nicht empfohlen. Ein Edgeserver als Teil der internen Domäne verletzt vertrauenswürdige Netzwerkgrenzen, bei denen das Internet am wenigsten vertraut ist, Umkreisnetzwerk ist vertrauenswürdiger als das Internet, und das interne Netzwerk ist am vertrauenswürdigsten. Ein Edgeserver als Mitglied der Domäne ist automatisch Teil des vertrauenswürdigsten Netzwerks, befindet sich aber in einem vertrauenswürdigen Netzwerk (dem Umkreis).

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
<td><p>Erstellen Sie die geeignete Edge-Topologie, und ermitteln Sie die geeigneten Komponenten.</p></td>
<td><ul>
<li><p>Führen Sie den Topologie-Generator aus, um Edge-Servereinstellungen zu konfigurieren und die Topologie zu erstellen und zu veröffentlichen, und verwenden Sie dann die lync Server-Verwaltungsshell zum Exportieren der Topologie-Konfigurationsdatei.</p></li>
</ul></td>
<td><p>Gruppe " <strong>Domänen-Admins</strong> " und " <strong>RTCUniversalServerAdmins</strong> " oder " <strong>CsAdmins</strong> "</p>
<div>

> [!NOTE]  
> Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber das Veröffentlichen einer Topologie erfordert ein Konto, das ein Mitglied der Gruppe der <STRONG>Domänenadministratoren</STRONG> und der <STRONG>RTCUniversalServerAdmins</STRONG> -Gruppe ist.


</div></td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge-und Director-Topologie in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Vorbereiten des Setups</p></td>
<td><ol>
<li><p>Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</p></li>
<li><p>Konfigurieren Sie IP-Adressen (bei Verwendung von IPv4 und IPv6) sowohl für interne als auch für öffentlich zugängliche Netzwerkschnittstellen auf jedem Edgeserver.</p></li>
<li><p>Konfigurieren Sie interne und externe DNS-Einträge (Host A und AAAA für IPv4 und IPv6), einschließlich der Konfiguration des DNS-Suffixes auf dem Computer, der als Edgeserver bereitgestellt werden soll.</p></li>
<li><p>Optional Erstellen und installieren Sie öffentliche Zertifikate. Die zum Abrufen von Zertifikaten erforderliche Zeit hängt davon ab, welche Zertifizierungsstelle das Zertifikat ausgibt. Wenn Sie diesen Schritt an diesem Punkt nicht ausführen, müssen Sie dies während der Installation des Edge-Servers tun. Die Edge-Server Dienste können erst gestartet werden, nachdem Zertifikate abgerufen und installiert wurden.</p></li>
<li><p>Bereitstellen von Unterstützung für öffentliche Chat Verbindungen, wenn Ihre Bereitstellung die Kommunikation mit Windows Live, AOL oder Yahoo! unterstützt Benutzer.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>


</div></li>
<li><p>Bereitstellen von Unterstützung für die Unterstützung von XMPP und Verbund für Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010-Partner, wenn diese von der Bereitstellung verwendet werden</p></li>
<li><p>Konfigurieren Sie Firewalls.</p></li>
</ol></td>
<td><p>Entsprechend Ihrer Organisation</p></td>
<td><p><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Einrichten eines Reverse-Proxys</p></td>
<td><ul>
<li><p>Einrichten des Reverse Proxys (beispielsweise für Microsoft Forefront Threat Management Gateway 2010 oder Microsoft Internet Security and Acceleration (ISA) Server mit Service Pack 1) im Umkreisnetzwerk, besorgen Sie sich die erforderlichen öffentlichen Zertifikate, und konfigurieren Sie die Webveröffentlichungsregeln auf dem Reverse-Proxy Server.</p>
<p>Bereiten Sie den Reverseproxy für Mobilitätsdienste vor, wenn Sie für Mobilität geplant haben und die Mobilitätsdienste im Front-End-Pool oder Standard Edition-Server bereitstellen.</p></li>
</ul></td>
<td><p>Gruppe " <strong>Administratoren</strong> " oder Reverse-Proxy-Administrator</p></td>
<td><p><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Einrichten eines Directors (optional)</p></td>
<td><ul>
<li><p>Optional Installieren und konfigurieren Sie einen oder mehrere Directors im internen Netzwerk.</p></li>
</ul></td>
<td><p>Gruppe " <strong>Administratoren</strong> "</p></td>
<td><p><a href="lync-server-2013-setting-up-the-director.md">Einrichten des Directors in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Einrichten von Edgeserver</p></td>
<td><ol>
<li><p>Installieren Sie die erforderliche Software.</p></li>
<li><p>Transportieren Sie die exportierte Topologie-Konfigurationsdatei auf jeden Edgeserver.</p></li>
<li><p>Installieren Sie die lync Server 2013-Software auf jedem Edgeserver.</p></li>
<li><p>Konfigurieren Sie die Edgeserver.</p></li>
<li><p>Fordern Sie Zertifikate für jeden Edgeserver an, und installieren Sie Sie.</p></li>
<li><p>Starten Sie die Edgeserver-Dienste.</p></li>
</ol></td>
<td><p>Gruppe " <strong>Administratoren</strong> "</p></td>
<td><p><a href="lync-server-2013-setting-up-edge-servers.md">Einrichten von Edgeserver in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Bereitstellung für den Zugriff durch externe Benutzer.</p></td>
<td><ol>
<li><p>Verwenden Sie die lync Server-Systemsteuerung, um die Unterstützung für jede der folgenden Optionen zu konfigurieren:</p>
<ul>
<li><p>Medien Relay</p></li>
<li><p>Föderations Route</p></li>
<li><p>Zugriff durch Remote Benutzer</p></li>
<li><p>Föderation mit lync Server, Office Communications Server und Live Communications Server</p></li>
<li><p>Verbindung mit öffentlichen Chatdiensten</p></li>
<li><p>XMPP-Föderation</p></li>
<li><p>Anonyme Benutzer</p></li>
</ul></li>
<li><p>Konfigurieren von Benutzerkonten für Remotebenutzerzugriff, Föderation, öffentliche Chat Verbindungen, XMPP und anonyme Benutzerunterstützung (sofern zutreffend)</p></li>
</ol></td>
<td><p><strong>RTCUniversalServerAdmins</strong> -Gruppe oder ein Benutzerkonto, das der <strong>CSAdministrator</strong> -Rolle zugewiesen ist</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen Sie Ihre Edge-Server-Konfiguration.</p></td>
<td><ol>
<li><p>Überprüfen Sie die Serverkonnektivität und die Replikation von Konfigurationsdaten von internen Servern.</p></li>
<li><p>Stellen Sie sicher, dass externe Benutzer eine Verbindung herstellen können, einschließlich Remotebenutzern, Benutzern in Verbunddomänen, öffentlichen Chat Benutzern und anonymen Benutzern entsprechend Ihrer Bereitstellung.</p></li>
<li><p>Überprüfen der Konfiguration und Kommunikation mithilfe der lync Server-Remote Verbindungsanalyse<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>Problembehandlung bei Konfigurations-und Kommunikationsproblemen</p></li>
</ol></td>
<td><p>Zur Überprüfung der Replikation, der <strong>RTCUniversalServerAdmins</strong> -Gruppe oder des Benutzerkontos, das der <strong>CSAdministrator</strong> -Rolle zugewiesen ist</p>
<p>Zur Überprüfung der Benutzerkonnektivität wird ein Benutzer für jeden von Ihnen unterstützten Typ von Zugriff auf externe Benutzer</p>
<p>Remote Benutzer</p></td>
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


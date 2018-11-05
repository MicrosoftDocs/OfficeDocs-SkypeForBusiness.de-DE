---
title: 'Lync Server 2013: Ausfallsicherheitslösungen für Zweigstellenstandorte'
TOCTitle: Ausfallsicherheitslösungen für Zweigstellenstandorte
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398234(v=OCS.15)
ms:contentKeyID: 49293299
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausfallsicherheitslösungen für Zweigstellenstandorte in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Bereitstellen von Ausfallsicherheit für Zweigstellenstandorte bietet offensichtliche Vorteile. Der wichtigste besteht darin, dass den Benutzern am Zweigstellenstandort bei einem Ausfall der Verbindung mit dem zentralen Standort weiterhin Enterprise-VoIP-Dienste und Voicemail zur Verfügung stehen (sofern Sie Einstellungen für die Voicemailumleitung konfigurieren; ausführliche Informationen hierzu finden Sie unter [Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Für Standorte mit weniger als 25 Benutzern ist die Implementierung einer Ausfallsicherheitslösung jedoch möglicherweise nicht ausreichend rentabel.

Wenn Sie sich zur Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte entschließen, haben Sie drei Möglichkeiten. Entscheiden Sie mithilfe der folgenden Tabelle, welche Option für Sie geeignet ist.



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Situation</th>
<th>Empfehlung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Host mit 25 bis 1.000 Benutzern am Zweigstellenstandort, wobei eine vollständige Bereitstellung nicht rentabel ist oder kein administrativer Support zur Verfügung steht</p></td>
<td><p>Survivable Branch-Anwendung</p>
<p>Survivable Branch-Anwendung ist ein Bladeserver nach Industriestandard, bei der ein Lync Server-Registrierungsserver und -Vermittlungsserver auf Windows Server 2008 R2 ausgeführt werden. Survivable Branch-Anwendung umfasst außerdem ein PSTN-Gateway. Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im Programm zur SBA-Qualifizierung/-Zertifizierung) bieten bei einem WAN-Ausfall eine dauerhafte PSTN-Verbindung (Public Switched Telephone Network, Telefonfestnetz), es werden jedoch keine ausfallsicheren Anwesenheits- und Konferenzfeatures bereitgestellt, da diese Features von den Front-End-Servern am zentralen Standort abhängen.</p>
<p>Ausführliche Informationen zu Survivable Branch-Anwendungenen finden Sie unter &quot;Details zur Survivable Branch-Anwendung&quot; weiter unten in diesem Thema.</p>
<p><strong>Hinweis:</strong> Wenn Sie beschließen, auch einen SIP-Trunk mit Ihrer Survivable Branch-Anwendung einzusetzen, erkundigen Sie sich beim Hersteller der Survivable Branch-Anwendung nach dem geeigneten Dienstanbieter für Ihre Organisation.</p></td>
</tr>
<tr class="even">
<td><p>Host mit 1.000 bis 2.000 Benutzern am Zweigstellenstandort, keine ausfallsichere WAN-Verbindung, geschulte Lync Server-Administratoren verfügbar</p></td>
<td><p>Survivable Branch-Server oder zwei Survivable Branch-Anwendungenen.</p>
<p>Der Survivable Branch-Server ist ein Windows-Server, der spezifische Hardwareanforderungen erfüllt und auf dem die Software für Lync Server-Registrierung und Vermittlungsserver installiert ist. Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein.</p>
<p>Ausführliche Informationen zu Survivable Branch-Serveren finden Sie unter &quot;Details zum Survivable Branch-Server&quot; weiter unten in diesem Thema.</p></td>
</tr>
<tr class="odd">
<td><p>Sie müssen neben VoIP-Funktionen für bis zu 5.000 Benutzer auch Anwesenheits- und Konferenzfunktionen bereitstellen, geschulte Lync Server-Administratoren sind verfügbar</p></td>
<td><p>Führen Sie statt einer Zweigstellenbereitstellung eine Bereitstellung als zentraler Standort mit einem Standard Edition-Server durch.</p>
<p>Eine vollständige Lync Server-Bereitstellung bietet eine dauerhafte PSTN-Verbindung und ausfallsichere Anwesenheits- und Konferenzfunktionen bei einem WAN-Ausfall.</p>
<p>Ausführliche Informationen zum Vorbereiten einer solchen Lösung finden Sie unter <a href="lync-server-2013-planning-for-your-organization.md">Organisationsplanung für Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Ermitteln Ihrer Infrastrukturanforderungen für Lync Server 2013</a> und in anderen relevanten Abschnitten der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


## Topologien zur Bereitstellung von Ausfallsicherheit

Die folgende Abbildung zeigt die empfohlenen Topologien zum Gewährleisten von Ausfallsicherheit für einen Zweigstellenstandort.

**Optionen für die Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte**

![VoIP-Zweig: Ausfallsicherheitsoptionen](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "VoIP-Zweig: Ausfallsicherheitsoptionen")

## Details zur Survivable Branch Appliance

Die Survivable Branch Appliance von Lync Server umfasst die folgenden Komponenten:

  - Einen Registrierungsserver für Benutzerauthentifizierung, Registrierung und Anrufrouting

  - Einen Vermittlungsserver für die Signalverarbeitung zwischen der Registrierung und einem PSTN-Gateway

  - Ein PSTN-Gateway zum Routen von Anrufen an das Telefonfestnetz als Fallback bei WAN-Ausfällen

  - SQL Server Express zur Speicherung lokaler Benutzerdaten

Die Survivable Branch-Anwendung umfasst außerdem PSTN-Trunks, analoge Ports und einen Ethernet-Adapter.

Wenn die WAN-Verbindung zwischen einem Zweigstellenstandort und einem zentralen Standort nicht verfügbar ist, können interne Benutzer am Zweigstellenstandort weiterhin bei der Survivable Branch-Anwendung-Registrierung registriert werden, sodass über die Survivable Branch-Anwendung-Verbindung mit dem Telefonfestnetz durchgängig VoIP-Dienste zur Verfügung gestellt werden können. Zweigstellenbenutzer, die von zu Hause oder von Remotestandorten aus eine Verbindung herstellen, können sich beim Registrierungsserver am zentralen Standort registrieren, wenn die WAN-Leitung zum Zweigstellenstandort nicht verfügbar ist. Diese Benutzer haben Zugriff auf die vollständige Unified Communications-Funktionalität (UM), mit der Ausnahme, dass eingehende Anrufe am Zweigstellenstandort an das Voicemailsystem übermittelt werden. Wenn die WAN-Verbindung wieder verfügbar ist, sollte für Benutzer am Zweigstellenstandort automatisch die vollständige Funktionalität wiederhergestellt werden. Weder für das Failover auf die Survivable Branch-Anwendung noch für die Wiederherstellung der Dienste ist die Anwesenheit eines IT-Administrators erforderlich.

Lync Server unterstützt bis zu zwei Survivable Branch-Anwendungs an einer Zweigstelle.

## Übersicht über die Bereitstellung einer Survivable Branch Appliance

Die Survivable Branch-Anwendung wird durch Originalgerätehersteller (Original Equipment Manufacturers, OEMs) in Partnerschaft mit Microsoft hergestellt und in deren Namen durch Vertragshändler bereitgestellt. Diese Bereitstellung sollte erst dann erfolgen, wenn Lync Server am zentralen Standort bereitgestellt und eine WAN-Verbindung zum Zweigstellenstandort eingerichtet wurde und die Zweigstellenbenutzer für Enterprise-VoIP aktiviert wurden.

Ausführliche Informationen zu diesen Phasen finden Sie unter [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in der Bereitstellungsdokumentation.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Benutzerrechte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Einrichten von Active Directory-Domänendiensten für die Survivable Branch-Anwendung</p></td>
<td><p><strong>Am zentralen Standort:</strong></p>
<ol>
<li><p>Erstellen Sie ein Domänenbenutzerkonto (oder Unternehmensidentität) für den Techniker, der die Survivable Branch-Anwendung am Zweigstellenstandort installiert und aktiviert.</p></li>
<li><p>Erstellen Sie in Active Directory Domain Services ein Computerkonto (mit geeignetem FQDN) für die Survivable Branch-Anwendung.</p></li>
<li><p>Erstellen und veröffentlichen Sie die Survivable Branch-Anwendung im Topologie-Generator.</p></li>
</ol></td>
<td><p>Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe &quot;RTCUniversalSBATechnicians&quot; sein. Die Survivable Branch-Anwendung muss der Gruppe &quot;RTCSBAUniversalServices&quot; hinzugefügt werden. Dies geschieht bei Verwendung des Topologie-Generators automatisch.</p></td>
</tr>
<tr class="even">
<td><p>Installieren und aktivieren Sie die Survivable Branch-Anwendung.</p></td>
<td><p><strong>Am Zweigstellenstandort:</strong></p>
<ol>
<li><p>Verbinden Sie die Survivable Branch-Anwendung mit einem Ethernet-Port und einem PSTN-Port.</p></li>
<li><p>Starten Sie die Survivable Branch-Anwendung.</p></li>
<li><p>Fügen Sie die Survivable Branch-Anwendung unter Verwendung des Domänenkontos, das Sie am zentralen Standort für die Survivable Branch-Anwendung erstellt haben, zur Domäne hinzu. Legen Sie FQDN und IP-Adresse auf den FQDN fest, den Sie im Computerkonto erstellt haben.</p></li>
<li><p>Konfigurieren Sie die Survivable Branch-Anwendung unter Verwendung der OEM-Benutzerschnittstelle.</p></li>
<li><p>Testen Sie die PSTN-Anbindung.</p></li>
</ol></td>
<td><p>Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe &quot;RTCUniversalSBATechnicians&quot; sein.</p></td>
</tr>
</tbody>
</table>


## Details zum Survivable Branch Server

Erstellen Sie im Topologie-Generator den Zweigstellenstandort, fügen Sie den Survivable Branch-Server zu diesem Standort hinzu, und führen Sie den Lync Server-Bereitstellungs-Assistenten auf dem Computer aus, auf dem Sie die Rolle installieren möchten.

## Siehe auch

#### Weitere Ressourcen

[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)


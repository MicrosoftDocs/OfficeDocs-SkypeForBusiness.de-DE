---
title: 'Lync Server 2013: Ports und Protokolle für interne Server '
TOCTitle: Ports und Protokolle für interne Server
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398833(v=OCS.15)
ms:contentKeyID: 49295389
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ports und Protokolle für interne Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-04-06_

In diesem Abschnitt werden die von Servern, Lastenausgleichssystemen und Clients in einer Lync Server-Bereitstellung verwendeten Ports und Protokolle beschrieben.


> [!IMPORTANT]
> Wenn Lync- und Communicator-Clients an einer Eins-zu-Eins-Kommunikation beteiligt sind, wird dies häufig als Peer-to-Peer-Situation bezeichnet. Vom technischen Standpunkt aus gesehen, kommunizieren die zwei Clients in einer Eins-zu-Eins-Unterhaltung mit der Multipoint Control Unit für Instant Messaging (IMMCU) als Bindeglied. Die IMMCU stellt eine Komponente von Front-End-Server dar. Die Platzierung der IMMCU im erforderlichen Kommunikationsworkflow ermöglicht die Aufzeichnung von Anrufdetails und weitere Features, die durch den Front-End-Server bereitgestellt werden. Die Kommunikation erfolgt von einem dynamischen Quellport auf dem Client an den Front-End-Server-Port TLS/TCP/5061 (bei angenommener Verwendung der empfohlenen Sicherheit in der Transportschicht). Konstruktionsbedingt ist Peer-to-Peer-Kommunikation (sowie Chat mit mehreren Teilnehmern) nur möglich, wenn Lync Server und die IMMCU aktiv und verfügbar sind.



## Port- und Protokolldetails


> [!NOTE]
> Die Windows-Firewall muss ausgeführt werden, bevor Sie die Lync Server-Dienste auf einem Server starten, da Lync Server dann die erforderlichen Ports in der Firewall öffnet.



Ausführliche Informationen zur Firewallkonfiguration für Edgekomponenten finden Sie unter [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

In der folgenden Tabelle werden alle Ports aufgeführt, die auf jeder internen Serverrolle geöffnet werden müssen.

### Erforderliche Serverports (nach Serverrolle)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Serverrolle</th>
<th>Name des Diensts</th>
<th>Port</th>
<th>Protokoll</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Alle Server</p></td>
<td><p>SQL-Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL-Browser für die lokal replizierte Kopie der Datenbank des zentralen Verwaltungsspeichers.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Wird optional von Standard Edition- und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End- und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit dem Monitoring Server verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Wird für die HTTPS-Kommunikation zwischen dem Konferenzzustandsobjekt (der Lync Server-Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.</p>
<p>Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch-Anwendungen und Front-End-Servern verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>135</p></td>
<td><p>DCOM und Remoteprozeduraufruf (RPC)</p></td>
<td><p>Wird für DCOM-basierte Vorgänge wie z. B. das Verschieben von Benutzern, die Synchronisierung des Benutzerreplikationsdiensts und die Synchronisierung von Adressbüchern verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Chatkonferenzdienst</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Webkonferenzdienst</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Webkonferenz-Kompatibilitätsdienst</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Live Meeting-Client und von früheren Lync Server-Versionen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-A/V-Konferenzdienst</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-A/V-Konferenzdienst</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Für Videokonferenzen verwendeter Medienportbereich.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Webkompatibilitätsdienst</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten verwendete URLs) verwendet, wenn kein HTTPS verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Webkompatibilitätsdienst</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten verwendete URLs) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Webkompatibilitätsdienst</p></td>
<td><p>8080</p></td>
<td><p>TCP und HTTP</p></td>
<td><p>Wird von Webkomponenten für den externen Zugriff verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Mobilitätsdienstekomponente</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Mobilitätsdienstekomponente</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Mobilitätsdienstekomponente</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Konferenzzentralendienst (Einwahlkonferenzen)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Konferenzzentralendienst (Einwahlkonferenzen)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Vermittlung (Einwahlkonferenzen) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p>
<p></p></td>
<td><p>Lync Server-Vermittlungsdienst</p>
<p></p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p>
<p></p></td>
<td><p>Lync Server-Vermittlungsdienst</p>
<p></p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Anwendungsfreigabedienst</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Anwendungsfreigabedienst</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Für die Anwendungsfreigabe verwendeter Medienportbereich.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Konferenzankündigungsdienst</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den Lync Server-Konferenzankündigungsdienst (d. h. für Einwahlkonferenzen) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Dienst zum Parken von Anrufen</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Audiotestdienst</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>Wird für das ausgehende E9-1-1-Gateway (9-1-1 [erweitert]) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Reaktionsgruppendienst</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Reaktionsgruppendienst</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Bandbreitenrichtliniendienst</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für TURN-Datenverkehr vom A/V-Edgeserver verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Bandbreitenrichtliniendienst</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die Anrufsteuerung durch den Lync Server-Bandbreitenrichtliniendienst verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server mit dem zentraler Verwaltungsspeicher</p></td>
<td><p>Dienst für den Master-Replikations-Agent von Lync Server</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Wird zum Pushen von Konfigurationsdaten von dem zentraler Verwaltungsspeicher auf Server verwendet, auf denen Lync Server ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>Alle Server</p></td>
<td><p>SQL-Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL-Browser für die lokal replizierte Kopie der zentralen Verwaltungsspeicher-Daten in der lokalen SQL Server-Instanz.</p></td>
</tr>
<tr class="odd">
<td><p>Alle internen Server</p></td>
<td><p>Verschiedene</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern mit Audioterminierung verwendet: Front-End-Server (für den Lync Server-Konferenzzentralendienst, den Lync Server-Konferenzankündigungsdienst und den Lync Server-A/V-Konferenzdienst) und Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps-Server</p></td>
<td><p></p></td>
<td><p>443</p></td>
<td><p></p></td>
<td><p>Wird von Lync Server 2013 zur Verbindung mit dem Office Web Apps-Server verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Directors</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Wird optional für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Directors</p></td>
<td><p>Lync ServerFront-End-Dienst</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus Clientzertifikatveröffentichung (an Front-End-Server) oder ‑überprüfung, ob das Clientzertifikat bereits veröffentlicht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>Directors</p></td>
<td><p>Lync Server-Webkompatibilitätsdienst</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten verwendeten URLs) verwendet. Im Normalbetrieb wird auf HTTPS-Datenverkehr mit Port 443 und Protokolltyp TCP umgeschaltet.</p></td>
</tr>
<tr class="even">
<td><p>Directors</p></td>
<td><p>Lync Server-Webkompatibilitätsdienst</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten verwendeten URLs) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Directors</p></td>
<td><p>Lync ServerFront-End-Dienst</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Wird für SIP-Anforderungen von den Front-End-Servern verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server für beständigen Chat</p></td>
<td><p>SIP für beständigen Chat</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server für beständigen Chat</p></td>
<td><p>Windows Communication Foundation (WCF) für beständigen Chat</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) und TCP (MTLS)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server für beständigen Chat</p></td>
<td><p>Dateiübertragungsdienst für beständigen Chat</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> In einigen Szenarien mit Remoteanrufsteuerung ist eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage erforderlich. Wenngleich TCP-Port&nbsp;5060 in Lync Server nicht mehr verwendet wird, können Sie bei der Bereitstellung der Remoteanrufsteuerung eine Konfiguration mit vertrauenswürdigen Servern erstellen, in der der FQDN des Anschlussservers für die Remoteanrufsteuerung dem TCP-Port zugeordnet wird, der vom Front-End-Server oder vom Director zur Verbindung mit der Nebenstellenanlage verwendet wird. Ausführliche Informationen hierzu finden Sie im Abschnitt zum Cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> in der Dokumentation zur Lync Server-Verwaltungsshell.



Für Pools, in denen nur Hardwaregeräte zum Lastenausgleich (kein DNS-Lastenausgleich) verwendet werden, zeigen die folgenden Tabellen die Ports, die für die Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.

### Ports für Hardwaregeräte zum Lastenausgleich, wenn nur ein Hardwarelastenausgleich verwendet wird

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Lastenausgleichssystem</th>
<th>Port</th>
<th>Protokoll</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>135</p></td>
<td><p>DCOM und Remoteprozeduraufruf (RPC)</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>8080</p></td>
<td><p>TCP – Abruf des Stammzertifikats für Clients und Geräte über den Front-End-Server – NTLM-Authentifizierung der Clients und Geräte</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p>
<p></p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem (wenn im Pool auch ein Vermittlungsserver ausgeführt wird)</p>
<p></p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleichssystem</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Director-Lastenausgleichssystem</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleichssystem</p>
<p></p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Director-Lastenausgleichssystem</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
</tbody>
</table>


Für die Front-End- und Director-Pools, die DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle werden die Ports aufgeführt, die auf diesen Hardwaregeräten geöffnet werden müssen.

### Ports für Hardwaregeräte zum Lastenausgleich, wenn DNS-Lastenausgleich verwendet wird

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Lastenausgleichssystem</th>
<th>Port</th>
<th>Protokoll</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>8080</p></td>
<td><p>TCP – Abruf des Stammzertifikats für Clients und Geräte über den Front-End-Server – NTLM-Authentifizierung der Clients und Geräte</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleichssystem</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleichssystem</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
</tbody>
</table>


### Erforderliche Clientports

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Komponente</th>
<th>Port</th>
<th>Protokoll</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Wird von Lync Server zur Ermittlung des Registrierungsstellen-FQDN verwendet (d. h. falls bei DNS-SRV ein Fehler auftritt und keine manuellen Einstellungen konfiguriert sind).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p>
<p></p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>Wird für Dateiübertragungen zwischen Lync-Clients und vorherigen Clientversionen verwendet (Microsoft Office Communications Server 2007 R2-Clients, Microsoft Office Communications Server 2007-Clients und Live Communications Server 2005-Clients).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Audioportbereich (mindestens 20 Ports erforderlich).</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p>
<p></p></td>
<td><p>Videoportbereich (mindestens 20 Ports erforderlich).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Peer-zu-Peer-Dateiübertragungen (zur Übertragung von Konferenzdateien verwenden Clients PSOM-Verbindungen).</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Anwendungsfreigabe.</p></td>
</tr>
<tr class="even">
<td><p>Aastra 6721ip (Telefon für öffentliche Bereiche)</p>
<p>Telefonapparat Aastra 6725ip</p>
<p>IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)</p>
<p>IP-Telefon HP 4120 (Telefonapparat)</p>
<p>IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)</p>
<p>IP-Telefonapparat Polycom CX600</p>
<p>IP-Telefonapparat Polycom CX700</p>
<p>IP-Konferenztelefon Polycom CX3000</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Wird von den gelisteten Geräten zum Ermitteln des Lync Server-Zertifikats, des FQDN für die Bereitstellung und des Registrierungsstellen-FQDN verwendet.</p></td>
</tr>
</tbody>
</table>


**\*** Zum Konfigurieren spezieller Ports für diese Medientypen verwenden Sie das Cmdlet **CsConferencingConfiguration** (Parameter **ClientMediaPortRangeEnabled**, **ClientMediaPort** und **ClientMediaPortRange**).


> [!NOTE]
> Zum Festlegen von Progammen für Lync-Clients müssen die erforderlichen Betriebssystemfirewall-Ausnahmen auf dem Clientcomputer automatisch erstellt werden.




> [!NOTE]
> Die für den externen Benutzerzugriff verwendeten Ports werden für jedes Szenario benötigt, in dem der Client die Firewall der Organisation durchqueren muss (z.&nbsp;B. bei externer Kommunikation oder bei Besprechungen, die von anderen Organisationen gehostet werden).



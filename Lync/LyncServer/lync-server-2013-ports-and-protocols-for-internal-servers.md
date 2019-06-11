---
title: 'Lync Server 2013: Ports und Protokolle für interne Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Ports und Protokolle für interne Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-04-06_

In diesem Abschnitt werden die Ports und Protokolle zusammengefasst, die von Servern, Load-Balancern und Clients in einer lync Server-Bereitstellung verwendet werden.

<div>


> [!IMPORTANT]  
> Lync-und Communicator-Clients werden, wenn Sie an einer 1:1-Kommunikation beteiligt sind, häufig als Peer-to-Peer bezeichnet. Technisch gesehen kommunizieren die beiden Clients in einer 1:1-Konversation mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte. Die IMMCU ist eine Komponente des Front-End-Servers. Wenn Sie den IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Anrufdetailaufzeichnung und andere Features, die der Front-End-Server ermöglicht, aufzeichnen. Die Kommunikation erfolgt von einem dynamischen Quell Port auf dem Client zum Front-End-Serverport TLS/TCP/5061 (unter der Voraussetzung, dass die empfohlene Transportschichtsicherheit verwendet wird). Die Peer-to-Peer-Kommunikation (ebenso wie die Chat Unterhaltung mit mehreren Teilnehmern) ist im Entwurf nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.



</div>

<div>

## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

<div>


> [!NOTE]  
> Die Windows-Firewall muss ausgeführt werden, bevor Sie die lync Server-Dienste auf einem Server starten, weil dies der Fall ist, wenn lync Server die erforderlichen Ports in der Firewall öffnet.



</div>

Details zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

In der folgenden Tabelle werden alle Ports aufgeführt, die auf jeder internen Serverrolle geöffnet werden müssen.

### <a name="required-server-ports-by-server-role"></a>Erforderliche Serverports (nach Serverrolle)

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
<td><p>SQL-Browser für die lokale replizierte Kopie der Datenbank des zentralen Verwaltungsspeichers.</p></td>
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
<td><p>Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End- und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit Monitoring Server verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Wird für die HTTPS-Kommunikation zwischen dem Fokus (der lync-Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.</p>
<p>Dieser Port wird auch für die TCP-Kommunikation zwischen Überlebenden Branch-Appliances und Front-End-Servern verwendet.</p></td>
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
<td><p>Lync Server im-Konferenzdienst</p></td>
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
<td><p>Wird verwendet, um auf Persistent Shared Object Model (PSOM)-Verbindungen vom Live Meeting-Client und früheren Versionen von lync Server zu lauschen.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Audio/Video Konferenzdienst</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Audio/Video Konferenzdienst</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Für Videokonferenzen verwendeter Medienportbereich.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet, wenn kein HTTPS verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>8080</p></td>
<td><p>TCP und HTTP</p></td>
<td><p>Wird von Webkomponenten für den externen Zugriff verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Servern für die AutoErmittlungsanmeldung.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Mobilitätsdienstekomponente</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Mobilitätsdienstekomponente</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Mobilitätsdienstekomponente</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Conferencing Attendant-Dienst (Einwahlkonferenzen)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Conferencing Attendant-Dienst (Einwahlkonferenzen)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Attendant (Dial in Conferencing) verwendet.</p></td>
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
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server-Vermittlungsdienst</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Anwendungsfreigabe Dienst</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-Anwendungsfreigabe Dienst</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Für die Anwendungsfreigabe verwendeter Medienportbereich.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Ankündigungsdienst für lync Server-Konferenzen</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den lync Server Conferencing-Ankündigungsdienst (also für Einwahlkonferenzen) verwendet.</p></td>
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
<td><p>Lync Server-audiotestdienst</p></td>
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
<td><p>Lync Server-bandbreitenrichtliniendienst</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für TURN-Datenverkehr vom A/V-Edgeserver verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-bandbreitenrichtliniendienst</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die Anrufsteuerung vom lync Server-bandbreitenrichtliniendienst verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server, auf denen sich der zentrale Verwaltungsspeicher befindet</p></td>
<td><p>Lync Server-Master-Replicator-Agent-Dienst</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Wird verwendet, um Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit lync Server zu übertragen.</p></td>
</tr>
<tr class="even">
<td><p>Alle Server</p></td>
<td><p>SQL-Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL-Browser für lokale replizierte Kopie von Daten des zentralen Verwaltungsspeichers in einer lokalen SQL Server-Instanz</p></td>
</tr>
<tr class="odd">
<td><p>Alle internen Server</p></td>
<td><p>Verschiedene</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für den lync Server Conferencing Attendant-Dienst, lync Server Conferencing Announcement Service und lync Server-Audio/Video Konferenzdienst) und Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps-Server</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Wird von lync Server 2013 zum Herstellen einer Verbindung mit Office Web Apps Server verwendet.</p></td>
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
<td><p>Lync Server-Front-End-Dienst</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus veröffentlichen Clientzertifikate (auf Front-End-Servern) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>Directors</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet. Im Normalbetrieb wird auf HTTPS-Datenverkehr mit Port 443 und Protokolltyp TCP umgeschaltet.</p></td>
</tr>
<tr class="even">
<td><p>Directors</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Directors</p></td>
<td><p>Lync Server-Front-End-Dienst</p></td>
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
<td></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server für beständigen Chat</p></td>
<td><p>Windows Communication Foundation (WCF) für beständigen Chat</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) und TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Front-End-Server für beständigen Chat</p></td>
<td><p>Dateiübertragungsdienst für beständigen Chat</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> In einigen Szenarien mit Remoteanrufsteuerung ist eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage erforderlich. Obwohl der TCP-Port 5060 von lync Server nicht mehr verwendet wird, erstellen Sie während der Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director für die Verbindung mit dem PBX-System verwendet. Ausführliche Informationen finden Sie im <STRONG>CsTrustedApplicationComputer</STRONG> -Cmdlet in der Dokumentation zur lync Server-Verwaltungsshell.



</div>

Für Pools, in denen nur Hardwaregeräte zum Lastenausgleich (kein DNS-Lastenausgleich) verwendet werden, zeigen die folgenden Tabellen die Ports, die für die Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>Ports für Hardwaregeräte zum Lastenausgleich, wenn nur ein Hardwarelastenausgleich verwendet wird

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
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver-Lastenausgleichssystem</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server-Lastenausgleichssystem (wenn im Pool auch ein Vermittlungsserver ausgeführt wird)</p></td>
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
<td><p>Director-Lastenausgleichssystem</p></td>
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


Für die Front-End- und Director-Pools, die DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle werden die Ports aufgeführt, die auf diesen Hardwaregeräten geöffnet sein müssen.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>Ports für Hardwaregeräte zum Lastenausgleich, wenn DNS-Lastenausgleich verwendet wird

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


### <a name="required-client-ports"></a>Erforderliche Clientports

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
<td><p>Wird von lync Server verwendet, um den FQDN der Registrierungsstelle zu finden (das heißt, wenn DNS SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
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
<td><p>Wird für die Dateiübertragung zwischen lync-Clients und vorherigen Clients (Clients von Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 und Live Communications Server 2005) verwendet.</p></td>
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
<td><p>TCP/UDP</p></td>
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
<td><p>Wird von den aufgelisteten Geräten verwendet, um das lync Server-Zertifikat, den Bereitstellungs-FQDN und den FQDN der Registrierungsstelle zu finden.</p></td>
</tr>
</tbody>
</table>


**\*** Wenn Sie bestimmte Ports für diese Medientypen konfigurieren möchten, verwenden Sie das CsConferencingConfiguration-Cmdlet (ClientMediaPortRangeEnabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).

<div>


> [!NOTE]  
> Mit den Einstellungen für lync-Clients werden die erforderlichen Ausnahmen für das Betriebssystem auf dem Clientcomputer automatisch erstellt.



</div>

<div>


> [!NOTE]  
> Die für den externen Benutzerzugriff verwendeten Ports werden für jedes Szenario benötigt, in dem der Client die Firewall der Organisation durchqueren muss (z. B. bei externer Kommunikation oder bei Besprechungen, die von anderen Organisationen gehostet werden).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


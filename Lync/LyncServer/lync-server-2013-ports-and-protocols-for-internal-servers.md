---
title: 'Lync Server 2013: Ports und Protokolle für interne Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c748a79fe118c9b1d233a7a276bd8298a0e1c3e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Ports und Protokolle für interne Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-04-06_

In diesem Abschnitt werden die von Servern, Lastenausgleichssystemen und Clients in einer lync Server-Bereitstellung verwendeten Ports und Protokolle zusammengefasst.

<div>


> [!IMPORTANT]  
> Lync-und Communicator-Clients werden, wenn Sie an einer Kommunikation mit einem einzelnen beteiligt sind, häufig als Peer-to-Peer bezeichnet. Technisch gesehen kommunizieren die beiden Clients in einer eins-zu-eins-Unterhaltung mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte. IMMCU ist eine Komponente von Front-End-Server. Wenn Sie die IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Aufzeichnung von Anrufdetails und andere Features, die der Front-End-Server aktiviert, aktivieren. Die Kommunikation erfolgt über einen dynamischen Quell Port auf dem Client zum Front-End-Server Port TLS/TCP/5061 (vorausgesetzt, dass die empfohlene Transportschichtsicherheit verwendet wird). Die Peer-zu-Peer-Kommunikation (sowie mehr Parteien-Chat) ist nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.



</div>

<div>

## <a name="port-and-protocol-details"></a>Port-und Protokoll Details

<div>


> [!NOTE]  
> Die Windows-Firewall muss gestartet werden, bevor Sie die lync Server Dienste auf einem Server starten, da lync Server die erforderlichen Ports in der Firewall öffnet.



</div>

Ausführliche Informationen zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

In der folgenden Tabelle sind die Ports aufgeführt, die für jede interne Serverrolle geöffnet sein müssen.

### <a name="required-server-ports-by-server-role"></a>Erforderliche Serverports (nach Server Rolle)

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
<th>Dienstname</th>
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
<td><p>SQL-Browser für die lokale replizierte Kopie der zentraler Verwaltungsspeicher Datenbank.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Optional von Standard Edition-Servern und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End-Servern und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit Monitoring Server verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Wird für die HTTPS-Kommunikation zwischen dem Fokus (der lync Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.</p>
<p>Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>135</p></td>
<td><p>DCOM und Remoteprozeduraufruf (RPC)</p></td>
<td><p>Wird für DCOM-basierte Vorgänge wie das Verschieben von Benutzern, die Benutzer Replikationssynchronisierung und die Adressbuchsynchronisierung verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Sofortnachrichten-Konferenzdienst</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Chat Konferenzen (Instant Messaging) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Webkonferenzdienst</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Webkonferenz-Kompatibilitätsdienst</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) aus dem Live Meeting-Client und früheren Versionen von lync Server verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Audio/Video-Konferenzdienst</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Audio/Video-Konferenzen (A/V) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Audio/Video-Konferenzdienst</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Für Videokonferenzen verwendeter Medienportbereich.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten verwendete URLs) verwendet, wenn kein HTTPS verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>8080</p></td>
<td><p>TCP und http</p></td>
<td><p>Wird von Webkomponenten für den externen Zugriff verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Webserverkomponente</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Pools für die Auto Ermittlungs Anmeldung.</p></td>
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
<td><p>Komponente "Mobility Services"</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>SIP-Port für interne Prozesse der Mobilitätsdienste</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Komponente "Mobility Services"</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>SIP-Port für interne Prozesse der Mobilitätsdienste</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Komponente "Mobility Services"</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für Attendant (Einwahlkonferenzen) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server zum Vermittlungsserver verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Anwendungsfreigabe Dienst</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Anwendungsfreigabe Dienst</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Für die Anwendungsfreigabe verwendete Medienportbereich.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Konferenz Ansagedienst</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den lync Server Konferenzankündigungsdienst (für Einwahlkonferenzen) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Dienst zum Parken von Anrufen</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den Anwendung zum Parken von Anrufen verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Audio-Test Dienst</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den Audio-Test Dienst verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>Wird für das ausgehende Enhanced 9-1-1 (E9-1-1)-Gateway verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Reaktionsgruppendienst</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server Reaktionsgruppendienst</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server bandbreitenrichtliniendienst</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die Anrufsteuerung durch den bandbreitenrichtliniendienst für A/V-Edge-Umdrehungs Datenverkehr verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server</p></td>
<td><p>Lync Server bandbreitenrichtliniendienst</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die Anrufsteuerung vom lync Server bandbreitenrichtliniendienst verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet</p></td>
<td><p>Lync Server des Master Replicator-Agent-Diensts</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Wird zum Pushen von Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit lync Server verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Alle Server</p></td>
<td><p>SQL-Browser</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>SQL-Browser für lokale replizierte Kopie der Daten des zentralen Verwaltungsspeichers in der lokalen SQL Server Instanz</p></td>
</tr>
<tr class="odd">
<td><p>Alle internen Server</p></td>
<td><p>Verschiedene</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Medienportbereich, der für Audiokonferenzen auf allen internen Servern verwendet wird. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für lync Server Konferenz Aufsichtsdienst, lync Server Konferenzankündigungsdienst und lync Server Audio/Video-Konferenzdienst) und Vermittlungsserver.</p></td>
</tr>
<tr class="even">
<td><p>Office-webapps-Server</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Wird von lync Server 2013 verwendet, um eine Verbindung mit Office-webapps Server herzustellen.</p></td>
</tr>
<tr class="odd">
<td><p>Verwaltungsrat</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Optional für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungsrat</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Kommunikation zwischen Servern zwischen Front-End und Director. Darüber hinaus veröffentlichen Clientzertifikate (an Front-End-Server) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>Verwaltungsrat</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet. Im normalen Betrieb wechselt zum HTTPS-Datenverkehr unter Verwendung von Port 443 und Protokolltyp TCP.</p></td>
</tr>
<tr class="even">
<td><p>Verwaltungsrat</p></td>
<td><p>Lync Server-webkompatibilitäts Dienst</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Verwaltungsrat</p></td>
<td><p>Lync Server Front-End-Dienst</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver</p></td>
<td><p>Lync Server Vermittlungsdienst</p></td>
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
> Einige Szenarien für die Remoteanrufsteuerung erfordern eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage. Obwohl lync Server TCP-Port 5060 nicht mehr verwendet, erstellen Sie während der Bereitstellung von Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem PBX-System verwendet. Ausführliche Informationen finden Sie im <STRONG>CsTrustedApplicationComputer</STRONG> -Cmdlet in der lync Server-Verwaltungsshell Dokumentation.



</div>

Für Ihre Pools, in denen nur Hardwarelastenausgleich (nicht DNS-Lastenausgleich) verwendet wird, werden in der folgenden Tabelle die Ports aufgeführt, die zum Öffnen der Hardwarelastenausgleichs-Geräte erforderlich sind.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>Hardware Lastenausgleichs-Ports bei Verwendung von nur Hardwarelastenausgleich

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Lastenausgleichsmodul</th>
<th>Port</th>
<th>Protokoll</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>135</p></td>
<td><p>DCOM und Remoteprozeduraufruf (RPC)</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>8080</p></td>
<td><p>TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server – von NTLM authentifizierte Clients und Geräte</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Vermittlungsserver Lastenausgleich</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich (wenn der Pool auch Vermittlungsserver ausgeführt wird)</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleich</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Director-Lastenausgleich</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleich</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Director-Lastenausgleich</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
</tbody>
</table>


Für die Front-End-Pools und Director-Pools, die den DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle sind die Ports aufgeführt, die für diese Hardwarelastenausgleichs-Geräte geöffnet sein müssen.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>Hardware Lastenausgleichs-Ports bei Verwendung des DNS-Lastenausgleichs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Lastenausgleichsmodul</th>
<th>Port</th>
<th>Protokoll</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>8080</p></td>
<td><p>TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server – von NTLM authentifizierte Clients und Geräte</p></td>
</tr>
<tr class="even">
<td><p>Front-End-Server Lastenausgleich</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleich</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Director-Lastenausgleich</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (vom Reverseproxy)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>Erforderliche Client-Ports

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
<td><p>Wird von lync Server verwendet, um den FQDN des Registrars zu finden (wenn DNS-SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Wird für den Zugriff durch externe Benutzer auf Webkonferenz Sitzungen verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>443</p></td>
<td><p>TCP (Stun/MSTURN)</p></td>
<td><p>Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (TCP) verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>3478</p></td>
<td><p>UDP (Stun/MSTURN)</p></td>
<td><p>Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (UDP) verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.</p></td>
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
<td><p>Audioport Bereich (mindestens 20 Ports erforderlich)</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Video Portbereich (mindestens 20 Ports erforderlich).</p></td>
</tr>
<tr class="even">
<td><p>Clients</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Peer-zu-Peer-Dateiübertragung (für die Übertragung von Konferenz Dateien verwenden Clients PSOM).</p></td>
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
<p>Polycom CX700-IP-Tischtelefon</p>
<p>IP-Konferenztelefon
Polycom CX3000</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Wird von den aufgelisteten Geräten verwendet, um das lync Server Zertifikat, den FQDN der Feststellung und den FQDN der Registrierung zu finden.</p></td>
</tr>
</tbody>
</table>


**\*** Verwenden Sie zum Konfigurieren bestimmter Ports für diese Medientypen das CsConferencingConfiguration-Cmdlet (Parameter clientmediaportrangeenabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).

<div>


> [!NOTE]  
> Die festgelegten Programme für lync-Clients erstellen automatisch die erforderlichen Betriebssystem-Firewall-Ausnahmen auf dem Clientcomputer.



</div>

<div>


> [!NOTE]  
> Die Ports, die für den Zugriff durch externe Benutzer verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (beispielsweise externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


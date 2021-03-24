---
title: Port- und Protokollanforderungen für Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Zusammenfassung: Überprüfen Sie die Überlegungen zur Portnutzung, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: 70caf72231797c4e245ac3117ec7fcc9241185f0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094949"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Port- und Protokollanforderungen für Server
 
**Zusammenfassung:** Überprüfen Sie die Überlegungen zur Portverwendung, bevor Sie Skype for Business Server implementieren.
  
Skype for Business Server erfordert, dass bestimmte Ports für die externe und interne Firewall geöffnet sind. Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden. 
  
Dies mag zunächst etwas bedenklich erscheinen, dies kann jedoch mithilfe des [Skype for Business Server 2015-Planungstools](https://go.microsoft.com/fwlink/p/?LinkID=282725)geplant werden. Nachdem Sie die Fragen des Assistenten zu den features durchgegangen haben, die Sie verwenden möchten, können Sie für jede von Ihnen definierten Website den Firewallbericht im Edge-Admin-Bericht anzeigen und die dort aufgeführten Informationen verwenden, um IhreFirewallregeln zu erstellen. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen. Weitere Informationen finden Sie [unter Review the Firewall Report](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Beachten Sie, dass Sie den Edgeadministratorbericht in eine Excel-Kalkulationstabelle exportieren können, und der Firewallbericht ist eines der Arbeitsblätter in der Datei. 
  
Sie können die Informationen in diesen Tabellen auch in Diagrammform finden, indem Sie das Poster Protocol Workloads überprüfen, das aus dem Artikel Technische Diagramme für [Skype for Business Server 2015 verknüpft](../../technical-diagrams.md) ist.
> [!NOTE]
> - Wenn Sie Skype for Business Online (Microsoft 365 oder Office 365) implementieren, lesen Sie [Microsoft 365- und Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Hybridumgebungen müssen auf dieses Thema verweisen und auch [hybride Verbindungen planen.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
> - Sie können Hardware- oder Softwarefirewalls verwenden, es sind keine bestimmten Modelle oder Versionen erforderlich. Es kommt darauf an, welche Ports auf die Whitelist gesetzt sind, damit die Firewall die Funktionsweise von Skype for Business Server nicht beeinträchtigt.
  
## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

In diesem Abschnitt werden die Ports und Protokolle zusammengefasst, die von Servern, Lastenausgleichsservern und Clients in einer Skype for Business Server-Bereitstellung verwendet werden.
  
> [!NOTE]
> Wenn Skype for Business Server gestartet wird, werden die erforderlichen Ports in der Windows-Firewall geöffnet. Die Windows-Firewall sollte bereits in den meisten normalen Anwendungen ausgeführt werden, aber wenn sie nicht verwendet wird, funktioniert Skype for Business Server ohne sie. 
  
Weitere Informationen zur Firewallkonfiguration für Edgekomponenten finden Sie unter [Edgeserverszenarien in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
In der folgenden Tabelle sind die Ports aufgeführt, die für jede interne Serverrolle geöffnet werden müssen. 
  
**Erforderliche Serverports (nach Serverrolle)**

|Serverrolle|Dienstname|Port|Protokoll|Anmerkungen|
|:-----|:-----|:-----|:-----|:-----|
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL browser for the local replicated copy of the Central Management Store database.  |
|Front-End-Server  |Skype for Business Server Front-End Service  |5060  |TCP  |Wird optional von Standard Edition-Servern und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie Remoteanrufsteuerungsservern verwendet.  |
|Front-End-Server  |Skype for Business Server Front-End Service  |5061  | TCP (TLS) |Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End-Servern und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit einem Monitoring Server verwendet.  |
| Front-End-Server |Skype for Business Server Front-End Service  |444  | HTTPS <br/> TCP  |Wird für die HTTPS-Kommunikation zwischen dem Focus (der Skype for Business Server-Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.  <br/> Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.  |
|Front-End-Server  |Skype for Business Server Front-End Service  |135  |DCOM und Remoteprozeduraufruf (RPC)  |Wird für DCOM-basierte Vorgänge wie Verschieben von Benutzern, Synchronisierung des Benutzerreplikatetors und Adressbuchsynchronisierung verwendet.  |
|Front-End-Server  |Skype for Business Server Chatkonferenzdienst  |5062  |TCP  |Wird für eingehende SIP-Anforderungen für Chatkonferenzen (Instant Messaging) verwendet.  |
|Front-End-Server  |Skype for Business Server Web Conferencing Service  |8057  |TCP (TLS)  |Wird zum Abhören von Verbindungen des beständigen gemeinsamen Objektmodells (Persistent Shared Object Model, PSOM) vom Client verwendet.  |
|Front-End-Server  |Skype for Business Server Web Conferencing Compatibility Service  |8058  |TCP (TLS)  |Wird zum Abhören von Verbindungen des beständigen gemeinsamen Objektmodells (Persistent Shared Object Model, PSOM) vom Live Meeting-Client und früheren Versionen von Skype for Business Server verwendet.  |
|Front-End-Server  |Skype for Business Server Audio/Video Conferencing Service  |5063  |TCP  |Wird für eingehende SIP-Anforderungen für Audio-/Videokonferenzen (A/V) verwendet.  |
|Front-End-Server  |Skype for Business Server Audio/Video Conferencing Service  |57501-65535  |TCP/UDP  |Medienportbereich, der für Videokonferenzen verwendet wird.  |
|Front-End-Server  |Skype for Business Server Web Compatibility Service  |80  |HTTP  |Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (die URLs, die von IIS-Webkomponenten verwendet werden) verwendet, wenn HTTPS nicht verwendet wird.  |
|Front-End-Server  |Skype for Business Server Web Compatibility Service  |443  |HTTPS  |Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm verwendet (die URLs, die von IIS-Webkomponenten verwendet werden).  |
|Front-End-Server  |Skype for Business Server Web Compatibility Service  |8080  |TCP und HTTP  |Wird von Webkomponenten für den externen Zugriff verwendet.  |
|Front-End-Server  |Webserverkomponente  |4443  |HTTPS  |HTTPS (von Reverseproxy) und HTTPS-Front-End-Poolkommunikation für die AutoErmittlungs-Anmeldung.  |
|Front-End-Server  |Webserverkomponente  |8060  |TCP (MTLS)  ||
|Front-End-Server  |Webserverkomponente  |8061  |TCP (MTLS)  ||
|Front-End-Server  |Mobility Services-Komponente  |5086  |TCP (MTLS)  |SIP-Port, der von internen Prozessen von Mobility Services verwendet wird  |
|Front-End-Server  |Mobility Services-Komponente  |5087  |TCP (MTLS)  |SIP-Port, der von internen Prozessen von Mobility Services verwendet wird  |
|Front-End-Server  |Mobility Services-Komponente  |443  |HTTPS  ||
|Front-End-Server  |Skype for Business Server Conferencing Attendant Service (Einwahlkonferenzen)  |5064  |TCP  |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  |
|Front-End-Server  |Skype for Business Server Conferencing Attendant Service (Einwahlkonferenzen)  |5072  |TCP  |Wird für eingehende SIP-Anforderungen für telefonieren (Einwahlkonferenzen) verwendet.  |
|Front-End-Server, auf denen auch ein kollokierter Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein kollokierter Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein kollokierter Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein kollokierter Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5081  |TCP  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server, auf denen auch ein kollokierter Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5082  |TCP (TLS)  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server  |Skype for Business Server Application Sharing Service  |5065  |TCP  |Wird für eingehende SIP-Abhöranforderungen für die Anwendungsfreigabe verwendet.  |
|Front-End-Server  |Skype for Business Server Application Sharing Service  |49152-65535  |TCP  |Medienportbereich, der für die Anwendungsfreigabe verwendet wird.  |
|Front-End-Server  |Skype for Business Server Conferencing Announcement Service  |5073  |TCP  |Wird für eingehende SIP-Anforderungen für den Skype for Business Server-Konferenzansagedienst (d. h. für Einwahlkonferenzen) verwendet.  |
|Front-End-Server  |Skype for Business Server-Anrufparkdienst  |5075  |TCP  |Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.  |
|Front-End-Server  |Skype for Business Server Audio Test Service  |5076  |TCP  |Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.  |
|Front-End-Server  |Nicht zutreffend  |5066  |TCP  |Wird für ausgehendes erweitertes 9-1-1-Gateway (E9-1-1) verwendet.  |
|Front-End-Server  |Skype for Business Server Response Group Service  |5071  |TCP  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppeanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server Response Group Service  |8404  |TCP (MTLS)  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppeanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server Bandwidth Policy Service  |5080  |TCP  |Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für A/V-Edge-TURN-Datenverkehr verwendet.  |
|Front-End-Server  |Zugriff auf den Skype for Business Server-Dateifreigabeserver  |445   |SMB/TCP  | Wird zum Abrufen von Adressbuch, Besprechungsinhalten und anderen Elementen verwendet, die auf dem Dateifreigabeserver gespeichert sind.  |
|Front-End-Server  |Skype for Business Server Bandwidth Policy Service  |448  |TCP  |Wird für die Anrufsteuerung durch den Skype for Business Server Bandwidth Policy Service verwendet.  |
|Front-End-Server, auf denen sich der zentrale Verwaltungsspeicher befindet  | Skype for Business Server Master Replicator Agent Service |445  |TCP  |Wird verwendet, um Konfigurationsdaten aus dem zentralen Verwaltungsspeicher an Server zu übertragen, auf denen Skype for Business Server ausgeführt wird.  |
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL browser for local replicated copy of Central Management store data in local SQL Server instance  |
|Alle internen Server  |Verschiedene  |49152-57500  |TCP/UDP  |Medienportbereich, der für Audiokonferenzen auf allen internen Servern verwendet wird. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für Skype for Business Server-Konferenzkonferenz-Telefonkonferenzdienst, Skype for Business Server-Konferenzansagedienst und Skype for Business Server-Audio-/Videokonferenzdienst) und Vermittlungsserver.  |
|Office Web Apps Server  ||443  ||Wird von Skype for Business Server verwendet, um eine Verbindung mit Office Web Apps Server herzustellen.  |
|Directors  |Skype for Business Server Front-End Service  |5060  |TCP  |Optional für statische Routen zu vertrauenswürdigen Diensten, z. B. Remoteanrufsteuerungsservern.  |
|Directors  |Skype for Business Server Front-End Service  |444  |HTTPS  <br/> TCP  |Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus wird das Clientzertifikat veröffentlicht (auf Front-End-Servern) oder überprüft, ob das Clientzertifikat bereits veröffentlicht wurde.  |
|Directors  |Skype for Business Server Web Compatibility Service  |80  |TCP  |Wird für die anfängliche Kommunikation von Directors mit den FQDNs der Webfarm verwendet (die URLs, die von IIS-Webkomponenten verwendet werden). Wechseln Sie im normalen Betrieb mithilfe von Port 443 und Protokolltyp TCP zu HTTPS-Datenverkehr.  |
|Directors  |Skype for Business Server Web Compatibility Service  |443  |HTTPS  |Wird für die Kommunikation von Directors mit den FQDNs der Webfarm verwendet (die URLs, die von IIS-Webkomponenten verwendet werden).  |
|Directors  |Skype for Business Server Front-End Service  |5061  |TCP  |Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5070  |TCP (MTLS)  |Wird für SIP-Anforderungen von den Front-End-Servern verwendet.  |
|Front-End-Server für beständigen Chat  |SIP für beständigen Chat  |5041  |TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Windows Communication Foundation (WCF) für beständigen Chat  |881  |TCP (TLS) und TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Dateiübertragungsdienst für beständigen Chat  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Einige Remoteanrufsteuerungsszenarien erfordern eine TCP-Verbindung zwischen dem Front-End-Server oder Director und der Nebenstellenanlage. Obwohl Skype for Business Server den TCP-Port 5060 nicht mehr verwendet, erstellen Sie während der Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC Line Server mit dem TCP-Port verknüpft, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem Nebenstellenanlagesystem verwendet. Ausführliche Informationen finden Sie im **Cmdlet CsTrustedApplicationComputer** in der Dokumentation zur Skype for Business Server Management Shell.
  
Für Ihre Pools, die nur den Hardwarelastenausgleich (nicht den DNS-Lastenausgleich) verwenden, sind in der folgenden Tabelle die Ports aufgeführt, die die Hardwaregeräte zum Lastenausgleich öffnen müssen.
  
**Hardware Load Balancer Ports if Using Only Hardware Load Balancing**

|Lastenausgleich|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleich  |5061  |TCP (TLS)  |
|Front-End-Server-Lastenausgleich  |444  |HTTPS  |
|Front-End-Server-Lastenausgleich  |135  |DCOM und Remoteprozeduraufruf (RPC)  |
|Front-End-Server-Lastenausgleich  |80  |HTTP  |
|Front-End-Server-Lastenausgleich  |8080  |TCP – Client- und Geräteabruf des Stammzertifikats vom Front-End-Server – Clients und Geräte, die von NTLM authentifiziert werden  |
|Front-End-Server-Lastenausgleich  |443  |HTTPS  |
|Front-End-Server-Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
|Front-End-Server-Lastenausgleich  |5072  |TCP  |
|Front-End-Server-Lastenausgleich  |5073  |TCP  |
|Front-End-Server-Lastenausgleich  |5075  |TCP  |
|Front-End-Server-Lastenausgleich  |5076  |TCP  |
|Front-End-Server-Lastenausgleich  |5071  |TCP  |
|Front-End-Server-Lastenausgleich  |5080  |TCP  |
|Front-End-Server-Lastenausgleich  |448  |TCP  |
|Vermittlungsserver-Lastenausgleich  |5070  |TCP  |
|Front-End-Server-Lastenausgleich (wenn der Pool auch vermittlungsserver ausgeführt wird)  |5070  |TCP  |
|Director Load Balancer  |443  |HTTPS  |
|Director Load Balancer  |444  |HTTPS  |
|Director Load Balancer  |5061  |TCP  |
|Director Load Balancer  |4443  |HTTPS (vom Reverseproxy)  |
   
Ihre Front-End-Pools und Director-Pools, die den DNS-Lastenausgleich verwenden, müssen auch über einen Hardwaregerät zum Lastenausgleich verfügen. In der folgenden Tabelle sind die Ports aufgeführt, die für diese Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.
  
**Hardware-Lastenausgleichsports bei Verwendung des DNS-Lastenausgleichs**

|Lastenausgleich|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleich  |80  |HTTP  |
|Front-End-Server-Lastenausgleich  |443  |HTTPS  |
|Front-End-Server-Lastenausgleich  |8080  |TCP – Client- und Geräteabruf des Stammzertifikats vom Front-End-Server – Clients und Geräte, die von NTLM authentifiziert werden  |
|Front-End-Server-Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
|Director Load Balancer  |443  |HTTPS  |
|Director Load Balancer  |4443  |HTTPS (vom Reverseproxy)  |

**Erforderliche Clientports**

|Komponente|Port|Protokoll|Anmerkungen|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Wird von Skype for Business Server verwendet, um den Registrierungs-FQDN zu finden (d. h., wenn DNS SRV ausfällt und manuelle Einstellungen nicht konfiguriert sind).  |
|Clients  |443  |TCP (TLS)  |Wird für Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff verwendet.  |
|Clients  |443  |TCP (PSOM/TLS)  |Wird für den externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Wird für den externen Benutzerzugriff auf A/V-Sitzungen und Medien (TCP) verwendet.  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Wird für den externen Benutzerzugriff auf A/V-Sitzungen und Medien (UDP) verwendet.  |
|Clients  |5061  |TCP (MTLS)  |Wird für Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff verwendet.  |
|Clients  |6891-6901  |TCP  |Wird für die Dateiübertragung zwischen Skype for Business-Clients und vorherigen Clients verwendet.  |
|Clients  |1024-65535 \*  |TCP/UDP  |Audioportbereich (mindestens 20 Ports erforderlich)  |
|Clients  |1024-65535 \*  |TCP/UDP  |Videoportbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535 \*  |TCP  |Peer-zu-Peer-Dateiübertragung (für die Übertragung von Konferenzdatei verwenden Clients PSOM).  |
|Clients  |1024-65535 \*  |TCP  |Anwendungsfreigabe.  |
|Aastra 6721ip (Telefon für öffentliche Bereiche)  <br/> Telefonapparat Aastra 6725ip  <br/> IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)  <br/> IP-Telefon HP 4120 (Telefonapparat)  <br/> IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)  <br/> IP-Telefonapparat Polycom CX600  <br/> Polycom CX700-IP-Tischtelefon  <br/> IP-Konferenztelefon
Polycom CX3000  |67/68  |DHCP  |Wird von den aufgeführten Geräten verwendet, um das Skype for Business Server-Zertifikat, den FQDN und den Registrierungsstellen-FQDN zu finden.  |
   
\* Verwenden Sie zum Konfigurieren bestimmter Ports für diese Medientypen das Cmdlet CsConferencingConfiguration (Parameter ClientMediaPortRangeEnabled, ClientMediaPort und ClientMediaPortRange).
  
> [!NOTE]
> Die Setupprogramme für Skype for Business-Clients erstellen automatisch die erforderlichen Betriebssystemfirewallausnahmen auf dem Clientcomputer. 

> [!NOTE]
> Die Ports, die für den externen Benutzerzugriff verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (z. B. externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden). 
  
## <a name="ipsec-exceptions"></a>IPsec-Ausnahmen

Für Unternehmensnetzwerke, in denen Internet Protocol Security (IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec über den Bereich der Ports für die Übermittlung von Audio-, Video- und Panoramavideos deaktiviert werden. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.
  
In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert. 
  
**Empfohlene IPsec-Ausnahmen**

|Regelname|Quell-IP|Ziel-IP|Protokoll|Quellport|Zielport|Authentifizierungsanforderung|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V-Edgeserver, intern eingehend  |Any  |A/V-Edgeserver, intern  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Edgeserver, extern eingehend  |Any  |A/V-Edgeserver, extern  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Edgeserver, intern ausgehend  |A/V-Edgeserver, intern  |Any  |UDP &amp; TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Edgeserver, extern ausgehend  |A/V-Edgeserver, extern  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Vermittlungsserver, eingehend  |Any  |Vermittlung  <br/> Server(n)  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Vermittlungsserver, ausgehend  |Vermittlung  <br/> Server(n)  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Konferenzzentrale, eingehend  |Any  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Konferenzzentrale (ausgehend)  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Konferenzserver, eingehend  |Any  |Front-End-Server  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Konferenzen, ausgehend  |Front-End-Server  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Exchange, eingehend  |Any  |Exchange Unified Messaging  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, eingehend  |Any  |Anwendungsfreigabeserver  |TCP  |Any  |Any  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, ausgehend  |Anwendungsfreigabeserver  |Any  |TCP  |Any  |Any  |Nicht authentifizieren  |
|Exchange, ausgehend  |Exchange Unified Messaging  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Clients  |Any  |Any  |UDP  |Angegebener Medienportbereich  |Any  |Nicht authentifizieren  |
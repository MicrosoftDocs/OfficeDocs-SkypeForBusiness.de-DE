---
title: Port-und Protokollanforderungen für Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Zusammenfassung: Überprüfen Sie die Port Nutzungs Überlegungen, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: 613067d90da4fb06811ca1497c83237019b3c021
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297022"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Port-und Protokollanforderungen für Server
 
**Zusammenfassung:** Überprüfen Sie die Port Nutzungs Überlegungen, bevor Sie Skype for Business Server implementieren.
  
Für Skype for Business Server müssen bestimmte Ports an den externen und internen Firewalls geöffnet sein. Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden. 
  
Dies mag zunächst etwas entmutigend erscheinen, aber die schwerwiegende Aufgabe für die Planung kann mit dem [Planning-Tool für Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725)erfolgen. Nachdem Sie die Fragen des Assistenten zu den Features, die Sie verwenden möchten, durchlaufen haben, können Sie für jede von Ihnen definierte Website den firewallbericht im Edge-Administrator Bericht anzeigen und die dort aufgelisteten Informationen verwenden, um yourfirewall-Regeln zu erstellen. Sie können auch Anpassungen an vielen der verwendeten Namen und IP-Adressen vornehmen, um Details finden Sie unter [Überprüfen des Firewall-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Beachten Sie, dass Sie den Bericht Edge-Administrator in eine Excel-Kalkulationstabelle exportieren können, und der firewallbericht eines der Arbeitsblätter in der Datei ist. 
  
Sie können die Informationen in diesen Tabellen auch in Diagrammform finden, indem Sie das Plakat für Protokoll Arbeitsauslastungen überprüfen, das aus dem Artikel [technische Diagramme für Skype for Business Server 2015](../../technical-diagrams.md) verknüpft ist.
> [!NOTE]
> - Wenn Sie Skype for Business Online (Office 365) implementieren, beziehen Sie sich auf [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Hybrid Umgebungen müssen auf dieses Thema verweisen und auch die [Hybrid Konnektivität planen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Sie können über Hardware-oder Softwarefirewalls verfügen, wir benötigen keine bestimmten Modelle oder Versionen. Wichtig ist, welche Ports auf Whitelists basieren, damit die Firewall die Funktionsweise von Skype for Business Server nicht beeinträchtigt.
  
## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

In diesem Abschnitt werden die Ports und Protokolle zusammengefasst, die von Servern, Load-Balancern und Clients in einer Skype for Business Server-Bereitstellung verwendet werden.
  
> [!NOTE]
> Wenn Skype for Business Server gestartet wird, werden die erforderlichen Ports in der Windows-Firewall geöffnet. Die Windows-Firewall sollte bereits in den meisten normalen Anwendungen ausgeführt werden, aber wenn Sie nicht verwendet wird, wird Skype for Business Server ohne Sie funktionieren. 
  
Details zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [Edge-Server Szenarien in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
In der folgenden Tabelle werden alle Ports aufgeführt, die auf jeder internen Serverrolle geöffnet werden müssen. 
  
**Erforderliche Serverports (nach Serverrolle)**

|Serverrolle|Name des Diensts|Port|Protokoll|Hinweise|
|:-----|:-----|:-----|:-----|:-----|
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL-Browser für die lokale replizierte Kopie der Datenbank des zentralen Verwaltungsspeichers.  |
|Front-End-Server  |Skype for Business Server-Front-End-Dienst  |5060  |TCP  |Wird optional von Standard Edition- und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.  |
|Front-End-Server  |Skype for Business Server-Front-End-Dienst  |5061  | TCP (TLS) |Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End- und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit einem Monitoring Server verwendet.  |
| Front-End-Server |Skype for Business Server-Front-End-Dienst  |444  | HTTPS <br/> TCP  |Wird für die HTTPS-Kommunikation zwischen dem Fokus (der Skype for Business-Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.  <br/> Dieser Port wird auch für die TCP-Kommunikation zwischen Überlebenden Branch-Appliances und Front-End-Servern verwendet.  |
|Front-End-Server  |Skype for Business Server-Front-End-Dienst  |135  |DCOM und Remoteprozeduraufruf (RPC)  |Wird für DCOM-basierte Vorgänge wie z. B. das Verschieben von Benutzern, die Synchronisierung des Benutzerreplikationsdiensts und die Synchronisierung von Adressbüchern verwendet.  |
|Front-End-Server  |Skype for Business Server-Chat Konferenzdienst  |5062  |TCP  |Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.  |
|Front-End-Server  |Skype for Business Server-Webkonferenzdienst  |8057  |TCP (TLS)  |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  |
|Front-End-Server  |Kompatibilitätsdienst für Skype for Business Server Web Conferencing  |8058  |TCP (TLS)  |Wird verwendet, um auf Persistent Shared Object Model (PSOM)-Verbindungen über den Live Meeting-Client und frühere Versionen von Skype for Business Server zu lauschen.  |
|Front-End-Server  |Skype for Business Server-Audio/Video Konferenzdienst  |5063  |TCP  |Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.  |
|Front-End-Server  |Skype for Business Server-Audio/Video Konferenzdienst  |57501-65535  |TCP/UDP  |Für Videokonferenzen verwendeter Medienportbereich.  |
|Front-End-Server  |Skype for Business Server-webkompatibilitäts Dienst  |80  |HTTP  |Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet, wenn kein HTTPS verwendet wird.  |
|Front-End-Server  |Skype for Business Server-webkompatibilitäts Dienst  |443  |HTTPS  |Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet.  |
|Front-End-Server  |Skype for Business Server-webkompatibilitäts Dienst  |8080  |TCP und HTTP  |Wird von Webkomponenten für den externen Zugriff verwendet.  |
|Front-End-Server  |Webserverkomponente  |4443  |HTTPS  |HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Servern für die AutoErmittlungsanmeldung.  |
|Front-End-Server  |Webserverkomponente  |8060  |TCP (MTLS)  ||
|Front-End-Server  |Webserverkomponente  |8061  |TCP (MTLS)  ||
|Front-End-Server  |Mobilitätsdienstekomponente  |5086  |TCP (MTLS)  |Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port  |
|Front-End-Server  |Mobilitätsdienstekomponente  |5087  |TCP (MTLS)  |Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port  |
|Front-End-Server  |Mobilitätsdienstekomponente  |443  |HTTPS  ||
|Front-End-Server  |Skype for Business Server Conferencing Attendant Service (Einwahlkonferenzen)  |5064  |TCP  |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  |
|Front-End-Server  |Skype for Business Server Conferencing Attendant Service (Einwahlkonferenzen)  |5072  |TCP  |Wird für eingehende SIP-Anforderungen für Attendant (Dial in Conferencing) verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5081  |TCP  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server-Vermittlungsdienst  |5082  |TCP (TLS)  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server  |Skype for Business Server-Anwendungsfreigabe Dienst  |5065  |TCP  |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  |
|Front-End-Server  |Skype for Business Server-Anwendungsfreigabe Dienst  |49152-65535  |TCP  |Für die Anwendungsfreigabe verwendeter Medienportbereich.  |
|Front-End-Server  |Skype for Business Server-Konferenzankündigungsdienst  |5073  |TCP  |Wird für eingehende SIP-Anforderungen für den Skype for Business Server-Konferenzankündigungsdienst (für Einwahlkonferenzen) verwendet.  |
|Front-End-Server  |Skype for Business Server-Anruf Park Service  |5075  |TCP  |Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.  |
|Front-End-Server  |Skype for Business Server-audiotestdienst  |5076  |TCP  |Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.  |
|Front-End-Server  |Nicht zutreffend  |5066  |TCP  |Wird für das ausgehende E9-1-1-Gateway (9-1-1 [erweitert]) verwendet.  |
|Front-End-Server  |Skype for Business Server-Reaktionsgruppendienst  |5071  |TCP  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server-Reaktionsgruppendienst  |8404  |TCP (MTLS)  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server-bandbreitenrichtliniendienst  |5080  |TCP  |Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für TURN-Datenverkehr vom A/V-Edgeserver verwendet.  |
|Front-End-Server  |Zugriff auf den Dateifreigabeserver für Skype for Business Server  |445   |SMB/TCP  | Dient zum Abrufen des Adressbuchs, des Besprechungsinhalts und anderer Elemente, die auf dem Dateifreigabeserver gespeichert sind.  |
|Front-End-Server  |Skype for Business Server-bandbreitenrichtliniendienst  |448  |TCP  |Wird für die Anrufsteuerung im Skype for Business Server-bandbreitenrichtliniendienst verwendet.  |
|Front-End-Server, auf denen sich der zentrale Verwaltungsspeicher befindet  | Skype for Business Server-Master-Replicator-Agent-Dienst |445  |TCP  |Wird verwendet, um Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit Skype for Business Server zu übertragen.  |
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL-Browser für lokale replizierte Kopie von Daten des zentralen Verwaltungsspeichers in einer lokalen SQL Server-Instanz  |
|Alle internen Server  |Verschiedene  |49152-57500  |TCP/UDP  |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für den Skype for Business Server-Konferenz Aufsichtsdienst, Skype for Business Server-Konferenzankündigungsdienst und Skype for Business Server-Audio/Video Konferenzdienst) und Vermittlungs Server.  |
|Office Web Apps-Server  ||443  ||Wird von Skype for Business Server verwendet, um eine Verbindung mit Office Web Apps Server herzustellen.  |
|Directors  |Skype for Business Server-Front-End-Dienst  |5060  |TCP  |Wird optional für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.  |
|Directors  |Skype for Business Server-Front-End-Dienst  |444  |HTTPS  <br/> TCP  |Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus veröffentlichen Clientzertifikate (auf Front-End-Servern) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.  |
|Directors  |Skype for Business Server-webkompatibilitäts Dienst  |80  |TCP  |Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet. Im Normalbetrieb wird auf HTTPS-Datenverkehr mit Port 443 und Protokolltyp TCP umgeschaltet.  |
|Directors  |Skype for Business Server-webkompatibilitäts Dienst  |443  |HTTPS  |Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet.  |
|Directors  |Skype for Business Server-Front-End-Dienst  |5061  |TCP  |Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server-Vermittlungsdienst  |5070  |TCP (MTLS)  |Wird für SIP-Anforderungen von den Front-End-Servern verwendet.  |
|Front-End-Server für beständigen Chat  |SIP für beständigen Chat  |5041  |TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Windows Communication Foundation (WCF) für beständigen Chat  |881  |TCP (TLS) und TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Dateiübertragungsdienst für beständigen Chat  |443  |TCP (TLS)  ||
   
> [!NOTE]
> In einigen Szenarien mit Remoteanrufsteuerung ist eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage erforderlich. Auch wenn der TCP-Port 5060 von Skype for Business Server nicht mehr verwendet wird, erstellen Sie während der Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem Telefonanlage. Ausführliche Informationen finden Sie im **CsTrustedApplicationComputer** -Cmdlet in der Dokumentation zur Skype for Business Server-Verwaltungsshell.
  
Für Pools, in denen nur Hardwaregeräte zum Lastenausgleich (kein DNS-Lastenausgleich) verwendet werden, zeigen die folgenden Tabellen die Ports, die für die Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.
  
**Ports für Hardwaregeräte zum Lastenausgleich, wenn nur ein Hardwarelastenausgleich verwendet wird**

|Lastenausgleichssystem|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleichssystem  |5061  |TCP (TLS)  |
|Front-End-Server-Lastenausgleichssystem  |444  |HTTPS  |
|Front-End-Server-Lastenausgleichssystem  |135  |DCOM und Remoteprozeduraufruf (RPC)  |
|Front-End-Server-Lastenausgleichssystem  |80  |HTTP  |
|Front-End-Server-Lastenausgleichssystem  |8080  |TCP-Client und Geräte Abruf des Stammzertifikats vom Front-End-Server – von NTLM authentifizierte Clients und Geräte  |
|Front-End-Server-Lastenausgleichssystem  |443  |HTTPS  |
|Front-End-Server-Lastenausgleichssystem  |4443  |HTTPS (vom Reverseproxy)  |
|Front-End-Server-Lastenausgleichssystem  |5072  |TCP  |
|Front-End-Server-Lastenausgleichssystem  |5073  |TCP  |
|Front-End-Server-Lastenausgleichssystem  |5075  |TCP  |
|Front-End-Server-Lastenausgleichssystem  |5076  |TCP  |
|Front-End-Server-Lastenausgleichssystem  |5071  |TCP  |
|Front-End-Server-Lastenausgleichssystem  |5080  |TCP  |
|Front-End-Server-Lastenausgleichssystem  |448  |TCP  |
|Vermittlungsserver-Lastenausgleichssystem  |5070  |TCP  |
|Front-End-Server-Lastenausgleichssystem (wenn im Pool auch ein Vermittlungsserver ausgeführt wird)  |5070  |TCP  |
|Director-Lastenausgleichssystem  |443  |HTTPS  |
|Director-Lastenausgleichssystem  |444  |HTTPS  |
|Director-Lastenausgleichssystem  |5061  |TCP  |
|Director-Lastenausgleichssystem  |4443  |HTTPS (vom Reverseproxy)  |
   
Für die Front-End- und Director-Pools, die DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle werden die Ports aufgeführt, die auf diesen Hardwaregeräten geöffnet sein müssen.
  
**Ports für Hardwaregeräte zum Lastenausgleich, wenn DNS-Lastenausgleich verwendet wird**

|Lastenausgleichssystem|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleichssystem  |80  |HTTP  |
|Front-End-Server-Lastenausgleichssystem  |443  |HTTPS  |
|Front-End-Server-Lastenausgleichssystem  |8080  |TCP-Client und Geräte Abruf des Stammzertifikats vom Front-End-Server – von NTLM authentifizierte Clients und Geräte  |
|Front-End-Server-Lastenausgleichssystem  |4443  |HTTPS (vom Reverseproxy)  |
|Director-Lastenausgleichssystem  |443  |HTTPS  |
|Director-Lastenausgleichssystem  |4443  |HTTPS (vom Reverseproxy)  |

**Erforderliche Clientports**

|Komponente|Port|Protokoll|Hinweise|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Wird von Skype for Business Server verwendet, um den FQDN der Registrierungsstelle zu finden (das heißt, wenn DNS SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).  |
|Clients  |443  |TCP (TLS)  |Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.  |
|Clients  |443  |TCP (PSOM/TLS)  |Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).  |
|Clients  |5061  |TCP (MTLS)  |Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.  |
|Clients  |6891-6901  |TCP  |Wird für die Dateiübertragung zwischen Skype for Business-Clients und vorherigen Clients verwendet.  |
|Clients  |1024-65535\*  |TCP/UDP  |Audioportbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535\*  |TCP/UDP  |Videoportbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535\*  |TCP  |Peer-zu-Peer-Dateiübertragungen (zur Übertragung von Konferenzdateien verwenden Clients PSOM-Verbindungen).  |
|Clients  |1024-65535\*  |TCP  |Anwendungsfreigabe.  |
|Aastra 6721ip (Telefon für öffentliche Bereiche)  <br/> Telefonapparat Aastra 6725ip  <br/> IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)  <br/> IP-Telefon HP 4120 (Telefonapparat)  <br/> IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)  <br/> IP-Telefonapparat Polycom CX600  <br/> IP-Telefonapparat Polycom CX700  <br/> IP-Konferenztelefon Polycom CX3000  |67/68  |DHCP  |Wird von den aufgelisteten Geräten verwendet, um das Skype for Business Server-Zertifikat, den FQDN der Bereitstellung und den FQDN der Registrierungsstelle zu finden.  |
   
\*Wenn Sie bestimmte Ports für diese Medientypen konfigurieren möchten, verwenden Sie das CsConferencingConfiguration-Cmdlet (ClientMediaPortRangeEnabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).
  
> [!NOTE]
> Die Setupprogramme für Skype for Business-Clients erstellen automatisch die erforderlichen Firewall-Ausnahmen für das Betriebssystem auf dem Clientcomputer. 

> [!NOTE]
> Die Ports, die für den Zugriff durch externe Benutzer verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (beispielsweise externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden). 
  
## <a name="ipsec-exceptions"></a>IPSec-Ausnahmen

Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.
  
In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert. 
  
**Empfohlene IPsec-Ausnahmen**

|Regelname|Quell-IP|Ziel-IP|Protokoll|Quellport|Zielport|Authentifizierungsanforderung|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V-Edgeserver, intern eingehend  |Beliebig  |A/V-Edgeserver, intern  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, extern eingehend  |Beliebig  |A/V-Edgeserver, extern  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, intern ausgehend  |A/V-Edgeserver, intern  |Beliebig  |UDP &amp; -TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, extern ausgehend  |A/V-Edgeserver, extern  |Beliebig  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Vermittlungsserver, eingehend  |Beliebig  |Vermittlungs-  <br/> server  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Vermittlungsserver, ausgehend  |Vermittlungs-  <br/> server  |Beliebig  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Konferenzzentrale, eingehend  |Beliebig  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Konferenzzentrale (ausgehend)  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Beliebig  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|A/V-Konferenzserver, eingehend  |Beliebig  |Front-End-Server  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|A/V-Konferenzen, ausgehend  |Front-End-Server  |Beliebig  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Exchange, eingehend  |Beliebig  |Exchange Unified Messaging  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, eingehend  |Beliebig  |Anwendungsfreigabeserver  |TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, ausgehend  |Anwendungsfreigabeserver  |Beliebig  |TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Exchange, ausgehend  |Exchange Unified Messaging  |Beliebig  |UDP und TCP  |Beliebig   |Beliebig  |Nicht authentifizieren  |
|Clients  |Beliebig   |Beliebig  |UDP  |Angegebener Medienportbereich  |Beliebig  |Nicht authentifizieren  |

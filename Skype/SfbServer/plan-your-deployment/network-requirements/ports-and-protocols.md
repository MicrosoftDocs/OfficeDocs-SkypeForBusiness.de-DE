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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Zusammenfassung: Überlegungen zur Portverwendung vor der Implementierung von Skype for Business Server.'
ms.openlocfilehash: 33199855d020af08e306022be47a0a9757125adb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025786"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Port-und Protokollanforderungen für Server
 
**Zusammenfassung:** Überprüfen Sie die Port Verwendungs Überlegungen vor der Implementierung von Skype for Business Server.
  
Skype for Business Server erfordert, dass bestimmte Ports in der externen und internen Firewall geöffnet sind. Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden. 
  
Dies kann zwar zunächst ein wenig entmutigend erscheinen, die Planung kann jedoch mit dem [Skype for Business Server 2015 Planungs Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725)stark angehoben werden. Nachdem Sie die Fragen des Assistenten zu den Funktionen, die Sie verwenden möchten, durchlaufen haben, können Sie für jeden Standort, den Sie definieren, den firewallbericht im Edge-Administrator Bericht anzeigen und die dort aufgelisteten Informationen verwenden, um yourfirewall-Regeln zu erstellen. Sie können auch viele der verwendeten Namen und IP-Adressen anpassen, ausführliche Informationen finden Sie unter [Überprüfen des Firewall-Berichts](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Denken Sie daran, dass Sie den Edge-Verwaltungsbericht in ein Excel-Arbeitsblatt exportieren können, und der firewallbericht ist eines der Arbeitsblätter in der Datei. 
  
Sie können die Informationen in diesen Tabellen auch in Diagrammform finden, indem Sie das Poster mit den Protokoll Arbeitslasten, das aus den [technischen Diagrammen für Skype for Business Server 2015](../../technical-diagrams.md) Artikel verknüpft ist, überprüfen.
> [!NOTE]
> - Wenn Sie Skype for Business Online implementieren (O365), lesen Sie [Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Hybrid Umgebungen müssen auf dieses Thema verweisen und auch die [Hybrid Konnektivität planen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Sie können Hardware-oder Softwarefirewalls haben, wir benötigen keine bestimmten Modelle oder Versionen. Worauf es ankommt, ist, welche Ports in der Whitelist sind, damit die Firewall die Funktion von Skype for Business Server nicht beeinträchtigt.
  
## <a name="port-and-protocol-details"></a>Port-und Protokoll Details

In diesem Abschnitt werden die von Servern, Lastenausgleichssystemen und Clients in einer Skype for Business Server-Bereitstellung verwendeten Ports und Protokolle zusammengefasst.
  
> [!NOTE]
> Wenn Skype for Business Server gestartet wird, werden die erforderlichen Ports in der Windows-Firewall geöffnet. Die Windows-Firewall sollte in den meisten normalen Anwendungen bereits vorhanden sein, wenn Sie jedoch nicht verwendet wird, funktioniert Skype for Business Server ohne Sie. 
  
Ausführliche Informationen zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [Edgeserver Szenarien in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
In der folgenden Tabelle sind die Ports aufgeführt, die für jede interne Serverrolle geöffnet sein müssen. 
  
**Erforderliche Serverports (nach Server Rolle)**

|Serverrolle|Dienstname|Port|Protokoll|Hinweise|
|:-----|:-----|:-----|:-----|:-----|
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL-Browser für die lokale replizierte Kopie der zentraler Verwaltungsspeicher Datenbank.  |
|Front-End-Server  |Skype for Business Server Front-End-Dienst  |5060  |TCP  |Optional von Standard Edition-Servern und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.  |
|Front-End-Server  |Skype for Business Server Front-End-Dienst  |5061  | TCP (TLS) |Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End-Servern und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit einem Monitoring Server verwendet.  |
| Front-End-Server |Skype for Business Server Front-End-Dienst  |444  | HTTPS <br/> TCP  |Wird für die HTTPS-Kommunikation zwischen dem Fokus (der Skype for Business Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.  <br/> Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.  |
|Front-End-Server  |Skype for Business Server Front-End-Dienst  |135  |DCOM und Remoteprozeduraufruf (RPC)  |Wird für DCOM-basierte Vorgänge wie das Verschieben von Benutzern, die Benutzer Replikationssynchronisierung und die Adressbuchsynchronisierung verwendet.  |
|Front-End-Server  |Skype for Business Server Sofortnachrichten-Konferenzdienst  |5062  |TCP  |Wird für eingehende SIP-Anforderungen für Chat Konferenzen (Instant Messaging) verwendet.  |
|Front-End-Server  |Skype for Business Server Webkonferenzdienst  |8057  |TCP (TLS)  |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  |
|Front-End-Server  |Skype for Business Server Webkonferenz-Kompatibilitätsdienst  |8058  |TCP (TLS)  |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) aus dem Live Meeting-Client und früheren Versionen von Skype for Business Server verwendet.  |
|Front-End-Server  |Skype for Business Server Audio/Video-Konferenzdienst  |5063  |TCP  |Wird für eingehende SIP-Anforderungen für Audio/Video-Konferenzen (A/V) verwendet.  |
|Front-End-Server  |Skype for Business Server Audio/Video-Konferenzdienst  |57501-65535  |TCP/UDP  |Für Videokonferenzen verwendeter Medienportbereich.  |
|Front-End-Server  |Skype for Business Server-webkompatibilitäts Dienst  |80  |HTTP  |Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten verwendete URLs) verwendet, wenn kein HTTPS verwendet wird.  |
|Front-End-Server  |Skype for Business Server-webkompatibilitäts Dienst  |443  |HTTPS  |Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.  |
|Front-End-Server  |Skype for Business Server-webkompatibilitäts Dienst  |8080  |TCP und http  |Wird von Webkomponenten für den externen Zugriff verwendet.  |
|Front-End-Server  |Webserverkomponente  |4443  |HTTPS  |HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Pools für die Auto Ermittlungs Anmeldung.  |
|Front-End-Server  |Webserverkomponente  |8060  |TCP (MTLS)  ||
|Front-End-Server  |Webserverkomponente  |8061  |TCP (MTLS)  ||
|Front-End-Server  |Komponente "Mobility Services"  |5086  |TCP (MTLS)  |SIP-Port für interne Prozesse der Mobilitätsdienste  |
|Front-End-Server  |Komponente "Mobility Services"  |5087  |TCP (MTLS)  |SIP-Port für interne Prozesse der Mobilitätsdienste  |
|Front-End-Server  |Komponente "Mobility Services"  |443  |HTTPS  ||
|Front-End-Server  |Skype for Business Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)  |5064  |TCP  |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  |
|Front-End-Server  |Skype for Business Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)  |5072  |TCP  |Wird für eingehende SIP-Anforderungen für Attendant (Einwahlkonferenzen) verwendet.  |
|Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5081  |TCP  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5082  |TCP (TLS)  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server  |Skype for Business Server Anwendungsfreigabe Dienst  |5065  |TCP  |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  |
|Front-End-Server  |Skype for Business Server Anwendungsfreigabe Dienst  |49152-65535  |TCP  |Für die Anwendungsfreigabe verwendete Medienportbereich.  |
|Front-End-Server  |Skype for Business Server Konferenz Ansagedienst  |5073  |TCP  |Wird für eingehende SIP-Anforderungen für den Skype for Business Server Konferenzankündigungsdienst (für Einwahlkonferenzen) verwendet.  |
|Front-End-Server  |Skype for Business Server Dienst zum Parken von Anrufen  |5075  |TCP  |Wird für eingehende SIP-Anforderungen für den Anwendung zum Parken von Anrufen verwendet.  |
|Front-End-Server  |Skype for Business Server Audio-Test Dienst  |5076  |TCP  |Wird für eingehende SIP-Anforderungen für den Audio-Test Dienst verwendet.  |
|Front-End-Server  |Nicht zutreffend  |5066  |TCP  |Wird für das ausgehende Enhanced 9-1-1 (E9-1-1)-Gateway verwendet.  |
|Front-End-Server  |Skype for Business Server Reaktionsgruppendienst  |5071  |TCP  |Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server Reaktionsgruppendienst  |8404  |TCP (MTLS)  |Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server bandbreitenrichtliniendienst  |5080  |TCP  |Wird für die Anrufsteuerung durch den bandbreitenrichtliniendienst für A/V-Edge-Umdrehungs Datenverkehr verwendet.  |
|Front-End-Server  |Zugriff auf Skype for Business Server Dateifreigabe Server  |445   |SMB/TCP  | Dient zum Abrufen von Adressbuch, Besprechungsinhalt und anderen Elementen, die auf dem Dateifreigabeserver gespeichert sind.  |
|Front-End-Server  |Skype for Business Server bandbreitenrichtliniendienst  |448  |TCP  |Wird für die Anrufsteuerung vom Skype for Business Server bandbreitenrichtliniendienst verwendet.  |
|Front-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet  | Skype for Business Server des Master Replicator-Agent-Diensts |445  |TCP  |Wird zum Pushen von Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit Skype for Business Server verwendet.  |
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL-Browser für lokale replizierte Kopie der Daten des zentralen Verwaltungsspeichers in der lokalen SQL Server Instanz  |
|Alle internen Server  |Verschiedene  |49152-57500  |TCP/UDP  |Medienportbereich, der für Audiokonferenzen auf allen internen Servern verwendet wird. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für Skype for Business Server Konferenz Aufsichtsdienst, Skype for Business Server Konferenzankündigungsdienst und Skype for Business Server Audio/Video-Konferenzdienst) und Vermittlungsserver.  |
|Office-webapps-Server  ||443  ||Wird von Skype for Business Server verwendet, um eine Verbindung mit Office-webapps Server herzustellen.  |
|Verwaltungsrat  |Skype for Business Server Front-End-Dienst  |5060  |TCP  |Optional für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.  |
|Verwaltungsrat  |Skype for Business Server Front-End-Dienst  |444  |HTTPS  <br/> TCP  |Kommunikation zwischen Servern zwischen Front-End und Director. Darüber hinaus veröffentlichen Clientzertifikate (an Front-End-Server) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.  |
|Verwaltungsrat  |Skype for Business Server-webkompatibilitäts Dienst  |80  |TCP  |Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet. Im normalen Betrieb wechselt zum HTTPS-Datenverkehr unter Verwendung von Port 443 und Protokolltyp TCP.  |
|Verwaltungsrat  |Skype for Business Server-webkompatibilitäts Dienst  |443  |HTTPS  |Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.  |
|Verwaltungsrat  |Skype for Business Server Front-End-Dienst  |5061  |TCP  |Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5070  |TCP (MTLS)  |Wird für SIP-Anforderungen von den Front-End-Servern verwendet.  |
|Front-End-Server für beständigen Chat  |SIP für beständigen Chat  |5041  |TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Windows Communication Foundation (WCF) für beständigen Chat  |881  |TCP (TLS) und TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Dateiübertragungsdienst für beständigen Chat  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Einige Szenarien für die Remoteanrufsteuerung erfordern eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage. Obwohl Skype for Business Server TCP-Port 5060 nicht mehr verwendet, erstellen Sie während der Bereitstellung von Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem PBX-System. Ausführliche Informationen finden Sie unter dem **CsTrustedApplicationComputer** -Cmdlet in der Dokumentation zur Skype for Business Server-Verwaltungskonsole.
  
Für Ihre Pools, in denen nur Hardwarelastenausgleich (nicht DNS-Lastenausgleich) verwendet wird, werden in der folgenden Tabelle die Ports aufgeführt, die zum Öffnen der Hardwarelastenausgleichs-Geräte erforderlich sind.
  
**Hardware Lastenausgleichs-Ports bei Verwendung von nur Hardwarelastenausgleich**

|Lastenausgleichsmodul|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server Lastenausgleich  |5061  |TCP (TLS)  |
|Front-End-Server Lastenausgleich  |444  |HTTPS  |
|Front-End-Server Lastenausgleich  |135  |DCOM und Remoteprozeduraufruf (RPC)  |
|Front-End-Server Lastenausgleich  |80  |HTTP  |
|Front-End-Server Lastenausgleich  |8080  |TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server-Clients und von NTLM authentifizierten Geräten  |
|Front-End-Server Lastenausgleich  |443  |HTTPS  |
|Front-End-Server Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
|Front-End-Server Lastenausgleich  |5072  |TCP  |
|Front-End-Server Lastenausgleich  |5073  |TCP  |
|Front-End-Server Lastenausgleich  |5075  |TCP  |
|Front-End-Server Lastenausgleich  |5076  |TCP  |
|Front-End-Server Lastenausgleich  |5071  |TCP  |
|Front-End-Server Lastenausgleich  |5080  |TCP  |
|Front-End-Server Lastenausgleich  |448  |TCP  |
|Vermittlungsserver Lastenausgleich  |5070  |TCP  |
|Front-End-Server Lastenausgleich (wenn der Pool auch Vermittlungsserver ausgeführt wird)  |5070  |TCP  |
|Director-Lastenausgleich  |443  |HTTPS  |
|Director-Lastenausgleich  |444  |HTTPS  |
|Director-Lastenausgleich  |5061  |TCP  |
|Director-Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
   
Für die Front-End-Pools und Director-Pools, die den DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle sind die Ports aufgeführt, die für diese Hardwarelastenausgleichs-Geräte geöffnet sein müssen.
  
**Hardware Lastenausgleichs-Ports bei Verwendung des DNS-Lastenausgleichs**

|Lastenausgleichsmodul|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server Lastenausgleich  |80  |HTTP  |
|Front-End-Server Lastenausgleich  |443  |HTTPS  |
|Front-End-Server Lastenausgleich  |8080  |TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server-Clients und von NTLM authentifizierten Geräten  |
|Front-End-Server Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
|Director-Lastenausgleich  |443  |HTTPS  |
|Director-Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |

**Erforderliche Client-Ports**

|Komponente|Port|Protokoll|Hinweise|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Wird von Skype for Business Server verwendet, um den FQDN des Registrars zu finden (wenn DNS-SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).  |
|Clients  |443  |TCP (TLS)  |Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.  |
|Clients  |443  |TCP (PSOM/TLS)  |Wird für den Zugriff durch externe Benutzer auf Webkonferenz Sitzungen verwendet.  |
|Clients  |443  |TCP (Stun/MSTURN)  |Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (TCP) verwendet.  |
|Clients  |3478  |UDP (Stun/MSTURN)  |Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (UDP) verwendet.  |
|Clients  |5061  |TCP (MTLS)  |Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.  |
|Clients  |6891-6901  |TCP  |Wird für die Dateiübertragung zwischen Skype for Business-Clients und vorherigen Clients verwendet.  |
|Clients  |1024-65535\*  |TCP/UDP  |Audioport Bereich (mindestens 20 Ports erforderlich)  |
|Clients  |1024-65535\*  |TCP/UDP  |Video Portbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535\*  |TCP  |Peer-zu-Peer-Dateiübertragung (für die Übertragung von Konferenz Dateien verwenden Clients PSOM).  |
|Clients  |1024-65535\*  |TCP  |Anwendungsfreigabe.  |
|Aastra 6721ip (Telefon für öffentliche Bereiche)  <br/> Telefonapparat Aastra 6725ip  <br/> IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)  <br/> IP-Telefon HP 4120 (Telefonapparat)  <br/> IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)  <br/> IP-Telefonapparat Polycom CX600  <br/> Polycom CX700-IP-Tischtelefon  <br/> IP-Konferenztelefon
Polycom CX3000  |67/68  |DHCP  |Wird von den aufgelisteten Geräten verwendet, um das Skype for Business Server Zertifikat, den FQDN der Feststellung und den FQDN der Registrierung zu finden.  |
   
\*Verwenden Sie zum Konfigurieren bestimmter Ports für diese Medientypen das CsConferencingConfiguration-Cmdlet (Parameter clientmediaportrangeenabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).
  
> [!NOTE]
> Die Setupprogramme für Skype for Business Clients erstellen automatisch die erforderlichen Firewall-Ausnahmen für das Betriebssystem auf dem Clientcomputer. 

> [!NOTE]
> Die Ports, die für den Zugriff durch externe Benutzer verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (beispielsweise externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden). 
  
## <a name="ipsec-exceptions"></a>IPsec-Ausnahmen

Für Enterprise-Netzwerke, in denen IPSec (Internet Protocol Security) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec über den Portbereich deaktiviert werden, der für die Zustellung von Audio-, Video-und Panorama Video verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.
  
In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert. 
  
**Empfohlene IPsec-Ausnahmen**

|Regelname|Quell-IP|Ziel-IP|Protokoll|Quellport|Zielport|Authentifizierungsanforderung|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V-Edgeserver, intern eingehend  |Any  |A/V-Edgeserver, intern  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Edgeserver, extern eingehend  |Any  |A/V-Edgeserver, extern  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Edgeserver, intern ausgehend  |A/V-Edgeserver, intern  |Any  |UDP &amp; -TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Edgeserver, extern ausgehend  |A/V-Edgeserver, extern  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Vermittlungsserver, eingehend  |Any  |Vermittlungs  <br/> Server (s)  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Vermittlungsserver, ausgehend  |Vermittlungs  <br/> Server (s)  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Konferenzzentrale, eingehend  |Any  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Konferenzzentrale (ausgehend)  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Konferenzserver, eingehend  |Any  |Front-End-Server  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|A/V-Konferenzen, ausgehend  |Front-End-Server  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Exchange, eingehend  |Any  |Exchange Unified Messaging  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, eingehend  |Any  |Anwendungsfreigabeserver  |TCP  |Any  |Any  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, ausgehend  |Anwendungsfreigabeserver  |Any  |TCP  |Any  |Any  |Nicht authentifizieren  |
|Exchange, ausgehend  |Exchange Unified Messaging  |Any  |UDP und TCP  |Any  |Any  |Nicht authentifizieren  |
|Clients  |Any  |Any  |UDP  |Angegebener Medienportbereich  |Any  |Nicht authentifizieren  |

---
title: Ports und Protokolle-Anforderungen für Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Zusammenfassung: Überprüfen der Aspekte beim Port-Nutzung vor der Implementierung von Skype für Business Server.'
ms.openlocfilehash: 6587bcfa9721362067d70bfc2e15549fa2a8e326
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293861"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Ports und Protokolle-Anforderungen für Server
 
**Zusammenfassung:** Überprüfen der Aspekte beim Port-Nutzung vor der Implementierung von Skype für Business Server.
  
Skype für Business Server erfordert, dass bestimmte Ports der externen und internen Firewall geöffnet sein. Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden. 
  
Dies mag ein Bit schwierige zunächst, den schwierigsten für die Planung, dies ist möglich, der [Skype für Business Server 2015 Planungstool](https://go.microsoft.com/fwlink/p/?LinkID=282725)verwenden. Nachdem Sie den Assistenten Fragen zu welche Features, den, die Sie verwenden möchten durchlaufen haben, für jeden Standort, den Sie definieren können Sie zum Anzeigen des Berichts Firewall innerhalb der Edgeverwaltungsbericht, und verwenden Sie die Informationen aufgelistet sind, um Yourfirewall Regeln zu erstellen. Sie können auch viele mit den Namen und die IP-Adressen verwendet, ausführliche [Überprüfung der Firewallbericht](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)finden Sie unter anpassen. Berücksichtigende Denken Sie können Exportieren der Edgeverwaltungsbericht in einer Excel-Kalkulationstabelle, und der Firewallbericht werden eines der Arbeitsblätter in der Datei. 
  
Sie können auch die Informationen in diesen Tabellen in Diagrammform mithilfe Protokollarbeitsauslastungen Poster von Artikel [Technical Diagrams für Skype für Business Server 2015](../../technical-diagrams.md) verknüpft suchen.
> [!NOTE]
> - Wenn Sie Skype für Business Online (O365) implementieren finden Sie in [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Hybridumgebungen müssen in diesem Thema und auch die [Ports und Protokolle Anforderungen](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#port-and-protocol-requirements)Hybrid verweisen.
> - Sie können Hardware- oder Firewalls, es ist nicht erforderlich, bestimmte Modelle oder Versionen. Wichtig ist, welche Ports weißen Liste enthalten sind, sodass die Firewall beeinträchtigt wird nicht das Funktionieren des Skype für Business Server.
  
## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

In diesem Abschnitt werden die Ports und Protokolle, die von Servern, lastenausgleichssystemen und Clients in einer Skype für Business Server-Bereitstellung verwendet.
  
> [!NOTE]
> Wenn Skype für Business Server gestartet wird, wird in der Windows-Firewall die erforderlichen Ports geöffnet. Windows-Firewall sollte bereits in die meisten normalen Clientanwendungen ausgeführt werden aber, wenn es nicht gerade verwendet Skype für Business Server ohne dienen soll. 
  
Ausführliche Informationen zur Firewallkonfiguration für edgekomponenten finden Sie unter [Edge-Server-Szenarien in Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
In der folgenden Tabelle werden alle Ports aufgeführt, die auf jeder internen Serverrolle geöffnet werden müssen. 
  
**Erforderliche Serverports (nach Serverrolle)**

|Serverrolle|Name des Diensts|Port|Protokoll|Hinweise|
|:-----|:-----|:-----|:-----|:-----|
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL-Browser für die lokal replizierte Kopie der Datenbank des zentralen Verwaltungsspeichers.  |
|Front-End-Server  |Skype für Business Server Front-End-Dienst  |5060  |TCP  |Wird optional von Standard Edition- und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.  |
|Front-End-Server  |Skype für Business Server Front-End-Dienst  |5061  | TCP (TLS) |Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End- und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit einem Monitoring Server verwendet.  |
| Front-End-Server |Skype für Business Server Front-End-Dienst  |444  | HTTPS <br/> TCP  |Wird für HTTPS-Kommunikation zwischen dem Konferenzzustandsobjekt (die Skype für Business Server-Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.  <br/> Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.  |
|Front-End-Server  |Skype für Business Server Front-End-Dienst  |135  |DCOM und Remoteprozeduraufruf (RPC)  |Wird für DCOM-basierte Vorgänge wie z. B. das Verschieben von Benutzern, die Synchronisierung des Benutzerreplikationsdiensts und die Synchronisierung von Adressbüchern verwendet.  |
|Front-End-Server  |Skype für Business Server Sofortnachrichten-Konferenzdienst  |5062  |TCP  |Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.  |
|Front-End-Server  |Skype für Business Server-Webkonferenzdienst  |8057  |TCP (TLS)  |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  |
|Front-End-Server  |Skype für Webkonferenzkompatibilität von Business Server-Dienst  |8058  |TCP (TLS)  |Wird zum Persistent Shared Object Model (PSOM) Verbindungen vom Live Meeting-Client und von früheren Versionen von Skype für Business Server verwendet.  |
|Front-End-Server  |Skype für Business Server a/v-Konferenzdienst  |5063  |TCP  |Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.  |
|Front-End-Server  |Skype für Business Server a/v-Konferenzdienst  |57501-65535  |TCP/UDP  |Für Videokonferenzen verwendeter Medienportbereich.  |
|Front-End-Server  |Skype für Business Server-webkompatibilitätsdienst  |80  |HTTP  |Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet, wenn kein HTTPS verwendet wird.  |
|Front-End-Server  |Skype für Business Server-webkompatibilitätsdienst  |443  |HTTPS  |Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet.  |
|Front-End-Server  |Skype für Business Server-webkompatibilitätsdienst  |8080  |TCP und HTTP  |Wird von Webkomponenten für den externen Zugriff verwendet.  |
|Front-End-Server  |Webserverkomponente  |4443  |HTTPS  |HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Servern für die AutoErmittlungsanmeldung.  |
|Front-End-Server  |Webserverkomponente  |8060  |TCP (MTLS)  ||
|Front-End-Server  |Webserverkomponente  |8061  |TCP (MTLS)  ||
|Front-End-Server  |Mobilitätsdienstekomponente  |5086  |TCP (MTLS)  |Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port  |
|Front-End-Server  |Mobilitätsdienstekomponente  |5087  |TCP (MTLS)  |Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port  |
|Front-End-Server  |Mobilitätsdienstekomponente  |443  |HTTPS  ||
|Front-End-Server  |Skype für Business Server-konferenzzentralendienst (einwahlkonferenzen)  |5064  |TCP  |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  |
|Front-End-Server  |Skype für Business Server-konferenzzentralendienst (einwahlkonferenzen)  |5072  |TCP  |Wird für eingehende SIP-Anforderungen für Attendant (einwahlkonferenzen) verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype für Business-Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype für Business-Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype für Business-Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype für Business-Vermittlungsdienst  |5081  |TCP  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype für Business-Vermittlungsdienst  |5082  |TCP (TLS)  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server  |Skype für Business Server-anwendungsfreigabedienst  |5065  |TCP  |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  |
|Front-End-Server  |Skype für Business Server-anwendungsfreigabedienst  |49152-65535  |TCP  |Für die Anwendungsfreigabe verwendeter Medienportbereich.  |
|Front-End-Server  |Skype für Business Server-konferenzankündigungsdienst  |5073  |TCP  |Wird für eingehende SIP-Anforderungen für die Skype für Business Server-konferenzankündigungsdienst verwendet (d. h., für einwahlkonferenzen).  |
|Front-End-Server  |Skype für Dienst zum Parken von Business Server  |5075  |TCP  |Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.  |
|Front-End-Server  |Skype für Business Server-audiotestdienst  |5076  |TCP  |Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.  |
|Front-End-Server  |Nicht zutreffend  |5066  |TCP  |Wird für das ausgehende E9-1-1-Gateway (9-1-1 [erweitert]) verwendet.  |
|Front-End-Server  |Skype für Business Server-reaktionsgruppendienst  |5071  |TCP  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype für Business Server-reaktionsgruppendienst  |8404  |TCP (MTLS)  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype für Business Server-Bandbreitenrichtliniendienst  |5080  |TCP  |Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für TURN-Datenverkehr vom A/V-Edgeserver verwendet.  |
|Front-End-Server  |Skype für Business-Dateifreigabe-Server-Zugriff  |445   |SMB/TCP  | Zum Abrufen der Adresse Adressbuch, Besprechungsinhalte und andere Elemente auf dem Server Dateifreigabe gespeichert.  |
|Front-End-Server  |Skype für Business Server-Bandbreitenrichtliniendienst  |448  |TCP  |Wird für die anrufsteuerung durch den Skype für Business Server-Bandbreitenrichtliniendienst verwendet.  |
|Front-End-Server, auf dem zentralen Verwaltungsspeicher befindet,  | Skype für Business Server Master-Replikations-Agent-Dienst |445  |TCP  |Wird zum Pushen von Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Servern mit Skype für Business Server verwendet.  |
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL-Browser für die lokal replizierte Kopie der zentralen speichern Daten in der lokalen SQL Server-Instanz  |
|Alle internen Server  |Verschiedene  |49152-57500  |TCP/UDP  |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Von allen Servern, die beendet Audio verwendet: Front-End-Servern (für Skype für Business Server-konferenzzentralendienst, Skype für Business Server-konferenzankündigungsdienst und Skype für Business Server a/v-Konferenzdienst), und Vermittlungsserver.  |
|Office Web Apps-Server  ||443  ||Verbindung mit Office Web Apps Server verwendet durch Skype für Business Server.  |
|Directors  |Skype für Business Server Front-End-Dienst  |5060  |TCP  |Wird optional für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.  |
|Directors  |Skype für Business Server Front-End-Dienst  |444  |HTTPS  <br/> TCP  |Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus Clientzertifikat veröffentlichen (auf Front-End-Servern) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.  |
|Directors  |Skype für Business Server-webkompatibilitätsdienst  |80  |TCP  |Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet. Im Normalbetrieb wird auf HTTPS-Datenverkehr mit Port 443 und Protokolltyp TCP umgeschaltet.  |
|Directors  |Skype für Business Server-webkompatibilitätsdienst  |443  |HTTPS  |Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet.  |
|Directors  |Skype für Business Server Front-End-Dienst  |5061  |TCP  |Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.  |
|Vermittlungsserver  |Skype für Business-Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.  |
|Vermittlungsserver  |Skype für Business-Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype für Business-Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype für Business-Vermittlungsdienst  |5070  |TCP (MTLS)  |Wird für SIP-Anforderungen von den Front-End-Servern verwendet.  |
|Front-End-Server für beständigen Chat  |SIP für beständigen Chat  |5041  |TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Windows Communication Foundation (WCF) für beständigen Chat  |881  |TCP (TLS) und TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Dateiübertragungsdienst für beständigen Chat  |443  |TCP (TLS)  ||
   
> [!NOTE]
> In einigen Szenarien mit Remoteanrufsteuerung ist eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage erforderlich. Obwohl Skype für Business Server TCP-Port 5060 nicht mehr verwendet wird, während der Bereitstellung der Remoteanrufsteuerung Sie erstellen eine vertrauenswürdige Serverkonfiguration, die RCC Zeile Server-FQDN den TCP-Port, die dem Front-End-Server oder dem Director zuordnet für die Verbindung verwenden die PBX-System. Weitere Informationen hierzu finden Sie unter **CsTrustedApplicationComputer** -Cmdlet in der Skype Business Server-Verwaltungsshell-Dokumentation.
  
Für Pools, in denen nur Hardwaregeräte zum Lastenausgleich (kein DNS-Lastenausgleich) verwendet werden, zeigen die folgenden Tabellen die Ports, die für die Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.
  
**Ports für Hardwaregeräte zum Lastenausgleich, wenn nur ein Hardwarelastenausgleich verwendet wird**

|Lastenausgleichssystem|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleichssystem  |5061  |TCP (TLS)  |
|Front-End-Server-Lastenausgleichssystem  |444  |HTTPS  |
|Front-End-Server-Lastenausgleichssystem  |135  |DCOM und Remoteprozeduraufruf (RPC)  |
|Front-End-Server-Lastenausgleichssystem  |80  |HTTP  |
|Front-End-Server-Lastenausgleichssystem  |8080  |TCP - Client- und Gerätefunktionen Abruf des Stammzertifikats vom Front-End-Server - Clients und Geräten, die NTLM-Authentifizierung  |
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
|Front-End-Server-Lastenausgleichssystem  |8080  |TCP - Client- und Gerätefunktionen Abruf des Stammzertifikats vom Front-End-Server - Clients und Geräten, die NTLM-Authentifizierung  |
|Front-End-Server-Lastenausgleichssystem  |4443  |HTTPS (vom Reverseproxy)  |
|Director-Lastenausgleichssystem  |443  |HTTPS  |
|Director-Lastenausgleichssystem  |4443  |HTTPS (vom Reverseproxy)  |

**Erforderliche Clientports**

|Komponente|Port|Protokoll|Hinweise|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Wird von Skype für Business Server, den FQDN der Registrierung erhalten (d. h., wenn DNS-SRV schlägt fehl und manuelle Einstellungen sind nicht konfiguriert) verwendet.  |
|Clients  |443  |TCP (TLS)  |Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.  |
|Clients  |443  |TCP (PSOM/TLS)  |Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).  |
|Clients  |5061  |TCP (MTLS)  |Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.  |
|Clients  |6891-6901  |TCP  |Für die Übertragung von Dateien zwischen Skype für Business-Clients und vorherigen Clientversionen verwendet.  |
|Clients  |1024-65535\*  |TCP/UDP  |Audioportbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535\*  |TCP/UDP  |Videoportbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535\*  |TCP  |Peer-zu-Peer-Dateiübertragungen (zur Übertragung von Konferenzdateien verwenden Clients PSOM-Verbindungen).  |
|Clients  |1024-65535\*  |TCP  |Anwendungsfreigabe.  |
|Aastra 6721ip (Telefon für öffentliche Bereiche)  <br/> Telefonapparat Aastra 6725ip  <br/> IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)  <br/> IP-Telefon HP 4120 (Telefonapparat)  <br/> IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)  <br/> IP-Telefonapparat Polycom CX600  <br/> IP-Telefonapparat Polycom CX700  <br/> IP-Konferenztelefon Polycom CX3000  |67/68  |DHCP  |Wird von den gelisteten Geräten zum Ermitteln von der Skype für Business Serverzertifikat, provisioning FQDN und Registrierungsstellen-FQDN verwendet.  |
   
\*Zum Konfigurieren spezieller Ports für diese Medientypen verwenden Sie das Cmdlet CsConferencingConfiguration (Parameter ClientMediaPortRangeEnabled, ClientMediaPort und ClientMediaPortRange-Parameter).
  
> [!NOTE]
> Das Setupprogramm für Skype für Business Clients erstellen automatisch die erforderlichen betriebssystemfirewall-Ausnahmen auf dem Clientcomputer. 

> [!NOTE]
> Die Ports, die für den Zugriff externer Benutzer verwendet werden, sind erforderlich für jedes Szenario, in dem der Client Firewall der Organisation (beispielsweise alle externen Kommunikation oder Besprechungen, die von anderen Organisationen gehostet) durchlaufen muss. 
  
## <a name="ipsec-exceptions"></a>IPSec-Ausnahmen

Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.
  
In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert. 
  
**Empfohlene IPsec-Ausnahmen**

|Regelname|Quell-IP|Ziel-IP|Protokoll|Quellport|Zielport|Authentifizierungsanforderung|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V-Edgeserver, intern eingehend  |Beliebig  |A/V-Edgeserver, intern  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, extern eingehend  |Beliebig  |A/V-Edgeserver, extern  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, intern ausgehend  |A/V-Edgeserver, intern  |Beliebig  |UDP &amp; TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, extern ausgehend  |A/V-Edgeserver, extern  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Vermittlungsserver, eingehend  |Beliebig  |Vermittlungs-  <br/> server  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Vermittlungsserver, ausgehend  |Vermittlungs-  <br/> server  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Konferenzzentrale, eingehend  |Beliebig  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Konferenzzentrale (ausgehend)  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Konferenzserver, eingehend  |Beliebig  |Front-End-Server  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Konferenzen, ausgehend  |Front-End-Server  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Exchange, eingehend  |Beliebig  |Exchange Unified Messaging  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, eingehend  |Beliebig  |Anwendungsfreigabeserver  |TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, ausgehend  |Anwendungsfreigabeserver  |Beliebig  |TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Exchange, ausgehend  |Exchange Unified Messaging  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Clients  |Beliebig  |Beliebig  |UDP  |Angegebener Medienportbereich  |Beliebig  |Nicht authentifizieren  |
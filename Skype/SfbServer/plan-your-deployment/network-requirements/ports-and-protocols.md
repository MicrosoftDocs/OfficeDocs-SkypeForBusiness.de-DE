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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Zusammenfassung: Überprüfen Sie die Überlegungen zur Portnutzung, bevor Sie Skype for Business Server implementieren.'
ms.openlocfilehash: 2ed181bd7bbcdce772e7db88a29e60d4f78e9fe2
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012989"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Port- und Protokollanforderungen für Server
 
**Zusammenfassung:** Überprüfen Sie die Überlegungen zur Portnutzung, bevor Sie Skype for Business Server implementieren.
  
Skype for Business Server erfordert, dass bestimmte Ports in den externen und internen Firewalls geöffnet sind. Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden. 
  
Obwohl dies etwas entmutigend erscheinen mag, kann dies mit dem Skype for Business Server 2015-Planungstool durchgeführt werden. Nachdem Sie die Fragen des Assistenten zu den Features, die Sie verwenden möchten, durchgegangen sind, können Sie für jede Website, die Sie definieren, den Firewallbericht im Edge-Administratorbericht anzeigen und die dort aufgeführten Informationen verwenden, um Ihre Firewallregeln zu erstellen. Sie können auch Anpassungen an vielen der verwendeten Namen und IP-Adressen vornehmen. Ausführliche Informationen finden Sie unter ["Überprüfen des Firewallberichts".](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report) Beachten Sie, dass Sie den Edgeadministratorbericht in eine Excel Tabelle exportieren können, und der Firewallbericht ist eines der Arbeitsblätter in der Datei. 
  
Die Informationen in diesen Tabellen finden Sie in Diagrammform, indem Sie das Poster "Protokollarbeitsauslastungen" überprüfen, das mit dem Artikel ["Technische Diagramme für Skype for Business Server 2015"](../../technical-diagrams.md) verknüpft ist.

> [!NOTE]
> - Wenn Sie Skype for Business Online implementieren (Microsoft 365 oder Office 365), beziehen Sie sich auf [Microsoft 365 und Office 365 URLs und IP-Adressbereiche.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US) Hybridumgebungen müssen auf dieses Thema verweisen und auch [die Hybridkonnektivität planen.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)
> - Sie können über eine Hardware- oder Softwarefirewall verfügen. Es sind keine bestimmten Modelle oder Versionen erforderlich. Entscheidend ist, welche Ports zu einer Zulassungsliste hinzugefügt werden, damit die Firewall die Funktion von Skype for Business Server nicht beeinträchtigt.
  
## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

In diesem Abschnitt werden die Ports und Protokolle zusammengefasst, die von Servern, Lastenausgleichsmodule und Clients in einer Skype for Business Server Bereitstellung verwendet werden.
  
> [!NOTE]
> Wenn Skype for Business Server gestartet wird, werden die erforderlichen Ports in der Windows Firewall geöffnet. Windows Firewall sollte bereits in den meisten normalen Anwendungen ausgeführt werden, aber wenn sie nicht verwendet wird, funktioniert Skype for Business Server ohne sie. 
  
Ausführliche Informationen zur Firewallkonfiguration für Edgekomponenten finden Sie [unter Edgeserverszenarien in Skype for Business Server 2015.](../../plan-your-deployment/edge-server-deployments/scenarios.md) 
  
In der folgenden Tabelle sind die Ports aufgeführt, die auf jeder internen Serverrolle geöffnet sein müssen. 
  
**Erforderliche Serverports (nach Serverrolle)**

|Serverrolle|Dienstname|Port|Protokoll|Anmerkungen|
|:-----|:-----|:-----|:-----|:-----|
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL Browser für die lokal replizierte Kopie der zentralen Verwaltungsdatenbank Store.  |
|Front-End Server  |Skype for Business Server Front-End Dienst  |5060  |TCP  |Wird optional von Standard Edition Servern und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie Remoteanrufsteuerungsservern verwendet.  |
|Front-End-Server  |Skype for Business Server Front-End Dienst  |5061  | TCP (TLS) |Wird von Standard Edition Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End-Servern und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit einem Monitoring Server verwendet.  |
| Front-End-Server |Skype for Business Server Front-End Dienst  |444  | HTTPS <br/> TCP  |Wird für die HTTPS-Kommunikation zwischen dem Fokus (der Skype for Business Server-Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.  <br/> Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.  |
|Front-End-Server  |Skype for Business Server Front-End Dienst  |135  |DCOM- und Remoteprozeduraufruf (RPC)  |Wird für DCOM-basierte Vorgänge wie Verschieben von Benutzern, Benutzerreplikationsdienstsynchronisierung und Adressbuchsynchronisierung verwendet.  |
|Front-End-Server  |Skype for Business Server Chatkonferenzdienst  |5062  |TCP  |Wird für eingehende SIP-Anforderungen für Chatkonferenzen verwendet.  |
|Front-End-Server  |Skype for Business Server Webkonferenzdienst  |8057  |TCP (TLS)  |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  |
|Front-End-Server  |Skype for Business Server Webkonferenzkompatibilitätsdienst  |8058  |TCP (TLS)  |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Live Meeting-Client und früheren Versionen von Skype for Business Server verwendet.  |
|Front-End-Server  |Skype for Business Server Audio-/Videokonferenzdienst  |5063  |TCP  |Wird für eingehende SIP-Anforderungen für Audio-/Videokonferenzen (A/V) verwendet.  |
|Front-End-Server  |Skype for Business Server Audio-/Videokonferenzdienst  |57501-65535  |TCP/UDP  |Für Videokonferenzen verwendeter Medienportbereich.  |
|Front-End-Server  |Skype for Business Server Webkompatibilitätsdienst  |80  |HTTP  |Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet, wenn HTTPS nicht verwendet wird.  |
|Front-End-Server  |Skype for Business Server Webkompatibilitätsdienst  |443  |HTTPS  |Wird für die Kommunikation von Front-End-Servern mit den Webfarm-FQDNs (den von IIS-Webkomponenten verwendeten URLs) verwendet.  |
|Front-End-Server  |Skype for Business Server Webkompatibilitätsdienst  |8080  |TCP und HTTP  |Wird von Webkomponenten für den externen Zugriff verwendet.  |
|Front-End-Server  |Webserverkomponente  |4443  |HTTPS  |HTTPS (von Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Pools für die AutoErmittlungsanmeldung.  |
|Front-End-Server  |Webserverkomponente  |8060  |TCP (MTLS)  ||
|Front-End-Server  |Webserverkomponente  |8061  |TCP (MTLS)  ||
|Front-End-Server  |Mobilitätsdienstekomponente  |5086  |TCP (MTLS)  |SIP-Port, der von internen Prozessen der Mobilitätsdienste verwendet wird  |
|Front-End-Server  |Mobilitätsdienstekomponente  |5087  |TCP (MTLS)  |SIP-Port, der von internen Prozessen der Mobilitätsdienste verwendet wird  |
|Front-End-Server  |Mobilitätsdienstekomponente  |443  |HTTPS  ||
|Front-End-Server  |Skype for Business Server Konferenzzentrale Dienst (Einwahlkonferenzen)  |5064  |TCP  |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  |
|Front-End-Server  |Skype for Business Server Konferenzzentrale Dienst (Einwahlkonferenzen)  |5072  |TCP  |Wird für eingehende SIP-Anforderungen für die Telefonzentrale (Einwahlkonferenzen) verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5081  |TCP  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  |Skype for Business Server Vermittlungsdienst  |5082  |TCP (TLS)  |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  |
|Front-End-Server  |Skype for Business Server Anwendungsfreigabedienst  |5065  |TCP  |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  |
|Front-End-Server  |Skype for Business Server Anwendungsfreigabedienst  |49152-65535  |TCP  |Für die Anwendungsfreigabe verwendeter Medienportbereich.  |
|Front-End-Server  |Skype for Business Server Konferenzankündigung Dienst  |5073  |TCP  |Wird für eingehende SIP-Anforderungen für den Skype for Business Server Konferenzankündigung Dienst (d. b. für Einwahlkonferenzen) verwendet.  |
|Front-End-Server  |Skype for Business Server Dienst zum Parken von Anrufen  |5075  |TCP  |Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.  |
|Front-End-Server  |Skype for Business Server Audiotestdienst  |5076  |TCP  |Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.  |
|Front-End-Server  |Nicht zutreffend  |5066  |TCP  |Wird für ausgehende erweiterte 9-1-1(E9-1-1)-Gateways verwendet.  |
|Front-End-Server  |Skype for Business Server Reaktionsgruppendienst  |5071  |TCP  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server Reaktionsgruppendienst  |8404  |TCP (MTLS)  |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  |
|Front-End-Server  |Skype for Business Server Bandbreitenrichtliniendienst  |5080  |TCP  |Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für A/V Edge TURN-Datenverkehr verwendet.  |
|Front-End-Server  |Skype for Business Server Dateifreigabeserverzugriff  |445   |SMB/TCP  | Wird zum Abrufen von Adressbuch, Besprechungsinhalten und anderen auf dem Dateifreigabeserver gespeicherten Elementen verwendet.  |
|Front-End-Server  |Skype for Business Server Bandbreitenrichtliniendienst  |448  |TCP  |Wird für die Anrufsteuerung durch den Skype for Business Server Bandbreitenrichtliniendienst verwendet.  |
|Front-End-Server, auf denen sich der zentrale Verwaltungsspeicher befindet  | Skype for Business Server Master Replicator Agent-Dienst |445  |TCP  |Wird verwendet, um Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server zu übertragen, auf denen Skype for Business Server ausgeführt wird.  |
|Alle Server  |SQL-Browser  |1434  |UDP  |SQL Browser für lokal replizierte Kopie der Daten des zentralen Verwaltungsspeichers in der lokalen SQL Server Instanz  |
|Alle internen Server  |Verschiedene  |49152-57500  |TCP/UDP  |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für Skype for Business Server Konferenzzentrale Dienst, Skype for Business Server Konferenzankündigung Dienst und Skype for Business Server Audio-/Videokonferenzdienst) und Vermittlungsserver.  |
|Office Web Apps-Server  ||443  ||Wird von Skype for Business Server zum Herstellen einer Verbindung mit Office Web Apps-Server verwendet.  |
|Directors  |Skype for Business Server Front-End Dienst  |5060  |TCP  |Wird optional für statische Routen zu vertrauenswürdigen Diensten wie Remoteanrufsteuerungsservern verwendet.  |
|Directors  |Skype for Business Server Front-End Dienst  |444  |HTTPS  <br/> TCP  |Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus veröffentlichen Clientzertifikate (auf Front-End-Servern) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.  |
|Directors  |Skype for Business Server Webkompatibilitätsdienst  |80  |TCP  |Wird für die anfängliche Kommunikation von Directors mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet. Wechselt im normalen Betrieb unter Verwendung von Port 443 und Protokolltyp TCP zu HTTPS-Datenverkehr.  |
|Directors  |Skype for Business Server Webkompatibilitätsdienst  |443  |HTTPS  |Wird für die Kommunikation von Directors mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.  |
|Directors  |Skype for Business Server Front-End Dienst  |5061  |TCP  |Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5070  |TCP  |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5067  |TCP (TLS)  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5068  |TCP  |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  |
|Vermittlungsserver  |Skype for Business Server Vermittlungsdienst  |5070  |TCP (MTLS)  |Wird für SIP-Anforderungen von den Front-End-Servern verwendet.  |
|Front-End-Server für beständigen Chat  |SIP für beständigen Chat  |5041  |TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Windows Communication Foundation (WCF) für beständigen Chat  |881  |TCP (TLS) und TCP (MTLS)  ||
|Front-End-Server für beständigen Chat  |Dateiübertragungsdienst für beständigen Chat  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Einige Remoteanrufsteuerungsszenarien erfordern eine TCP-Verbindung zwischen dem Front-End-Server oder Director und der Nebenstellenanlage. Obwohl Skype for Business Server tcp-Port 5060 nicht mehr verwendet, erstellen Sie während der Bereitstellung der Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Anschlussservers dem TCP-Port zuweist, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem Nebenstellensystem verwenden wird. Ausführliche Informationen finden Sie im Cmdlet **"CsTrustedApplicationComputer"** in der Dokumentation zur Skype for Business Server Verwaltungsshell.
  
Für Ihre Pools, die nur hardwarebasierten Lastenausgleich (nicht DNS-Lastenausgleich) verwenden, sind in der folgenden Tabelle die Ports aufgeführt, die die Hardwaregeräte zum Lastenausgleich öffnen müssen.
  
**Hardwarelastenausgleichs-Ports, wenn nur Hardwarelastenausgleich verwendet wird**

|Lastenausgleich|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Serverlastenausgleich  |5061  |TCP (TLS)  |
|Front-End-Serverlastenausgleich  |444  |HTTPS  |
|Front-End-Serverlastenausgleich  |135  |DCOM- und Remoteprozeduraufruf (Remote Procedure Call, RPC)  |
|Front-End-Serverlastenausgleich  |80  |HTTP  |
|Front-End-Serverlastenausgleich  |8080  |TCP – Client- und Geräteabruf des Stammzertifikats vom Front-End-Server – Clients und Geräte, die von NTLM authentifiziert werden  |
|Front-End-Serverlastenausgleich  |443  |HTTPS  |
|Front-End-Serverlastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
|Front-End-Serverlastenausgleich  |5072  |TCP  |
|Front-End-Serverlastenausgleich  |5073  |TCP  |
|Front-End-Serverlastenausgleich  |5075  |TCP  |
|Front-End-Serverlastenausgleich  |5076  |TCP  |
|Front-End-Serverlastenausgleich  |5071  |TCP  |
|Front-End-Serverlastenausgleich  |5080  |TCP  |
|Front-End-Serverlastenausgleich  |448  |TCP  |
|Vermittlungsserver-Lastenausgleich  |5070  |TCP  |
|Front-End-Serverlastenausgleich (wenn der Pool auch Vermittlungsserver ausführt)  |5070  |TCP  |
|Director-Lastenausgleich  |443  |HTTPS  |
|Director-Lastenausgleich  |444  |HTTPS  |
|Director-Lastenausgleich  |5061  |TCP  |
|Director-Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
   
Für Ihre Front-End-Pools und Directorpools, die den DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle sind die Ports aufgeführt, die für diese Hardwaregeräte zum Lastenausgleich geöffnet sein müssen.
  
**Hardwarelastenausgleichsports bei Verwendung des DNS-Lastenausgleichs**

|Lastenausgleich|Port|Protokoll|
|:-----|:-----|:-----|
|Front-End-Serverlastenausgleich  |80  |HTTP  |
|Front-End-Serverlastenausgleich  |443  |HTTPS  |
|Front-End-Serverlastenausgleich  |8080  |TCP – Client- und Geräteabruf des Stammzertifikats vom Front-End-Server – Clients und Geräte, die von NTLM authentifiziert werden  |
|Front-End-Serverlastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |
|Director-Lastenausgleich  |443  |HTTPS  |
|Director-Lastenausgleich  |4443  |HTTPS (vom Reverseproxy)  |

**Erforderliche Clientports**

|Komponente|Port|Protokoll|Anmerkungen|
|:-----|:-----|:-----|:-----|
|Clients  |67/68  |DHCP  |Wird von Skype for Business Server verwendet, um den Registrierungsstellen-FQDN zu finden (d. a. wenn DNS SRV fehlschlägt und keine manuellen Einstellungen konfiguriert sind).  |
|Clients  |443  |TCP (TLS)  |Wird für Client-zu-Server-SIP-Datenverkehr für externen Benutzerzugriff verwendet.  |
|Clients  |443  |TCP (PSOM/TLS)  |Wird für den Zugriff externer Benutzer auf Webkonferenzsitzungen verwendet.  |
|Clients  |443  |TCP (STUN/MSTURN)  |Wird für den Zugriff externer Benutzer auf A/V-Sitzungen und -Medien (TCP) verwendet.  |
|Clients  |3478  |UDP (STUN/MSTURN)  |Wird für den Zugriff externer Benutzer auf A/V-Sitzungen und Medien (UDP) verwendet.  |
|Clients  |5061  |TCP (MTLS)  |Wird für Client-zu-Server-SIP-Datenverkehr für externen Benutzerzugriff verwendet.  |
|Clients  |6891-6901  |TCP  |Wird für die Dateiübertragung zwischen Skype for Business-Clients und vorherigen Clients verwendet.  |
|Clients  |1024-65535 \*  |TCP/UDP  |Audioportbereich (mindestens 20 Ports erforderlich)  |
|Clients  |1024-65535 \*  |TCP/UDP  |Videoportbereich (mindestens 20 Ports erforderlich).  |
|Clients  |1024-65535 \*  |TCP  |Peer-to-Peer-Dateiübertragung (für die Konferenzdateiübertragung verwenden Clients PSOM).  |
|Clients  |1024-65535 \*  |TCP  |Anwendungsfreigabe.  |
|Aastra 6721ip (Telefon für öffentliche Bereiche)  <br/> Telefonapparat Aastra 6725ip  <br/> IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)  <br/> IP-Telefon HP 4120 (Telefonapparat)  <br/> IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)  <br/> IP-Telefonapparat Polycom CX600  <br/> Polycom CX700-IP-Tischtelefon  <br/> IP-Konferenztelefon
Polycom CX3000  |67/68  |DHCP  |Wird von den aufgeführten Geräten verwendet, um das Skype for Business Server-Zertifikat, den Bereitstellungs-FQDN und den Registrierungsstellen-FQDN zu finden.  |
   
\* Verwenden Sie zum Konfigurieren bestimmter Ports für diese Medientypen das Cmdlet "CsConferencingConfiguration" (Parameter "ClientMediaPortRangeEnabled", "ClientMediaPort" und "ClientMediaPortRange").
  
> [!NOTE]
> Die Setupprogramme für Skype for Business-Clients erstellen automatisch die erforderlichen Betriebssystemfirewall-Ausnahmen auf dem Clientcomputer. 

> [!NOTE]
> Die Ports, die für den externen Benutzerzugriff verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (z. B. externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden). 
  
## <a name="ipsec-exceptions"></a>IPsec-Ausnahmen

Für Unternehmensnetzwerke, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) bereitgestellt wurde (siehe IETF RFC 4301-4309), muss IPsec über den Bereich der Ports deaktiviert werden, die für die Bereitstellung von Audio-, Video- und Panoramavideos verwendet werden. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.
  
In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert. 
  
**Empfohlene IPsec-Ausnahmen**

|Regelname|Quell-IP|Ziel-IP|Protokoll|Quellport|Zielport|Authentifizierungsanforderung|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V-Edgeserver, intern eingehend  |Beliebig  |A/V-Edgeserver, intern  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, extern eingehend  |Beliebig  |A/V-Edgeserver, extern  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, intern ausgehend  |A/V-Edgeserver, intern  |Beliebig  |UDP &amp; TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Edgeserver, extern ausgehend  |A/V-Edgeserver, extern  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Vermittlungsserver, eingehend  |Beliebig  |Mediation  <br/> Server  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Vermittlungsserver, ausgehend  |Mediation  <br/> Server  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Konferenzzentrale, eingehend  |Beliebig  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Konferenzzentrale (ausgehend)  |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Konferenzserver, eingehend  |Beliebig  |Front-End-Server  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|A/V-Konferenzen, ausgehend  |Front-End-Server  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Exchange, eingehend  |Beliebig  |Exchange Unified Messaging  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, eingehend  |Beliebig  |Anwendungsfreigabeserver  |TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Anwendungsfreigabeserver, ausgehend  |Anwendungsfreigabeserver  |Beliebig  |TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Exchange, ausgehend  |Exchange Unified Messaging  |Beliebig  |UDP und TCP  |Beliebig  |Beliebig  |Nicht authentifizieren  |
|Clients  |Beliebig  |Beliebig  |UDP  |Angegebener Medienportbereich  |Beliebig  |Nicht authentifizieren  |
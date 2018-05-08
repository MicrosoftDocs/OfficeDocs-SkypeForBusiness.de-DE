---
title: Ports und Protokolle-Anforderungen für Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Zusammenfassung: Überprüfen der Aspekte beim Port-Nutzung vor der Implementierung von Skype für Business Server 2015.'
ms.openlocfilehash: 4bf9b7f9f1d0d0b99a8add76c4f73d4adcebea16
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="port-and-protocol-requirements-for-servers"></a>Ports und Protokolle-Anforderungen für Server
 
**Zusammenfassung:** Überprüfen der Aspekte beim Port-Nutzung vor der Implementierung von Skype für Business Server 2015.
  
Skype für Business Server erfordert, dass bestimmte Ports der externen und internen Firewall geöffnet sein. Wenn IPsec (Internet Protocol Security) in Ihrer Organisation bereitgestellt wird, muss außerdem IPsec für den Portbereich, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird, deaktiviert werden. 
  
Dies mag ein Bit schwierige zunächst, den schwierigsten für die Planung, dies ist möglich, der [Skype für Business Server 2015 Planungstool](https://www.microsoft.com/en-us/download/details.aspx?id=50357)verwenden. Nachdem Sie den Assistenten Fragen zu welche Features, den, die Sie verwenden möchten durchlaufen haben, für jeden Standort, den Sie definieren können Sie zum Anzeigen des Berichts Firewall innerhalb der Edgeverwaltungsbericht, und verwenden Sie die Informationen aufgelistet sind, um Yourfirewall Regeln zu erstellen. Sie können auch viele mit den Namen und die IP-Adressen verwendet, ausführliche [Überprüfung der Firewallbericht](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)finden Sie unter anpassen. Berücksichtigende Denken Sie können Exportieren der Edgeverwaltungsbericht in einer Excel-Kalkulationstabelle, und der Firewallbericht werden eines der Arbeitsblätter in der Datei. 
  
Sie können auch die Informationen in diesen Tabellen in Diagrammform mithilfe Protokollarbeitsauslastungen Poster von Artikel [Technical Diagrams für Skype für Business Server 2015](../../technical-diagrams.md) verknüpft suchen.
  
## <a name="port-and-protocol-details"></a>Port- und Protokolldetails

In diesem Abschnitt werden die Ports und Protokolle, die von Servern, lastenausgleichssystemen und Clients in einer Skype für Business Server-Bereitstellung verwendet.
  
> [!NOTE]
> Wenn Skype für Business Server gestartet wird, wird in der Windows-Firewall die erforderlichen Ports geöffnet. Windows-Firewall sollte bereits in die meisten normalen Clientanwendungen ausgeführt werden aber, wenn es nicht gerade verwendet Skype für Business Server ohne dienen soll. 
  
Ausführliche Informationen zur Firewallkonfiguration für edgekomponenten finden Sie unter [Edge-Server-Szenarien in Skype für Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
In der folgenden Tabelle werden alle Ports aufgeführt, die auf jeder internen Serverrolle geöffnet werden müssen. 
  
**Erforderliche Serverports (nach Serverrolle)**

|**Serverrolle**|**Dienstname**|**Port**|**Protokoll**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Alle Server  <br/> |SQL-Browser  <br/> |1434  <br/> |UDP  <br/> |SQL-Browser für die lokal replizierte Kopie der Datenbank des zentralen Verwaltungsspeichers.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server Front-End-Dienst  <br/> |5060  <br/> |TCP  <br/> |Wird optional von Standard Edition- und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server Front-End-Dienst  <br/> |5061  <br/> | TCP (TLS) <br/> |Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End- und Vermittlungsservern (MTLS) verwendet. Wird auch für die Kommunikation mit einem Monitoring Server verwendet.  <br/> |
| Front-End-Server <br/> |Skype für Business Server Front-End-Dienst  <br/> |444  <br/> | HTTPS <br/> TCP  <br/> |Wird für HTTPS-Kommunikation zwischen dem Konferenzzustandsobjekt (die Skype für Business Server-Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.  <br/> Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server Front-End-Dienst  <br/> |135  <br/> |DCOM und Remoteprozeduraufruf (RPC)  <br/> |Wird für DCOM-basierte Vorgänge wie z. B. das Verschieben von Benutzern, die Synchronisierung des Benutzerreplikationsdiensts und die Synchronisierung von Adressbüchern verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server Sofortnachrichten-Konferenzdienst  <br/> |5062  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Instant Messaging-Konferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-Webkonferenzdienst  <br/> |8057  <br/> |TCP (TLS)  <br/> |Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Webkonferenzkompatibilität von Business Server-Dienst  <br/> |8058  <br/> |TCP (TLS)  <br/> |Wird zum Persistent Shared Object Model (PSOM) Verbindungen vom Live Meeting-Client und von früheren Versionen von Skype für Business Server verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server a/v-Konferenzdienst  <br/> |5063  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für A/V-Konferenzen (Audio/Video) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server a/v-Konferenzdienst  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Für Videokonferenzen verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-webkompatibilitätsdienst  <br/> |80  <br/> |HTTP  <br/> |Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet, wenn kein HTTPS verwendet wird.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-webkompatibilitätsdienst  <br/> |443  <br/> |HTTPS  <br/> |Wird für die Kommunikation von den Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten genutzte URLs) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-webkompatibilitätsdienst  <br/> |8080  <br/> |TCP und HTTP  <br/> |Wird von Webkomponenten für den externen Zugriff verwendet.  <br/> |
|Front-End-Server  <br/> |Webserverkomponente  <br/> |4443  <br/> |HTTPS  <br/> |HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Servern für die AutoErmittlungsanmeldung.  <br/> |
|Front-End-Server  <br/> |Webserverkomponente  <br/> |8060  <br/> |TCP (MTLS)  <br/> ||
|Front-End-Server  <br/> |Webserverkomponente  <br/> |8061  <br/> |TCP (MTLS)  <br/> ||
|Front-End-Server  <br/> |Mobilitätsdienstekomponente  <br/> |5086  <br/> |TCP (MTLS)  <br/> |Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port  <br/> |
|Front-End-Server  <br/> |Mobilitätsdienstekomponente  <br/> |5087  <br/> |TCP (MTLS)  <br/> |Der von internen Prozessen der Mobilitätsdienste verwendete SIP-Port  <br/> |
|Front-End-Server  <br/> |Mobilitätsdienstekomponente  <br/> |443  <br/> |HTTPS  <br/> ||
|Front-End-Server  <br/> |Skype für Business Server-konferenzzentralendienst (einwahlkonferenzen)  <br/> |5064  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-konferenzzentralendienst (einwahlkonferenzen)  <br/> |5072  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für Attendant (einwahlkonferenzen) verwendet.  <br/> |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5070  <br/> |TCP  <br/> |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server an den Vermittlungsserver verwendet.  <br/> |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5067  <br/> |TCP (TLS)  <br/> |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.  <br/> |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5068  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway an den Vermittlungsserver verwendet.  <br/> |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5081  <br/> |TCP  <br/> |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  <br/> |
|Front-End-Server, auf denen auch ein verbundener Vermittlungsserver ausgeführt wird  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5082  <br/> |TCP (TLS)  <br/> |Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-konferenzankündigungsdienst  <br/> |5073  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für die Skype für Business Server-konferenzankündigungsdienst verwendet (d. h., für einwahlkonferenzen).  <br/> |
|Front-End-Server  <br/> |Skype für Dienst zum Parken von Business Server  <br/> |5075  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für die Anwendung zum Parken von Anrufen verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-audiotestdienst  <br/> |5076  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für den Audiotestdienst verwendet.  <br/> |
|Front-End-Server  <br/> |Nicht zutreffend  <br/> |5066  <br/> |TCP  <br/> |Wird für das ausgehende E9-1-1-Gateway (9-1-1 [erweitert]) verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-reaktionsgruppendienst  <br/> |5071  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-reaktionsgruppendienst  <br/> |8404  <br/> |TCP (MTLS)  <br/> |Wird für eingehende SIP-Anforderungen für die Reaktionsgruppenanwendung verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-Bandbreitenrichtliniendienst  <br/> |5080  <br/> |TCP  <br/> |Wird für die Anrufsteuerung durch den Bandbreitenrichtliniendienst für TURN-Datenverkehr vom A/V-Edgeserver verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-Bandbreitenrichtliniendienst  <br/> |448  <br/> |TCP  <br/> |Wird für die anrufsteuerung durch den Skype für Business Server-Bandbreitenrichtliniendienst verwendet.  <br/> |
|Front-End-Server, auf dem zentralen Verwaltungsspeicher befindet,  <br/> | Skype für Business Server Master-Replikations-Agent-Dienst <br/> |445  <br/> |TCP  <br/> |Wird zum Pushen von Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Servern mit Skype für Business Server verwendet.  <br/> |
|Alle Server  <br/> |SQL-Browser  <br/> |1434  <br/> |UDP  <br/> |SQL-Browser für die lokal replizierte Kopie der zentralen speichern Daten in der lokalen SQL Server-Instanz  <br/> |
|Alle internen Server  <br/> |Verschiedene  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |Für Audiokonferenzen auf allen internen Servern verwendeter Medienportbereich. Von allen Servern, die beendet Audio verwendet: Front-End-Servern (für Skype für Business Server-konferenzzentralendienst, Skype für Business Server-konferenzankündigungsdienst und Skype für Business Server a/v-Konferenzdienst), und Vermittlungsserver.  <br/> |
|Office Web Apps-Server  <br/> ||443  <br/> ||Wird von Skype für Business Server 2015 Verbindung mit Office Web Apps Server verwendet.  <br/> |
|Directors  <br/> |Skype für Business Server Front-End-Dienst  <br/> |5060  <br/> |TCP  <br/> |Wird optional für statische Routen zu vertrauenswürdigen Diensten wie z. B. Servern für die Remoteanrufsteuerung verwendet.  <br/> |
|Directors  <br/> |Skype für Business Server Front-End-Dienst  <br/> |444  <br/> |HTTPS  <br/> TCP  <br/> |Serverübergreifende Kommunikation zwischen Front-End und Director. Darüber hinaus Clientzertifikat veröffentlichen (auf Front-End-Servern) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.  <br/> |
|Directors  <br/> |Skype für Business Server-webkompatibilitätsdienst  <br/> |80  <br/> |TCP  <br/> |Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet. Im Normalbetrieb wird auf HTTPS-Datenverkehr mit Port 443 und Protokolltyp TCP umgeschaltet.  <br/> |
|Directors  <br/> |Skype für Business Server-webkompatibilitätsdienst  <br/> |443  <br/> |HTTPS  <br/> |Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (den von den IIS-Webkomponenten genutzten URLs) verwendet.  <br/> |
|Directors  <br/> |Skype für Business Server Front-End-Dienst  <br/> |5061  <br/> |TCP  <br/> |Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.  <br/> |
|Vermittlungsserver  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5070  <br/> |TCP  <br/> |Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.  <br/> |
|Vermittlungsserver  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5067  <br/> |TCP (TLS)  <br/> |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  <br/> |
|Vermittlungsserver  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5068  <br/> |TCP  <br/> |Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.  <br/> |
|Vermittlungsserver  <br/> |Skype für Business-Vermittlungsdienst  <br/> |5070  <br/> |TCP (MTLS)  <br/> |Wird für SIP-Anforderungen von den Front-End-Servern verwendet.  <br/> |
|Front-End-Server für beständigen Chat  <br/> |SIP für beständigen Chat  <br/> |5041  <br/> |TCP (MTLS)  <br/> ||
|Front-End-Server für beständigen Chat  <br/> |Windows Communication Foundation (WCF) für beständigen Chat  <br/> |881  <br/> |TCP (TLS) und TCP (MTLS)  <br/> ||
|Front-End-Server für beständigen Chat  <br/> |Dateiübertragungsdienst für beständigen Chat  <br/> |443  <br/> |TCP (TLS)  <br/> ||
   
> [!NOTE]
> In einigen Szenarien mit Remoteanrufsteuerung ist eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage erforderlich. Obwohl Skype für Business Server TCP-Port 5060 nicht mehr verwendet wird, während der Bereitstellung der Remoteanrufsteuerung Sie erstellen eine vertrauenswürdige Serverkonfiguration, die RCC Zeile Server-FQDN den TCP-Port, die dem Front-End-Server oder dem Director zuordnet für die Verbindung verwenden die PBX-System. Weitere Informationen hierzu finden Sie unter **CsTrustedApplicationComputer** -Cmdlet in der Skype Business Server-Verwaltungsshell-Dokumentation.
  
Für Pools, in denen nur Hardwaregeräte zum Lastenausgleich (kein DNS-Lastenausgleich) verwendet werden, zeigen die folgenden Tabellen die Ports, die für die Hardwaregeräte zum Lastenausgleich geöffnet werden müssen.
  
**Hardware Ports zum Lastenausgleich bei Verwendung nur Hardwaregeräte zum Lastenausgleich**

|**System zum Lastenausgleich**|**Port**|**Protokoll**|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleichssystem  <br/> |5061  <br/> |TCP (TLS)  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |444  <br/> |HTTPS  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |135  <br/> |DCOM und Remoteprozeduraufruf (RPC)  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |80  <br/> |HTTP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |8080  <br/> |TCP - Client- und Gerätefunktionen Abruf des Stammzertifikats vom Front-End-Server - Clients und Geräten, die NTLM-Authentifizierung  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |443  <br/> |HTTPS  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |4443  <br/> |HTTPS (vom Reverseproxy)  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |5072  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |5073  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |5075  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |5076  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |5071  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |5080  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |448  <br/> |TCP  <br/> |
|Vermittlungsserver-Lastenausgleichssystem  <br/> |5070  <br/> |TCP  <br/> |
|Front-End-Server-Lastenausgleichssystem (wenn im Pool auch ein Vermittlungsserver ausgeführt wird)  <br/> |5070  <br/> |TCP  <br/> |
|Director-Lastenausgleichssystem  <br/> |443  <br/> |HTTPS  <br/> |
|Director-Lastenausgleichssystem  <br/> |444  <br/> |HTTPS  <br/> |
|Director-Lastenausgleichssystem  <br/> |5061  <br/> |TCP  <br/> |
|Director-Lastenausgleichssystem  <br/> |4443  <br/> |HTTPS (vom Reverseproxy)  <br/> |
   
Für die Front-End- und Director-Pools, die DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden. In der folgenden Tabelle werden die Ports aufgeführt, die auf diesen Hardwaregeräten geöffnet sein müssen.
  
**Hardware Ports zum Lastenausgleich bei Verwendung von DNS-Lastenausgleich**

|**System zum Lastenausgleich**|**Port**|**Protokoll**|
|:-----|:-----|:-----|
|Front-End-Server-Lastenausgleichssystem  <br/> |80  <br/> |HTTP  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |443  <br/> |HTTPS  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |8080  <br/> |TCP - Client- und Gerätefunktionen Abruf des Stammzertifikats vom Front-End-Server - Clients und Geräten, die NTLM-Authentifizierung  <br/> |
|Front-End-Server-Lastenausgleichssystem  <br/> |4443  <br/> |HTTPS (vom Reverseproxy)  <br/> |
|Director-Lastenausgleichssystem  <br/> |443  <br/> |HTTPS  <br/> |
|Director-Lastenausgleichssystem  <br/> |4443  <br/> |HTTPS (vom Reverseproxy)  <br/> |
   
**Erforderliche Clientports**

|**Komponente**|**Port**|**Protokoll**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |67/68  <br/> |DHCP  <br/> |Wird von Skype für Business Server, den FQDN der Registrierung erhalten (d. h., wenn DNS-SRV schlägt fehl und manuelle Einstellungen sind nicht konfiguriert) verwendet.  <br/> |
|Clients  <br/> |443  <br/> |TCP (TLS)  <br/> |Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.  <br/> |
|Clients  <br/> |443  <br/> |TCP (PSOM/TLS)  <br/> |Wird für externen Benutzerzugriff auf Webkonferenzsitzungen verwendet.  <br/> |
|Clients  <br/> |443  <br/> |TCP (STUN/MSTURN)  <br/> |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (TCP).  <br/> |
|Clients  <br/> |3478  <br/> |UDP (STUN/MSTURN)  <br/> |Wird für externen Benutzerzugriff auf A/V-Sitzungen und -Mediendaten verwendet (UDP).  <br/> |
|Clients  <br/> |5061  <br/> |TCP (MTLS)  <br/> |Wird bei externem Benutzerzugriff für SIP-Datenverkehr vom Client zum Server verwendet.  <br/> |
|Clients  <br/> |6891-6901  <br/> |TCP  <br/> |Für die Übertragung von Dateien zwischen Skype für Business-Clients und vorherigen Clientversionen verwendet.  <br/> |
|Clients  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Audioportbereich (mindestens 20 Ports erforderlich).  <br/> |
|Clients  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Videoportbereich (mindestens 20 Ports erforderlich).  <br/> |
|Clients  <br/> |1024-65535\*  <br/> |TCP  <br/> |Peer-zu-Peer-Dateiübertragungen (zur Übertragung von Konferenzdateien verwenden Clients PSOM-Verbindungen).  <br/> |
|Clients  <br/> |1024-65535\*  <br/> |TCP  <br/> |Anwendungsfreigabe.  <br/> |
|Aastra 6721ip (Telefon für öffentliche Bereiche)  <br/> Telefonapparat Aastra 6725ip  <br/> IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)  <br/> IP-Telefon HP 4120 (Telefonapparat)  <br/> IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)  <br/> IP-Telefonapparat Polycom CX600  <br/> IP-Telefonapparat Polycom CX700  <br/> IP-Konferenztelefon Polycom CX3000  <br/> |67/68  <br/> |DHCP  <br/> |Wird von den gelisteten Geräten zum Ermitteln von der Skype für Business Serverzertifikat, provisioning FQDN und Registrierungsstellen-FQDN verwendet.  <br/> |
   
\*Zum Konfigurieren spezieller Ports für diese Medientypen verwenden Sie das Cmdlet CsConferencingConfiguration (Parameter ClientMediaPortRangeEnabled, ClientMediaPort und ClientMediaPortRange-Parameter).
  
> [!NOTE]
> Das Setupprogramm für Skype für Business Clients erstellen automatisch die erforderlichen betriebssystemfirewall-Ausnahmen auf dem Clientcomputer. 
  
> [!NOTE]
> Die Ports, die für den Zugriff externer Benutzer verwendet werden, sind erforderlich für jedes Szenario, in dem der Client Firewall der Organisation (beispielsweise alle externen Kommunikation oder Besprechungen, die von anderen Organisationen gehostet) durchlaufen muss. 
  
## <a name="ipsec-exceptions"></a>IPSec-Ausnahmen

Bei Unternehmensnetzwerken, in denen Internetprotokollsicherheit (Internet Protocol Security, IPsec) (siehe IETF RFC 4301-4309) bereitgestellt wurde, muss IPsec für den Portbereich deaktiviert werden, der zur Übermittlung von Audio-, Video- und Panoramavideodaten verwendet wird. Mit dieser Empfehlung sollen Verzögerungen in der Zuweisung von Medienports vermieden werden, die sich aus dem IPsec-Aushandlungsvorgang ergeben könnten.
  
In der folgenden Tabelle werden die empfohlenen Einstellungen für IPsec-Ausnahmen erläutert. 
  
**Empfohlene IPsec-Ausnahmen**

|**Regelname**|**Quell-IP**|**Ziel-IP-**|**Protokoll**|**Quellport**|**Zielport**|**Authentifizierungsanforderung**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|A/V-Edgeserver, intern eingehend  <br/> |Beliebig  <br/> |A/V-Edgeserver, intern  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|A/V-Edgeserver, extern eingehend  <br/> |Beliebig  <br/> |A/V-Edgeserver, extern  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|A/V-Edgeserver, intern ausgehend  <br/> |A/V-Edgeserver, intern  <br/> |Beliebig  <br/> |UDP &amp; TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|A/V-Edgeserver, extern ausgehend  <br/> |A/V-Edgeserver, extern  <br/> |Beliebig  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Vermittlungsserver, eingehend  <br/> |Beliebig  <br/> |Vermittlungs-  <br/> server  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Vermittlungsserver, ausgehend  <br/> |Vermittlungs-  <br/> server  <br/> |Beliebig  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Konferenzzentrale, eingehend  <br/> |Beliebig  <br/> |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Konferenzzentrale (ausgehend)  <br/> |Front-End-Server, auf dem die Konferenzzentrale ausgeführt wird  <br/> |Beliebig  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|A/V-Konferenzserver, eingehend  <br/> |Beliebig  <br/> |Front-End-Server  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|A/V-Konferenzen, ausgehend  <br/> |Front-End-Server  <br/> |Beliebig  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Exchange, eingehend  <br/> |Beliebig  <br/> |Exchange Unified Messaging  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Anwendungsfreigabeserver, eingehend  <br/> |Beliebig  <br/> |Anwendungsfreigabeserver  <br/> |TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Anwendungsfreigabeserver, ausgehend  <br/> |Anwendungsfreigabeserver  <br/> |Beliebig  <br/> |TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Exchange, ausgehend  <br/> |Exchange Unified Messaging  <br/> |Beliebig  <br/> |UDP und TCP  <br/> |Beliebig  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
|Clients  <br/> |Beliebig  <br/> |Beliebig  <br/> |UDP  <br/> |Angegebener Medienportbereich  <br/> |Beliebig  <br/> |Nicht authentifizieren  <br/> |
   


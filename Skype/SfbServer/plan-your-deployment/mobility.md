---
title: Planen Sie für die Mobilität Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Plan für die Implementierung von Mobilität für Skype für Business Server.
ms.openlocfilehash: 6616560afbea5a2aed30fbf671035ae46d6ed8b7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878182"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planen Sie für die Mobilität Skype für Business Server
 
Plan für die Implementierung von Mobilität für Skype für Business Server.
  
Mit Skype für Business Server können Sie Skype für Business Server-Funktionen auf mobilen Geräten bereitstellen, um die Mobilitätsfeatures bereitstellen. In diesem Artikel finden Sie Informationen über die Mobilitätsfeatures und Unterstützung bei der Planung Ihrer bereitstellungs.
  
Das Mobilitätsfeature für Skype für Business Server kann zur Unterstützung von mobilen Clients für Skype für Unternehmen als auch Lync-Clients auf 2010 zurückgehen. Nachdem sie bereitgestellt wird, die Benutzer können verbinden mit Ihrer Skype für iOS-Business Server Bereitstellung verwenden unterstützten Android und Windows Phone Mobilgeräten verschiedene Features, einschließlich Enterprise-VoIP-Funktionen nutzen. Wir haben eine partielle unten aufgenommen, und Sie können ferner [Desktopclient Featurevergleich für Skype für Unternehmen](clients-and-devices/desktop-feature-comparison.md) für Weitere Informationen:
  
- Nachrichten senden und empfangen
    
- Anwesenheitsinformationen anzeigen
    
- Kontakte anzeigen
    
- Klicken, um an einer Konferenz teilzunehmen
    
- Geschäftlich anrufen
    
- Erreichbarkeit unter einer Nummer
    
- Voicemail
    
- Benachrichtigung über verpasste Anrufe
    
- Voice over IP (VoIP)
    
- Teilnehmervideo (H.264)
    
- Besprechungsinhalt anzeigen (PowerPoint und Desktop-/Anwendungsfreigabe)
    
Bei allen diesen Funktionen kommt die Unified Communications-Web-API (UCWA) zum Einsatz. UCWA wurde in Lync Server 2013 eingeführt, und es ist noch in Verwendung für Skype für Business Server. Es ist eine zusätzliche Funktionalität für die Kommunikation mit Lync 2010-Clients und Mobility Service ("MCX") ist. Dies sind kostenlosen Dienste, die für Lync Server 2010 und 2013-Clients sowie Skype für Business-Clients erfolgreich Skype für Business Server-Bereitstellungen Zugriff auf zulassen.
  
> [!NOTE]
> Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar. Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden. Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.
  
Es ist wichtig, beachten Sie, dass während alle diese Features zur Verfügung stehen, nachdem Mobilität implementiert wurde, sie ein wenig anders einige Geräte arbeiten können. Wir haben eine Website, die erläutert, welche Features auf welchen Geräten, unter [Mobile Client Featurevergleich für Skype für Unternehmen](clients-and-devices/mobile-feature-comparison.md)arbeiten. Wir haben auch einige hervorragende Gerät und Betriebssystem-Informationen unter [Planen von Clients und Geräten](clients-and-devices/clients-and-devices.md).
  
Mobilität nutzt die AutoErmittlung-Feature, das ermöglicht es Clients, die automatisch Skype für Webdienste Business Server ohne in alle URLs eingeben (sie werden nicht auch sie wissen müssen) müssen Benutzer suchen. Für die Problembehandlung wird die manuelle Eingabe von URLs nach wie vor unterstützt.
  
Pushbenachrichtigungen werden ebenfalls unterstützt, wenn nicht der Skype für Geschäfts-app im Hintergrund ausgeführt wird (oder für mobile Geräte, die nicht im Hintergrund ausgeführt Applications unterstützen). Mit einem mobilen Gerät über ein Ereignis, das auftritt, wenn das Gerät oder app nicht aktiv ist, wird eine Push-Benachrichtigung gesendet. Ein Beispiel für eine gute fehlt eine Sofortnachricht Wenn das Telefon des nicht aktiv ist, das führt zu einer Push-Benachrichtigung gesendet werden (Dies wird präsentiert als Toast oder Benachrichtigung, wie wenn die app im Hintergrund ausgeführt wird). Mit push-Benachrichtigungen, Benutzer wird nicht verpassen Sofortnachrichten oder VoIP-Anrufe.
  
Weitere Informationen haben wir in die folgenden Abschnitte unterteilt:
  
- [Mobilitätskomponenten](mobility.md#MobilityComponents)
    
- [Unterstützte Topologien](mobility.md#SupportedTopos)
    
- [Technische Anforderungen](mobility.md#TechRequirements)
    
- [Definieren der Mobilitätsanforderungen](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Mobilitätskomponenten
<a name="MobilityComponents"> </a>

Es gibt vier Dienste, die Mobilität für Skype für Business Server umfassen:
  
- **Unified Communications-Web-API (UCWA)**
    
    Stellt Dienste für die Echtzeitkommunikation mit Mobile und Web-Clients für Skype für Business Server bereit. Wenn Skype für Business Server bereitgestellt wird, erstellt eines UCWA virtuellen Verzeichnis in den internen und externen Webdiensten. Es handelt sich um eine virtuelle Komponente in diesem virtuellen Verzeichnis, die Anrufe von UCWA-fähigen Clients akzeptiert. Die Client-Apps kommunizieren zu folgenden Zwecken über eine REST-Schnittstelle (Representational State Transfer):
    
  - Anwesenheit
    
  - Kontakte
    
  - Chat
    
  - VoIP
    
  - Videokonferenzen
    
  - Zusammenarbeit
    
    UCWA verwendet einen P-GET-basierten Kanal, um Ereignisse zu senden, z. B. eingehende Anrufe, eingehende Sofortnachrichten oder Nachrichten für die Client-App.
    
- **Mobilitätsdienst (MCX)**
    
    Unterstützt Skype für Business-Funktionen wie Sofortnachrichten, Anwesenheit und Kontakte auf mobilen Geräten. Der mobilitätsdienst ist auf jedem Front-End-Server in jedem Pool installiert, die für die Unterstützung von Skype für Business-Funktionen auf mobilen Geräten vorgesehen ist. Bei der Installation von Skype für Business Server 2015 wird ein neues virtuelles Verzeichnis ("MCX") unter der internen und externen Websites auf Front-End-Servern erstellt.
    
    > [!NOTE]
    > Unterstützung für mobile Clients von Vorversionen MCX (Mobility Service) ist nicht mehr in Skype für Business Server 2019 verfügbar. Alle aktuellen Skype für mobile Clients Business Unified Communications Web API (UCWA) zur Unterstützung von Sofortnachrichten (IM), Anwesenheit und Kontakte bereits verwenden. Benutzer mit Clients von Vorversionen von MCX müssen an einen aktuellen Client aktualisieren.
  
- **AutoErmittlungsdienst**
    
    Gibt die Position des Benutzers und mobile Geräte und andere Skype für Business-Clients nach Ressourcen (wie die internen und externen URLS für Skype für Business Server-Webdienste, die Mcx URL oder UCWA-URL) suchen unabhängig vom Speicherort im Netzwerk ermöglicht. Für die automatische Ermittlung werden hartcodierte Hostnamen („lyncdiscoverinternal“ für Benutzer innerhalb des Netzwerks und „lyncdiscover“ für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers verwendet. Sowohl Clientverbindungen über HTTP als auch über HTTPS werden unterstützt. 
    
    Der AutoErmittlungsdienst installiert ist, klicken Sie auf jedem Front-End-Server und auf jedem Director in jedem Pool, der Skype für Business-Funktionen auf mobilen Geräten unterstützen soll hat. Wenn Sie den Dienst installieren, wird ein neues virtuelles Verzeichnis (AutoErmittlung) unter der internen und externen Websites auf Ihren Front-End-Server und Director-Server erstellt.
    
- **Pushbenachrichtigungsdienst**
    
    Ein Cloud-basierten Dienst, der sich in Ihrer Skype für Business Online-Rechenzentrum befindet. Klicken Sie auf Telefone, die keine Skype für Business-Client im Hintergrund ausgeführt haben, wenn ein neues Ereignis eintritt, Benachrichtigung über eine verpasste Ereignis (Push-Benachrichtigung genannt) Ruft gesendet an das mobile Gerät stattdessen. Der mobilitätsdienst sendet eine Benachrichtigung an den pushbenachrichtigungsdienst (MPNS), der dann an das mobile Gerät gesendet. Der Benutzer kann dann auf seinem mobilen Gerät auf die Benachrichtigung reagieren und die App dadurch aktivieren. Ein Edge-Server ist für diese Funktionalität erforderlich.
    
## <a name="supported-topologies"></a>Unterstützte Topologien
<a name="SupportedTopos"> </a>

Wir haben die folgenden unterstützt Skype für Business Server-Clientanwendungen für die Planung Ihrer Topologie:
  
- Mobilität Standard Edition
    
- Mobilität Enterprise Edition
    
Sie sollten diese Funktion mit Skype für Business Server Edge-Server oder Lync Server 2013-Edge-Server verwenden können.
  
Der mobilitätsdienst wird auf Front-End-Servern beim gemeinsam mit dem Vermittlungsserver mit zwei Netzwerkschnittstellen werden unterstützt, jedoch müssen Sie die entsprechenden Schritte ausführen, um diese Schnittstellen konfigurieren. Sie müssen die Schnittstelle, die als der Vermittlungsserver kommuniziert und der IP-Schnittstelle, die als Front-End-Server kommunizieren IP-Adressen zugewiesen. Sie können im Topologie-Generator dazu, indem Sie die richtige IP-Adresse für jeden Dienst, anstatt die Standardauswahl **verwenden alle konfigurierte IP-Adressen** auswählen.
  
## <a name="technical-requirements"></a>Technische Anforderungen
<a name="TechRequirements"> </a>

Es ist wichtig, bei der Planung die verschiedenen Szenarien zu berücksichtigen, die sich im Zusammenhang mit mobilen Anwendungen für Ihre mobilen Benutzer ergeben können. Beispiel: Jemand verwendet privat eine mobile App über ein 3G-Netzwerk und wechselt dann am Arbeitsplatz zum Unternehmens-WLAN. Benutzer können beim Verlassen Gebäude 4 G umschalten. Wenn Sie jetzt entsprechend planen, können Sie diese Netzwerkübergänge unterstützen und für konsistente Benutzerfreundlichkeit sorgen.
  
### <a name="dns-configuration"></a>DNS-Konfiguration

Die Mobilitätsdienste Mcx und UCWA verwenden DNS auf die gleiche Weise. Bei der AutoErmittlung suchen mobile Geräte mithilfe von DNS nach Ressourcen. Bei der DNS-Suche wird versucht, eine Verbindung mit dem FQDN herzustellen, der dem internen DNS-Eintrag zugeordnet ist („lyncdiscoverinternal.[interner Domänenname]“). Wenn der interne DNS-Eintrag nicht für die Verbindung verwendet werden kann, wird eine zweite Verbindung versucht, dieses Mal mit dem externen DNS-Eintrag („lyncdiscover.[SIP-Domäne]“). Warum zwei DNS-Einträge? Ein mobiles Gerät, das sich intern im Netzwerk befindet, kann die interne AutoErmittlungs-URL verwenden. Externe mobile Geräte verwenden die externe AutoErmittlungs-URL. In beiden Fällen zurückgegebenen der AutoErmittlungsdienst alle Webdienst-URLs für Homepool des Benutzers, der den mobilitätsdienst (Mcx und UCWA) enthält.
  
Es wird erwartet, dass die externen AutoErmittlung-Anfragen über den Reverseproxy weitergeleitet werden, den Sie für Skype für Business Server konfiguriert haben. Allerdings werden die internen Mobilitätsdienst-URL und die externe Mobilitätsdienst-URL den externen Webdienste-FQDN zugeordnet. Aus diesem Grund unabhängig davon, ob ein mobiles Gerät intern oder extern in Ihr Netzwerk ist, das Gerät verbindet immer auf die Skype für Business Server mobilitätsdienst extern, über den Reverseproxy.
  
> [!NOTE]
> Wie einfach erwähnt, gehen alle Mobility Service-Datenverkehr (intern und extern) über den Reverseproxy. Manchmal treten jedoch Probleme auf, wenn der interne Datenverkehr über eine Schnittstelle ausgeht und dann über die gleiche Schnittstelle wieder zurückfließen soll. Dies kann gegen Ihre Spoofingregeln (formell: Spoofing von TCP-Paketen) verstoßen. Sie müssen **Haarstrich Verankern** , Mobilität Funktion zulassen.
  
> [!NOTE]
> Wenn Sie dazu bereit sind, können Sie auch einen Reverseproxy verwenden, der ist unabhängig von der Firewall (für Sicherheit, den Zwecke spoofing Prevention immer an Ihrer Firewall erzwungen werden soll) auswählen. Auf diese Weise kann die Hairpin an der externen Schnittstelle des Ihren Reverseproxy aufrufen, statt die Firewall externe Schnittstelle vorkommen. Dadurch können Sie die spoofing ordnungsgemäß an der Firewall, während Sie die Regel an Ihren Reverseproxy aufrufen sicher – und Sie Ihre Mobilitätsfunktionen erhalten erkennen. 
  
> [!NOTE]
> Wenn Sie diese Route wechseln, müssen Sie die DNS-Host oder CNAME-Einträge verwenden, um den Reverseproxy für das Hairpin-Verhalten (nicht die Firewall), falls möglich definieren. 
  
Sie müssen einige Aspekte konfigurieren, um Benutzer innerhalb und außerhalb des Unternehmensnetzwerks zu unterstützen.
  
Für interne und externe Web-FQDNs gelten die folgenden Regeln:
  
- Neue CNAME- oder A-Einträge (Host für IPv6: AAAA) für die automatische Ermittlung
    
- Neue Firewallregel, wenn Pushbenachrichtigungen über das WLAN-Netzwerk unterstützt werden sollen
    
- Subject alternative Namen auf interne Serverzertifikate und reverseproxyzertifikate für die automatische Ermittlung.
    
- Front-End-Server Hardwaregerät zum Lastenausgleich des Konfiguration Änderungen Quelle Affinität.
    
Dies sind die erforderlichen Topologie zur Unterstützung der Mobility Service and Autodiscover Service:
  
- Das Front-End-Pool interne Web-FQDN muss sich vom Front-End-Pool externen Web-FQDN.
    
- Auf den internen Web-FQDN darf nur von innerhalb des Unternehmensnetzwerks zugegriffen werden, und er darf nur in eine Unternehmensnetzwerkadresse aufgelöst werden.
    
- Auf den externen Web-FQDN darf nur vom Internet aus zugegriffen werden, und er darf nur in eine Internetadresse aufgelöst werden.
    
- Für einen Benutzer innerhalb des Firmennetzwerks befinden muss die Mobilitätsdienst-URL an den externen Web-FQDN behandelt werden. Dies ist für den mobilitätsdienst und gilt nur für diese URL.
    
- Für einen Benutzer außerhalb des Firmennetzwerks befinden muss die Anforderung an den externen Web-FQDN des Front-End-Pool oder Director wechseln.
    
Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:
  
- Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen
    
- Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen
    
Die interne AutoErmittlungs-URL sollte nicht von außerhalb des internen Netzwerks adressierbar sein. Die externe AutoErmittlungs-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn dies für die externe URL nicht möglich ist, wird dies die Funktionen der mobilen Clients vermutlich nicht beeinträchtigen, da immer zuerst versucht wird, eine Verbindung mit der internen URL herzustellen.
  
### <a name="port-and-firewall-requirements"></a>Port- und Firewallanforderungen

Wir haben die meisten dieser in unsere anderen Dokumentationen behandelt, aber insbesondere für die Mobilität, Sie nun die folgenden Ports haben möchten öffnen in Ihrem Netzwerk Enterprise Wi-Fi, wenn Sie haben keine Benutzer verwaltet auf einer Survivable Branch Appliance (SBA):
  
- Für „UcwaSipExternalListeningPort“ wird Port 5088 benötigt.
    
- Für „UcwaSipPrimaryListeningPort“ wird Port 5089 benötigt.
    
### <a name="certificate-requirements"></a>Zertifikatanforderungen

Wenn Sie automatische Ermittlung für mobile Clients Business für Ihre Skype verwenden, müssen Sie die SAN (Subject alternative Name) Listen Zertifikate zur Unterstützung von sicherer Verbindungen von Ihren mobilen Clients ändern. Wenn bereits Zertifikate vorhanden sind, müssen Sie neue Zertifikate mit den hier beschriebenen SAN-Einträgen anfordern und zuweisen. Dies muss für jeden Front-End-Server und Director (Wenn in Ihrer Umgebung) durchgeführt werden, die den AutoErmittlungsdienst ausgeführt wird. Wir empfehlen auch SAN Reverseproxy Zertifikate, Listen, Hinzufügen von SAN-Einträge für jede SIP-Domäne in Ihrer Organisation zu ändern.
  
Dies sollte ein einfacher Vorgang sein, wenn Sie die neue Zertifikate aus einer internen Zertifizierungsstelle (Certificate Authority) anfordern, aber öffentliche Zertifikate sind etwas komplexerer und potenziell viel teurer, weisen Sie darauf hin, dass es für viele SIP hinzufügen kostspielig sein kann nicht erneut anfordern, Domänen für eine neue öffentliche Cert. In diesem Fall muss ist es ein Ansatz, der unterstützt wird, jedoch **nicht empfohlen**. Sie können Ihren Reverseproxy aufrufen, um die anfängliche autoermittlungsanforderung Service über Port 80, der HTTP verwendet wird, anstatt Port 443, stellen HTTPS ist konfigurieren (und 443 ist die Standardkonfiguration). Eingehende Anforderung wird an Port 8080 auf dem Front-End-Pool oder Director umgeleitet. Auf diese Weise müssen Sie, um alle zertifikatänderungen anzuzeigen da dieser Datenverkehr HTTPS für Anfragen verwenden nicht zur Verfügung. Jedoch erneut, es wird nicht empfohlen, obwohl es für Sie geeignet ist.
  
### <a name="windows-and-iis-requirements"></a>Anforderungen im Hinblick auf Windows und IIS

Sie sollten eine unterstützte Version von Windows Server für Ihre Skype für Business Server-Umgebung verfügen. Daher benötigen Sie für Mobilitätsfunktionen auch IIS 8 oder IIS 8.5. Es müssen einige Änderungen auf die Standardeinstellungen für ASP.NET werden, aber das Mobilität-Installationsprogramm ausführen, das automatisch.
  
### <a name="hlb-requirements"></a>HLB-Anforderungen

Wenn Sie eine Topologie für Skype Business Server nutzen, die ein Hardwaregeräts zum Lastenausgleich für den Front-End-Pool enthält (Topologie mit mehreren Front-End-Server wäre), müssen die externe Webdienste virtuelle IP-Adressen (Ends) für Webdienste Datenverkehr konfiguriert werden soll für die Datenquelle. Die Quellaffinität stellt sicher, dass mehrere Verbindungen von einem einzelnen Client an einen einzigen Server gesendet werden, um den Sitzungsstatus aufrechtzuerhalten.
  
Wenn Sie Skype für mobile Clients Business nur über das interne Wi-Fi-Netzwerk unterstützen möchten, sollten Sie Ihre interne Web Services-Ends für Quelle konfigurieren, wie für externe Web Services-Ends beschrieben. In diesem Fall sollten Sie verwenden Source_addr (oder TCP) Affinität für die interne Web Services-Ends auf die Hardwaregeräts zum Lastenausgleich.
  
Ausführlichere Informationen hierzu finden Sie in der Dokumentation zu [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Anforderungen an den Reverseproxy

Um die Unterstützung der AutoErmittlung für mobile Clients Business für Skype benötigen Sie eine neue Webveröffentlichungsregel erstellen wie folgt aktualisieren:
  
- Wenn Sie aktualisieren möchten SAN listet Reverseproxy Zertifikate, und Sie HTTPS für die anfängliche autoermittlungsanforderung Dienst verwenden, müssen Sie die Webveröffentlichungsregel für Lyncdiscover zu aktualisieren. \<Sipdomain\>. Dies wird in der Regel für die externen Webdienste-URL auf den Front-End-Pool mit der Veröffentlichung Rul kombiniert.
    
- Wenn Sie sich entschieden haben, verwenden Sie HTTP für die anfängliche autoermittlungsanforderung Dienst zu verhindern, dass die SAN aktualisieren für Ihren Reverseproxy-Zertifikaten (Dies wird nicht empfohlen) aufgelistet, müssen Sie als Nächstes erstellen Sie eine neue Webveröffentlichungsregel für Port 80 für HTTP/TCP, nicht vorhanden ist bereits. Wenn diese Regel vorhanden ist, aktualisieren Sie, um eine Lyncdiscover enthalten. \<Sipdomain\> Eintrag.
    
## <a name="defining-your-mobility-needs"></a>Definieren der Mobilitätsanforderungen
<a name="MobilityNeeds"> </a>

Nun, da wir die Topologien, Komponenten und technische Anforderungen überprüft haben, sehen wir uns im Hinblick auf eine Implementierung der Mobilität möglicherweise Ihrer Organisation.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Möchten Sie für mobile Skype for Business-Clients die automatische Ermittlung verwenden?

Wir empfehlen dringend, die automatische Ermittlung zu verwenden. Dazu müssen Sie wie weiter oben unter „Technische Anforderungen“ beschrieben neue interne und externe DNS-Einträge erstellen. Bei der automatischen Suche kann die Skype für Business Clients automatisch Skype für Business Server-Webdienste von einer beliebigen Position suchen ohne eine URL manuell eingegeben werden.
  
Wenn Sie möchten, können Sie manuelle Einstellungen verwenden. Die Benutzer müssen dann auf ihren mobilen Geräten die folgenden URLs eingeben:
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** für den externen Zugriff.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** für den internen Zugriff.
    
Wir möchten nochmals betonen, dass wir die automatische Ermittlung empfehlen. Manuelle Einstellungen können jedoch bei der Problembehandlung hilfreich sein.
  
### <a name="are-you-going-to-support-push-notifications"></a>Möchten Sie Pushbenachrichtigungen unterstützen?

Pushbenachrichtigungen werden für mobile Anwendungen verwendet, die diese Funktionalität unterstützen, um Benutzer über Ereignisse zu benachrichtigen, wenn die App gerade nicht aktiv ist. Den Edge-Server müssen eine verbundbeziehung für Ihre Cloud-basierten Skype für Business Server Push Notification Service verfügen, die sich auf die Skype für Business Online-Rechenzentrum befindet. Um Pushbenachrichtigungen zu aktivieren, müssen Sie ein Cmdlet ausführen.
  
> [!NOTE]
> Wenn Sie alle Benutzer weiterhin mit Lync Server 2010-Clients verfügen, benötigen sie TCP-Port 5223 öffnen auf Ihrem Unternehmensnetzwerk WiFi ausgehende. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Möchten Sie alle Ihre Benutzer den Zugriff auf alle Features für Mobilität, oder möchten Sie die Benutzer angeben, die diese Funktionen stattdessen zugreifen können?

Wir haben die Tabelle, die Ihnen bei der einige der Features, die für alle Benutzer verfügbar sind und als Standard verwenden, ob sie, wie oder nicht festgelegt sind. Die vollständige Liste finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Alle diese Funktionen gelten global, für bestimmte Standorte oder für bestimmte Benutzer. 
  
|**Funktion**|**Parametername**|**Beschreibung**|**Standardeinstellung**|
|:-----|:-----|:-----|:-----|
|Mobilität aktivieren  <br/> |EnableMobility  <br/> |Steuert die Benutzer in einem bestimmten Bereich, die Skype für Business mobilen Client installiert haben. Wenn die Richtlinie auf „False“ festgelegt ist, können sich die Benutzer nicht mit ihrem Client anmelden.  <br/> |True  <br/> |
|Externe Anrufe  <br/> |EnableOutsideVoice  <br/> |Ermöglicht Benutzern die Verwendung der Funktion „Geschäftlich anrufen“, das heißt, die Benutzer können Anrufe unter ihrer geschäftlichen Telefonnummer anstelle ihrer Mobiltelefonnummer tätigen und empfangen. Wenn „False“ festgelegt ist, können die Benutzer auf ihren Mobiltelefonen nicht über die geschäftliche Telefonnummer Anrufe tätigen oder empfangen.  <br/> |True  <br/> |
|IP-Audio und -Video aktivieren  <br/> |EnableIPAudioVideo  <br/> |Wenn der Standardwert festgelegt ist, können Benutzer auf mobilen Geräten über VoIP Sprach- oder Videoanrufe tätigen oder empfangen. Wenn die Einstellung auf „False“ festgelegt ist, können die Benutzer auf ihren mobilen Geräten keine dieser Funktionen nutzen.  <br/> |True  <br/> |
|Wi-Fi für IP-Audio erforderlich  <br/> |RequireWiFiForIPAudio  <br/> |Definiert, ob VoIP-Anrufe in Clients über das WLAN anstatt über das Mobilfunknetz getätigt oder empfangen werden. Wenn „True“ festgelegt ist, können die Benutzer nur dann VoIP-Anrufe tätigen und empfangen, wenn sie mit einem WLAN verbunden sind.  <br/> |Falsch  <br/> |
|Wi-Fi für IP-Video erforderlich  <br/> |RequireWiFiForIPVideo  <br/> |Definiert, ob Videoanrufe in Clients über das WLAN anstatt über das Mobilfunknetz getätigt oder empfangen werden. Wenn „True“ festgelegt ist, können die Benutzer nur dann VoIP-Anrufe tätigen und empfangen, wenn sie mit einem WLAN verbunden sind.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Sollen Benutzer, die nicht für Enterprise-VoIP aktiviert sind, an Konferenzen teilnehmen können, indem sie auf den entsprechenden Teilnahmelink klicken?

Um Benutzern Zugriff auf Mobilitätsfeatures und Anrufen über den Arbeitsplatz haben müssen sie für Enterprise Voice aktiviert werden. Aber auch wenn sie nicht aktiviert ist, sie können weiterhin an Konferenzen teilnehmen, indem Sie auf einen Link auf ihrem mobilen Gerät, jedoch nur, wenn sie eine entsprechende VoIP-Richtlinie zugewiesen werden. Sie können:
  
- Sie weisen diesen Benutzern eine bestimmte VoIP-Richtlinie zu, oder
    
- Sie stellen sicher, dass eine globale Richtlinie oder eine Richtlinie auf Standortebene vorhanden ist, die für diese Benutzer gilt.
    
In jedem Fall muss die zugewiesene VoIP-Richtlinie über PSTN-Verwendungseinträge und -Routen verfügen. Diese definieren die Bereiche, in die Benutzer hinauswählen können, um an einer Konferenz teilzunehmen.
  
> [!NOTE]
> Mobile Benutzer, die möchten, klicken Sie auf zur Teilnahme verwenden erfordern eine VoIP-Richtlinie sowie die zugehörigen PSTN-verwendungsdatensätzen und VoIP-Routen, da beim Klicken auf diesen Link auf ihren mobilen Geräten auf, ein ausgehendes Anrufs über Skype für Business Server das Ergebnis sein. 
  


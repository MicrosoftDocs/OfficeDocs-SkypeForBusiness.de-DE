---
title: Planen der Mobilität für Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planen Sie ihre Implementierung von Mobilität für Skype for Business Server.
ms.openlocfilehash: a86f9ed4c3c41a1afa60a3f8181307589b0ce678
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400279"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planen der Mobilität für Skype for Business Server
 
Planen Sie ihre Implementierung von Mobilität für Skype for Business Server.
  
Mit Skype for Business Server können Sie das Mobilitätsfeature bereitstellen, um Skype for Business Server Funktionen auf mobilen Geräten bereitzustellen. Dieser Artikel enthält Details zum Mobilitätsfeature und hilft Ihnen bei der Planung Ihrer Bereitstellung.
  
Das Mobilitätsfeature für Skype for Business Server kann mobile Clients für Skype for Business sowie Lync-Clients bis 2010 unterstützen. Nach der Bereitstellung können Ihre Benutzer mithilfe von unterstützten iOS-, Android- und Windows Phone mobilen Geräten eine Verbindung zu Ihrer Skype for Business Server Bereitstellung herstellen, um verschiedene Features zu nutzen, einschließlich Enterprise-VoIP Features. Wir haben unten eine partielle Liste eingefügt, und Sie können auch den [Vergleich der Desktopclientfeatures auf Skype for Business](clients-and-devices/desktop-feature-comparison.md) überprüfen, um weitere Informationen zu erhalten:
  
- Senden und Empfangen von Nachrichten
    
- Anzeigen der Anwesenheit
    
- Anzeigen von Kontakten
    
- Klicken, um an einer Konferenz teilzunehmen
    
- Anruf über Arbeit
    
- Erreichen einzelner Nummern
    
- Voicemail
    
- Benachrichtigung über verpasste Anrufe
    
- VoIP (Voice over IP)
    
- Teilnehmervideo (H.264)
    
- Anzeigen von Besprechungsinhalten (PowerPoint und Desktop-/Anwendungsfreigabe)
    
All dies geschieht über die Unified Communications-Web-API oder UCWA. UCWA wurde erstmals in Lync Server 2013 eingeführt und wird weiterhin für Skype for Business Server verwendet. Es gibt eine zusätzliche Funktionalität für die Kommunikation mit Lync 2010-Clients, und das ist Mobility Service (MCX). Dies sind kostenlose Dienste, die es Lync Server 2010- und 2013-Clients sowie Skype for Business Clients ermöglichen, erfolgreich auf Skype for Business Server Bereitstellungen zuzugreifen.
  
> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
Es ist wichtig zu beachten, dass alle diese Features zwar verfügbar sind, nachdem Mobilität implementiert wurde, aber auf einigen Geräten möglicherweise etwas anders funktionieren. Wir haben eine Website, auf der erläutert wird, welche Features auf welchen Geräten funktionieren, beim [Vergleich der Mobilen Clientfeatures für Skype for Business](clients-and-devices/mobile-feature-comparison.md). Wir haben auch einige hervorragende Geräte- und Betriebssysteminformationen bei [Plan für Clients und Geräte](clients-and-devices/clients-and-devices.md).
  
Mobilität nutzt die AutoErmittlungsfunktion, mit der Clients Skype for Business Server Webdienste automatisch suchen können, ohne dass Benutzer URLs eingeben müssen (sie müssen sie nicht einmal kennen). Wenn Sie eine Problembehandlung durchführen müssen, wird die manuelle Eingabe von URLs weiterhin unterstützt.
  
Pushbenachrichtigungen werden auch unterstützt, wenn die Skype for Business App nicht im Hintergrund ausgeführt wird (oder für mobile Geräte, die anwendungen nicht unterstützen, die im Hintergrund ausgeführt werden). Eine Pushbenachrichtigung wird an ein mobiles Gerät über ein Ereignis gesendet, das eintritt, wenn das Gerät oder die App inaktiv ist. Ein gutes Beispiel ist das Fehlen einer Chatnachricht, wenn Ihr Telefon nicht aktiv ist. Dies würde dazu führen, dass eine Pushbenachrichtigung gesendet wird (dies wird als Popup oder Benachrichtigung angezeigt, z. B. wenn die App im Hintergrund ausgeführt wird). Bei Pushbenachrichtigungen verpassen Benutzer keine Chat- oder Sprachanrufe.
  
Weitere Informationen finden Sie in den folgenden Abschnitten:
  
- [Mobilitätskomponenten](mobility.md#MobilityComponents)
    
- [Unterstützte Topologien](mobility.md#SupportedTopos)
    
- [Technische Anforderungen](mobility.md#TechRequirements)
    
- [Definieren ihrer Mobilitätsanforderungen](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Mobilitätskomponenten
<a name="MobilityComponents"> </a>

Es gibt vier Dienste, die Mobilität für Skype for Business Server umfassen:
  
- **Unified Communications Web API (UCWA)**
    
    Stellt Dienste für die Echtzeitkommunikation mit mobilen Clients und Webclients für Skype for Business Server bereit. Wenn Skype for Business Server bereitgestellt wird, wird ein virtuelles UCWA-Verzeichnis in den internen und externen Webdiensten erstellt. Eine virtuelle Komponente in diesem virtuellen Verzeichnis, die Aufrufe von UCWA-fähigen Clients akzeptiert. Die Client-Apps kommunizieren über eine REST-Schnittstelle (Representational State Transfer) für:
    
  - Anwesenheit
    
  - contacts
    
  - Chat
    
  - Voip
    
  - Videokonferenzen
    
  - Zusammenarbeit
    
    UCWA verwendet einen P-GET-basierten Kanal, um Ereignisse wie einen eingehenden Anruf, eingehende Chatnachrichten oder eine Nachricht an die Client-App zu senden.
    
- **Mobilitätsdienst (MCX)**
    
    Unterstützt Skype for Business Server Funktionen wie Chatnachrichten, Anwesenheitsinformationen und Kontakte auf mobilen Geräten. Der Mobilitätsdienst wird auf jedem Front-End-Server in jedem Pool installiert, der Skype for Business Server Funktionen auf mobilen Geräten unterstützen soll. Wenn Sie Skype for Business Server 2015 installieren, wird ein neues virtuelles Verzeichnis (Mcx) unter den internen und externen Websites auf Ihren Front-End-Servern erstellt.
    
    > [!NOTE]
    > McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
- **AutoErmittlungsdienst**
    
    Identifiziert den Standort des Benutzers und ermöglicht mobilen Geräten und anderen Skype for Business Clients, Ressourcen (z. B. die internen und externen URLs für Skype for Business Server Webdienste, die Mcx-URL oder die UCWA-URL) unabhängig vom Netzwerkstandort zu suchen. Die automatische Ermittlung verwendet hartcodierte Hostnamen (lyncdiscoverinternal für Benutzer innerhalb des Netzwerks, LyncDiscover für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers. Es unterstützt Clientverbindungen, die HTTP oder HTTPS verwenden. 
    
    Der AutoErmittlungsdienst wird auf jedem Front-End-Server und auf jedem Director in jedem Pool installiert, der Skype for Business Server Funktionen auf mobilen Geräten unterstützen soll. Wenn Sie den Dienst installieren, wird ein neues virtuelles Verzeichnis (AutoErmittlung) unter den internen und externen Websites auf Ihren Front-End-Servern und Directors erstellt.
    
- **Pushbenachrichtigungsdienst**
    
    Ein cloudbasierter Dienst, der sich in Ihrem Skype for Business Online-Rechenzentrum befindet. Auf Telefonen, auf denen Skype for Business Client nicht im Hintergrund ausgeführt wird, wird bei einem neuen Ereignis stattdessen die Benachrichtigung über ein verpasstes Ereignis (als Pushbenachrichtigung bezeichnet) an das mobile Gerät gesendet. Der Mobilitätsdienst sendet eine Benachrichtigung an den Pushbenachrichtigungsdienst (MPNS), der sie dann an das mobile Gerät sendet. Der Benutzer kann dann auf dem mobilen Gerät auf die Benachrichtigung reagieren, um die App zu aktivieren. Für diese Funktionalität ist ein Edgeserver erforderlich.
    
## <a name="supported-topologies"></a>Unterstützte Topologien
<a name="SupportedTopos"> </a>

Wir haben die folgenden unterstützten Skype for Business Server Anwendungen für Ihre Topologieplanung:
  
- Mobilität Standard Edition
    
- Mobilität Enterprise Edition
    
Sie sollten diese Funktionalität mit Skype for Business Server Edgeservern oder Lync Server 2013-Edgeservern verwenden können.
  
Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, wenn er mit der Vermittlungsserverrolle mit zwei Netzwerkschnittstellen verbunden ist. Sie müssen jedoch die entsprechenden Schritte zum Konfigurieren dieser Schnittstellen ausführen. Sie müssen der spezifischen Schnittstelle, die als Vermittlungsserver kommunizieren wird, UND der Netzwerk-IP-Schnittstelle, die als Front-End-Server kommunizieren wird, IP-Adressen zuweisen. Sie können dies im Topologie-Generator tun, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die Standardauswahl **"Alle konfigurierten IP-Adressen verwenden** " zu verwenden.
  
## <a name="technical-requirements"></a>Technische Anforderungen
<a name="TechRequirements"> </a>

Es ist wichtig, die verschiedenen Szenarien für mobile Anwendungen zu planen, auf die Ihre mobilen Benutzer stoßen können. Beispielsweise kann jemand außerhalb der Arbeit mit der Verwendung einer mobilen App beginnen, indem er eine Verbindung über ein 3G Netzwerk herstellt und dann zum Unternehmens-Wi-Fi-Netzwerk wechselt, wenn er die Arbeit erreicht. Sie können zu 4G wechseln, wenn sie ihr Gebäude verlassen. Mit der Planung können Sie diese Netzwerkübergänge unterstützen und eine konsistente Benutzererfahrung gewährleisten.
  
### <a name="dns-configuration"></a>DNS-Konfiguration

Die Mobilitätsdienste Mcx und UCWA verwenden DNS auf die gleiche Weise. Bei der automatischen Ermittlung verwenden mobile Geräte DNS, um Ressourcen zu suchen. Während der DNS-Suche wird versucht, eine Verbindung mit dem FQDN herzustellen, der dem internen DNS-Eintrag (lyncdiscoverinternal.[ interner Domänenname]). Wenn der interne DNS-Eintrag nicht verwendet werden kann, um diese Verbindung herzustellen, wird versucht, eine zweite Verbindung herzustellen, dieses Mal mit dem externen DNS-Eintrag (lyncdiscover.[ sipdomain]). Warum also zwei? Ein mobiles Gerät, das in Ihrem Netzwerk intern ist, kann die interne AutoErmittlungs-URL verwenden. Externe mobile Geräte verwenden die externe AutoErmittlungs-URL. In beiden Fällen gibt der AutoErmittlungsdienst alle Webdienst-URLs für den Startpool des Benutzers zurück, der den Mobilitätsdienst (Mcx und UCWA) enthält.
  
Es wird erwartet, dass die externen AutoErmittlungsanforderungen den Reverseproxy durchlaufen, den Sie für Skype for Business Server konfiguriert haben. Allerdings sind sowohl die interne Mobilitätsdienst-URL als auch die URL des externen Mobilitätsdiensts dem externen Webdienst-FQDN zugeordnet. Unabhängig davon, ob es sich bei einem mobilen Gerät um ein internes oder externes Gerät handelt, stellt das Gerät daher immer eine externe Verbindung mit dem Skype for Business Server Mobilitätsdienst über Ihren Reverseproxy her.
  
> [!NOTE]
> Wie bereits erwähnt, wird der gesamte Mobilitätsdienstdatenverkehr (intern und extern) über Ihren Reverseproxy geleitet. Manchmal tritt jedoch ein Problem auf, wenn der interne Datenverkehr eine Schnittstelle verlässt, nur um dann zu versuchen, auf derselben Schnittstelle wieder einzukommen. Dies kann gegen Ihre Spoofingsicherheitsregeln (formell als TCP-Paketspoofing bezeichnet) verstoßen. Sie müssen die **Mobilitätsfunktion für das Anheften von Haaren** zulassen.
  
> [!NOTE]
> Wenn Sie dazu bereit sind, können Sie auch einen Reverseproxy verwenden, der von Ihrer Firewall getrennt ist (aus Sicherheitsgründen sollte spoofing prevention immer in Ihrer Firewall erzwungen werden). Auf diese Weise kann die Spitzkehren an der externen Schnittstelle Ihres Reverseproxys statt an der externen Schnittstelle Ihrer Firewall erfolgen. Auf diese Weise können Sie spoofing ordnungsgemäß in Ihrer Firewall erkennen, während Sie die Regel am Reverseproxy lockern und Ihre Mobilitätsfunktionalität abrufen. 
  
> [!NOTE]
> Wenn Sie diese Route verwenden, müssen Sie nach Möglichkeit den DNS-Host oder die CNAME-Einträge verwenden, um den Reverseproxy für das Spitzkehrenverhalten (nicht die Firewall) zu definieren. 
  
Es gibt einige Dinge, die Sie konfigurieren müssen, um Benutzer innerhalb und außerhalb Ihres Unternehmensnetzwerks zu unterstützen.
  
Dies sind die Regeln für interne und externe Web-FQDNs:
  
- Neue CNAME- oder A-DNS-Einträge (Host, wenn IPv6, AAAA) für die automatische Ermittlung.
    
- Neue Firewallregel, wenn Sie Pushbenachrichtigungen über Ihr Wi-Fi Netzwerk unterstützen möchten.
    
- Alternative Antragstellernamen für interne Serverzertifikate und Reverseproxyzertifikate für die automatische Ermittlung.
    
- Die Konfiguration des Hardwarelastenausgleichs auf dem Front-End-Server ändert die Quellaffinität.
    
Dies sind die Topologieanforderungen, die zur Unterstützung des Mobilitätsdiensts und des AutoErmittlungsdiensts erforderlich sind:
  
- Der interne Web-FQDN des Front-End-Pools muss sich vom externen Web-FQDN des Front-End-Pools unterscheiden.
    
- Der interne Web-FQDN darf nur innerhalb des Unternehmensnetzwerks aufgelöst werden und von dort aus zugänglich sein.
    
- Der externe Web-FQDN darf nur in das Internet aufgelöst werden und über das Internet zugänglich sein.
    
- Für einen Benutzer innerhalb des Unternehmensnetzwerks muss die URL des Mobilitätsdiensts an den externen Web-FQDN adressiert werden. Diese Anforderung gilt für den Mobilitätsdienst und gilt nur für diese URL.
    
- Für einen Benutzer außerhalb des Unternehmensnetzwerks muss die Anforderung zum externen Web-FQDN des Front-End-Pools oder Director gehen.
    
Wenn Sie die automatische Ermittlung unterstützen, müssen Sie die folgenden DNS-Einträge für jede SIP-Domäne erstellen:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die innerhalb des Netzwerks Ihrer Organisation eine Verbindung herstellen.
    
- Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Internet eine Verbindung herstellen.
    
Die interne URL für die automatische Ermittlung sollte nicht von außerhalb Ihres internen Netzwerks adressierbar sein. Die EXTERNE URL für die automatische Ermittlung sollte nicht innerhalb Ihres Netzwerks adressierbar sein. Wenn dies für die externe URL jedoch nicht möglich ist, ist ihre Mobile Client-Funktionalität wahrscheinlich nicht betroffen, da die interne URL immer zuerst ausprobiert wird.
  
### <a name="port-and-firewall-requirements"></a>Port- und Firewallanforderungen

Wir haben dies größtenteils in unserer anderen Dokumentation behandelt, aber speziell für Mobilität möchten Sie die folgenden Ports in Ihrem Unternehmens-Wi-Fi-Netzwerk öffnen lassen, wenn Sie Benutzer haben, die in einer Survivable Branch Appliance (SBA) verwaltet werden:
  
- UcwaSipExternalListeningPort erfordert 5088.
    
- UcwaSipPrimaryListeningPort erfordert 5089.
    
### <a name="certificate-requirements"></a>Anforderungen für Zertifikate

Wenn Sie die automatische Ermittlung für Ihre Skype for Business mobilen Clients verwenden, müssen Sie die SAN-Listen (alternative Antragstellernamen) auf Ihren Zertifikaten ändern, um sichere Verbindungen von Ihren mobilen Clients zu unterstützen. Wenn Sie bereits über Zertifikate verfügen, müssen Sie neue Zertifikate mit den hier beschriebenen SAN-Einträgen anfordern und zuweisen. Dies muss für jeden Front-End-Server und Director (falls in Ihrer Umgebung) ausgeführt werden, auf dem der AutoErmittlungsdienst ausgeführt wird. Wir empfehlen außerdem, die SAN-Listen für Ihre Reverseproxyzertifikate zu ändern und SAN-Einträge für jede SIP-Domäne in Ihrer Organisation hinzuzufügen.
  
Dies sollte ein einfacher Prozess sein, wenn Sie die neuen Zertifikate von einer internen Zertifizierungsstelle (Zertifizierungsstelle) anfordern. Öffentliche Zertifikate sind jedoch komplexer und möglicherweise wesentlich aufwendiger für die erneute Anforderung, ganz zu erwähnen, dass es kostspielig sein kann, viele SIP-Domänen zu einem neuen öffentlichen Zertifikat hinzuzufügen. In dieser Situation gibt es einen Ansatz, der unterstützt, aber **nicht empfohlen wird**. Sie können Ihren Reverseproxy so konfigurieren, dass die ursprüngliche AutoErmittlungsdienstanforderung über Port 80 ausgeführt wird, der HTTP anstelle von Port 443 verwendet, der HTTPS ist (und 443 die Standardkonfiguration ist). Diese eingehende Anforderung wird an Port 8080 in Ihrem Front-End-Pool oder Director umgeleitet. Dadurch müssen Sie keine Zertifikatänderungen vornehmen, da für diesen Datenverkehr kein HTTPS für Anforderungen verwendet wird. Dies wird jedoch nicht empfohlen, auch wenn es für Sie funktioniert.
  
### <a name="windows-and-iis-requirements"></a>Windows- und IIS-Anforderungen

Sie sollten über eine unterstützte Windows Serverversion für Ihre Skype for Business Server Umgebung verfügen. Daher sollten Sie auch IIS 8 oder IIS 8.5 für Ihre Mobilitätsanforderungen verwenden. Es müssen einige Änderungen an den Standardeinstellungen für ASP.NET vorgenommen werden, dies wird jedoch automatisch vom Mobilitätsdienst-Installationsprogramm ausgeführt.
  
### <a name="hlb-requirements"></a>HLB-Anforderungen

Wenn Sie eine Topologie für Skype for Business Server verwenden, die einen HLB für Ihren Front-End-Pool enthält (bei der es sich um eine Topologie mit mehr als einem Front-End-Server handeln würde), müssen die externen virtuellen Webdienst-IPs (VIPs) für Webdienstdatenverkehr für die Quelle konfiguriert werden. Die Quellaffinität trägt dazu bei, sicherzustellen, dass mehrere Verbindungen von einem einzelnen Client an denselben Server gesendet werden, um den Sitzungsstatus aufrechtzuerhalten.
  
Wenn Sie beabsichtigen, Skype for Business mobile Clients nur über Ihr internes Wi-Fi Netzwerk zu unterstützen, sollten Sie die internen Webdienst-VIPs für die Quelle konfigurieren, wie für externe Webdienste VIPs beschrieben. In diesem Fall sollten Sie source_addr (oder TCP)-Affinität für die internen Webdienst-VIPs auf dem HLB verwenden.
  
Ausführliche Informationen hierzu finden Sie in den [Lastenausgleichsanforderungen für Skype for Business](network-requirements/load-balancing.md) Dokumentation.
  
### <a name="reverse-proxy-requirements"></a>Reverseproxyanforderungen

Um die automatische Ermittlung für Skype for Business mobile Clients zu unterstützen, müssen Sie die aktuelle Veröffentlichungsregel wie folgt aktualisieren:
  
- Wenn Sie die SAN-Listen für Ihre Reverseproxyzertifikate aktualisieren möchten und HTTPS für die ursprüngliche AutoErmittlungsdienstanforderung verwenden, müssen Sie die Webveröffentlichungsregel für lyncdiscover\<sipdomain\> aktualisieren. Dies wird in der Regel mit dem Veröffentlichungs-Rul für die URL der externen Webdienste im Front-End-Pool kombiniert.
    
- Wenn Sie sich entschieden haben, HTTP für die ursprüngliche AutoErmittlungsdienstanforderung zu verwenden, um zu vermeiden, dass die SAN-Liste für Ihre Reverseproxyzertifikate aktualisiert werden muss (was nicht empfohlen wird), müssen Sie eine neue Webveröffentlichungsregel für Port HTTP/TCP 80 erstellen, falls noch keine vorhanden ist. Wenn diese Regel vorhanden ist, aktualisieren Sie sie, um eine LyncDiscover einzuschließen.\<sipdomain\> Eintrag.
    
## <a name="defining-your-mobility-needs"></a>Definieren ihrer Mobilitätsanforderungen
<a name="MobilityNeeds"> </a>

Nachdem wir die Topologien, Komponenten und technischen Anforderungen überprüft haben, sehen wir uns an, was Ihre Organisation im Hinblick auf eine Mobility-Implementierung möglicherweise benötigt.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Möchten Sie die automatische Ermittlung für Skype for Business mobile Clients verwenden?

Es wird dringend empfohlen, die automatische Ermittlung zu verwenden. Es ist die Erstellung neuer interner und externer DNS-Einträge erforderlich, wie im Abschnitt "Technische Anforderungen" oben beschrieben. Mit der automatischen Ermittlung können die Skype for Business Clients Skype for Business Server Webdienste automatisch von jedem Speicherort suchen, ohne dass eine URL manuell eingegeben werden muss.
  
Sie können bei Bedarf manuelle Einstellungen verwenden. Diese URLs müssen von Benutzern auf ihren mobilen Geräten eingegeben werden:
  
- **\<ExtPoolFQDN\>https:///AutoErmittlung/autodiscoverservice.svc/Root** für externen Zugriff.
    
- **\<IntPoolFQDN\>https:///AutoErmittlung/autodiscoverservice.svc/Root** für internen Zugriff.
    
Auch hier empfehlen wir die Verwendung der automatischen Ermittlung. Möglicherweise sind manuelle Einstellungen für Problembehandlungszwecke hilfreich.
  
### <a name="are-you-going-to-support-push-notifications"></a>Unterstützen Sie Pushbenachrichtigungen?

Pushbenachrichtigungen werden für mobile Anwendungen verwendet, die diese Funktion unterstützen, um einen Benutzer über Ereignisse zu benachrichtigen, während die App nicht aktiv ist. Ihr Edgeserver muss über eine Verbundbeziehung mit Ihrem cloudbasierten Skype for Business Server Pushbenachrichtigungsdienst verfügen, der sich im Skype for Business Online-Rechenzentrum befindet. Sie müssen ein Cmdlet ausführen, um Pushbenachrichtigungen zu aktivieren.
  
> [!NOTE]
> Wenn noch jemand Lync Server 2010-Clients verwendet, benötigt er tcp-Port 5223, der ausgehend in Ihrem Unternehmens-WLAN-Netzwerk geöffnet ist. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Möchten Sie, dass alle Ihre Benutzer auf alle Mobilitätsfeatures zugreifen, oder möchten Sie die Benutzer angeben, die stattdessen auf diese Features zugreifen können?

Wir haben eine Tabelle, die Ihnen bei einigen der Features hilft, die für alle Benutzer verfügbar sind, und ob sie standardmäßig auf diese Weise festgelegt sind oder nicht. Eine vollständige Liste finden Sie unter ["New-CsMobilityPolicy"](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Die Bereiche für alle diese Features sind global/Website/Benutzer. 
  
|**Feature**|**Parametername**|**Beschreibung**|**Standardeinstellung**|
|:-----|:-----|:-----|:-----|
|Aktivieren der Mobilität  <br/> |EnableMobility  <br/> |Steuert Benutzer in einem bestimmten Bereich, die Skype for Business mobilen Client installiert haben. Wenn die Richtlinie auf "False" festgelegt ist, können sich Ihre Benutzer nicht mit ihrem Client anmelden.  <br/> |Wahr  <br/> |
|Externe Sprachausgabe  <br/> |EnableOutsideVoice  <br/> |Ermöglicht benutzern die Verwendung von "Anruf über Arbeit", wodurch Benutzer Anrufe mithilfe ihrer Geschäftlichen Nummer anstelle ihrer Mobiltelefonnummer senden und empfangen können. Wenn der Wert auf "False" festgelegt ist, können Ihre Benutzer keine Anrufe auf ihrem Mobiltelefon tätigen oder empfangen, wenn sie ihre geschäftliche Telefonnummer verwenden.  <br/> |Wahr  <br/> |
|Ip-Audio und -Video aktivieren  <br/> |EnableIPAudioVideo  <br/> |Auf den Standardwert festgelegt, ermöglicht es einem Benutzer, VoIP zum Tätigen oder Empfangen von Telefon- oder Videoanrufen auf dem mobilen Gerät zu verwenden. Wenn der Wert auf "False" festgelegt ist, können Ihre Benutzer ihr mobiles Gerät nicht verwenden, um eine dieser Aktionen auszuführen.  <br/> |Wahr  <br/> |
|WLAN für IP-Audio anfordern  <br/> |RequireWiFiForIPAudio  <br/> |Definiert, ob ein Client Anrufe über VoIP über WLAN und nicht über ein Mobilfunknetz tätigen und empfangen muss. Wenn der Wert auf "True" festgelegt ist, können Ihre Benutzer nur VoIP-Anrufe tätigen und empfangen, wenn sie über WLAN verbunden sind.  <br/> |Falsch  <br/> |
|WLAN für IP-Video anfordern  <br/> |RequireWiFiForIPVideo  <br/> |Definiert, ob ein Client Videoanrufe über WLAN und nicht über ein Mobilfunknetz tätigen und empfangen muss. Wenn der Wert auf "True" festgelegt ist, können Ihre Benutzer nur VoIP-Anrufe tätigen und empfangen, wenn sie über WLAN verbunden sind.  <br/> |Falsch  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Sollten Benutzer, die nicht für Enterprise-VoIP aktiviert sind, mit "Click to Join" an Konferenzen teilnehmen können?

Damit Benutzer Zugriff auf Mobilitätsfeatures und "Anruf über Arbeit" haben, müssen sie für Enterprise-VoIP aktiviert sein. Aber auch wenn sie nicht aktiviert sind, können sie weiterhin an Konferenzen teilnehmen, indem sie auf einen Link auf ihrem mobilen Gerät klicken, aber nur, wenn ihnen eine entsprechende VoIP-Richtlinie zugewiesen ist. Sie können eine der folgenden Aktionen ausführen:
  
- diesen Benutzern eine bestimmte VoIP-Richtlinie zuweisen oder
    
- stellen Sie sicher, dass eine globale Richtlinie oder Richtlinie auf Standortebene vorhanden ist und für sie gilt.
    
In beiden Fällen müssen für die von Ihnen zugewiesene VoIP-Richtlinie PSTN-Verwendungseinträge und -routen vorhanden sein, die definieren, wo Ihre Benutzer ausgehende Anrufe für die Teilnahme an Konferenzen durchführen können.
  
> [!NOTE]
> Mobile Benutzer, die "Click to Join" verwenden möchten, benötigen eine VoIP-Richtlinie zusammen mit den zugehörigen PSTN-Verwendungsdatensätzen und VoIP-Routen, da ein ausgehender Anruf von Skype for Business Server das Ergebnis ist, wenn sie auf diesen Link auf ihren mobilen Geräten klicken. 

---
title: Planen der Mobilität für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planen Sie die Implementierung von Mobility for Skype for Business Server.
ms.openlocfilehash: 6452154db1047cfe91a7c8ceaf6ee6c63b94ee6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810075"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planen der Mobilität für Skype for Business Server
 
Planen Sie die Implementierung von Mobility for Skype for Business Server.
  
Mit Skype for Business Server können Sie die Mobilitätsfunktion bereitstellen, um Skype for Business Server auf mobilen Geräten bereitzustellen. Dieser Artikel enthält Details zum Mobilitätsfeature und hilft Ihnen bei der Planung Ihrer Bereitstellung.
  
Die Mobilitätsfunktion für Skype for Business Server kann mobile Clients für Skype for Business sowie Lync-Clients, die bis 2010 zurück gehen, unterstützen. Nach der Bereitstellung können Ihre Benutzer über unterstützte mobile iOS-, Android- und Windows Phone-Geräte eine Verbindung mit Ihrer Skype for Business Server-Bereitstellung herstellen, um verschiedene Features zu nutzen, einschließlich Enterprise-VoIP Features. Wir haben eine Teilliste unten hinzugefügt, und Sie können auch den Vergleich der Desktopclientfeatures [für Skype for Business](clients-and-devices/desktop-feature-comparison.md) überprüfen, um weitere Informationen zu erhalten:
  
- Senden und Empfangen von Nachrichten
    
- Anzeigen der Anwesenheit
    
- Kontakte anzeigen
    
- Klicken Sie, um an einer Konferenz teil zu nehmen
    
- Anruf über Arbeit
    
- Reichweite einzelner Nummern
    
- Voicemail
    
- Benachrichtigung über verpasste Anrufe
    
- VoIP (Voice over IP)
    
- Teilnehmervideo (H.264)
    
- Anzeigen von Besprechungsinhalten (PowerPoint und Desktop-/Anwendungsfreigabe)
    
All dies erfolgt über die Unified Communications-Web-API oder UCWA. UCWA wurde erstmals in Lync Server 2013 eingeführt und wird weiterhin für Skype for Business Server verwendet. Es gibt eine zusätzliche Funktionalität für die Kommunikation mit Lync 2010-Clients, und das ist Mobilitätsdienst (MCX). Dies sind kostenlose Dienste, mit denen Lync Server 2010- und 2013-Clients sowie Skype for Business-Clients erfolgreich auf Skype for Business Server-Bereitstellungen zugreifen können.
  
> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Es ist wichtig zu beachten, dass alle diese Features nach der Implementierung von Mobility zwar verfügbar sind, sie aber auf einigen Geräten möglicherweise etwas anders funktionieren. Wir haben eine Website, auf der erläutert wird, welche Features auf welchen Geräten funktionieren, im Vergleich der mobilen Clientfeatures [für Skype for Business.](clients-and-devices/mobile-feature-comparison.md) Außerdem finden Sie unter ["Plan for clients and devices"](clients-and-devices/clients-and-devices.md)einige großartige Informationen zu Geräten und Betriebssystemen.
  
Mobilität nutzt das AutoErmittlungsfeature, mit dem Clients skype for Business Server-Webdienste automatisch suchen können, ohne dass Benutzer URLs eingeben müssen (sie müssen sie nicht einmal kennen). Wenn Sie eine Problembehandlung durchführen müssen, wird die manuelle Eingabe von URLs weiterhin unterstützt.
  
Pushbenachrichtigungen werden auch unterstützt, wenn die Skype for Business-App nicht im Hintergrund ausgeführt wird (oder für mobile Geräte, die keine Anwendungen unterstützen, die im Hintergrund ausgeführt werden). Eine Pushbenachrichtigung wird an ein mobiles Gerät über ein Ereignis gesendet, das auftritt, wenn das Gerät oder die App inaktiv ist. Ein gutes Beispiel ist das Fehlen einer Nachrichtennachricht, wenn Ihr Telefon nicht aktiv ist, was dazu führen würde, dass eine Pushbenachrichtigung gesendet wird (dies wird als Popup oder Benachrichtigung angezeigt, z. B. wenn die App im Hintergrund ausgeführt wird). Bei Pushbenachrichtigungen verpassen Benutzer keine Im- oder Sprachanrufe.
  
Weitere Informationen finden Sie in den folgenden Abschnitten:
  
- [Mobilitätskomponenten](mobility.md#MobilityComponents)
    
- [Unterstützte Topologien](mobility.md#SupportedTopos)
    
- [Technische Anforderungen](mobility.md#TechRequirements)
    
- [Definieren Ihrer Mobilitätsanforderungen](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Mobilitätskomponenten
<a name="MobilityComponents"> </a>

Es gibt vier Dienste, die Mobility for Skype for Business Server umfassen:
  
- **Unified Communications Web API (UCWA)**
    
    Stellt Dienste für die Echtzeitkommunikation mit mobilen Clients und Webclients für Skype for Business Server zur Verfügung. Wenn Skype for Business Server bereitgestellt wird, wird ein virtuelles UCWA-Verzeichnis in den internen und externen Webdiensten erstellt. Eine virtuelle Komponente in diesem virtuellen Verzeichnis, die Anrufe von UCWA-fähigen Clients akzeptiert. Die Client-Apps kommunizieren über eine Representational State Transfer (REST)-Schnittstelle für:
    
  - Anwesenheit
    
  - contacts
    
  - Chat
    
  - VoIP
    
  - Videokonferenzen
    
  - Zusammenarbeit
    
    UCWA verwendet einen P-GET-basierten Kanal zum Senden von Ereignissen, z. B. eines eingehenden Anrufs, einer eingehenden Nachricht oder einer Nachricht an die Client-App.
    
- **Mobilitätsdienst (MCX)**
    
    Unterstützt Skype for Business Server-Funktionen, z. B. Chat, Anwesenheit und Kontakte, auf mobilen Geräten. Der Mobilitätsdienst wird auf jedem Front-End-Server in jedem Pool installiert, der die Skype for Business Server-Funktionalität auf mobilen Geräten unterstützen soll. Bei der Installation von Skype for Business Server 2015 wird ein neues virtuelles Verzeichnis (Mcx) unter den internen und externen Websites auf Ihren Front-End-Servern erstellt.
    
    > [!NOTE]
    > Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
- **AutoErmittlungsdienst**
    
    Identifiziert den Standort des Benutzers und ermöglicht mobilen Geräten und anderen Skype for Business-Clients, Ressourcen (z. B. die internen und externen URLs für Skype for Business Server-Webdienste, die Mcx-URL oder die UCWA-URL) unabhängig vom Netzwerkspeicherort zu finden. Die automatische Ermittlung verwendet hartcodierte Hostnamen (lyncdiscoverinternal für Benutzer innerhalb des Netzwerks, lyncdiscover für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers. Es unterstützt Clientverbindungen, die HTTP oder HTTPS verwenden. 
    
    Der AutoErmittlungsdienst wird auf jedem Front-End-Server und auf jedem Director in jedem Pool installiert, der die Skype for Business Server-Funktionalität auf mobilen Geräten unterstützen soll. Wenn Sie den Dienst installieren, wird ein neues virtuelles Verzeichnis (AutoErmittlung) sowohl auf den internen als auch auf externen Websites auf Ihren Front-End-Servern und Directors erstellt.
    
- **Pushbenachrichtigungsdienst**
    
    Ein cloudbasierter Dienst, der sich in Ihrem Skype for Business Online-Rechenzentrum befindet. Wenn auf Telefonen, auf denen der Skype for Business-Client nicht im Hintergrund ausgeführt wird, ein neues Ereignis eintritt, wird stattdessen eine Benachrichtigung über ein verpasstes Ereignis (als Pushbenachrichtigung bezeichnet) an das mobile Gerät gesendet. Der Mobilitätsdienst sendet eine Benachrichtigung an den Pushbenachrichtigungsdienst (Push Notification Service, MPNS), der sie dann an das mobile Gerät sendet. Der Benutzer kann dann auf die Benachrichtigung auf dem mobilen Gerät reagieren, um die App zu aktivieren. Für diese Funktionalität ist ein Edgeserver erforderlich.
    
## <a name="supported-topologies"></a>Unterstützte Topologien
<a name="SupportedTopos"> </a>

Wir haben die folgenden unterstützten Skype for Business Server-Anwendungen für Ihre Topologieplanung:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Sie sollten diese Funktion mit Skype for Business Server-Edgeservern oder Lync Server 2013-Edgeservern verwenden können.
  
Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, wenn er mit der Vermittlungsserverrolle und zwei Netzwerkschnittstellen verbunden ist. Sie müssen jedoch die entsprechenden Schritte ausführen, um diese Schnittstellen zu konfigurieren. Sie müssen der bestimmten Schnittstelle, die als Vermittlungsserver kommuniziert, und der Netzwerk-IP-Schnittstelle, die als Front-End-Server kommuniziert, IP-Adressen zuweisen. Sie können dies im Topologie-Generator tun, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die Standardauswahl "Alle konfigurierten **IP-Adressen verwenden" zu** verwenden.
  
## <a name="technical-requirements"></a>Technische Anforderungen
<a name="TechRequirements"> </a>

Es ist wichtig, die verschiedenen Szenarien für mobile Anwendungen zu planen, auf die Ihre mobilen Benutzer möglicherweise stoßen. Beispielsweise kann jemand außerhalb der Arbeit mit einer mobilen App beginnen, indem er sich über ein 3G-Netzwerk verbindet und dann zum Unternehmensnetzwerk Wi-Fi wechselt, wenn er zur Arbeit kommt. Sie können zu 4G wechseln, wenn sie das Gebäude verlassen. Wenn Sie jetzt planen, können Sie diese Netzwerkübergänge unterstützen und eine konsistente Benutzererfahrung gewährleisten.
  
### <a name="dns-configuration"></a>DNS-Konfiguration

Die Mobilitätsdienste Mcx und UCWA verwenden DNS auf die gleiche Weise. Bei der automatischen Ermittlung verwenden mobile Geräte DNS, um Ressourcen zu suchen. Während der DNS-Suche wurde versucht, eine Verbindung mit dem FQDN herzustellen, der dem internen DNS-Eintrag zugeordnet ist (lyncdiscoverinternal.[ interner Domänenname]). Wenn der interne DNS-Eintrag nicht verwendet werden kann, um diese Verbindung herzustellen, wird versucht, eine zweite Verbindung herzustellen, dieses Mal zum externen DNS-Eintrag (lyncdiscover.[ sipdomain]). Warum also zwei? Ein mobiles Gerät, das sich in Ihrem Netzwerk befinden, kann die interne AutoErmittlungs-URL verwenden. Externe mobile Geräte verwenden die externe AutoErmittlungs-URL. In beiden Fällen gibt der AutoErmittlungsdienst alle Webdienst-URLs für den Homepool des Benutzers zurück, der den Mobilitätsdienst (Mcx und UCWA) enthält.
  
Es wird erwartet, dass die externen AutoErmittlungsanforderungen den Reverseproxy durchgehen, den Sie für Skype for Business Server konfiguriert haben. Allerdings sind sowohl die interne Mobilitätsdienst-URL als auch die externe Mobilitätsdienst-URL dem externen Webdienste-FQDN zugeordnet. Aus diesem Grund stellt das Gerät unabhängig davon, ob es sich um ein internes oder externes Gerät in Ihrem Netzwerk handelt, immer eine externe Verbindung mit dem Skype for Business Server -Mobilitätsdienst über Ihren Reverseproxy herzustellen.
  
> [!NOTE]
> Wie bereits erwähnt, wird der sämtliche Datenverkehr des Mobilitätsdiensts (intern und extern) über Ihren Reverseproxy verarbeitet. Aber manchmal tritt ein Problem auf, wenn der interne Datenverkehr eine Schnittstelle durchlässt, nur um dann zu versuchen, auf derselben Schnittstelle wieder ein- und zurück zu kommen. Dies kann gegen Ihre Spoofing-Sicherheitsregeln (formell als TCP-Pakets spoofing bezeichnet) verstoßen. Sie müssen die Funktion "Hair **Pinning"** zulassen, um mobilitätsfunktion zu haben.
  
> [!NOTE]
> Wenn Sie dazu bereit sind, können Sie auch einen Reverseproxy verwenden, der von Ihrer Firewall getrennt ist (aus Sicherheitsgründen sollte spoofing prevention immer in Ihrer Firewall erzwungen werden). Auf diese Weise kann die Kehrkehre an der externen Schnittstelle des Reverseproxys statt an der externen Schnittstelle Ihrer Firewall auftreten. Auf diese Weise können Sie spoofing ordnungsgemäß in Ihrer Firewall erkennen, während Sie die Regel am Reverseproxy lockern und Ihre Mobilitätsfunktionen erhalten. 
  
> [!NOTE]
> Wenn Sie diese Route verwenden, verwenden Sie nach Möglichkeit den #A0 oder die CNAME-Einträge, um den Reverseproxy für das #A1 (nicht die Firewall) zu definieren. 
  
Es gibt einige Dinge, die Sie konfigurieren müssen, um Benutzer innerhalb und außerhalb Ihres Unternehmensnetzwerks zu unterstützen.
  
Dies sind die Regeln für interne und externe Web-FQDNs:
  
- Neue CNAME- oder A-DNS-Einträge (Host, wenn IPv6, AAAA) für die automatische Ermittlung.
    
- Neue Firewallregel, wenn Sie Pushbenachrichtigungen über Ihr Wi-Fi unterstützen möchten.
    
- Alternative Subject-Namen für interne Serverzertifikate und Reverseproxyzertifikate für die automatische Ermittlung.
    
- Die Konfiguration des Hardwarelastenausgleichs für den Front-End-Server ändert die Quellaffinität.
    
Dies sind die Topologieanforderungen, die zur Unterstützung des Mobilitätsdiensts und des AutoErmittlungsdiensts erforderlich sind:
  
- Der interne Web-FQDN des Front-End-Pools muss sich vom externen Web-FQDN des Front-End-Pools unterscheiden.
    
- Der interne Web-FQDN darf nur innerhalb des Unternehmensnetzwerks aufgelöst werden und kann von dort aus zugänglich sein.
    
- Der externe Web-FQDN darf nur in das Internet aufgelöst werden und kann über dieses zugegriffen werden.
    
- Für einen Benutzer innerhalb des Unternehmensnetzwerks muss die Mobilitätsdienst-URL an den externen Web-FQDN adressiert werden. Diese Anforderung gilt für den Mobilitätsdienst und gilt nur für diese URL.
    
- Für einen Benutzer außerhalb des Unternehmensnetzwerks muss die Anforderung an den externen Web-FQDN des Front-End-Pools oder Directors gehen.
    
Wenn Sie die automatische Ermittlung unterstützen, müssen Sie die folgenden DNS-Einträge für jede SIP-Domäne erstellen:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung von innerhalb des Unternehmensnetzwerks herstellen.
    
- Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen.
    
Die interne URL für die automatische Ermittlung sollte nicht von außerhalb Ihres internen Netzwerks adressierbar sein. Die externe automatische Ermittlungs-URL sollte nicht von innerhalb Ihres Netzwerks adressierbar sein. Wenn dies für die externe URL jedoch nicht möglich ist, ist dies wahrscheinlich nicht von der Funktionalität Ihres mobilen Clients betroffen, da die interne URL immer zuerst ausprobiert wird.
  
### <a name="port-and-firewall-requirements"></a>Port- und Firewallanforderungen

Den größten Teil davon haben wir in unserer anderen Dokumentation behandelt, aber speziell für Mobilität möchten Sie, dass die folgenden Ports in Ihrem Unternehmens-Wi-Fi-Netzwerk geöffnet sind, wenn Benutzer in einer Survivable Branch Appliance (SBA) zu hause sind:
  
- UcwaSipExternalListeningPort erfordert 5088.
    
- UcwaSipPrimaryListeningPort erfordert 5089.
    
### <a name="certificate-requirements"></a>Anforderungen für Zertifikate

Wenn Sie die automatische Ermittlung für Ihre mobilen Skype for Business-Clients verwenden, müssen Sie die San -Listen (alternativer Subject Name) für Ihre Zertifikate ändern, um sichere Verbindungen von Ihren mobilen Clients zu unterstützen. Wenn Sie bereits Zertifikate vorhanden haben, müssen Sie neue Zertifikate mit den hier beschriebenen SAN-Einträgen anfordern und zuweisen. Dies muss für jeden Front-End-Server und Director (falls in Ihrer Umgebung), auf dem der AutoErmittlungsdienst ausgeführt wird, durchgeführt werden. Es wird auch empfohlen, die San-San-Listen für Ihre Reverseproxyzertifikate zu ändern, indem Sie für jede SIP-Domäne in Ihrer Organisation SAN-Einträge hinzufügen.
  
Dies sollte ein einfacher Prozess sein, wenn Sie die neuen Zertifikate von einer internen Zertifizierungsstelle (Zertifizierungsstelle) anfordern. Öffentliche Zertifikate sind jedoch komplexer und potenziell viel teurer, um die Anforderung erneut anzustellen, ganz zu wissen, dass das Hinzufügen einer großen Anzahl von #A0 zu einem neuen öffentlichen Zertifikat sehr kostspielig sein kann. In diesem Fall gibt es einen Ansatz, der unterstützt, aber **nicht empfohlen wird.** Sie können Ihren Reverseproxy so konfigurieren, dass die anfängliche Anforderung des AutoErmittlungsdiensts über Port 80 ausgeführt wird, der HTTP anstelle von Port 443 verwendet, bei dem es sich um HTTPS handelt (und 443 die Standardkonfiguration ist). Diese eingehende Anforderung wird an Port 8080 in Ihrem Front-End-Pool oder Director umgeleitet. Dadurch müssen Sie keine Zertifikatänderungen vornehmen, da dieser Datenverkehr für Anforderungen kein HTTPS verwendet. Dies wird jedoch auch hier nicht empfohlen, obwohl es für Sie funktioniert.
  
### <a name="windows-and-iis-requirements"></a>Windows- und IIS-Anforderungen

Sie sollten über eine unterstützte Windows Server-Version für Ihre Skype for Business Server-Umgebung verfügen. Daher sollten Sie auch IIS 8 oder IIS 8.5 für Ihre Mobilitätsanforderungen haben. Es müssen einige Änderungen an den Standardeinstellungen ASP.NET werden, dies wird jedoch automatisch vom Installationsprogramm für den Mobilitätsdienst ausgeführt.
  
### <a name="hlb-requirements"></a>HlB-Anforderungen

Wenn Sie eine Topologie für Skype for Business Server verwenden, die einen HLB für Ihren Front-End-Pool enthält (bei der es sich um eine Topologie mit mehr als einem Front-End-Server geht), müssen die virtuellen IPs (VIPs) der externen Webdienste für webdienste-Datenverkehr für die Quelle konfiguriert werden. Die Quellaffinität trägt dazu bei, sicherzustellen, dass mehrere Verbindungen von einem einzelnen Client an denselben Server gesendet werden, um den Sitzungsstatus auf demselben Server zu verwalten.
  
Wenn Sie planen, mobile Skype for Business-Clients nur über Ihr internes Wi-Fi-Netzwerk zu unterstützen, sollten Sie Ihre internen Webdienste-VIPs für die Quelle konfigurieren, wie für externe ViPs der Webdienste beschrieben. In diesem Fall sollten Sie die source_addr (oder TCP)-Affinität für die internen #A0 auf dem HLB verwenden.
  
Ausführliche Informationen dazu finden Sie in der Dokumentation zu [lastenausgleichsanforderungen für Skype for Business.](network-requirements/load-balancing.md)
  
### <a name="reverse-proxy-requirements"></a>Reverseproxyanforderungen

Um die automatische Ermittlung für mobile Skype for Business-Clients zu unterstützen, müssen Sie die aktuelle Veröffentlichungsregel wie folgt aktualisieren:
  
- Wenn Sie die San-San-Listen für Ihre Reverseproxyzertifikate aktualisieren möchten und HTTPS für die anfängliche Anforderung des AutoErmittlungsdiensts verwenden, müssen Sie die Webveröffentlichungsregel für lyncdiscover \<sipdomain\> aktualisieren. Dies wird in der Regel mit der Veröffentlichungs-RUL für die externe Webdienste-URL im Front-End-Pool kombiniert.
    
- Wenn Sie sich entschieden haben, HTTP für die anfängliche AutoErmittlungsdienstanforderung zu verwenden, um zu vermeiden, dass die San-San-Liste für Ihre Reverseproxyzertifikate aktualisiert werden muss (was nicht empfohlen wird), müssen Sie eine neue Webveröffentlichungsregel für Port HTTP/TCP 80 erstellen, falls noch keine vorhanden ist. Wenn diese Regel vorhanden ist, aktualisieren Sie sie so, dass sie eine lyncdiscover enthält.\<sipdomain\> eintrag.
    
## <a name="defining-your-mobility-needs"></a>Definieren Ihrer Mobilitätsanforderungen
<a name="MobilityNeeds"> </a>

Nachdem wir nun die Topologien, Komponenten und technischen Anforderungen überprüft haben, sehen wir uns an, was Ihre Organisation im Hinblick auf eine Mobilitätsimplementierung möglicherweise benötigt.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Möchten Sie die automatische Ermittlung für mobile Skype for Business-Clients verwenden?

Es wird dringend empfohlen, die automatische Ermittlung zu verwenden. Es erfordert die Erstellung neuer interner und externer DNS-Einträge, wie im Abschnitt "Technische Anforderungen" oben beschrieben. Mit der automatischen Ermittlung können die Skype for Business-Clients skype for Business Server-Webdienste automatisch von einem beliebigen Speicherort aus suchen, ohne dass eine URL manuell eingegeben werden muss.
  
Sie können bei Bedarf manuelle Einstellungen verwenden. Diese URLs müssen von Benutzern auf ihren mobilen Geräten eingegeben werden:
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** für externen Zugriff.
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** für internen Zugriff.
    
Auch hier wird empfohlen, die automatische Ermittlung zu verwenden. Manuelle Einstellungen sind möglicherweise für Problembehandlungszwecke hilfreich.
  
### <a name="are-you-going-to-support-push-notifications"></a>Unterstützen Sie Pushbenachrichtigungen?

Pushbenachrichtigungen werden für mobile Anwendungen verwendet, die diese Funktionalität unterstützen, um einen Benutzer über Ereignisse zu benachrichtigen, während die App nicht aktiv ist. Ihr Edgeserver benötigt eine Verbundbeziehung mit Ihrem cloudbasierten Skype for Business Server-Pushbenachrichtigungsdienst, der sich im Skype for Business Online-Rechenzentrum befindet. Sie müssen ein Cmdlet ausführen, um Pushbenachrichtigungen zu aktivieren.
  
> [!NOTE]
> Wenn Noch-Benutzer Lync Server 2010-Clients verwenden, muss der Port 5223 von TCP ausgehend in Ihrem Unternehmens-WLAN geöffnet sein. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Möchten Sie, dass alle Benutzer auf alle Mobilitätsfeatures zugreifen, oder möchten Sie die Benutzer angeben, die stattdessen auf diese Features zugreifen können?

Wir haben eine Tabelle zur Unterstützung einiger features, die für alle Benutzer verfügbar sind, und ob sie auf diese Weise festgelegt sind oder nicht standardmäßig. Eine vollständige Liste finden Sie unter ["New-CsMobilityPolicy".](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)
  
> [!NOTE]
> Die Bereiche für alle diese Features sind "Global/Site/User". 
  
|**Funktion**|**Parametername**|**Beschreibung**|**Standardeinstellung**|
|:-----|:-----|:-----|:-----|
|Aktivieren der Mobilität  <br/> |EnableMobility  <br/> |Steuert Benutzer in einem bestimmten Bereich, auf denen der mobile Skype for Business-Client installiert ist. Wenn die Richtlinie auf "False" festgelegt ist, können sich die Benutzer nicht mit ihrem Client anmelden.  <br/> |Richtig  <br/> |
|Externe Sprachbefehle  <br/> |EnableOutsideVoice  <br/> |Ermöglicht einem Benutzer die Verwendung von "Über Arbeit anrufen", wodurch Benutzer Anrufe über ihre Telefonnummer und nicht über ihre Mobiltelefonnummer senden und empfangen können. Wenn der Wert auf "False" festgelegt ist, können Ihre Benutzer keine Anrufe auf ihrem Mobiltelefon mit ihrer Arbeitstelefonnummer machen oder empfangen.  <br/> |Richtig  <br/> |
|Aktivieren von IP-Audio und -Video  <br/> |EnableIPAudioVideo  <br/> |Der Standardwert ist festgelegt und ermöglicht einem Benutzer die Verwendung von VoIP zum Senden oder Empfangen von Telefon- oder Videoanrufen auf dem mobilen Gerät. Bei "False" können Ihre Benutzer keine dieser Dinge über ihr mobiles Gerät tun.  <br/> |Richtig  <br/> |
|WLAN für IP-Audio erforderlich  <br/> |RequireWiFiForIPAudio  <br/> |Definiert, ob ein Client Anrufe über VoIP über WLAN und nicht über ein Mobilfunknetz ein- und empfangen muss. Wenn "True" festgelegt ist, können Ihre Benutzer nur dann VoIP-Anrufe machen und empfangen, wenn sie über WLAN verbunden sind.  <br/> |False  <br/> |
|WLAN für IP Video erforderlich  <br/> |RequireWiFiForIPVideo  <br/> |Definiert, ob ein Client Videoanrufe über WLAN und nicht über ein Mobilfunknetz machen und empfangen muss. Wenn "True" festgelegt ist, können Ihre Benutzer nur dann VoIP-Anrufe machen und empfangen, wenn sie über WLAN verbunden sind.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Sollen Benutzer, die nicht für die Teilnahme Enterprise-VoIP die Option "Click to Join" verwenden können, um an Konferenzen teilzunehmen?

Damit Benutzer Zugriff auf Mobilitätsfeatures und "Anruf über Arbeit" haben, müssen sie für die Enterprise-VoIP. Aber auch wenn sie nicht aktiviert sind, können sie trotzdem an Konferenzen teilnehmen, indem sie auf einem Link auf ihrem mobilen Gerät klicken, aber nur, wenn ihnen eine entsprechende Richtlinie zugewiesen ist. Sie können eine der folgenden Aktionen ausführen:
  
- Weisen Sie diesen Benutzern eine bestimmte "Voice"-Richtlinie zu, oder
    
- Stellen Sie sicher, dass eine globale Richtlinie oder Richtlinie auf Standortebene vorhanden ist und auf sie angewendet wird.
    
In beiden Beiden Weisen muss die zugewiesene Sprachrichtlinie über PstN-Nutzungsdatensätze (Public Switched Telephone Network, Telefonnetz) und Routen verfügen, die definieren, an welchem Ort Ihre Benutzer sich auswählen können, um an Konferenzen teilzunehmen.
  
> [!NOTE]
> Mobile Benutzer, die click to Join verwenden möchten, benötigen eine Voicerichtlinie sowie die zugehörigen PSTN-Verwendungsdatensätze und -Routen, da ein ausgehender Anruf von Skype for Business Server das Ergebnis ist, wenn sie auf diesen Link auf ihren mobilen Geräten klicken. 
  


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
description: Planen Sie Ihre Implementierung von Mobility for Skype for Business Server.
ms.openlocfilehash: 5c33c88d13dd3720d1526c1620f852fe176a9750
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096641"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planen der Mobilität für Skype for Business Server
 
Planen Sie Ihre Implementierung von Mobility for Skype for Business Server.
  
Mit Skype for Business Server können Sie das Mobilitätsfeature bereitstellen, um Skype for Business Server-Funktionen auf mobilen Geräten bereitzustellen. Dieser Artikel enthält Details zum Mobilitätsfeature und hilft Ihnen bei der Planung Ihrer Bereitstellung.
  
Das Mobilitätsfeature für Skype for Business Server kann mobile Clients für Skype for Business sowie Lync-Clients unterstützen, die bis in das Jahr 2010 zurück gehen. Nach der Bereitstellung können Ihre Benutzer eine Verbindung mit Ihrer Skype for Business Server-Bereitstellung über unterstützte iOS-, Android- und Windows Phone-Mobilgeräte herstellen, um verschiedene Features zu nutzen, einschließlich Enterprise-VoIP Features. Nachfolgend finden Sie eine Teilliste, und Sie können auch den Vergleich der Desktopclientfeatures für [Skype for Business](clients-and-devices/desktop-feature-comparison.md) überprüfen, um weitere Informationen zu erhalten:
  
- Senden und Empfangen von Nachrichten
    
- Anzeigen von Anwesenheit
    
- Anzeigen von Kontakten
    
- Klicken Sie, um an einer Konferenz teil zu nehmen
    
- Anruf über die Arbeit
    
- Reichweite mit einer einzelnen Nummer
    
- Voicemail
    
- Benachrichtigung über verpasste Anrufe
    
- VoIP (Voice over IP)
    
- Teilnehmervideo (H.264)
    
- Anzeigen von Besprechungsinhalten (PowerPoint- und Desktop-/Anwendungsfreigabe)
    
All dies erfolgt über die Unified Communications Web API oder UCWA. UCWA wurde erstmals in Lync Server 2013 eingeführt und wird weiterhin für Skype for Business Server verwendet. Es gibt eine zusätzliche Funktionalität für die Kommunikation mit Lync 2010-Clients, und das ist Mobility Service (MCX). Dies sind kostenlose Dienste, mit denen Lync Server 2010- und 2013-Clients sowie Skype for Business-Clients erfolgreich auf Skype for Business Server-Bereitstellungen zugreifen können.
  
> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Es ist wichtig zu beachten, dass alle diese Features nach der Implementierung von Mobility zwar verfügbar sind, sie jedoch auf einigen Geräten möglicherweise etwas anders funktionieren. Wir haben eine Website, auf der erläutert wird, welche Features auf welchen Geräten funktionieren, unter [Mobile client feature comparison for Skype for Business](clients-and-devices/mobile-feature-comparison.md). Wir haben auch einige großartige Geräte- und Betriebssysteminformationen unter [Plan for clients and devices](clients-and-devices/clients-and-devices.md).
  
Mobilität nutzt das AutoErmittlungsfeature, mit dem Clients skype for Business Server-Webdienste automatisch suchen können, ohne dass Benutzer URLs eingeben müssen (sie müssen sie nicht einmal kennen). Wenn Sie eine Problembehandlung durchführen müssen, wird die manuelle Eingabe von URLs weiterhin unterstützt.
  
Pushbenachrichtigungen werden auch unterstützt, wenn die Skype for Business-App nicht im Hintergrund ausgeführt wird (oder für mobile Geräte, die keine Anwendungen unterstützen, die im Hintergrund ausgeführt werden). Eine Pushbenachrichtigung wird an ein mobiles Gerät über ein Ereignis gesendet, das auftritt, wenn das Gerät oder die App inaktiv ist. Ein gutes Beispiel ist das Fehlen einer Nachrichtennachricht, wenn Ihr Telefon nicht aktiv ist, was dazu führen würde, dass eine Pushbenachrichtigung gesendet wird (dies wird als Popup oder Benachrichtigung angezeigt, z. B. wenn die App im Hintergrund ausgeführt wird). Bei Pushbenachrichtigungen verpassen Benutzer keine Anrufnachrichten oder Sprachanrufe.
  
Weitere Informationen finden Sie in den folgenden Abschnitten:
  
- [Mobilitätskomponenten](mobility.md#MobilityComponents)
    
- [Unterstützte Topologien](mobility.md#SupportedTopos)
    
- [Technische Anforderungen](mobility.md#TechRequirements)
    
- [Definieren Ihrer Mobilitätsanforderungen](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Mobilitätskomponenten
<a name="MobilityComponents"> </a>

Es gibt vier Dienste, die Mobility for Skype for Business Server umfassen:
  
- **Unified Communications Web API (UCWA)**
    
    Stellt Dienste für die Echtzeitkommunikation mit mobilen und Webclients für Skype for Business Server zur Verfügung. Wenn Skype for Business Server bereitgestellt wird, wird ein virtuelles UCWA-Verzeichnis in den internen und externen Webdiensten erstellt. Eine virtuelle Komponente in diesem virtuellen Verzeichnis, die Anrufe von UCWA-fähigen Clients akzeptiert. Die Client-Apps kommunizieren über eine Representational State Transfer (REST)-Schnittstelle für:
    
  - Anwesenheit
    
  - contacts
    
  - Instant Messaging (Instant Messaging, Chat)
    
  - VoIP
    
  - Videokonferenzen
    
  - Zusammenarbeit
    
    UCWA verwendet einen P-GET-basierten Kanal zum Senden von Ereignissen, z. B. ein eingehender Anruf, eingehender Anruf oder eine Nachricht an die Client-App.
    
- **Mobilitätsdienst (Mobility Service, MCX)**
    
    Unterstützt Skype for Business Server-Funktionen, z. B. Chat, Anwesenheit und Kontakte, auf mobilen Geräten. Der Mobilitätsdienst wird auf jedem Front-End-Server in jedem Pool installiert, der die Skype for Business Server-Funktionalität auf mobilen Geräten unterstützen soll. Wenn Sie Skype for Business Server 2015 installieren, wird ein neues virtuelles Verzeichnis (Mcx) sowohl auf den internen als auch auf externen Websites auf Ihren Front-End-Servern erstellt.
    
    > [!NOTE]
    > McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
- **AutoErmittlungsdienst**
    
    Identifiziert den Standort des Benutzers und ermöglicht mobilen Geräten und anderen Skype for Business-Clients, Ressourcen (z. B. die internen und externen URLs für Skype for Business Server-Webdienste, die Mcx-URL oder die UCWA-URL) unabhängig vom Netzwerkspeicherort zu finden. Die automatische Ermittlung verwendet hartcodierte Hostnamen (lyncdiscoverinternal für Benutzer innerhalb des Netzwerks, lyncdiscover für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers. Es unterstützt Clientverbindungen, die HTTP oder HTTPS verwenden. 
    
    Der AutoErmittlungsdienst wird auf jedem Front-End-Server und jedem Director in jedem Pool installiert, der die Skype for Business Server-Funktionalität auf mobilen Geräten unterstützen soll. Wenn Sie den Dienst installieren, wird ein neues virtuelles Verzeichnis (AutoErmittlung) sowohl auf den internen als auch auf externen Websites auf Ihren Front-End-Servern und Directors erstellt.
    
- **Pushbenachrichtigungsdienst**
    
    Ein cloudbasierter Dienst, der sich in Ihrem Skype for Business Online-Rechenzentrum befindet. Auf Telefonen, auf denen der Skype for Business-Client nicht im Hintergrund ausgeführt wird, wird stattdessen eine Benachrichtigung über ein verpasstes Ereignis (als Pushbenachrichtigung bezeichnet) an das mobile Gerät gesendet. Der Mobilitätsdienst sendet eine Benachrichtigung an den Pushbenachrichtigungsdienst (Push Notification Service, MPNS), der sie dann an das mobile Gerät sendet. Der Benutzer kann dann auf die Benachrichtigung auf dem mobilen Gerät reagieren, um die App zu aktivieren. Für diese Funktionalität ist ein Edgeserver erforderlich.
    
## <a name="supported-topologies"></a>Unterstützte Topologien
<a name="SupportedTopos"> </a>

Wir haben die folgenden unterstützten Skype for Business Server-Anwendungen für Ihre Topologieplanung:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Sie sollten diese Funktionalität mit Skype for Business Server-Edgeservern oder Lync Server 2013-Edgeservern verwenden können.
  
Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, wenn er mit der Vermittlungsserverrolle und zwei Netzwerkschnittstellen verbunden ist. Sie müssen jedoch geeignete Schritte zum Konfigurieren dieser Schnittstellen ausführen. Sie müssen der bestimmten Schnittstelle, die als Vermittlungsserver kommuniziert, und der Netzwerk-IP-Schnittstelle, die als Front-End-Server kommuniziert, IP-Adressen zuweisen. Sie können dies im Topologie-Generator tun, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die Standardauswahl Alle konfigurierten **IP-Adressen verwenden zu** verwenden.
  
## <a name="technical-requirements"></a>Technische Anforderungen
<a name="TechRequirements"> </a>

Es ist wichtig, die verschiedenen Szenarien für mobile Anwendungen zu planen, auf die Ihre mobilen Benutzer möglicherweise stoßen. Beispielsweise kann jemand mit der Verwendung einer mobilen App außerhalb der Arbeit beginnen, indem er über ein 3G-Netzwerk eine Verbindung herstellen und dann zum Unternehmensnetzwerk Wi-Fi wechseln, wenn er zur Arbeit kommt. Sie können beim Verlassen ihres Gebäudes auf 4G umschalten. Mit der Planung können Sie diese Netzwerkübergänge unterstützen und eine konsistente Benutzererfahrung gewährleisten.
  
### <a name="dns-configuration"></a>DNS-Konfiguration

Die Mobilitätsdienste Mcx und UCWA verwenden DNS auf die gleiche Weise. Bei der automatischen Ermittlung verwenden mobile Geräte DNS, um Ressourcen zu finden. Während der DNS-Suche wurde versucht, eine Verbindung mit dem FQDN herzustellen, der dem internen DNS-Eintrag zugeordnet ist (lyncdiscoverinternal.[ interner Domänenname]). Wenn der interne DNS-Eintrag nicht zum Herstellen dieser Verbindung verwendet werden kann, wird eine zweite Verbindung versucht, dieses Mal mit dem externen DNS-Eintrag (lyncdiscover.[ sipdomain]). Warum also zwei? Ein mobiles Gerät, das in Ihrem Netzwerk intern ist, kann die interne AutoErmittlungs-URL verwenden. Externe mobile Geräte verwenden die externe AutoErmittlungs-URL. In beiden Fällen gibt der AutoErmittlungsdienst alle Webdienst-URLs für den Startpool des Benutzers zurück, einschließlich des Mobilitätsdiensts (Mcx und UCWA).
  
Es wird erwartet, dass die externen AutoErmittlungsanforderungen den Reverseproxy durchgehen, den Sie für Skype for Business Server konfiguriert haben. Allerdings sind sowohl die interne Mobilitätsdienst-URL als auch die externe Mobilitätsdienst-URL dem externen Webdienst-FQDN zugeordnet. Unabhängig davon, ob ein mobiles Gerät intern oder extern in Ihrem Netzwerk ist, stellt das Gerät daher immer eine externe Verbindung mit dem Skype for Business Server Mobility-Dienst über Ihren Reverseproxy ein.
  
> [!NOTE]
> Wie bereits erwähnt, wird der ganze Mobilitätsdienstdatenverkehr (intern und extern) über Ihren Reverseproxy ausgeführt. Manchmal tritt jedoch ein Problem auf, wenn der interne Datenverkehr eine Schnittstelle durchlässt, um dann zu versuchen, wieder auf derselben Schnittstelle ein- und zurück zu kommen. Dies kann gegen Ihre Spoofing-Sicherheitsregeln (formal wird sie als TCP-Pakets spoofing bezeichnet) verstoßen. Sie müssen zulassen, dass **hair pinning** die Mobilitätsfunktion hat.
  
> [!NOTE]
> Wenn Sie dazu bereit sind, können Sie auch einen Reverseproxy verwenden, der von Ihrer Firewall getrennt ist (aus Sicherheitsgründen sollte spoofing prevention immer in Ihrer Firewall erzwungen werden). Auf diese Weise kann die Haarnadel an der externen Schnittstelle Des Reverseproxys statt an der externen Schnittstelle Ihrer Firewall auftreten. Auf diese Weise können Sie das Spoofing an Ihrer Firewall richtig erkennen, während Sie die Regel am Reverseproxy lockern und Ihre Mobilitätsfunktionalität erhalten. 
  
> [!NOTE]
> Wenn Sie diese Route verwenden, verwenden Sie nach Möglichkeit den #A0 oder die #A1 zum Definieren des Reverseproxys für das Haarnadelverhalten (nicht die Firewall). 
  
Es gibt einige Dinge, die Sie konfigurieren müssen, um Benutzer innerhalb und außerhalb Ihres Unternehmensnetzwerks zu unterstützen.
  
Dies sind die Regeln für interne und externe Web-FQDNs:
  
- Neue CNAME- oder A-DNS-Einträge (Host, wenn IPv6, AAAA) für die automatische Ermittlung.
    
- Neue Firewallregel, wenn Sie Pushbenachrichtigungen über Ihr Netzwerk Wi-Fi möchten.
    
- Alternative Subject-Namen für interne Serverzertifikate und Reverseproxyzertifikate für die automatische Ermittlung.
    
- Die Konfiguration des Front-End-Servers für den Lastenausgleich ändert die Quellaffinität.
    
Dies sind die Topologieanforderungen, die für die Unterstützung des Mobilitätsdiensts und des AutoErmittlungsdiensts erforderlich sind:
  
- Der interne Web-FQDN des Front-End-Pools muss sich vom externen Web-FQDN des Front-End-Pools unterscheiden.
    
- Der interne Web-FQDN darf nur innerhalb des Unternehmensnetzwerks aufgelöst werden und kann von dort aus darauf zugreifen.
    
- Der externe Web-FQDN darf nur in das Internet aufgelöst werden und kann über dieses zugegriffen werden.
    
- Für einen Benutzer innerhalb des Unternehmensnetzwerks muss die Url des Mobilitätsdiensts an den externen Web-FQDN adressiert werden. Diese Anforderung gilt für den Mobilitätsdienst und gilt nur für diese URL.
    
- Für einen Benutzer außerhalb des Unternehmensnetzwerks muss die Anforderung an den externen Web-FQDN des Front-End-Pools oder Directors gehen.
    
Wenn Sie die automatische Ermittlung unterstützen, müssen Sie die folgenden DNS-Einträge für jede SIP-Domäne erstellen:
  
- Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Netzwerk Ihrer Organisation herstellen.
    
- Ein externer oder öffentlicher DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen.
    
Die interne url für die automatische Ermittlung sollte nicht von außerhalb Ihres internen Netzwerks adressierbar sein. Die externe url für die automatische Ermittlung sollte nicht innerhalb Ihres Netzwerks adressierbar sein. Wenn dies für die externe URL jedoch nicht möglich ist, wird dies wahrscheinlich nicht beeinträchtigt, da die interne URL immer zuerst ausprobiert wird.
  
### <a name="port-and-firewall-requirements"></a>Port- und Firewallanforderungen

Das meiste davon haben wir in unserer anderen Dokumentation behandelt, aber speziell für Mobilität möchten Sie, dass die folgenden Ports in Ihrem Unternehmens-Wi-Fi-Netzwerk geöffnet sind, wenn Sie Benutzer in einer Survivable Branch Appliance (SBA) haben:
  
- UcwaSipExternalListeningPort erfordert 5088.
    
- UcwaSipPrimaryListeningPort erfordert 5089.
    
### <a name="certificate-requirements"></a>Anforderungen für Zertifikate

Wenn Sie die automatische Ermittlung für Ihre mobilen Skype for Business-Clients verwenden, müssen Sie die SAN-Listen (alternativer Betreffname) in Ihren Zertifikaten ändern, um sichere Verbindungen von Ihren mobilen Clients zu unterstützen. Wenn Sie bereits über zertifikate verfügen, müssen Sie neue Zertifikate mit den hier beschriebenen SAN-Einträgen anfordern und zuweisen. Dies muss für jeden Front-End-Server und Director (falls in Ihrer Umgebung) ausgeführt werden, auf dem der AutoErmittlungsdienst ausgeführt wird. Außerdem wird empfohlen, die SAN-Listen für Ihre Reverseproxyzertifikate zu ändern und SAN-Einträge für jede SIP-Domäne in Ihrer Organisation zu hinzufügen.
  
Dies sollte ein unkomplizierter Prozess sein, wenn Sie die neuen Zertifikate von einer internen Zertifizierungsstelle (Zertifizierungsstelle) anfordern, aber öffentliche Zertifikate komplexer sind und möglicherweise viel kostspieliger für die erneute Anforderung sind, ganz zu schweigen davon, dass es möglicherweise kostspielig ist, einer neuen öffentlichen Zertifizierungsstelle viele #A0 hinzuzufügen. In dieser Situation gibt es einen Ansatz, der unterstützt, aber **nicht empfohlen wird.** Sie können Ihren Reverseproxy so konfigurieren, dass die anfängliche AutoErmittlungsdienstanforderung über Port 80 ausgeführt wird, der HTTP anstelle von Port 443 verwendet, was HTTPS (und 443 ist die Standardkonfiguration) ist. Diese eingehende Anforderung wird an Port 8080 in Ihrem Front-End-Pool oder Director umgeleitet. Dadurch müssen Sie keine Zertifikatänderungen vornehmen, da dieser Datenverkehr https für Anforderungen nicht verwendet. Dies wird jedoch auch hier nicht empfohlen, obwohl es für Sie funktioniert.
  
### <a name="windows-and-iis-requirements"></a>Windows- und IIS-Anforderungen

Sie sollten über eine unterstützte Windows Server-Version für Ihre Skype for Business Server-Umgebung verfügen. Daher sollten Sie auch IIS 8 oder IIS 8.5 für Ihre Mobilitätsanforderungen haben. Es müssen einige Änderungen an den Standardeinstellungen ASP.NET werden, aber das Installationsprogramm des Mobilitätsdiensts wird dies automatisch tun.
  
### <a name="hlb-requirements"></a>#A0

Wenn Sie eine Topologie für Skype for Business Server verwenden, die eine HLB für Ihren Front-End-Pool enthält (bei der es sich um eine Topologie mit mehreren Front-End-Servern handele), müssen die externen virtuellen #A0 (ViPs) für Webdienstedatenverkehr für die Quelle konfiguriert werden. Die Quellaffinität trägt dazu bei, sicherzustellen, dass mehrere Verbindungen von einem einzelnen Client an denselben Server gesendet werden, um den Sitzungsstatus zu erhalten.
  
Wenn Sie planen, mobile Skype for Business-Clients nur über Ihr internes Wi-Fi-Netzwerk zu unterstützen, sollten Sie Ihre internen Webdienst-VIPs für die Quelle konfigurieren, wie für externe Webdienst-VIPs beschrieben. In dieser Situation sollten Sie die source_addr (oder TCP)-Affinität für die internen Webdienst-VIPs auf der HLB verwenden.
  
Ausführliche Informationen zu all diesem Thema finden Sie in der Dokumentation zu Lastenausgleichsanforderungen [für Skype for Business.](network-requirements/load-balancing.md)
  
### <a name="reverse-proxy-requirements"></a>Reverseproxyanforderungen

Um die automatische Ermittlung für mobile Skype for Business-Clients zu unterstützen, müssen Sie die aktuelle Veröffentlichungsregel wie folgt aktualisieren:
  
- Wenn Sie die SAN-Listen für Ihre Reverseproxyzertifikate aktualisieren möchten und HTTPS für die anfängliche AutoErmittlungsdienstanforderung verwenden, müssen Sie die Webveröffentlichungsregel für lyncdiscover \<sipdomain\> aktualisieren. Dies wird in der Regel mit der Veröffentlichungs-Rul für die externe Webdienst-URL im Front-End-Pool kombiniert.
    
- Wenn Sie http für die anfängliche AutoErmittlungsdienstanforderung verwenden möchten, um zu vermeiden, dass die SAN-Liste für Ihre Reverseproxyzertifikate aktualisiert werden muss (was nicht empfohlen wird), müssen Sie eine neue Webveröffentlichungsregel für Port HTTP/TCP 80 erstellen, falls noch keines vorhanden ist. Wenn diese Regel vorhanden ist, aktualisieren Sie sie so, dass sie eine lyncdiscover enthält.\<sipdomain\> Eintrag.
    
## <a name="defining-your-mobility-needs"></a>Definieren Ihrer Mobilitätsanforderungen
<a name="MobilityNeeds"> </a>

Nachdem wir nun die Topologien, Komponenten und technischen Anforderungen überprüft haben, sehen wir uns an, was Ihre Organisation im Hinblick auf eine Mobilitätsimplementierung benötigen kann.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Möchten Sie die automatische Ermittlung für mobile Skype for Business-Clients verwenden?

Es wird dringend empfohlen, die automatische Ermittlung zu verwenden. Es erfordert die Erstellung neuer interner und externer DNS-Einträge, wie oben im Abschnitt Technische Anforderungen beschrieben. Mit der automatischen Ermittlung können die Skype for Business-Clients skype for Business Server-Webdienste automatisch von einem beliebigen Speicherort aus suchen, ohne dass eine URL manuell eingegeben werden muss.
  
Sie können bei Bedarf manuelle Einstellungen verwenden. Diese URLs müssen von Benutzern auf ihren mobilen Geräten eingegeben werden:
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root für** externen Zugriff.
    
- **https:// \<IntPoolFQDN\> /AutoDiscover/autodiscoverservice.svc/Root für** internen Zugriff.
    
Auch hier wird empfohlen, die automatische Ermittlung zu verwenden. Möglicherweise finden Sie manuelle Einstellungen, die zur Problembehandlung hilfreich sind.
  
### <a name="are-you-going-to-support-push-notifications"></a>Unterstützen Sie Pushbenachrichtigungen?

Pushbenachrichtigungen werden für mobile Anwendungen verwendet, die diese Funktionalität unterstützen, um einen Benutzer über Ereignisse zu benachrichtigen, während die App nicht aktiv ist. Ihr Edgeserver benötigt eine Verbundbeziehung mit Ihrem cloudbasierten Skype for Business Server-Pushbenachrichtigungsdienst, der sich im Skype for Business Online-Rechenzentrum befindet. Sie müssen ein Cmdlet ausführen, um Pushbenachrichtigungen zu aktivieren.
  
> [!NOTE]
> Wenn sie noch Lync Server 2010-Clients verwenden, benötigen sie den TCP-Port 5223, der ausgehend in Ihrem Unternehmens-WLAN-Netzwerk geöffnet ist. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Möchten Sie, dass alle Benutzer auf alle Mobilitätsfeatures zugreifen, oder möchten Sie die Benutzer angeben, die stattdessen auf diese Features zugreifen können?

Wir haben eine Tabelle, die ihnen bei einigen der Features hilft, die allen Benutzern zur Verfügung stehen, und ob sie standardmäßig so festgelegt sind oder nicht. Eine vollständige Liste finden Sie unter [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Die Bereiche für alle diese Features sind Global/Site/User. 
  
|**Feature**|**Parametername**|**Beschreibung**|**Standardeinstellung**|
|:-----|:-----|:-----|:-----|
|Aktivieren der Mobilität  <br/> |EnableMobility  <br/> |Steuert Benutzer in einem bestimmten Bereich, auf denen der mobile Skype for Business-Client installiert ist. Wenn die Richtlinie auf False festgelegt ist, können sich Ihre Benutzer nicht mit ihrem Client anmelden.  <br/> |Wahr  <br/> |
|Externe Sprachsteuerung  <br/> |EnableOutsideVoice  <br/> |Ermöglicht benutzern die Verwendung von Anrufen über die Arbeit, wodurch Benutzer Anrufe senden und empfangen können, indem sie ihre Arbeitsnummer anstelle ihrer Mobiltelefonnummer verwenden. Wenn sie auf False festgelegt ist, können Ihre Benutzer keine Anrufe auf ihrem Mobiltelefon über ihre Telefonnummer für ihre Arbeit machen oder empfangen.  <br/> |Wahr  <br/> |
|Aktivieren von IP-Audio und Video  <br/> |EnableIPAudioVideo  <br/> |Auf den Standardwert festgelegt, ermöglicht es einem Benutzer die Verwendung von VoIP zum Senden oder Empfangen von Telefon- oder Videoanrufen auf dem mobilen Gerät. Wenn sie auf False festgelegt sind, können Ihre Benutzer ihr mobiles Gerät nicht verwenden, um eines dieser Dinge zu tun.  <br/> |Wahr  <br/> |
|Wlan für IP-Audio benötigen  <br/> |RequireWiFiForIPAudio  <br/> |Definiert, ob ein Client Anrufe über VoIP über WLAN statt über ein Mobilfunkdatennetzwerk ein- und empfangen muss. Wenn sie auf True festgelegt ist, können Ihre Benutzer nur Dann VoIP-Anrufe machen und empfangen, wenn sie über WLAN verbunden sind.  <br/> |Falsch  <br/> |
|Wlan für IP-Video erforderlich  <br/> |RequireWiFiForIPVideo  <br/> |Definiert, ob ein Client Videoanrufe über WLAN statt über ein Mobilfunkdatennetzwerk machen und empfangen muss. Wenn sie auf True festgelegt ist, können Ihre Benutzer nur Dann VoIP-Anrufe machen und empfangen, wenn sie über WLAN verbunden sind.  <br/> |Falsch  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Sollen Benutzer, die nicht für die Enterprise-VoIP aktiviert sind, click to Join verwenden können, um an Konferenzen teilzunehmen?

Damit Benutzer Zugriff auf Mobilitätsfeatures und Anrufe über Die Arbeit haben, müssen sie für die Enterprise-VoIP. Aber auch wenn sie nicht aktiviert sind, können sie dennoch an Konferenzen teilnehmen, indem sie auf einem Link auf ihrem mobilen Gerät klicken, aber nur, wenn ihnen eine entsprechende Voicerichtlinie zugewiesen ist. Sie können eine der folgenden Aktionen ausführen:
  
- weisen Sie diesen Benutzern eine bestimmte Voicerichtlinie zu, oder,
    
- stellen Sie sicher, dass eine globale Richtlinie oder Richtlinie auf Standortebene vorhanden ist und auf sie angewendet wird.
    
So oder so muss die von Ihnen zugewiesene Voicerichtlinie über PstN-Nutzungsdatensätze (Public Switched Telephone Network) und Routen verfügen, mit denen definiert wird, wo Ihre Benutzer sich abwählen können, um an Konferenzen teilzunehmen.
  
> [!NOTE]
> Mobile Benutzer, die Click to Join verwenden möchten, benötigen eine Voicerichtlinie sowie die zugehörigen PSTN-Nutzungsdatensätze und Voicerouten, da ein ausgehender Anruf von Skype for Business Server das Ergebnis ist, wenn sie auf diesen Link auf ihren mobilen Geräten klicken. 

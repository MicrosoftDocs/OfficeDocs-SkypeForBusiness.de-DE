---
title: Planen der Mobilität für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Planen Sie Ihre Implementierung von Mobility für Skype for Business Server.
ms.openlocfilehash: 8b0ba8dd4ae07d3330a8ca722a1101c6b41a7cec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297323"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Planen der Mobilität für Skype for Business Server
 
Planen Sie Ihre Implementierung von Mobility für Skype for Business Server.
  
Mit Skype for Business Server können Sie die Mobilitäts Funktion bereitstellen, um die Funktionalität von Skype for Business Server auf mobilen Geräten bereitzustellen. Dieser Artikel enthält Details zur Mobilitäts Funktion und unterstützt Sie bei der Planung Ihrer Bereitstellung.
  
Das Mobilitätsfeature für Skype for Business Server kann Mobile Clients für Skype for Business sowie lync-Clients unterstützen, die zurück zu 2010 werden. Nach der Bereitstellung können Ihre Benutzer mit unterstützten IOS-, Android-und Windows Phone-mobilen Geräten eine Verbindung mit Ihrer Skype for Business Server-Bereitstellung herstellen, um verschiedene Funktionen, einschließlich Enterprise-VoIP-Funktionen, zu nutzen. Wir haben eine unvollständige Liste unten hinzugefügt, und Sie können auch den [Vergleich der Desktop-Client-Funktionen für Skype for Business](clients-and-devices/desktop-feature-comparison.md) für weitere Informationen überprüfen:
  
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
    
Bei allen diesen Funktionen kommt die Unified Communications-Web-API (UCWA) zum Einsatz. UCWA wurde erstmals in lync Server 2013 eingeführt und wird weiterhin für Skype for Business Server verwendet. Es gibt eine zusätzliche Funktionalität für die Kommunikation mit lync 2010-Clients, und das ist Mobility Service (MCX). Hierbei handelt es sich um ﻿kostenlose Dienste, die für lync Server 2010-und 2013-Clients sowie für Skype for Business-Clients für den erfolgreichen Zugriff auf Skype for Business Server-Bereitstellungen geeignet sind.
  
> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
Es ist wichtig zu beachten, dass diese Funktionen zwar verfügbar sind, sobald die Mobilität implementiert ist, aber auf einigen Geräten möglicherweise etwas anders funktionieren. Wir haben eine Website, die beschreibt, welche Funktionen an welchen Geräten funktionieren, und zwar beim [Vergleich der mobilen Clientfeatures für Skype for Business](clients-and-devices/mobile-feature-comparison.md). Wir verfügen auch über einige hervorragende Informationen zu Geräten und Betriebssystemen unter [Plan für Clients und Geräte](clients-and-devices/clients-and-devices.md).
  
Mobility nutzt die Auto Ermittlungsfunktion, die es Clients ermöglicht, Skype for Business Server-Webdienste automatisch zu finden, ohne dass Benutzer URLs eingeben müssen (Sie müssen Sie nicht einmal kennen). Für die Problembehandlung wird die manuelle Eingabe von URLs nach wie vor unterstützt.
  
Push-Benachrichtigungen werden ebenfalls unterstützt, wenn die Skype for Business-APP nicht im Hintergrund ausgeführt wird (oder bei mobilen Geräten, die Anwendungen nicht unterstützen, die im Hintergrund ausgeführt werden). Eine Push-Benachrichtigung wird an ein mobiles Gerät zu einem Ereignis gesendet, das auftritt, wenn das Gerät oder die APP inaktiv ist. Ein gutes Beispiel ist das Fehlen einer Chatnachricht, wenn Ihr Telefon nicht aktiv ist, was dazu führen würde, dass eine Push-Benachrichtigung gesendet wird (Dies wird als Popup oder Benachrichtigung angezeigt, wie wenn die APP im Hintergrund ausgeführt wird). Mit Push-Benachrichtigungen verpassen Benutzer keine Chat-oder Sprachanrufe.
  
Weitere Informationen haben wir in die folgenden Abschnitte unterteilt:
  
- [Mobilitätskomponenten](mobility.md#MobilityComponents)
    
- [Unterstützte Topologien](mobility.md#SupportedTopos)
    
- [Technische Anforderungen](mobility.md#TechRequirements)
    
- [Definieren der Mobilitätsanforderungen](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Mobilitätskomponenten
<a name="MobilityComponents"> </a>

Es gibt vier Dienste, die Mobilität für Skype for Business Server umfassen:
  
- **Unified Communications-Web-API (UCWA)**
    
    Bietet Dienste für die Echtzeitkommunikation mit mobilen und Webclients für Skype for Business Server. Wenn Skype for Business Server bereitgestellt wird, wird ein virtuelles UCWA-Verzeichnis in den internen und externen Webdiensten erstellt. Es handelt sich um eine virtuelle Komponente in diesem virtuellen Verzeichnis, die Anrufe von UCWA-fähigen Clients akzeptiert. Die Client-Apps kommunizieren zu folgenden Zwecken über eine REST-Schnittstelle (Representational State Transfer):
    
  - Anwesenheit
    
  - Kontakte
    
  - Chat
    
  - VoIP
    
  - Videokonferenzen
    
  - Zusammenarbeit
    
    UCWA verwendet einen P-GET-basierten Kanal, um Ereignisse zu senden, z. B. eingehende Anrufe, eingehende Sofortnachrichten oder Nachrichten für die Client-App.
    
- **Mobilitätsdienst (MCX)**
    
    Unterstützt die Funktionalität von Skype for Business Server wie Chat, Anwesenheit und Kontakte auf mobilen Geräten. Der Mobilitätsdienst ist auf jedem Front-End-Server in jedem Pool installiert, der die Skype for Business-Server Funktionalität auf mobilen Geräten unterstützen soll. Wenn Sie Skype for Business Server 2015 installieren, wird ein neues virtuelles Verzeichnis (MCX) unter den internen und externen Websites auf Ihren Front-End-Servern erstellt.
    
    > [!NOTE]
    > MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
- **AutoErmittlungsdienst**
    
    Identifiziert den Standort des Benutzers und ermöglicht es mobilen Geräten und anderen Skype for Business-Clients, Ressourcen (wie die internen und externen URLs für Skype for Business Server-Webdienste, die MCX-URL oder die UCWA-URL) unabhängig vom Netzwerkstandort zu finden. Für die automatische Ermittlung werden hartcodierte Hostnamen („lyncdiscoverinternal“ für Benutzer innerhalb des Netzwerks und „lyncdiscover“ für Benutzer außerhalb des Netzwerks) und die SIP-Domäne des Benutzers verwendet. Sowohl Clientverbindungen über HTTP als auch über HTTPS werden unterstützt. 
    
    Der AutoErmittlungsdienst ist auf jedem Front-End-Server und jedem Director in jedem Pool installiert, der die Skype for Business-Server Funktionalität auf mobilen Geräten unterstützen soll. Wenn Sie den Dienst installieren, wird ein neues virtuelles Verzeichnis (autodiscover) sowohl auf interner als auch auf externen Websites auf Ihren Front-End-Servern und-Directors erstellt.
    
- **Pushbenachrichtigungsdienst**
    
    Ein Cloud-basierter Dienst, der sich in Ihrem Skype for Business Online-Rechenzentrum befindet. Auf Smartphones, in denen Skype for Business-Client nicht im Hintergrund ausgeführt wird, wird, wenn ein neues Ereignis eintritt, die Benachrichtigung über ein verpasstes Ereignis (so genannte Push-Benachrichtigung) stattdessen an das Mobile Gerät gesendet. Der Mobilitätsdienst sendet eine Benachrichtigung an den Push Notification Service (MPNS), der Sie dann an das Mobile Gerät sendet. Der Benutzer kann dann auf seinem mobilen Gerät auf die Benachrichtigung reagieren und die App dadurch aktivieren. Für diese Funktion ist ein Edgeserver erforderlich.
    
## <a name="supported-topologies"></a>Unterstützte Topologien
<a name="SupportedTopos"> </a>

Wir haben die folgenden unterstützten Skype for Business Server-Anwendungen für Ihre Topologie-Planung:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
Sie sollten diese Funktion mit Skype for Business Server Edge-Servern oder lync Server 2013-Edgeserver verwenden können.
  
Der Mobilitätsdienst wird auf Front-End-Servern unterstützt, wenn er mit der Vermittlungs Server Rolle mit zwei Netzwerkschnittstellen verbunden ist, Sie müssen jedoch die entsprechenden Schritte zum Konfigurieren dieser Schnittstellen Unternehmen. Sie müssen der jeweiligen Schnittstelle, die als Vermittlungsserver kommuniziert, und der Netzwerk-IP-Schnittstelle, die als Front-End-Server kommuniziert, IP-Adressen zuweisen. Sie können dies im Topologie-Generator durchführen, indem Sie die richtige IP-Adresse für jeden Dienst auswählen, anstatt die Standardeinstellung **alle konfigurierte IP-Adressen verwenden zu verwenden** .
  
## <a name="technical-requirements"></a>Technische Anforderungen
<a name="TechRequirements"> </a>

Es ist wichtig, bei der Planung die verschiedenen Szenarien zu berücksichtigen, die sich im Zusammenhang mit mobilen Anwendungen für Ihre mobilen Benutzer ergeben können. Beispiel: Jemand verwendet privat eine mobile App über ein 3G-Netzwerk und wechselt dann am Arbeitsplatz zum Unternehmens-WLAN. Sie können beim Verlassen Ihres Gebäudes auf 4G umschalten. Wenn Sie jetzt entsprechend planen, können Sie diese Netzwerkübergänge unterstützen und für konsistente Benutzerfreundlichkeit sorgen.
  
### <a name="dns-configuration"></a>DNS-Konfiguration

Die Mobilitätsdienste MCX und UCWA verwenden DNS auf die gleiche Weise. Bei der AutoErmittlung suchen mobile Geräte mithilfe von DNS nach Ressourcen. Bei der DNS-Suche wird versucht, eine Verbindung mit dem FQDN herzustellen, der dem internen DNS-Eintrag zugeordnet ist („lyncdiscoverinternal.[interner Domänenname]“). Wenn der interne DNS-Eintrag nicht für die Verbindung verwendet werden kann, wird eine zweite Verbindung versucht, dieses Mal mit dem externen DNS-Eintrag („lyncdiscover.[SIP-Domäne]“). Warum zwei DNS-Einträge? Ein mobiles Gerät, das sich intern im Netzwerk befindet, kann die interne AutoErmittlungs-URL verwenden. Externe mobile Geräte verwenden die externe AutoErmittlungs-URL. In beiden Fällen gibt der AutoErmittlungsdienst alle Webdienst-URLs für den privaten Pool des Benutzers zurück, der den Mobilitätsdienst enthält (MCX und UCWA).
  
Es wird davon ausgegangen, dass die externen Auto Ermittlungsanforderungen den umgekehrten Proxy durchlaufen, den Sie für Skype for Business Server konfiguriert haben. Die URL für den internen Mobilitätsdienst und die URL für den externen Mobilitätsdienst sind jedoch mit dem FQDN der externen Webdienste verbunden. Unabhängig davon, ob ein mobiles Gerät intern oder extern für Ihr Netzwerk ist, stellt das Gerät über Ihren Reverse-Proxy immer eine Verbindung mit dem Skype for Business Server-Mobilitätsdienst extern her.
  
> [!NOTE]
> Wie bereits erwähnt, wird der gesamte Mobilitätsdienst-Datenverkehr (intern und extern) durch den Reverse-Proxy durchlaufen. Manchmal treten jedoch Probleme auf, wenn der interne Datenverkehr über eine Schnittstelle ausgeht und dann über die gleiche Schnittstelle wieder zurückfließen soll. Dies kann gegen Ihre Spoofingregeln (formell: Spoofing von TCP-Paketen) verstoßen. Sie müssen für die Beweglichkeit der **Haar Fixierung** sorgen.
  
> [!NOTE]
> Wenn Sie dazu bereit sind, können Sie auch einen umgekehrten Proxy verwenden, der von der Firewall getrennt ist (aus Sicherheitsgründen sollte Spoofing-Prävention immer in Ihrer Firewall erzwungen werden). Auf diese Weise kann die Haarnadel an der externen Schnittstelle Ihres Reverse-Proxys statt an der externen Schnittstelle der Firewall erfolgen. Auf diese Weise können Sie die Spoofing-Funktion in Ihrer Firewall richtig erkennen, während Sie die Regel beim Reverse-Proxy entspannen, und Sie erhalten Ihre Mobilitäts Funktionalität. 
  
> [!NOTE]
> Wenn Sie diesen Weg gehen, stellen Sie sicher, dass Sie den DNS-Host oder CNAME-Einträge verwenden, um den Reverseproxy für das Haarnadel-Verhalten (nicht für die Firewall) zu definieren, wenn dies möglich ist. 
  
Sie müssen einige Aspekte konfigurieren, um Benutzer innerhalb und außerhalb des Unternehmensnetzwerks zu unterstützen.
  
Für interne und externe Web-FQDNs gelten die folgenden Regeln:
  
- Neue CNAME- oder A-Einträge (Host für IPv6: AAAA) für die automatische Ermittlung
    
- Neue Firewallregel, wenn Pushbenachrichtigungen über das WLAN-Netzwerk unterstützt werden sollen
    
- Sie können alternative Namen für interne Serverzertifikate und Reverse-Proxy Zertifikate für die automatische Ermittlung untersuchen.
    
- Die Konfiguration der Front-End-Server-Hardware Lastenausgleich ändert die Quell Affinität.
    
Dies sind die Topologie-Anforderungen, die für die Unterstützung des mobilitätsdiensts und des AutoErmittlungsdiensts erforderlich sind:
  
- Der interne Web-FQDN des Front-End-Pools muss sich vom externen Web-FQDN des Front-End-Pools unterscheiden.
    
- Auf den internen Web-FQDN darf nur von innerhalb des Unternehmensnetzwerks zugegriffen werden, und er darf nur in eine Unternehmensnetzwerkadresse aufgelöst werden.
    
- Auf den externen Web-FQDN darf nur vom Internet aus zugegriffen werden, und er darf nur in eine Internetadresse aufgelöst werden.
    
- Für einen Benutzer innerhalb des Unternehmensnetzwerks muss die URL des mobilitätsdiensts an den FQDN des externen Webdiensts adressiert sein. Diese Anforderung gilt für den Mobilitätsdienst und gilt nur für diese URL.
    
- Für einen Benutzer außerhalb des Unternehmensnetzwerks muss die Anforderung zum externen Web-FQDN des Front-End-Pools oder Directors wechseln.
    
Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:
  
- Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen
    
- Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen
    
Die interne AutoErmittlungs-URL sollte nicht von außerhalb des internen Netzwerks adressierbar sein. Die externe AutoErmittlungs-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn dies für die externe URL nicht möglich ist, wird dies die Funktionen der mobilen Clients vermutlich nicht beeinträchtigen, da immer zuerst versucht wird, eine Verbindung mit der internen URL herzustellen.
  
### <a name="port-and-firewall-requirements"></a>Port- und Firewallanforderungen

Wir haben die meisten dieser Informationen in unserer anderen Dokumentation behandelt, aber speziell für die Mobilität werden Sie die folgenden Ports in Ihrem Enterprise Wi-Fi-Netzwerk öffnen möchten, wenn sich Benutzer auf einer Survivable Branch Appliance (SBA) befinden:
  
- Für „UcwaSipExternalListeningPort“ wird Port 5088 benötigt.
    
- Für „UcwaSipPrimaryListeningPort“ wird Port 5089 benötigt.
    
### <a name="certificate-requirements"></a>Zertifikatanforderungen

Wenn Sie die automatische Ermittlung für Ihre mobilen Skype for Business-Clients verwenden, müssen Sie die Listen San (Subject Alternative Name) für Ihre Zertifikate ändern, um sichere Verbindungen von ihren mobilen Clients zu unterstützen. Wenn bereits Zertifikate vorhanden sind, müssen Sie neue Zertifikate mit den hier beschriebenen SAN-Einträgen anfordern und zuweisen. Dies muss für jeden Front-End-Server und Director (falls in Ihrer Umgebung) erfolgen, auf dem der AutoErmittlungsdienst ausgeführt wird. Darüber hinaus empfiehlt es sich, die San-Listen für Ihre Reverse-Proxy Zertifikate zu ändern und San-Einträge für jede SIP-Domäne in Ihrer Organisation hinzuzufügen.
  
Dies sollte ein einfacher Vorgang sein, wenn Sie die neuen certs von einer internen Zertifizierungsstelle (Zertifizierungsstelle) anfordern, öffentliche Zertifikate aber komplexer sind und möglicherweise viel teurer sind, um Sie erneut anzufordern, ganz zu schweigen davon, dass es kostspielig ist, viel SIP hinzuzufügen. Domänen zu einem neuen öffentlichen Zertifikat hinzu. In dieser Situation gibt es einen Ansatz, der unterstützt wird, aber **nicht empfohlen**wird. Sie können Ihren Reverse-Proxy so konfigurieren, dass die ursprüngliche AutoErmittlungsdienst Anforderung über Port 80, die HTTP verwendet, statt Port 443, also https (und 443 ist die Standardkonfiguration), erfolgt. Diese eingehende Anforderung wird an Port 8080 im Front-End-Pool oder Director umgeleitet. Auf diese Weise müssen Sie keine Zertifikat Änderungen vornehmen, da dieser Datenverkehr nicht HTTPS für Anforderungen verwendet. Wir empfehlen dies aber noch einmal nicht, auch wenn es für Sie funktionieren wird.
  
### <a name="windows-and-iis-requirements"></a>Anforderungen im Hinblick auf Windows und IIS

Für Ihre Skype for Business Server-Umgebung sollten Sie über eine unterstützte Windows Server-Version verfügen. Daher benötigen Sie für Mobilitätsfunktionen auch IIS 8 oder IIS 8.5. Es müssen einige Änderungen an den standardmäßigen ASP.NET-Einstellungen vorgenommen werden, aber das Mobilitätsdienst-Installationsprogramm führt dies automatisch aus.
  
### <a name="hlb-requirements"></a>HLB-Anforderungen

Wenn Sie eine Topologie für Skype for Business Server verwenden, die eine HLB für Ihren Front-End-Pool umfasst (bei der es sich um eine Topologie mit mehr als einem Front-End-Server handelt), müssen die externen Web Services Virtual IPS (VIPs) für Webdienste-Datenverkehr konfiguriert sein. für Quelle. Die Quellaffinität stellt sicher, dass mehrere Verbindungen von einem einzelnen Client an einen einzigen Server gesendet werden, um den Sitzungsstatus aufrechtzuerhalten.
  
Wenn Sie beabsichtigen, Skype for Business Mobile-Clients nur über Ihr internes WLAN-Netzwerk zu unterstützen, sollten Sie Ihre internen Webdienste-VIPs für Source so konfigurieren, wie dies für externe Webdienste-VIPs beschrieben ist. In diesem Fall sollten Sie die source_addr (oder TCP)-Affinität für die internen Webdienste-VIPs auf der HLB verwenden.
  
Ausführlichere Informationen hierzu finden Sie in der Dokumentation zu [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md).
  
### <a name="reverse-proxy-requirements"></a>Anforderungen an den Reverseproxy

Um die automatische Ermittlung für Skype for Business Mobile-Clients zu unterstützen, müssen Sie die aktuelle Veröffentlichungsregel wie folgt aktualisieren:
  
- Wenn Sie sich entschließen, die San-Listen auf Ihren Reverse-Proxy Zertifikaten zu aktualisieren, und Sie HTTPS für die ursprüngliche AutoErmittlungsdienst Anforderung verwenden, müssen Sie die Webveröffentlichungsregel für lyncdiscover aktualisieren. \<sipdomain\>. Dies wird in der Regel mit dem Veröffentlichungs-rul für die externe Webdienst-URL im Front-End-Pool kombiniert.
    
- Wenn Sie sich entschieden haben, http für die ursprüngliche AutoErmittlungsdienst Anfrage zu verwenden, um zu vermeiden, dass Sie die San-Liste für Ihre Reverse-Proxy Zertifikate aktualisieren müssen (was wir nicht empfehlen), müssen Sie eine neue Webveröffentlichungsregel für Port http/TCP 80 erstellen, wenn keine vorhanden ist. bereits. Wenn diese Regel vorhanden ist, aktualisieren Sie Sie so, dass Sie eine lyncdiscover enthält. \<sipdomain\> -Eintrag.
    
## <a name="defining-your-mobility-needs"></a>Definieren der Mobilitätsanforderungen
<a name="MobilityNeeds"> </a>

Nachdem wir nun die Topologien, Komponenten und technischen Anforderungen überprüft haben, sehen wir uns an, was Ihre Organisation in Bezug auf eine Mobilitäts Implementierung möglicherweise benötigt.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Möchten Sie für mobile Skype for Business-Clients die automatische Ermittlung verwenden?

Wir empfehlen dringend, die automatische Ermittlung zu verwenden. Dazu müssen Sie wie weiter oben unter „Technische Anforderungen“ beschrieben neue interne und externe DNS-Einträge erstellen. Bei der automatischen Ermittlung können die Skype for Business-Clients Skype for Business Server-Webdienste automatisch von einem beliebigen Standort aus finden, ohne dass eine URL manuell eingegeben werden muss.
  
Wenn Sie möchten, können Sie manuelle Einstellungen verwenden. Die Benutzer müssen dann auf ihren mobilen Geräten die folgenden URLs eingeben:
  
- **https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root** für externen Zugriff.
    
- **https://\<IntPoolFQDN\>/autodiscover/autodiscoverservice.svc/root** für den internen Zugriff.
    
Wir möchten nochmals betonen, dass wir die automatische Ermittlung empfehlen. Manuelle Einstellungen können jedoch bei der Problembehandlung hilfreich sein.
  
### <a name="are-you-going-to-support-push-notifications"></a>Möchten Sie Pushbenachrichtigungen unterstützen?

Pushbenachrichtigungen werden für mobile Anwendungen verwendet, die diese Funktionalität unterstützen, um Benutzer über Ereignisse zu benachrichtigen, wenn die App gerade nicht aktiv ist. Ihr Edgeserver muss über eine Verbundbeziehung zu Ihrem Cloud-basierten Skype for Business Server-Push-Benachrichtigungsdienst verfügen, der im Skype for Business Online-Rechenzentrum zu finden ist. Um Pushbenachrichtigungen zu aktivieren, müssen Sie ein Cmdlet ausführen.
  
> [!NOTE]
> Wenn Sie noch über eine andere Person mit lync Server 2010-Clients verfügen, benötigt Sie TCP-Port 5223, der in Ihrem WLAN-Netzwerk für Unternehmen geöffnet ist. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Möchten Sie, dass alle Benutzer auf alle Mobilitätsfeatures zugreifen, oder möchten Sie die Benutzer angeben, die stattdessen auf diese Features zugreifen können?

Wir verfügen über eine Tabelle, die Ihnen bei einigen der Features helfen kann, die für alle Benutzer verfügbar sind, und ob Sie auf diese Weise oder nicht standardmäßig festgelegt sind. Die vollständige Liste finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Alle diese Funktionen gelten global, für bestimmte Standorte oder für bestimmte Benutzer. 
  
|**Funktion**|**Parametername**|**Beschreibung**|**Standardeinstellung**|
|:-----|:-----|:-----|:-----|
|Mobilität aktivieren  <br/> |EnableMobility  <br/> |Steuert Benutzer in einem bestimmten Bereich, auf dem Skype for Business Mobile-Client installiert ist. Wenn die Richtlinie auf „False“ festgelegt ist, können sich die Benutzer nicht mit ihrem Client anmelden.  <br/> |True  <br/> |
|Externe Anrufe  <br/> |EnableOutsideVoice  <br/> |Ermöglicht Benutzern die Verwendung der Funktion „Geschäftlich anrufen“, das heißt, die Benutzer können Anrufe unter ihrer geschäftlichen Telefonnummer anstelle ihrer Mobiltelefonnummer tätigen und empfangen. Wenn „False“ festgelegt ist, können die Benutzer auf ihren Mobiltelefonen nicht über die geschäftliche Telefonnummer Anrufe tätigen oder empfangen.  <br/> |True  <br/> |
|IP-Audio und -Video aktivieren  <br/> |EnableIPAudioVideo  <br/> |Wenn der Standardwert festgelegt ist, können Benutzer auf mobilen Geräten über VoIP Sprach- oder Videoanrufe tätigen oder empfangen. Wenn die Einstellung auf „False“ festgelegt ist, können die Benutzer auf ihren mobilen Geräten keine dieser Funktionen nutzen.  <br/> |True  <br/> |
|Wi-Fi für IP-Audio erforderlich  <br/> |RequireWiFiForIPAudio  <br/> |Definiert, ob VoIP-Anrufe in Clients über das WLAN anstatt über das Mobilfunknetz getätigt oder empfangen werden. Wenn „True“ festgelegt ist, können die Benutzer nur dann VoIP-Anrufe tätigen und empfangen, wenn sie mit einem WLAN verbunden sind.  <br/> |Falsch  <br/> |
|Wi-Fi für IP-Video erforderlich  <br/> |RequireWiFiForIPVideo  <br/> |Definiert, ob Videoanrufe in Clients über das WLAN anstatt über das Mobilfunknetz getätigt oder empfangen werden. Wenn „True“ festgelegt ist, können die Benutzer nur dann VoIP-Anrufe tätigen und empfangen, wenn sie mit einem WLAN verbunden sind.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Sollen Benutzer, die nicht für Enterprise-VoIP aktiviert sind, an Konferenzen teilnehmen können, indem sie auf den entsprechenden Teilnahmelink klicken?

Damit Benutzer Zugriff auf Mobilitätsfunktionen haben und über die Arbeit anrufen können, müssen Sie für Enterprise-VoIP aktiviert sein. Auch wenn Sie nicht aktiviert sind, können Sie weiterhin an Konferenzen teilnehmen, indem Sie auf Ihrem mobilen Gerät auf einen Link klicken, aber nur, wenn Ihnen eine entsprechende VoIP-Richtlinie zugewiesen ist. Sie können eine der folgenden Aktionen ausführen:
  
- Sie weisen diesen Benutzern eine bestimmte VoIP-Richtlinie zu, oder
    
- Sie stellen sicher, dass eine globale Richtlinie oder eine Richtlinie auf Standortebene vorhanden ist, die für diese Benutzer gilt.
    
In jedem Fall muss die zugewiesene VoIP-Richtlinie über PSTN-Verwendungseinträge und -Routen verfügen. Diese definieren die Bereiche, in die Benutzer hinauswählen können, um an einer Konferenz teilzunehmen.
  
> [!NOTE]
> Mobile Benutzer, die Click-to-Join verwenden möchten, benötigen eine VoIP-Richtlinie zusammen mit den zugehörigen PSTN-Nutzungsdaten Sätzen und VoIP-Routen, denn wenn Sie auf Ihren mobilen Geräten auf diesen Link klicken, ist ein ausgehender Anruf von Skype for Business Server das Ergebnis. 
  


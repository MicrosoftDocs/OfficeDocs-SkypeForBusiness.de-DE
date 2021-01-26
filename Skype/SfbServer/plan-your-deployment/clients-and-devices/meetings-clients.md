---
title: Planen von Besprechungsclients (Web App und Besprechungs-App)
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
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
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Zusammenfassung: WÄHREND der Planung für Skype for Business Server sollten die Supportanforderungen für die Skype for Business Web App und die Skype-Besprechungs-App überprüft werden. Dieser Artikel richtet sich nicht an die Benutzer dieser Apps.'
ms.openlocfilehash: 4956a11c0ed163cbe50c49233e9aa05a0fbbd872
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826015"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planen von Besprechungsclients (Web App und Besprechungs-App)
 
**Zusammenfassung:** WÄHREND der Planung für Skype for Business Server sollten die Supportanforderungen für die Skype for Business Web App und die Skype-Besprechungs-App überprüft werden. Dieser Artikel richtet sich nicht an die Benutzer dieser Apps.
  
Nachdem Sie Skype for Business Server implementiert haben, wird den Benutzern Ihrer Organisation vermutlich der Skype for Business-Client im Rahmen des Bereitstellungsprozesses installiert. 
  
Später können diese Benutzer Besprechungen erstellen und Benutzer von außerhalb der Organisation einladen, und diese Besprechungsteilnehmer verfügen möglicherweise über keine Version des Skype for Business-Clients. Wenn diese Benutzer auf die URL für die Besprechungs-Einladung klicken, wird das Fehlen eines Clients erkannt, und der eingeladene Benutzer ohne Skype for Business-Client wird aufgefordert, einen einfachen Client nur für Besprechungen herunterzuladen und zu installieren, damit er an der Besprechung teilnehmen kann.
  
> [!NOTE]
> Die Skype for Business Web App und die Skype-Besprechungs-App sind nur verfügbar, wenn Sie versuchen, sich bei einer Besprechung ohne Skype for Business zu anmelden. Die Benutzerhilfe für diese Apps finden Sie unter [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> Sie können weder die Skype for Business Web App noch [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) die Skype-Besprechungs-App vorab installieren, Aber Smartphone- und Tablet-Benutzer können möglicherweise kostengünstige mobile Clients installieren, die sie für die Teilnahme an Besprechungen verwenden können. [](https://products.office.com/skype-for-business/download-app?tab=tabs-2)
  
Standardmäßig leitet der Server, der die Besprechung hosten, den Benutzer an, Skype for Business Web App herunterzuladen und zu installieren, um an der Besprechung teil zu nehmen. Die Skype for Business Web App wird auf dem Front-End-Server gespeichert und an den Besprechungsteilnehmer gesendet. 
  
For Skype for Business Server, Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac) are available as replacements for Skype for Business Web App beginning with CU5, but providing the replacement apps requires the additional configuration described in [Enable Skype Meetings App to replace Skype for Business Web App (Optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Wenn die Skype-Besprechungs-App und Skype for Business für Mac aktiviert sind, laden Benutzer die neueste Version der Apps aus dem Microsoft 365- oder Office 365 Content Delivery Network (CDN) und nicht von Ihrem Skype for Business-Server herunter. Für Skype for Business Server 2019 ist die Verwendung der Skype-Besprechungs-App und Skype for Business für Mac die einzige Option.
  
Die Skype-Besprechungs-App bietet eine vereinfachte Browsererfahrung zum Herunterladen und Installieren der App sowie zum Beitreten zu Besprechungen, einschließlich der Teilnahme per Mausklick für Benutzer von Internet Explorer. Die Skype-Besprechungs-App bietet außerdem viele Verbesserungen gegenüber der Skype for Business Web App für Zuverlässigkeit und Besprechungserfahrung. 
  
> [!NOTE]
> Ab Skype for Business Server 2015 CU5 oder höher senden Besprechungen, die mit Skype for Business Online abgehalten werden, einem clientlosen Benutzer nicht mehr die Skype for Business Web App, sondern stattdessen die Skype-Besprechungs-App (unter Windows) oder Skype for Business für Mac (auf dem Mac). Wenn Sie ab Skype for Business Server 2015 CU5 oder höher skype for Business Web App als Ersatz für [Skype for Business Web App aktivieren (optional),](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)erhalten clientlose Benutzer die Skype-Besprechungs-App oder Skype for Business für Mac anstelle von Skype for Business Web App. 
  
## <a name="software-requirements"></a>Softwareanforderungen
<a name="OS-Browser"> </a>

Um die Skype for Business Web App verwenden zu können, muss ein Benutzer über eine der folgenden unterstützten Kombinationen aus Betriebssystem und Browser verfügen. 
  
**Betriebssystem und minimale Browserunterstützung für Skype for Business Web App**

| Betriebssystem | Microsoft Edge | 32- und 64-Bit-Internet Explorer 11 oder höher | 32- und 64-Bit-Internet Explorer 10 oder höher | 32- und 64-Bit-Internet Explorer 9 oder höher | 32- und 64-Bit-Version von Safari 6.2.8 - 11.X | 32- und 64-Bit-Version von Chrome 18.X oder höher |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Ja  <br/> |Ja  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja &#x2778; <br/> |
|Windows 8.1-&#x2776; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend <br/> |Ja &#x2778; <br/> |
|Windows 8 (Intel-basierte) &#x2776; <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nicht zutreffend <br/> |Nicht zutreffend  <br/> |Ja &#x2778; <br/> |
|Windows 7 mit SP1 &#x2777; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nicht zutreffend <br/>|Ja &#x2778; <br/> |
|Windows Server 2008 R2 mit SP1-&#x2777; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nicht zutreffend <br/>|Ja &#x2778; <br/> |
|macOS 10.8 und höher (Intel-basiert) &#x2777; <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Ja <br/> |
   
&#x2776; Das Skype for Business Web App-Browser-Plug-In erfordert ein bestimmtes Freigabe-Plug-In, um computerbasierte Sprach-, Video-, Freigabe- und Anzeigefunktionen der laufenden Bildschirmfreigabe und anderer Funktionen zu verwenden. Einem Besprechungsteilnehmer wird die Möglichkeit gegeben, das Freigabe-Plug-In zu installieren, wenn er der Besprechung beitritt oder eine dieser Features initiiert. Auf Windows 8 und Windows 8.1 kann das Freigabe-Plug-In nur installiert werden, wenn Sie Internet Explorer 10 oder Internet Explorer 11 für den Desktop ausführen. Diese Features sind nicht für Nicht-Desktop-Versionen von Internet Explorer 10 11 verfügbar. Beachten Sie, dass Firefox und Safari, Version 12.0 und höher, nicht mehr unterstützt werden.
  
&#x2777; Unter den unterstützten Betriebssystemen Windows 7, Windows Server 2008 R2 und Macintosh sind alle Funktionen verfügbar, einschließlich computerbasierter Sprach-, Video-, Anwendungsanzeige, Anwendungsfreigabe, Desktopanzeige und Desktopfreigabe. Um diese Features verwenden zu können, müssen Sie ein Plug-In installieren, wenn Sie dazu aufgefordert werden. Beachten Sie, dass Mac OS X, Version 10.7, nicht mehr unterstützt wird.  Beachten Sie außerdem, dass die Web App nicht unter OS X 10.15 oder höher installiert wird.  Es wird empfohlen, die neueste Version von Skype for Business für Mac zu verwenden, die szenarien für anonyme Teilnahmen in Zukunft unterstützt.
  
&#x2778; Zugriff auf die Web App über Chrome unter Windows wird ein kleines Programm gestartet, das die Web App in einen eingebetteten Internet -Explorer-Frame lädt. Für dieses Programm muss eine der unterstützten Versionen von Internet Explorer installiert sein, damit die Web App ordnungsgemäß geladen wird.
  
> [!NOTE]
> Microsoft 365- und Office 365-Benutzer können Internet Explorer 10 oder höher mit Skype for Business verwenden. 
  
### <a name="skype-meetings-app"></a>Skype-Besprechungs-App

Die Skype-Besprechungs-App wird als App auf Computern mit Windows 10, Windows 8.1, Windows 8, Windows 7 mit 32- und 64-Bit-Installation von Internet Explorer 11 oder höher ausgeführt. 
  
Weitere Abhängigkeiten finden Sie unter ["Unterstützte Plattformen für Skype-Besprechungs-App".](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business für Mac

Skype for Business für Mac wird auf Computern mit macOS, Version 10.8 oder höher, ausgeführt. 

## <a name="hardware-requirements"></a>Hardwareanforderungen
<a name="OS-Browser"> </a>

Die Computerhardwareanforderungen werden durch das Betriebssystem und den Browser bestimmt. Für Sprach- und Telefoniefunktionen sind ein Mikrofon und Lautsprecher, ein Headset mit Mikrofon oder ein entsprechendes gerät erforderlich, das mit dem Computer kompatibel ist. Videofeatures erfordern ein videokompatibles Gerät mit dem Computer. Ausführliche Informationen zur Unterstützung der Videohardware und zur erwarteten Videoqualität finden Sie unter [Skype for Business-Client-Videoauflösungen.](video-resolutions.md)
  
## <a name="network-requirements"></a>Netzwerkanforderungen
<a name="Network"> </a>

Wenn ein Benutzer der Skype for Business Web App oder der Skype-Besprechungs-App Besprechungsverbindungsprobleme hat, besteht die Wahrscheinlichkeit, dass die Netzwerkinfrastruktur ihrer Organisation nicht für die Unterstützung von Office 365 konfiguriert ist, wie in [OFFICE 365-URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)und -IP-Adressbereichen beschrieben. Dies ist der Fall, wenn die Besprechung von einem Benutzer von Skype for Business Online oder Skype for Business Server erstellt wurde. 
  
Wenn sich der Benutzer in einem Netzwerk befindet, das nicht wie beschrieben konfiguriert ist, funktionieren möglicherweise viele App-Features, und er kann überhaupt keine Verbindung mit der Besprechung herstellen.
  
## <a name="supported-meetings-features"></a>Unterstützte Besprechungsfeatures
<a name="BKMK_Conferencing"> </a>

In dieser Tabelle werden die Besprechungsfunktionen verglichen, die Benutzern des Skype for Business-Clients, der Skype for Business Web App, der Skype-Besprechungs-App und der Lync Web App zur Verfügung stehen. Lync Web App wird zu Featurevergleichszwecken aufgelistet: Ein Benutzer würde Lync Web App nur herunterladen und verwenden, wenn die Besprechung auf einem Lync 2013-Server gehostet wird.

| Feature/Funktion | Skype for Business 2016- oder 2019-Client | Skype for Business auf dem Mac-Client | Skype-Besprechungs-App | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Computeraudiofunktionen hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |
|Video hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |
|Wechseln von Audio zu einem Telefon für authentifizierte Teilnehmer  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Wechseln von Audio zu einem Telefon für Gastteilnehmer  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Video mit mehrerenPartys anzeigen (Katalogansicht)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(Nur Ansicht)  <br/> |||
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Auf detaillierte Besprechungsliste zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Festlegen von Nachrichten mit hoher Wichtigkeit  <br/> |&#x2714;|||||
|Desktop freigeben (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |
|Programm freigeben (sofern aktiviert)  <br/> |&#x2714;||&#x2714;(nur unter Windows; erfordert ein Plug-In)  <br/> |&#x2714;(nur unter Windows; erfordert ein Plug-In)  <br/> |&#x2714;(nur unter Windows; erfordert ein Plug-In)  <br/> |
|Übernehmen der Kontrolle über den freigegebenen Desktop oder das Programm eines anderen Benutzers  <br/> |&#x2714;||&#x2714; (&#x2776; nur unter Windows; erfordert ein Plug-In)  <br/> |&#x2714; (&#x2776; nur unter Windows; erfordert ein Plug-In)  <br/> |&#x2714; (&#x2776; nur unter Windows; erfordert ein Plug-In)  <br/> |
|Let another user take control of your shared desktop or program  <br/> |&#x2714;|||||
|Anonyme Teilnehmer hinzufügen (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer nach Namen einladen  <br/> |&#x2714;|&#x2714;||||
|Teilnehmer nach Telefonnummer einladen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer per E-Mail einladen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahlaudiobesprechungen  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Initiieren einer Sofortsitzung  <br/> |&#x2714;|&#x2714;||||
|Aufzeichnen einer Besprechung  <br/> |&#x2714;|||||
|Hinzufügen und Herunterladen von Anlagen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navigieren in Microsoft PowerPoint-Dateien  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Hinzufügen und Bearbeiten von OneNote-Besprechungsnotizen  <br/> |&#x2714;||Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |
|Whiteboard verwenden  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Abstimmungen durchführen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Hochladen von Dateien für die Freigabe für andere  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen  <br/> |Outlook oder Skype for Business Web Scheduler  <br/> |Outlook oder Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |
|&amp;F-A-Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Teilnehmervideo deaktivieren  <br/> |&#x2714;|||||
|Deaktivieren von Besprechungsbenachrichtigungen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Stummschalten der Zielgruppe  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Machen Sie jeden zu einem Teilnehmer  <br/> |&#x2714;|||||
|Erzeugen von Skype Meeting Broadcast  <br/> |&#x2714;|||||
   
 &#x2776; Teilnehmer können keine Desktops steuern, die von Benutzern von Skype for Business für Mac, Lync für Mac 2011 oder Communicator für Mac 2011 gemeinsam genutzt werden. Dies funktioniert auch nicht für Skype for Business Web App unter Max OSX.
  
 &#x2777; für Skype for Business Online erfordert diese Funktion Microsoft PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.
  
 &#x2778; Der Lync für Mac 2011-Client kann Microsoft Office 2013 -PowerPoint-Präsentationen nicht anzeigen, wenn sie in einer Konferenz von skype for Business Web App freigegeben wurden.
  
## <a name="known-issues-and-troubleshooting"></a>Bekannte Probleme und Problembehandlung
<a name="BKMK_Conferencing"> </a>

Für Endbenutzer steht die [Onlinehilfe für](https://aka.ms/smahelp) diese Apps zur Verfügung. It Professionals should be aware of the following issues:
  
- Wenn sich der Benutzer in einem Netzwerk befindet, das nicht für die Erfüllung der Netzwerkanforderungen konfiguriert [ist,](meetings-clients.md#Network)funktionieren möglicherweise viele App-Features, und er kann möglicherweise überhaupt keine Verbindung mit der Besprechung herstellen.
    
- Einige Benutzer verfügen möglicherweise über vom Unternehmen verwaltete Computer mit deaktivierter Berechtigung zum Installieren von Apps. Für diese Benutzer ist keine app eine [](https://products.office.com/skype-for-business/download-app?tab=tabs-2) Option, aber [Smartphones](https://products.office.com/skype-for-business/download-app?tab=tabs-1) und Tablet-Benutzer können kostengünstige mobile Clients installieren, die sie zur Teilnahme an Besprechungen verwenden können.
    
    Andere Installationsprobleme werden auch in den [Hilfethemen behandelt.](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US) 
    
- Benutzern wird möglicherweise beim ersten Ausführen der Besprechungs-App eine Firewallwarnung angezeigt. Sie werden möglicherweise aufgefordert, Ports zu öffnen, um die Benutzererfahrung zu optimieren, und dies erfordert möglicherweise Administratorrechte auf dem Computer, den sie möglicherweise nicht haben. Die App sollte weiterhin funktionieren, und der Benutzer kann sicher ablehnen, die angeforderten Ports zu öffnen. 
    
- Sie müssen die ActiveX [ohne Filterung](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer aktiviert haben, auch wenn IE nicht Ihr Standardbrowser ist. In Skype for Business Web App ist für die Audio-, Video- und Bildschirmfreigabe ein ActiveX-Steuerelement erforderlich, ein kleines Modul, das einer Web App oder einem anderen Programm zusätzliche Features hinzufügt.
    
- Damit einige Features von Skype for Business Web App ordnungsgemäß [](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) funktionieren, müssen Sie Ihrem Browser erlauben, Cookies auf Ihrem Computer oder Gerät zu speichern.
    
- Möglicherweise müssen Sie die Unterstützung von [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) in Ihrem Browser aktivieren, damit einige Skype for Business Web App-Features wie erwartet funktionieren.
    
### <a name="aes-support"></a>AES-Unterstützung 

Ab Skype for Business Server 2015 CU5 wird AES für ASP.NET 4.6 nicht unterstützt, was dazu führen kann, dass die Skype-Besprechungs-App nicht gestartet wird. [Kryptografieanforderungen aufgrund von ASP .NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) haben weitere Details.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Bereitstellen von herunterladbaren Webclients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für die Skype-Besprechungs-App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

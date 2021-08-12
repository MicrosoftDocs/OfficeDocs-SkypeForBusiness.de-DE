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
description: 'Zusammenfassung: IT-Experten sollten die Supportanforderungen für die Skype for Business-Web-App- und Skype-Besprechungs-App während der Planung für Skype for Business Server überprüfen. Dieser Artikel richtet sich nicht an die Benutzer dieser Apps.'
ms.openlocfilehash: 575b1c7a5d335350ade6008cd0713b89b7e14ad07e86f290c98b72fcfdcd7cd4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281698"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planen von Besprechungsclients (Web App und Besprechungs-App)
 
**Zusammenfassung:** IT-Experten sollten die Supportanforderungen für die Skype for Business-Web-App- und Skype-Besprechungs-App während der Planung für Skype for Business Server überprüfen. Dieser Artikel richtet sich nicht an die Benutzer dieser Apps.
  
Nachdem Sie Skype for Business Server implementiert haben, werden die Benutzer Ihrer Organisation vermutlich den Skype for Business-Client im Rahmen des Bereitstellungsprozesses installiert haben. 
  
Später können diese Benutzer Besprechungen erstellen und Benutzer von außerhalb der Organisation einladen, und diese Eingeladenen haben möglicherweise keine Version des Skype for Business Clients. Wenn diese Benutzer auf die URL für die Besprechungseinladung klicken, wird das Fehlen eines Clients erkannt, und der eingeladene Benutzer ohne Skype for Business Client wird aufgefordert, einen einfachen, besprechungsgeschützten Client herunterzuladen und zu installieren, damit er an der Besprechung teilnehmen kann.
  
> [!NOTE]
> Die Skype for Business-Web-App- und Skype-Besprechungs-App ist nur verfügbar, wenn Sie versuchen, sich bei einer Besprechung anzumelden, ohne Skype for Business zu müssen. Die Benutzerhilfe für diese Apps ist unter [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> Sie können weder die Skype for Business-Web-App noch Skype Besprechungs-App vorinstallieren, aber [Smartphone-](https://products.office.com/skype-for-business/download-app?tab=tabs-1) und [Tablet-Benutzer](https://products.office.com/skype-for-business/download-app?tab=tabs-2) können möglicherweise kostengünstige mobile Clients installieren, die sie für die Teilnahme an Besprechungen verwenden können.
  
Standardmäßig wird der Benutzer vom Server, auf dem die Besprechung gehostet wird, aufgefordert, Skype for Business-Web-App herunterzuladen und zu installieren, um an der Besprechung teilzunehmen. Die Skype for Business-Web-App wird auf dem Front-End-Server gespeichert und an den Besprechungsteilnehmer gesendet. 
  
Für Skype for Business Server stehen Skype Besprechungs-App (auf Windows) und Skype for Business für Mac (auf dem Mac) als Ersatz für Skype for Business-Web-App ab CU5 zur Verfügung. Für die Bereitstellung der Ersatz-Apps ist jedoch die unter [Aktivieren Skype Besprechungs-App beschriebene](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)zusätzliche Konfiguration erforderlich, um Skype for Business-Web-App (optional) zu ersetzen. Wenn Skype Besprechungs-App und Skype for Business für Mac aktiviert sind, laden Benutzer die neueste Version der Apps von der Microsoft 365 oder Office 365 Content Delivery Network (CDN) und nicht von Ihrem Skype for Business-Server herunter. Für Skype for Business Server 2019 ist die Verwendung Skype Besprechungs-App und Skype for Business für Mac die einzige Option.
  
Skype Die Besprechungs-App bietet eine vereinfachte Browseroberfläche für das Herunterladen und Installieren der App und die Teilnahme an Besprechungen, einschließlich der Teilnahme mit einem Klick für Benutzer von Internet Explorer. Skype Die Besprechungs-App bietet außerdem viele Verbesserungen gegenüber dem Skype for Business-Web-App für Zuverlässigkeit und Besprechungserfahrung. 
  
> [!NOTE]
> Ab Skype for Business Server 2015 CU5 oder höher senden Besprechungen, die mit Skype for Business Online abgehalten werden, keinen clientlosen Benutzer mehr die Skype for Business-Web-App, sondern sie werden stattdessen Skype Besprechungs-App (auf Windows) oder Skype for Business für Mac (auf dem Mac) gesendet. Wenn Sie ab Skype for Business Server 2015 CU5 oder höher [Skype Besprechungs-App aktivieren, um Skype for Business-Web-App (optional) zu ersetzen,](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)werden clientlose Benutzer Skype Besprechungs-App oder Skype for Business für Mac anstatt Skype for Business-Web-App gesendet. 
  
## <a name="software-requirements"></a>Softwareanforderungen
<a name="OS-Browser"> </a>

Um die Skype for Business-Web-App verwenden zu können, muss ein Benutzer über eine der folgenden unterstützten Betriebssystem- und Browserkombinationen verfügen. 
  
**Betriebssystem- und Mindestbrowserunterstützung für Skype for Business-Web-App**

| Betriebssystem | Microsoft Edge | 32- und 64-Bit-Internet Explorer 11 oder höher | 32- und 64-Bit-Internet Explorer 10 oder höher | 32- und 64-Bit-Internet Explorer 9 oder höher | 32- und 64-Bit-Version von Safari 6.2.8 - 11.X | 32- und 64-Bit-Version von Chrome 18.X oder höher |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Ja  <br/> |Ja  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend <br/> |Ja &#x2778; <br/> |
|Windows 8 (Intel-basiert) &#x2776; <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nicht zutreffend <br/> |Nicht zutreffend  <br/> |Ja &#x2778; <br/> |
|Windows 7 mit SP1 &#x2777; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nicht zutreffend <br/>|Ja &#x2778; <br/> |
|Windows Server 2008 R2 mit SP1 &#x2777; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nicht zutreffend <br/>|Ja &#x2778; <br/> |
|macOS 10.8 und höher (Intel-basiert) &#x2777; <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Ja <br/> |
   
&#x2776; Das Skype for Business-Web-App Browser-Plug-In erfordert ein bestimmtes Freigabe-Plug-In, um computerbasierte Sprach-, Video-, Freigabe- und Anzeigefunktionen für die laufende Bildschirmfreigabe und andere Features zu verwenden. Ein Besprechungsteilnehmer erhält die Möglichkeit, das Freigabe-Plug-In zu installieren, wenn er an der Besprechung teilnimmt oder eine dieser Features initiiert. Auf Windows 8 und Windows 8.1 kann das Freigabe-Plug-In nur installiert werden, wenn Sie Internet Explorer 10 oder Internet Explorer 11 für den Desktop ausführen. Diese Features sind für Nicht-Desktopversionen von Internet Explorer 10 und 11 nicht verfügbar. Beachten Sie, dass Firefox und Safari, Version 12.0 und höher, nicht mehr unterstützt werden.
  
&#x2777; On supported Windows 7, Windows Server 2008 R2, and Macintosh operating systems, all features are available including computer-based voice, video, application viewing, application sharing, desktop viewing, and desktop sharing. Um diese Features zu verwenden, müssen Sie ein Plug-In installieren, wenn Sie dazu aufgefordert werden. Beachten Sie, dass Mac OS X, Version 10.7, nicht mehr unterstützt wird.  Beachten Sie außerdem, dass die Web-App nicht unter OS X 10.15 oder höher installiert wird.  Es wird empfohlen, die neueste Version von Skype for Business für Mac zu verwenden, die anonyme Beitrittsszenarien in Zukunft unterstützt.
  
&#x2778; Zugreifen auf die Web App über Chrome auf Windows wird ein kleines Programm gestartet, das die Web App in einem eingebetteten Internet Explorer-Frame lädt. Für dieses Programm muss eine der unterstützten Versionen von Internet Explorer installiert sein, damit die Web App ordnungsgemäß geladen wird.
  
> [!NOTE]
> Microsoft 365 und Office 365 Benutzer können Internet Explorer 10 oder höher mit Skype for Business verwenden. 
  
### <a name="skype-meetings-app"></a>Skype-Besprechungs-App

Skype Die Besprechungs-App wird als App auf Computern mit Windows 10, Windows 8.1, Windows 8 Windows 7 und 32- und 64-Bit-Internet Explorer 11 oder höher ausgeführt. 
  
Informationen zu anderen Abhängigkeiten finden Sie unter ["Unterstützte Plattformen" für Skype Besprechungs-App.](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business für Mac

Skype for Business für Mac wird auf Computern mit macOS Version 10.8 oder höher ausgeführt. 

## <a name="hardware-requirements"></a>Hardwareanforderungen
<a name="OS-Browser"> </a>

Die Computerhardwareanforderungen werden durch das Betriebssystem und den Browser bestimmt. Sprach- und Telefoniefunktionen erfordern ein Mikrofon und Lautsprecher, ein Headset mit Mikrofon oder ein entsprechendes Gerät, das mit dem Computer kompatibel ist. Videofeatures erfordern ein Videogerät, das mit dem Computer kompatibel ist. Ausführliche Informationen zur Unterstützung der Videohardware und zur erwarteten Videoqualität finden Sie unter [Skype for Business Clientvideoauflösungen.](video-resolutions.md)
  
## <a name="network-requirements"></a>Netzwerkanforderungen
<a name="Network"> </a>

Wenn ein Benutzer von Skype for Business-Web-App oder Skype Besprechungs-App Probleme mit der Besprechungsverbindung hat, ist die Netzwerkinfrastruktur seiner Organisation wahrscheinlich nicht so konfiguriert, dass Office 365 unterstützt wird, wie in [Office 365 URLs und IP-Adressbereichen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)beschrieben. Dies ist der Fall, unabhängig davon, ob die Besprechung von einem Benutzer von Skype for Business Online oder Skype for Business Server erstellt wurde. 
  
Wenn sich der Benutzer in einem Netzwerk befindet, das nicht wie beschrieben konfiguriert ist, funktionieren viele App-Features möglicherweise oder nicht, und sie können keine Verbindung mit der Besprechung herstellen.
  
## <a name="supported-meetings-features"></a>Unterstützte Besprechungsfunktionen
<a name="BKMK_Conferencing"> </a>

In dieser Tabelle werden die Besprechungsfeatures verglichen, die Benutzern des Skype for Business Clients, Skype for Business-Web-App, Skype Besprechungs-App und Lync Web App zur Verfügung stehen. Lync Web App wird für Featurevergleiche aufgeführt: Ein Benutzer würde Lync Web App nur herunterladen und verwenden, wenn die Besprechung auf einem Lync 2013-Server gehostet wurde.

| Feature/Funktion | Skype for Business 2016- oder 2019-Client | Skype for Business auf dem Mac-Client | Skype-Besprechungs-App | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Computeraudiofunktionen hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |
|Video hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |
|Wechseln von Audio zu einem Telefon für authentifizierte Teilnehmer  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Wechseln von Audio zu einem Telefon für Gastteilnehmer  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(schreibgeschützt)  <br/> |||
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Auf detaillierte Besprechungsliste zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Festlegen von Chatnachrichten mit hoher Wichtigkeit  <br/> |&#x2714;|||||
|Desktop freigeben (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |&#x2714; (erfordert Plug-In)  <br/> |
|Programm freigeben (sofern aktiviert)  <br/> |&#x2714;||&#x2714;(Nur bei Windows; erfordert Plug-In)  <br/> |&#x2714;(Nur bei Windows; erfordert Plug-In)  <br/> |&#x2714;(Nur bei Windows; erfordert Plug-In)  <br/> |
|Übernehmen der Kontrolle über den freigegebenen Desktop oder das Programm eines anderen Benutzers  <br/> |&#x2714;||&#x2714; (&#x2776; nur bei Windows; erfordert Plug-In)  <br/> |&#x2714; (&#x2776; nur bei Windows; erfordert Plug-In)  <br/> |&#x2714; (&#x2776; nur bei Windows; erfordert Plug-In)  <br/> |
|Zulassen, dass ein anderer Benutzer die Kontrolle über Ihren freigegebenen Desktop oder Ihr freigegebenes Programm übernimmt  <br/> |&#x2714;|||||
|Anonyme Teilnehmer hinzufügen (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer nach Name einladen  <br/> |&#x2714;|&#x2714;||||
|Einladen von Teilnehmern nach Telefonnummer  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer per E-Mail einladen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahlaudiobesprechungen  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Initiieren einer Sofortbesprechung  <br/> |&#x2714;|&#x2714;||||
|Aufzeichnen einer Besprechung  <br/> |&#x2714;|||||
|Hinzufügen und Herunterladen von Anlagen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navigieren in Microsoft PowerPoint-Dateien  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Hinzufügen und Bearbeiten OneNote Besprechungsnotizen  <br/> |&#x2714;||Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |
|Whiteboard verwenden  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Abstimmungen durchführen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Hochladen dateien für andere Personen freigeben  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen  <br/> |Outlook oder Skype for Business Web Scheduler  <br/> |Outlook oder Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |
|F &amp; A-Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Deaktivieren des Teilnehmervideos  <br/> |&#x2714;|||||
|Deaktivieren von Chatnachrichten für Besprechungen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Stummschalten der Zielgruppe  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Machen Sie jeden zum Teilnehmer  <br/> |&#x2714;|||||
|Erzeugen von Skype-Besprechung Broadcast  <br/> |&#x2714;|||||
   
 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business für Mac, Lync für Mac 2011 oder Communicator für Mac 2011-Benutzer freigegeben werden. Dies funktioniert auch nicht für Skype for Business-Web-App auf Max OSX.
  
 &#x2777; Für Skype for Business Online erfordert dieses Feature Microsoft PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.
  
 &#x2778; Der Lync für Mac 2011-Client kann Microsoft Office 2013 PowerPoint Präsentationen nicht anzeigen, wenn sie von der Skype for Business-Web-App in einer Konferenz freigegeben wurden.
  
## <a name="known-issues-and-troubleshooting"></a>Bekannte Probleme und Problembehandlung
<a name="BKMK_Conferencing"> </a>

Endbenutzern steht die [Onlinehilfe](https://aka.ms/smahelp) für diese Apps zur Verfügung. IT-Experten sollten sich der folgenden Probleme bewusst sein:
  
- Wenn sich der Benutzer in einem Netzwerk befindet, das nicht für die Erfüllung der [Netzwerkanforderungen](meetings-clients.md#Network)konfiguriert ist, funktionieren möglicherweise viele App-Features oder funktionieren nicht, und sie können sich möglicherweise überhaupt nicht mit der Besprechung verbinden.
    
- Einige Benutzer verfügen möglicherweise über vom Unternehmen verwaltete Computer mit deaktivierter Berechtigung zum Installieren von Apps. für diese Benutzer ist keine App eine Option, aber [Smartphone-](https://products.office.com/skype-for-business/download-app?tab=tabs-1) und [Tablet-Benutzer](https://products.office.com/skype-for-business/download-app?tab=tabs-2) können möglicherweise kostengünstige mobile Clients installieren, die sie für die Teilnahme an Besprechungen verwenden können.
    
    Weitere Installationsprobleme werden auch in den [Hilfethemen](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)behandelt. 
    
- Benutzern wird möglicherweise eine Firewallwarnung angezeigt, wenn sie die Besprechungs-App zum ersten Mal ausführen. Sie werden möglicherweise aufgefordert, Ports zu öffnen, um die Benutzererfahrung zu optimieren, und dies erfordert möglicherweise Administratorrechte auf dem Computer, über den sie möglicherweise nicht verfügen. Die App sollte weiterhin funktionieren, und der Benutzer kann das Öffnen der angeforderten Ports sicher ablehnen. 
    
- Sie müssen [ActiveX ohne Filterung](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer aktiviert haben, auch wenn IE nicht Ihr Standardbrowser ist. In Skype for Business-Web-App ist ein ActiveX-Steuerelement – ein kleines Modul, das einer Web-App oder einem anderen Programm zusätzliche Features hinzufügt – für Audio-, Video- und Bildschirmfreigaben erforderlich.
    
- Damit einige Features von Skype for Business-Web-App ordnungsgemäß funktionieren, müssen Sie zulassen, dass Ihr Browser Cookies auf Ihrem Computer oder Gerät [speichert.](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)
    
- Möglicherweise müssen Sie die [JavaScript-Unterstützung](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) in Ihrem Browser aktivieren, damit einige Skype for Business-Web-App Features wie erwartet funktionieren.
    
### <a name="aes-support"></a>AES-Unterstützung 

Ab Skype for Business Server 2015 CU5 wird AES für ASP.NET 4.6 nicht unterstützt, was dazu führen kann, dass Skype Besprechungs-App nicht gestartet werden kann. [Kryptografische Anforderungen aufgrund von ASP .NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) haben weitere Details.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Bereitstellen von herunterladbaren Webclients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für Skype Besprechungs-App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

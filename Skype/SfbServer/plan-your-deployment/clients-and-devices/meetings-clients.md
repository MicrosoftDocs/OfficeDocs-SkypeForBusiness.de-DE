---
title: Planen von Besprechungs Clients (app für Webanwendungen und Besprechungen)
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: IT-Experten sollten die Supportanforderungen für die APP Skype for Business-Webanwendung und Skype-Besprechungen überprüfen, während Sie Skype for Business Server planen. Dieser Artikel ist nicht für die Benutzer dieser apps vorgesehen.'
ms.openlocfilehash: 30397c922dbc5bb8578714d70712f90d7e14ca4c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221045"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planen von Besprechungs Clients (app für Webanwendungen und Besprechungen)
 
**Zusammenfassung:** IT-Experten sollten die Supportanforderungen für die APP Skype for Business-Webanwendung und Skype-Besprechungen überprüfen, während Sie Skype for Business Server planen. Dieser Artikel ist nicht für die Benutzer dieser apps vorgesehen.
  
Nachdem Sie Skype for Business Server implementiert haben, werden die Benutzer Ihrer Organisation vermutlich den Skype for Business-Client als Teil des Bereitstellungsprozesses installiert haben. 
  
Später können diese Benutzer Besprechungen erstellen und Benutzer von außerhalb der Organisation einladen, und diese Besprechungsteilnehmer verfügen möglicherweise nicht über eine Version des Skype for Business Clients. Wenn diese Benutzer auf die URL für die Besprechungseinladung klicken, wird das Fehlen eines Clients erkannt, und die Einladung ohne Skype for Business-Client wird aufgefordert, einen einfachen, nur für Besprechungen verwendeten Client herunterzuladen und zu installieren, damit Sie an der Besprechung teilnehmen können.
  
> [!NOTE]
> Die Skype for Business-Webanwendung und Skype-Besprechungs-APP sind nur verfügbar, wenn Sie sich bei einer Besprechung anmelden, ohne Skype for Business zu haben. Benutzer Hilfe für diese apps finden Sie unter [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> Sie können die Skype for Business-Webanwendung oder die Skype-Besprechungs-APP nicht vorab installieren, aber [Smart Phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) -und [Tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) -Benutzer können möglicherweise kostengünstige mobile Clients installieren, die Sie für die Teilnahme an Besprechungen verwenden können.
  
Standardmäßig wird der Server, der die Besprechung hostet, den Benutzer anweisen, Skype for Business-Webanwendung herunterzuladen und zu installieren, um an der Besprechung teilzunehmen. Die Skype for Business-Webanwendung wird im Front-End-Server gespeichert und an den Besprechungsteilnehmer gesendet. 
  
Für Skype for Business Server sind die Skype-Besprechungs-app (unter Windows) und Skype for Business für Mac (auf dem Mac) als Ersetzungen für Skype for Business-Webanwendung verfügbar, die mit CU5 beginnt, die Bereitstellung der Ersatz-apps erfordert jedoch die unter [enable Skype Meetings App beschriebene zusätzliche Konfiguration, um Skype for Business-Webanwendung zu ersetzen (optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Wenn die Skype-Besprechungs-APP und Skype for Business für Mac aktiviert sind, laden Benutzer die neueste Version der Apps aus dem Microsoft 365-oder Office 365 Content Delivery Network (CDN) anstatt aus dem Skype for Business Server herunter. Für Skype for Business Server 2019 ist die Verwendung der Skype-Besprechungs-APP und Skype for Business für Mac die einzige Option.
  
Die Skype-Besprechungs-App bietet eine vereinfachte Browserumgebung für das herunterladen und Installieren der APP und die Teilnahme an Besprechungen, einschließlich eines einzigen Klick-Joins für Benutzer von Internet Explorer. Die Skype-Besprechungs-App bietet auch viele Verbesserungen gegenüber der Skype for Business-Webanwendung, um Zuverlässigkeit und Besprechungs Erfahrung zu Gewährleistung. 
  
> [!NOTE]
> Ab Skype for Business Server 2015 CU5 oder höher senden Besprechungen, die mit Skype for Business Online stattfinden, nicht mehr einen Client loseren Benutzer der Skype for Business-Webanwendung, sondern werden stattdessen Skype-Besprechungs-app (unter Windows) oder Skype for Business für Mac (auf dem Mac) gesendet. Wenn Sie Skype for Business Server 2015 CU5 oder höher [die Skype-Besprechungs-App aktivieren, um Skype for Business-Webanwendung zu ersetzen (optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), werden Client-Benutzer ohne Skype for Business-Webanwendung Skype-Besprechungs-APP oder Skype for Business für Mac gesendet. 
  
## <a name="software-requirements"></a>Softwareanforderungen
<a name="OS-Browser"> </a>

Um die Skype for Business-Webanwendung verwenden zu können, muss ein Benutzer über eine der folgenden unterstützten Betriebssystem-und Browser Kombinationen verfügen. 
  
**Betriebs System und minimale Browserunterstützung für Skype for Business-Webanwendung**

| Betriebssystem | Microsoft Edge | 32-und 64-Bit Internet Explorer 11 oder höher | 32-und 64-Bit Internet Explorer 10 oder höher | 32-und 64-Bit Internet Explorer 9 oder höher | 32-und 64-Bit-Version von Safari 6.2.8-11. X | 32-und 64-Bit-Version von Chrome 18. X oder höher |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Ja  <br/> |Ja  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend <br/> |Ja &#x2778; <br/> |
|Windows 8 (Intel-basiert) &#x2776; <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nicht zutreffend <br/> |Nicht zutreffend  <br/> |Ja &#x2778; <br/> |
|Windows 7 mit SP1 &#x2777; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nicht zutreffend <br/>|Ja &#x2778; <br/> |
|Windows Server 2008 R2 mit SP1 &#x2777; <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |Nicht zutreffend <br/>|Ja &#x2778; <br/> |
|macOS 10,8 und höher (Intel-basiert) &#x2777; <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |Ja  <br/> |Ja <br/> |
   
&#x2776; das Plug-in für das Skype for Business-Webbrowser-Webanwendungs Modul ein spezielles Freigabe Modul erfordert, um computerbasierte sprach-, Video-, Freigabe-und Anzeigefunktionen für die fortlaufende Bildschirmfreigabe und andere Features zu verwenden. Ein Besprechungsteilnehmer hat die Möglichkeit, das Freigabe-Plug-in entweder beim Beitritt zur Besprechung oder beim Initiieren eines dieser Features zu installieren. In Windows 8 und Windows 8.1 kann das Freigabe-Plug-in nur installiert werden, wenn Sie Internet Explorer 10 oder Internet Explorer 11 für den Desktop verwenden. Diese Features sind nicht verfügbar mit nicht-Desktop-Versionen von Internet Explorer 10 und 11. Beachten Sie, dass Firefox und Safari Version 12,0 und höher nicht mehr unterstützt werden.
  
&#x2777; für unterstützte Windows 7-, Windows Server 2008 R2-und Macintosh-Betriebssysteme stehen alle Funktionen zur Verfügung, einschließlich computerbasierter sprach-, Video-, Anwendungsanzeige, Anwendungsfreigabe, Desktop Anzeige und Desktopfreigabe. Um diese Funktionen verwenden zu können, müssen Sie ein Plug-in installieren, wenn Sie dazu aufgefordert werden. Beachten Sie, dass Mac OS X Version 10,7 nicht mehr unterstützt wird.  Beachten Sie auch, dass die Webanwendung unter OS X 10,15 oder höher nicht installiert wird.  Es wird empfohlen, die neueste Version von Skype for Business für Mac zu verwenden, die das fortsetzen anonymer Join-Szenarien unterstützt.
  
&#x2778; auf die Webanwendung von Chrome unter Windows zuzugreifen, wird ein kleines Programm gestartet, das die Webanwendung in einem eingebetteten Internet Explorer-Frame lädt. Für dieses Programm muss eine der unterstützten Versionen von Internet Explorer installiert sein, damit die Webanwendung ordnungsgemäß lädt.
  
> [!NOTE]
> Microsoft 365 und Office 365 Benutzer können Internet Explorer 10 oder höher mit Skype for Business verwenden. 
  
### <a name="skype-meetings-app"></a>Skype-Besprechungs-App

Skype Meetings-APP wird als APP auf Computern mit Windows 10, Windows 8.1, Windows 8 Windows 7, mit 32-und 64-Bit-Internet Explorer 11 oder höher installiert. 
  
Weitere Abhängigkeiten finden Sie [unter Supported Platforms for Skype Meetings App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001) .
  
### <a name="skype-for-business-for-mac"></a>Skype for Business für Mac

Skype for Business für Mac wird auf Computern mit macOS Version 10,8 oder höher ausgeführt. 

## <a name="hardware-requirements"></a>Hardwareanforderungen
<a name="OS-Browser"> </a>

Die Computer Hardwareanforderungen werden vom Betriebssystem und vom Browser bestimmt. Für Sprach-und Telefoniefunktionen sind Mikrofon und Lautsprecher, Headset mit Mikrofon oder ein gleichwertiges, mit dem Computer kompatibles Gerät erforderlich. Für Videofunktionen ist ein mit dem Computer kompatibles Videogerät erforderlich. Ausführliche Informationen zur Unterstützung von Videohardware und zu einer erwarteten Videoqualität finden Sie unter [Skype for Business Client-Videoauflösungen](video-resolutions.md).
  
## <a name="network-requirements"></a>Netzwerkanforderungen
<a name="Network"> </a>

Wenn ein Benutzer von Skype for Business-Webanwendungs-oder Skype-Besprechungs-App Verbindungsprobleme hat, besteht die Gefahr, dass die Netzwerkinfrastruktur Ihrer Organisation nicht für die Unterstützung von Office 365 konfiguriert ist, wie in [Office 365 URLs und IP-Adressbereichen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)beschrieben. Dies ist der Fall, wenn die Besprechung von einem Benutzer Skype for Business Online oder Skype for Business Server erstellt wurde. 
  
Wenn sich der Benutzer in einem Netzwerk befindet, das nicht wie beschrieben konfiguriert ist, können viele App-Funktionen möglicherweise nicht funktionieren, und Sie können möglicherweise überhaupt keine Verbindung mit der Besprechung herstellen.
  
## <a name="supported-meetings-features"></a>Unterstützte besprechungsfeatures
<a name="BKMK_Conferencing"> </a>

In dieser Tabelle werden die besprechungsfeatures verglichen, die Benutzern des Skype for Business-Clients, Skype for Business-Webanwendung, Skype-Besprechungs-APP und lync Web App zur Verfügung stehen. Lync Web App wird für Features-Vergleichszwecke aufgeführt: ein Benutzer würde nur dann herunterladen und lync Web App verwenden, wenn die Besprechung auf einem lync 2013 Server gehostet wurde.

| Feature/Funktion | Skype for Business 2016-oder 2019-Client | Skype for Business auf dem Mac-Client | Skype-Besprechungs-App | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Computeraudiofunktionen hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |
|Video hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |
|Wechseln von Audio zu einem Telefon für authentifizierte Teilnehmer  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Audiodaten zu einem Telefon für Gastteilnehmer wechseln  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Video mit mehreren Teilen anzeigen (Galerieansicht)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (nur anzeigen)  <br/> |||
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Auf detaillierte Besprechungsliste zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Festlegen von Chatnachrichten als hohe Wichtigkeit  <br/> |&#x2714;|||||
|Desktop freigeben (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |
|Programm freigeben (sofern aktiviert)  <br/> |&#x2714;||&#x2714; (nur unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur unter Windows; erfordert Plug-in)  <br/> |
|Übernehmen der Steuerung des freigegebenen Desktops oder Programms eines anderen Benutzers  <br/> |&#x2714;||&#x2714; (nur &#x2776; unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur &#x2776; unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur &#x2776; unter Windows; erfordert Plug-in)  <br/> |
|Zulassen, dass ein anderer Benutzer die Steuerung des freigegebenen Desktops oder Programms übernehmen kann  <br/> |&#x2714;|||||
|Anonyme Teilnehmer hinzufügen (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer nach Name einladen  <br/> |&#x2714;|&#x2714;||||
|Teilnehmer nach Telefonnummer einladen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer per e-Mail einladen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahl Audiokonferenzen  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Initiieren einer Sofortbesprechung  <br/> |&#x2714;|&#x2714;||||
|Aufzeichnen einer Besprechung  <br/> |&#x2714;|||||
|Hinzufügen und Herunterladen von Anlagen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navigieren in Microsoft PowerPoint Dateien  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote-Besprechungsnotizen hinzufügen und bearbeiten  <br/> |&#x2714;||Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |
|Whiteboard verwenden  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Abstimmungen durchführen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Hochladen von Dateien, die für andere Personen freigegeben werden  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen  <br/> |Outlook-oder Skype for Business-Webplaner  <br/> |Outlook-oder Skype for Business-Webplaner  <br/> |Skype for Business-Webplaner  <br/> |Skype for Business-Webplaner  <br/> |Skype for Business-Webplaner  <br/> |
|Q &amp; ein Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Video für Teilnehmer deaktivieren  <br/> |&#x2714;|||||
|Besprechungs-Chat deaktivieren  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Benutzergruppe stumm schalten  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Jeder als Teilnehmer festlegen  <br/> |&#x2714;|||||
|Erstellen von Skype-Live Konferenz  <br/> |&#x2714;|||||
   
 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business für Mac, lync für Mac 2011 oder Communicator für Mac 2011-Benutzer gemeinsam verwendet werden. Dies funktioniert auch nicht für Skype for Business-Webanwendung auf Max OSX.
  
 &#x2777; für Skype for Business Online erfordert diese Funktion Microsoft PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.
  
 &#x2778; der Client für lync für Mac 2011 kann Microsoft Office 2013 PowerPoint-Präsentationen nicht anzeigen, wenn Sie von der Skype for Business-Webanwendung in einer Konferenz freigegeben wurden.
  
## <a name="known-issues-and-troubleshooting"></a>Bekannte Probleme und Problembehandlung
<a name="BKMK_Conferencing"> </a>

Für Endbenutzer ist die [Online Hilfe](https://aka.ms/smahelp) für diese apps leicht verfügbar. IT-Experten sollten sich der folgenden Probleme bewusst sein:
  
- Wenn sich der Benutzer in einem Netzwerk befindet, das nicht für die [Netzwerkanforderungen](meetings-clients.md#Network)konfiguriert ist, funktionieren viele App-Funktionen möglicherweise nicht, und Sie können möglicherweise überhaupt keine Verbindung mit der Besprechung herstellen.
    
- Einige Benutzer verfügen möglicherweise über Unternehmens verwaltete Computer mit deaktivierter Berechtigung zum Installieren von apps. für diese Benutzer ist keine App eine Option, aber [Smart Phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) -und [Tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) -Benutzer können möglicherweise kostengünstige mobile Clients installieren, die Sie für die Teilnahme an Besprechungen verwenden können.
    
    Andere Installationsprobleme werden auch in den [Hilfethemen](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)behandelt. 
    
- Benutzern wird möglicherweise eine Firewall-Warnung angezeigt, wenn Sie die Besprechungs-App zum ersten Mal ausführen. Sie werden möglicherweise aufgefordert, Ports zu öffnen, um die Benutzeroberfläche zu optimieren, und dies erfordert möglicherweise Administratorrechte für den Computer, den Sie möglicherweise nicht haben. Die APP sollte weiterhin funktionieren, und der Benutzer kann sicher ablehnen, die angeforderten Ports zu öffnen. 
    
- Sie müssen [ActiveX ohne Filterung](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer aktiviert lassen, auch wenn es sich bei dem IE nicht um den Standardbrowser handelt. In Skype for Business-Webanwendung ist ein ActiveX-Steuerelement (ein kleines Modul, das einer Webanwendung oder einem anderen Programm zusätzliche Features hinzufügt) für die Audio-, Video-und Bildschirmfreigabe erforderlich.
    
- Damit einige Features von Skype for Business-Webanwendung ordnungsgemäß funktionieren, müssen Sie Ihrem Browser das [Speichern von Cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) auf Ihrem Computer oder Gerät gestatten.
    
- Möglicherweise müssen Sie JavaScript-Unterstützung in Ihrem Browser [aktivieren](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) , damit einige Skype for Business-Webanwendungs Funktionen wie erwartet funktionieren.
    
### <a name="aes-support"></a>AES-Unterstützung 

Ab Skype for Business Server 2015 CU5 wird AES für ASP.NET 4,6 nicht unterstützt, und dies kann dazu führen, dass die Skype-Besprechungs-APP nicht gestartet wird. [Kryptografische Anforderungen aufgrund von ASP .NET 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) enthält weitere Details.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Bereitstellen von Webdownload-Clients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für Skype-Besprechungs-App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

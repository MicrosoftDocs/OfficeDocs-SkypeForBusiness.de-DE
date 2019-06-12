---
title: Planen von Besprechungs Clients (app für Web App und Besprechungen)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Zusammenfassung: IT-Experten sollten die Supportanforderungen für die Skype for Business Web App-und Skype-Besprechungs-APP während der Planung für Skype for Business Server überprüfen. Dieser Artikel ist nicht für die Benutzer dieser apps vorgesehen.'
ms.openlocfilehash: a2bc418b9179a63452c5d4fdd1990676f9db4b14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277314"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planen von Besprechungs Clients (app für Web App und Besprechungen)
 
**Zusammenfassung:** IT-Experten sollten die Supportanforderungen für die Skype for Business Web App-und Skype-Besprechungs-APP während der Planung für Skype for Business Server überprüfen. Dieser Artikel ist nicht für die Benutzer dieser apps vorgesehen.
  
Nachdem Sie Skype for Business Server implementiert haben, wird der Skype for Business-Client vermutlich im Rahmen des Bereitstellungsprozesses für die Benutzer Ihrer Organisation installiert. 
  
Später können diese Benutzer Besprechungen erstellen und Benutzer von außerhalb der Organisation einladen, und diese Besprechungseinladungen haben möglicherweise keine Version des Skype for Business-Clients. Wenn diese Benutzer auf die URL für die Besprechungseinladung klicken, wird das Fehlen eines Clients erkannt, und die Einladung ohne Skype for Business-Client wird zum herunterladen und Installieren eines einfachen, nur für Besprechungen bereitgestellten Clients aufgefordert, damit Sie an der Besprechung teilnehmen können.
  
> [!NOTE]
> Die Skype for Business-Web-App und die Skype-Besprechungs-APP sind nur verfügbar, wenn Sie versuchen, sich bei einer Besprechung anzumelden, ohne Skype for Business zu haben. Benutzer Hilfe für diese apps finden Sie [https://aka.ms/smahelp](https://aka.ms/smahelp)unter. 
  
> [!NOTE]
> Sie können die Skype for Business Web App-oder Skype-Besprechungs-APP nicht vorinstallieren, aber [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) -und [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) -Benutzer können günstige Mobile Clients installieren, die Sie für die Teilnahme an Besprechungen verwenden können.
  
Standardmäßig leitet der Server, auf dem die Besprechung gehostet wird, den Benutzer zum herunterladen und Installieren von Skype for Business Web App, um an der Besprechung teilzunehmen. Die Skype for Business-Web-App ist auf dem Front-End-Server gespeichert und wird an den Besprechungsteilnehmer gesendet. 
  
Für Skype for Business Server stehen die Skype-Besprechungs-app (unter Windows) und Skype for Business für Mac (unter Mac) als Ersatz für Skype for Business Web App ab CU5 zur Verfügung, aber die Bereitstellung der Ersatz-apps erfordert die zusätzliche Konfiguration. beschrieben unter [Aktivieren der Skype-Besprechungs-App zum Ersetzen von Skype for Business Web App (optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Wenn Skype-Besprechungs-APP und Skype for Business für Mac aktiviert sind, werden die Benutzer die neueste Version der Apps aus dem Office 365 Content Delivery Network (CDN) herunterladen, anstatt von Ihrem Skype for Business-Server. Für Skype for Business Server 2019 ist die Verwendung der Skype-Besprechungs-APP und von Skype for Business für Mac die einzige Option.
  
Die Skype-Besprechungs-App bietet eine vereinfachte Browserumgebung zum herunterladen und Installieren der APP sowie zum teilnehmen an Besprechungen, einschließlich einer Klick-Teilnahme für Benutzer von Internet Explorer. Die Skype-Besprechungs-App bietet zudem zahlreiche Verbesserungen gegenüber der Skype for Business Web App für Zuverlässigkeit und die Besprechungs Erfahrung. 
  
> [!NOTE]
> Ab Skype for Business Server 2015 CU5 oder höher senden Besprechungen, die mit Skype for Business Online abgehalten werden, keinen Client-Nutzer der Skype for Business-Web-App mehr, sondern stattdessen eine Skype-Besprechungs-app (unter Windows) oder Skype for Business für Mac (auf einem Mac). Ab Skype for Business Server 2015 CU5 oder höher, wenn Sie Skype- [Besprechungs-App zum Ersetzen von Skype for Business Web App (optional) aktivieren](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), werden Client-Benutzer ohne Skype-Besprechungs-APP oder Skype for Business für Mac anstelle von Skype for Business Web App gesendet. 
  
## <a name="software-requirements"></a>Softwareanforderungen
<a name="OS-Browser"> </a>

Um die Skype for Business-Web-App verwenden zu können, muss ein Benutzer über eine der folgenden unterstützten Betriebssystem-und Browser Kombinationen verfügen. 
  
**Betriebs System und minimale Browserunterstützung für Skype for Business Web App**

| Betriebssystem | Edge | 32-und 64-Bit Internet Explorer 11 oder höher | 32-und 64-Bit Internet Explorer 10 oder höher | 32-und 64-Bit Internet Explorer 9 oder höher | 32-und 64-Bit-Version von Safari 6.2.8-11. X | 32-und 64-Bit-Version von Chrome 18. X oder höher |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Ja   <br/> |Ja  <br/> |-  <br/> |-  <br/> |-  <br/> |Ja #a0 <br/> |
|Windows 8,1 #a0 <br/> |n/v  <br/> |Ja  <br/> |-  <br/> |-  <br/> |- <br/> |Ja #a0 <br/> |
|Windows 8 (Intel-basiert) #a0 <br/> |-  <br/> |n/v  <br/> |Ja  <br/> |- <br/> |-  <br/> |Ja #a0 <br/> |
|Windows 7 mit SP1 #a0 <br/> |n/v  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |n/v <br/>|Ja #a0 <br/> |
|Windows Server 2008 R2 mit SP1 #a0 <br/> |n/v  <br/> |Ja  <br/> |Ja   <br/> |Ja  <br/> |Nicht zutreffend <br/>|Ja #a0 <br/> |
|macOS 10,8 und höher (Intel-basiert) #a0 <br/> |-  <br/> |-  <br/> |-  <br/> |n/v  <br/> |Ja  <br/> |Ja <br/> |
   
&#x2776; das Plug-in für das Skype for Business Web App-Browser ein spezielles Freigabe-Plug-in für die Verwendung von computerbasierter sprach-, Video-, Freigabe-und Anzeige der laufenden Bildschirmfreigabe und anderer Features erfordert. Eine Besprechungs Teilnehmerin erhält die Option, das Freigabe-Plug-in zu installieren, wenn Sie an der Besprechung teilnehmen oder eine dieser Features initiieren. Unter Windows 8 und Windows 8,1 kann das Freigabe-Plug-in nur installiert werden, wenn Sie mit Internet Explorer 10 oder Internet Explorer 11 für den Desktop arbeiten. Diese Features sind für nicht-Desktop Versionen von Internet Explorer 10 und 11 nicht verfügbar. Beachten Sie, dass Firefox und Safari, Version 12,0 und höher, nicht mehr unterstützt werden.
  
&#x2777; unter unterstützten Windows 7-, Windows Server 2008 R2-und Macintosh-Betriebssystemen stehen alle Features zur Verfügung, einschließlich computerbasierter sprach-, Video-, Anwendungsanzeige, Anwendungsfreigabe, Desktop Anzeige und Desktopfreigabe. Um diese Funktionen zu verwenden, müssen Sie ein Plug-In installieren, wenn Sie dazu aufgefordert werden. Mac OS X Version 10.7 wird nicht mehr unterstützt.
  
&#x2778; der Zugriff auf die Web-App in Chrome unter Windows wird ein kleines Programm gestartet, das die Web-App in einem eingebetteten Internet Explorer-Frame lädt. Damit die Web-App richtig geladen wird, muss eine der unterstützten Versionen von Internet Explorer installiert sein.
  
> [!NOTE]
> Office 365-Benutzer können Internet Explorer 10 oder höher mit Skype for Business verwenden. 
  
### <a name="skype-meetings-app"></a>Skype-Besprechungs-App

Die Skype-Besprechungs-APP wird als APP auf Computern unter Windows 10, Windows 8,1, Windows 8, Windows 7, mit 32-und 64-Bit Internet Explorer 11 oder höher ausgeführt. 
  
Weitere Abhängigkeiten finden Sie [unter Unterstützte Plattformen für die Skype-Besprechungs-App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001) .
  
### <a name="skype-for-business-for-mac"></a>Skype for Business für Mac

Skype for Business für Mac wird auf Computern unter macOS Version 10,8 oder höher ausgeführt. 

## <a name="hardware-requirements"></a>Hardwareanforderungen
<a name="OS-Browser"> </a>

Die Anforderungen an die Computerhardware sind vom Betriebssystem und vom Browser abhängig. Für die Sprach- und Telefoniefunktionen werden ein Mikrofon und Lautsprecher, ein Headset mit Mikrofon oder ein ähnliches Gerät benötigt, das mit dem Computer kompatibel ist. Für die Videofunktionen ist ein Videogerät erforderlich, das mit dem Computer kompatibel ist. Detaillierte Informationen zur Unterstützung von Videohardware und zu erwarteter Videoqualität finden Sie unter [Skype for Business-Client-Video](video-resolutions.md)Auflösungen.
  
## <a name="network-requirements"></a>Netzwerkanforderungen
<a name="Network"> </a>

Wenn ein Benutzer der Skype for Business Web App-oder Skype-Besprechungs-App Verbindungsprobleme hat, ist es wahrscheinlich, dass die Netzwerkinfrastruktur Ihres Unternehmens nicht für die Unterstützung von Office 365 konfiguriert ist, wie es in [Office 365-URLs und IP-Adressbereichen](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)beschrieben ist. Dies ist der Fall, wenn die Besprechung von einem Nutzer von Skype for Business Online oder Skype for Business Server erstellt wurde. 
  
Wenn sich der Benutzer in einem Netzwerk befindet, das nicht wie beschrieben konfiguriert ist, funktionieren viele App-Features möglicherweise nicht, und Sie können möglicherweise überhaupt keine Verbindung mit der Besprechung herstellen.
  
## <a name="supported-meetings-features"></a>Unterstützte Besprechungsfunktionen
<a name="BKMK_Conferencing"> </a>

Diese Tabelle vergleicht die besprechungsfeatures, die Benutzern des Skype for Business-Clients, der Skype for Business-Web-App, der Skype-Besprechungs-APP und der lync Web App zur Verfügung stehen. Lync Web App ist für Funktionsvergleichs Zwecke aufgelistet: ein Benutzer würde nur lync Web App herunterladen und verwenden, wenn die Besprechung auf einem lync 2013-Server gehostet wurde.

| Feature/Funktion | Skype for Business 2016 oder 2019-Client | Skype for Business für Mac-Client | Skype-Besprechungs-App | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Computeraudio hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |
|Video hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |
|Audio für authentifizierte Teilnehmer zu einem Telefon wechseln  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Audio für Gastteilnehmer zu einem Telefon wechseln  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Videobasierte Bildschirmübertragung  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (nur anzeigen)  <br/> |||
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Auf detaillierte Teilnehmerliste der Besprechung zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Chats mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|„Hohe Priorität“ für Chatnachrichten festlegen  <br/> |&#x2714;|||||
|Desktop freigeben (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |&#x2714; (erfordert Plug-in)  <br/> |
|Programm freigeben (sofern aktiviert)  <br/> |&#x2714;||&#x2714; (nur unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur unter Windows; erfordert Plug-in)  <br/> |
|Übernehmen der Steuerung des freigegebenen Desktops oder Programms eines anderen Benutzers  <br/> |&#x2714;||&#x2714; (nur #a1 unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur #a1 unter Windows; erfordert Plug-in)  <br/> |&#x2714; (nur #a1 unter Windows; erfordert Plug-in)  <br/> |
|Einem anderen Benutzer die Steuerung Ihres freigegebenen Desktops oder Programms überlassen  <br/> |&#x2714;|||||
|Anonyme Teilnehmer hinzufügen (sofern aktiviert)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer nach Namen einladen  <br/> |&#x2714;|&#x2714;||||
|Teilnehmer nach Telefonnummern einladen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer nach E-Mail-Adressen einladen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Dial-in-Audiobesprechungen verwenden  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Besprechung mit „Jetzt besprechen“ initiieren  <br/> |&#x2714;|&#x2714;||||
|Eine Besprechung aufzeichnen  <br/> |&#x2714;|||||
|Anlagen hinzufügen und herunterladen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|In Microsoft PowerPoint-Dateien navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote-Besprechungsnotizen hinzufügen und bearbeiten  <br/> |&#x2714;||Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |
|Whiteboard verwenden  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Umfragen durchführen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Dateien zur gemeinsamen Verwendung mit anderen hochladen  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Besprechung oder Konferenz planen  <br/> |Outlook oder Skype for Business Web Scheduler  <br/> |Outlook oder Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Teilnehmervideo deaktivieren  <br/> |&#x2714;|||||
|Besprechungschat deaktivieren  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Teilnehmer stummschalten  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Alle zu Teilnehmern machen  <br/> |&#x2714;|||||
|Skype Meeting Broadcast erstellen  <br/> |&#x2714;|||||
   
 &#x2776; Teilnehmer können keine Desktops steuern, die von Skype for Business für Mac, lync für Mac 2011 oder Communicator für Mac 2011-Benutzer freigegeben werden. Das funktioniert auch bei Skype for Business Web App auf Max OSX nicht.
  
 &#x2777; für Skype for Business Online erfordert dieses Feature Microsoft-PSTN-Konferenzen, Exchange Unified Messaging oder einen Drittanbieter für Audiokonferenzen.
  
 &#x2778; der lync für Mac 2011-Client kann Microsoft Office 2013 PowerPoint-Präsentationen nicht anzeigen, wenn Sie von der Skype for Business Web App in einer Konferenz freigegeben wurden.
  
## <a name="known-issues-and-troubleshooting"></a>Bekannte Probleme und Problembehandlung
<a name="BKMK_Conferencing"> </a>

Für Endbenutzer steht die [Online-Hilfe](https://aka.ms/smahelp) für diese apps sofort zur Verfügung. IT-Experten sollten sich mit den folgenden Problemen vertraut machen:
  
- Wenn sich der Benutzer in einem Netzwerk befindet, das nicht so konfiguriert ist, dass er die [Netzwerkanforderungen](meetings-clients.md#Network)erfüllt, funktionieren viele App-Features möglicherweise nicht, und Sie können möglicherweise überhaupt keine Verbindung mit der Besprechung herstellen.
    
- Einige Benutzer verfügen möglicherweise über Unternehmens verwaltete Computer mit deaktivierter Berechtigung zum Installieren von apps. für diese Benutzer ist keine App eine Option, aber [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) -und [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) -Benutzer können günstige Mobile Clients installieren, die Sie für die Teilnahme an Besprechungen verwenden können.
    
    Andere Installationsprobleme werden auch in den [Hilfethemen](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)behandelt. 
    
- Benutzern wird möglicherweise eine Firewall-Warnung angezeigt, wenn Sie die Besprechungs-App zum ersten Mal ausführen. Sie werden möglicherweise aufgefordert, Ports zu öffnen, um die Benutzeroberfläche zu optimieren, und dies erfordert möglicherweise Administratorrechte auf dem Computer, die möglicherweise nicht vorhanden sind. Die APP sollte weiterhin funktionieren, und der Benutzer kann sicher ablehnen, die angeforderten Ports zu öffnen. 
    
- Sie müssen [ActiveX aktiviert](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) haben, ohne in Internet Explorer zu filtern, auch wenn IE nicht Ihr Standardbrowser ist. In Skype for Business Web App ist ein ActiveX-Steuerelement – ein kleines Modul, das einer Web-App oder einem anderen Programm zusätzliche Features hinzufügt – für Audio-, Video-und Bildschirm Freigaben erforderlich.
    
- Damit einige Funktionen von Skype for Business Web App ordnungsgemäß funktionieren, müssen Sie Ihrem Browser gestatten, Cookies auf Ihrem Computer oder Gerät zu [Speichern](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) .
    
- Möglicherweise müssen Sie JavaScript-Unterstützung in Ihrem Browser [aktivieren](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) , damit einige Funktionen von Skype for Business Web App wie erwartet funktionieren.
    
### <a name="aes-support"></a>AES-Unterstützung 

Ab Skype for Business Server 2015 CU5 wird AES für ASP.NET 4,6 nicht unterstützt, was dazu führen kann, dass die APP für Skype-Besprechungen nicht gestartet wird. [Kryptografische Anforderungen aufgrund von ASP .NET 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) enthält weitere Informationen.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_Conferencing"> </a>

[Bereitstellen von Webdownload-Clients in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für die Skype-Besprechungs-App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

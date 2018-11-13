---
title: Planen von Besprechungen-Clients (Web App und Besprechungen App)
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Zusammenfassung: IT-Experten die Support-Anforderungen für die Skype für Business Web App und Skype Besprechungen App sollten beim Planen von Skype für Business Server. In diesem Artikel ist nicht für die Benutzer über diese apps vorgesehen.'
ms.openlocfilehash: c76770d570aaa1d1c686df7b0845e41a767cfbef
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293673"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planen von Besprechungen-Clients (Web App und Besprechungen App)
 
**Zusammenfassung:** IT-Experten sollten die Support-Anforderungen für die Skype für Business Web App und Skype Besprechungen App beim Planen von Skype für Business Server überprüfen. In diesem Artikel ist nicht für die Benutzer über diese apps vorgesehen.
  
Nachdem Sie Skype für Business Server implementiert haben, müssen Benutzer Ihrer Organisation vermutlich die Skype für Business-Client als Teil des Bereitstellungsprozesses installiert. 
  
Höher auf diejenigen Benutzer können Besprechungen erstellen und Benutzer von außerhalb der Organisation einladen, und diese Besprechung eingeladen wurden möglicherweise keine Versionen von der Skype für Business-Client. Wenn diese Benutzer auf die URL für die Besprechung einladen klicken, der Mangel an einen Client wird erkannt, und ohne einen Skype für Business Client eingeladene Benutzer werden aufgefordert, Client herunterladen und installieren einen kompakten, Besprechungen nur so, dass sie die Besprechung beitreten können.
  
> [!NOTE]
> Die Skype für Business Web App und Skype Besprechungen App sind nur verfügbar, wenn Sie versuchen, einer Besprechung anzumelden, ohne dass Skype für Unternehmen. Benutzerhilfe für diese apps wird unter [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Sie können für Business Web App oder Skype Besprechungen App entweder die Skype nicht vor dem installieren, aber [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) und [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) -Benutzer möglicherweise kostengünstigen mobilen Clients installieren, die sie für die Teilnahme an Besprechungen verwenden können.
  
Standardmäßig wird der Hostserver für die Besprechung weisen Sie den Benutzer zum Herunterladen und Installieren von Skype für Business Web App an der Besprechung teilnehmen. Die Skype für Web-Geschäfts-App auf dem Front-End-Server gespeichert ist und ruft an Besprechungsteilnehmer gesendet. 
  
Für Skype für Business Server 2015 Skype Besprechungen App steht als Ersatz für Skype für Web-Geschäfts-App mit CU5 beginnt, aber in [Aktivieren Skype Besprechungen App ersetzen beschriebene zusätzliche Konfiguration erfordert die Skype Besprechungen App bereitstellen Skype für Business Web App (Optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Skype-Besprechungen App aktiviert ist, wird die neueste Version der app aus der Office 365 Content Delivery Network (CDN) und nicht aus Ihrer Skype für Business Server herunterladen werden. Für Skype für Business Server 2019 Skype Besprechungen App ist die einzige Option.
  
Skype-Besprechungen App bietet eine vereinfachte Browserumgebung zum Herunterladen und Installieren der app und teilnehmen an Besprechungen, einschließlich per Mausklick Join für Benutzer von Internet Explorer. Skype-Besprechungen App hat auch zahlreichen Verbesserungen TheSkype für Web-Geschäfts-App für Zuverlässigkeit und die besprechungsumgebung. 
  
> [!NOTE]
> Ab Skype für Business Server 2015 CU5 oder höher Besprechungen vergleichbar, die mithilfe der Skype für Business Online werden nicht mehr senden einem Objektserver Benutzer die Skype für Web-Geschäfts-App, stattdessen Skype Besprechungen App gesendet. Ab Skype für Business Server 2015 CU5 oder höher, wenn Sie [Skype Besprechungen-App ersetzen Skype für Business Web App (Optional) aktivieren](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), Objektserver Benutzern Skype Besprechungen App anstelle von Skype für Business Web App nicht gesendet werden. 
  
## <a name="software-requirements"></a>Softwareanforderungen
<a name="OS-Browser"> </a>

Verwendung der Skype für Business Web App, die ein Benutzer muss eine der folgenden Betriebssystem und Browser Kombinationen unterstützt haben. 
  
**Betriebssystem und minimale Browserunterstützung für Skype für Business Web App**

| Betriebssystem | Edge | 32- und 64-Bit InternetExplorer 11 oder höher | 32- und 64-Bit InternetExplorer 10 oder höher | 32- und 64-Bit InternetExplorer 9 oder höher | 32- und 64-Bit-Version von Safari 6.2.8 - 11.X | 32- und 64-Bit Version von Chrome 18.X oder höher |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Ja  <br/> |Ja  <br/> |n/v  <br/> |n/v  <br/> |n/v  <br/> |Ja & #x 2778; <br/> |
|Windows 8.1 & #x 2776; <br/> |n/v  <br/> |Ja  <br/> |n/v  <br/> |n/v  <br/> |n/v <br/> |Ja & #x 2778; <br/> |
|Windows 8 (Intel-basiert) & #x 2776; <br/> |n/v  <br/> |n/v  <br/> |Ja  <br/> |n/v <br/> |n/v  <br/> |Ja & #x 2778; <br/> |
|Windows 7 mit SP1 & #x 2777; <br/> |n/v  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |n/v <br/>|Ja & #x 2778; <br/> |
|Windows Server 2008 R2 mit SP1 & #x 2777; <br/> |n/v  <br/> |Ja  <br/> |Ja  <br/> |Ja  <br/> |n/v <br/>|Ja & #x 2778; <br/> |
|Mac OS 10,8 und höher (Intel-basiert) & #x 2777; <br/> |n/v  <br/> |n/v  <br/> |n/v  <br/> |n/v  <br/> |Ja  <br/> |Ja <br/> |
   
& #x 2776; Die Skype für Web-Geschäfts-App-Browser-Plug-in erfordert eine bestimmte Freigabe-Plug-Ins computerbasierter, Video, Freigabe und Anzeige von laufenden Bildschirmfreigabe und anderen Features verwenden. Ein Teilnehmer der Besprechung erhält die Option zum Installieren der Freigabe-Plug-in beim Beitritt zu der Besprechung oder wenn sie eines dieser Features initiieren. Unter Windows 8 und Windows 8.1 kann die Freigabe-Plug-In installiert werden nur, wenn Sie Internet Explorer 10 oder Internet Explorer 11 für den Desktop ausführen. Diese Funktionen sind mit anderen (Nicht-Desktop-) Versionen von Internet Explorer 10 oder Internet Explorer 11 nicht verfügbar. Beachten Sie, dass Firefox und Safari Version 12.0 oder höher nicht mehr unterstützt werden.
  
& #x 2777; Klicken Sie auf unterstützte Windows 7, Windows Server 2008 R2 und Macintosh-Betriebssysteme sind alle Features verfügbar, einschließlich computerbasierter, Video, Anwendung anzeigen, Anwendungsfreigabe, desktop anzeigen und Desktopfreigabe. Um diese Funktionen zu verwenden, müssen Sie ein Plug-In installieren, wenn Sie dazu aufgefordert werden. Mac OS X Version 10.7 wird nicht mehr unterstützt.
  
& #x 2778; Zugreifen auf das Web App von Chrome unter Windows wird ein kleines Programm gestartet, das um die Web-App in einem eingebetteten Internet Explorer-Frame zu laden. Damit die Web-App richtig geladen wird, muss eine der unterstützten Versionen von Internet Explorer installiert sein.
  
> [!NOTE]
> Office 365-Benutzer können InternetExplorer 10 oder höher mit Skype für Unternehmen. 
  
### <a name="skype-meetings-app"></a>Skype-Besprechungs-App

Die Skype Besprechungen App als einer app auf Computern mit Windows 10, Windows 8.1, Windows 8, Windows 7 mit 32- und 64-Bit Internet Explorer 11 ausgeführt oder höher installiert sein. 
  
Die app führt auch auf Mac OS 10.10 oder spätere Betriebssysteme mit keine bestimmten Browser Abhängigkeit. 
  
Informationen zu anderen Abhängigkeiten finden Sie unter [Unterstützte Plattformen für die Skype-Besprechungs-App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001).
  
## <a name="hardware-requirements"></a>Hardwareanforderungen
<a name="OS-Browser"> </a>

Die Anforderungen an die Computerhardware sind vom Betriebssystem und vom Browser abhängig. Für die Sprach- und Telefoniefunktionen werden ein Mikrofon und Lautsprecher, ein Headset mit Mikrofon oder ein ähnliches Gerät benötigt, das mit dem Computer kompatibel ist. Für die Videofunktionen ist ein Videogerät erforderlich, das mit dem Computer kompatibel ist. Ausführliche Informationen zur Unterstützung der Videohardware und erwartenden Videoqualität finden Sie unter [Skype für Business Client Auflösung](video-resolutions.md).
  
## <a name="network-requirements"></a>Netzwerkanforderungen
<a name="Network"> </a>

Wenn ein Benutzer von Skype für Business Web App oder Skype Besprechungen App Erfahrungen meeting Verbindungsproblemen, sind wahrscheinlich, dass ihre Organisation Netzwerkinfrastruktur zur Unterstützung von Office 365 nicht konfiguriert ist, wie beschrieben in [Office 365-URLs und IP-Adressbereiche](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Dies ist der Fall, ob die Besprechung für Business Server von einem Benutzer von Skype für Business Online oder Skype erstellt wurde. 
  
Wenn der Benutzer ist in einem Netzwerk nicht wie beschrieben konfiguriert, viele app Features oder funktionieren möglicherweise nicht und sie möglicherweise nicht zur Besprechung überhaupt eine Verbindung herstellen.
  
## <a name="supported-meetings-features"></a>Unterstützte Besprechungsfunktionen
<a name="BKMK_Conferencing"> </a>

Die folgende Tabelle vergleicht die besprechungsfunktionen für Benutzer des Skype für Business-Client, der Skype für Web-Geschäfts-App, Skype Besprechungen App und Lync Web App. Lync Web App wird zu Vergleichszwecken Feature aufgelistet: ein Benutzer würde nur herunterladen und Lync Web App verwenden, wenn die Besprechung auf einem Lync 2013-Server gehostet wurde.

| Feature/Funktion | Skype für Business 2016 oder 2019 client | Skype für Unternehmen auf Mac-client | Skype-Besprechungs-App | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Computeraudio hinzufügen  <br/> |& #x 2714;|& #x 2714;|& #x 2714; (erfordert plug-in)  <br/> |& #x 2714; (erfordert plug-in)  <br/> |& #x 2714; (erfordert plug-in)  <br/> |
|Video hinzufügen  <br/> |& #x 2714;|& #x 2714;|& #x 2714; (erfordert plug-in)  <br/> |& #x 2714; (erfordert plug-in)  <br/> |& #x 2714; (erfordert plug-in)  <br/> |
|Audio für authentifizierte Teilnehmer zu einem Telefon wechseln  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Audio für Gastteilnehmer zu einem Telefon wechseln  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|||
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Videobasierte Bildschirmübertragung  <br/> |& #x 2714;|& #x 2714; <br/> |& #x2714;(View-only)  <br/> |||
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Auf detaillierte Teilnehmerliste der Besprechung zugreifen  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|An Chats mit mehreren Teilnehmern teilnehmen  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|„Hohe Priorität“ für Chatnachrichten festlegen  <br/> |& #x 2714;|||||
|Desktop freigeben (sofern aktiviert)  <br/> |& #x 2714;|& #x 2714;|& #x 2714; (erfordert plug-in)  <br/> |& #x 2714; (erfordert plug-in)  <br/> |& #x 2714; (erfordert plug-in)  <br/> |
|Programm freigeben (sofern aktiviert)  <br/> |& #x 2714;||& #x 2714; (nur unter Windows; erfordert plug-in)  <br/> |& #x 2714; (nur unter Windows; erfordert plug-in)  <br/> |& #x 2714; (nur unter Windows; erfordert plug-in)  <br/> |
|Übernehmen der Steuerung eines freigegebenen Desktops oder Programms eines anderen Benutzers  <br/> |& #x 2714;||& #x 2714; (& #x 2776; Klicken Sie auf nur Windows; erfordert plug-in)  <br/> |& #x 2714; (& #x 2776; Klicken Sie auf nur Windows; erfordert plug-in)  <br/> |& #x 2714; (& #x 2776; Klicken Sie auf nur Windows; erfordert plug-in)  <br/> |
|Einem anderen Benutzer die Steuerung Ihres freigegebenen Desktops oder Programms überlassen  <br/> |& #x 2714;|||||
|Anonyme Teilnehmer hinzufügen (sofern aktiviert)  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Teilnehmer nach Namen einladen  <br/> |& #x 2714;|& #x 2714;||||
|Teilnehmer nach Telefonnummern einladen  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Teilnehmer nach E-Mail-Adressen einladen  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Dial-in-Audiobesprechungen verwenden  <br/> |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |& #x 2714; & #x 2777; |
|Besprechung mit „Jetzt besprechen“ initiieren  <br/> |& #x 2714;|& #x 2714;||||
|Eine Besprechung aufzeichnen  <br/> |& #x 2714;|||||
|Anlagen hinzufügen und herunterladen  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Microsoft PowerPoint-Dateien hinzufügen und präsentieren  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|In Microsoft PowerPoint-Dateien navigieren  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|OneNote-Besprechungsnotizen hinzufügen und bearbeiten  <br/> |& #x 2714;||Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |Nur bearbeiten (nicht hinzufügen)  <br/> |
|Whiteboard verwenden  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Umfragen durchführen  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Dateien zur gemeinsamen Verwendung mit anderen hochladen  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Besprechung oder Konferenz planen  <br/> |Outlook oder Skype für Business-Webplaner  <br/> |Outlook oder Skype für Business-Webplaner  <br/> |Skype für Business-Webplaner  <br/> |Skype für Business-Webplaner  <br/> |Skype für Business-Webplaner  <br/> |
|Q&amp;ein Manager  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Teilnehmervideo deaktivieren  <br/> |& #x 2714;|||||
|Besprechungschat deaktivieren  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|Teilnehmer stummschalten  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|Alle zu Teilnehmern machen  <br/> |& #x 2714;|||||
|Skype Meeting Broadcast erstellen  <br/> |& #x 2714;|||||
   
 & #x 2776;  Teilnehmer können nicht Desktops steuern, die von Skype für Unternehmen für Mac, Lync für Mac 2011 oder Communicator für Mac 2011 Benutzer freigegeben werden. Auch für die Skype for Business Web App unter Mac OS X funktioniert das nicht.
  
 & #x 2777;  Dieses Feature erfordert Microsoft PSTN-Konferenz, Exchange Unified Messaging, Skype für Business Online oder ein 3rd von Drittanbietern für Audiokonferenzen.
  
 & #x 2778;  Lync für Mac 2011-Client kann nicht Microsoft Office 2013 PowerPoint-Präsentationen anzeigen, wenn sie an einer Konferenz mithilfe der Skype für Business Web App freigegeben wurden.
  
## <a name="known-issues-and-troubleshooting"></a>Bekannte Probleme und Problembehandlung
<a name="BKMK_Conferencing"> </a>

Für die Endbenutzer ist die [online-Hilfe](https://aka.ms/smahelp) für diese apps immer leicht zugänglich sind. IT-Experten sollten die folgenden Punkte beachten:
  
- Wenn der Benutzer nicht in einem Netzwerk ist so konfiguriert, dass die [Netzwerk-Anforderungen](meetings-clients.md#Network)erfüllen, zahlreiche Features für die app können oder funktionieren möglicherweise nicht und sie möglicherweise nicht mit der Besprechung verbinden.
    
- Einige Benutzer haben möglicherweise im Unternehmen verwaltet von Computern mit deaktivierten Berechtigung-apps installieren. für diese Benutzer weder app ist eine Option, aber [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) und [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) -Benutzer möglicherweise kostengünstigen mobilen Clients installieren, die sie für die Teilnahme an Besprechungen verwenden können.
    
    Andere Probleme bei der Installation werden auch in den [Hilfethemen](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)behandelt. 
    
- Benutzer sehen möglicherweise eine Warnung beim ersten Firewall führen Sie die app Besprechungen. Sie werden aufgefordert, öffnen Sie Ports so, dass die benutzerfreundlichkeit und dafür möglicherweise Administratorrechte auf dem Computer, den sie möglicherweise nicht erforderlich. Die app sollten weiterhin funktionsfähig, und der Benutzer kann zum Öffnen der angeforderten Ports sicher ablehnen. 
    
- Benötigen Sie [ActiveX ohne Filterung aktiviert](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer, selbst wenn IE nicht wird als Standardbrowser. In Skype für Business Web App ein ActiveX-Steuerelement – ein kleines Modul, die zusätzliche Features einer Web-app oder ein anderes Programm hinzufügt – für Audio-, Video- und Bildschirmfreigabe ist erforderlich.
    
- Für einige Features von Skype für Business Web App ordnungsgemäß funktioniert müssen Sie Ihren Browser zum [Speichern von Cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) auf Ihrem Computer oder Gerät zulassen.
    
- Sie können zum [Aktivieren von JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) in Ihrem Browser für einige Skype für Business Web App-Funktionen erwartungsgemäß unterstützen müssen.
    
### <a name="aes-support"></a>AES-Unterstützung 

Ab Skype für Business Server 2015 CU5 AES für ASP.NET 4.6 nicht unterstützt wird, und dadurch kann Skype Besprechungen App zu einem Fehler beim Starten. [Kryptografische Anforderungen aufgrund von ASP .NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) hat weitere Details.
  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="BKMK_Conferencing"> </a>

[Bereitstellen Sie herunterladbare Webclients in Skype für Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Unterstützte Plattformen für Skype Besprechungen App](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

---
title: Vergleich der Funktionen des mobilen Clients für Skype for Business
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
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Zusammenfassung: Überprüfen Sie die Featureunterstützung für den mobilen Client, während Sie Skype for Business Server planen.'
ms.openlocfilehash: cdd6e5d5afc95fe6488ee89ed96739963b5f5ac0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825995"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Vergleich der Funktionen des mobilen Clients für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie die Featureunterstützung für den mobilen Client, während Sie Skype for Business Server planen.
  
In diesem Artikel werden die Features und Funktionen zwischen mobilen Skype for Business-Clients und dem Skype for Business-Desktopclient in den folgenden Kategorien verglichen:
  
- Anmeldung, Pushbenachrichtigungen und allgemeine Features
    
- Erweiterte Anwesenheit
    
- Kontakte und Kontaktgruppen
    
- Sofortnachrichten
    
- Audio- und Videodaten von Skype for Business zu Skype for Business
    
- Konferenzen
    
- Telefonie
    
- Externe Benutzer
    
- Archivierung und Kompatibilität
    
-  Moderne Authentifizierung
    
In den folgenden Tabellen sind die Funktionen aufgeführt, die Skype for Business-Benutzern in einer lokalen Bereitstellung von Skype for Business Server zur Verfügung stehen. Dieselben Features sind auch für Skype for Business Online- und Microsoft 365- oder Office 365-Benutzer verfügbar, sofern nicht anders in den Fußnoten der Tabelle angegeben.
  
> [!NOTE]
> Onlinehilfe und Ressourcen für Endbenutzer finden Sie unter ["Skype for Business entdecken".](https://go.microsoft.com/fwlink/p/?LinkId=528686) 
  
> [!NOTE]
> Einen Vergleich der funktionen, die in anderen Skype for Business-Clients verfügbar sind, finden Sie im Vergleich der [Desktopclientfunktionen für Skype for Business.](desktop-feature-comparison.md) 

> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Anmeldung, Pushbenachrichtigungen und allgemeine Features

 
 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-Sitzung bleibt angemeldet  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Unterstützung für Pushbenachrichtigungen  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|Kontoinformationen für mehrere Benutzer können auf demselben Gerät zwischengespeichert werden  <br/> |&#x2714;||||
|Sprachausgabe/Sprachausgabe  <br/> |&#x2714;|&#x2714; &#x2777;           nur Englisch  <br/> |&#x2714;|&#x2714;|
|Verwenden einer externen Tastatur für Barrierefreiheit  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Support für das Programm zur Verbesserung der Benutzererfahrung von Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business Windows Phone nach einer bestimmten Zeit der Inaktivität automatisch ab, wie folgt:
  
- Wenn der Benutzer Pushbenachrichtigungen aktiviert hat, meldet sich Skype for Business nach 10 Tagen Inaktivität ab.
    
- Wenn der Benutzer keine Pushbenachrichtigungen aktiviert hat, meldet sich Skype for Business ab, sobald der Benutzer die App verlässt.
    
Auf iOS-Geräten meldet sich Skype for Business automatisch ab, nachdem der mobile Client den Server 10 Tage lang aufgrund von Netzwerkkonnektivitätsverlusten oder anderen Problemen nicht kontaktiert hat.
  
 &#x2777; nur in der App.
  
 &#x2778; Benachrichtigungen sind verfügbar, wenn die App im Hintergrund ausgeführt wird.
 
 &#x2779; sowohl Google/Android/GCNS als auch Apple/APNS mobile Benachrichtigungsdienste verwenden https/TLS-Verschlüsselung für die Zustellung von Benachrichtigungen. Die Benachrichtigungsnutzlast wird im Nur-Text-Text verarbeitet, während sie vom Benachrichtigungsanbieter verarbeitet wird.
 
-   Skype for Business für Android empfängt einfache Benachrichtigungen (über GCNS übermittelt) ohne Kundendaten.
-   Skype for Business für iOS empfängt Benachrichtigungen (über APNS übermittelt), die Kundendaten für den Anruf oder die Nachricht enthalten können.
 
  
## <a name="enhanced-presence-support"></a>Erweiterte Anwesenheitsunterstützung


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Status veröffentlichen und anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Statushinweise und Abwesenheitsnotizen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Benutzerdefinierten Standort hinzufügen  <br/> |&#x2714;||||
|Eigene Notiz hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Kalenderinformationen  <br/> |&#x2714; &#x2776; ||||
|Festlegen des manuellen Anwesenheitsstatus (z. B. "Beschäftigt", "Nicht stören" und so weiter)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; mobilen Skype for Business-Clients aktualisieren die Anwesenheit eines Benutzers nicht basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn ein mobiler Clientbenutzer auch beim Skype for Business-Desktopclient angemeldet ist, aktualisiert der Desktopclient die Anwesenheit des Benutzers basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn der Benutzer nur bei einem mobilen Client angemeldet ist, wird die Anwesenheit des Benutzers nicht basierend auf Frei/Gebucht-Kalenderinformationen aktualisiert.
  
## <a name="contacts-and-contact-groups-support"></a>Support für Kontakte und Kontaktgruppen


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Kontaktliste anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktgruppen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gruppe "Häufige Kontakte anzeigen"  <br/> |&#x2714;||||
|Kontaktliste ändern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen  <br/> |&#x2714;||||
|Private Beziehungen verwalten  <br/> |&#x2714;||||
|Unternehmensadressbuch durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Liste "Kontakte durchsuchen"  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktgruppen verwalten  <br/> |&#x2714;|||&#x2714;|
|Erweitern von Verteilergruppen  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Nach Reaktionsgruppen suchen  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Anzeigen oder Ausblenden von Kontaktfotos  <br/> |&#x2714;|&#x2714;|||
|Anheften eines Kontakts an den Startbildschirm  <br/> ||&#x2714;|||
   
 &#x2776; Nicht verfügbar für Skype for Business Online- und/oder Microsoft 365- oder Office 365-Benutzer.
  
## <a name="instant-messaging-support"></a>Sofortnachrichtenunterstützung


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Initiieren von Chatnachrichten mit einem Kontakt  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Einladen anderer Personen aus dem Unterhaltungsfenster  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen aktueller Unterhaltungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zwischen mehreren Sofortnachrichtenunterhaltungen navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Automatisches Protokollieren von Chatunterhaltungen in Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Senden einer Unterhaltung mit Einer Nachricht als E-Mail  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|E-Mail an Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen von Einladungen für verpasste E-Mail-Enfeinungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrieren mit eingehenden Imitieren  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; Dieses Gerät vibriert jedes Mal, wenn eine Nachricht empfangen wird, auch wenn die aktuelle Nachricht in der Unterhaltung mit Denknachrichten angezeigt wird
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Audio- und Videodaten von Skype for Business zu Skype for Business


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-zu-Skype for Business Voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-zu-Skype for Business-Video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Für Video auf einem mobilen Gerät ist standardmäßig eine WLAN-Verbindung erforderlich. 
  
## <a name="conferencing-support"></a>Konferenzunterstützung


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Klicken Sie auf einen Link in der Besprechungserinnerung, um an einer Video- oder Einer -VoIP-Besprechung teil zu nehmen.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Einwahlkonferenzen (Server ruft das mobile Gerät an)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Einwahlaudiokonferenzen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen des Besprechungsvideos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video mit mehrerenPartys anzeigen (Katalogansicht)  <br/> |&#x2714;||||
|Warten in Besprechungslobby  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;||||
|Zugreifen auf detaillierte Besprechungsliste für Audiokonferenzen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zugreifen auf detaillierte Besprechungsliste für Im-Im-Konferenzen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Desktop oder Programm freigeben  <br/> |&#x2714;||||
|Anzeigen freigegebener Desktops oder Programme (VbSS oder RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Anzeigen freigegebener PowerPoint-Dateien  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Hochladen und Präsentieren von PowerPoint-Dateien  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Verwenden von Besprechungstools (Whiteboard verwenden, Umfragen durchführen, Dateien freigeben)  <br/> |&#x2714;||||
|Navigieren in einer Liste Ihrer Besprechungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An einer Besprechung teilnehmen, auch wenn Sie kein Skype for Business-Konto haben  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Weitere Informationen zu Besprechungsteilnehmern anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Starten einer ungeplanten Gruppengespräch mit mehreren Teilnehmern direkt von Ihrem Client oder Gerät aus  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; für Microsoft 365- oder Office 365-Benutzer erfordert dieses Feature Enterprise-VoIP, das Teil der E5-Lizenz ist.
  
 &#x2777; erfordert standardmäßig eine WLAN-Verbindung.
 
 &#x2778; Anzeigen eingebetteter Videos in PowerPoint-Präsentationen wird nicht unterstützt.
  
## <a name="telephony-support"></a>Telefonieunterstützung


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Tippen Sie in Skype for Business auf das Anrufsymbol, um einen Kontakt an anrufen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten  <br/> |&#x2714;|&#x2714;|&#x2714;||
|15.000  <br/> |&#x2714; &#x2778; ||||
|Anrufweiterleitung verwalten  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Einstellungen für Teamanruf verwalten  <br/> |&#x2714; &#x2776; ||||
|Verwalten von Stellvertretungen  <br/> |&#x2714; &#x2776; ||||
|Anruf an eine Reaktionsgruppe initiieren  <br/> |&#x2714; &#x2776; ||||
|Unterstützen von Notrufdiensten  <br/> |&#x2714; &#x2777; ||||
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario)  <br/> |&#x2714; &#x2776; ||||
|Behandeln von Anrufen eines anderen Kontakts, sofern diese als Stellvertretung konfiguriert sind  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Verwenden von "Anruf über Arbeit"  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Zugreifen auf Voicemail  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Verwenden der Tastatur in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; Verfügbar für Skype for Business Online- und/oder Office 365 E5-Benutzer sowie für Benutzer, die in Skype for Business Server oder Lync Server 2013 mit aktivierter Enterprise-VoIP sind.
  
 &#x2777; Für Skype for Business Online- und/oder Microsoft 365- oder Office 365-Benutzer wird diese Funktion von Microsoft-Partnern unterstützt.
  
 &#x2778; windows-Desktopclient.
  
## <a name="external-user-support"></a>Unterstützung externer Benutzer


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Sofortnachricht mit öffentlichem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Sofortnachricht mit Partnerkontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufe mit zwei Parteien mit externen Benutzern durchführen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Durchführen von Anrufen mit mehrerenPartys mit externen Benutzern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden Sie "Anruf über Arbeit", um einen Verbundkontakt auf dem Mobiltelefon zu erreichen, indem Sie die veröffentlichte Arbeitsnummer &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Standardmäßig wird Verbundbenutzern die Datenschutzbeziehung "Externe Kontakte" zugewiesen. Um einen Verbundkontakt auf dem Mobiltelefon über seine veröffentlichte Arbeitsnummer erreichen zu können, muss ihnen der Verbundkontakt manuell die Datenschutzbeziehung "Kollegen" zuweisen.
  
## <a name="address-book-integration"></a>Adressbuchintegration


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Adressbuchkontakte des Anrufgeräts  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Direktes Senden von Skype for Business-Anrufen an Kontakte aus dem Geräteadressenbuch  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Archivierungs- und Kompatibilitätsunterstützung


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clientseitige Archivierung bereitstellen  <br/> |&#x2714;||||
|Clientseitige Aufzeichnung bereitstellen  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; Nicht verfügbar für Skype for Business Online- und/oder Microsoft 365- oder Office 365-Benutzer.
  
## <a name="modern-authentication"></a>Moderne Authentifizierung

Diese Tabelle enthält Features, die Unterstützung für die moderne Authentifizierung erfordern.
  
Die moderne Authentifizierung erfordert auch eine Topologie, die in [Skype for Business-Topologien](../../plan-your-deployment/modern-authentication/topologies-supported.md)beschrieben wird, die mit moderner Authentifizierung unterstützt werden.
  

 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Moderne Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung  <br/> |&#x2714;(nur in die Domäne eingetretenes Gerät)  <br/> ||&#x2714;|&#x2714;|
|Verwaltung mobiler Anwendungen (über Intune)  <br/> |||&#x2714;|&#x2714;|
   


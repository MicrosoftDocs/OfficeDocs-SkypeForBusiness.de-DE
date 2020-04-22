---
title: Vergleich der Funktionen eines mobilen Clients für Skype for Business
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
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Zusammenfassung: Überprüfen Sie die Funktionsunterstützung für den mobilen Client, während Sie Skype for Business Server planen.'
ms.openlocfilehash: 36ae93e796e4142a9ae3b5fb85ac806c9a38cdca
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777770"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Vergleich der Funktionen eines mobilen Clients für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie die Funktionsunterstützung für den mobilen Client, während Sie Skype for Business Server planen.
  
In diesem Artikel werden die Features und Funktionen zwischen Skype for Business mobilen Clients und dem Skype for Business-Desktop Client in den folgenden Kategorien verglichen:
  
- Anmeldung, Push-Benachrichtigungen und allgemeine Features
    
- Erweiterte Anwesenheit
    
- Kontakte und Kontaktgruppen
    
- Sofortnachrichten
    
- Skype for Business zum Skype for Business von Audio und Video
    
- Konferenzen
    
- Telefonie
    
- Externe Benutzer
    
- Archivierung und Kompatibilität
    
-  Moderne Authentifizierung
    
In den folgenden Tabellen sind die Features aufgeführt, die für Skype for Business Benutzer in einer lokalen Bereitstellung von Skype for Business Server verfügbar sind. Die gleichen Funktionen stehen auch Skype for Business Online-und Microsoft 365-oder Office 365-Benutzern zur Verfügung, sofern in den Tabellen Fußnoten nichts anderes angegeben ist.
  
> [!NOTE]
> Online Hilfe und Ressourcen für Endbenutzer finden Sie unter [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Informationen zum Vergleich der in anderen Skype for Business Clients verfügbaren Features finden Sie unter [Desktop Client Feature Comparison for Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle aktuellen Skype for Business mobilen Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit älteren Clients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Anmeldung, Push-Benachrichtigungen und allgemeine Features

 
 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business Sitzung bleibt angemeldet  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Unterstützung für Push-Benachrichtigungen  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|Kontoinformationen für mehrere Benutzer können auf demselben Gerät zwischengespeichert werden  <br/> |&#x2714;||||
|Screenreader/Voice over  <br/> |&#x2714;|Nur &#x2714; &#x2777;  Englisch  <br/> |&#x2714;|&#x2714;|
|Verwenden einer externen Tastatur für Barrierefreiheit  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Support für das Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; auf Windows Phone Skype for Business meldet sich nach einem Zeitraum der Inaktivität wie folgt automatisch ab:
  
- Wenn der Benutzer Push-Benachrichtigungen aktiviert hat, Skype for Business sich nach 10 Tagen Inaktivität abmeldet.
    
- Wenn der Benutzer keine Push-Benachrichtigungen aktiviert hat, meldet sich Skype for Business, sobald der Benutzer die APP verlässt.
    
Auf IOS-Geräten meldet sich Skype for Business automatisch ab, nachdem der Mobile Client aufgrund eines Verlusts von Netzwerkkonnektivität oder anderen Problemen 10 Tage lang keinen Kontakt mit dem Server hergestellt hat.
  
 &#x2777; nur in der app.
  
 &#x2778; Benachrichtigungen stehen zur Verfügung, wenn die APP im Hintergrund ausgeführt wird.
 
 &#x2779; sowohl Google/Android/GCNS als auch Apple/APNS Mobile Notification Services verwenden die HTTPS/TLS-Verschlüsselung für die Zustellung von Benachrichtigungen. Die Benachrichtigungs Nutzlast wird beim Verarbeiten durch den Benachrichtigungsanbieter als nur-Text behandelt.
 
-   Skype for Business für Android erhält einfache Benachrichtigungen (über GCNS übermittelt) ohne Kundendaten.
-   Skype for Business für IOS empfängt Benachrichtigungen (zugestellt über APNS), die Kundendaten für den Anruf oder die Nachricht enthalten können.
 
  
## <a name="enhanced-presence-support"></a>Erweiterte Anwesenheits Unterstützung


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Status veröffentlichen und anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Statushinweise und Abwesenheitsnotizen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Benutzerdefinierten Standort hinzufügen  <br/> |&#x2714;||||
|Eigene Notiz hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Veröffentlichen des Status basierend auf den Frei/Gebucht-Kalenderinformationen  <br/> |&#x2714; &#x2776; ||||
|Manuellen Anwesenheitsstatus festlegen (beispielsweise "beschäftigt", "nicht stören" usw.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business Mobile Clients wird die Anwesenheit eines Benutzers basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers nicht aktualisiert. Wenn ein mobiler Clientbenutzer ebenfalls beim Skype for Business Desktop Client angemeldet ist, aktualisiert der Desktop Client die Anwesenheit des Benutzers basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn der Benutzer nur bei einem mobilen Client angemeldet ist, wird die Anwesenheit des Benutzers nicht basierend auf Frei/Gebucht-Kalenderinformationen aktualisiert.
  
## <a name="contacts-and-contact-groups-support"></a>Unterstützung für Kontakte und Kontaktgruppen


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Kontaktliste anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen von Kontaktgruppen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gruppe "häufige Kontakte" anzeigen  <br/> |&#x2714;||||
|Kontaktliste ändern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen  <br/> |&#x2714;||||
|Private Beziehungen verwalten  <br/> |&#x2714;||||
|Unternehmensadressbuch durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktliste durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktgruppen verwalten  <br/> |&#x2714;|||&#x2714;|
|Verteilergruppen erweitern  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Nach Reaktionsgruppen suchen  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Anzeigen oder Ausblenden von Kontaktfotos  <br/> |&#x2714;|&#x2714;|||
|Anheften eines Kontakts an Ihren Startbildschirm  <br/> ||&#x2714;|||
   
 &#x2776; nicht für Skype for Business Online-und/oder Microsoft 365-oder Office 365-Benutzer verfügbar.
  
## <a name="instant-messaging-support"></a>Unterstützung für Chatnachrichten


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Sofortnachrichten (Chat) mit einem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Andere Personen aus dem Unterhaltungsfenster einladen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen von aktuellen Unterhaltungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zwischen mehreren Sofortnachrichtenunterhaltungen navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Automatisches Protokollieren von Chat Unterhaltungen in Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Senden einer Chat Unterhaltung als e-Mail-Nachricht  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|E-Mail an Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verpasste Chat Einladungen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrieren mit eingehenden Chatnachrichten  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; dieses Gerät vibriert jedes Mal, wenn ein Chat empfangen wird, auch wenn die aktuelle Nachricht in der Chat Unterhaltung angezeigt wird.
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business zum Skype for Business von Audio und Video


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-zu-Skype for Business-VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-zu-Skype for Business-Video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Für Video auf einem mobilen Gerät ist standardmäßig eine WLAN-Verbindung erforderlich. 
  
## <a name="conferencing-support"></a>Unterstützung von Konferenzen


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Klicken Sie auf einen Link in der Besprechungserinnerung, um an einer Video-oder VoIP-Besprechung teilzunehmen.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Auswahl Konferenzen (Server Ruft das Mobile Gerät an)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Einwahlaudiokonferenzen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Besprechungs Video anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video mit mehreren Teilen anzeigen (Galerieansicht)  <br/> |&#x2714;||||
|Warten in der Besprechungslobby  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;||||
|Zugriff auf detaillierte Besprechungsliste für Audiokonferenzen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zugriff auf detaillierte Besprechungsliste für Chat Konferenzen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Freigeben von Desktop oder Programm  <br/> |&#x2714;||||
|Anzeigen des freigegebenen Desktops oder Programms (VbSS oder RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Anzeigen von freigegebenen PowerPoint-Dateien  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Hochladen und präsentieren von PowerPoint-Dateien  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Verwenden von Besprechungstools (Whiteboard verwenden, Umfragen durchführen, Dateien freigeben)  <br/> |&#x2714;||||
|Navigieren in einer Liste Ihrer Besprechungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An einer Besprechung teilnehmen, auch wenn Sie kein Skype for Business Konto haben  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen weiterer Informationen zu Besprechungsteilnehmern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Starten einer ungeplanten Gruppenunterhaltung mit mehreren Teilnehmern direkt vom Client oder Gerät  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; für Microsoft 365-oder Office 365-Benutzer erfordert dieses Feature Enterprise-VoIP, das Teil der E5-Lizenz ist.
  
 &#x2777; erfordert standardmäßig eine WLAN-Verbindung.
 
 &#x2778; das Anzeigen eingebetteter Videos in PowerPoint-Präsentationen wird nicht unterstützt.
  
## <a name="telephony-support"></a>Telefonie-Unterstützung


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Tippen Sie in Skype for Business auf das Anrufsymbol, um einen Kontakt anzurufen.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Beratende Übertragung  <br/> |&#x2714; &#x2778; ||||
|Anrufweiterleitung verwalten  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Einstellungen für Teamanruf verwalten  <br/> |&#x2714; &#x2776; ||||
|Verwalten von Stellvertretungen  <br/> |&#x2714; &#x2776; ||||
|Anruf an eine Reaktionsgruppe initiieren  <br/> |&#x2714; &#x2776; ||||
|Unterstützung von Notfalldiensten  <br/> |&#x2714; &#x2777; ||||
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario)  <br/> |&#x2714; &#x2776; ||||
|Behandeln der Anrufe eines anderen Kontakts, falls als Stellvertreter konfiguriert  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Verwenden von "Anruf über Arbeit"  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Zugreifen auf Voicemail  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Verwenden der Tastatur in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; für Skype for Business Online-und/oder Office 365 E5-Benutzer sowie für Benutzer verfügbar, die auf Skype for Business Server oder lync Server 2013 mit aktivierter Enterprise-VoIP verwaltet werden.
  
 &#x2777; für Skype for Business Online-und/oder Microsoft 365-oder Office 365-Benutzer wird dieses Feature von Microsoft-Partnern unterstützt.
  
 Nur &#x2778; Windows-Desktop Client.
  
## <a name="external-user-support"></a>Unterstützung für externe Benutzer


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Sofortnachricht mit öffentlichem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Sofortnachricht mit Partnerkontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Durchführen von Anrufen mit zwei Teilnehmern mit externen Benutzern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Durchführen von mehrteiligen anrufen mit externen Benutzern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden Sie die Funktion "Anruf über Arbeit", um einen Verbundkontakt auf Ihrem Mobiltelefon zu erreichen, indem Sie Ihre veröffentlichte Arbeitsnummer aufrufen &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; standardmäßig werden Verbundbenutzern die Datenschutz Beziehung externe Kontakte zugewiesen. Damit Sie einen Verbundkontakt auf Ihrem Mobiltelefon erreichen können, indem Sie Ihre veröffentlichte Arbeitsnummer anrufen, muss der Partner Kontakt Ihnen manuell die Datenschutz Beziehung für Kollegen zuweisen.
  
## <a name="address-book-integration"></a>Adressbuchintegration


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Adressbuchkontakte des Anruf Geräts  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Direktes Skype for Business von Kontakten aus dem Adressbuch des Geräts aus tätigen  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Unterstützung bei Archivierung und Compliance


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clientseitige Archivierung bereitstellen  <br/> |&#x2714;||||
|Clientseitige Aufzeichnung bereitstellen  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; nicht für Skype for Business Online-und/oder Microsoft 365-oder Office 365-Benutzer verfügbar.
  
## <a name="modern-authentication"></a>Moderne Authentifizierung

Diese Tabelle enthält Features, die Unterstützung für die moderne Authentifizierung erfordern.
  
Die moderne Authentifizierung erfordert auch eine Topologie, die in Skype for Business Topologien beschrieben ist, die [mit moderner Authentifizierung unterstützt werden](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Moderne Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung  <br/> |&#x2714; (nur Domäne-registriertes Gerät)  <br/> ||&#x2714;|&#x2714;|
|Verwaltung mobiler Anwendungen (über InTune)  <br/> |||&#x2714;|&#x2714;|
   


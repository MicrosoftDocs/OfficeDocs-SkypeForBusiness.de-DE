---
title: Vergleich der Mobilen Clientfeatures für Skype for Business
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Zusammenfassung: Überprüfen Sie die Featureunterstützung für den mobilen Client, während Sie Skype for Business Server planen.'
ms.openlocfilehash: f1bbb046827ef762f5def1d532089e9621c32b28
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834123"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Vergleich der Mobilen Clientfeatures für Skype for Business
 
**Zusammenfassung:** Überprüfen Sie die Featureunterstützung für den mobilen Client, während Sie Skype for Business Server planen.
  
In diesem Artikel werden die Features und Funktionen zwischen Skype for Business mobilen Clients und dem Skype for Business-Desktopclient in den folgenden Kategorien verglichen:
  
- Anmeldung, Pushbenachrichtigungen und allgemeine Features
    
- Erweiterte Anwesenheit
    
- Kontakte und Kontaktgruppen
    
- Sofortnachrichten
    
- Skype for Business zum Skype for Business von Audio- und Videodaten
    
- Konferenzen
    
- Telefonie
    
- Externe Benutzer
    
- Archivierung und Kompatibilität
    
-  Moderne Authentifizierung
    
In den folgenden Tabellen sind die Features aufgeführt, die Skype for Business Benutzern in einer lokalen Bereitstellung von Skype for Business Server zur Verfügung stehen. Dieselben Features sind auch für Skype for Business Online- und Microsoft 365- oder Office 365-Benutzer verfügbar, sofern in den Fußnoten der Tabelle nichts anderes angegeben ist.
  
> [!NOTE]
> Onlinehilfe und Ressourcen für Endbenutzer finden Sie unter ["Entdecken Skype for Business".](https://go.microsoft.com/fwlink/p/?LinkId=528686) 
  
> [!NOTE]
> Informationen zum Vergleichen der Features, die in anderen Skype for Business Clients verfügbar sind, finden Sie unter Vergleich der [Desktopclientfeatures für Skype for Business.](desktop-feature-comparison.md) 

> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Anmeldung, Pushbenachrichtigungen und allgemeine Features

 
 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business Sitzung bleibt angemeldet  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Unterstützung für Pushbenachrichtigungen  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|Kontoinformationen für mehrere Benutzer können auf demselben Gerät zwischengespeichert werden.  <br/> |&#x2714;||||
|Sprachausgabe/Sprachausgabe  <br/> |&#x2714;|nur &#x2714; &#x2777;           Englisch  <br/> |&#x2714;|&#x2714;|
|Verwenden einer externen Tastatur für Barrierefreiheit  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Support für das Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Am Windows Phone meldet sich Skype for Business nach einem Zeitraum der Inaktivität wie folgt automatisch ab:
  
- Wenn der Benutzer Pushbenachrichtigungen aktiviert hat, meldet sich Skype for Business nach 10 Tagen Inaktivität ab.
    
- Wenn der Benutzer keine Pushbenachrichtigungen aktiviert hat, wird Skype for Business abgemeldet, sobald der Benutzer die App verlässt.
    
Auf iOS-Geräten wird Skype for Business automatisch abgemeldet, nachdem der mobile Client den Server 10 Tage lang aufgrund eines Ausfalls der Netzwerkkonnektivität oder anderer Probleme nicht kontaktiert hat.
  
 nur in der App &#x2777;.
  
 &#x2778; Benachrichtigungen sind verfügbar, wenn die App im Hintergrund ausgeführt wird.
 
 &#x2779; sowohl Google/Android/GCNS als auch apple/APNS mobile Benachrichtigungsdienste verwenden https/TLS-Verschlüsselung für die Übermittlung von Benachrichtigungen. Die Benachrichtigungsnutzlast wird im Nur-Text-Format verarbeitet, während sie vom Benachrichtigungsanbieter verarbeitet wird.
 
-   Skype for Business für Android erhält einfache Benachrichtigungen (über GCNS) ohne Kundendaten.
-   Skype for Business für iOS empfängt Benachrichtigungen (über APNS), die Kundendaten für den Anruf oder die Nachricht enthalten können.
 
  
## <a name="enhanced-presence-support"></a>Erweiterte Anwesenheitsunterstützung


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Status veröffentlichen und anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Statushinweise und Abwesenheitsnotizen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Benutzerdefinierten Standort hinzufügen  <br/> |&#x2714;||||
|Eigene Notiz hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Veröffentlichungsstatus basierend auf Frei/Gebucht-Kalenderinformationen  <br/> |&#x2714; &#x2776; ||||
|Festlegen des manuellen Anwesenheitsstatus (z. B. Beschäftigt, Nicht stören usw.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business mobile Clients aktualisieren die Anwesenheit eines Benutzers nicht basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn ein mobiler Clientbenutzer auch beim Skype for Business Desktopclient angemeldet ist, aktualisiert der Desktopclient die Anwesenheit des Benutzers basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn der Benutzer nur bei einem mobilen Client angemeldet ist, wird die Anwesenheit des Benutzers nicht basierend auf Frei/Gebucht-Kalenderinformationen aktualisiert.
  
## <a name="contacts-and-contact-groups-support"></a>Support für Kontakte und Kontaktgruppen


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Kontaktliste anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen von Kontaktgruppen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen der Gruppe "Häufig auftretende Kontakte"  <br/> |&#x2714;||||
|Kontaktliste ändern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kennzeichnen von Kontakten für Benachrichtigungen bei Statusänderungen  <br/> |&#x2714;||||
|Private Beziehungen verwalten  <br/> |&#x2714;||||
|Unternehmensadressbuch durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktliste durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktgruppen verwalten  <br/> |&#x2714;|||&#x2714;|
|Erweitern von Verteilergruppen  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Nach Reaktionsgruppen suchen  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Anzeigen oder Ausblenden von Kontaktfotos  <br/> |&#x2714;|&#x2714;|||
|Anheften eines Kontakts an Ihren Startbildschirm  <br/> ||&#x2714;|||
   
 &#x2776; für Skype for Business Online- und/oder Microsoft 365- oder Office 365-Benutzer nicht verfügbar.
  
## <a name="instant-messaging-support"></a>Instant Messaging-Unterstützung


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Chatnachrichten mit einem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Einladen anderer Personen aus dem Unterhaltungsfenster  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aktuelle Unterhaltungen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zwischen mehreren Sofortnachrichtenunterhaltungen navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Automatisches Protokollieren von Chatunterhaltungen in Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Senden einer Chatunterhaltung als E-Mail-Nachricht  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|E-Mail an Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen verpasster Chateinladungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrieren mit eingehenden Chatnachrichten  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; Dieses Gerät vibriert jedes Mal, wenn eine Chatnachricht empfangen wird, auch wenn die aktuelle Nachricht in der Chatunterhaltung angezeigt wird
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business zum Skype for Business von Audio und Video


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-zu-Skype for Business-VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-zu-Skype for Business-Video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Video auf einem mobilen Gerät erfordert standardmäßig eine WLAN-Verbindung. 
  
## <a name="conferencing-support"></a>Konferenzunterstützung


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Klicken Sie auf einen Link in der Besprechungserinnerung, um an einem Video oder einer VoIP-Besprechung teilzunehmen.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Sofortnachrichten mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden von Ausgehende Konferenzen (Server ruft das mobile Gerät an)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Einwahlaudiokonferenzen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen des Besprechungsvideos  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht)  <br/> |&#x2714;||||
|Warten im Besprechungslobby  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;||||
|Zugriff auf detaillierte Besprechungslisten für Audiokonferenzen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zugriff auf detaillierte Besprechungslisten für Chatkonferenzen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Freigeben eines Desktops oder Programms  <br/> |&#x2714;||||
|Anzeigen des freigegebenen Desktops oder Programms (VbSS oder RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Anzeigen freigegebener PowerPoint Dateien  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Hochladen und präsentieren PowerPoint Dateien  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Verwenden von Besprechungstools (Whiteboard verwenden, Umfragen durchführen, Dateien freigeben)  <br/> |&#x2714;||||
|Navigieren in einer Liste Ihrer Besprechungen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An einer Besprechung teilnehmen, auch wenn Sie kein Skype for Business Konto haben  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Weitere Informationen zu Besprechungsteilnehmern anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Starten einer ungeplanten Gruppenunterhaltung mit mehreren Teilnehmern direkt von Ihrem Client oder Gerät aus  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; Für Microsoft 365 oder Office 365 Benutzer erfordert dieses Feature Enterprise-VoIP, das Teil der E5-Lizenz ist.
  
 &#x2777; erfordert standardmäßig eine WLAN-Verbindung.
 
 &#x2778; Das Anzeigen eingebetteter Videos in PowerPoint Präsentationen wird nicht unterstützt.
  
## <a name="telephony-support"></a>Telefonieunterstützung


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Tippen Sie in Skype for Business auf das Anrufsymbol, um einen Kontakt anzurufen.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anruf weiterleiten  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Beratungsübertragung  <br/> |&#x2714; &#x2778; ||||
|Anrufweiterleitung verwalten  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Einstellungen für Teamanruf verwalten  <br/> |&#x2714; &#x2776; ||||
|Verwalten von Stellvertretungen  <br/> |&#x2714; &#x2776; ||||
|Anruf an eine Reaktionsgruppe initiieren  <br/> |&#x2714; &#x2776; ||||
|Unterstützen von Notrufdiensten  <br/> |&#x2714; &#x2777; ||||
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertreter-Szenario)  <br/> |&#x2714; &#x2776; ||||
|Verarbeiten von Anrufen eines anderen Kontakts, wenn diese als Stellvertretung konfiguriert sind  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Verwenden von "Anruf über Arbeit"  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Zugreifen auf Voicemail  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Verwenden der Tastatur in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; verfügbar für Skype for Business Online- und/oder Office 365 E5-Benutzer sowie für Benutzer, die auf Skype for Business Server oder Lync Server 2013 verwaltet werden, mit aktivierter Enterprise-VoIP.
  
 &#x2777; Für Skype for Business Online- und/oder Microsoft 365- oder Office 365-Benutzer wird dieses Feature von Microsoft-Partnern unterstützt.
  
 nur &#x2778; Windows Desktopclient.
  
## <a name="external-user-support"></a>Unterstützung externer Benutzer


 | Feature/Funktion  | Skype for Business Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Sofortnachricht mit öffentlichem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Sofortnachricht mit Partnerkontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Durchführen von Anrufen mit zwei Teilnehmern mit externen Benutzern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Durchführen von Anrufen mit mehreren Teilnehmern mit externen Benutzern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Standardmäßig wird Verbundbenutzern die Datenschutzbeziehung für externe Kontakte zugewiesen. Damit Sie einen Verbundkontakt auf dem Mobiltelefon erreichen können, indem er seine veröffentlichte Geschäftliche Nummer aufruft, muss der Verbundkontakt Ihnen manuell die Datenschutzbeziehung "Kollegen" zuweisen.
  
## <a name="address-book-integration"></a>Adressbuchintegration


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Adressbuchkontakte des Anrufgeräts  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Tätigen von Skype for Business Aufrufen von Kontakten direkt aus dem Geräteadressbuch  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Archivierungs- und Complianceunterstützung


 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clientseitige Archivierung bereitstellen  <br/> |&#x2714;||||
|Clientseitige Aufzeichnung bereitstellen  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; für Skype for Business Online- und/oder Microsoft 365- oder Office 365-Benutzer nicht verfügbar.
  
## <a name="modern-authentication"></a>Moderne Authentifizierung

Diese Tabelle enthält Features, die Unterstützung für die moderne Authentifizierung erfordern.
  
Moderne Authentifizierung erfordert auch eine Topologie, die in Skype for Business Topologien beschrieben ist, [die mit moderner Authentifizierung unterstützt werden.](../../plan-your-deployment/modern-authentication/topologies-supported.md)
  

 | Feature/Funktion  | Skype for Business-Desktopclient  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Moderne Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung  <br/> |&#x2714;(nur In die Domäne eingebundenes Gerät)  <br/> ||&#x2714;|&#x2714;|
|Mobile Anwendungsverwaltung (über Intune)  <br/> |||&#x2714;|&#x2714;|
   


---
title: Vergleich der Features für mobile Clients in Skype for Business
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
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Zusammenfassung: Überprüfen Sie die Funktionsunterstützung für den mobilen Client bei der Planung für Skype for Business Server.'
ms.openlocfilehash: 9f85d692dac8be7c2e1fb141ddf575f7bfc1a8f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277307"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Vergleich der Features für mobile Clients in Skype for Business
 
**Zusammenfassung:** Überprüfen Sie die Funktionsunterstützung für den mobilen Client bei der Planung für Skype for Business Server.
  
In diesem Artikel werden die Features und Funktionen von Skype for Business-mobilen Clients und dem Skype for Business-Desktop Client in den folgenden Kategorien verglichen:
  
- Anmeldung, Pushbenachrichtigungen und allgemeine Funktionen
    
- Erweiterte Anwesenheit
    
- Kontakte und Kontaktgruppen
    
- Chat
    
- Skype for Business für Skype for Business-Audio und-Video
    
- Konferenzen
    
- Telefonie
    
- Externe Benutzer
    
- Archivierung und Kompatibilität
    
-  Moderne Authentifizierung
    
In den folgenden Tabellen sind die Features aufgeführt, die Skype for Business-Benutzern in einer lokalen Bereitstellung von Skype for Business Server zur Verfügung stehen. Die gleichen Funktionen sind auch für Skype for Business Online-und Microsoft Office 365-Benutzer verfügbar, sofern in den Tabellen Fußnoten nichts anderes angegeben ist.
  
> [!NOTE]
> Online Hilfe und Ressourcen für Endbenutzer finden Sie unter [Entdecken von Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Informationen zum Vergleich der Features, die in anderen Skype for Business-Clients zur Verfügung stehen, finden Sie unter [Vergleich der Desktop-Clientfunktionen für Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Anmeldung, Pushbenachrichtigungen und allgemeine Funktionen

 
 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-Sitzung bleibt angemeldet  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Unterstützung von Pushbenachrichtigungen  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|Kontoinformationen für mehrere Benutzer können auf demselben Gerät zwischengespeichert werden  <br/> |&#x2714;||||
|Sprachausgabe/Voiceover  <br/> |&#x2714;|&#x2714; &#x2777;           Nur Englisch  <br/> |&#x2714;|&#x2714;|
|Verwenden einer externen Tastatur zugunsten der Barrierefreiheit  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Unterstützung für das Programm zur Verbesserung der Benutzerfreundlichkeit von Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Unter Windows Phone meldet sich Skype for Business nach einem Zeitraum der Inaktivität wie folgt automatisch ab:
  
- Wenn der Benutzer Push-Benachrichtigungen aktiviert hat, meldet sich Skype for Business nach 10 Tagen Inaktivität ab.
    
- Wenn der Benutzer keine Push-Benachrichtigungen aktiviert hat, meldet sich Skype for Business ab, sobald der Benutzer die APP verlässt.
    
Auf IOS-Geräten meldet sich Skype for Business automatisch ab, nachdem der Mobile Client 10 Tage lang keinen Kontakt mit dem Server aufgenommen hat, weil die Netzwerkverbindung unterbrochen wurde oder andere Probleme auftreten.
  
 &#x2777;  Nur in der app.
  
 &#x2778;  Benachrichtigungen stehen zur Verfügung, wenn die APP im Hintergrund ausgeführt wird.
  
## <a name="enhanced-presence-support"></a>Unterstützung von erweiterten Anwesenheitsinformationen


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Status veröffentlichen und anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Statushinweise und Abwesenheitsnotizen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Benutzerdefinierten Standort hinzufügen  <br/> |&#x2714;||||
|Benutzerdefinierte Notiz hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) veröffentlichen   <br/> |&#x2714; &#x2776; ||||
|Anwesenheitsstatus manuell festlegen (z. B. gebucht, nicht stören usw.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business Mobile-Clients aktualisieren die Anwesenheit eines Benutzers nicht basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn ein mobiler Clientbenutzer ebenfalls bei dem Skype for Business-Desktop Client angemeldet ist, aktualisiert der Desktop Client die Anwesenheit des Benutzers basierend auf den Frei/Gebucht-Kalenderinformationen des Benutzers. Wenn der Benutzer nur bei einem mobilen Client angemeldet ist, wird die Anwesenheit des Benutzers nicht basierend auf Frei/Gebucht-Kalenderinformationen aktualisiert.
  
## <a name="contacts-and-contact-groups-support"></a>Unterstützung von Kontakten und Kontaktgruppen


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Kontaktliste anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktgruppen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gruppe „Häufig verwendete Kontakte“ anzeigen  <br/> |&#x2714;||||
|Kontaktliste ändern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontakte für Statusänderungsbenachrichtigungen markieren  <br/> |&#x2714;||||
|Private Beziehungen verwalten  <br/> |&#x2714;||||
|Unternehmensadressbuch durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktliste durchsuchen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Kontaktgruppen verwalten  <br/> |&#x2714;|||&#x2714;|
|Verteilergruppen erweitern  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Nach Reaktionsgruppen suchen  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Kontaktfotos ein- oder ausblenden  <br/> |&#x2714;|&#x2714;|||
|Kontakt an Startseite anheften  <br/> ||&#x2714;|||
   
 &#x2776;  Nicht verfügbar für Skype for Business Online-und/oder Office 365-Benutzer.
  
## <a name="instant-messaging-support"></a>Unterstützung von Chatfunktionen


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Chatnachrichten mit einem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Chats mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Andere vom Unterhaltungsfenster aus einladen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aktuelle Unterhaltungen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zwischen mehreren Chatunterhaltungen navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Chatnachrichtenunterhaltungen in Exchange automatisch protokollieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Chatnachrichtenunterhaltung in einer E-Mail-Nachricht senden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|E-Mail an Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verpasste Chatnachrichteneinladungen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Bei eingehenden Chatnachrichten vibrieren  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;  Dieses Gerät vibriert jedes Mal, wenn ein Chat empfangen wird, auch wenn die aktuelle Nachricht in der Chat Unterhaltung angezeigt wird
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business für Skype for Business-Audio und-Video


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-zu-Skype for Business-VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-zu-Skype for Business-Video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Für Video auf einem mobilen Gerät ist eine standardmäßige WLAN-Verbindung erforderlich.  
  
## <a name="conferencing-support"></a>Konferenzunterstützung


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In einer Besprechungserinnerung auf einen Link klicken, um an einer Video- oder VoIP-Besprechung teilzunehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|An Chats mit mehreren Teilnehmern teilnehmen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Dial-Out-Konferenzen verwenden (Server ruft das mobile Gerät an)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Einwahlaudiokonferenzen verwenden  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Besprechungsvideo anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Video mit mehreren Teilnehmern anzeigen (Katalogansicht)  <br/> |&#x2714;||||
|Warten in Besprechungslobby  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Steuerelemente für Referenten in Besprechungen verwenden  <br/> |&#x2714;||||
|Auf detaillierte Besprechungsliste für Audiokonferenzen zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Auf detaillierte Besprechungsliste für Chatnachrichtenkonferenzen zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Desktop oder Programm freigeben  <br/> |&#x2714;||||
|Anzeigen des freigegebenen Desktops oder Programms (schlechte VBSS oder RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Freigegebene PowerPoint-Dateien anzeigen  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|PowerPoint-Dateien hochladen und präsentieren  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Besprechungstools verwenden (Whiteboard verwenden, Umfragen durchführen, Dateien freigeben)  <br/> |&#x2714;||||
|In Besprechungsliste navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Teilnehmen an einer Besprechung, auch wenn Sie nicht über ein Skype for Business-Konto verfügen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen weiterer Informationen zu Besprechungsteilnehmern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Starten einer ungeplanten Gruppenunterhaltung mit mehreren Teilnehmern direkt vom Client oder Gerät   <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776;  Für Office 365-Benutzer erfordert dieses Feature Enterprise-VoIP, das Teil der E5-Lizenz ist.
  
 &#x2777;  Standardmäßig ist eine WLAN-Verbindung erforderlich.
 
 &#x2778;  Das Anzeigen von eingebettetem Video in PowerPoint-Präsentationen wird nicht unterstützt.
  
## <a name="telephony-support"></a>Telefonieunterstützung


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Tippen Sie in Skype for Business auf das Anrufsymbol, um einen Kontakt anzurufen.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufdurchstellung  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Durchstellen mit Ankündigung  <br/> |&#x2714; &#x2778; ||||
|Anrufweiterleitung verwalten  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Einstellungen für Teamanrufe verwalten  <br/> |&#x2714; &#x2776; ||||
|Stellvertretungen verwalten  <br/> |&#x2714; &#x2776; ||||
|Anruf an eine Reaktionsgruppe initiieren  <br/> |&#x2714; &#x2776; ||||
|Unterstützung von Notrufdiensten  <br/> |&#x2714; &#x2777; ||||
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertretung-Szenario)  <br/> |&#x2714; &#x2776; ||||
|Behandeln der Anrufe eines anderen Kontakts, wenn er als Stellvertretung konfiguriert ist  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|„Geschäftlich anrufen“ verwenden   <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Auf Voicemail zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Verwenden der Tastatur in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Verfügbar für Skype for Business Online-und/oder Office 365 E5-Benutzer sowie für Benutzer, die in Skype for Business Server oder lync Server 2013 mit Enterprise-VoIP aktiviert sind.
  
 &#x2777;  Für Skype for Business Online-und/oder Office 365-Benutzer wird dieses Feature von Microsoft-Partnern unterstützt.
  
 &#x2778;  Nur Windows-Desktop Client.
  
## <a name="external-user-support"></a>Unterstützung externer Benutzer


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Chatnachricht mit öffentlichem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Chat mit Partnerkontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufe mit zwei Teilnehmern mit externen Benutzern durchführen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufe mit mehreren Teilnehmern mit externen Benutzern durchführen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Verwenden Sie Anruf über Arbeit, um einen Föderations Kontakt auf seinem Mobiltelefon zu erreichen, indem Sie die veröffentlichte Arbeitsnummer & # x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Standardmäßig werden Verbundbenutzern die Datenschutz Beziehung externe Kontakte zugewiesen. Damit Sie einen Partnerkontakt auf seinem Mobiltelefon erreichen können, indem Sie die veröffentlichte geschäftliche Telefonnummer anrufen, muss der Partnerkontakt Ihnen manuell die private Beziehung „Kollegen“ zuweisen.
  
## <a name="address-book-integration"></a>Adressbuchintegration


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Kontakte aus dem Adressbuch des Geräts anrufen  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Tätigen von Skype for Business-Anrufen an Kontakte direkt aus dem Adressbuch des Geräts  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Archivierungs- und Konformitätsunterstützung


 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clientseitige Archivierung bereitstellen  <br/> |&#x2714;||||
|Clientseitige Aufzeichnung bereitstellen  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Nicht verfügbar für Skype for Business Online-und/oder Office 365-Benutzer.
  
## <a name="modern-authentication"></a>Moderne Authentifizierung

Diese Tabelle enthält Funktionen, die Unterstützung für moderne Authentifizierung erfordern.
  
Die moderne Authentifizierung erfordert auch eine Topologie, die in Skype for Business-Topologien beschrieben ist, die [mit moderner Authentifizierung unterstützt werden](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Feature/Funktion  | Skype for Business-Desktop Client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Moderne Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung  <br/> |& # x2714; (nur Domänen verbundenes Gerät)  <br/> ||&#x2714;|&#x2714;|
|Verwaltung mobiler Anwendungen (über InTune)  <br/> |||&#x2714;|&#x2714;|
   


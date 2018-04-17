---
title: Mobile client feature comparison for Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Summary: Review the feature support for the mobile client while planning for Skype for Business Server 2015.'
ms.openlocfilehash: 4287c5baf0642fab9d55d291470b2352f3da5932
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Mobile client feature comparison for Skype for Business
 
**Summary:** Review the feature support for the mobile client while planning for Skype for Business Server 2015.
  
This article compares the features and capabilities among Skype for Business mobile clients and the Skype for Business desktop client in the following categories:
  
- Anmeldung, Pushbenachrichtigungen und allgemeine Funktionen
    
- Erweiterte Anwesenheit
    
- Kontakte und Kontaktgruppen
    
- Chat
    
- Skype for Business to Skype for Business audio and video
    
- Konferenzen
    
- Telefonie
    
- Externe Benutzer
    
- Archivierung und Kompatibilität
    
-  Moderne Authentifizierung
    
The following tables list the features that are available to Skype for Business users in an on-premises deployment of Skype for Business Server 2015. The same features are also available to Skype for Business Online and Microsoft Office 365 users, unless otherwise indicated in the table footnotes.
  
> [!NOTE]
> For online help and resources for end users, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> To compare the features available in other Skype for Business clients, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 
  
## <a name="sign-in-push-notifications-and-general-features"></a>Anmeldung, Pushbenachrichtigungen und allgemeine Funktionen

 
 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business session remains signed in  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Unterstützung von Pushbenachrichtigungen  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|Kontoinformationen für mehrere Benutzer können auf demselben Gerät zwischengespeichert werden  <br/> |&#x2714;||||
|Sprachausgabe/Voiceover  <br/> |&#x2714;|&#x2714; &#x2777;           English only  <br/> |&#x2714;|&#x2714;|
|Verwenden einer externen Tastatur zugunsten der Barrierefreiheit  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Unterstützung für das Programm zur Verbesserung der Benutzerfreundlichkeit von Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  On Windows Phone, Skype for Business signs out automatically after a period of inactivity, as follows:
  
- If the user has enabled push notifications, Skype for Business signs out after 10 days of inactivity.
    
- If the user has not enabled push notifications, Skype for Business signs out as soon as the user leaves the app.
    
On iOS devices, Skype for Business signs out automatically after the mobile client has not contacted the server for 10 days due to loss of network connectivity or other issues.
  
 &#x2777;  In app only.
  
 &#x2778;  Notifications are available when the app is running in the background.
  
## <a name="enhanced-presence-support"></a>Unterstützung von erweiterten Anwesenheitsinformationen


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Status veröffentlichen und anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Statushinweise und Abwesenheitsnotizen anzeigen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Benutzerdefinierten Standort hinzufügen  <br/> |&#x2714;||||
|Benutzerdefinierte Notiz hinzufügen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Status basierend auf Kalenderinformationen (frei/gebucht) veröffentlichen   <br/> |&#x2714; &#x2776; ||||
|Anwesenheitsstatus manuell festlegen (z. B. gebucht, nicht stören usw.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business mobile clients do not update a user's presence based on the user's free/busy calendar information. If a mobile client user is also signed in to the Skype for Business desktop client, the desktop client updates the user's presence based on the user's free/busy calendar information. If the user is signed in to a mobile client only, the user's presence does not update based on free/busy calendar information.
  
## <a name="contacts-and-contact-groups-support"></a>Unterstützung von Kontakten und Kontaktgruppen


 | Feature/Funktion  | Skype for Business Lync 2013 desktop client  | Windows Phone  | iOS  | Android |
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
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="instant-messaging-support"></a>Unterstützung von Chatfunktionen


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
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
   
 &#x2776;  This device vibrates every time an IM is received even if the current message in the IM conversation is displayed
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business to Skype for Business audio and video


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-to-Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Für Video auf einem mobilen Gerät ist eine standardmäßige WLAN-Verbindung erforderlich.  
  
## <a name="conferencing-support"></a>Konferenzunterstützung


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
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
|View shared desktop or program (VbSS or RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Freigegebene PowerPoint-Dateien anzeigen  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|PowerPoint-Dateien hochladen und präsentieren  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Besprechungstools verwenden (Whiteboard verwenden, Umfragen durchführen, Dateien freigeben)  <br/> |&#x2714;||||
|In Besprechungsliste navigieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Join a meeting even if you don't have a Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anzeigen weiterer Informationen zu Besprechungsteilnehmern  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Starten einer ungeplanten Gruppenunterhaltung mit mehreren Teilnehmern direkt vom Client oder Gerät   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  For Office 365 users, this feature requires Enterprise Voice, which is part of the E5 license.
  
 &#x2777;  Requires a WiFi connection by default.
  
## <a name="telephony-support"></a>Telefonieunterstützung


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business, tap the call icon to call a contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufdurchstellung  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Durchstellen mit Ankündigung  <br/> |&#x2714; &#x2778; ||||
|Anrufweiterleitung verwalten  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Einstellungen für Teamanrufe verwalten  <br/> |&#x2714; &#x2776; ||||
|Stellvertretungen verwalten  <br/> |&#x2714; &#x2776; ||||
|Anruf an eine Reaktionsgruppe initiieren  <br/> |&#x2714; &#x2776; ||||
|Unterstützung von Notrufdiensten  <br/> |&#x2714; &#x2777; ||||
|Anrufe im Namen eines anderen Kontakts tätigen (Vorgesetzter/Stellvertretung-Szenario)  <br/> |&#x2714; &#x2776; ||||
|Handle another contact's calls, if configured as a delegate  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|„Geschäftlich anrufen“ verwenden   <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Auf Voicemail zugreifen  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use the keypad in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Available to Skype for Business Online and/or Office 365 E5 users, and users homed on Skype for Business Server 2015 or Lync 2013 with Enterprise Voice enabled.
  
 &#x2777;  For Skype for Business Online and/or Office 365 users, this feature is supported by Microsoft partners.
  
 &#x2778;  Windows Desktop client only.
  
## <a name="external-user-support"></a>Unterstützung externer Benutzer


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Chatnachricht mit öffentlichem Kontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Chat mit Partnerkontakt initiieren  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufe mit zwei Teilnehmern mit externen Benutzern durchführen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Anrufe mit mehreren Teilnehmern mit externen Benutzern durchführen  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number  &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  By default, federated users are assigned the External Contacts privacy relationship. Damit Sie einen Partnerkontakt auf seinem Mobiltelefon erreichen können, indem Sie die veröffentlichte geschäftliche Telefonnummer anrufen, muss der Partnerkontakt Ihnen manuell die private Beziehung „Kollegen“ zuweisen.
  
## <a name="address-book-integration"></a>Adressbuchintegration


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Kontakte aus dem Adressbuch des Geräts anrufen  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Make Skype for Business calls to contacts directly from device address book  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Archivierungs- und Konformitätsunterstützung


 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clientseitige Archivierung bereitstellen  <br/> |&#x2714;||||
|Clientseitige Aufzeichnung bereitstellen  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="modern-authentication"></a>Moderne Authentifizierung

Diese Tabelle enthält Funktionen, die Unterstützung für moderne Authentifizierung erfordern.
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Feature/Funktion  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Moderne Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mehrstufige Authentifizierung  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Zertifikatbasierte Authentifizierung  <br/> |&#x2714;(Domain-joined device only)  <br/> ||&#x2714;|&#x2714;|
|Mobile Application Management (via Intune)  <br/> |||&#x2714;|&#x2714;|
   


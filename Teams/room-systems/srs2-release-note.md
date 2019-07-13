---
title: Anmerkungen zu dieser Version
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: In diesem Artikel werden die kumulativen Verbesserungen in Microsoft Teams-Räumen erläutert.
ms.openlocfilehash: f6fc9bb36a4b34d9e900666bf14df0c4d0893c46
ms.sourcegitcommit: baa425d7a07429e6fe84b4f27c76243cf755c1a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643131"
---
# <a name="release-notes"></a>Anmerkungen zu dieser Version 

In diesem Artikel werden die kumulativen Verbesserungen in Microsoft Teams-Räumen erläutert.


##  <a name="version-history"></a>Versionsverlauf

| Release | Veröffentlicht in <br>Microsoft Store | 
| ---     | ---  |
| 4.0.105.0 | 07/10/2019   |
| 4.0.85.0 | 04/08/2019   |
| 4.0.78.0 | 03/14/2019   |
| 4.0.76.0 | 03/04/2019   |
| 4.0.64.0 | 12/14/2018   |
| 4.0.51.0 | 11/17/2018   | 
| 4.0.31.0 | 10/16/2018   | 
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  08/27/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  06/18/2018    |
| 3.1.113.0|  06/13/2018    |   
| 3.1.112.0|  06/05/2018    |   
| 3.1.104.0|  04/16/2018    |            
| 3.1.100.0|  03/16/2018    |            
| 3.1.99.0 | 3/14/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  11/27/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 11/16/2017 | 
| 3.0.6.0 | 11/16/2017 | 
| 2.0.2.0  | 03/15/2017 | 
| RTM (1.0.8) | 12/7/2016  | 

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Einführung in Microsoft Teams Rooms und Problembehebung
### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

In diesem Update eingeführt:
- Skype Room System Store-App-Branding für "Microsoft Teams Room"
- Microsoft Teams Room Console-Benutzeroberflächen Ausrichtung an Microsoft Teams
- Design Update, um nur das benutzerdefinierte Hintergrundbild vor dem Raum anzuzeigen, während eine neutrale Konsolen Hintergrundfarbe festgestellt wird, um sicherzustellen, dass die Konsolen-UI-Steuerelemente Farbkontrast-Barrierefreiheitsanforderungen
- Universelle Leiste für in-Besprechung-Anrufsteuerungen für Teams-Anrufe/Besprechungen, um konsistente Erfahrungen mit Microsoft Teams PC/Web/Mobile-Clients zu gewährleisten<sup>1</sup>
- Bewertung der Anrufqualität nach Teams-anrufen/Besprechungen<sup>1</sup>
- Empfangen/Rendern von Microsoft Whitebord in Microsoft Teams Room Front of room Display, wenn Sie von PC/Web/Mobile Teams Client<sup>1</sup><sup>2</sup> freigegeben  
- Unterstützung für ein Upgrade auf Windows 10, Version 1809, wurde aufgrund von Kompatibilitätsproblemen mit dem Microsoft Teams Room-Client entfernt. Windows 10-Version 19H1-Unterstützung wird in zukünftigen Versionen hinzugefügt

<sup>1</sup> Microsoft Teams Service-Rollout mit Teams klingelt. Dieses Feature steht möglicherweise früher oder später als 4.0.105.0-Client Update zur Verfügung.

<sup>2</sup> erfordert IT-Administratoren, Microsoft Whiteboard Web einzuschalten. Darüber hinaus müssen Sie, wenn Sie die Bildschirmanzeige "Touch Front" haben, mehrere Touchscreens mithilfe von Windows-Einstellungen mit dem Geräteadministrator-Anmeldenamen kalibrieren, um die Verwendung von Microsoft Whiteboard für collboration von der Raum Anzeige nach der Freigabe in die Teams-Besprechung zu starten.

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

In diesem Update eingeführt:

- Behebt ein Problem mit der Funktion "Feedback senden" 
- Optimierungen in Vorbereitung auf das bevorstehende MTR-Geräte Upgrade auf Windows 10, Version 1809

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

In diesem Update eingeführt:

- Beheben Sie den Fehler "beim Start der APP hängen", der sich auf Geräte auf Legacy-RS2-Builds von Windows 10 auswirkt.  


### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

In diesem Update eingeführt:

- DTMF-Tastatur für Microsoft Teams-P2P-Besprechungen und PSTN-Anrufe. Damit Microsoft Teams Ihr Standard Anruf Client ist, müssen Administratoren IsTeamsDefaultClient auf "true" festlegen.
- Anheften des eingehenden Videos eines Remote Teilnehmers an den Vollbildmodus vor der Raum Anzeige Verwenden des Befehls "anheften" in der Teilnehmerliste auf der Konsole
- Verbesserungen bei Benachrichtigungen über Lobbys mit Hinzufügen der Benachrichtigung über den Chatroom
- Vorderseite der Raum Anzeige entfernt das Umwandlungs Symbol, wenn Bluetooth-Beacon auf dem Raumsystem Gerät nicht aktiviert ist
- Beheben von Problemen mit der Lautstärkeregelung in Teams-Besprechungen


### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

In diesem Update eingeführt:

- Anzeigen von Inhalten auf beiden Front of room (für)-Displays auf Dual-Screen-Room-Systemen
- Verbesserungen bei der Benutzeroberfläche für Themen und vor dem Zimmer
- TLS 1,2-clientseitige Unterstützung. Für Kunden, die Ziel Kommunikation fördern über TLS 1,2 für Microsoft Teams rooms aktivieren, ist Skype for Business Server 2015 kummulative Update 9 (CU9) oder Skype for Business Server 2019 kummulative Update 1 (CU1) erforderlich.

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

In diesem Update eingeführt:

- Dual-Display (Front of room)-Unterstützung für Teams-Besprechungen 

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

In diesem Update eingeführt:

- Fehlerbehebungen für Qualität und Zuverlässigkeit

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

In diesem Update eingeführt:
 
- Code Änderungen, die erforderlich sind, um die Microsoft Teams rooms-App für spätere Updates für Windows 10 Version 1803 vorzubereiten
- Beheben von Formatierungsproblemen mit lokalisierten Endbenutzer-Lizenzbedingungen – speziell Norwegisch – verhindert das Vordringen über das OOBE-Setup Fenster von EULA hinaus
- Code Änderungen, die erforderlich sind, damit Microsoft Teams rooms-Anwendungen auf Legacy-lync-Raumsystemen ausgeführt werden. Weitere Informationen finden Sie [hier](https://aka.ms/lrsupgrade).
 
### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)
In diesem Update eingeführt:

- Hotfix für Crestron-Anwendung wird nicht gestartet, auf den normalerweise durch Drücken der APP-Schaltfläche auf Crestron SR-Geräten zugegriffen werden kann. Microsoft Teams rooms-Neustart der APP nach der Installation von 4.0.19.0 erforderlich. 

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)
In diesem Update eingeführt:

- Verbesserungen des Features "Problem melden" im Modus "Teams" (entspricht "Feedback senden" im Skype for Business-Modus)
- Aktivieren der Möglichkeit zum Fallback von Teams auf den Skype for Business-Modus für SIP-Anrufe
- Verbesserungen bei der Barrierefreiheit (Sprachausgabe, Bildschirmlupe)
- Automatisches erneutes Starten der APP nach Bedarf, nachdem XML-Bereitstellungsänderungen angewendet wurden
- Verschiedene Fehlerbehebungen

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

In diesem Update eingeführt:
- Dieses Update ermöglicht die Unterstützung von Skype for Business *-und* Microsoft Teams-Besprechungen auf Raumsystem Geräten.  Teams ist standardmäßig deaktiviert, sobald das Update angewendet wurde.  Administratoren können Teams lokal in Geräteeinstellungen oder über einen Remote-XML-Push aktivieren.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

In diesem Update eingeführt:

- Fix to Address-Fehler, der auf einigen Systemen während des App-Starts beobachtet wurde.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)
In diesem Update eingeführt:

- Änderungen, die es Microsoft ermöglichen, Windows-Updates flexibler zu verwalten.
- Keine Änderung an der Benutzeroberfläche.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

In diesem Update eingeführt:

- Beheben von Problemen mit der Konsolen Reaktion auf Surface pro 2017-basierten Geräten, die mit zwei Front-Room-Displays und Videoaufnahme verbunden sind
- Automatische Überprüfung, um sicherzustellen, dass das aktuelle Bereitstellungsskript für das System ausgeführt wird.

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

In diesem Update eingeführt:

- Korrektur zum Verbessern des Verhaltens von OSK (Bildschirmtastatur) in Windows 10-basierten Systemen auf der Version 1709
- Verbesserungen bei der Vorbereitung auf zukünftige Betriebssystemupdates

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

In diesem Update eingeführt: 

- Anwendung aktualisiert, um die Telemetrie zu verbessern.

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

In diesem Update eingeführt:

- Behebt ein Problem, bei dem sporadische Probleme mit der Besprechung auftreten können.
- Behebt ein Problem, das bekanntermaßen zu einem Gerät "hängen" führt.

### <a name="31980--382018"></a>3.1.98.0 (3/8/2018)

In diesem Update eingeführt:

- Fehler/Absturz Korrekturen zur Verbesserung der Stabilität
- Unterstützung für Console mit variabler Größe
- Auslagerungsfunktion für periphere Audioverarbeitung (zusätzliche Medien Whitelist)
- Optimierungen, mit denen IT-Experten selbst eigene Bilder mit Windows 10, Version 1709, Januar-Update und höher erstellen können.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

In diesem Update eingeführt:
 
- Behebt ein Problem mit der Funktion "Feedback senden".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

In diesem Update eingeführt:

- Unterstützung für die Dock-Hardware der [Polycom MSR-Serie](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Unterstützung für die [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Behebt ein Problem, bei dem Anzeige (Konsole und Front-of-room) nicht in den Ruhemodus wechselt, wenn keine Aktivitäten im Chatroom vorhanden sind.


### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

In diesem Update eingeführt:

- Läuft auf einem Surface pro (2017)-Tablet  
- Unterstützt Windows 10 Enterprise Creators Update (englische Sprache, Build 1703)
- Unterstützung für [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) Dock-Hardware
- OEM-Unterstützung für Umgebungs Steuerelemente (Crestron)

Die 64-Bit-Version von Windows 10 Enterprise Anniversary Edition (englische Sprache, Version 1607) wird ab Version 3.0.12.0 (Update 3) von Microsoft Teams rooms nicht mehr unterstützt.

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

In diesem Update eingeführt:

- Behebt Probleme, die bei der Suche nach Verbundbenutzern über das Suchfeld der Teilnehmer aufgetreten sind. Zurück zu diesem Fix haben Suchergebnisse für externe Verbundbenutzer möglicherweise nicht ordnungsgemäß aufgelöst und stattdessen falsche Ergebnisse zurückgegeben.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

In diesem Update eingeführt:

- Dual-Screen-Unterstützung (für Legacy-System Parität)
- Themen (integrierte Designs und die Möglichkeit, benutzerdefiniertes Design zu definieren)
- Möglichkeit, Feedback für öffentliche Builds zu geben
- Verbesserte Telemetrie um die Zuverlässigkeit der Besprechungsteilnahme
- Zusätzliche OMS-Berichterstellung
- Möglichkeit für IT-Administratoren, Geräte remote zu konfigurieren  <!--  - Front-of-Room UX shows room details pre-meeting U2  -->


### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

In diesem Update eingeführt:

- In-App-Benutzerauswahl der Audio-und Video-USB-Geräte des Besprechungsraums
- Integrierte Raum Konsolenstatus Berichte für Kunden, die Microsoft Operations Management Suite verwenden, jetzt Azure Monitor  

### <a name="release-to-market--1272016"></a>Veröffentlichung in den Markt (12/7/2016)

**Feature (s):**

 **Für Skype for Business konzipiert**
  
- One-Touch-Teilnahme an Skype-Besprechungen
- Optimierte Skype-Besprechungsumgebung für Räume mit bildschirmfüllendem HD-Video und HD-Breitbandaudio
- Alle Teilnehmer können über ihr bevorzugtes Gerät eine Verbindung mit der Skype-Besprechung herstellen – ganz gleich, wo sie sich gerade aufhalten.
- Sie können Personen aus Ihrem Verzeichnis, wo Sie ihre Verfügbarkeit sofort sehen können, oder telefonisch einladen.
- Unterstützt Skype for Business-PSTN-Konferenzen und -PSTN-Anrufe als Ersatz für das eigenständige Konferenztelefon in Ihrem Raum.

  **Neue Möglichkeiten für Besprechungsräume**
  
- Eigene Skype-Besprechungs-App mit Optimierung für einen Touchcontroller in der Tischmitte und einen großen Bildschirm vorn im Raum
- Nutzung vorhandener Investitionen in Bildschirme oder Projektoren
- Für alle Arten von Besprechungsräumen geeignet – von kleinen Besprechungsräumen bis hin zu großen Konferenzräumen
- Für Skype for Business zertifizierte Audio- und Videogeräte für verschiedene Raumgrößen
- Integrierte verkabelte Erfassung zum Projizieren der Desktopfreigabe in den Raum und die Skype-Besprechung

  **Leicht bereitzustellen, einfach zu verwalten**
  
- Immer aktive Appliance, die die Bildschirme automatisch reaktiviert, sobald Personen im Raum erkannt werden
- Einfache Bereitstellung und Aktualisierung der UWP-App (Universal Windows Platform) für Skype-Besprechungen
- Feste Bindung des Geräts an die Skype-Besprechungs-App durch Windows AppLocker
- Überwachung und Verwaltung als Windows 10 Enterprise-Gerät über Intune und SCCM (MDM)
- Zuverlässigkeit der Unternehmensklasse
- Geringer Aufwand für Endbenutzerschulungen dank der vertrauten Skype-Benutzeroberfläche
- Läuft auf Surface pro 4-Tablet

<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Microsoft Teams Rooms-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Vorbereiten der Umgebung](srs-v2-prep.md)

[Unterstützung für Microsoft Teams rooms aktuelle Branch-Versionen](srs2-lifecycle-support.md)

[Bekannte Probleme für Microsoft Teams-Chatrooms](known-issues.md)

[Planen von Microsoft Teams-Räumen](skype-room-systems-v2-0.md)

[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)

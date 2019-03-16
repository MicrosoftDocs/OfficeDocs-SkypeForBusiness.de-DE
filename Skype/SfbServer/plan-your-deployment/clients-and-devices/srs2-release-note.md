---
title: Anmerkungen zu dieser Version
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Artikel werden die kumulative Verbesserungen in Skype Raum Systemen v2.
ms.openlocfilehash: fefad8a37d53760a81b2ea78e73bbd75069c848f
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645356"
---
# <a name="release-notes"></a>Anmerkungen zu dieser Version 

In diesem Artikel werden die kumulative Verbesserungen in Skype Raum Systemen v2.


##  <a name="version-history"></a>Versionsverlauf

| Version | Veröffentlicht <br>Microsoft Store | 
| ---     | ---  |
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
| RTM-VERSION (1.0.8) | 7/12/2016  | 


## <a name="skype-room-systems-v2-feature-introduction-and-issue-resolution"></a>Skype-Chatroom-Systemen v2 Feature Einführung und Behebung

### <a name="40780-03142018"></a>4.0.78.0 (14/03/2018)
In diesem Update eingeführt:
- Update für "hängt beim Start app" Fehler, die Geräte an, für die Vorversion Windows 10 RS2 Build betroffen.  

### <a name="40760-03042019"></a>4.0.76.0 (04/03/2019)
In diesem Update eingeführt:
- DTMF-Tastatur für Microsoft-Teams, Besprechungen. Damit Microsoft-Teams, der Standardclient für aufrufen können, müssen Administratoren IsTeamsDefaultClient auf True festgelegt.
- Anheften eines remote Teilnehmers eingehendes Video Vollbildmodus auf Raum Anzeige am Anfang. Verwenden Sie Befehl "Anheften" aus der Teilnehmerliste der Teilnehmer in der Konsole
- Verbesserungen an Wartebereich Benachrichtigungen durch Hinzufügen von Front-Chatroom-Benachrichtigung
- Am Anfang Raum Anzeige entfernt Casting-Symbol, wenn Bluetooth-Signal auf Raum Systemgerät nicht aktiviert ist
- Update für Volume Steuerelement Problem in Teams Besprechungen


### <a name="40640-12142018"></a>4.0.64.0 (14/12/2018)
In diesem Update eingeführt:
- Anzeigen von Inhalten auf beide Front-der Raum (zeigt auf zwei Bildschirm Raum Systemen für)
- Designs und Front-Raum Verbesserungen der Benutzeroberfläche
- Client-seitigen TLS 1.2 unterstützt. Für erfordert auf Kunden vor Ort, aktivieren Threats-Kommunikation über TLS 1.2 für Skype Raum System V2 Skype für Business Server 2015 Cummulative Update 9 (CU9) oder Skype für Unternehmenseinheiten Server 2019 Cummulative Update 1 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)
In diesem Update eingeführt:
- Unterstützung für Teams Besprechungen Duale Anzeige (Vorderseite der Raum) 

### <a name="40310-10162018"></a>4.0.31.0 (16/10/2018)
In diesem Update eingeführt:
- Updates für die Qualität und Zuverlässigkeit 

### <a name="40270-1012018"></a>4.0.27.0 (1/10/2018)
In diesem Update eingeführt: 
- Ändern von Code erforderlich sind, um die app SRSv2 höher Windows 10 Version 1803-Upgrade vorbereiten
- Beheben von Formatierung Problem mit lokalisierten EULAs - speziell Norwegisch - die verhindert, dass der Inhalt hinter EULA OOBE-Setup-Fenster
- Ändern von Code erforderlich, damit Skype Raum Systemen v2 Anwendung auf Systeme der Vorversion Lync Raum ausgeführt. Weitere Informationen finden Sie [hier](https://aka.ms/lrsupgrade).
 

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)
In diesem Update eingeführt: 
- Hotfix für Crestron-Anwendung nicht starten, die normalerweise möglich wäre durch Drücken der Taste app auf Crestron SR-Geräte. SRSv2 app neu starten nach der Installation von 4.0.19.0 erforderlich 

### <a name="40180-08272018"></a>4.0.18.0 (27/08/2018)
In diesem Update eingeführt: 
- "Problemberichte" funktionsverbesserungen im Teams Modus (entspricht der "Feedback geben" in Skype für Business-Modus)
- Bei aktivierter Möglichkeit Fallback von Teams Skype für Business-Modus für SIP-Anrufe
- Verbesserte Eingabehilfen (die Sprachausgabe, Bildschirmlupe)
- Automatisch neu gestartet app bei Bedarf nach der Bereitstellung Änderungen XML angewendet wurden
- Sonstige fixes

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)
In diesem Update eingeführt: 
- Dieses Update ermöglicht sowohl Skype *und* Teams Besprechungen Unterstützung auf Geräten Raum Systeme.  Teams ist standardmäßig deaktiviert, nachdem das Update angewendet wird.  Administratoren können Teams lokal in den geräteeinstellungen oder über eine remote-Xml-Push aktivieren.

### <a name="311150-06182018"></a>3.1.115.0 (18/06/2018)
In diesem Update eingeführt: 
- Auf einige Systeme während der app-Start beobachteten Adresse Fehler beheben.

### <a name="311130-06132018"></a>3.1.113.0 (13/06/2018)
In diesem Update eingeführt: 
- Aktivieren von Microsoft flexibel auf mehrere Änderungen Verwalten von Windows-Updates.
- Keine Änderung an den Endbenutzer.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)
In diesem Update eingeführt: 
- Zu Adresse Konsole Reaktionsfähigkeit, die Aufnahme auf 2017 Surface Pro-basierten Geräten verbunden mit zwei Vorderseite der Raum zeigt und Videofunktionen beobachteten Probleme beheben
- Automatisierte stellen Sie sicher, dass das System die neuesten provisioning Skript ausgeführt wird.

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)
In diesem Update eingeführt: 
- Update zur Verbesserung der Bildschirmtastatur (Bildschirmtastatur) Verhalten im Fenster 10 Version 1709-basierte Systeme
- Verbesserungen für zukünftige Betriebssystemupdates vorbereiten

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)
In diesem Update eingeführt:  
- Anwendung zum Verbessern der Telemetrie aktualisiert.

### <a name="31990-03142018"></a>3.1.99.0 (14/03/2018)
In diesem Update eingeführt: 
- Updates ein Problem zeitweilige Besprechung beitreten, in dem Probleme auftreten.
- Behebt ein Problem bekannt, dass ein Gerät "hängen" Erlebnis führen.

### <a name="31980--382018"></a>3.1.98.0 (8/3/2018)
In diesem Update eingeführt: 
- Fehler/Absturz Updates zur Verbesserung der Stabilität
- Unterstützung für die Konsole variabler Größe
- Peripherer Verarbeitung von Audiosignalen Verschiebung (Weitere Medien mithilfe)
- Optimierungen für die IT-Spezialisten das Erstellen von Yourself Bilder mit Windows 10 Version 1709 Januar Update und höher aktiviert wird.  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)
In diesem Update eingeführt:  
- Behebt ein Problem mit dem Feature "Feedback geben".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)
In diesem Update eingeführt: 
- Unterstützung für [Polycom MSR Datenreihe](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) Andocken hardware
- Unterstützung für die [Logitech Brio](https://www.logitech.com/en-us/product/brio)
- Wird ein Fehler behoben, auf denen Energiesparmodus eingeben, wenn keine Aktivität stattgefunden, im Raum hat zeigt (Konsole und Vorderseite der Raum) fehlschlägt.


### <a name="30120-912017"></a>3.0.12.0 (1/9/2017)
In diesem Update eingeführt:   
- Führt auf einem Surface Pro Tablet (2017)  
- Unterstützt Windows 10 Enterprise Creator Update (englische, Build 1703)    
- Unterstützung für [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) Andocken hardware    
- OEM-Unterstützung für Umgebung-Steuerelemente (Crestron)
    
Die 64-Bit-Version von Windows 10 Enterprise Jahrestag Edition (englische, Version 1607) wird nicht mehr Skype Raum Systemen v2 Version 3.0.12.0 (Update 3) unterstützt. 

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017) 
In diesem Update eingeführt: 
- Behebt Probleme beobachtet, wenn Benutzer über das Suchfeld Teilnehmer federated gesucht. Vor diesem Update können nicht die Suchergebnisse für externe Verbundbenutzer ordnungsgemäß aufgelöst und stattdessen falsche Ergebnisse zurückgegeben. 

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017) 
In diesem Update eingeführt: 
- Dual-Bildschirm Unterstützung (älterer Systeme Parität)   
- Themability (integrierten Designs und die Möglichkeit, benutzerdefinierte Designs festgelegt) 
- Die Möglichkeit, Feedback geben für Öffentliche builds     
- Verbesserte Telemetrie an Besprechung teilnehmen Zuverlässigkeit     
- Zusätzliche OMS reporting     
- Möglichkeit für IT-Administrator können Sie Geräte Remote konfigurieren  <!--  - Front-of-Room UX shows room details pre-meeting U2  --> 


### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)
In diesem Update eingeführt: 
- Auswahl des meeting Room Audio- und USB-Geräte in app-Benutzers
- Integrierte Raum Konsole Statusberichte für Kunden mit Microsoft Operations Management Suite (finden Sie unter [Planen von Skype Raum v2 systemverwaltung mit OMS](oms-management.md)) 

### <a name="release-to-market--1272016"></a>Version (7/12/2016) auf den Markt
**Features:** 

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
- Führt auf Surface Pro 4-tablet
 

<a name="See"> </a>  
## <a name="see-also"></a>Siehe auch

[Skype Raum Systeme Version 2-Hilfe](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Vorbereiten Sie Ihrer Skype Geschäftsumgebung](srs-v2-prep.md)

[Unterstützung für Skype Raum Systemen v2 aktuellen Branch Versionen](srs2-lifecycle-support.md)

[Bekannte Probleme bei Skype Raum Systemen v2](../../manage/skype-room-systems-v2/known-issues.md)

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)

[Verwalten von Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

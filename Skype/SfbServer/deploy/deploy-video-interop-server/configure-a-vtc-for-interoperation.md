---
title: Konfigurieren einer VTC für die Interoperation mit Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Zusammenfassung: Konfigurieren der Geräte VTC Skype für Business Server entwickelt.'
ms.openlocfilehash: 1a8422ddfa33652fa13d5aeb42b86a72b809126b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219674"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Konfigurieren einer VTC für die Interoperation mit Skype für Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Geräte VTC Skype für Business Server entwickelt.
  
Sie müssen die folgenden Konfiguration Anpassung Verfahren für jede VTC ausführen, die die Skype für gegenüber Business Server über einen SIP-Trunk und Cisco Unified Communications-Manager (CallManager oder CUCM) eine Verbindung herstellt video Gateway.
  
Die hier beschriebenen Einstellungen Präsentationsstil nur als Beispiele wie CUCM konfiguriert werden kann einen VIS. entwickelt Andere Einstellungen und/oder Verwendungsmöglichkeiten von alternativen CUCM-Funktionen können auch zum Erzielen des gleichen Ergebnisses herangezogen werden. Es wird keine Empfehlung für die optimale Konfiguration eines bestimmten Szenarios impliziert.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Konfigurieren einer beim CUCM registrierten Videotelekonferenz

1. Melden Sie sich an dem Gerät Cisco VTC und navigieren Sie zur Konfiguration -\>System Konfiguration -\>Provisioning.
    
2. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Bereitstellungsmodus  <br/> | CUCM <br/> |
   |ExternalManager-Adresse  <br/> | Vollqualifizierter Domänenname des CUCM <br/> |
   | ExternalManager Domäne <br/> |Domäne des CUCM  <br/> |
   
3. Navigieren Sie zur Konfiguration -\>System Konfiguration -\>Netzwerk.
    
4. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |DNS-Domänenname  <br/> | CUCM-Domänenname <br/> |
   |DNS-Serveradresse 1  <br/> | Die Adresse Ihres gewünschten DNS-Servers <br/> |
   
5. Navigieren Sie zur Konfiguration -\>System Konfiguration -\>Netzwerkdienste. Stellen Sie sicher, dass der H.323-Modus deaktiviert und der SIP-Modus aktiviert ist. 
    
6. Diese Optionen werden automatisch eingestellt, wenn der Endpunkt beim CUCM registriert wird. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |H.323-Modus  <br/> | Aus <br/> |
   |HTTP-Modus  <br/> | Ein <br/> |
   | SIP-Modus <br/> | Ein <br/> |
   |Telnet-Modus  <br/> | Ein <br/> |
   |Begrüßungstext  <br/> | Ein <br/> |
   |XMLAPI-Modus  <br/> | Ein <br/> |
   
7. Navigieren Sie zur Konfiguration -\>System Konfiguration -\>SIP.
    
8. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Profil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profil 1 - Ausgehend  <br/> | Aus <br/> |
   |Profil 1 - TlsVerify  <br/> | Ein <br/> |
   |Profil 1 - Typ  <br/> | Cisco <br/> |
   |Profil 1 - URI  <br/> | Bei CUCM-Registrierung automatisch zugewiesen <br/> |
   |Proxy 1 - Adresse  <br/> |Der Hostname des CUCM  <br/> |
   
Die Videotelekonferenz ist jetzt für Interoperabilität konfiguriert. Bevor der Dienst gestartet werden kann, müssen CUCM-seitig abschließende Schritte durchgeführt werden.
### <a name="configure-vtc-devices-on-cucm"></a>Konfigurieren Sie Videotelekonferenzgeräte im CUCM

1. Melden Sie sich bei CUCM und navigieren Sie zu Cisco Unified CM Administration -\>Gerät -\>Phone -\>suchen. 
    
2. Wählen Sie das Videotelekonferenzgerät, das konfiguriert werden soll. Überprüfen Sie die folgenden Einstellungen im Bildschirm „Telefonkonfiguration“ und führen Sie ggf. Korrekturen durch. Klicken Sie auf **Save** (Speichern), nachdem diese Einstellungen geändert oder überprüft wurden.
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Geräteinformation - Telefontastenvorlage  <br/> | Standard Cisco Telearbeiter Codec C40 <br/> |
   |Geräteinformation - Allgemeines Telefonprofil  <br/> | Standardmäßiges allgemeines Telefonprofil <br/> |
   |Geräteinformation - Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformation - AAR-Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformation - Medienressourcen-Gruppenliste  <br/> | MRGL_SfBVideoInterop <br/> |
   |Protokollspezifische Information - Gerätesicherheitsprofil  <br/> | Cisco Telearbeiter Codec C40 <br/> |
   |Protokollspezifische Information - Umleitungs-Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Spezifische Informationen Protokoll – abonnieren Suchbereich aufrufen  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Information - SIP-Profil  <br/> | Standardmäßiges SIP-Profil für Telepräsenzendpunkt <br/> |
   
3. Wenn die VTC-Konfiguration gespeichert ist, navigieren Sie erneut zum Bildschirm „Telefonkonfiguration“ für das Gerät. Klicken Sie oben im Bildschirm in der Gruppe „Zuordnung“ auf die Zuordnung für die Videointeroperabilität. Damit öffnen Sie den Bildschirm „Verzeichnisnummernkonfiguration“. 
    
4. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
    Nehmen Sie die entsprechenden Änderungen vor wie in der Verzeichnisnummerninformation und den Verzeichnisnummerneinstellungen dargestellt.
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   | Verzeichnisnummerninformation - Routenpartition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Verzeichnisnummerneinstellungen - Leerzeichen für Anrufsuche  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP-Einstellungen für neuen Gesprächspartner und vertrauliche Zugriffsebene - MLPP-Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Zeile 1 auf Gerät - Anzeige (Anrufer-ID)  <br/> | Nach Bedarf <br/> |
   |Zeile 1 auf Gerät - ASCII-Anzeige (Anrufer-ID)  <br/> | Nach Bedarf <br/> |
   
5. Scrollen Sie nach Beendigung im Bildschirm nach oben und drücken Sie **Speichern**. 
    
Die Konfiguration für dieses Videotelekonferenzgerät ist damit beendet. Sie müssen diesen Vorgang ggf. für andere Videotelekonferenzgeräte in Ihrem Unternehmen wiederholen.


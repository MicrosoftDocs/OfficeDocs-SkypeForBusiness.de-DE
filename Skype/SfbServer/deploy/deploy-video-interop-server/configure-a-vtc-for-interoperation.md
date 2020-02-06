---
title: Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Zusammenfassung: Konfigurieren Sie die VTC-Geräte so, dass Sie mit Skype for Business Server funktionieren.'
ms.openlocfilehash: b266c8cc97898fe192ec023183a565b921d86949
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798082"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die VTC-Geräte für die Zusammenarbeit mit Skype for Business Server.
  
Sie müssen die folgenden Konfigurations Anpassungsverfahren für jede VTC durchführen, die mit dem Skype for Business-VIS-Server über einen SIP-Trunk und einen Cisco Unified Communications Manager (CallManager oder CUCM)-Video Gateway verbunden werden.
  
Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Arbeit mit einem VIS konfiguriert werden kann. Andere Einstellungen und/oder Verwendungsmöglichkeiten von alternativen CUCM-Funktionen können auch zum Erzielen des gleichen Ergebnisses herangezogen werden. Es wird keine Empfehlung für die optimale Konfiguration eines bestimmten Szenarios impliziert.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Konfigurieren einer beim CUCM registrierten Videotelekonferenz

1. Melden Sie sich beim Cisco VTC-Gerät an, und navigieren\>Sie zu Konfiguration\>– System Konfiguration – Bereitstellung.
    
2. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Bereitstellungsmodus  <br/> | CUCM <br/> |
   |ExternalManager-Adresse  <br/> | Vollqualifizierter Domänenname des CUCM <br/> |
   | Externalmanager-Domäne <br/> |CUCM-Domäne  <br/> |
   
3. Navigieren Sie zu Konfiguration\>– System Konfiguration\>– Netzwerk.
    
4. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |DNS-Domänenname  <br/> | CUCM-Domänenname <br/> |
   |DNS-Serveradresse 1  <br/> | Die Adresse Ihres gewünschten DNS-Servers <br/> |
   
5. Navigieren Sie zu Konfiguration\>– System Konfiguration\>– Netzwerkdienste. Stellen Sie sicher, dass der H.323-Modus deaktiviert und der SIP-Modus aktiviert ist. 
    
6. Diese Optionen werden automatisch eingestellt, wenn der Endpunkt beim CUCM registriert wird. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |H.323-Modus  <br/> | Aus <br/> |
   |HTTP-Modus  <br/> | Ein <br/> |
   | SIP-Modus <br/> | Ein <br/> |
   |Telnet-Modus  <br/> | Ein <br/> |
   |Begrüßungstext  <br/> | Ein <br/> |
   |XMLAPI-Modus  <br/> | Ein <br/> |
   
7. Navigieren Sie zu Konfiguration\>– System Konfiguration\>– SIP.
    
8. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Profil 1 - DefaultTransport  <br/> | TCP <br/> |
   |Profil 1 - Ausgehend  <br/> | Aus <br/> |
   |Profil 1 – TlsVerify  <br/> | Ein <br/> |
   |Profil 1 - Typ  <br/> | Cisco <br/> |
   |Profil 1 - URI  <br/> | Bei CUCM-Registrierung automatisch zugewiesen <br/> |
   |Proxy 1 - Adresse  <br/> |Der Hostname des CUCM  <br/> |
   
Die Videotelekonferenz ist jetzt für Interoperabilität konfiguriert. Bevor der Dienst gestartet werden kann, müssen CUCM-seitig abschließende Schritte durchgeführt werden.
### <a name="configure-vtc-devices-on-cucm"></a>Konfigurieren Sie Videotelekonferenzgeräte im CUCM

1. Melden Sie sich bei CUCM an, und navigieren Sie zu Cisco\>Unified cm\>Administration-\>Device-Phone-Find. 
    
2. Wählen Sie das Videotelekonferenzgerät, das konfiguriert werden soll. Überprüfen Sie die folgenden Einstellungen im Bildschirm „Telefonkonfiguration“ und führen Sie ggf. Korrekturen durch. Klicken Sie auf **Save** (Speichern), nachdem diese Einstellungen geändert oder überprüft wurden.
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Geräteinformation - Telefontastenvorlage  <br/> | Standard-Cisco TelePresence-Codec C40 <br/> |
   |Geräteinformation - Allgemeines Telefonprofil  <br/> | Standardmäßiges allgemeines Telefonprofil <br/> |
   |Geräteinformation - Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformation - AAR-Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformation - Medienressourcen-Gruppenliste  <br/> | MRGL_SfBVideoInterop <br/> |
   |Protokollspezifische Information - Gerätesicherheitsprofil  <br/> | Cisco TelePresence-Codec C40 <br/> |
   |Protokollspezifische Information - Umleitungs-Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen-abonnieren des Suchbereichs für Anrufe  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Information - SIP-Profil  <br/> | Standardmäßiges SIP-Profil für Telepräsenzendpunkt <br/> |
   
3. Wenn die VTC-Konfiguration gespeichert ist, navigieren Sie erneut zum Bildschirm „Telefonkonfiguration“ für das Gerät. Klicken Sie oben im Bildschirm in der Gruppe „Zuordnung“ auf die Zuordnung für die Videointeroperabilität. Damit öffnen Sie den Bildschirm „Verzeichnisnummernkonfiguration“. 
    
4. Überprüfen und korrigieren Sie ggf. die folgenden Einstellungen: 
    
    Nehmen Sie die entsprechenden Änderungen vor wie in der Verzeichnisnummerninformation und den Verzeichnisnummerneinstellungen dargestellt.
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   | Verzeichnisnummerninformation - Routenpartition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Verzeichnisnummerneinstellungen - Leerzeichen für Anrufsuche  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP-Einstellungen für neuen Gesprächspartner und vertrauliche Zugriffsebene - MLPP-Wahlberechtigungsmodul  <br/> | CSS_SfBVideoInterop <br/> |
   |Zeile 1 auf Device-Display (Rufnummernanzeige)  <br/> | Nach Bedarf <br/> |
   |Zeile 1 auf Device-ASCII-Display (Rufnummernanzeige)  <br/> | Nach Bedarf <br/> |
   
5. Scrollen Sie nach Beendigung im Bildschirm nach oben und drücken Sie **Speichern**. 
    
Die Konfiguration für dieses Videotelekonferenzgerät ist damit beendet. Sie müssen diesen Vorgang ggf. für andere Videotelekonferenzgeräte in Ihrem Unternehmen wiederholen.


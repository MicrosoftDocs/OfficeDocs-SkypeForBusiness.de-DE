---
title: Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Zusammenfassung: Konfigurieren Sie die VTC-Geräte für die Verwendung mit Skype for Business Server.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802075"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die VTC-Geräte für die Zusammenarbeit mit Skype for Business Server.
  
Sie müssen die folgenden Konfigurationsanpassungsverfahren für jedes VTC ausführen, das über einen SIP-Trunk und ein Cisco Unified Communications Manager (CallManager oder CUCM)-Videogateway eine Verbindung mit dem Skype for Business -VIS-Server herstellen wird.
  
Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Verwendung mit einem VIS konfiguriert werden kann. Andere Einstellungen und/oder Verwendungen alternativer CUCM-Funktionen können auch verwendet werden, um dasselbe Ergebnis zu erzielen. Es wird keine Empfehlung zur optimalen Konfiguration für ein bestimmtes Szenario impliziert.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Konfigurieren eines mit CUCM registrierten VTC

1. Melden Sie sich beim Cisco -VTC-Gerät an, und navigieren Sie zu "Configuration- \> System Configuration- \> Provisioning".
    
2. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Bereitstellungsmodus  <br/> | CUCM <br/> |
   |ExternalManager Address  <br/> | FQDN des CUCM <br/> |
   | ExternalManager Domain <br/> |Domäne des CUCM  <br/> |
   
3. Navigieren Sie zu "Konfiguration – \> Systemkonfiguration- \> Netzwerk".
    
4. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |DNS Domain Name  <br/> | CUCM-Domänenname <br/> |
   |DNS Server 1-Adresse  <br/> | Die gewünschte DNS-Serveradresse <br/> |
   
5. Navigieren Sie zu "Konfiguration - \> Systemkonfiguration- \> Netzwerkdienste". Stellen Sie sicher, dass der H.323-Modus deaktiviert und der MODUS "SIP" aktiviert ist. 
    
6. Diese Optionen werden automatisch festgelegt, wenn der Endpunkt beim CUCM registriert wird. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |H.323-Modus  <br/> | Off <br/> |
   |HTTP-Modus  <br/> | Ein <br/> |
   | SIP-Modus <br/> | Ein <br/> |
   |Telnetmodus  <br/> | Ein <br/> |
   |WelcomeText  <br/> | Ein <br/> |
   |XMLAPI-Modus  <br/> | Ein <br/> |
   
7. Navigieren Sie zu "Configuration- \> System Configuration- \> SIP".
    
8. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Profil 1 – DefaultTransport  <br/> | TCP <br/> |
   |Profil 1 – Ausgehend  <br/> | Off <br/> |
   |Profil 1 – TlsVerify  <br/> | Ein <br/> |
   |Profil 1 – Typ  <br/> | Cisco <br/> |
   |Profil 1 – URI  <br/> | Automatisch zugewiesen bei der CUCM-Registrierung <br/> |
   |Proxy 1 – Adresse  <br/> |Der Hostname des CUCM  <br/> |
   
Das VTC ist jetzt für die Interoperabilität konfiguriert. Bevor der Dienst beginnen kann, müssen auf der CuCM-Seite abschließende Schritte unternommen werden.
### <a name="configure-vtc-devices-on-cucm"></a>Konfigurieren von VTC-Geräten auf CUCM

1. Melden Sie sich beim CUCM an, und navigieren Sie zu Cisco Unified CM Administration - \> Gerät - \> Telefon \> suchen. 
    
2. Wählen Sie das zu konfigurierende VTC-Gerät aus. Überprüfen Sie die folgenden Einstellungen auf dem Bildschirm "Telefonkonfiguration", und korrigieren Sie sie bei Bedarf. Nachdem diese Einstellungen geändert oder überprüft wurden, klicken Sie auf **"Speichern".**
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Geräteinformationen – Vorlage für Telefonschaltfläche  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |Geräteinformationen – Allgemeines Telefonprofil  <br/> | Standard Common Phone Profile <br/> |
   |Geräteinformationen – Anrufsuchbereich  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformationen – AAR Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformationen – Liste der Medienressourcengruppen  <br/> | MRGL_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen – Gerätesicherheitsprofil  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Protokollspezifische Informationen – erneutes Umleitung des Suchbereichs für Anrufe  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen – SUBSCRIBE Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen –SIP-Profil  <br/> | Standard-SIP-Profil für Telepräsenzendpunkt <br/> |
   
3. Nachdem die Konfiguration von VTC gespeichert wurde, navigieren Sie erneut zum Bildschirm "Telefonkonfiguration" für das Gerät. Klicken Sie oben auf dem Bildschirm in der Gruppe "Zuordnung" auf die Zuordnung für die Videointeop. Dadurch wird der Bildschirm "Konfiguration der Verzeichnisnummer" angezeigt. 
    
4. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
    Nehmen Sie die entsprechenden Änderungen wie in den Verzeichnisnummerinformationen und den Verzeichnisnummereinstellungen dargestellt vor.
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   | Verzeichnisnummerinformationen – Routenpartition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Verzeichnisnummereinstellungen – Suchbereich für Anrufe  <br/> | CSS_SfBVideoInterop <br/> |
   |Einstellungen für alternative Und vertrauliche Zugriffsebenen von MLPP – Suchbereich für ANRUFE von MLPP  <br/> | CSS_SfBVideoInterop <br/> |
   |Zeile 1 auf Gerät - Anzeige (Anrufer-ID)  <br/> | Nach Bedarf <br/> |
   |Zeile 1 auf dem Gerät - ASCII-Anzeige (Anrufer-ID)  <br/> | Nach Bedarf <br/> |
   
5. Wenn Sie fertig sind, scrollen Sie zum oberen Rand des Bildschirms, und drücken Sie **"Speichern".** 
    
Die Konfiguration für dieses VTC-Gerät ist nun abgeschlossen. Sie müssen diesen Vorgang für andere VTC-Geräte in Ihrem Unternehmen wiederholen.


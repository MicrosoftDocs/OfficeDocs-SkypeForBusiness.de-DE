---
title: Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Zusammenfassung: Konfigurieren sie die VTC-Geräte für die Verwendung mit Skype for Business Server.'
ms.openlocfilehash: 8044e2038ebb8e9c1b68b5b91473e9e57dd1fb7a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389657"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>Konfigurieren eines VTC für die Interoperabilität mit Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die VTC-Geräte für die Verwendung mit Skype for Business Server.
  
Sie müssen die folgenden Konfigurationsanpassungsverfahren für jeden VTC ausführen, der über einen SIP-Trunk und ein Videogateway von Cisco Unified Communications Manager (CallManager oder CUCM) eine Verbindung mit dem Skype for Business VIS-Server herstellt.
  
Die hier beschriebenen Einstellungen sind nur als Beispiele dafür gedacht, wie CUCM für die Verwendung mit einem VIS konfiguriert werden kann. Andere Einstellungen und/oder Verwendungen alternativer CUCM-Funktionen können ebenfalls verwendet werden, um dasselbe Ergebnis zu erzielen. Es wird keine Empfehlung hinsichtlich der optimalen Konfiguration für ein bestimmtes Szenario impliziert.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>Konfigurieren eines bei CUCM registrierten VTC

1. Melden Sie sich beim Cisco VTC-Gerät an, und navigieren Sie zu Configuration-System\> Configuration-Provisioning\>.
    
2. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Bereitstellungsmodus  <br/> | CUCM <br/> |
   |ExternalManager-Adresse  <br/> | CUCM-FQDN <br/> |
   | ExternalManager-Domäne <br/> |CUCM-Domäne  <br/> |
   
3. Navigieren Sie zu Configuration-System\> Configuration-Network\>.
    
4. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |DNS-Domänenname  <br/> | CUCM-Domänenname <br/> |
   |DNS Server 1-Adresse  <br/> | Ihre gewünschte DNS-Serveradresse <br/> |
   
5. Navigieren Sie zu Configuration-System\> Configuration-Network\> Services. Stellen Sie sicher, dass der H.323-Modus deaktiviert und der SIP-Modus aktiviert ist. 
    
6. Diese Optionen werden automatisch festgelegt, wenn der Endpunkt bei CUCM registriert wird. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |H.323-Modus  <br/> | Off <br/> |
   |HTTP-Modus  <br/> | Ein <br/> |
   | SIP-Modus <br/> | Ein <br/> |
   |Telnet-Modus  <br/> | Ein <br/> |
   |WelcomeText  <br/> | Ein <br/> |
   |XMLAPI-Modus  <br/> | Ein <br/> |
   
7. Navigieren Sie zu Configuration-System\> Configuration-SIP\>.
    
8. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Profil 1 – DefaultTransport  <br/> | TCP <br/> |
   |Profil 1 – Ausgehend  <br/> | Off <br/> |
   |Profil 1 – TlsVerify  <br/> | Ein <br/> |
   |Profil 1 – Typ  <br/> | Cisco <br/> |
   |Profil 1 – URI  <br/> | Bei CUCM-Registrierung automatisch zugewiesen <br/> |
   |Proxy 1 – Adresse  <br/> |Der Hostname des CUCM  <br/> |
   
Der VTC ist jetzt für die Interoperabilität konfiguriert. Bevor der Dienst beginnen kann, müssen auf cucm-Seite abschließende Schritte ausgeführt werden.
### <a name="configure-vtc-devices-on-cucm"></a>Konfigurieren von VTC-Geräten auf CUCM

1. Melden Sie sich bei CUCM an, und navigieren Sie zu Cisco Unified CM Administration-Device-Telefon-Find\>\>\>. 
    
2. Wählen Sie das zu konfigurierende VTC-Gerät aus. Überprüfen Sie die folgenden Einstellungen auf dem Telefon Konfigurationsbildschirm, und korrigieren Sie sie nach Bedarf. Nachdem diese Einstellungen geändert oder überprüft wurden, klicken Sie auf **"Speichern**".
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   |Geräteinformationen – Telefon-Schaltflächenvorlage  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |Geräteinformationen – allgemeines Telefon profil  <br/> | Standard Common Telefon Profile <br/> |
   |Geräteinformationen – Aufrufen des Suchbereichs  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformationen – AAR-Anrufsuchbereich  <br/> | CSS_SfBVideoInterop <br/> |
   |Geräteinformationen – Medienressourcengruppenliste  <br/> | MRGL_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen – Gerätesicherheitsprofil  <br/> | Cisco Telepresence Codec C40 <br/> |
   |Protokollspezifische Informationen – Umgeleitet des Anrufsuchbereichs  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen – Abonnieren des Suchbereichs für Anrufe  <br/> | CSS_SfBVideoInterop <br/> |
   |Protokollspezifische Informationen – SIP-Profil  <br/> | Standard-SIP-Profil für Telepresence-Endpunkt <br/> |
   
3. Navigieren Sie nach dem Speichern der VTC-Konfiguration erneut zum Telefon Konfigurationsbildschirm für das Gerät. Klicken Sie oben auf dem Bildschirm in der Zuordnungsgruppe auf die Zuordnung für die Video-Interoperabilität. Dadurch wird der Bildschirm "Verzeichnisnummernkonfiguration" angezeigt. 
    
4. Überprüfen Sie die folgenden Einstellungen, und korrigieren Sie sie nach Bedarf: 
    
    Nehmen Sie die entsprechenden Änderungen an den Verzeichnisnummerninformationen und der Verzeichnisnummer Einstellungen vor.
    
   |**Parameter**|**Empfohlene Einstellung**|
   |:-----|:-----|
   | Verzeichnisnummerninformationen – Routenpartition <br/> | SfBVideoInterop_RoutePartition <br/> |
   |Verzeichnisnummer Einstellungen – Anrufsuchbereich  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP Alternate Party and Confidential Access Level Einstellungen – MLPP Calling Search Space  <br/> | CSS_SfBVideoInterop <br/> |
   |Zeile 1 auf dem Gerät – Anzeige (Anrufer-ID)  <br/> | Nach Bedarf <br/> |
   |Zeile 1 auf dem Gerät – ASCII-Anzeige (Anrufer-ID)  <br/> | Nach Bedarf <br/> |
   
5. Scrollen Sie nach Abschluss des Vorgangs zum oberen Rand des Bildschirms, und drücken **Sie "Speichern"**. 
    
Die Konfiguration für dieses VTC-Gerät ist nun abgeschlossen. Sie müssen diesen Vorgang für andere VTC-Geräte in Ihrem Unternehmen wiederholen.


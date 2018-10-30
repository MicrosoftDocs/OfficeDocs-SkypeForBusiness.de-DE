---
title: Sicherheit der mobilen App von Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Hier erfahren Sie, mobile app-Sicherheit für Ihre Benutzer eingerichtet. '
ms.openlocfilehash: 03b6575826defd5bd4c8c7739a1975edaabe0752
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838495"
---
# <a name="skype-for-business-mobile-app-security"></a>Sicherheit der mobilen App von Skype for Business

## <a name="skype-for-business-client-security"></a>Skype for Business Client-Sicherheitstabelle

Dieser Artikel beinhaltet Informationen zur Datenverschlüsselung für mobile Skype for Business-Apps.
  
|||||
|:-----|:-----|:-----|:-----|
||**Benutzername/Kennwort** <br/> |**App-Daten (Unterhaltungen,<br/> Kontaktliste, Besprechungen)** <br/> |**Diagnoseprotokolle** <br/> |
|**Android** <br/> |Wir speichern Anmeldeinformationen in Android Accounts. Zudem verschlüsseln wir Anmeldeinformationen, bevor wir sie unter „Konten" speichern. Wir verwenden den Verschlüsselungsalgorithmus „ **AES/CBC/PKCS5Padding** ".<br/> |Wir speichern eine verschlüsselte SQL-Datenbank unter Verwendung einer Bibliothek namens [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Wir verwenden deren Standardalgorithmus von 256-Bit AES im CBC-Modus. Die verbleibenden Daten werden immer in der Datenbankdatei verschlüsselt und nur für die Übertragung innerhalb des flüchtigen Speichers und der Anrufliste der App entschlüsselt. Wir entschlüsseln ebenfalls Voicemail-Dateien unter Einsatz derselben Methode wie die Verschlüsselung von Benutzernamen und Kennwörtern (diese werden nicht in der Datenbank gespeichert). Voicemails werden vorübergehend auf der Festplatte zwecks Wiedergabe entschlüsselt.<br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
|**iOS** <br/> |Der Benutzername bzw. das Kennwort werden in der Schlüsselkette NICHT verschlüsselt. Die Schlüsselkette selbst wird jedoch verschlüsselt.  <br/> |Wir verwenden bereits das [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)-Datenschutzkennzeichen für alle Dateien im App-Speicher. Das heißt, dass alle Dateien im App-Speicher verschlüsselt sind, bis ein Benutzer das Gerät zum ersten Mal nach dem Neustart des Geräts entschlüsselt.<br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
|**Windows Phone** <br/> |Windows Phone verwendet die DPAPI (Data Protection API) in Windows zum Sichern von Kennwörtern. Ich glaube, dass AES das verwendete Verschlüsselungsschema ist. Windows bietet keine Option zum Konfigurieren der Schlüsselgröße (oder des Schemas). Die Einstellungen werden also von DPAPI vorgegeben. Ich verwende das Geräte-TPM, um die für den Benutzer und das Gerät spezifischen Schlüssel zu sichern. Beachten Sie, dass DPAPI-Schlüssel nicht App-spezifisch sind.  <br/> |WP-App-Daten werden wie die Anmeldeinformationen mit [DPAPI](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx) geschützt. Je nach gewünschter Detailebene werden einige der Indexinformationen für die App-Daten durch die AES-Verschlüsselung (nicht-DPAPI) geschützt, um die Verwendung zusätzlicher Anhänge zu vermeiden. Dadurch ist eine Suche ohne Entschlüsselung möglich und der Schlüssel wird im Gegenzug durch DPAPI geschützt. Gecachte Daten können von jedem Prozess über dasselbe Telefon gelesen werden (vorausgesetzt, der Datenordner wird erreicht). Windows-Verschlüsselung schützt nicht vor Sandbox-Angriffen, nur vor externen Zugriffsversuchen.<br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
   
**Hinweis:** Finden Sie in [dieser Dokumentation der öffentlichen](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) für Gerät Pin Erzwingung auf alle oben genannten mobilen Plattformen verfügbar
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
 
---
title: Sicherheit der mobilen App von Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Hier erfahren Sie, wie Sie die Sicherheit mobiler Apps für Ihre Benutzer einrichten. '
ms.openlocfilehash: 1adfc8e44880b89ab9f4b24be532ae4a327744cf69d0ef63ecea3f65ae684fc8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295112"
---
# <a name="skype-for-business-mobile-app-security"></a>Sicherheit der mobilen App von Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Skype for Business Client-Sicherheitstabelle

Dieser Artikel beinhaltet Informationen zur Datenverschlüsselung für mobile Skype for Business-Apps.
  
|||||
|:-----|:-----|:-----|:-----|
||**Benutzername/Kennwort** <br/> |**App-Daten (Unterhaltungen, <br/> Kontaktliste, Besprechungen)** <br/> |**Diagnoseprotokolle** <br/> |
|**Android** <br/> |Wir speichern Anmeldeinformationen in Android Accounts. Zudem verschlüsseln wir Anmeldeinformationen, bevor wir sie unter „Konten" speichern. Wir verwenden den Verschlüsselungsalgorithmus „ **AES/CBC/PKCS5Padding** ".<br/> |Wir speichern eine verschlüsselte SQL-Datenbank unter Verwendung einer Bibliothek namens [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Wir verwenden deren Standardalgorithmus von 256-Bit AES im CBC-Modus. Die verbleibenden Daten werden immer in der Datenbankdatei verschlüsselt und nur für die Übertragung innerhalb des flüchtigen Speichers und der Anrufliste der App entschlüsselt. Wir entschlüsseln ebenfalls Voicemail-Dateien unter Einsatz derselben Methode wie die Verschlüsselung von Benutzernamen und Kennwörtern (diese werden nicht in der Datenbank gespeichert). Voicemails werden vorübergehend auf der Festplatte zwecks Wiedergabe entschlüsselt.<br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
|**iOS** <br/> |Der Benutzername bzw. das Kennwort werden in der Schlüsselkette NICHT verschlüsselt. Die Schlüsselkette selbst wird jedoch verschlüsselt.  <br/> |Wir verwenden bereits das [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)-Datenschutzkennzeichen für alle Dateien im App-Speicher. Das heißt, dass alle Dateien im App-Speicher verschlüsselt sind, bis ein Benutzer das Gerät zum ersten Mal nach dem Neustart des Geräts entschlüsselt.<br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
|**Windows Phone** <br/> |Windows Phone verwendet die DPAPI (Data Protection API) in Windows zum Sichern von Kennwörtern. Ich glaube, dass AES das verwendete Verschlüsselungsschema ist. Windows bietet keine Option zum Konfigurieren der Schlüsselgröße (oder des Schemas). Die Einstellungen werden also von DPAPI vorgegeben. Ich verwende das Geräte-TPM, um die für den Benutzer und das Gerät spezifischen Schlüssel zu sichern. Beachten Sie, dass DPAPI-Schlüssel nicht App-spezifisch sind.  <br/> |WP-App-Daten werden wie die Anmeldeinformationen mit [DPAPI](/previous-versions/windows/apps/hh487164(v=vs.105)) geschützt. Je nach gewünschter Detailebene werden einige der Indexinformationen für die App-Daten durch die AES-Verschlüsselung (nicht-DPAPI) geschützt, um die Verwendung zusätzlicher Anhänge zu vermeiden. Dadurch ist eine Suche ohne Entschlüsselung möglich und der Schlüssel wird im Gegenzug durch DPAPI geschützt. Gecachte Daten können von jedem Prozess über dasselbe Telefon gelesen werden (vorausgesetzt, der Datenordner wird erreicht). Windows-Verschlüsselung schützt nicht vor Sandbox-Angriffen, nur vor externen Zugriffsversuchen.<br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
   
**Hinweis:** Informationen zur [Erzwingung von Geräte-PIN](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) finden Sie in dieser öffentlichen Dokumentation zu den oben genannten mobilen Plattformen.
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  

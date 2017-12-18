---
title: "Skype für Business mobile-app-Sicherheit"
ms.author: kenwith
author: kenwith
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: concetpual
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
description: ""
---

# Skype für Business mobile-app-Sicherheit

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
## Skype for Business Client-Sicherheitstabelle

Dieser Artikel beinhaltet Informationen zur Datenverschlüsselung für mobile Skype for Business-Apps.
  
|||||
|:-----|:-----|:-----|:-----|
||**Benutzername/Kennwort** <br/> |**App-Daten (Unterhaltungen, Kontaktliste, Besprechungen)** <br/> |**Diagnoseprotokolle** <br/> |
|**Android** <br/> |Wir speichern Anmeldeinformationen in Android Accounts. Zudem verschlüsseln wir Anmeldeinformationen, bevor wir sie unter „Konten" speichern. Wir verwenden den Verschlüsselungsalgorithmus „ **AES/CBC/PKCS5Padding** ". <br/> |Wir speichern eine verschlüsselte SQL-Datenbank unter Verwendung einer Bibliothek namens [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Wir verwenden deren Standardalgorithmus von 256-Bit AES im CBC-Modus. Die verbleibenden Daten werden immer in der Datenbankdatei verschlüsselt und nur für die Übertragung innerhalb des flüchtigen Speichers und der Anrufliste der App entschlüsselt. Wir entschlüsseln ebenfalls Voicemail-Dateien unter Einsatz derselben Methode wie die Verschlüsselung von Benutzernamen und Kennwörtern (diese werden nicht in der Datenbank gespeichert). Voicemails werden vorübergehend auf der Festplatte zwecks Wiedergabe entschlüsselt.  <br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
|**iOS** <br/> |Der Benutzername bzw. das Kennwort werden in der Schlüsselkette NICHT verschlüsselt. Die Schlüsselkette selbst wird jedoch verschlüsselt.  <br/> |Wir verwenden bereits das [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)-Datenschutzkennzeichen für alle Dateien im App-Speicher. Das heißt, dass alle Dateien im App-Speicher verschlüsselt sind, bis ein Benutzer das Gerät zum ersten Mal nach dem Neustart des Geräts entschlüsselt.  <br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
|**Windows Phone** <br/> |Windows Phone verwendet die DPAPI (Data Protection API) in Windows zum Sichern von Kennwörtern. Ich glaube, dass AES das verwendete Verschlüsselungsschema ist. Windows bietet keine Option zum Konfigurieren der Schlüsselgröße (oder des Schemas). Die Einstellungen werden also von DPAPI vorgegeben. Ich verwende das Geräte-TPM, um die für den Benutzer und das Gerät spezifischen Schlüssel zu sichern. Beachten Sie, dass DPAPI-Schlüssel nicht App-spezifisch sind.  <br/> |WP-App-Daten werden wie die Anmeldeinformationen mit [DPAPI](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx) geschützt. Je nach gewünschter Detailebene werden einige der Indexinformationen für die App-Daten durch die AES-Verschlüsselung (nicht-DPAPI) geschützt, um die Verwendung zusätzlicher Anhänge zu vermeiden. Dadurch ist eine Suche ohne Entschlüsselung möglich und der Schlüssel wird im Gegenzug durch DPAPI geschützt. Gecachte Daten können von jedem Prozess über dasselbe Telefon gelesen werden (vorausgesetzt, der Datenordner wird erreicht). Windows-Verschlüsselung schützt nicht vor Sandbox-Angriffen, nur vor externen Zugriffsversuchen. <br/> |Diese Informationen sind nicht verschlüsselt.  <br/> |
   
Hinweis: Informationen zur Erzwingung der auf allen oben genannten Mobilgeräteplattformen finden Sie in [dieser öffentlichen Dokumentation](https://docs.microsoft.com/de-de/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  


---
title: Unterstützte Richtlinien für bedingten Zugriff und Intune Gerätekompatibilität für Microsoft Teams-Räume
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über unterstützte und empfohlene Richtlinien für bedingten Zugriff und Intune Gerätecompliance für Microsoft Teams-Räume.
ms.openlocfilehash: befe8faae5db204f5e15e307cadcc24f6867a487
ms.sourcegitcommit: 5fe5516f6118ce3fa0449ab194a6fe87bf48c664
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2022
ms.locfileid: "64732293"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Unterstützte Richtlinien für bedingten Zugriff und Intune Gerätekompatibilität für Microsoft Teams-Räume

Dieser Artikel enthält unterstützte Richtlinien für bedingten Zugriff und Intune Gerätekompatibilität für Microsoft Teams-Räume. Bewährte Methoden und Beispielrichtlinien finden Sie unter ["Bedingter Zugriff" und Intune bewährten Methoden für Microsoft Teams-Räume](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Teams-Räume müssen bereits auf den Geräten bereitgestellt werden, den Sie Richtlinien für bedingten Zugriff zuweisen möchten. Wenn Sie Teams-Räume noch nicht bereitgestellt haben, finden Sie weitere Informationen unter ["Erstellen von Ressourcenkonten für Räume und freigegebene Teams-Geräte](with-office-365.md)" und ["Bereitstellen von Microsoft Teams-Räume unter Android](../devices/collab-bar-deploy.md)".

## <a name="supported-conditional-access-policies"></a>Unterstützte Richtlinien für bedingten Zugriff  

Die folgende Liste enthält die unterstützten Richtlinien für bedingten Zugriff für Teams-Räume unter Windows und unter Android. Die unterstützten Android-Richtlinien gelten für alle Android-Geräte in gemeinsam genutzten Räumen, einschließlich Telefonen und Panels für gemeinsame Bereiche.

| Zuweisung | Windows | Android |
|------------|---------|---------|
| Benutzer- oder Workloadidentitäten |Unterstützt | Unterstützt |
|Cloud-Apps oder -Aktionen | Unterstützt <br><br> Teams-Räume müssen auf die folgenden drei Cloud-Apps zugreifen, wenn sie sich im modus "Teams" befinden: Office 365 Exchange Online, Office 365 SharePoint Online und Microsoft Teams | Unterstützt <br><br> Teams-Räume müssen auf die folgenden drei Cloud-Apps zugreifen, wenn sie sich im modus "Teams" befinden: Office 365 Exchange Online, Office 365 SharePoint Online und Microsoft Teams |
|**Bedingungen**| --- | --- |
| Benutzerrisiko | Unterstützt | Unterstützt |
| Anmelderisiko | Unterstützt | Unterstützt |
| Geräteplattformen | Unterstützt | Unterstützt |
| Standorte | Unterstützt | Unterstützt |
|Client-Apps |Nicht unterstützt| Nicht unterstützt |
|Filtern nach Geräten | Unterstützt | Unterstützt |
|**Gewähren**| --- | --- |
| Zugriff blockieren | Unterstützt | Unterstützt |
| Zugriff gewähren | Unterstützt | Unterstützt | 
| Mehrstufige Authentifizierung erforderlich | Nicht unterstützt | Nicht unterstützt |
| Festlegen, dass das Gerät als konform gekennzeichnet wird | Unterstützt | Unterstützt |
|Hybrid-Azure AD verbundenes Gerät erforderlich | Nicht unterstützt | Nicht unterstützt |
|Genehmigte Client-App anfordern | Nicht unterstützt | Nicht unterstützt |
| App-Schutzrichtlinie anfordern | Nicht unterstützt |Nicht unterstützt |
| Kennwortänderung erforderlich | Nicht unterstützt | Nicht unterstützt |

> [!NOTE]
> Skype for Business Online wird eingestellt und nicht unterstützt. Skype for Business Online-Cloud-App wird für Gerätecompliance-basierte Richtlinien für bedingten Zugriff nicht unterstützt.

> [!NOTE]
> Microsoft Teams-Räume auf Windows müssen die folgenden Anforderungen erfüllen, um Die Gerätekompatibilitätsgenehmigungssteuerelemente zu unterstützen:
>
> - Microsoft Teams-Räume Anwendung 4.8.19.0 oder höher
> - Windows 10 Version 20H2 und höher (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Unterstützte Gerätekompatibilitätsrichtlinien 

Microsoft Teams-Räume auf Windows und Teams-Räume unter Android unterstützen unterschiedliche Gerätekompatibilitätsrichtlinien.

#### <a name="teams-rooms-on-windows"></a>[Teams-Räume auf Windows](#tab/mtr-w)

Im Folgenden finden Sie eine Tabelle der Gerätekompatibilitätseinstellungen und Empfehlungen für deren Verwendung mit Teams-Räume.  

|Richtlinie | Verfügbarkeit | Hinweise|
|---------|-------------|-------|
| [**Geräteintegrität**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|BitLocker erforderlich| Unterstützt | Verwenden Sie diese Option nur, wenn Sie BitLocker auf Teams-Räume aktiviert haben. |
|Aktivieren des sicheren Starts auf dem Gerät erforderlich |Unterstützt |Der sichere Start ist eine Anforderung für Teams-Räume. |
|Codeintegrität erforderlich |Unterstützt  | Codeintegrität ist bereits eine Anforderung für Teams-Räume. |
| [**Geräteeigenschaften**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Betriebssystemversion (minimum, maximum) |Nicht unterstützt | Teams-Räume wird automatisch auf neuere Versionen von Windows aktualisiert, und das Festlegen von Werten hier kann eine erfolgreiche Anmeldung nach einem Betriebssystemupdate verhindern.|
|Betriebssystemversion für mobile Geräte (minimum, maximum) | Nicht unterstützt. | Nicht zutreffend |
| Gültige Betriebssystembuilds | Nicht unterstützt | Nicht zutreffend |
| [**Configuration Manager Compliance**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Gerätekompatibilität von Configuration Manager anfordern | Unterstützt |  Nicht zutreffend |
| [**Systemsicherheit**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Alle Kennwortrichtlinien | Nicht unterstützt | Kennwortrichtlinien können verhindern, dass sich das lokale Skype Konto automatisch anmeldet. |
| Verschlüsselung des Datenspeichers auf dem Gerät erforderlich. | Unterstützt  | Verwenden Sie dies nur, wenn Sie die Verschlüsselung des Datenspeichers auf Teams-Räume aktiviert haben. |
| Firewall | Unterstützt | Firewall ist bereits eine Anforderung für Teams-Räume |
| Trusted Platform Module (TPM) | Unterstützt | Trusted Platform Module (TPM) ist bereits eine Anforderung für Teams-Räume. |
| Antivirus | Unterstützt | Antivirus (Windows Defender) ist bereits eine Anforderung für Teams-Räume. |
| Antispyware | Unterstützt | Antispyware (Windows Defender) ist bereits eine Anforderung für Teams-Räume. |
| Microsoft Defender Antischadsoftware | Unterstützt | Microsoft Defender Antimalware ist bereits eine Anforderung für Teams-Räume. |
| Mindestversion von Microsoft Defender Antischadsoftware | Nicht unterstützt. | Teams-Räume diese Komponente automatisch aktualisiert, sodass keine Compliancerichtlinien festgelegt werden müssen.|
| Microsoft Defender Antimalware Security Intelligence
Auf dem neuesten Stand | Unterstützt | Überprüfen Sie, ob Microsoft Defender Antischadsoftware bereits eine Anforderung für Teams-Räume ist. |
| Echtzeitschutz | Unterstützt | Echtzeitschutz ist bereits eine Anforderung für Teams-Räume. |
| [**Microsoft Defender für Endpunkt**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Fordern Sie an, dass sich das Gerät auf oder unter der Risikobewertung des Computers beläuft. | Unterstützt |  Nicht zutreffend |

#### <a name="teams-rooms-on-android"></a>[Teams-Räume unter Android](#tab/mtr-a)

Im Folgenden finden Sie eine Tabelle der Gerätekompatibilitätseinstellungen und Empfehlungen für deren Verwendung mit Teams-Räume.  

| Richtlinie | Verfügbarkeit | Hinweise |
|---------|-------------|-------|
| [**Microsoft Defender für Endpunkt**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Festlegen, dass sich das Gerät auf oder unter der Risikobewertung des Computers beläuft | Nicht unterstützt |  Nicht zutreffend |
| [**Geräteintegrität**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Gerät, das mit dem Geräteadministrator verwaltet wird | Erforderlich | Teams Android-Geräteverwaltung erfordert die Aktivierung des Geräteadministrators. |
| Gerootete Geräte | Unterstützt |  Nicht zutreffend |
| Festlegen, dass sich das Gerät auf oder unter der Bedrohungsstufe des Geräts beläuft | Nicht unterstützt |  Nicht zutreffend |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services ist konfiguriert | Nicht unterstützt | Google Play ist nicht auf Teams Android-Geräten installiert. |
| Aktueller Sicherheitsanbieter | Nicht unterstützt | Google Play ist nicht auf Teams Android-Geräten installiert. |
| Bedrohungsscan für Apps | Nicht unterstützt | Google Play ist nicht auf Teams Android-Geräten installiert. |
| SafetyNet-Gerätenachweis | Nicht unterstützt | Google Play ist nicht auf Teams Android-Geräten installiert.|
| [**Geräteeigenschaften**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Betriebssystemversion (minimum, maximum) | Unterstützt |  Nicht zutreffend |
[**Systemsicherheit**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Verschlüsselung des Datenspeichers auf dem Gerät erforderlich. |Unterstützt |  Nicht zutreffend |
[**Gerätesicherheit**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Blockieren von Apps aus unbekannten Quellen | Nicht unterstützt | Nur Teams Administratoren installieren Apps oder OEM-Tools |
| Unternehmensportal App-Laufzeitintegrität | Unterstützt |  Nicht zutreffend|
| Eingeschränkte Apps | Nicht unterstützt |  Nicht zutreffend |
| Blockieren des USB-Debuggens auf dem Gerät | Unterstützt |  Nicht zutreffend|
[**Alle Android-Geräte*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Maximale Inaktivitätsminuten, bevor ein Kennwort erforderlich ist | Nicht unterstützt |  Nicht zutreffend |
| Anfordern eines Kennworts zum Entsperren mobiler Geräte | Nicht unterstützt | Nicht zutreffend |
| [**Android 10 und höher**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 und früher oder Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Erforderlicher Kennworttyp |Nicht unterstützt | Nicht zutreffend|

---

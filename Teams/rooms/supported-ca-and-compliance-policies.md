---
title: Unterstützte Richtlinien für bedingten Zugriff und Intune-Gerätekonformität für Microsoft Teams-Räume
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
description: Erfahren Sie mehr über unterstützte und empfohlene Richtlinien für bedingten Zugriff und Intune-Gerätekonformitätsrichtlinien für Microsoft Teams-Räume.
ms.openlocfilehash: ea27f71a7d4f64bc1d9e8c8a3cd3d7b2a52151f3
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504195"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Unterstützte Richtlinien für bedingten Zugriff und Intune-Gerätekonformität für Microsoft Teams-Räume

Dieser Artikel enthält unterstützte Richtlinien für bedingten Zugriff und Intune-Gerätekonformität für Microsoft Teams-Räume. Bewährte Methoden und Beispielrichtlinien finden Sie unter Bewährte Methoden [für bedingten Zugriff und Intune-Compliance für Microsoft Teams-Räume](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> Teams-Räume müssen bereits auf den Geräten bereitgestellt sein, den Sie Richtlinien für bedingten Zugriff zuweisen möchten. Wenn Sie noch keine Teams-Räume bereitgestellt haben, finden Sie weitere Informationen unter Erstellen von Ressourcenkonten für Räume und freigegebene [Teams-Geräte](with-office-365.md) und Bereitstellen Microsoft Teams-Räume [unter Android](../devices/collab-bar-deploy.md).

## <a name="supported-conditional-access-policies"></a>Unterstützte Richtlinien für bedingten Zugriff  

Die folgende Liste enthält die unterstützten Richtlinien für bedingten Zugriff für Teams-Räume auf Windows Android-Geräten. Die unterstützten Android-Richtlinien gelten für alle Android-Geräte, -Smartphones und -Panels.

| Zuweisung | Windows | Android |
|------------|---------|---------|
| Benutzer- oder Workloadidentitäten |Unterstützt | Unterstützt |
|Cloud-Apps oder -Aktionen | Unterstützt <br><br> Teams-Räume muss nur im Teams auf die folgenden drei Cloud-Apps zugreifen: Office 365 Exchange Online, Office 365 SharePoint Online und Microsoft Teams | Unterstützt <br><br> Teams-Räume muss nur im Teams auf die folgenden drei Cloud-Apps zugreifen: Office 365 Exchange Online, Office 365 SharePoint Online und Microsoft Teams |
|**Bedingungen**| --- | --- |
| Benutzerrisiko | Unterstützt | Unterstützt |
| Anmelderisiko | Unterstützt | Unterstützt |
| Geräteplattformen | Unterstützt | Unterstützt |
| Standorte | Unterstützt | Unterstützt |
|Client-Apps |Nicht unterstützt| Nicht unterstützt |
|Filtern nach Geräten | Unterstützt | Unterstützt |
|**Grant**| --- | --- |
| Zugriff blockieren | Unterstützt | Unterstützt |
| Gewähren des Zugriffs | Unterstützt | Unterstützt | 
| Mehrstufige Authentifizierung erfordern | Nicht unterstützt | Nicht unterstützt |
| Verlangen, dass das Gerät als konform gekennzeichnet wird | Unterstützt | Unterstützt |
|Hybridgerät Azure AD gerät erforderlich | Nicht unterstützt | Nicht unterstützt |
|Genehmigte Client-App erforderlich | Nicht unterstützt | Nicht unterstützt |
| App-Schutzrichtlinien erfordern | Nicht unterstützt |Nicht unterstützt |
| Kennwortänderung erforderlich | Nicht unterstützt | Nicht unterstützt |

> [!NOTE]
> Skype for Business Online ist eingestellt und wird nicht unterstützt. Skype for Business Online-Cloud-App wird für Gerätekonformitätsbasierte Richtlinien für bedingten Zugriff nicht unterstützt.

> [!NOTE]
> Microsoft Teams-Räume auf Windows müssen die folgenden Anforderungen erfüllen, um Geräte-Compliance-Grant-Steuerelemente zu unterstützen:
>
> - Microsoft Teams-Räume 4.8.19.0 oder höher
> - Windows 10 Version 20H2 und höher (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Unterstützte Richtlinien zur Gerätekonformität 

Microsoft Teams-Räume auf Windows und Teams-Räume unter Android unterstützen verschiedene Richtlinien zur Gerätekonformität.

#### <a name="teams-rooms-on-windows"></a>[Teams-Räume auf Windows](#tab/mtr-w)

Unten finden Sie eine Tabelle mit Gerätekonformitätseinstellungen und Empfehlungen für deren Verwendung mit Teams-Räume.  

|Richtlinie | Verfügbarkeit | Hinweise|
|---------|-------------|-------|
| [**Geräteinte health**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|BitLocker erfordern| Unterstützt | Verwenden Sie nur, wenn Sie BitLocker zum ersten Mal aktiviert Teams-Räume. |
|Aktivieren von Secure Boot auf dem Gerät erforderlich |Unterstützt |Secure Boot ist eine Voraussetzung für Teams-Räume. |
|Codeintegrität erfordern |Unterstützt  | Codeintegrität ist bereits eine Voraussetzung für Teams-Räume. |
| [**Geräteeigenschaften**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Betriebssystemversion (Minimum, Maximum) |Nicht unterstützt | Teams-Räume auf neuere Versionen von Windows und das Festlegen von Werten hier kann eine erfolgreiche Anmeldung nach einem Betriebssystemupdate verhindern.|
|Betriebssystemversion für mobile Geräte (Minimum, Maximum) | Nicht unterstützt. | Nicht zutreffend |
| Gültige Builds von Betriebssystemen | Nicht unterstützt | Nicht zutreffend |
| [**Configuration Manager-Compliance**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Gerätekonformität von Configuration Manager erforderlich | Unterstützt |  Nicht zutreffend |
| [**Systemsicherheit**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Alle Kennwortrichtlinien | Nicht unterstützt | Kennwortrichtlinien können verhindern, dass sich Skype Konto des lokalen Kontos automatisch anmelden. |
| Verschlüsselung der Datenspeicherung auf dem Gerät erforderlich. | Unterstützt  | Verwenden Sie nur, wenn Sie die Verschlüsselung der Datenspeicherung auf Ihrem Gerät Teams-Räume. |
| Firewall | Unterstützt | Die Firewall ist bereits eine Voraussetzung für Teams-Räume |
| Trusted Platform Module (TPM) | Unterstützt | Das vertrauenswürdige Plattformmodul (Trusted Platform Module, TPM) ist bereits eine Voraussetzung für Teams-Räume. |
| Antivirus | Unterstützt | Antivirus (Windows Defender) ist bereits eine Voraussetzung für Teams-Räume. |
| Antistatware | Unterstützt | Anti antivirusware (Windows Defender) ist bereits eine Voraussetzung für Teams-Räume. |
| Microsoft Defender Anmalware | Unterstützt | Microsoft Defender Anmalware ist bereits eine Voraussetzung für Teams-Räume. |
| Mindestversion von Microsoft Defender Anmalware | Nicht unterstützt. | Teams-Räume diese Komponente automatisch aktualisiert, sodass keine Compliancerichtlinien festgelegt werden müssen.|
| Microsoft Defender Anmalware-Sicherheitsintelligenz
Auf dem neuesten Stand | Unterstützt | Überprüfen Sie, ob Microsoft Defender Antimalware bereits eine Voraussetzung für die Verwendung Teams-Räume. |
| Echtzeitschutz | Unterstützt | Echtzeitschutz ist bereits eine Voraussetzung für Teams-Räume. |
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Das Gerät muss sich mit oder unter der Risikobewertung des Computers begnen. | Unterstützt |  Nicht zutreffend |

#### <a name="teams-rooms-on-android"></a>[Teams-Räume unter Android](#tab/mtr-a)

Unten finden Sie eine Tabelle mit Gerätekonformitätseinstellungen und Empfehlungen für deren Verwendung mit Teams-Räume.  

| Richtlinie | Verfügbarkeit | Hinweise |
|---------|-------------|-------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Das Gerät muss sich auf dem Computer oder unter der Risikobewertung des Computers besennen. | Nicht unterstützt |  Nicht zutreffend |
| [**Geräteinte health**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Mit Geräteadministrator verwaltetes Gerät | Nicht unterstützt. | Teams Android-Geräte werden mit Gerät verwaltet
Administrator. |
| Stammgeräte | Unterstützt |  Nicht zutreffend |
| Das Gerät muss sich auf der Stufe oder unter der Bedrohungsstufe des Geräts besennen. | Nicht unterstützt |  Nicht zutreffend |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services ist konfiguriert | Nicht unterstützt | Google Play ist auf Android-Geräten Teams installiert. |
| Aktuelle Sicherheitsanbieter | Nicht unterstützt | Google Play ist auf Android-Geräten Teams installiert. |
| Bedrohungsscan für Apps | Nicht unterstützt | Google Play ist auf Android-Geräten Teams installiert. |
| SafetyNet-Geräte nachweisen | Nicht unterstützt | Google Play ist auf Android-Geräten Teams installiert.|
| [**Geräteeigenschaften**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Betriebssystemversion (Minimum, Maximum) | Unterstützt |  Nicht zutreffend |
[**Systemsicherheit**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Verschlüsselung der Datenspeicherung auf dem Gerät erforderlich. |Unterstützt |  Nicht zutreffend |
[**Gerätesicherheit**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Blockieren von Apps aus unbekannten Quellen | Nicht unterstützt | Nur Teams installieren Apps oder OEM-Tools |
| Unternehmensportal der App-Laufzeitintegrität | Unterstützt |  Nicht zutreffend|
| Eingeschränkte Apps | Nicht unterstützt |  Nicht zutreffend |
| Blockieren des USB-Debuggens auf dem Gerät | Unterstützt |  Nicht zutreffend|
[**Alle Android-Geräte*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Maximale Zeit der Inaktivität, bevor ein Kennwort erforderlich ist | Nicht unterstützt |  Nicht zutreffend |
| Verlangen eines Kennworts zum Entsperren mobiler Geräte | Nicht unterstützt | Nicht zutreffend |
| [**Android 10 und höher**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 und früher oder Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Erforderlicher Kennworttyp |Nicht unterstützt | Nicht zutreffend|

---

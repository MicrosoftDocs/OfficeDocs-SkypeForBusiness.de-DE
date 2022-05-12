---
title: Verwalten von Voicemailrichtlinien
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Verwalten von Voicemailrichtlinien für Ihre Benutzer.
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370828"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

> [!WARNING]
> Für Skype for Business Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business Benutzer deaktivieren.

Sie können Voicemailrichtlinien verwenden, um verschiedene Features im Zusammenhang mit Cloud-Voicemail zu steuern.

## <a name="voicemail-organization-defaults-for-all-users"></a>Voicemail-Organisationsstandards für alle Benutzer
- Die Voicemailtranskription ist aktiviert.
- Die Übersetzung der Voicemailtranskription ist aktiviert.
- Die Maskierung von Voicemailtranskriptionen ist deaktiviert.
- Die maximale Aufzeichnungsdauer wird auf fünf Minuten festgelegt.
- Die Bearbeitung von Anrufbeantwortungsregeln ist aktiviert.
- Primäre und sekundäre Systemeingabeaufforderungssprachen sind auf NULL festgelegt, und die Voicemail-Spracheinstellung des Benutzers wird verwendet.

Sie können die globale Richtlinie (organisationsweite Standardrichtlinie), die automatisch erstellt wird, verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="create-a-custom-voicemail-policy"></a>Erstellen einer benutzerdefinierten Voicemailrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Voicemailrichtlinie zu erstellen.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoiceVoicemail-Richtlinien** > .
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie die Features, die Sie in Ihrer Voicemailrichtlinie verwenden möchten.
4. Klicken Sie auf **Speichern**.

## <a name="edit-a-voicemail-policy"></a>Bearbeiten einer Voicemailrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Voicemailrichtlinie zu bearbeiten.

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center **VoiceVoicemail-Richtlinien** >  aus.
2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **"Bearbeiten"** aus.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern"**.

> [!IMPORTANT]
> Sie können die vorkonfigurierten Richtlinieninstanzen "TranscriptionDisabled" und "TranscriptionProfanityMaskingEnabled" nicht bearbeiten oder entfernen.


## <a name="assign-a-custom-voicemail-policy-to-users"></a>Zuweisen einer benutzerdefinierten Voicemailrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>Voicemail-Richtlinieneinstellungen
  
### <a name="enable-transcription"></a>Transkription aktivieren

Diese Einstellung steuert, ob der Cloud-Voicemail-Dienst eine Texttransciption der aufgezeichneten Voicemail generiert und in die Voicemailnachricht einschließt. Die Transkription erfolgt basierend auf der Sprache, die in der aufgezeichneten Voicemail erkannt wurde.

### <a name="transcription-translation"></a>Transkriptionsübersetzung

Diese Einstellung steuert, ob der Cloud-Voicemail-Dienst die Transkription der aufgezeichneten Voicemail übersetzt. Die Übersetzung wird in die bevorzugte Sprache des Voicemailempfängers versucht.

### <a name="transcription-profanity-masking"></a>Transkriptions-Profanitätsmaskierung

Mit dieser Einstellung wird gesteuert, ob der Cloud-Voicemail-Dienst die in der Transkription der Voicemail gefundene Untreue maskieren wird.

### <a name="maximum-recording-duration"></a>Maximale Aufzeichnungsdauer

Die maximale Aufzeichnungslänge steuert, wie lange eine Voicemail maximal aufgezeichnet werden kann. Der Standardwert beträgt 5 Minuten.

### <a name="call-answering-rules"></a>Anrufbeantwortungsregeln

Diese Einstellung steuert, ob der Benutzer Voicemail-Anrufbeantwortungsregeln in Microsoft Teams konfigurieren darf.

### <a name="dual-language-system-prompts"></a>Eingabeaufforderungen für duale Sprachen

Standardmäßig werden die Eingabeaufforderungen des Voicemailsystems Anrufern in der Sprache angezeigt, die der Benutzer beim Einrichten seiner Voicemail ausgewählt hat. Wenn eine geschäftliche Anforderung besteht, dass die Voicemail-Systemaufforderungen in zwei Sprachen angezeigt werden, kann eine primäre und sekundäre Sprache festgelegt werden, die möglicherweise nicht identisch ist.

### <a name="share-data-for-service-improvements"></a>Freigeben von Daten für Dienstverbesserungen

Gibt an, ob Voicemail- und Transkriptionsdaten für den Dienst zur Schulung und Verbesserung der Genauigkeit freigegeben werden. Bei Festlegung auf "false" werden Voicemaildaten unabhängig von der Benutzerauswahl nicht freigegeben.


> [!IMPORTANT]
> Der Voicemaildienst in Microsoft 365 und Office 365 speichert Voicemailrichtlinien zwischen und aktualisiert den Cache alle 6 Stunden. Es kann also bis zu 6 Stunden dauern, bis Richtlinienänderungen angewendet werden.

## <a name="related-articles"></a>Verwandte Artikel

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

---
title: Verwalten von Voicemailrichtlinien
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
ms.openlocfilehash: da5909a1d460373be60bf26de08e414ca6470c8a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267750"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>Verwalten Cloud-Voicemail Richtlinien für Ihre Benutzer

> [!WARNING]
> Für Skype for Business Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams-Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business Benutzer deaktivieren.

Mithilfe von Voicemailrichtlinien können Sie vorhandene oder neue Voicemailrichtlinien für Benutzergruppen konfigurieren und zuweisen, um Funktionen wie Anrufbeantwortungsregeln, Voicemailtranskription, Transkription, Transkriptionsübersetzung und Systemeingabeaufforderungssprache zu verwenden.

Bevor Sie Richtlinien angeben, sollten Sie ["Einrichten Cloud-Voicemail](set-up-phone-system-voicemail.md)" lesen. Informationen zum Verwalten von Einstellungen für einzelne Benutzer finden [Sie unter Verwalten von Voicemail-Setltings](manage-voicemail-settings.md).

Zum Verwalten von Voicemailrichtlinien können Sie das Teams Admin Center oder das New-CsOnlineVoicemailPolicy PowerShell-Cmdlet verwenden. 

Die Standardrichtlinien für Benutzer sind:

- Die Voicemailtranskription ist aktiviert.
- Die Übersetzung der Voicemailtranskription ist aktiviert.
- Die Maskierung von Voicemailtranskriptionen ist deaktiviert.
- Die maximale Aufzeichnungsdauer wird auf fünf Minuten festgelegt.
- Die Bearbeitung von Anrufbeantwortungsregeln ist aktiviert.
- Primäre und sekundäre Systemeingabeaufforderungssprachen sind auf NULL festgelegt, und die Voicemail-Spracheinstellung des Benutzers wird verwendet.

Sie können die globale Richtlinie (organisationsweite Standardrichtlinie), die automatisch erstellt wird, verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.

> [!IMPORTANT]
> Der Voicemaildienst in Microsoft 365 speichert Voicemailrichtlinien zwischen und aktualisiert den Cache alle 6 Stunden. Es kann also bis zu 6 Stunden dauern, bis Richtlinienänderungen angewendet werden.

## <a name="use-teams-admin-center"></a>Verwenden des Teams Admin Centers

### <a name="create-a-custom-voicemail-policy"></a>Erstellen einer benutzerdefinierten Voicemailrichtlinie

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Voicemailrichtlinie zu erstellen.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Voicemailrichtlinien** > .

2. Klicken Sie auf **Hinzufügen**.

3. Aktivieren oder deaktivieren Sie die Features, die Sie in Ihrer Voicemailrichtlinie verwenden möchten.

4. Klicken Sie auf **Speichern**.

### <a name="edit-a-voicemail-policy"></a>Bearbeiten einer Voicemailrichtlinie

Führen Sie die folgenden Schritte aus, um eine vorhandene Voicemailrichtlinie zu bearbeiten.

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **Voicemailrichtlinien** >  aus.

2. Klicken Sie neben der Richtlinie, die Sie ändern möchten, und wählen Sie dann **"Bearbeiten"** aus.

3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **"Speichern"**.

> [!IMPORTANT]
> Sie können die vorkonfigurierten Richtlinieninstanzen "TranscriptionDisabled" und "TranscriptionProfanityMaskingEnabled" nicht bearbeiten oder entfernen.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>Zuweisen einer benutzerdefinierten Voicemailrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>Verwenden von PowerShell

Sie können powerShell auch verwenden, um vorhandene oder neue Voicemailrichtlinien zu konfigurieren und zuzuweisen. Verwenden Sie die folgenden Cmdlets, um Richtlinien mithilfe von PowerShell zu verwalten:

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>Voicemail-Richtlinieneinstellungen
  
- **Transkription aktivieren** – Diese Einstellung steuert, ob der Cloud-Voicemail-Dienst eine Text transciption der aufgezeichneten Voicemail generiert und in die Voicemailnachricht einschließt. Die Transkription erfolgt basierend auf der Sprache, die in der aufgezeichneten Voicemail erkannt wurde.

- **Transkriptionsübersetzung** – Diese Einstellung steuert, ob der Cloud-Voicemail-Dienst die Transkription der aufgezeichneten Voicemail übersetzt. Die Übersetzung wird in die bevorzugte Sprache des Voicemailempfängers versucht.

- **Transkriptions-Unanstößigkeitsmaskierung** – Diese Einstellung steuert, ob der Cloud-Voicemail-Dienst die in der Transkription der Voicemail gefundene Anstößigkeit maskieren wird.

- **Maximale Aufzeichnungsdauer** – Die maximale Aufzeichnungsdauer steuert, wie lange eine Voicemail maximal aufgezeichnet werden kann. Der Standardwert beträgt 5 Minuten.

- **Anrufbeantwortungsregeln** – Diese Einstellung steuert, ob der Benutzer Voicemail-Anrufbeantwortungsregeln in Microsoft Teams konfigurieren darf.

- **Eingabeaufforderungen für duale Sprachen** : Standardmäßig werden die Eingabeaufforderungen des Voicemailsystems anrufern in der Sprache angezeigt, die der Benutzer beim Einrichten seiner Voicemail ausgewählt hat. Wenn eine geschäftliche Anforderung besteht, dass die Voicemail-Systemaufforderungen in zwei Sprachen angezeigt werden, kann eine primäre und sekundäre Sprache festgelegt werden, die möglicherweise nicht identisch ist.

### <a name="share-data-for-service-improvements"></a>Freigeben von Daten für Dienstverbesserungen

Gibt an, ob Voicemail- und Transkriptionsdaten für den Dienst zur Schulung und Verbesserung der Genauigkeit freigegeben werden. Bei Festlegung auf "false" werden Voicemaildaten unabhängig von der Benutzerauswahl nicht freigegeben.


## <a name="related-articles"></a>Verwandte Artikel



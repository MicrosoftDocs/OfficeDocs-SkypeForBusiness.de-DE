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
description: Verwalten Sie Voicemailrichtlinien für Ihre Benutzer.
ms.openlocfilehash: 275c67cef3a318d15f030f26aa50a74a15748c03
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604424"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

> [!WARNING]
> Für Skype for Business Kunden kann das Deaktivieren von Voicemail über eine Richtlinie für Microsoft Teams-Anrufe auch den Voicemail-Dienst für Ihre Benutzer Skype for Business deaktivieren.

## <a name="voicemail-organization-defaults-for-all-users"></a>Standardeinstellungen der Voicemailorganisation für alle Benutzer
- Voicemail-Transkription ist aktiviert.
- Voicemail-Transkription obszöne Maskierung ist deaktiviert.
- Die maximale Aufzeichnungsdauer ist auf fünf Minuten festgelegt.

Sie können diese Standardwerte mithilfe der [Cmdlets Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) und [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) steuern.

Voicemailnachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in Microsoft 365 Oder Office 365 Organisation gehostet wird. Die Region, in der Ihr Mandant gehostet wird, ist möglicherweise nicht dieselbe Region, in der sich der Benutzer befindet, der die Voicemailnachricht empfängt. Um die Region anzuzeigen, in der [](https://go.microsoft.com/fwlink/p/?linkid=2067339) Ihr Mandant gehostet  wird, wechseln Sie zur Profilseite Organisation, und klicken Sie dann neben Datenspeicherort auf **Details anzeigen**.

> [!IMPORTANT]
> Sie können mit dem **Cmdlet New-CsOnlineVoiceMailPolicy** keine neue Richtlinieninstanz für die Transkription und Transkription von Obszönitätsmasken erstellen, und Sie können mit dem **Cmdlet Remove-CsOnlineVoiceMailPolicy** keine vorhandene Richtlinieninstanz entfernen.

Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Instanzen der Voicemailrichtlinie zu sehen, können Sie das [Cmdlet Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) verwenden.

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a>Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) deaktivieren. Führen Sie dazu Folgendes aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation

Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert. Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) aktivieren. Führen Sie dazu dies aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>Ändern der Aufzeichnungsdauer für Ihre Organisation

Die maximale Aufzeichnungslänge ist für Ihre Organisation standardmäßig auf fünf Minuten festgelegt. Wenn eine geschäftliche Anforderung zum Erhöhen oder Verringern der maximalen Aufzeichnungslänge besteht, können Sie dazu [Set-CsOnlineVoicemailPolicy verwenden.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Wenn Sie beispielsweise die maximale Aufzeichnungszeit auf 60 Sekunden festlegen möchten, führen Sie folgende Ausführung aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>Systemaufforderungen für zwei Sprachen für Ihre Organisation

Standardmäßig werden Voicemail-Systemanrufe Anrufern in der Sprache angezeigt, die der Benutzer beim Einrichten seiner Voicemail ausgewählt hat. Wenn geschäftliche Anforderungen lauten, dass die Eingabeaufforderungen für das Voicemail-System in zwei Sprachen angezeigt werden, können Sie dazu [Set-CsOnlineVoicemailPolicy verwenden.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) Eine primäre und sekundäre Sprache müssen festgelegt werden und sind möglicherweise nicht identisch. Führen Sie dazu dies aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>Aufzeichnung für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn Voicemail-Transkription beispielsweise für alle Ihre Benutzer aktiviert ist, können Sie mit dem [Grant-CsOnlineVoicemailPolicy-Cmdlet](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) eine Richtlinie zuweisen, um die Transkription für einen bestimmten Benutzer zu deaktivieren.

Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren

Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.

Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>Ändern der Aufzeichnungsdauer für einen Benutzer

Sie müssen zuerst eine benutzerdefinierte Voicemailrichtlinie mit dem [New-CsOnlineVoicemailPolicy-Cmdlet](/powershell/module/skype/New-CsOnlineVoicemailPolicy) erstellen. Mit dem unten gezeigten Befehl wird eine Online-Voicemailrichtlinie für pro Benutzer OneMinuteVoicemailPolicy erstellt, bei der MaximumRecordingLength auf 60 Sekunden und andere Felder auf den globalen Wert auf Mandantenebene festgelegt sind.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

Führen Sie zum Zuweisen dieser benutzerdefinierten Richtlinie zu einem Benutzer: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>Systemaufforderungen für zwei Sprachen für einen Benutzer

Sie müssen zuerst eine benutzerdefinierte Voicemailrichtlinie mit dem [New-CsOnlineVoicemailPolicy-Cmdlet](/powershell/module/skype/New-CsOnlineVoicemailPolicy) erstellen. Mit dem unten gezeigten Befehl wird eine Online-Voicemailrichtlinie für benutzerspezifische Voicemail enUS-esSP-VoicemailPolicy erstellt, bei der PrimarySystemPromptLanguage auf en-US (Englisch – Vereinigte Staaten) und secondarySystemPromptLanguage auf es-SP (Spanisch – Spanien) festgelegt ist.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

Führen Sie zum Zuweisen dieser benutzerdefinierten Richtlinie zu einem Benutzer: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> Das Get-CsOnlineVoicemailPolicy gibt derzeit nicht die Werte für PrimarySystemPromptLanguage und SecondarySystemPromptLanguage zurück. Wenn Sie diese Werte sehen möchten, ändern Sie den Befehl wie folgt:
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> Ersetzen **Sie PolicyName** durch den Namen der Richtlinie.


> [!IMPORTANT]
> Der Voicemaildienst in Microsoft 365 und Office 365 Voicemailrichtlinien zwischen und aktualisiert den Cache alle 6 Stunden. Daher kann es bis zu sechs Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.

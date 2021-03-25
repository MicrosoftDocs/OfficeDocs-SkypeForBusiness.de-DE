---
title: Einrichten von Cloudvoicemail
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Erfahren Sie, wie Sie Cloud Voicemail für Ihre Benutzer einrichten. '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117063"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloudvoicemail

Dieser Artikel gilt für den Microsoft 365- oder [](/microsoft-365/admin/add-users/about-admin-roles) Office 365-Administrator, wie unter Informationen zu Administratorrollen beschrieben, der das Cloud Voicemail-Feature für alle Unternehmen einrichten möchte.

> [!NOTE]
> Cloud Voicemail unterstützt das Speichern von Voicemailnachrichten nur in einem Exchange-Postfach und keine E-Mail-Systeme von Drittanbietern. 

> [!NOTE]
> Wenn eine Stellvertretung einen Anruf im Auftrag eines Delegators beantwortet, sind Benachrichtigungen in Cloud Voicemail nicht verfügbar. Benutzer können Benachrichtigungen über verpasste Anrufe erhalten.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Nur-Cloud-Umgebungen: Einrichten von Cloud Voicemail für Benutzer des Onlinetelefonsystems

Für Benutzer des Onlinetelefonsystems wird Cloud Voicemail automatisch eingerichtet und  für Benutzer bereitgestellt, nachdem Sie den Benutzern eine Telefonsystemlizenz zugewiesen haben. 

> [!NOTE]
> Bei Skype for Business Phone System-Onlinebenutzern mit lokal bereitgestellten Telefonnummern müssen Sie möglicherweise gehostete Voicemail mit [Set-CsUser -HostedVoicemail $True.](/powershell/module/skype/set-csuser?view=skype-ps) 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud Voicemail für Exchange Server Postfachbenutzer

In den folgenden Informationen geht es um das Konfigurieren von Cloud Voicemail für die Zusammenarbeit mit Benutzern, die für Telefonsystem online sind, aber ihr Postfach auf Exchange Server. 
  
1. Voicemailnachrichten werden über SMTP, das über Exchange Online Protection geroutet wird, an das Exchange-Postfach der Benutzer übermittelt. Um die erfolgreiche Übermittlung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass #A0 zwischen Ihren #A1 und Exchange Online Protection ordnungsgemäß konfiguriert sind. [Verwenden Sie Connectors zum Konfigurieren des Nachrichtenflusses.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Zum Aktivieren von Voicemailfeatures wie anpassen von Begrüßungen und visueller Voicemail in Skype for Business-Clients ist eine Konnektivität von Microsoft 365 oder Office 365 mit dem Exchange-Serverpostfach über Exchange Web Services erforderlich. Um diese Konnektivität zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter Konfigurieren der OAuth-Authentifizierung zwischen [Exchange-](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)und Exchange Online-Organisationen beschrieben wird, oder den Exchange-Hybrid-Assistenten aus Exchange 2013 CU5 oder höher ausführen. Darüber hinaus müssen Sie die Integration und Oauth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter Konfigurieren von Integration und [OAuth zwischen Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)und Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Einrichten von Cloud Voicemail für Skype for Business Server-Benutzer

Informationen zum Konfigurieren von Skype for Business-Serverbenutzern für Cloud Voicemail finden Sie unter [Planen des Cloud voicemail-Diensts für](/skypeforbusiness/hybrid/plan-cloud-voicemail)lokale Benutzer.

## <a name="enabling-protected-voicemail-in-your-organization"></a>Aktivieren von geschützter Voicemail in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Voicemail als Anlage einer E-Mail-Nachricht an das Postfach des Benutzers übermittelt. Mithilfe von Nachrichtenflussregeln zum Anwenden der Nachrichtenverschlüsselung können Sie verhindern, dass diese Voicemailnachrichten an andere Empfänger weitergeleitet werden. Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten anhören, indem sie in ihr Voicemailpostfach anrufen oder die Nachricht in Outlook, Outlook im Web oder in Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können in Skype for Business oder Microsoft Teams nicht geöffnet werden.

Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [E-Mail-Verschlüsselung.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Gehen Sie wie folgt vor, um eine geschützte Voicemail zu einrichten:

1. Wechseln Sie https://admin.microsoft.com zu und melden Sie sich mit einem Konto mit globalen Administratorberechtigungen an.
2. Wählen **Sie Alle anzeigen** aus, und wechseln Sie dann zu Admin **Center**  >  **Exchange.**
3. Wählen Sie im Exchange Admin Center die Option **E-Mail-Flussregeln**  >  **aus.**
4. Wählen **+** **Sie Hinzufügen** und dann **Office 365-Nachrichtenverschlüsselung** und Rechteschutz auf Nachrichten anwenden aus.
5. Geben Sie einen Namen für die neue E-Mail-Flussregel ein, und wählen Sie dann unter Diese Regel **anwenden, wenn**, die Nachrichteneigenschaften Enthalten den Nachrichtentyp   >    >  **Voicemail aus.** Wählen Sie **OK aus.**
6. Wählen **Sie unter Wie folgt vor,** die Option Office **365-Nachrichtenverschlüsselung** und -Rechteschutz auf die Nachricht anwenden mit aus, und wählen Sie **dann Eine auswählen aus.** Wählen **Sie unter RMS-Vorlage** die Option **Nicht weiterleiten aus.** Wählen Sie **OK** und dann **Speichern aus.**
    > [!NOTE]
    > Wenn die **RmS-Vorlagenliste** leer ist, müssen Sie die Nachrichtenverschlüsselung einrichten. Weitere Informationen zum Einrichten der Nachrichtenverschlüsselung finden Sie in den folgenden Artikeln:
    > - [Einrichten neuer Nachrichtenverschlüsselungsfunktionen](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)
    > - [Option "Nicht weiterleiten" für E-Mails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

> [!WARNING]
> Für Skype for Business-Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams-Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business-Benutzer deaktivieren.

Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) und [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) steuern.

Voicemailnachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in der Ihre Microsoft 365- oder Office 365-Organisation gehostet wird. Die Region, in der Ihr Mandant gehostet wird, ist möglicherweise nicht dieselbe Region, in der sich der Benutzer befindet, der die Voicemailnachricht empfängt. Um die Region anzuzeigen, in der [](https://go.microsoft.com/fwlink/p/?linkid=2067339) Ihr Mandant gehostet  wird, wechseln Sie zur Profilseite Organisation, und klicken Sie dann neben **Datenspeicherort** auf Details anzeigen.

> [!IMPORTANT]
> Sie können mit dem **Cmdlet New-CsOnlineVoiceMailPolicy** keine neue Richtlinieninstanz für die Transkription und Transkription der Profanitätsformatierung erstellen, und Sie können keine vorhandene Richtlinieninstanz mit dem **Cmdlet Remove-CsOnlineVoiceMailPolicy** entfernen.

Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Voicemailrichtlinieninstanzen zu sehen, können Sie das [Cmdlet Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) verwenden.

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
  
### <a name="turning-off-transcription-for-your-organization"></a>Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) deaktivieren. Führen Sie dazu Folgendes aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation

Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert. Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) aktivieren. Führen Sie dazu Dies aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Aufzeichnung für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn beispielsweise die Voicemail-Transkription für alle Benutzer aktiviert ist, können Sie mithilfe des [Grant-CsOnlineVoicemailPolicy-Cmdlets](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) eine Richtlinie zum Deaktivieren der Transkription für einen bestimmten Benutzer zuweisen.

Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren

Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.

Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Der Voicemaildienst in Microsoft 365 und Office 365 speichert Voicemailrichtlinien zwischen und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Hilfe für Ihre Benutzer beim Erlernen der Voicemailfeatures von Teams

Wir verfügen über die folgenden Informationen für Ihre Benutzer zum Verwalten ihrer Voicemaileinstellungen sowie zu anderen Anruffunktionen in Teams:

- [Verwalten Sie Ihre Anrufeinstellungen in Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) In diesem Artikel wird erläutert, wie sie alle Anruffunktionen von Endbenutzern in Teams verwalten. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:

- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.

- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)

[Planen der Migration von Skype for Business Server und Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)
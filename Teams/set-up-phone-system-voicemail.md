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
description: 'Erfahren Sie, wie Sie Cloud-Voicemail für Ihre Benutzer einrichten. '
ms.openlocfilehash: 4ed61a825ce4e583c71f052020692e4478324003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117063"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloudvoicemail

Dieser Artikel gilt für Microsoft 365 oder Office 365 Administrator, [](/microsoft-365/admin/add-users/about-admin-roles) wie unter Informationen zu Administratorrollen beschrieben, die das Cloud-Voicemail-Feature für alle Benutzer im Unternehmen einrichten.

> [!NOTE]
> Cloud-Voicemail unterstützt die Ablage von Voicemailnachrichten nur in einem Exchange-Postfach und unterstützt keine E-Mail-Systeme von Drittanbietern. 

> [!NOTE]
> Wenn eine Stellvertretung einen Anruf im Namen eines Delegators beantwortet, sind in der Stellvertretung keine Benachrichtigungen Cloud-Voicemail. Benutzer können Benachrichtigungen über verpasste Anrufe erhalten.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Nur-Cloud-Umgebungen: Einrichten Cloud-Voicemail für Onlinebenutzer Telefonsystem Benutzer

Für Onlinebenutzer Telefonsystem Benutzer Cloud-Voicemail Benutzer automatisch eingerichtet und bereitgestellt, nachdem  Sie den Benutzern eine Telefonsystem-Lizenz zugewiesen haben. 

> [!NOTE]
> Für Online Skype for Business Telefonsystem mit lokal bereitgestellten Telefonnummern müssen Sie möglicherweise gehostete Voicemail mit [Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)und $True. 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud-Voicemail für Exchange Server Postfachbenutzer

Die folgenden Informationen enthalten Informationen zum Konfigurieren Cloud-Voicemail, damit sie mit Benutzern zusammenarbeiten, die für Telefonsystem deren Postfach aber ein Postfach aktiviert Exchange Server. 
  
1. Voicemailnachrichten werden an das Postfach Exchange benutzerpostfachs über SMTP übermittelt, das über Exchange Online Protection. Um eine erfolgreiche Übermittlung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange Connectors zwischen Ihren Exchange-Servern und Exchange Online Protection; [Verwenden Von Connectors können Sie E-Mail-Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Um Voicemailfunktionen zu aktivieren, z. B. das Anpassen von Begrüßungen und visuellen Voicemails in Skype for Business-Clients, ist eine Verbindung von Microsoft 365 oder Office 365 zum Exchange-Serverpostfach über Exchange-Webdienste erforderlich. Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter Konfigurieren der [OAuth-Authentifizierung](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)zwischen Exchange und Exchange Online-Organisationen beschrieben ist, oder den Exchange-Hybrid-Assistenten von Exchange 2013 CU5 oder höher ausführen. Darüber hinaus müssen Sie die Integration und Oauth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter Konfigurieren der Integration und [OAuth zwischen Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)und Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Einrichten von Cloud-Voicemail für Skype for Business Server Benutzer

Informationen zum Skype for Business von Serverbenutzern Cloud-Voicemail Sie unter [Planen Cloud-Voicemail Diensts](/skypeforbusiness/hybrid/plan-cloud-voicemail)für lokale Benutzer.

## <a name="enabling-protected-voicemail-in-your-organization"></a>Aktivieren geschützter Voicemails in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Voicemail als Anlage einer E-Mail-Nachricht an das Postfach des Benutzers zugestellt. Wenn Sie Nachrichtenverschlüsselung mithilfe von Nachrichtenflussregeln anwenden, können Sie verhindern, dass diese Voicemailnachrichten an andere Empfänger weitergeleitet werden. Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten abhören, indem sie sich in ihr Voicemail-Postfach einrufen oder die Nachricht in Outlook, Outlook im Web oder in Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können nicht in anderen Skype for Business oder auf Microsoft Teams.

Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [E-Mail-Verschlüsselung.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Gehen Sie wie folgt vor, um geschützte Voicemails zu einrichten:

1. Wechseln Sie zu https://admin.microsoft.com , und melden Sie sich mit einem Konto mit globalen Administratorberechtigungen an.
2. Wählen **Sie Alle anzeigen** aus, und wechseln Sie dann zu Admin **Center**  >  **Exchange.**
3. Wählen Sie Exchange Admin Center die Option **Nachrichtenflussregeln**  >  **aus.**
4. Wählen **+** **Sie Hinzufügen** aus, und wählen Sie dann Office 365-Nachrichtenverschlüsselung **- und -Rechteschutz auf Nachrichten anwenden aus.**
5. Geben Sie einen Namen für die neue Nachrichtenflussregel ein, und wählen Sie dann unter Diese Regel **anwenden, wenn** die Option Die Nachrichteneigenschaften Schließen Sie den Nachrichtentyp   >    >  **Voicemail ein.** Wählen Sie **OK aus.**
6. Wählen **Sie unter Gehen Sie wie folgt** vor die Option Anwenden **Office 365-Nachrichtenverschlüsselung-** und Rechteschutz auf die Nachricht mit aus, und wählen Sie **dann eine aus.** Wählen **Sie unter RMS-Vorlage** die Option **Nicht weiterleiten aus.** Wählen **Sie OK** und dann Speichern **aus.**
    > [!NOTE]
    > Wenn die **RMS-Vorlagenliste** leer ist, müssen Sie die Nachrichtenverschlüsselung einrichten. Weitere Informationen zum Einrichten der Nachrichtenverschlüsselung finden Sie in den folgenden Artikeln:
    > - [Einrichten neuer Nachrichtenverschlüsselungsfunktionen](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)
    > - [Option "Nicht weiterleiten" für E-Mails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

> [!WARNING]
> Für Skype for Business Kunden kann das Deaktivieren von Voicemail über eine Richtlinie für Microsoft Teams-Anrufe auch den Voicemaildienst für Ihre Benutzer Skype for Business deaktivieren.

Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) und [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) steuern.

Voicemailnachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in Microsoft 365 Oder Office 365 Organisation gehostet wird. Die Region, in der Ihr Mandant gehostet wird, ist möglicherweise nicht dieselbe Region, in der sich der Benutzer befindet, der die Voicemailnachricht empfängt. Um die Region anzuzeigen, in der [](https://go.microsoft.com/fwlink/p/?linkid=2067339) Ihr Mandant gehostet  wird, wechseln Sie zur Profilseite Organisation, und klicken Sie dann neben **Datenspeicherort** auf Details anzeigen .

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
  
### <a name="turning-off-transcription-for-your-organization"></a>Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) deaktivieren. Führen Sie dazu Folgendes aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation

Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert. Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) aktivieren. Führen Sie dazu dies aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Aufzeichnung für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn Voicemail-Transkription beispielsweise für alle Ihre Benutzer aktiviert ist, können Sie mit dem [Grant-CsOnlineVoicemailPolicy-Cmdlet](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) eine Richtlinie zum Deaktivieren der Transkription für einen bestimmten Benutzer zuweisen.

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
> Der Voicemaildienst in Microsoft 365 und Office 365 Voicemailrichtlinien zwischen und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Unterstützen der Benutzer beim Erlernen Teams Voicemail-Funktionen

Wir haben die folgenden Informationen für Ihre Benutzer zum Verwalten ihrer Voicemaileinstellungen sowie weitere Anruffunktionen in Teams:

- [Verwalten Sie Ihre Anrufeinstellungen in Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) In diesem Artikel wird erläutert, wie Sie alle Anruffunktionen Teams Endbenutzer verwalten. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:

- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.

- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)

[Planen der Migration von Skype for Business Server und Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)
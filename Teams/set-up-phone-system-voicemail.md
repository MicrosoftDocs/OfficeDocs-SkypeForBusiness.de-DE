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
description: 'Hier erfahren Sie, wie Sie Cloud Voicemail für Ihre Benutzer einrichten. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662210"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloudvoicemail

Dieser Artikel richtet sich an den Microsoft 365-oder Office 365-Administrator, wie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) beschrieben, die das Feature für die Cloud-Voicemail für alle Personen im Unternehmen einrichten möchten.

> [!NOTE]
> Cloud Voicemail unterstützt das Hinterlegen von Voicemail-Nachrichten nur in einem Exchange-Postfach und unterstützt keine e-Mail-Systeme von Drittanbietern. 

> [!NOTE]
> Wenn eine Stellvertretung einen Anruf im Namen eines delegierenden beantwortet, sind Benachrichtigungen in Cloud Voicemail nicht verfügbar. Benutzer können Benachrichtigungen für verpasste Anrufe erhalten.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Cloud-only-Umgebungen: Einrichten von Cloud Voicemail für Online-Telefon System Benutzer

Für Benutzer von Online-Telefonsystemen wird Cloud Voicemail automatisch für Benutzer eingerichtet und bereitgestellt, nachdem Sie den Benutzern eine **Telefonsystem** Lizenz zugewiesen haben. 

> [!NOTE]
> Bei Online-Skype for Business-Telefon System Benutzern mit lokal bereitgestellten Telefonnummern müssen Sie möglicherweise die gehostete Voicemail mit der [$true "CsUser-HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)" aktivieren. 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud Voicemail für Exchange Server-Postfachbenutzer

Die folgenden Informationen besprechen die Konfiguration von Cloud Voicemail für die Arbeit mit Benutzern, die für das Telefon System online sind, aber über Ihr Postfach auf dem Exchange-Server verfügen. 
  
1. Voicemail-Nachrichten werden an das Exchange-Postfach der Benutzer über einen SMTP-Router über den Exchange Online-Schutz übermittelt. Um eine erfolgreiche Zustellung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange-Connectors zwischen Ihren Exchange-Servern und dem Exchange Online-Schutz ordnungsgemäß konfiguriert sind. [Verwenden Sie Connectors zum Konfigurieren des Nachrichtenflusses](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Um Voicemail-Features wie das Anpassen von Begrüßungen und visuelle Voicemail in Skype for Business-Clients zu aktivieren, ist die Konnektivität von Microsoft 365 oder Office 365 mit dem Exchange Server-Postfach über Exchange-Webdienste erforderlich. Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange-OAuth-Authentifizierungsprotokoll konfigurieren, das unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange-und Exchange Online-Organisationen](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)beschrieben wird, oder den Exchange-Hybrid-Assistenten in Exchange 2013 CU5 oder höher ausführen. Darüber hinaus müssen Sie die Integration und die OAuth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben sind. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Einrichten von Cloud Voicemail für Skype for Business Server-Benutzer

Informationen zum Konfigurieren von Skype for Business Server-Benutzern für Cloud Voicemail finden Sie unter [Planen des Cloud Voicemail-Diensts für lokale Benutzer](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="enabling-protected-voicemail-in-your-organization"></a>Aktivieren von geschützter Voicemail in Ihrer Organisation

Wenn jemand eine Sprachnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Sprachnachricht als Anlage für e-Mail-Nachrichten an das Postfach des Benutzers übermittelt. Wenn Sie Nachrichtenfluss Regeln verwenden, um die Nachrichtenverschlüsselung anzuwenden, können Sie verhindern, dass diese Voicemail-Nachrichten an andere Empfänger weitergeleitet werden. Wenn Sie Geschützte Voicemail aktivieren, können Benutzer geschützte Voicemail-Nachrichten abhören, indem Sie in Ihr Voicemail-Postfach anrufen oder die Nachricht in Outlook, Outlook im Web oder in Outlook für Android oder IOS öffnen. Geschützte Voicemail-Nachrichten können in Skype for Business oder Microsoft Teams nicht geöffnet werden.

Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [e-Mail-Verschlüsselung](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).

Gehen Sie wie folgt vor, um geschützte Voicemail einzurichten:

1. Wechseln Sie zu und registrieren Sie sich mit https://admin.microsoft.com einem Konto mit globalen Administratorberechtigungen.
2. Wählen Sie **Alle anzeigen** aus, und wechseln Sie dann zu **Admin Center**  >  **Exchange**.
3. Wählen Sie im Exchange Admin Center die Option **Nachrichtenfluss**  >  **Regeln** aus.
4. Wählen Sie **+** **Hinzufügen** aus, und wählen Sie dann **Office 365-Nachrichtenverschlüsselung und-Rechte Schutz auf Nachrichten anwenden** aus.
5. Geben Sie einen Namen für die neue Nachrichtenfluss Regel ein, und wählen Sie dann unter **diese Regel anwenden, wenn** die **Nachrichteneigenschaften**  >  **den Nachrichtentyp**  >  **Voicemail** enthalten aus. Wählen Sie **OK** aus.
6. Wählen Sie unter **Folgendes ausführen die** Option **Office 365-Nachrichtenverschlüsselung und-Rechte Schutz auf die Nachricht anwenden** aus, und wählen Sie dann **auswählen** aus. Wählen Sie unter **RMS-Vorlage** die Option **nicht weiterleiten** aus. Klicken Sie auf **OK** und dann auf **Speichern**.
    > [!NOTE]
    > Wenn die Liste der **RMS-Vorlagen** leer ist, müssen Sie die Nachrichtenverschlüsselung einrichten. Weitere Informationen zum Einrichten der Nachrichtenverschlüsselung finden Sie in den folgenden Artikeln:
    > - [Einrichten neuer Nachrichten Verschlüsselungsfunktionen](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Option "nicht weiterleiten" für e-Mails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

> [!WARNING]
> Bei Skype for Business-Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams-Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business-Benutzer deaktivieren.

Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.

Voicemail-Nachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in der Ihre Microsoft 365-oder Office 365-Organisation gehostet wird. Der Bereich, in dem der Mandant gehostet wird, ist möglicherweise nicht derselbe Bereich, in dem sich der Benutzer befindet, der die Sprachnachricht empfängt. Um die Region anzuzeigen, in der Ihr Mandant gehostet wird, wechseln Sie zur Seite [Organisationsprofil](https://go.microsoft.com/fwlink/p/?linkid=2067339) , und klicken Sie dann neben **Datenspeicherort** auf **Details anzeigen** .

> [!IMPORTANT]
> Mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** können Sie keine neue Richtlinieninstanz für Transkriptions-und Transkriptions Obszönitäten erstellen, und Sie können eine vorhandene Richtlinieninstanz nicht mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** entfernen.

Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Voicemail-Richtlinieninstanzen anzuzeigen, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.

 **PS C: \\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation

Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert. Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) aktivieren. Führen Sie dazu die folgenden Aktionen aus:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Aufzeichnung für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn beispielsweise die Voicemail-Transkription für alle Benutzer aktiviert ist, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) eine Richtlinie zum Deaktivieren der Transkription für einen bestimmten Benutzer zuweisen.

Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren

Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.

Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Der Voicemaildienst in Microsoft 365 und Office 365 speichert Voicemail-Richtlinien zwischen und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Unterstützen der Benutzer bei der Sprachnachrichten Funktion von Teams

Wir haben die folgenden Informationen für Ihre Benutzer bei der Verwaltung Ihrer Voicemail-Einstellungen sowie anderer Anruffunktionen in Teams:

- [Verwalten Sie Ihre Anrufeinstellungen in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). In diesem Artikel wird erläutert, wie alle Anruffeatures für Endbenutzer Teams verwaltet werden. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:

- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.

- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Planen der Migration von Skype for Business Server und Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

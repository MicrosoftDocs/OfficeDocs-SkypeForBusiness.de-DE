---
title: Einrichten von Voicemail für das Telefonsystem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Erfahren Sie, wie Sie ein Voicemail Telefonsystem (Cloud, PBX) für Ihr Skype for Business Users einrichten. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252889"
---
# <a name="set-up-phone-system-voicemail"></a>Einrichten von Voicemail für das Telefonsystem

Dieser Artikel richtet sich an Administratoren von [Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), die die Voicemailfunktion für Telefonsysteme für alle Mitarbeiter im Unternehmen einrichten möchten.

> [!NOTE]
> Voicemail für Telefonsysteme unterstützt die Ablage von Voicemailnachrichten nur in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. Als Ausweichmechanismus kann Voicemail für Telefonsysteme Nachrichten über SMTP erneut senden. Das bedeutet, dass Benutzer mit einem Postfach in einem E-Mail-System eines Drittanbieters ihre Voicemailnachrichten ohne garantierte Dienstbetriebszeit oder andere Voicemailfunktionen (beispielsweise Ändern ihrer Begrüßung und anderer Einstellungen) erhalten.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Reine Cloudumgebungen: Einrichten von Voicemail für Telefonsysteme

Für Benutzer von Skype for Business Online und Anrufplänen wird Voicemail für Telefonsysteme automatisch eingerichtet und für Benutzer bereitgestellt, nachdem Sie den Benutzern eine **Telefonsystemlizenz** und eine Telefonnummer zugewiesen haben.

1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen. Siehe [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) und die Exchange Online-Lizenzen den jeweiligen Personen in Ihrem Unternehmen zu. Anschließend können sie Voicemailnachrichten empfangen.

3. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.

## <a name="phone-system-with-on-premises-environments"></a>Telefonsystem in lokalen Umgebungen

Den folgenden Informationen können Sie entnehmen, wie Sie Voicemail für Telefonsysteme für die Verwendung in lokalen Umgebungen mit Anrufplänen konfigurieren.

1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen auch eine Exchange Online-Lizenz kaufen. Siehe [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) und die Exchange Online-Lizenzen den jeweiligen Personen in Ihrem Unternehmen zu.

3. Folgen Sie den Anweisungen im Abschnitt **Aktivieren von Benutzern für Telefonsystem-VoIP und Voicemail** des [Konfigurationshandbuchs für die Skype for Business Cloud Connector-Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).

4. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.

5. Unter [Unterstützung für Azure-PBX-Voicemail für Exchange Server](https://support.microsoft.com/en-us/kb/3195158) können Sie nachlesen, wie Sie die Übermittlung von Azure-Voicemailnachrichten für Telefonsystembenutzer mit lokalen Postfächern konfigurieren.

## <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) steuern.

> [!IMPORTANT]
> Sie können mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** keine neue Richtlinieninstanz für die Profanität-Maskierung während der Transkription erstellen, und Sie können mit dem Cmdlet **Remove-CsOnlineVoiceMailPolicy** keine vorhandene Richtlinieninstanz entfernen.

Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Instanzen der Voicemailrichtlinien anzuzeigen, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation

Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert. Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) aktivieren. Zu diesem Zweck führen Sie Folgendes aus:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Transkription für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn beispielsweise Voicemailtranskription für alle Benutzer aktiviert ist, können Sie mit dem Cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) eine Richtlinie zuweisen, um die Transkription für einen bestimmten Benutzer zu deaktivieren.

Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren

Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.

Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:

- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.

- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Das bekommen Sie mit dem Telefonsystem in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)



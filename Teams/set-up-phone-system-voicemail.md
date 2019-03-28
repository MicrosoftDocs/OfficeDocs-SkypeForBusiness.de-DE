---
title: Einrichten von Cloud-Voicemail
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Informationen Sie zum Einrichten von Voicemail Cloud für Ihre Benutzer. '
ms.openlocfilehash: 8219934b8e95962f0e9ea81f4965ad9e5c55fb34
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934772"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloud-Voicemail

Dieser Artikel ist für die [Office 365-Admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , möchte das Cloud-Voicemail-Feature für alle Benutzer im Unternehmen eingerichtet.

> [!NOTE]
> Cloud Voicemail unterstützt Voicemailnachrichten Hinterlegung nur in einem Exchange-Postfach und Drittanbieter-e-Mail-Systemen nicht unterstützt. Als ein Sicherungsmechanismus Cloud Voicemail-Nachrichten mithilfe von SMTP, d. h., Benutzer mit einem Postfach auf einem Drittanbieter-e-Mail-System erhalten ihre Voicemail-Nachrichten mit keine zuverlässiger Dienst Betriebszeit oder andere Voicemail-Features, beispielsweise ändern senden können ihre Ansagen und andere Einstellungen.

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Nur-Cloud-Umgebungen: Einrichten von Cloud-Voicemail

Cloud-Voicemail wird für Skype für Benutzer Online Business und plant aufrufen einrichten und für Benutzer bereitgestellt werden, nachdem Sie ihnen eine Lizenz **Telefonsystem** und eine Telefonnummer zuweisen.
  
1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen. Finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md)und die Exchange Online Lizenzen an die Personen in Ihrem Unternehmen. After you do that, they will be able to receive voicemail messages!
    
3. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.

## <a name="phone-system-with-on-premises-environments"></a>Telefonsystem in lokalen Umgebungen

Die folgenden Informationen sind zum Konfigurieren von Cloud-Voicemail lokale aufrufen planen Umgebungen entwickelt.
  
1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen auch eine Exchange Online-Lizenz kaufen. Finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md)und die Exchange Online Lizenzen an die Personen in Ihrem Unternehmen.
    
3. Befolgen Sie die Anweisungen im Abschnitt **Aktivieren von Benutzern für Telefonsystem Sprach- und Voicemail-Dienste** von der [Skype für Business Cloud Connector Edition Handbuch konfigurieren](https://technet.microsoft.com/library/mt605228.aspx).

4. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.

5. Unter [Unterstützung für Azure-PBX-Voicemail für Exchange Server](https://support.microsoft.com/kb/3195158) können Sie nachlesen, wie Sie die Übermittlung von Azure-Voicemailnachrichten für Telefonsystembenutzer mit lokalen Postfächern konfigurieren.

6. Wenden Sie sich auch lesen und befolgen Sie die Schritte im folgenden Dokument: [Hybrid-Konfigurations-Assistenten](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)

## <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.

> [!IMPORTANT]
> Sie können eine neue Richtlinieninstanz für Umsetzung und Lautschrift Gotteslästerung maskieren mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** erstellen, und eine vorhandene Richtlinieninstanz mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** kann nicht entfernt werden .

Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Voicemail-Richtlinieninstanzen angezeigt wird, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Deaktivieren der Aufzeichnung für Ihre Organisation

Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation

Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert. Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) aktivieren. Zu diesem Zweck führen Sie Folgendes aus:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Aufzeichnung für einen Benutzer deaktivieren

Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn Voicemail Lautschrift für alle Benutzer aktiviert ist, können Sie beispielsweise eine Richtlinie Lautschrift für einen bestimmten Benutzer zu deaktivieren, indem Sie mit dem Cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) zuweisen.

Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren

Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.

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
[Einrichten von Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Das bekommen Sie mit Telefonsystem in Office 365](here-s-what-you-get-with-phone-system.md)



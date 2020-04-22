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
ms.openlocfilehash: 4f85e8db6f50becb4ae2406e84621c08507e9737
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779731"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloudvoicemail

Dieser Artikel richtet sich an den [Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , der die Cloud-Voicemail-Funktion für alle Personen im Unternehmen einrichten möchte.

> [!NOTE]
> Cloud Voicemail unterstützt das Hinterlegen von Voicemail-Nachrichten nur in einem Exchange-Postfach und unterstützt keine e-Mail-Systeme von Drittanbietern. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Cloud-only-Umgebungen: Einrichten von Cloud-Voicemail

Bei Skype for Business Online-und Anruf Plan Benutzern wird Cloud Voicemail automatisch für Benutzer eingerichtet und bereitgestellt, nachdem Sie Ihnen eine **Telefon System** Lizenz und eine Telefonnummer zugewiesen haben.
  
1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen. Weitere Informationen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Zuweisen oder Entfernen von Lizenzen für Office 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md)und Exchange Online-Lizenzen für die Personen in Ihrem Unternehmen. Anschließend können sie Voicemailnachrichten empfangen.
    
3. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.

## <a name="phone-system-with-on-premises-environments"></a>Telefonsystem in lokalen Umgebungen

Die folgenden Informationen bezieht sich auf die Konfiguration von Cloud Voicemail für die Arbeit mit lokalen Anruf Plan Umgebungen.
  
1. Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen. Sie müssen auch eine Exchange Online-Lizenz kaufen. Weitere Informationen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Zuweisen oder Entfernen von Lizenzen für Office 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md)und Exchange Online-Lizenzen für die Personen in Ihrem Unternehmen.
    
3. Befolgen Sie die Anweisungen für die lokale PSTN-Anruf Lösung, die für Ihre Benutzer bereitgestellt wird. Befolgen Sie für Cloud Connector Edition die Anweisungen im Abschnitt **Benutzer für Telefon System-sprach-und Voicemail-Dienste aktivieren** des [Skype for Business Cloud Connector Edition-Handbuchs](https://technet.microsoft.com/library/mt605228.aspx). Für PSTN-Anrufe mit Skype for Business Server, folgen Sie [Aktivieren der Benutzer für Enterprise-VoIP lokal](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises). Wenn Sie das direkte Routing von Teams ausführen möchten, folgen Sie dem Abschnitt konfigurieren **der Telefonnummer und Aktivieren von Enterprise-VoIP und Voicemail** unter [Konfigurieren des direkten Routings](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).

4. Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.

5. Voicemail-Nachrichten werden an das Exchange-Postfach der Benutzer über einen SMTP-Router über den Exchange Online-Schutz übermittelt. Um eine erfolgreiche Zustellung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange-Connectors zwischen Ihren Exchange-Servern und dem Exchange Online-Schutz ordnungsgemäß konfiguriert sind. [Verwenden Sie Connectors zum Konfigurieren des Nachrichtenflusses](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

6. Um Voicemail-Features wie das Anpassen von Begrüßungen und visuelle Voicemail in Skype for Business-Clients zu aktivieren, ist die Konnektivität von Office 365 mit dem Exchange Server-Postfach über Exchange-Webdienste erforderlich. Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, das unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange-und Exchange Online-Organisationen](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)beschrieben wird, oder den Exchange-Hybrid-Assistenten in Exchange 2013 CU5 oder höher ausführen. Darüber hinaus müssen Sie die Integration und die OAuth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben sind. 

> [!NOTE]
> Wenn eine Stellvertretung einen Anruf im Namen eines delegierenden beantwortet, sind Benachrichtigungen in Cloud Voicemail nicht verfügbar. Benutzer können Benachrichtigungen für verpasste Anrufe erhalten.

## <a name="setting-voicemail-policies-in-your-organization"></a>Einrichten von Voicemailrichtlinien in Ihrer Organisation

> [!WARNING]
> Bei Skype for Business-Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams-Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business-Benutzer deaktivieren.

Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.

Voicemail-Nachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in der Ihre Office 365-Organisation gehostet wird. Der Bereich, in dem der Mandant gehostet wird, ist möglicherweise nicht derselbe Bereich, in dem sich der Benutzer befindet, der die Sprachnachricht empfängt. Um die Region anzuzeigen, in der Ihr Mandant gehostet wird, wechseln Sie zur Seite [Organisationsprofil](https://go.microsoft.com/fwlink/p/?linkid=2067339) , und klicken Sie dann neben **Datenspeicherort**auf **Details anzeigen** .

> [!IMPORTANT]
> Mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** können Sie keine neue Richtlinieninstanz für Transkriptions-und Transkriptions Obszönitäten erstellen, und Sie können eine vorhandene Richtlinieninstanz nicht mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** entfernen.

Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten. Um alle verfügbaren Voicemail-Richtlinieninstanzen anzuzeigen, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
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
> Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Unterstützen der Benutzer bei der Sprachnachrichten Funktion von Teams

Wir haben die folgenden Informationen für Ihre Benutzer bei der Verwaltung Ihrer Voicemail-Einstellungen sowie anderer Anruffunktionen in Teams:

- [Verwalten Sie Ihre Anrufeinstellungen in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). In diesem Artikel wird erläutert, wie alle Anruffeatures für Endbenutzer Teams verwaltet werden. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:

- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.

- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Planen der Migration von Skype for Business Server und Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


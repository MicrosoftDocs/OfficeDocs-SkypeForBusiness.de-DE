---
title: Ändern der Standardsprache für Ansagen und E-Mails
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie Microsoft Teams und Skype for Business einrichten, um eine andere Sprache für die standardmäßige Voicemail-Begrüßung Ihrer Organisation zu verwenden.
ms.openlocfilehash: 30e122c0d41c93326cdfa39de4c0ceb3a6d55cd2
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241124"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>Ändern der Standardsprache für Ansagen und E-Mails

Cloud-Voicemail verwendet verschiedene Spracheinstellungen zum Wiedergeben von Begrüßungen, zum Generieren von Transkriptionsübersetzungen und zum Generieren von Voicemailnachrichten. Die Spracheinstellungen können standardmäßig auf Mandantenebene, nach Richtlinie oder einzeln für einen bestimmten Benutzer angegeben werden.

## <a name="greetings"></a>Grüße
Begrüßungen werden an den Anrufer wiedergegeben, der voicemail verlässt, und können die folgenden Typen sein:

- Systemgrüße
- Benutzerdefinierte Begrüßungen, die vom aufgerufenen Benutzer aufgezeichnet werden
- Benutzerdefinierte Text-zu-Sprache-Begrüßung, die für den aufgerufenen Benutzer angegeben ist

Die zum Wiedergeben der Systemansagen verwendete Sprache ist in der Reihenfolge der Priorität entweder die primäre und sekundäre Eingabeaufforderungssprache, die in der Dem Benutzer zugewiesenen Online-Voicemailrichtlinie, der für den Benutzer angegebenen bevorzugten Sprache oder der Standardsprache des Mandanten angegeben ist.

Die benutzerdefinierte und abwesenheitsspezifische Begrüßung wird vom Benutzer in der vom Benutzer ausgewählten Sprache aufgezeichnet.

Wenn benutzerdefinierte Text-zu-Sprache-Begrüßungen für den Benutzer entweder vom Benutzer oder vom Mandantenadministrator angegeben werden, wird zum Generieren der Sprache die "PromptLanguage" verwendet, die zusammen mit den Text-zu-Sprache-Begrüßungen angegeben wird.

Die benutzerdefinierten Text-zu-Sprache-Begrüßungen werden nur verwendet, wenn keine benutzerdefinierten Begrüßungen für den Benutzer aufgezeichnet werden.

## <a name="transcription"></a>Transkription
Wenn dies durch die Online-Voicemailrichtlinie für den aufgerufenen Benutzer aktiviert ist, versucht Cloud-Voicemail, die vom Anrufer hinterlassene Voicemail zu transkribieren. Sie verwendet die Spracherkennung, um die im Audioinhalt verwendete Sprache zu verstehen und, wenn möglich, den Inhalt mithilfe der erkannten Sprache zu transkribieren.It will use speech detection to understand the language used in the audio content, if possible, transcribe the content using the detected language.

## <a name="transcription-translation"></a>Transkriptionsübersetzung
Wenn dies durch die Online-Voicemailrichtlinie für den aufgerufenen Benutzer aktiviert ist, übersetzt Cloud-Voicemail die transkribierte Voicemail. Es wird von der sprache, die während der Spracherkennung erkannt wird, in prioritätsreihenfolge entweder die bevorzugte Sprache für den Benutzer angegeben oder die Standardmandantensprache übersetzt.

## <a name="voicemail-message-template"></a>Voicemail-Nachrichtenvorlage
Cloud-Voicemail generiert die Voicemailnachricht mithilfe einer Sprachvorlage, die auf der für den Benutzer angegebenen bevorzugten Sprache oder der Standardsprache des Mandanten in der Reihenfolge der Priorität basiert.

## <a name="setting-the-preferred-language-for-a-user"></a>Festlegen der bevorzugten Sprache für einen Benutzer
Sie können die bevorzugte Sprache für einen Benutzer mithilfe von PowerShell entweder in Azure Active Directory oder in der lokales Active Directory festlegen. Weitere Informationen finden Sie unter [Festlegen von Sprach- und Regionseinstellungen für Microsoft 365 oder Office 365](/office365/troubleshoot/access-management/set-language-and-region).

Benutzer können ihre eigene bevorzugte Sprache über ihre Einstellungen ändern, nachdem sie sich angemeldet haben. Weitere Informationen finden Sie [unter Ändern der Anzeigesprache und Zeitzone in Microsoft 365 Business](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>Ändern der Systemsprache für alle Benutzer in der Organisation

1. Melden Sie sich mit Ihrem [globalen Administratorkonto](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) unter an [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).

2. Wählen Sie im Microsoft 365 Admin Center **"Einstellungen** > **Organisationseinstellungen****Organisationsprofil**"  >  aus.

3. Wählen Sie **"Organisationsinformationen" aus**.

4. Wählen Sie in der Liste **Bevorzugte Sprache** eine Sprache für alle in der Organisation aus.

5. Klicken Sie auf **Speichern**.

**Die Ihnen zur Verfügung stehenden Sprachen hängen vom Standort Ihrer Organisation ab**. Wenn sich Ihre Organisation beispielsweise in den USA befindet, können Sie die Standardsprache auf Englisch oder Spanisch festlegen. Wenn sich Ihre Organisation in Kanada befindet, können Sie zwischen Englisch und Französisch wählen.

## <a name="supported-languages-in-cloud-voicemail"></a>Unterstützte Sprachen in Cloud-Voicemail
Eine Liste der unterstützten Sprachen in Cloud-Voicemail für Microsoft Teams und Skype for Business finden Sie [unter Cloud-Voicemail unterstützten Sprachen](languages-for-voicemail-greetings-and-messages.md).
  

## <a name="custom-greeting-recorded-by-a-user"></a>Benutzerdefinierte Begrüßung, die von einem Benutzer aufgezeichnet wurde
Benutzer können ihre eigene benutzerdefinierte und abwesenheitseigene benutzerdefinierte Begrüßung aufzeichnen. Sehen Sie sich [die Einstellungen des Teams-Desktopclients](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) an, und [überprüfen Sie Skype for Business Voicemail und Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>Benutzerdefinierte Text-zu-Sprache-Begrüßung, die für einen Benutzer angegeben ist
Der Mandantenadministrator kann die benutzerdefinierte Text-zu-Sprache-Begrüßungs- und Eingabeaufforderungssprache für einen Benutzer mithilfe der Registerkarte "Voicemail" auf der Seite "Benutzerdetails" im Teams Admin Center oder mithilfe des Cmdlets ["Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) " angeben.

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>Benutzerdefinierte Text-zu-Sprache-Begrüßung, die von einem Benutzer angegeben wird
Benutzer können ihre eigenen benutzerdefinierten Text-zu-Sprache-Begrüßungen und die für die Begrüßung verwendete Sprache angeben. Für Microsoft Teams – Benutzer können ihre Voicemail-Begrüßung über die [Einstellungen des Teams-Desktopclients](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) ändern. Für Skype for Business – [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) und wählen Sie unter **"Sprache eingabeaufforderung"** eine neue Sprache aus. 


## <a name="related-articles"></a>Verwandte Artikel

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

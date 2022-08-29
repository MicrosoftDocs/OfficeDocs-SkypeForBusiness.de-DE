---
title: Verwalten von Feedbackrichtlinien in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: heprecel
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie feedbackrichtlinien verwenden, um zu steuern, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können.
ms.openlocfilehash: 933c6971058c107ab881cb48bb0f2a9dbd74900d
ms.sourcegitcommit: 44fd07d8e6e5fcbe5051de2300e180f295eaaad3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2022
ms.locfileid: "67339799"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedbackrichtlinien in Microsoft Teams

Benutzer in Ihrer Organisation können Feedback zu Microsoft Teams senden, um uns mitzuteilen, wie wir direkt auf dem Teams-Desktop, auf Webclients und mobilen Geräten vorgehen. Wir verbessern kontinuierlich die Teams-Erfahrung und verwenden dieses Feedback, um Teams zu verbessern.

> [!NOTE]
> Feedbackrichtlinien sind in GCC-, GCC High- oder DOD-Bereitstellungen nicht verfügbar.

**Das **Feature "Feedback geben** "**

Benutzer können uns Kommentare und Vorschläge zu Teams senden, indem sie **uns helfen** > , Feedback in Teams-Desktop und -Web zu **geben**.


![Feedbackoption in Teams geben](media/manage-feedback-policies-in-teams-give-feedback.png)

Zugriff auf Feedback auf mobilen Geräten mithilfe der **Einstellungshilfe** > **& Feedback** > **senden Feedback senden**.

![Feedbackoption in Teams auf Mobilgeräten](media/feedback3.jpg)

 Daten, die über **"Feedback senden**" und **"Feedback senden**" gesendet werden, gelten als "Supportdaten" in Ihrem Microsoft 365- oder Office 365-Vertrag, einschließlich Informationen, die andernfalls als "Kundendaten" oder "Personenbezogene Daten" betrachtet würden.



**Umfragen**

Benutzer können auch ihre Erfahrung mit Teams bewerten und uns Details zu der Bewertung senden, die sie geben. Diese Popup-Umfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt. Wenn ein Benutzer in der Benachrichtigung **"Feedback bereitstellen** " auswählt, wird die Umfrage für den Abschluss angezeigt.

![die Umfragebenachrichtigung und das Formular in Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können und ob sie die Umfrage erhalten. Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale Richtlinie (organisationsweite Standardrichtlinie) zugewiesen, und das Feedbackfeature und die Umfrage werden in der Richtlinie aktiviert. Die Ausnahme ist Teams für Education, bei dem die Features für Lehrer aktiviert und für Schüler/Studenten deaktiviert sind.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis Änderungen wirksam werden.

Angenommen, Sie möchten es allen Benutzern in Ihrer Organisation ermöglichen, Feedback zu senden und Umfragen mit Ausnahme von Neueinstellungen in Schulungen zu erhalten. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und neuen Mitarbeitern zuzuweisen. Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.  

Sie verwalten Feedbackrichtlinien mithilfe von PowerShell. Verwenden Sie das [Cmdlet **New-CsTeamsFeedbackPolicy**](/powershell/module/skype/new-csteamsfeedbackpolicy), um eine benutzerdefinierte Richtlinie zu erstellen. Verwenden Sie das Cmdlet **Grant-CsTeamsFeedbackPolicy** , um es einem oder mehreren Benutzern oder Benutzergruppen, z. B. einer Sicherheitsgruppe oder Verteilergruppe, zuzuweisen. Verwenden Sie **Set-CsTeamsFeedbackPolicy** , um bestimmte Flags festzulegen.

Um die Features zu deaktivieren und zu aktivieren, legen Sie die folgenden Parameter fest:

 - **Feedback geben**: Legen Sie den Parameter **"userInitiatedMode** " so fest, dass er **aktiviert** ist, damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Wenn Sie den Parameter auf **"Deaktiviert** " festlegen, wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.

 - **Umfragen**: Legen Sie den Parameter **"receiveSurveysMode** " **so fest** , dass er aktiviert ist, damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können. Damit Benutzer die Umfrage erhalten und sie abmelden können, legen Sie den Parameter auf **"enabledUserOverride**" fest. In Teams können Benutzer dann zu **"Datenschutzeinstellungen"** >  wechseln und auswählen, ob sie an Umfragen teilnehmen möchten. Wenn Sie den Parameter auf **"Deaktiviert** " festlegen, wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.

 - **Screenshots**: Verwenden Sie das **AllowScreenshotCollection-Flag** , um die Screenshotsammlung für Benutzer hinzuzufügen.
 - **Email**: Verwenden Sie das **AllowEmailCollection-Flag**, um ein E-Mail-Feld hinzuzufügen.
 - **Protokollsammlung**: Verwenden Sie das **AllowLogCollection-Flag** , um die Protokollsammlungsanmeldung für Benutzer hinzuzufügen. Die Protokollsammlung ist derzeit nur auf mobilgeräten aktiviert. Weitere Informationen dazu, welche Daten über Protokolle freigegeben werden, [finden Sie hier](https://go.microsoft.com/fwlink/?linkid=2168178).

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedbackrichtlinie

In diesem Beispiel erstellen wir eine Feedbackrichtlinie namens "Feedbackrichtlinie für neue Mitarbeiter", und wir deaktivieren die Möglichkeit, Feedback über **Feedback** und die Umfrage zu geben.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Zuweisen einer benutzerdefinierten Feedbackrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In diesem Beispiel weisen wir eine benutzerdefinierte Richtlinie namens "Feedbackrichtlinie für neu eingestellte Mitarbeiter" einem Benutzer namens "user1" zu.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)

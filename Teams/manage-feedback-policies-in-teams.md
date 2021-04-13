---
title: Verwalten von Feedbackrichtlinien in Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe von Feedbackrichtlinien steuern können, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656721"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedbackrichtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Benutzer in Ihrer Organisation können Feedback zu Teams an Microsoft senden und uns wissen lassen, wie es geht, direkt aus den Desktop- und Webclients von Teams. Wir verbessern ständig die Teams-Erfahrung, und wir verwenden dieses Feedback, um Teams zu verbessern.

> [!NOTE]
> Feedbackrichtlinien sind in GCC-, GCC-Hoch- oder DOD-Bereitstellungen nicht verfügbar.

**Das Feature "Feedback geben"**

Benutzer können kommentare und Vorschläge zu Teams an uns senden, indem sie **hilfe zum** Feedback in  >   Teams gehen. Daten,  die über Feedback senden gesendet werden, werden unter Ihrem Microsoft 365- oder Office 365-Vertrag als "Supportdaten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "Persönliche Daten" betrachtet würden.

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Umfragen**

Benutzer können ihre Erfahrungen mit Teams auch bewerten und uns Details zu ihrer Bewertung senden. Diese Popupumfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt. Wenn ein Benutzer **in** der Benachrichtigung Feedback bereitstellen auswählt, wird die Umfrage angezeigt, damit er die Umfrage abschließen kann.

![die Umfragebenachrichtigung und das Formular in Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation  Feedback zu Teams an Microsoft senden können, wenn sie Feedback geben und ob sie die Umfrage erhalten. Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale Richtlinie (organisationsweite Standardrichtlinie) zugewiesen, und das Feature "Feedback geben" und die Umfrage werden in der Richtlinie aktiviert.  Die Ausnahme ist Teams for Education, in dem die Features für Lehrkräfte aktiviert und für Schüler/Studenten deaktiviert sind.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis änderungen wirksam werden.

Sie möchten beispielsweise allen Benutzern in Ihrer Organisation erlauben,  Feedback über Feedback zu senden und Umfragen zu erhalten, mit Ausnahme neuer Mitarbeiter in Schulungen. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und sie neuen Mitarbeitern zuzuordnen. Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.  

Sie verwalten Feedbackrichtlinien mithilfe von PowerShell. Verwenden Sie **das Cmdlet New-CsTeamsFeedbackPolicy,** das hier zu finden *ist, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* um eine benutzerdefinierte Richtlinie zu erstellen. Verwenden Sie **das Grant-CsTeamsFeedbackPolicy-Cmdlet,** um es einem oder mehreren Benutzern oder Benutzergruppen zuzuordnen, z. B. einer Sicherheitsgruppe oder Verteilergruppe. Verwenden **Sie Set-CsTeamsFeedbackPolicy, um** bestimmte Kennzeichnungen zu setzen.

Um die Features zu deaktivieren und zu aktivieren, legen Sie die folgenden Parameter fest:

 - **Feedback geben:** Legen Sie den Parameter  **userInitiatedMode** auf aktiviert, damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Wenn Sie den Parameter auf **deaktiviert festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.
 - **Umfragen:** Legen Sie den Parameter  **receiveSurveysMode** auf aktiviert, um Benutzern, denen die Richtlinie zugewiesen ist, den Empfang der Umfrage zu ermöglichen. Damit Benutzer die Umfrage erhalten und zulassen, dass sie sich abmelden können, legen Sie den Parameter auf **enabledUserOverride .** In Teams können Benutzer dann zu **Datenschutzeinstellungen** wechseln und auswählen, ob sie  >   an Umfragen teilnehmen möchten. Wenn Sie den Parameter **auf deaktiviert festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.
 - **E-Mail:** Verwenden Sie **das AllowEmailCollection-Flag,** um ein E-Mail-Feld hinzuzufügen.

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedbackrichtlinie

In diesem Beispiel erstellen wir eine Feedbackrichtlinie mit dem Namen Neue Einstellungsfeedbackrichtlinie, und wir deaktivieren die Möglichkeit, Feedback über Feedback und die Umfrage zu geben. 

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Zuweisen einer benutzerdefinierten Feedbackrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In diesem Beispiel weisen wir einem Benutzer mit dem Namen Benutzer1 eine benutzerdefinierte Richtlinie mit dem Namen Neue Einstellungsfeedbackrichtlinie zu.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)

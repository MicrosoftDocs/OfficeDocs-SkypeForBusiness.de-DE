---
title: Verwalten von Feedbackrichtlinien in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
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
description: Erfahren Sie, wie Sie mithilfe von Feedbackrichtlinien steuern können, ob Die Benutzer von Microsoft Teams in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804695"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedbackrichtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Die Benutzer in Ihrer Organisation können uns direkt in den Desktop- und Webclients von Teams Feedback zu Microsoft senden. Wir verbessern die Benutzererfahrung in Teams ständig und nutzen dieses Feedback, um Teams zu verbessern.

> [!NOTE]
> Feedbackrichtlinien sind in Bereitstellungen mit GCC, GCC High oder DOD nicht verfügbar.

**Das Feature "Feedback geben"**

Benutzer können uns Kommentare und Vorschläge zu Teams senden, indem sie in Teams  >  **hilfe zu Feedback** geben. Über "Feedback senden" gesendete Daten werden im Rahmen Ihres Microsoft 365- oder Office 365-Vertrags als "Supportdaten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "Persönliche Daten" betrachtet würden. 

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Umfragen**

Benutzer können ihre Erfahrungen mit Teams auch bewerten und uns Details zu der bewertung senden, die sie geben. Diese Popupumfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt. Wenn ein Benutzer in der Benachrichtigung auf **"Feedback** bereitstellen" klickt, wird die Umfrage angezeigt, damit er die Umfrage abschließen kann.

![Screenshot der Benachrichtigung und des Formulars für die Umfrage in Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation  Feedback zu Teams an Microsoft senden können, wenn sie Feedback geben und ob sie die Umfrage erhalten. Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale Richtlinie  (organisationsweite Standardrichtlinie) zugewiesen, und das Feature "Feedback geben" und die Umfrage werden in der Richtlinie aktiviert. Die Ausnahme ist Teams für Bildungseinrichtungen, in dem die Features für Lehrkräfte aktiviert und für Schüler/Studenten deaktiviert sind.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

So möchten Sie beispielsweise allen Benutzern in Ihrer Organisation  erlauben, Feedback über Feedback zu senden und Umfragen zu erhalten, mit Ausnahme neuer Mitarbeiter in schulungen. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und sie neuen Mitarbeiter zuzuordnen. Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.  

Sie verwalten Feedbackrichtlinien mithilfe von PowerShell. Verwenden Sie das Cmdlet **"New-CsTeamsFeedbackPolicy",** das hier zu finden ist, um eine benutzerdefinierte Richtlinie zu erstellen, und verwenden Sie das **Cmdlet Grant-CsTeamsFeedbackPolicy,** um sie einem oder mehreren Benutzern oder Benutzergruppen zuzuordnen, z. B. einer Sicherheitsgruppe oder Verteilergruppe. *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*

Legen Sie die folgenden Parameter fest, um die Features zu deaktivieren und zu aktivieren:

 - **Feedback geben:** Legen Sie den Parameter  **"userInitiatedMode"** so ein, dass er aktiviert ist, damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Wenn Sie den Parameter **auf "Deaktiviert"** festlegen, wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.
 - **Umfragen:** Legen Sie den Parameter  **"receiveSurveysMode"** so ein, dass benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können. Damit benutzer die Umfrage erhalten und zulassen, dass sie die Umfrage abmelden, legen Sie den Parameter auf **"enabledUserOverride" festgelegt.** In Teams können Benutzer dann zu "Datenschutzeinstellungen" wechseln und auswählen, ob sie  >   an Umfragen teilnehmen möchten. Wenn Sie den deaktivierten Parameter **festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedbackrichtlinie

In diesem Beispiel erstellen wir eine Feedbackrichtlinie namens "Feedbackrichtlinie für neue Mitarbeiter" und deaktivieren die Möglichkeit, Feedback über Feedback und **die** Umfrage zu geben.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Zuweisen einer benutzerdefinierten Feedbackrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In diesem Beispiel weisen wir einem Benutzer mit dem Namen "benutzer1" eine benutzerdefinierte Richtlinie mit dem Namen "Feedbackrichtlinie für neue Mitarbeiter" zu.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)
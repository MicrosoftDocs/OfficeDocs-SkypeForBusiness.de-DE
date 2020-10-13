---
title: Verwalten von Feedback Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Erfahren Sie, wie Sie mithilfe von Feedback Richtlinien steuern können, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433038"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedback Richtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Benutzer in Ihrer Organisation können Feedback zu Teams an Microsoft senden lassen Sie uns wissen, wie wir vorgehen, und zwar direkt von den Desktop-und Webclients der Teams aus. Wir arbeiten ständig an der Verbesserung der Teams, und wir nutzen dieses Feedback, um Teams besser zu machen.

> [!NOTE]
> Feedback Richtlinien sind in gcc-, gcc-Hochspannungs-oder DoD-Bereitstellungen nicht verfügbar.

**Das Feature "Feedback senden"**

Benutzer können Kommentare und Vorschläge zu Teams an uns **senden, indem Sie**  >  **Feedback** in Teams geben. Daten, die durch **Feedback** gesendet werden, gelten als "Support Daten" unter Ihrem Microsoft 365-oder Office 365-Vertrag, einschließlich Informationen, die andernfalls als "Kundendaten" oder "persönliche Daten" gelten.

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Umfragen**

Benutzer können auch Ihre Erfahrungen mit Teams bewerten und uns Informationen über die von Ihnen gegebene Bewertung senden. Diese Popup Umfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt. Wenn ein Benutzer in der Benachrichtigung auf **Feedback bereitstellen** klickt, wird die Umfrage angezeigt, damit Sie abgeschlossen werden kann.

![Screenshot der Umfrage Benachrichtigung und des Formulars in Microsoft Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können, indem Sie **Feedback geben und angeben** , ob Sie die Umfrage erhalten. Standardmäßig werden allen Benutzern in Ihrer Organisation automatisch die globale (org-Wide Standard)-Richtlinie zugewiesen, und das Feature " **Feedback senden** " und die Umfrage sind in der Richtlinie aktiviert. Die Ausnahme bilden Teams für Bildungseinrichtungen, in denen die Features für Lehrer und Behinderte für Schüler aktiviert sind.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

Angenommen, Sie möchten allen Benutzern in Ihrer Organisation das Senden **von Feedback über Feedback und empfangen** von Umfragen mit Ausnahme von neuen Mitarbeitern in der Schulung gestatten. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und neuen Mitarbeitern zuzuweisen. Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.  

Sie können Feedback Richtlinien mithilfe von PowerShell verwalten. Verwenden Sie das Cmdlet **New-CsTeamsFeedbackPolicy** , *das [hier gefunden](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)werden kann*, um eine benutzerdefinierte Richtlinie und das **Grant-CsTeamsFeedbackPolicy-** Cmdlet zu erstellen, um es einem oder mehreren Benutzern oder Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, zuzuweisen.

Um die Features zu deaktivieren und zu aktivieren, setzen Sie die folgenden Parameter:

 - **Feedback geben**: Legen Sie den **userInitiatedMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.
 - **Umfragen**: setzen Sie den **receiveSurveysMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können. Damit Benutzer die Umfrage erhalten und Sie Sie deaktivieren können, setzen Sie den Parameter auf **enabledUserOverride**. In Teams können Benutzer dann zu **Einstellungen**  >  **Datenschutz** wechseln und auswählen, ob Sie an Umfragen teilnehmen möchten. Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedback Richtlinie

In diesem Beispiel erstellen wir eine Feedback-Richtlinie namens "New Hire Feedback Policy" und deaktivieren die Möglichkeit, **Feedback durch Feedback** und die Umfrage zu geben.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Zuweisen einer benutzerdefinierten Feedback Richtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In diesem Beispiel weisen wir einem Benutzer mit dem Namen Benutzer1 eine benutzerdefinierte Richtlinie mit dem Namen "New Hire Feedback Policy" zu.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
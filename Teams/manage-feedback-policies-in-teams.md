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
description: Hier erfahren Sie, wie Sie mithilfe von Feedbackrichtlinien steuern können, Teams Benutzer in Ihrer Organisation Feedback zu ihrem Produkt Teams Microsoft übermitteln können.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656721"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedbackrichtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Benutzer in Ihrer Organisation können feedback zu Teams an Microsoft senden und uns wissen lassen, wie wir dabei sind, direkt aus dem Teams-Desktop- und Webclients. Wir verbessern ständig die Benutzererfahrung Teams und nutzen dieses Feedback, um Teams verbessern.

> [!NOTE]
> Feedbackrichtlinien sind in Bereitstellungen mit hohen GCC, GCC hohen oder doD-Bereitstellungen nicht verfügbar.

**Das Feature "Feedback geben"**

Benutzer können uns Kommentare und Vorschläge Teams senden, indem sie in der Hilfe zu Feedback  >  **geben** in Teams. Über "Feedback senden" gesendete Daten werden im Rahmen Ihrer Microsoft 365- oder Office 365-Vereinbarung als "Supportdaten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "persönliche Daten" angesehen würden. 

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Umfragen**

Benutzer können ihre Erfahrung mit der Bewertung Teams uns Details zu der von ihnen bewerteten Bewertung senden. Diese Popupumfrage wird Benutzern von Zeit zu Zeit im Internet Teams. Wenn ein Benutzer in der Benachrichtigung **Feedback** geben auswählt, wird die Umfrage für den Abschluss der Umfrage angezeigt.

![Benachrichtigung und Formular der Umfrage in Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback  zu Teams an Microsoft senden können, und ob sie die Umfrage erhalten. Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale Richtlinie (Organisationsweite Standardrichtlinie) zugewiesen, und das Feature "Feedback geben" und die Umfrage sind in der Richtlinie aktiviert.  Eine Ausnahme bildet Teams Education, in dem die Features für Lehrkräfte und für Schüler/Studenten aktiviert und deaktiviert sind.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

Sie möchten beispielsweise zulassen, dass alle Benutzer in Ihrer  Organisation Feedback über Feedback geben und Umfragen erhalten, mit Ausnahme neuer Mitarbeiter in Schulungen. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und sie neuen Mitarbeitern zuzuordnen. Für alle anderen Benutzer in Ihrer Organisation wird die globale Richtlinie mit aktivierten Features aktiviert.  

Sie verwalten Feedbackrichtlinien mithilfe von PowerShell. Verwenden Sie **das Cmdlet New-CsTeamsFeedbackPolicy,** das Sie hier *finden, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* um eine benutzerdefinierte Richtlinie zu erstellen. Verwenden Sie **das Grant-CsTeamsFeedbackPolicy-Cmdlet,** um es einem oder mehreren Benutzern oder Benutzergruppen, z. B. einer Sicherheitsgruppe oder Verteilergruppe, zuzuordnen. Verwenden **Sie Set-CsTeamsFeedbackPolicy** zum Festlegen bestimmter Kennzeichnungen.

Legen Sie die folgenden Parameter fest, um die Features zu deaktivieren und zu aktivieren:

 - **Feedback geben:** Legen Sie den Parameter  **userInitiatedMode** auf aktiviert, damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Wenn Sie den Parameter **auf Disabled festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.
 - **Umfragen:** Legen Sie den Parameter  **receiveSurveysMode** auf aktiviert, damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können. Damit Benutzer die Umfrage erhalten und zulassen, dass sie sich abmelden, legen Sie den Parameter auf **enabledUserOverride .** In Teams können Benutzer dann zu Einstellungen Datenschutz wechseln und auswählen, ob sie an  >   Umfragen teilnehmen möchten. Wenn Sie den Parameter **auf Disabled festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten keine Umfrage.
 - **E-Mail:** Verwenden Sie die **AllowEmailCollection-Kennzeichnung,** um ein E-Mail-Feld hinzuzufügen.

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedbackrichtlinie

In diesem Beispiel erstellen wir eine Feedbackrichtlinie mit dem Namen Feedbackrichtlinie für neue Mitarbeiter und deaktivieren die Möglichkeit, Feedback über Feedback geben **und** die Umfrage zu geben.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Zuweisen einer benutzerdefinierten Feedbackrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In diesem Beispiel weisen wir einem Benutzer mit dem Namen "Benutzer1" eine benutzerdefinierte Richtlinie mit dem Namen "Feedbackrichtlinie für neue Mitarbeiter" zu.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)

---
title: Verwalten von Feedbackrichtlinien in Microsoft Teams
author: serdarsoysal
ms.author: serdars
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
description: Hier erfahren Sie, wie Sie mithilfe von Feedbackrichtlinien steuern können, Teams Benutzer in Ihrer Organisation Feedback zu diesem Thema Teams Microsoft übermitteln können.
ms.openlocfilehash: 582c5e39fca8dc37cefe8b480b2ff886779f6fa0
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2021
ms.locfileid: "59942100"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedbackrichtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Benutzer in Ihrer Organisation können Feedback zu Microsoft Teams senden, um uns wissen zu lassen, wie wir direkt in der Teams Desktop, Webclients und mobilen Geräten vor sich gehen. Wir verbessern ständig die Benutzererfahrung Teams und nutzen dieses Feedback, um Teams verbessern.

> [!NOTE]
> Feedbackrichtlinien sind in Bereitstellungen von GCC, GCC high oder DOD nicht verfügbar.

**Das **Feature "Feedback geben"****

Benutzer können uns Kommentare und Vorschläge zu Teams senden, indem sie in der Desktop- und Teams Hilfe Feedback   >   geben.


![Feedbackoption in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Greifen Sie mithilfe der Hilfe-Einstellungen auf Feedback  >  **&**  >  **mobilen Geräten zu.**

![Feedbackoption in mobilen Teams senden](media/feedback3.jpg)

 Über Feedback  senden  und Feedback senden werden unter Ihrer Microsoft 365- oder Office 365-Vereinbarung als "Supportdaten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "Persönliche Daten" betrachtet würden.


**Umfragen**

Benutzer können ihre Erfahrung mit ihren Bewertungen Teams uns Details zu der von ihnen bewerteten Bewertung senden. Diese Popupumfrage wird Benutzern von Zeit zu Zeit im Teams. Wenn ein Benutzer in der Benachrichtigung **Feedback** geben auswählt, wird die Umfrage für den Abschluss der Umfrage angezeigt.

![Benachrichtigung und Formular der Umfrage in Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können und ob sie die Umfrage erhalten. Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale Richtlinie (Organisationsweite Standardrichtlinie) zugewiesen, und das Feedbackfeature und die Umfrage werden in der Richtlinie aktiviert. Die Ausnahme ist Teams für Education, bei der die Features für Lehrkräfte und für Schüler/Studenten aktiviert und deaktiviert werden.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine benutzerdefinierte Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

So möchten Sie beispielsweise allen Benutzern in Ihrer Organisation erlauben, Feedback zu senden und Umfragen zu erhalten, mit Ausnahme neuer Mitarbeiter in Schulungen. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und sie neuen Mitarbeitern zuzuordnen. Für alle anderen Benutzer in Ihrer Organisation wird die globale Richtlinie mit aktivierten Features aktiviert.  

Sie verwalten Feedbackrichtlinien mithilfe von PowerShell. Verwenden Sie [ **das Cmdlet New-CsTeamsFeedbackPolicy**](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) zum Erstellen einer benutzerdefinierten Richtlinie. Verwenden Sie **das Grant-CsTeamsFeedbackPolicy-Cmdlet,** um es einem oder mehreren Benutzern oder Benutzergruppen, z. B. einer Sicherheitsgruppe oder Verteilergruppe, zuzuordnen. Verwenden **Sie Set-CsTeamsFeedbackPolicy,** um bestimmte Kennzeichen festlegen.

Legen Sie die folgenden Parameter fest, um die Features zu deaktivieren und zu aktivieren:

 - **Feedback geben:** Legen Sie den Parameter  **userInitiatedMode** auf aktiviert, damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Wenn Sie den Parameter **auf Disabled festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.
 - **Umfragen:** Legen Sie den Parameter  **receiveSurveysMode** auf aktiviert, damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können. Damit Benutzer die Umfrage erhalten und zulassen, dass sie sich abmelden, legen Sie den Parameter auf **enabledUserOverride .** In Teams können benutzer dann zu Einstellungen Datenschutz wechseln und auswählen, ob sie an Umfragen  >   teilnehmen möchten. Wenn Sie den Parameter **auf Disabled festlegen,** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten keine Umfrage.
 - **E-Mail:** Verwenden Sie die **AllowEmailCollection-Kennzeichnung,** um ein E-Mail-Feld hinzuzufügen.
 - **Protokollsammlung:** Verwenden Sie das **Kennzeichen AllowLogCollection,** um Benutzer eine Protokollsammlungs-Opt-In hinzuzufügen. Die Protokollsammlung ist derzeit nur auf mobilen Geräten aktiviert. Weitere Informationen zu den über Protokolle freigegebenen Daten finden [Sie unter](https://go.microsoft.com/fwlink/?linkid=2168178).

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

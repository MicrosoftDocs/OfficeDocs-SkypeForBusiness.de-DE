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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe von Feedback Richtlinien steuern können, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: e43cc46e16a17ad4f059398e99736d14fdee62ee
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570633"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedback Richtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Benutzer in Ihrer Organisation können Feedback zu Teams an Microsoft senden lassen Sie uns wissen, wie wir vorgehen, und zwar direkt von den Desktop-und Webclients der Teams aus. Wir arbeiten ständig an der Verbesserung der Teams, und wir nutzen dieses Feedback, um Teams besser zu machen.

**Das Feature "Feedback senden"**

Benutzer können Kommentare und Vorschläge zu Teams an uns **senden, indem Sie** > **Feedback** in Teams geben. Daten, die durch **Feedback** gesendet werden, werden unter Ihrer Office 365-Vereinbarung als "Support Daten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "personenbezogene Daten" gelten.

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Umfragen**

Benutzer können auch Ihre Erfahrungen mit Teams bewerten und uns Informationen über die von Ihnen gegebene Bewertung senden. Diese Popup Umfrage wird Benutzern von Zeit zu Zeit in Teams angezeigt. Wenn ein Benutzer in der Benachrichtigung auf **Feedback bereitstellen** klickt, wird die Umfrage angezeigt, damit Sie abgeschlossen werden kann.

![Screenshot der Umfrage Benachrichtigung und des Formulars in Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können, indem Sie **Feedback geben und angeben** , ob Sie die Umfrage erhalten. Standardmäßig werden allen Benutzern in Ihrer Organisation automatisch die globale (org-Wide Standard)-Richtlinie zugewiesen, und das Feature " **Feedback senden** " und die Umfrage sind in der Richtlinie aktiviert. Die Ausnahme bilden Teams für Bildungseinrichtungen, in denen die Features für Lehrer und Behinderte für Schüler aktiviert sind.

Sie können die globale Richtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer. Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer. Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

Angenommen, Sie möchten allen Benutzern in Ihrer Organisation das Senden **von Feedback über Feedback und empfangen** von Umfragen mit Ausnahme von neuen Mitarbeitern in der Schulung gestatten. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um beide Features zu deaktivieren und neuen Mitarbeitern zuzuweisen. Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktivierten Features.  

Sie verwenden das Cmdlet **New-CsTeamsFeedbackPolicy** , *das [hier gefunden](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)werden kann*, um eine benutzerdefinierte Richtlinie zu erstellen, und das Cmdlet **Grant-CsTeamsFeedbackPolicy** , um es einem oder mehreren Benutzern oder Gruppen von Benutzern zuzuweisen, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe.

Um die Features zu deaktivieren und zu aktivieren, setzen Sie die folgenden Parameter:

 - **Feedback geben**: Legen Sie den **userInitiatedMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.
 - **Umfragen**: setzen Sie den **receiveSurveysMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, die Umfrage empfangen können. Damit Benutzer die Umfrage erhalten und Sie Sie deaktivieren können, setzen Sie den Parameter auf **enabledUserOverride**. In Teams können Benutzer dann zu **Einstellungen** > **Datenschutz** wechseln und auswählen, ob Sie an Umfragen teilnehmen möchten. Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, erhalten die Umfrage nicht.

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedback Richtlinie

In diesem Beispiel erstellen wir eine Feedback-Richtlinie namens "New Hire Feedback Policy" und deaktivieren die Möglichkeit, **Feedback durch Feedback** und die Umfrage zu geben.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>Zuweisen einer benutzerdefinierten Feedback Richtlinie

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Feedback Richtlinie zu einem Benutzer

In diesem Beispiel weisen wir einem Benutzer mit dem Namen Benutzer1 eine benutzerdefinierte Richtlinie mit dem Namen "New Hire Feedback Policy" zu.

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Feedback Richtlinie zu Benutzern in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Feedback Richtlinie zuweisen. So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.

In diesem Beispiel weisen wir allen Benutzern in der Gruppe Contoso New hires eine benutzerdefinierte Feedback Richtlinie mit dem Namen "New Hire Feedback Policy" zu.  

Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
Rufen Sie die Mitglieder der angegebenen Gruppe ab.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie allen Benutzern in der Gruppe eine bestimmte Feedback Richtlinie zu. In diesem Beispiel handelt es sich um eine neue Richtlinie für Einstellungs Feedback.
```
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
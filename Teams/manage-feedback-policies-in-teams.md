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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe von Feedback Richtlinien steuern können, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540953"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Verwalten von Feedback Richtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Benutzer können Kommentare und Vorschläge zu Microsoft Teams an Microsoft senden, indem **** > Sie Feedback zu den Teams-Clients**geben** . Wir arbeiten ständig an der Verbesserung der Teams, und wir nutzen dieses Feedback, um Teams besser zu machen.

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Daten, die durch **Feedback** gesendet werden, werden unter Ihrer Office 365-Vereinbarung als "Support Daten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "personenbezogene Daten" gelten.

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können

Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können. Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale (org-Wide Standard)-Richtlinie zugewiesen, und das Feature ist in der Richtlinie aktiviert. Die Ausnahme bilden Teams für Bildungseinrichtungen, in denen das Feature für Lehrer und Behinderte für Schüler aktiviert ist.

Sie können die globale Richtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer. Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer. Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

Angenommen, Sie möchten allen Benutzern in Ihrer Organisation das Senden von Feedback mit Ausnahme der neuen Mitarbeiter in der Schulung gestatten. In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um die Funktion zu deaktivieren und neuen Mitarbeitern zuzuweisen. Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktiviertem Feature.  

Sie verwenden das Cmdlet **New-CsTeamsFeedbackPolicy** zum Erstellen einer benutzerdefinierten Richtlinie und des Cmdlets **Grant-CsTeamsFeedbackPolicy** , um es einem oder mehreren Benutzern oder Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, zuzuweisen. 

Legen Sie den **userInitiatedMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können. Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.

## <a name="create-a-custom-feedback-policy"></a>Erstellen einer benutzerdefinierten Feedback Richtlinie

In diesem Beispiel erstellen wir eine Feedback-Richtlinie namens "New Hire Feedback Policy" und deaktivieren die Möglichkeit, Feedback zu geben.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
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
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
---
title: Verwalten von Teamrichtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: Hier erfahren Sie, wie Sie Teamrichtlinien in Ihrer Organisation verwenden und verwalten, um zu steuern, welche Aktionen Benutzer in Teams und Kanälen durchführen können.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 40647aec4f55d3d922f29c853ec84ee175dc8166
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483202"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Verwalten von Teamrichtlinien in Microsoft Teams

Als Administrator können Sie die Teamrichtlinien in Microsoft Teams verwenden, um zu steuern, welche Benutzer in Ihrer Organisation in Teams und Kanälen tun können. So können Sie beispielsweise festlegen, ob Benutzer private Teams in Suchergebnissen und in der Team Galerie entdecken dürfen und ob Benutzer private Kanäle erstellen dürfen.

Sie verwalten die Teamrichtlinien im Microsoft Teams Admin Center. Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und diesen Benutzern zuweisen. Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.

Sie können die globale Richtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer. Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer. Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

## <a name="create-a-custom-teams-policy"></a>Erstellen einer benutzerdefinierten Teams-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams** > Teams-**Richtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

    ![Screenshot der Richtlinieneinstellungen für Teams](media/teams-policies.png)
4. Wählen Sie die gewünschten Einstellungen aus:

- [**Entdecken Sie private Teams**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): Aktivieren Sie diese Einstellung, damit Benutzer private Teams in Suchergebnissen und im Team Katalog entdecken können.
- [**Private Kanäle erstellen**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): Aktivieren Sie diese Einstellung, damit Benutzer private Kanäle erstellen können.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-teams-policy"></a>Bearbeiten einer Teams-Richtlinie

Sie können die globale Richtlinie oder alle von Ihnen erstellten benutzerdefinierten Richtlinien bearbeiten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams** > Teams-**Richtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken und dann auf **Bearbeiten**klicken.
3. Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Zuweisen einer benutzerdefinierten Teams-Richtlinie zu Benutzern

Mit dem Microsoft Teams Admin Center können Sie einem oder mehreren Benutzern oder dem Skype for Business PowerShell-Modul eine benutzerdefinierte Richtlinie zuweisen, um Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen.

### <a name="assign-a-custom-teams-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Teams-Richtlinie zu einem Benutzer

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Klicken Sie auf **Richtlinien**und dann neben **zugewiesene Richtlinien**auf **Bearbeiten**.
3. Wählen Sie unter **Teamrichtlinien**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.

Informationen zum Zuweisen einer benutzerdefinierten Teams-Richtlinie zu mehreren Benutzern gleichzeitig finden Sie unter [Bearbeiten von Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).

Oder Sie können auch die folgenden Aktionen ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams** > Teams-**Richtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten**aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Speichern**.

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Teams-Richtlinie zu Benutzern in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Teams-Richtlinie zuweisen. So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

In diesem Beispiel weisen wir allen Benutzern in der Contoso-Marketinggruppe eine Teams-Richtlinie namens "Marketingteams-Richtlinie" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
Rufen Sie die Mitglieder der angegebenen Gruppe ab.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie alle Benutzer in der Gruppe einer bestimmten Teams-Richtlinie zu. In diesem Beispiel handelt es sich um die Richtlinie für Marketing Teams.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der Erkennung privater Teams in Teams](manage-discovery-of-private-teams.md)

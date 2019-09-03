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
description: Informationen zur Verwendung und Verwaltung von Teamrichtlinien in Ihrer Organisation, damit Sie steuern können, wozu Benutzer in Teams und Kanälen berechtigt sind.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 6a562f9a271a9771796fd73424a94f2820c2f966
ms.sourcegitcommit: 25c30baec1c969eef95b725251a3f4ad3706a19d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "36622061"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Verwalten von Teamrichtlinien in Microsoft Teams

Als Administrator, können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, wozu Benutzer in Ihrer Organisation in Teams und Kanälen berechtigt sind. Sie können z. B. festlegen, ob private Teams für Benutzer in den Suchergebnissen und im Teamkatalog sichtbar sind und ob Benutzer private Kanäle erstellen dürfen.

Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**. Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer. Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie. Nachdem Sie die globale Standardrichtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

## <a name="create-a-custom-teams-policy"></a>Erstellen einer benutzerdefinierten Teamrichtlinie.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.

    ![Screenshot der Einstellungen für Teamrichtlinien.](media/teams-policies.png)
4. Wählen Sie die gewünschten Einstellungen aus:

- [**Private Teams entdecken**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): Aktivieren Sie diese Einstellung, um Benutzern zu ermöglichen, private Teams in den Suchergebnissen und im Teamkatalog zu entdecken.
- [**Private Kanäle erstellen**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): Aktivieren Sie diese Einstellung, um Benutzern zu ermöglichen, private Kanäle zu erstellen.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-teams-policy"></a>Bearbeiten einer Teamrichtlinie

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf**Edit** klicken.
3. Aktivieren oder deaktivieren Sie die gewünschten Einstellungen und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer

Um einem oder mehreren Benutzern eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Microsoft Teams Admin Center verwenden. Um Benutzergruppen, z. B. einer Sicherheitsgruppe oder einer Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Skype for Business PowerShell-Modul verwenden.

### <a name="assign-a-custom-teams-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Teamrichtlinie an einen Benutzer

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Benutzer** und klicken Sie dann den gewünschten Benutzer an.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen Sie unter **Teamrichtlinien** diejenige Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.

Informationen dazu, wie Sie eine benutzerdefinierte Teamrichtlinie mehreren Benutzern gleichzeitig zuweisen können, finden Sie unter [Batchbearbeitung von Benutzereinstellungen eines Teams](edit-user-settings-in-bulk.md).

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten**.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer in einer Gruppe.

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Teamrichtlinie zuweisen. So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).

In diesem Beispiel wird eine als „Marketing-Teamrichtlinie“ bezeichnete Teamrichtlinie allen Benutzern in der Contoso-Marketinggruppe zugewiesen.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
Abrufen der Mitglieder der gewählten Gruppe.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Zuweisen aller Benutzer in der Gruppe zu einer bestimmten Teamrichtlinie. Bei diesem Beispiel handelt es sich um die „Marketing-Teamrichtlinie“.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der Sichtbarkeit privater Teams unter Teams](manage-discovery-of-private-teams.md)

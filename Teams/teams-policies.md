---
title: Verwalten von Kanalrichtlinien in Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Erfahren Sie, wie Sie Teamkanalrichtlinien in Ihrer Organisation verwenden und verwalten, um zu steuern, welche Benutzer in Teams und Kanälen arbeiten können.
ms.openlocfilehash: 727bb8b133d5119cd396c79561dde453281206f0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432267"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Verwalten von Kanalrichtlinien in Microsoft Teams

Als Administrator können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, wozu Benutzer in Ihrer Organisation in Teams und Kanälen berechtigt sind. So können Sie beispielsweise festlegen, ob Benutzer private Kanäle erstellen dürfen.

Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

## <a name="create-a-custom-teams-policy"></a>Erstellen einer benutzerdefinierten Teamrichtlinie.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.

    ![Screenshot der Richtlinieneinstellungen für Teams.](media/teams-policies.png)
4. Aktivieren oder deaktivieren Sie private <a name="createchannels"></a> Kanäle **erstellen**, je nachdem, ob Sie Benutzern das Erstellen privater Kanäle gestatten möchten.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-teams-policy"></a>Bearbeiten einer Teamrichtlinie

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Verwandte Themen

[Verwalten Teams verbundener Websites und Kanalwebsites](/SharePoint/teams-connected-sites)

[Private Kanäle in Teams](private-channels.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)

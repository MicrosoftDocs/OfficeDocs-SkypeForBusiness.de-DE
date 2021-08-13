---
title: Verwalten von Teamrichtlinien in Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
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
description: Informationen zur Verwendung und Verwaltung von Teamrichtlinien in Ihrer Organisation, damit Sie steuern können, wozu Benutzer in Teams und Kanälen berechtigt sind.
ms.openlocfilehash: 4c980f6881a1ec73131e35cae1f04bf33f844026dccb1c14045d8310e2c755a5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321107"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Verwalten von Teamrichtlinien in Microsoft Teams

Als Administrator können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, wozu Benutzer in Ihrer Organisation in Teams und Kanälen berechtigt sind. So können Sie beispielsweise festlegen, ob Benutzer private Kanäle erstellen dürfen.

Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

## <a name="create-a-custom-teams-policy"></a>Erstellen einer benutzerdefinierten Teamrichtlinie.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.

    ![Screenshot der Richtlinieneinstellungen für Teams](media/teams-policies.png)
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

[Private Kanäle in Teams](private-channels.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
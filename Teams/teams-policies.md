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
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711779"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Verwalten von Kanalrichtlinien in Microsoft Teams

Als Administrator können Sie Richtlinien in Microsoft Teams, um zu steuern, welche Benutzer in Ihrer Organisation in Teams und Kanälen arbeiten können. So können Sie beispielsweise festlegen, ob Benutzer private oder freigegebene Kanäle erstellen dürfen.

Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es 24 Stunden dauern, bis die Änderungen wirksam werden.

## <a name="channel-policies"></a>Kanalrichtlinien

Die folgenden Richtlinien sind für Teams-Kanäle verfügbar:

|Richtlinie|Beschreibung|
|:-----|:----------|
|**Erstellen privater Kanäle**|Wenn **eins** ist, können Teambesitzer und -mitglieder private Kanäle erstellen. (Teambesitzer können steuern, ob Mitglieder in jedem Team private Kanäle erstellen können.)|
|**Erstellen freigegebener Kanäle**|Wenn **dies** der Usa ist, können Teambesitzer freigegebene Kanäle erstellen. Teams apps, die für Ihre Organisation verfügbar sind, stehen auch in freigegebenen Kanälen zur Verfügung.|
|**Einladen externer Benutzer zu freigegebenen Kanälen**|Wenn **dies** zu sehen ist, können Besitzer und Mitglieder freigegebener Kanäle externe Teilnehmer aus Organisationen einladen, in denen eine organisationsübergreifende Vertrauensstellung konfiguriert wurde. Teams Richtlinien für Ihre Organisation gelten für diese Kanäle.|
|**Teilnehmen an externen freigegebenen Kanälen**|Bei **dieser** Konfiguration können Benutzer an freigegebenen Kanälen teilnehmen, die von anderen Organisationen erstellt wurden, für die eine organisationsübergreifende Vertrauensstellung konfiguriert wurde. Teams Richtlinien für die andere Organisation gelten für diese Kanäle.|

## <a name="create-a-custom-teams-policy"></a>Erstellen einer benutzerdefinierten Teamrichtlinie.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.

    ![Screenshot der Richtlinieneinstellungen für Teams.](media/teams-policies.png)
4. Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.

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

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)

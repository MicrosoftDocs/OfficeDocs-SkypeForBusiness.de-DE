---
title: Verwalten von Anrufroutingrichtlinien für Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Anrufroutingrichtlinien für das direkte Routing Microsoft Teams verwalten.
ms.openlocfilehash: 348eef9e33dba4f33868c94d72e21289b1a87690
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457395"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>Verwalten von Anrufroutingrichtlinien für Direct Routing

Wenn Sie Direct [Routing in Ihrer](direct-routing-landing-page.md) Organisation bereitgestellt haben, verwenden Sie Anrufroutingrichtlinien, um es Teams-Benutzern zu ermöglichen, Telefonanrufe über Ihre lokale Telefonieinfrastruktur an das Public Switched Telephone Network (PSTN) zu empfangen und zu nehmen.

Eine Anrufroutingrichtlinie (auch als Voice Routing Policy bezeichnet) ist ein Container für PSTN-Nutzungsdatensätze. Sie erstellen und verwalten Voice Routing-Richtlinien, indem Sie zu **VoiceVoice-Routingrichtlinien**  >  im Microsoft Teams Admin Center oder mithilfe von VoiceVoice Windows PowerShell.

Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.

Es ist wichtig zu wissen, dass benutzer mit der Zuweisung einer Sprachroutingrichtlinie nicht in der Lage sind, pstN-Anrufe in einem Teams. Außerdem müssen Sie den Benutzer für Direct-Routing aktivieren und andere Konfigurationsschritte ausführen. Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing](direct-routing-configure.md).

## <a name="create-a-custom-call-routing-policy"></a>Erstellen einer benutzerdefinierten Anrufroutingrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **VoiceVoice-Routingrichtlinien** > , und klicken Sie dann auf **Hinzufügen**.<br>

2. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.

3. Klicken **Sie unter PSTN-Nutzungsdatensätze** auf **PSTN-Nutzung** hinzufügen, und wählen Sie dann die Einträge aus, die Sie hinzufügen möchten. Wenn Sie einen neuen PSTN-Nutzungsdatensatz erstellen müssen, klicken Sie auf **Hinzufügen**.

4. Wenn Sie mehrere PSTN-Nutzungsdatensätze hinzugefügt haben, ordnen Sie diese in der von Ihnen verwendeten Reihenfolge an.
5. Wenn Sie fertig sind, klicken Sie auf **Übernehmen**.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-call-routing-policy"></a>Bearbeiten einer Anrufroutingrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **VoiceVoice-Routingrichtlinien** > .

2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.

3. Klicken **Sie auf PSTN-Nutzungsdatensätze** hinzufügen/entfernen, nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufroutingrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Konfigurieren des Anrufroutings für Direct Routing](direct-routing-voice-routing.md)

[Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
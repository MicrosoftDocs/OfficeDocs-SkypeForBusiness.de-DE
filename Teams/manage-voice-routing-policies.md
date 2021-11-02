---
title: Verwalten von Anrufroutingrichtlinien für Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark
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
description: Erfahren Sie, wie Sie Richtlinien für die Anrufrouting in einer Microsoft Teams.
ms.openlocfilehash: dec6f19dea1f2a44f1c550bf4ae6b9c4f4dedc77
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634934"
---
# <a name="manage-call-routing-policies-for-direct-routing"></a>Verwalten von Anrufroutingrichtlinien für Direct Routing

Wenn Sie Direct Routing [in](direct-routing-landing-page.md) Ihrer Organisation bereitgestellt haben, verwenden Sie Anrufroutingrichtlinien, um es Teams-Benutzern zu ermöglichen, Telefonanrufe über Ihre lokale Telefonieinfrastruktur an das Public Switched Telephone Network (PSTN) zu empfangen und zu nehmen.

Eine Anrufroutingrichtlinie (auch als Voice Routing Policy bezeichnet) ist ein Container für PSTN-Nutzungsdatensätze. Sie erstellen und verwalten Voice Routing-Richtlinien, indem Sie zu **Voice Voice** Routing policies im Microsoft Teams Admin Center oder mithilfe von  >   Windows PowerShell.

Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.

Es ist wichtig zu wissen, dass Benutzer durch das Zuweisen einer Sprachroutingrichtlinie nicht in der Lage sind, pstN-Anrufe in Teams. Darüber hinaus müssen Sie den Benutzer für das direkte Routing Telefonsystem und andere Konfigurationsschritte ausführen. Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md)

## <a name="create-a-custom-call-routing-policy"></a>Erstellen einer benutzerdefinierten Anrufroutingrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Voice Voice** Voice  >  **Routing Policies**, und klicken Sie dann auf **Hinzufügen**.<br>
    ![Screenshot der Seite "Voice Routing Policy hinzufügen" im Microsoft Teams Admin Center.](media/manage-voice-routing-policies.png) 
2. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
3. Klicken **Sie unter PSTN-Nutzungsdatensätze** auf **PSTN-Nutzung hinzufügen**, und wählen Sie dann die Einträge aus, die Sie hinzufügen möchten. Wenn Sie einen neuen PSTN-Nutzungsdatensatz erstellen müssen, klicken Sie auf **Hinzufügen**.
4. Wenn Sie mehrere PSTN-Nutzungsdatensätze hinzugefügt haben, ordnen Sie diese in der von Ihnen verwendeten Reihenfolge an.
5. Wenn Sie fertig sind, klicken Sie auf **Übernehmen**.
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-call-routing-policy"></a>Bearbeiten einer Anrufroutingrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Voice Voice** Voice  >  **Routing Policies**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Klicken **Sie auf PSTN-Nutzungsdatensätze hinzufügen/entfernen**, nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Speichern.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter Set-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufroutingrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Konfigurieren des Anrufroutings für Direct Routing](direct-routing-voice-routing.md)

[Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
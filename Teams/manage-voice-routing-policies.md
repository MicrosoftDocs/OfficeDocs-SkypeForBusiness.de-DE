---
title: Verwalten von VoIP-Routing Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie VoIP-Routing Richtlinien in Microsoft Teams erstellen und verwalten.
ms.openlocfilehash: 2bef422f22dc212b2c615e2ca2ab98806b396e9f
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217656"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Verwalten von VoIP-Routing Richtlinien in Microsoft Teams

Wenn Sie in Ihrer Organisation ein [Direktes Routing für das Telefon System](direct-routing-landing-page.md) bereitgestellt haben, können Sie mithilfe der VoIP-Routing Richtlinien Teams und Skype for Business Online-Benutzern das empfangen und tätigen von Telefon anrufen mit dem öffentlichen Telefonnetz (PSTN) über Ihre lokale Telefonie-Infrastruktur ermöglichen.

Eine VoIP-Routing Richtlinie ist ein Container für PSTN-Verwendungsdaten Sätze. Sie können VoIP-Routing Richtlinien erstellen und verwalten, **Voice**indem Sie  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Routing Richtlinien** wechseln.

Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.

Es ist wichtig zu wissen, dass es für das Zuweisen einer VoIP-Routing Richtlinie zu einem Benutzer nicht möglich ist, in Teams PSTN-Anrufe zu tätigen. Darüber hinaus müssen Sie den Benutzer für das direkte Routing des Telefonsystems aktivieren und andere Konfigurationsschritte ausführen. Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

## <a name="create-a-custom-voice-routing-policy"></a>Erstellen einer benutzerdefinierten VoIP-Routing Richtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**, und klicken Sie dann auf **Hinzufügen**.<br>
    ![Screenshot der Seite "VoIP-Routing Richtlinie hinzufügen" im Microsoft Teams Admin Center ](media/manage-voice-routing-policies.png) 
2. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
3. Klicken Sie unter **PSTN-Verwendungsdaten Sätze**auf **PSTN-Verwendung hinzufügen**, und wählen Sie dann die Datensätze aus, die Sie hinzufügen möchten. Wenn Sie einen neuen PSTN-Verwendungsdaten Satz erstellen müssen, klicken Sie auf **Hinzufügen**.
4. Wenn Sie mehrere PSTN-Verwendungsdaten Sätze hinzugefügt haben, ordnen Sie diese in der gewünschten Reihenfolge an.
5. Wenn Sie fertig sind, klicken Sie auf über **nehmen**.
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).

## <a name="edit-a-voice-routing-policy"></a>Bearbeiten einer VoIP-Routing Richtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Klicken Sie auf **PSTN-Verwendungsdaten Sätze hinzufügen/entfernen**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten VoIP-Routing Richtlinie für Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Konfigurieren des VoIP-Routings für das direkte Routing](direct-routing-voice-routing.md)

[Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)

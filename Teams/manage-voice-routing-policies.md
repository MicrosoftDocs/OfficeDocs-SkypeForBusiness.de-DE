---
title: Verwalten von Voice Routingrichtlinien in Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie Richtlinien für das Voicerouting in Microsoft Teams erstellen und verwalten.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802555"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>Verwalten von Voice Routingrichtlinien in Microsoft Teams

Wenn Sie direct Routing für Telefonsystem [in](direct-routing-landing-page.md) Ihrer Organisation bereitgestellt haben, verwenden Sie Sprachroutingrichtlinien, um Teams- und Skype for Business Online-Benutzern das Empfangen und Führen von Telefonanrufen beim öffentlichen Telefonnetz (PSTN) mithilfe Ihrer lokalen Telefonieinfrastruktur zu ermöglichen.

Eine Sprachroutingrichtlinie ist ein Container für PSTN-Nutzungsdatensätze. Sie erstellen und verwalten Voiceroutingrichtlinien, indem Sie zu den **Voice**  >  **Voice -Routingrichtlinien** im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell.

Sie können die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Die Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, sie aber nicht umbenennen oder löschen können.

Es ist wichtig zu wissen, dass das Zuweisen einer Sprachroutingrichtlinie zu einem Benutzer nicht es ihm ermöglicht, In-PstN-Anrufe in Teams zu erstellen. Außerdem müssen Sie den Benutzer für das direkte Routing des Telefonsystems aktivieren und andere Konfigurationsschritte ausführen. Weitere Informationen finden Sie unter ["Konfigurieren des direkten Routings".](direct-routing-configure.md)

## <a name="create-a-custom-voice-routing-policy"></a>Erstellen einer benutzerdefinierten Voiceroutingrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Voice** Routing Policies", und klicken Sie dann auf  >   **"Hinzufügen".**<br>
    ![Screenshot der Seite "Voice routing policy hinzufügen" im Microsoft Teams Admin Center ](media/manage-voice-routing-policies.png) 
2. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
3. Klicken **Sie unter "PSTN-Nutzungsdatensätze"** auf **"PSTN-Verwendung** hinzufügen", und wählen Sie dann die Datensätze aus, die Sie hinzufügen möchten. Wenn Sie einen neuen PstN-Nutzungsdatensatz erstellen müssen, klicken Sie auf **"Hinzufügen".**
4. Wenn Sie mehrere PstN-Nutzungsdatensätze hinzugefügt haben, ordnen Sie diese in der von Ihnen verwendeten Reihenfolge an.
5. Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**
6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter "New-CsOnlineVoiceRoutingPolicy".](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)

## <a name="edit-a-voice-routing-policy"></a>Bearbeiten einer Sprachroutingrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den **Voice**  >  **Voice-Routingrichtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Klicken **Sie auf "PSTN-Nutzungsdatensätze hinzufügen/entfernen",** nehmen Sie die änderungen vor, und klicken Sie dann auf **"Speichern".**

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Sprachroutingrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Konfigurieren des Sprachroutings für direktes Routing](direct-routing-voice-routing.md)

[Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

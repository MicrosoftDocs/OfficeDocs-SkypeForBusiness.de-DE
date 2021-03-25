---
title: Verwalten von Richtlinien für Notrufe in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Richtlinien für Notrufe in Microsoft Teams verwenden und verwalten, um zu definieren, was geschieht, wenn ein Teams-Benutzer in Ihrer Organisation einen Notruf ab nimmt.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120566"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für Notrufe in Microsoft Teams

Wenn Ihre [](set-up-calling-plans.md) Organisation Anrufpläne oder das bereitgestellte Direkte Telefonsystemrouting [verwendet,](direct-routing-landing-page.md)können Sie mithilfe von Richtlinien für Notrufe in Microsoft Teams definieren, was geschieht, wenn ein Teams-Benutzer in Ihrer Organisation einen Notruf ableitet. Sie können festlegen, wer benachrichtigt werden soll und wie er benachrichtigt wird, wenn ein Benutzer, dem die Richtlinie zugewiesen ist, Notdienste anruft. Beispielsweise können Sie Richtlinieneinstellungen so konfigurieren, dass sie den Sicherheitsschalter Ihrer Organisation automatisch benachrichtigen und sie in Notrufen anhören lassen.  

Sie verwalten Richtlinien für Notrufe, indem Sie im Microsoft Teams Admin Center zu den Richtlinien für Sprachnotrufe oder  >   über Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten können, sie aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für Notrufe zugewiesen haben und sich dieser Benutzer auf dieser Netzwerkwebsite befindet, setzt die Der Netzwerkwebsite zugewiesene Richtlinie die dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="create-a-custom-emergency-calling-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Sprachnotrufrichtlinien, und klicken Sie dann auf die Registerkarte  >   **Anrufrichtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Legen Sie vor, wie Sie Personen in Ihrer Organisation, in der Regel den Sicherheitsschalter, benachrichtigen möchten, wenn ein Notruf erfolgt. Wählen Sie dazu unter **Benachrichtigungsmodus** eine der folgenden Optionen aus:
    - **Nur Benachrichtigung senden:** Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet.
    - **Konferenz in stummgeschaltet** und kann die Stummschaltung nicht wieder aufhören: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet und kann an der Unterhaltung zwischen dem Anrufer und dem PSAP-Operator lauschen (aber nicht teilnehmen).
    - **In** stummgeschalteter Konferenz, aber in der Lage, die Stummschaltung aufzuhören: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet, und sie können die Stummschaltung aufhören und an der Unterhaltung zwischen dem Anrufer und dem PSAP-Operator teilnehmen.
5.  Wenn Sie eine der Konferenz **in** stummgeschalteten  Benachrichtigungsmodi ausgewählt haben, können Sie im Feld Telefonnummern für Notrufbenachrichtigungen eine PSTN-Telefonnummer eines Benutzers oder einer Gruppe eingeben, um an dem Notruf zu teilnehmen. Geben Sie z. B. die Nummer des Sicherheitsschalters Ihrer Organisation ein, der bei einem Notruf einen Anruf erhält und dann den Anruf anhören kann. Das PSTN-Telefon kann nicht stummgeschaltet werden, auch wenn der Modus in "Stummgeschaltet" auf Konferenz festgelegt ist, aber die Stummschaltung **wieder aufschalten kann.**
6. Suchen Und wählen Sie einen oder mehrere Benutzer oder Gruppen aus, z. B. den Security Desk Ihrer Organisation, um zu benachrichtigen, wenn ein Notruf erfolgt.  Die Benachrichtigung kann an E-Mail-Adressen von Benutzern, Verteilergruppen und Sicherheitsgruppen gesendet werden. Maximal 50 Benutzer können benachrichtigt werden.
7. Klicken Sie auf **Anwenden**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Bearbeiten einer Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Sprachnotrufrichtlinien, und klicken Sie dann auf die Registerkarte  >   **Anrufrichtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **Übernehmen.**

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für Notrufe zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für Notrufe zu einer Netzwerkwebsite

Verwenden Sie [das Cmdlet Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Richtlinie für Notrufe zuzuordnen.

Das folgende Beispiel zeigt, wie Sie der Website "Website1" eine Richtlinie namens Contoso Emergency Calling Policy 1 zuweisen.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Routingrichtlinien für Notrufe in Teams](manage-emergency-call-routing-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
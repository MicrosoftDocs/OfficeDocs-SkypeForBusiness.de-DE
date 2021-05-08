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
description: Erfahren Sie, wie Sie Richtlinien für Notrufe in Microsoft Teams verwenden und verwalten, um zu definieren, was passiert, wenn ein Teams-Benutzer in Ihrer Organisation einen Notruf ablaget.
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

Wenn Ihre [](set-up-calling-plans.md) Organisation Anrufpläne verwendet oder Telefonsystem [Direct Routing](direct-routing-landing-page.md)bereitgestellt hat, können Sie mithilfe von Richtlinien für Notrufe in Microsoft Teams definieren, was geschieht, wenn ein Teams-Benutzer in Ihrer Organisation einen Notruf ableitet. Sie können festlegen, wer benachrichtigt werden soll und wie er benachrichtigt wird, wenn ein Benutzer, dem die Richtlinie zugewiesen ist, Notdienste anruft. So können Sie beispielsweise Richtlinieneinstellungen so konfigurieren, dass sie das Sicherheitsdesk Ihrer Organisation automatisch benachrichtigen und sie Notrufe abhören lassen.  

Sie verwalten Richtlinien für Notrufe, indem Sie zu den Richtlinien für Notrufe im Microsoft Teams Admin Center oder mithilfe von  >   Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für Notrufe zugewiesen haben und sich der Benutzer an diesem Netzwerkstandort befindet, setzt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="create-a-custom-emergency-calling-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Sprachnotrufe , und klicken Sie dann auf die Registerkarte  >   **Anrufrichtlinien.**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Legen Sie die Art und Weise vor, wie Personen in Ihrer Organisation, in der Regel die Sicherheitsanrufe, benachrichtigt werden, wenn ein Notruf erfolgt. Wählen Sie dazu unter **Benachrichtigungsmodus** eine der folgenden Optionen aus:
    - **Nur Benachrichtigung senden:** Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet.
    - Konferenz in **stumm** geschaltet und die Stummschaltung nicht wieder möglich: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet und kann an der Unterhaltung zwischen dem Anrufer und dem PSAP-Operator lauschen (aber nicht teilnehmen).
    - Konferenz in **stumm** geschaltet, aber stummgeschaltet: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet und kann die Stummschaltung für die Audioanrufe und die Teilnahme an der Unterhaltung zwischen dem Anrufer und dem PSAP-Operator wieder aufschalten.
5.  Wenn Sie eine der Telefonkonferenzen **im** Benachrichtigungsmodus "Stummgeschaltet" ausgewählt haben, können Sie im Feld Für Notrufe zu wählende Nummern eine PSTN-Telefonnummer eines Benutzers oder einer Gruppe eingeben, der bzw. die angerufen und an dem Notruf teilnehmen soll.  Geben Sie z. B. die Nummer des Sicherheitsdiensts Ihrer Organisation ein, der bei einem Notruf einen Anruf erhält und den Anruf dann anhören kann. Die Stummschaltung des PSTN-Telefons kann nicht gelöst werden, auch wenn der Modus auf Konferenz in stummgeschaltet festgelegt ist, die Stummschaltung **aber wieder aufgeschaltet werden kann.**
6. Suchen Sie nach einem oder mehreren Benutzern oder Gruppen, z. B. dem Sicherheitsdienst Ihrer Organisation, und wählen Sie diese aus, um sich bei einem Notruf zu benachrichtigen.  Die Benachrichtigung kann an die E-Mail-Adressen von Benutzern, Verteilergruppen und Sicherheitsgruppen gesendet werden. Maximal 50 Benutzer können benachrichtigt werden.
7. Klicken Sie auf **Anwenden**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere [Informationen finden Sie unter New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Bearbeiten einer Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien für Sprachnotrufe , und klicken Sie dann auf die Registerkarte  >   **Anrufrichtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann **auf Übernehmen**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für Notrufe zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für Notrufe zu einem Netzwerkstandort

Verwenden Sie [das Cmdlet Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Richtlinie für Notrufe zuzuordnen.

Das folgende Beispiel zeigt, wie Sie der Website "Site1" eine Richtlinie namens "Contoso-Notrufrichtlinie 1" zuweisen.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für das Routing von Notrufen in Teams](manage-emergency-call-routing-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)
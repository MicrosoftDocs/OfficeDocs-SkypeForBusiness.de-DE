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
description: Erfahren Sie, wie Sie Richtlinien für Notrufe in Microsoft Teams verwenden und verwalten, um zu definieren, was geschieht, wenn ein Teambenutzer in Ihrer Organisation einen Notruf ab anruft.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973139"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für Notrufe in Microsoft Teams

Wenn Ihre [](set-up-calling-plans.md) Organisation Anrufpläne oder das bereitgestellte [Telefonsystem-Direct-Routing](direct-routing-landing-page.md)verwendet, können Sie mithilfe von Richtlinien für Notrufe in Microsoft Teams definieren, was geschieht, wenn ein Teambenutzer in Ihrer Organisation einen Notruf ableitet. Sie können festlegen, wer benachrichtigt werden soll und wie er benachrichtigt wird, wenn ein Benutzer, dem die Richtlinie zugewiesen ist, Notdienste anruft. Beispielsweise können Sie Richtlinieneinstellungen so konfigurieren, dass sie das Sicherheitsdesk Ihrer Organisation automatisch benachrichtigen und diese in Notrufen abhören lassen.  

Sie verwalten Richtlinien für Notrufe, indem Sie zu den **Richtlinien** für Notrufe im Microsoft Teams Admin Center oder mithilfe von  >   Windows PowerShell. Die Richtlinien können Benutzern und [Netzwerkwebsites zugewiesen werden.](cloud-voice-network-settings.md)

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Die Benutzer erhalten die globale Richtlinie automatisch, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, sie aber nicht umbenennen oder löschen können. Für Netzwerkwebsites erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie einer Netzwerkwebsite und einem Benutzer eine Richtlinie für Notrufe zugewiesen haben und sich der Benutzer an diesem Netzwerkstandort befindet, setzt die Richtlinie, die der Netzwerkwebsite zugewiesen ist, die dem Benutzer zugewiesene Richtlinie außer Kraft.

## <a name="create-a-custom-emergency-calling-policy"></a>Erstellen einer benutzerdefinierten Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Notfallrichtlinien für Sprachanrufe", und klicken Sie dann auf die Registerkarte  >   **"Anrufrichtlinien".**
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Legen Sie die Art und Weise für die Benachrichtigung von Personen in Ihrer Organisation (in der Regel dem Sicherheitsdienst) bei einem Notruf festgelegt. Wählen Sie dazu im **Benachrichtigungsmodus** eine der folgenden Optionen aus:
    - **Nur Benachrichtigung senden:** Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet.
    - Konferenz in **stummgeschalteter** und nicht stummgeschalteter Kommunikation: Eine Chatnachricht in Teams wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet und kann an der Unterhaltung zwischen dem Anrufer und dem Anbieter von PSAP lauschen (aber nicht teilnehmen).
    - Konferenz stumm geschaltet, aber Stummschaltung wieder **möglich:** Eine Chatnachricht in Teams wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet und kann die Stummschaltung für das Anhören und die Teilnahme an der Unterhaltung zwischen dem Anrufer und dem PSAP-Operator wieder aufklingen.
5.  Wenn Sie eine der Telefonkonferenzen **im** Modus  "Stummgeschaltete Benachrichtigungen" ausgewählt haben, können Sie im Feld "Nummern für Notrufbenachrichtigungen" eine Festnetztelefonnummer eines Benutzers oder einer Gruppe eingeben, um den Notruf an- und an dem Notruf teilnehmen zu können. Geben Sie z. B. die Nummer des Sicherheitsdiensts Ihrer Organisation ein, der bei einem Notruf einen Anruf erhält und dann den Anruf anhören kann. Das Festnetztelefon kann nicht stummgeschaltet werden, auch wenn der Modus in "Stummgeschaltet" auf "Konferenz" festgelegt ist, die Stummschaltung **aber wieder aufgeschaltet werden kann.**
6. Suchen Sie nach einem oder mehreren Benutzern oder Gruppen, z. B. dem Sicherheitsdesk Ihrer Organisation, und wählen Sie diese aus, um eine Benachrichtigung zu erhalten, wenn ein Notruf erfolgt.  Die Benachrichtigung kann an E-Mail-Adressen von Benutzern, Verteilergruppen und Sicherheitsgruppen gesendet werden. Es können maximal 50 Benutzer benachrichtigt werden.
7. Klicken Sie auf **Anwenden**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe ["New-CsTeamsEmergencyCallingPolicy".](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)

## <a name="edit-an-emergency-calling-policy"></a>Bearbeiten einer Richtlinie für Notrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu "Notfallrichtlinien für Sprachanrufe", und klicken Sie dann auf die Registerkarte  >   **"Anrufrichtlinien".**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die von Ihnen vorgenommenen Änderungen vor, und klicken Sie dann auf **"Übernehmen".**

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Richtlinie für Notrufe zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Richtlinie für Notrufe zu einem Netzwerkstandort

Verwenden Sie [das Cmdlet "Set-CsTenantNetworkSite",](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) um einer Netzwerkwebsite eine Richtlinie für Notrufe zuzuordnen.

Das folgende Beispiel zeigt, wie Sie der Website "Site1" eine Richtlinie namens "Contoso-Notrufrichtlinie 1" zuweisen.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für das Routing von Notrufen in Teams](manage-emergency-call-routing-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

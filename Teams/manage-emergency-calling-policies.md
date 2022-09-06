---
title: Verwalten von Notrufrichtlinien in Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Notrufrichtlinien in Microsoft Teams verwenden und verwalten, um zu definieren, was geschieht, wenn ein Teams-Benutzer in Ihrer Organisation einen Notruf abnimmt.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 658e7191a821069d3fa9b13e02cc7cbcdfb29413
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606554"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Verwalten von Notrufrichtlinien in Microsoft Teams

Wenn Ihre Organisation Microsoft-Anrufpläne, Telefonieanbieter, Telefonieanbieter mit Mobil (Öffentliche Vorschauversion) oder Direct Routing als [PSTN-Konnektivitätsoption](pstn-connectivity.md) verwendet, können Sie mithilfe von Richtlinien für Notrufe in Microsoft Teams definieren, was geschieht, wenn ein Teams-Benutzer in Ihrer Organisation einen Notruf abgibt.

Sie können festlegen, wer benachrichtigt werden soll und wie sie benachrichtigt werden, wenn ein Benutzer, dem die Richtlinie zugewiesen ist, Notrufe tätigt. Sie können z. B. Richtlinieneinstellungen so konfigurieren, dass der Sicherheitsdesk Ihrer Organisation automatisch benachrichtigt und in Notrufen abgehört wird.  

Sie verwalten Notrufrichtlinien, indem Sie zu **VoIP-Notfallrichtlinien** >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell wechseln. Die Richtlinien können Benutzern und [Netzwerkstandorten](cloud-voice-network-settings.md) zugewiesen werden.

Für Benutzer können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Denken Sie daran, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten können, sie jedoch nicht umbenennen oder löschen können. Für Netzwerkstandorte erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

Wenn Sie eine Richtlinie für Notrufe einem Netzwerkstandort und einem Benutzer zugewiesen haben und sich dieser Benutzer an diesem Netzwerkstandort befindet, überschreibt die Richtlinie, die dem Netzwerkstandort zugewiesen ist, die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-calling-policy"></a>Erstellen einer benutzerdefinierten Notrufrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **VoIP-Notfallrichtlinien** > , und klicken Sie dann auf die Registerkarte "**Anrufrichtlinien**".

2. Klicken Sie auf **Hinzufügen**.

3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.

4. Legen Sie den **Nachschlagemodus für externe Standorte** auf "Aktiviert" fest, damit Ihre Endbenutzer ihre Notfalladresse konfigurieren können, wenn sie von einem Netzwerkstandort aus außerhalb des Unternehmensnetzwerks arbeiten.

5. Legen Sie fest, wie Sie Personen in Ihrer Organisation, in der Regel den Sicherheitsdesk, benachrichtigen möchten, wenn ein Notruf getätigt wird. Wählen Sie dazu im **Benachrichtigungsmodus** eine der folgenden Optionen aus:

    - **Nur Benachrichtigung senden**: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet.
    - **Konferenz stummgeschaltet und kann die Stummschaltung nicht aufheben**: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet, und sie können die Unterhaltung zwischen dem Anrufer und dem PSAP-Operator anhören (aber nicht daran teilnehmen).
    - **Konferenz stummgeschaltet, kann aber die Stummschaltung aufheben**: Eine Teams-Chatnachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet, und sie können die Stummschaltung aufheben, um die Unterhaltung zwischen dem Anrufer und dem PSAP-Operator abzuhören und daran teilzunehmen.

6.  Legen Sie den **Haftungsausschluss für den Notfalldienst** so fest, dass ein Banner angezeigt wird, das Ihre Endbenutzer daran erinnert, ihren Notfallstandort zu bestätigen.

7.  Wenn Sie **einen der Konferenzen im Modus für stummgeschaltete** Benachrichtigungen ausgewählt haben, können Sie im Feld **"Nummern für Notrufbenachrichtigungen** " eine PSTN-Telefonnummer eines Benutzers oder einer Gruppe eingeben, um den Notruf anzurufen und am Notruf teilzunehmen. Geben Sie z. B. die Nummer des Sicherheitsdesks Ihrer Organisation ein, der einen Anruf erhält, wenn ein Notruf getätigt wird, und dann den Anruf abhören kann. Das PSTN-Telefon kann nicht stummgeschaltet werden, auch wenn der Modus auf " **Konferenzen" im Stummschaltmodus festgelegt ist, aber die Stummschaltung aufheben kann**.

8. Suchen Sie nach einem oder mehreren Benutzern oder Gruppen, z. B. dem Sicherheitsdesk Ihrer Organisation, und wählen Sie sie aus, um zu benachrichtigen, wenn ein Notruf getätigt wird.  Die Benachrichtigung kann an E-Mail-Adressen von Benutzern, Verteilergruppen und Sicherheitsgruppen gesendet werden. Maximal 50 Benutzer können benachrichtigt werden.

9. Klicken Sie auf **Anwenden**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Bearbeiten einer Notrufrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **VoIP-Notfallrichtlinien** > , und klicken Sie dann auf die Registerkarte "**Anrufrichtlinien**".
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **'Übernehmen'**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Siehe [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Notrufrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Siehe auch [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Notrufrichtlinie zu einem Netzwerkstandort

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Richtlinie oder alle benutzerdefinierten Richtlinien zuweisen, die Sie erstellen.

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu "**Netzwerktopologie** für **Standorte** > ", und klicken Sie auf die Registerkarte **"Netzwerkstandorte**".
2. Wählen Sie die Website aus, indem Sie links neben dem Namen klicken und dann auf **"Bearbeiten"** klicken.
3. Wählen Sie unter **"Richtlinie für Notrufe**" die Richtlinie aus, und klicken Sie dann auf **"Speichern"**.

### <a name="using-powershell"></a>Verwendung von PowerShell
Verwenden Sie das Cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) , um einem Netzwerkstandort eine Richtlinie für Notrufe zuzuweisen.

Das folgende Beispiel zeigt, wie Sie der Site1-Website eine Richtlinie namens "Contoso Emergency Calling Policy 1" zuweisen.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Richtlinien für die Notrufweiterleitung in Teams](manage-emergency-call-routing-policies.md)

[Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)

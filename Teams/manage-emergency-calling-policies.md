---
title: Verwalten von Notruf Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Notfall Anruf Richtlinien in Microsoft Teams verwenden und verwalten.
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: b339f2ef46e0d9949fb440d2ad5a6fa0dee09fe4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694371"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Verwalten von Notruf Richtlinien in Microsoft Teams

Wenn Ihre Organisation Anrufpläne verwendet oder ein direktes Routing für das Telefon System bereitgestellt hat, können Sie in Microsoft Teams Notruf Richtlinien verwenden, um zu definieren, was passiert, wenn ein Team Benutzer in Ihrer Organisation einen Notfall Anruf tätigt. Sie können festlegen, welche Personen benachrichtigt werden sollen und wie Sie benachrichtigt werden, wenn ein Benutzer, dem die Richtlinie zugewiesen ist, Notfalldienste aufruft. So können Sie beispielsweise Richtlinieneinstellungen so konfigurieren, dass Sie den Security Desk Ihrer Organisation automatisch benachrichtigen und in Notrufen abhören.  

Sie verwalten Notruf Richtlinien, indem Sie im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu **VoIP** > -**Notfall Richtlinien** wechseln. Die Richtlinien können Benutzern und [Netzwerk Websites](cloud-voice-network-settings.md)zugewiesen werden.

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.

Wenn Sie einer Netzwerk Website und einem Benutzer eine Notruf Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-calling-policy"></a>Erstellen einer benutzerdefinierten Notfall Anrufrichtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Richtlinien** .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Legen Sie fest, wie Personen in Ihrer Organisation, in der Regel der Security Desk, benachrichtigt werden sollen, wenn ein Notruf durchgeführt wird. Wählen Sie dazu unter **Benachrichtigungsmodus**eine der folgenden Optionen aus:
    - **Nur Benachrichtigung**: eine Team-Chat-Nachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet.
    - **Konferenz, aber stumm geschaltet**: eine Team-Chat-Nachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet, und Sie können in der Konversation zwischen dem Anrufer und dem PSAP-Operator lauschen (aber nicht teilnehmen).
5.  Wenn Sie den Benachrichtigungsmodus für Konferenzgespräche, **aber stumm geschaltet** ausgewählt haben, können Sie im Feld **auswählnummer für Benachrichtigungen** eine PSTN-Telefonnummer eines Benutzers oder einer Gruppe eingeben, um anzurufen und an dem Notruf teilzunehmen. Geben Sie beispielsweise die Nummer des Security Desk Ihrer Organisation ein, der einen Anruf erhält, wenn ein Notruf durchgeführt wird, den Sie dann anhören oder am Anruf teilnehmen können.
6. Suchen Sie nach einem oder mehreren Benutzern oder Gruppen, wie dem Security Desk Ihrer Organisation, um zu benachrichtigen, wenn ein Notruf durchgeführt wird.  Die Benachrichtigung kann an e-Mail-Adressen von Benutzern, Verteilergruppen und Sicherheitsgruppen gesendet werden. Es können maximal 50-Benutzer benachrichtigt werden.
7. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwenden von PowerShell

Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Bearbeiten einer Notruf Richtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Richtlinien** .
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="using-powershell"></a>Verwenden von PowerShell

Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie für Benutzer

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen Sie unter **Notruf Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.

Informationen dazu, wie Sie eine benutzerdefinierte Teamrichtlinie mehreren Benutzern gleichzeitig zuweisen können, finden Sie unter [Batchbearbeitung von Benutzereinstellungen eines Teams](edit-user-settings-in-bulk.md).

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Richtlinien** .
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwenden von PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie zu einem Benutzer

Siehe [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie zu Benutzern in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Notruf Richtlinie zuweisen. So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.

In diesem Beispiel weisen wir allen Benutzern in der Contoso-Vorgangsgruppe eine Richtlinie mit dem Namen "Operations Emergency Calling Policy" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
Abrufen der Mitglieder der gewählten Gruppe.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Zuweisen aller Benutzer in der Gruppe zu einer bestimmten Teamrichtlinie. In diesem Beispiel handelt es sich um die Richtlinie für die Notfall Anrufweiterleitung.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie zu einer Netzwerk Website

Verwenden Sie das Cmdlet " [Satz-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notruf Richtlinie zuzuweisen.

Im folgenden Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Contoso Emergency Calling Policy 1" zugewiesen wird.

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notfall Anruf Weiterleitungsrichtlinien in Teams](manage-emergency-call-routing-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

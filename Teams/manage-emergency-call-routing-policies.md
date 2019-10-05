---
title: Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Routing Richtlinien für Notfälle für das Dynamic E911-Feature in Microsoft Teams verwenden und verwalten.
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e7a1295d481db2d970fae2c77be2cff6834c6448
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401831"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Wenn Sie in Ihrer Organisation ein direktes Routing für Telefonsysteme bereitgestellt haben, können Sie in Microsoft Teams Notfall-Anruf Weiterleitungsrichtlinien verwenden, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden. Eine Notruf Routing-Richtlinie legt fest, ob erweiterte Notfalldienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notrufdienste aufgerufen werden (beispielsweise 911 in den USA) und wie Anrufe an Notfalldienste weitergeleitet werden.

Sie verwalten Notruf Routing Richtlinien, indem Sie im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu **VoIP** > -**Notfall Richtlinien** wechseln. Die Richtlinien können Benutzern und [Netzwerk Websites](location-based-routing-terminology.md)zugewiesen werden.

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.

Wenn Sie einer Netzwerk Website und einem Benutzer eine Notfall Anruf-Routing Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
4. Aktivieren Sie erweiterte **Notfalldienste,** um erweiterte Notfalldienste zu aktivieren. Wenn erweiterte Notfalldienste aktiviert sind, ruft Teams Richtlinien-und Standortinformationen vom Dienst ab und enthält diese Informationen im Rahmen des Notrufs.
5. Definieren Sie eine der weiteren Notrufnummern. Gehen Sie dazu unter **Notrufnummern**wie folgt vor:
    1. **Notfall Wahl Zeichenfolge**: Geben Sie die Notrufnummer ein. Diese Wählzeichenfolge zeigt an, dass ein Anruf ein Notruf ist.
    2. **Notfall-Wähl Maske**: Sie können für jede Notrufnummer NULL oder mehr Notrufnummern angeben. Eine Wähl Maske ist die Nummer, die Sie in den Wert der Notruf-Wählzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann auch Notfalldienste erreichen. <br>Beispielsweise fügen Sie 112 als Notruf Maske hinzu, bei der es sich um die Notrufnummer für die meisten Europa und 911 als Notruf Zeichenfolge handelt. Ein Team Nutzer aus Europa, der gerade besucht, weiß möglicherweise nicht, dass 911 die Notrufnummer in den Vereinigten Staaten ist, und wenn Sie 112 wählen, wird der Anruf an 911 durchgeführt. Wenn Sie mehrere Wähl Masken definieren möchten, trennen Sie die einzelnen Werte durch ein Semikolon. Beispiel: 112; 212.
    3. **PSTN-Verwendung**: Wählen Sie die Verwendung des öffentlichen Switched Telephone Network (PSTN) aus. Die PSTN-Nutzung wird verwendet, um zu ermitteln, welche Route zur Weiterleitung von Notrufen von Benutzern verwendet wird, die zur Verwendung autorisiert sind. Die Route, die mit dieser Verwendung verknüpft ist, sollte auf einen SIP-Stammverweisen, der für Notrufe vorgesehen ist, oder für ein Notfall Standort-Identifikationsnummer (Elin)-Gateway, das Notrufe an den nächstgelegenen öffentlichen Sicherheits-Anrufbeantworter (PSAP) weiterleitet.

    > [!NOTE]
    > Wählzeichenfolgen und Wähl Masken müssen innerhalb einer Richtlinie eindeutig sein. Das bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren können, und Sie können mehrere Wähl Masken für eine Wählzeichenfolge festlegen, aber jede Wählzeichenfolge und Wähl Maske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwenden von PowerShell

Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Notfall Anruf-Routing Richtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Sie können die globale Richtlinie oder alle von Ihnen erstellten benutzerdefinierten Richtlinien bearbeiten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken und dann auf **Bearbeiten**klicken.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="using-powershell"></a>Verwenden von PowerShell

Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Klicken Sie auf **Richtlinien**und dann neben **zugewiesene Richtlinien**auf **Bearbeiten**.
3. Wählen Sie unter **Notruf Weiterleitungs Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.

Informationen zum Zuweisen einer benutzerdefinierten Teams-Richtlinie zu mehreren Benutzern gleichzeitig finden Sie unter [Bearbeiten von Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).

Oder Sie können auch die folgenden Aktionen ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten**aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwenden von PowerShell

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe an einen Benutzer

Siehe [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Notfall Routing Richtlinie zuweisen. So können Sie beispielsweise allen Benutzern in einer Sicherheits-oder Verteilergruppe eine Richtlinie zuweisen. Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.

In diesem Beispiel weisen wir allen Benutzern in der Gruppe Contoso HR eine Richtlinie mit dem Namen "HR Emergency Call Routing Policy" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
Rufen Sie die Mitglieder der angegebenen Gruppe ab.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie alle Benutzer in der Gruppe einer bestimmten Teams-Richtlinie zu. In diesem Beispiel handelt es sich um eine Personal Notruf-Routing-Richtlinie.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie zu einer Netzwerk Website

Verwenden Sie das Cmdlet " [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notfall Anruf-Routing Richtlinie zuzuweisen.

In diesem Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Emergency Call Routing Policy 1" zugewiesen wird.

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)

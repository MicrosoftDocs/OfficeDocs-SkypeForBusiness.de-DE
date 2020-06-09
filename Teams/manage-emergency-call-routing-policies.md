---
title: Verwalten von Notfall-Anrufweiterleitungsrichtlinien
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Microsoft Teams Notruf-Routing Richtlinien verwenden und verwalten, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b200f5a160e7b13a9412d588f3342eeb5a08ccd8
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638694"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams

Wenn Sie in Ihrer Organisation ein [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md) bereitgestellt haben, können Sie in Microsoft Teams Notfall-Anruf Weiterleitungsrichtlinien verwenden, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden. Eine Notruf Routing-Richtlinie legt fest, ob erweiterte Notfalldienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notrufdienste aufgerufen werden (beispielsweise 911 in den USA) und wie Anrufe an Notfalldienste weitergeleitet werden.

Sie verwalten Notruf Routing Richtlinien, indem Sie **Voice**  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Notfall Richtlinien** wechseln. Die Richtlinien können Benutzern und [Netzwerk Websites](cloud-voice-network-settings.md)zugewiesen werden.

Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu. Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können. Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.

Wenn Sie einer Netzwerk Website und einem Benutzer eine Notfall Anruf-Routing Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Erstellen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Aktivieren Sie **dynamische**Notrufe, um dynamische Notrufe zu ermöglichen. Wenn dynamische Notrufe aktiviert sind, ruft Teams Richtlinien-und Standortinformationen vom Dienst ab und enthält diese Informationen im Rahmen des Notrufs.
5. Definieren Sie eine oder mehrere Notfallnummern. Klicken Sie dazu unter **Notrufnummern**auf **Hinzufügen**, und gehen Sie dann folgendermaßen vor:
    1. **Notfall Wahl Zeichenfolge**: Geben Sie die Notrufnummer ein. Diese Wählzeichenfolge zeigt an, dass ein Anruf ein Notruf ist.
        > [!NOTE]
        > Für das direkte Routing wechseln wir von Teams-Clients, die Notrufe mit einem "+" vor der Notruf Zeichenfolge senden. Bis zum Abschluss des Übergangs sollte das VoIP-Routenmuster einer Notruf Zeichenfolge entsprechen, um sicherzustellen, dass Zeichenfolgen mit einem vorangehenden "+", wie 911 und + 911, übereinstimmen. Beispiel: ^ \\ +? 911 oder. *.
    2. **Notfall-Wähl Maske**: Sie können für jede Notrufnummer NULL oder mehr Notrufnummern angeben. Eine Wähl Maske ist die Nummer, die Sie in den Wert der Notruf-Wählzeichenfolge übersetzen möchten. Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann auch Notfalldienste erreichen. <br>Beispielsweise fügen Sie 112 als Notruf Maske hinzu, bei der es sich um die Notrufnummer für die meisten Europa und 911 als Notruf Zeichenfolge handelt. Ein Team Nutzer aus Europa, der gerade besucht, weiß möglicherweise nicht, dass 911 die Notrufnummer in den Vereinigten Staaten ist, und wenn Sie 112 wählen, wird der Anruf an 911 durchgeführt. Wenn Sie mehrere Wähl Masken definieren möchten, trennen Sie die einzelnen Werte durch ein Semikolon. Beispiel: 112; 212.
    3. **PSTN-Verwendungsdaten Satz**: Wählen Sie den Eintrag für die öffentliche Telefonnetz Nutzung (PSTN) aus. Der PSTN-Nutzungsdaten Satz wird verwendet, um zu ermitteln, welche Route zur Weiterleitung von Notrufen von Benutzern verwendet wird, die zur Verwendung autorisiert sind. Die Route, die mit dieser Verwendung verknüpft ist, sollte auf einen SIP-Stamm (Session Initiation Protocol) verweisen, der für Notrufe vorgesehen ist, oder für ein Notfall-Standort-ID (Elin)-Gateway, das Notrufe an den nächstgelegenen öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weiterleitet.

    > [!NOTE]
    > Wählzeichenfolgen und Wähl Masken müssen innerhalb einer Richtlinie eindeutig sein. Das bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren können, und Sie können mehrere Wähl Masken für eine Wählzeichenfolge festlegen, aber jede Wählzeichenfolge und Wähl Maske darf nur einmal verwendet werden.

6. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Bearbeiten einer Notfall Anruf-Routing Richtlinie

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen Sie unter **Notruf Weiterleitungs Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
3. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.  

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe an einen Benutzer

Siehe [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Notfall Routing Richtlinie zuweisen. So können Sie beispielsweise allen Benutzern in einer Sicherheits-oder Verteilergruppe eine Richtlinie zuweisen. Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.

In diesem Beispiel weisen wir allen Benutzern in der Gruppe Contoso HR eine Richtlinie mit dem Namen "HR Emergency Call Routing Policy" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
Abrufen der Mitglieder der gewählten Gruppe.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Zuweisen aller Benutzer in der Gruppe zu einer bestimmten Teamrichtlinie. In diesem Beispiel handelt es sich um eine Personal Notruf-Routing-Richtlinie.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallRoutingPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie zu einer Netzwerk Website

Verwenden Sie das Cmdlet " [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notfall Anruf-Routing Richtlinie zuzuweisen.

In diesem Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Emergency Call Routing Policy 1" zugewiesen wird.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notruf Richtlinien in Teams](manage-emergency-calling-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)

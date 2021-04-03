---
title: Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie mehr über die verschiedenen Methoden zum Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574317"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen

In diesem Artikel werden die verschiedenen Methoden zum Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams erläutert. Stellen Sie vor dem Lesen sicher, dass Sie Richtlinien in Teams zuweisen gelesen haben [– erste Schritte.](policy-assignment-overview.md)

## <a name="assign-a-policy-package-to-users"></a>Zuweisen eines Richtlinienpakets zu Benutzern

Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die über dieselben oder ähnliche Rollen in Ihrer Organisation verfügen. Jedes Richtlinienpaket ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen. Einige Beispiele für Richtlinienpakete sind das Bildungspaket (Lehrer) und das Paket Gesundheitswesen (Klinischer Mitarbeiter). Weitere Informationen finden Sie unter [Verwalten von Richtlinienpaketen in Teams.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Zuweisen eines Richtlinienpakets zu einem Benutzer

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Benutzer**, und wählen Sie dann den Benutzer aus.
2. Wählen Sie auf der Seite des Benutzers **Richtlinien** und dann neben **Richtlinienpaket** die Option **Bearbeiten aus.**
3. Wählen Sie **im Bereich Richtlinienpaket zuweisen** das Paket aus, das Sie zuweisen möchten, und wählen Sie dann Speichern **aus.**

![Screenshot des Teams Admin Center für die Zuweisung eines Richtlinienpakets an einen Benutzer](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Zuweisen eines Richtlinienpakets zu mehreren Benutzern

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Richtlinienpakete, und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.
2. Wählen Sie **Benutzer verwalten** aus.
3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern aus.**

![Screenshot des Teams Admin Center für die Richtlinienpaketzuweisung für mehrere Benutzer](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Zuweisung von Richtlinienpaketen zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.

Wenn Sie das Richtlinienpaket zuweisen, wird es der Gruppe sofort zugewiesen. Die Weitergabe der Richtlinienzuordnung an Die Mitglieder der Gruppe wird jedoch als Hintergrundvorgang ausgeführt und kann je nach Größe der Gruppe einige Zeit dauern. Das gleiche gilt, wenn eine Richtlinie nicht aus einer Gruppe zugewiesen wird oder wenn Mitglieder zu einer Gruppe hinzugefügt oder aus dieser entfernt werden.

> [!IMPORTANT]
> Bevor Sie beginnen, ist es wichtig zu verstehen ([Rangfolgeregeln](assign-policies-users-and-groups.md#precedence-rules)) und ([Gruppenzuordnungsrangliste](assign-policies-users-and-groups.md#group-assignment-ranking)). Stellen Sie sicher, dass Sie die Konzepte in ([Was](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)Sie über die Richtlinienzuordnung zu Gruppen wissen müssen) weiter oben in diesem Artikel lesen und verstehen.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern im Admin Center

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Wechseln Sie im linken Navigationsbereich zur Seite "Richtlinienpaket".
3. Wählen Sie die Registerkarte Gruppenrichtlinienzuordnung aus.
4. Wählen **Sie Gruppe hinzufügen** aus, und gehen Sie dann im Bereich Zuweisen eines Richtlinienpakets zum Gruppenbereich wie folgt vor:

    a. Suchen Sie nach der Gruppe, der Sie das Richtlinienpaket zuweisen möchten, und fügen Sie sie hinzu.

    b. Wählen Sie ein Richtlinienpaket aus.

    c. Legen Sie die Bewertung für jeden Richtlinientyp ein.

    d. Wählen Sie **Übernehmen aus.**

![zeigt die Gruppenrichtlinienzuordnung an.](media/group-pkg-assignment.png)

5. Um die Bewertung für einen bestimmten Richtlinientyp zu verwalten, navigieren Sie zur jeweiligen Richtlinienseite.
6. Wenn Sie ein Richtlinienpaket einer Gruppe erneut zuweisen möchten, entfernen Sie zuerst die Gruppenrichtlinienzuordnung. Führen Sie dann die vorstehenden Schritte aus, um das Richtlinienpaket einer Gruppe zuzuordnen.

### <a name="work-with-powershell"></a>Arbeiten mit PowerShell

#### <a name="get-the-teams-powershell-module"></a>Holen Sie sich das Teams PowerShell-Modul

Schrittweise Anleitungen finden Sie unter [Installieren von Teams PowerShell](teams-powershell-install.md).

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

Verwenden Sie [das Grant-CsGroupPolicyPackageAssignment-Cmdlet,](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) um einer Gruppe ein Richtlinienpaket zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, DER SIP-Adresse oder der E-Mail-Adresse angeben. Geben Sie beim Zuweisen des[](assign-policies-users-and-groups.md#group-assignment-ranking)Richtlinienpakets für jeden Richtlinientyp im Richtlinienpaket eine ( Gruppenzuordnungsrangliste) an.

In diesem Beispiel weisen wir das Education_Teacher-Richtlinienpaket einer Gruppe mit der Zuordnungsrangfolge 1 für TeamsAppSetupPolicy und TeamsMeetingBroadcastPolicy und einer Rangfolge von 2 für TeamsMeetingPolicy zu.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

Bei der Zuweisung von Batchrichtlinienpaketen können Sie großen Benutzergruppen gleichzeitig ein Richtlinienpaket zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das [Cmdlet New-CsBatchPolicyAssignmentOperation,](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um einen Batch von Benutzern und das Richtlinienpaket zu übermitteln, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das [Cmdlet Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) verwenden, um den Fortschritt und Status der Zuordnungen in einem Batch nachverfolgt zu haben.

Geben Sie Benutzer nach ihrer Objekt-ID oder der SIP-Adresse (Session Initiation Protocol) an. Die SIP-Adresse eines Benutzers hat häufig denselben Wert wie der User Principal Name (UPN) oder die E-Mail-Adresse, aber dies ist nicht erforderlich. Wenn ein Benutzer mit dem UPN oder der E-Mail angegeben wird, aber einen anderen Wert als seine SIP-Adresse hat, kann die Richtlinienzuweisung für den Benutzer fehlschlagen. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die eindeutigen Benutzer bereitgestellt, die im Batch verblieben sind.

Ein Batch enthält bis zu 5.000 Benutzer. Um optimale Ergebnisse zu erzielen, reichen Sie nicht mehr als ein paar Batches gleichzeitig ein. Zulassen, dass Batches die Verarbeitung abschließen, bevor Sie weitere Batches übermitteln.

### <a name="use-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Führen Sie folgendes aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern noch nicht). Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Zuweisen von Richtlinienpaketen zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das [Cmdlet New-CsBatchPolicyAssignmentOperation,](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) um das Education_PrimaryStudent-Richtlinienpaket einem Batch von Benutzern zuzuweisen.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Anzeigen des Status einer Batchzuordnung

Führen Sie folgendes aus, um den Status einer Batchzuordnung zu erhalten, wobei "OperationId" die Vorgangs-ID ist, die vom Cmdlet für einen bestimmten ```New-CsBatchPolicyAssignmentOperation``` Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie folgendes aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der -Eigenschaft ```UserState``` befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
- [Verwalten von Richtlinienpaketen in Microsoft Teams](manage-policy-packages.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams – erste Schritte](policy-assignment-overview.md)
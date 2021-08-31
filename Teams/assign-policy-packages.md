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
ms.localizationpriority: medium
search.appverid: MET150
description: Lernen Sie die verschiedenen Methoden zum Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: fb7d402ab8a280a724562eec7820f1cad06ea52f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727194"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen

In diesem Artikel werden die verschiedenen Methoden zum Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams. Stellen Sie vor dem Lesen sicher, dass Sie unter Zuweisen von Richtlinien [in Teams – Erste Schritte gelesen haben.](policy-assignment-overview.md)

> [!NOTE]
> Jeder Benutzer benötigt das Add-On für erweiterte Kommunikation, um eine benutzerdefinierte Richtlinienpaketzuweisung zu erhalten. Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Zuweisen eines Richtlinienpakets zu Benutzern

Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die in Ihrer Organisation über die gleichen oder ähnliche Rollen verfügen. Jedes Richtlinienpaket ist auf eine Benutzerrolle ausgelegt und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen. Einige Beispiele für Richtlinienpakete sind das Paket "Education (Teacher)" und das Paket "Klinischer Mitarbeiter" im Gesundheitswesen. Weitere Informationen finden Sie unter [Verwalten von Richtlinienpaketen in Teams.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>Zuweisen eines Richtlinienpakets zu einem Benutzer

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Benutzer**, und wählen Sie dann den Benutzer aus.
2. Wählen Sie auf der Seite des Benutzers **Richtlinien** und dann neben Richtlinienpaket **die** Option **Bearbeiten aus.**
3. Wählen Sie **im Bereich Richtlinienpaket** zuweisen das Paket aus, das Sie zuweisen möchten, und wählen Sie dann Speichern **aus.**

![Teams Admin Center-Screenshot für die Richtlinienpaketzuweisung an einen Benutzer.](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Zuweisen eines Richtlinienpakets zu mehreren Benutzern

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu Richtlinienpakete **,** und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.
2. Wählen Sie **Benutzer verwalten** aus.
3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.
4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern aus.**

![Teams Admin Center-Screenshot für die Richtlinienpaketzuweisung für mehrere Benutzer.](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Zuweisung von Richtlinienpaketen zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch bei größeren Gruppen.

Wenn Sie das Richtlinienpaket zuweisen, wird es der Gruppe sofort zugewiesen. Die Weitergabe der Richtlinienzuweisung an Mitglieder der Gruppe erfolgt jedoch als Hintergrundvorgang und kann je nach Größe der Gruppe einige Zeit dauern. Dasselbe gilt, wenn eine Richtlinie nicht einer Gruppe zugewiesen wird oder Mitglieder einer Gruppe hinzugefügt oder aus ihr entfernt werden.

> [!IMPORTANT]
> Bevor Sie beginnen, sollten Sie ( Rangfolgeregeln[)](assign-policies-users-and-groups.md#precedence-rules)und ([Gruppenzuordnungsrangfolge) verstehen.](assign-policies-users-and-groups.md#group-assignment-ranking) Lesen und verstehen Sie die Konzepte in[(](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen) weiter oben in diesem Artikel.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Zuweisen eines Richtlinienpakets zu einer Benutzergruppe im Admin Center

1. Melden Sie sich beim Microsoft Teams Admin Center an.
2. Wechseln Sie im linken Navigationsbereich zur Seite des Richtlinienpakets.
3. Wählen Sie die Registerkarte Gruppenrichtlinienzuordnung aus.
4. Wählen **Sie Gruppe hinzufügen** aus, und gehen Sie dann im Bereich Richtlinienpaket einer Gruppe zuweisen wie folgt vor:

    a. Suchen Sie nach der Gruppe, der Sie das Richtlinienpaket zuweisen möchten, und fügen Sie sie hinzu.

    b. Wählen Sie ein Richtlinienpaket aus.

    c. Legen Sie die Rangfolge für jeden Richtlinientyp an.

    d. Wählen Sie **Übernehmen aus.**

![Zeigt die Gruppenrichtlinienzuordnung an.](media/group-pkg-assignment.png)

5. Um die Rangfolge für einen bestimmten Richtlinientyp zu verwalten, navigieren Sie zur jeweiligen Richtlinienseite.
6. Wenn Sie ein Richtlinienpaket einer Gruppe erneut zuweisen möchten, entfernen Sie zuerst die Gruppenrichtlinienzuweisung. Führen Sie dann die vorstehenden Schritte aus, um das Richtlinienpaket einer Gruppe zuzuordnen.

### <a name="work-with-powershell"></a>Arbeiten mit PowerShell

#### <a name="get-the-teams-powershell-module"></a>Holen Sie sich Teams PowerShell-Modul

Eine schrittweise Anleitung finden Sie unter Installieren [Teams PowerShell.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Benutzergruppe

Verwenden Sie das [Cmdlet Grant-CsGroupPolicyPackageAssignment,](/powershell/module/teams/grant-csgrouppolicypackageassignment) um einer Gruppe ein Richtlinienpaket zuzuweisen. Sie können eine Gruppe mit der Objekt-ID, der SIP-Adresse oder der E-Mail-Adresse angeben. Geben Sie beim Zuweisen des Richtlinienpakets für jeden Richtlinientyp im Richtlinienpaket eine[an](assign-policies-users-and-groups.md#group-assignment-ranking)( Gruppenzuordnungsrangfolge).

In diesem Beispiel weisen wir das Education_Teacher-Richtlinienpaket einer Gruppe mit der Zuordnungsrangfolge 1 für TeamsAppSetupPolicy und TeamsMeetingBroadcastPolicy und der Rangfolge 2 für TeamsMeetingPolicy zu.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

Mit der Batchrichtlinienpaketzuordnung können Sie großen Gruppen von Benutzern gleichzeitig ein Richtlinienpaket zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das [Cmdlet New-CsBatchPolicyAssignmentOperation,](/powershell/module/teams/new-csbatchpolicyassignmentoperation) um eine Gruppe von Benutzern und das Richtlinienpaket zu übermitteln, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das [Cmdlet Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) verwenden, um den Fortschritt und Status der Zuordnungen in einem Stapel nachverfolgt.

Geben Sie Benutzer nach ihrer Objekt-ID oder der SIP-Adresse (Session Initiation Protocol) an. Die SIP-Adresse eines Benutzers hat häufig den gleichen Wert wie der Benutzerprinzipalname (User Principal Name, UPN) oder die E-Mail-Adresse, aber dies ist nicht erforderlich. Wenn ein Benutzer mit dem UPN oder der E-Mail-Adresse angegeben wird, aber einen anderen Wert als seine SIP-Adresse hat, kann die Richtlinienzuweisung für den Benutzer nicht ausgeführt werden. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die im Batch verbleibenden eindeutigen Benutzer bereitgestellt.

Ein Batch enthält bis zu 5.000 Benutzer. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehr als ein paar Batches gleichzeitig. Lassen Sie die Verarbeitung von Batches abschließen, bevor Sie weitere Batches übermitteln.

### <a name="use-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Führen Sie Folgendes aus, um [das Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern noch nicht vorhanden). Vergewissern Sie sich, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um Teams Verbindung herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Zuweisen von Richtlinienpaketen zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das [Cmdlet New-CsBatchPolicyAssignmentOperation,](/powershell/module/teams/new-csbatchpolicyassignmentoperation) um das Education_PrimaryStudent-Richtlinienpaket einer Gruppe von Benutzern zuzuweisen.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Anzeigen des Status einer Batchzuordnung

Führen Sie die folgenden Schritte aus, um den Status einer Batchzuordnung zu erhalten. Dabei steht "OperationId" für die Vorgangs-ID, die vom Cmdlet für einen bestimmten ```New-CsBatchPolicyAssignmentOperation``` Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der -Eigenschaft ```UserState``` befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten Teams mit Richtlinien](manage-teams-with-policies.md)
- [Verwalten von Richtlinienpaketen in Microsoft Teams](manage-policy-packages.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams – Erste Schritte](policy-assignment-overview.md)

---
title: Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen
author: mkbond007
ms.author: mabond
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
description: Lernen Sie die verschiedenen Methoden zum Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams kennen.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 48391db005ca7d40081c0aeb22f71be58fcc9f9f
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646524"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen

In diesem Artikel werden die verschiedenen Methoden zum Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams beschrieben. Stellen Sie vor dem Lesen sicher, dass Sie ["Richtlinien zuweisen" in Teams gelesen haben – erste Schritte](policy-assignment-overview.md).

> [!NOTE]
> Jeder Benutzer benötigt das Add-On für erweiterte Kommunikation, um eine benutzerdefinierte Richtlinienpaketzuweisung zu erhalten. Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="assign-a-policy-package-to-users"></a>Zuweisen eines Richtlinienpakets zu Benutzern

Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die die gleichen oder ähnliche Rollen in Ihrer Organisation haben. Jedes Richtlinienpaket basiert auf einer Benutzerrolle und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die aktivitäten unterstützen, die für diese Rolle typisch sind. Einige Beispiele für Richtlinienpakete sind das Paket "Bildung" (Lehrer) und "Gesundheitswesen" (Klinischer Mitarbeiter). Weitere Informationen finden [Sie unter Verwalten von Richtlinienpaketen in Teams](manage-policy-packages.md).

### <a name="assign-a-policy-package-to-one-user"></a>Zuweisen eines Richtlinienpakets zu einem Benutzer

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **"Benutzer**", und wählen Sie dann den Benutzer aus.

2. Wählen Sie auf der Seite des Benutzers **"Richtlinien**" und dann neben " **Richtlinienpaket**" die Option " **Bearbeiten"** aus.

3. Wählen Sie im Bereich " **Richtlinienpaket zuweisen** " das Paket aus, das Sie zuweisen möchten, und wählen Sie dann **"Speichern"** aus.

![Teams Screenshot des Admin Centers für die Zuweisung eines Richtlinienpakets zu einem Benutzer.](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>Zuweisen eines Richtlinienpakets zu mehreren Benutzern

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **"Richtlinienpakete**", und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.

2. Wählen Sie **Nutzer verwalten** aus.

3. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.

4. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Speichern"** aus.


![Teams Screenshot des Admin Centers für die Zuweisung von Richtlinienpaketen zu mehreren Benutzern.](media/assign-policypackages-multipleusers.png)


## <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.

Die Zuweisung von Richtlinienpaketen zu Gruppen wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.

Wenn Sie das Richtlinienpaket zuweisen, wird es sofort der Gruppe zugewiesen. Die Weitergabe der Richtlinienzuweisung an Mitglieder der Gruppe wird jedoch als Hintergrundvorgang ausgeführt und kann je nach Größe der Gruppe einige Zeit in Anspruch nehmen. Dasselbe gilt, wenn eine Richtlinie einer Gruppe nicht zugewiesen wird oder wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden.

> [!IMPORTANT]
> Bevor Sie beginnen, ist es wichtig zu verstehen ([Rangfolgeregeln](assign-policies-users-and-groups.md#precedence-rules)) und ([Gruppenzuweisungsrangfolge](assign-policies-users-and-groups.md#group-assignment-ranking)). Stellen Sie sicher, dass Sie die Konzepte weiter oben in diesem Artikel lesen und verstehen ([Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)).

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern im Admin Center

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Wechseln Sie im linken Navigationsbereich zur Seite "Richtlinienpaket".

3. Wählen Sie die Registerkarte "Gruppenrichtlinienzuweisung" aus.

4. Wählen Sie **"Gruppe hinzufügen"** aus, und führen Sie dann im Gruppenbereich "Richtlinienpaket zuweisen" die folgenden Schritte aus:

    1. Suchen Sie nach der Gruppe, der Sie das Richtlinienpaket zuweisen möchten, und fügen Sie sie hinzu.

    1. Wählen Sie ein Richtlinienpaket aus.

    1. Legen Sie die Rangfolge für jeden Richtlinientyp fest.

    1. Wählen Sie **"Übernehmen" aus**.


       ![zeigt die Gruppenrichtlinienzuweisung an.](media/group-pkg-assignment.png)

5. Um die Rangfolge für einen bestimmten Richtlinientyp zu verwalten, navigieren Sie zur jeweiligen Richtlinienseite.

6. Um ein Richtlinienpaket einer Gruppe erneut zuzuweisen, entfernen Sie zuerst die Gruppenrichtlinienzuweisung. Führen Sie dann die vorstehenden Schritte aus, um das Richtlinienpaket einer Gruppe zuzuweisen.

### <a name="work-with-powershell"></a>Arbeiten mit PowerShell

#### <a name="get-the-teams-powershell-module"></a>Abrufen des Teams PowerShell-Moduls

Eine schrittweise Anleitung finden [Sie unter "Installieren Teams PowerShell](teams-powershell-install.md)".

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

Verwenden Sie das Cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) , um einer Gruppe ein Richtlinienpaket zuzuweisen. Sie können eine Gruppe mithilfe der Objekt-ID, SIP-Adresse oder E-Mail-Adresse angeben. Wenn Sie das Richtlinienpaket zuweisen, geben Sie eine ([Gruppenzuweisungsrangfolge](assign-policies-users-and-groups.md#group-assignment-ranking)) für jeden Richtlinientyp im Richtlinienpaket an.

In diesem Beispiel weisen wir das Education_Teacher Richtlinienpaket einer Gruppe mit der Zuordnungsrangfolge 1 für "TeamsAppSetupPolicy" und "TeamsMeetingBroadcastPolicy" und der Rangfolge "2" für "TeamsMeetingPolicy" zu.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern

Mit der Batch-Richtlinienpaketzuweisung können Sie großen Gruppen von Benutzern gleichzeitig ein Richtlinienpaket zuweisen, ohne ein Skript verwenden zu müssen. Sie verwenden das Cmdlet ["New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) ", um eine Reihe von Benutzern und das Richtlinienpaket zu senden, die Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert. Anschließend können Sie das Cmdlet ["Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) " verwenden, um den Fortschritt und Status der Zuordnungen in einem Batch nachzuverfolgen.

Geben Sie Benutzer anhand ihrer Objekt-ID oder SIP-Adresse (Session Initiation Protocol) an. Die SIP-Adresse eines Benutzers hat häufig denselben Wert wie der Benutzerprinzipalname (User Principal Name, UPN) oder die E-Mail-Adresse, dies ist jedoch nicht erforderlich. Wenn ein Benutzer mithilfe seines UPN oder seiner E-Mail angegeben wird, aber einen anderen Wert als seine SIP-Adresse aufweist, schlägt die Richtlinienzuweisung für den Benutzer fehl. Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate vor der Verarbeitung aus dem Batch entfernt, und der Status wird nur für die im Batch verbleibenden eindeutigen Benutzer bereitgestellt.

Ein Batch enthält bis zu 5.000 Benutzer. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehr als ein paar Batches gleichzeitig. Zulassen, dass Batches die Verarbeitung abschließen, bevor weitere Batches gesendet werden.

### <a name="use-the-teams-powershell-module"></a>Verwenden des Teams PowerShell-Moduls

Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern noch nicht geschehen). Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie Folgendes aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>Zuweisen von Richtlinienpaketen zu einer Gruppe von Benutzern

In diesem Beispiel verwenden wir das Cmdlet ["New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) ", um das Education_PrimaryStudent Richtlinienpaket einem Benutzerbatch zuzuweisen.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>Anzeigen des Status einer Batchzuordnung

Führen Sie Folgendes aus, um den Status einer Batchzuordnung abzurufen, wobei "OperationId" die Vorgangs-ID ist, die `New-CsBatchPolicyAssignmentOperation` vom Cmdlet für einen bestimmten Batch zurückgegeben wird.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie Folgendes aus, um weitere Informationen zu Fehlern zu erhalten, die sich in der `UserState` Eigenschaft befinden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
- [Verwalten von Richtlinienpaketen in Microsoft Teams](manage-policy-packages.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien in Teams – erste Schritte](policy-assignment-overview.md)

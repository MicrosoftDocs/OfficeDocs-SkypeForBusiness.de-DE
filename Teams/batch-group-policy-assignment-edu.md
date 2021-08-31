---
title: Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie großen Gruppen in Ihrer Bildungseinrichtung basierend auf Gruppenmitgliedschaften oder direkt über eine Batchzuweisung für Remoteunterrichtszwecke (Teleschool, Teleschule) Richtlinien zuweisen.
f1keywords: ''
ms.openlocfilehash: 8d7eed80375b87eb09cbad803e99d35578c5bbc8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731374"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Weitere Informationen zum Zuweisen von Richtlinien in Microsoft Teams finden Sie unter Zuweisen von Richtlinien [zu Benutzern in Teams.](assign-policies.md)

## <a name="overview"></a>Übersicht

Müssen Sie Ihren Schülern/Studierenden und Lehrkräften Zugriff auf verschiedene Features in ihrer Microsoft Teams? Sie können die Benutzer in Ihrer Organisation schnell nach Lizenztyp identifizieren und ihnen dann die entsprechende Richtlinie zuweisen. In diesem Lernprogramm wird gezeigt, wie Sie eine Besprechungsrichtlinie großen Gruppen von Benutzern in Ihrer Schule zuweisen. Sie können Richtlinien über Microsoft Teams Admin Center und PowerShell zuweisen, und wir zeigen Ihnen beide Möglichkeiten.

Sie können eine Besprechungsrichtlinie einer Sicherheitsgruppe zuweisen, deren Mitglieder die Benutzer sind, oder Benutzern direkt im Maßstab einer Batchrichtlinienzuweisung zuweisen. Folgende Punkte werden behandelt:

- **Verwenden [Sie Richtlinienzuweisungen zu Gruppen,](#assign-a-policy-to-a-group) um einer Sicherheitsgruppe eine Besprechungsrichtlinie zuzuordnen (empfohlen).** Mit dieser Methode können Sie eine Richtlinie basierend auf der Gruppenmitgliedschaft zuweisen. Sie können einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zuweisen. Wenn Mitglieder der Gruppe hinzugefügt oder aus ihr entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Wir empfehlen, diese Methode zu verwenden, da dadurch die Zeit zum Verwalten von Richtlinien für neue Benutzer verringert wird oder sich die Rollen von Benutzern ändern. Diese Methode funktioniert am besten für Gruppen mit bis zu 50.000 Benutzern, kann aber auch mit größeren Gruppen verwendet werden.

- **Verwenden Sie [die Batchrichtlinienzuweisung,](assign-policies.md#assign-a-policy-to-a-batch-of-users) um benutzern eine Besprechungsrichtlinie direkt in Massen zuzuordnen.** Sie können bis zu 5.000 Benutzern gleichzeitig eine Richtlinie zuweisen. Bei mehr als 5.000 Benutzern können Sie mehrere Batches übermitteln. Bei dieser Methode müssen Sie, wenn Sie neue Benutzer haben, die Batchzuweisung erneut ausführen, um den neuen Benutzern die Richtlinie zuzuordnen.

Denken Sie daran, Teams Benutzer automatisch die globale (organisationsweite Standard)-Richtlinie für einen Teams-Richtlinientyp erhalten, es sei denn, Sie erstellen und weisen eine benutzerdefinierte Richtlinie zu. Da die Schüler/Studenten häufig die größte Gruppe von Benutzern sind und häufig die restriktivsten Einstellungen erhalten, wird folgendes empfohlen:

- Erstellen Sie eine benutzerdefinierte Richtlinie, die grundlegende Funktionen wie private Chats und Besprechungsplanung zulässt, und weisen Sie die Richtlinie Ihren Mitarbeitern und Lehrkräften zu.
- Weisen Sie Ihren Mitarbeitern und Lehrkräften die benutzerdefinierte Richtlinie zu.
- Bearbeiten Sie die globale (organisationsweite Standardrichtlinie), und wenden Sie sie an, um Funktionen für Schüler/Studierende einzuschränken.

Denken Sie daran, dass die Globale Richtlinie für alle Benutzer in Ihrer Schule gilt, bis Sie eine benutzerdefinierte Richtlinie erstellen und sie Ihren Mitarbeitern und Lehrkräften zuweisen.

In diesem Lernprogramm erhalten die Kursteilnehmer die Globale Besprechungsrichtlinie, und wir weisen Mitarbeitern und Lehrkräften eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zu. Wir gehen davon aus, dass Sie die globale [](policy-packages-edu.md) Richtlinie bearbeitet haben, um Besprechungseinstellungen für Schüler/Studierende zu anpassen, und eine benutzerdefinierte Richtlinie erstellt haben, die die Besprechungserfahrung für Mitarbeiter und Lehrkräfte definiert.

![Screenshot der Seite "Besprechungsrichtlinien" im Teams Admin Center](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Führen Sie die folgenden Schritte aus, um eine Sicherheitsgruppe für Ihre Mitarbeiter und Lehrkräfte zu erstellen, und weisen Sie dieser Sicherheitsgruppe dann eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zu.

### <a name="before-you-get-started"></a>Bevor Sie beginnen

> [!IMPORTANT]
> Wenn Sie einer Gruppe eine Richtlinie zuweisen, wird die Richtlinienzuweisung gemäß den Rangfolgeregeln an Mitglieder der Gruppe weiterverfolgen. Wenn einem Benutzer beispielsweise direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batchzuordnung), hat diese Richtlinie Vorrang vor einer Richtlinie, die von einer Gruppe geerbt wird. Dies bedeutet auch, dass Sie, wenn ein Benutzer über eine Besprechungsrichtlinie verfügt, die ihm direkt zugewiesen wurde, diese Besprechungsrichtlinie vom Benutzer entfernen müssen, bevor er eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben kann.

Bevor Sie beginnen, ist es wichtig, Rangfolgeregeln [und](assign-policies.md#precedence-rules) Rangfolge von [Gruppenzuweisungen zu verstehen.](assign-policies.md#group-assignment-ranking) Lesen und verstehen Sie die Konzepte in Wichtige Informationen zur Richtlinienzuweisung **[zu Gruppen.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**

Sie müssen alle diese Schritte ausführen, damit Ihre Mitarbeiter und Lehrkräfte eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können.

1. [Erstellen Sie Sicherheitsgruppen.](#create-security-groups)
2. [Weisen Sie einer Sicherheitsgruppe eine Richtlinie zu.](#assign-a-policy-to-a-security-group)
3. [Entfernen Sie eine Richtlinie, die Benutzern direkt zugewiesen wurde.](#remove-a-policy-that-was-directly-assigned-to-users)

### <a name="create-security-groups"></a>Erstellen von Sicherheitsgruppen

Erstellen Sie zunächst eine Sicherheitsgruppe für Ihre Mitarbeiter und Lehrkräfte.

Mit [School Data Sync](/SchoolDataSync/) (SDS) können Sie auf einfache Weise Sicherheitsgruppen erstellen, [die Lehrkräfte und Schüler/Studenten](/SchoolDataSync/edu-security-groups) in Ihrer Schule haben. Wir empfehlen, SDS zum Erstellen der Sicherheitsgruppen zu verwenden, die Sie zum Verwalten von Richtlinien für Ihre Schule benötigen.

Wenn Sie sdS nicht in Ihrer Umgebung bereitstellen können, verwenden Sie dieses [PowerShell-Skript,](scripts/powershell-script-security-groups-edu.md) um zwei Sicherheitsgruppen zu erstellen: eine für alle Mitarbeiter und Lehrkräfte, denen eine Lehrpersonallizenz zugewiesen ist, und eine weitere für alle Schüler/Studenten, denen eine Student-Lizenz zugewiesen ist. Sie müssen dieses Skript routinemäßig ausführen, um die Gruppen aktuell und auf dem neuesten Stand zu halten.

### <a name="assign-a-policy-to-a-security-group"></a>Zuweisen einer Richtlinie zu einer Sicherheitsgruppe

#### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung an Gruppen über das Microsoft Teams Admin Teams Center nur für Anrufrichtlinien, Parkrichtlinien für Teams-Anrufe, Teams-Richtlinie, Teams-Richtlinie für Liveereignisse, Teams-Besprechungsrichtlinien und Teams-Messaging-Richtlinie verfügbar. Verwenden Sie PowerShell für andere Richtlinientypen.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Besprechungen** > **Besprechungsrichtlinien**.
2. Wählen Sie die **Registerkarte Gruppenrichtlinienzuordnung** aus.
3. Wählen **Sie Gruppe hinzufügen** aus, und gehen Sie dann im Bereich Richtlinie **zu** Gruppe zuweisen wie folgt vor:

    ![Screenshot des Bereichs "Einstellungen bearbeiten" mit Besprechungsrichtlinie](media/batch-group-policy-assignment-edu-group.png)
    1. Suchen Sie **im Feld Gruppe auswählen** nach der Sicherheitsgruppe, die Ihre Mitarbeiter und Lehrkräfte enthält, und fügen Sie sie hinzu.
    2. Geben Sie **im Feld Rang** auswählen den Wert **1 ein.**
    3. Wählen Sie **im Feld Richtlinie auswählen** die Option **EducatorMeetingPolicy aus.**
    4. Wählen Sie **Übernehmen aus.**

Um eine Gruppenrichtlinienzuweisung zu  entfernen, wählen Sie auf der Richtlinienseite auf der Registerkarte Gruppenrichtlinienzuweisung die Gruppenzuweisung und dann Entfernen **aus.**

Um die Bewertung einer Gruppenzuordnung zu ändern, müssen Sie zuerst die Gruppenrichtlinienzuweisung entfernen. Führen Sie dann die vorstehenden Schritte aus, um die Richtlinie einer Gruppe zuzuordnen.

#### <a name="using-powershell"></a>Verwendung von PowerShell

> [!NOTE]
> Derzeit ist die Richtlinienzuweisung an Gruppen mithilfe von PowerShell nicht für alle Teams Richtlinientypen verfügbar. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment.](/powershell/module/teams/new-csgrouppolicyassignment)

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie Folgendes aus, um [das Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist). Vergewissern Sie sich, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um Teams Verbindung herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

##### <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Führen Sie Folgendes aus, um der Sicherheitsgruppe, die Ihre Mitarbeiter und Lehrkräfte enthält, die Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuordnen, und legen Sie die Aufgabenrangfolge auf 1 fest. Sie können eine Sicherheitsgruppe mithilfe der Objekt-ID, der SIP-Adresse (Session Initiation Protocol) oder der E-Mail-Adresse angeben. In diesem Beispiel verwenden wir eine E-Mail-Adresse (staff-faculty@contoso.com).

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Entfernen einer Richtlinie, die Benutzern direkt zugewiesen wurde

Denken Sie daran: Wenn einem Benutzer eine Richtlinie direkt zugewiesen wurde (entweder einzeln oder über eine Batchzuweisung), hat diese Richtlinie Vorrang. Dies bedeutet: Wenn ein Benutzer über eine Besprechungsrichtlinie verfügt, die ihm direkt zugewiesen wurde, müssen Sie diese Besprechungsrichtlinie vom Benutzer entfernen, bevor er eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben kann.

Weitere Informationen finden Sie unter Wichtige Informationen zur [Richtlinienzuweisung zu Gruppen.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)

Führen Sie die folgenden Schritte aus, um die Besprechungsrichtlinie zu entfernen, die Ihren Mitarbeitern und Lehrkräften direkt zugewiesen wurde.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie Folgendes aus, um [das Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist). Vergewissern Sie sich, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um Teams Verbindung herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit den gleichen Administratoranmeldeinformationen an, die Sie für die Verbindung zu Azure AD verwendet haben.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Eine Richtlinie, die Benutzern direkt zugewiesen wurde, wieder zuweisen

Führen Sie Folgendes aus, um eine Besprechungsrichtlinie von Benutzern zu entfernen, denen diese Richtlinie direkt zugewiesen wurde. Sie können Benutzer nach E-Mail-Adresse oder Objekt-ID angeben.

In diesem Beispiel wird die Besprechungsrichtlinie von Benutzern entfernt, die durch ihre E-Mail-Adresse angegeben sind.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

In diesem Beispiel wird die Besprechungsrichtlinie aus der Liste der Benutzer in einer Textdatei namens "user_ids.txt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Erhalten von Richtlinienzuweisungen für eine Gruppe

Führen Sie die folgenden Schritte aus, um alle Richtlinien zu sehen, die einer bestimmten Sicherheitsgruppe zugewiesen sind. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgelistet werden, auch wenn deren SIP-Adresse oder E-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Erhalten der Richtlinien, die einem Benutzer zugewiesen werden

Führen Sie die folgenden Schritte aus, um alle Richtlinien zu sehen, die einem bestimmten Benutzer zugewiesen sind. Das folgende Beispiel zeigt, wie Sie die Richtlinien erhalten, die einem bestimmten reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einer Gruppe von Benutzern

Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Lehrkräften eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy in Massen direkt zuzuordnen.

### <a name="using-powershell"></a>Verwendung von PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Verbinden zum Azure AD PowerShell für Graph-Modul und zum Teams PowerShell-Modul

Bevor Sie die in diesem Artikel erläuterten Schritte ausführen, müssen Sie das Azure AD PowerShell für Graph-Modul (zum Identifizieren von Benutzern nach den ihnen zugewiesenen Lizenzen) und das Microsoft Teams PowerShell-Modul (zum Zuweisen der Richtlinien zu diesen Benutzern) installieren und eine Verbindung damit herstellen.

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph Modul

Öffnen Sie eine Eingabeaufforderung Windows PowerShell mit erhöhten Rechten (führen Sie Windows PowerShell als Administrator aus), und führen Sie dann die folgenden Schritte aus, um das Azure Active Directory PowerShell für Graph zu installieren.

```powershell
Install-Module -Name AzureAD
```

Führen Sie Folgendes aus, um eine Verbindung mit Azure AD herzustellen.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

Weitere Informationen finden Sie [unter Verbinden des Moduls Azure Active Directory PowerShell für Graph Modul.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie das folgende Skript aus, [um Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist). Vergewissern Sie sich, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um Teams Verbindung herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit den gleichen Administratoranmeldeinformationen an, die Sie für die Verbindung zu Azure AD verwendet haben.

#### <a name="identify-your-users"></a>Identifizieren der Benutzer

Führen Sie zunächst die folgenden Schritte aus, um Ihre Mitarbeiter und Lehrkräfte nach Lizenztyp zu identifizieren. Dies teilt Ihnen mit, welche SKUs in Ihrer Organisation verwendet werden. Sie können dann Mitarbeiter und Lehrkräfte identifizieren, denen eine Lehrpersonal-SKU zugewiesen ist.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Gibt zurück:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

In diesem Beispiel zeigt die Ausgabe, dass die Lizenz-SkuId für Lehrpersonal "e97c048c-37a4-45fb-ab50-922fbf07a370" ist.

> [!NOTE]
> Eine Liste der Education-SKUs und SKU-IDs finden Sie unter [Education-SKU -Referenz.](sku-reference-edu.md)

Als Nächstes führen wir die folgenden Schritte aus, um die Benutzer zu identifizieren, die über diese Lizenz verfügen, und sie alle zusammen zu sammeln.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Massen zuweisen einer Richtlinie

Jetzt weisen wir den Benutzern die entsprechenden Richtlinien in Massen zu. Die maximale Anzahl von Benutzern, denen Sie Richtlinien zuweisen oder aktualisieren können, beträgt 5.000 gleichzeitig. Wenn Sie beispielsweise über mehr als 5.000 Mitarbeiter und Lehrkräfte verfügen, müssen Sie mehrere Batches übermitteln.

Führen Sie Folgendes aus, um Ihren Mitarbeitern und Lehrkräften eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuordnen.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Wenn Sie einen anderen Richtlinientyp (z. B. TeamsMessagingPolicy) in Massen zuweisen möchten, müssen Sie zu der Richtlinie, die Sie zuweisen, und dem ```PolicyType``` ```PolicyName``` Richtliniennamen wechseln.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Anzeigen des Status einer Massenzuweisung

Jede Massenzuweisung gibt eine Vorgangs-ID zurück, mit der Sie den Fortschritt der Richtlinienzuweisungen nachverfolgen oder mögliche Fehler identifizieren können. Führen Sie z. B. Folgendes aus:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Führen Sie die folgenden Schritte aus, um den Aufgabenstatus der einzelnen Benutzer im Batchvorgang zu sehen. Details zu jedem Benutzer sind in der ```UserState``` -Eigenschaft zu finden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Massen zuweisen einer Richtlinie bei mehr als 5.000 Benutzern

Führen Sie zunächst die folgenden Schritte aus, um zu sehen, über wie viele Mitarbeiter und Lehrkräfte Sie verfügen:

```powershell
$faculty.count
```

Anstatt die gesamte Liste der Benutzer-IDs anzugeben, führen Sie die folgenden Schritte aus, um die ersten 5.000, dann die nächsten 5.000 und so weiter anzugeben.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Sie können den Bereich der Benutzer-IDs ändern, bis Sie die vollständige Liste der Benutzer erreicht haben. Geben Sie z. B. für den ersten Stapel ein, verwenden Sie für den zweiten Batch, für den dritten Batch ```$faculty[0..4999``` ```$faculty[5000..9999``` eingeben und so ```$faculty[10000..14999``` weiter.

#### <a name="get-the-policies-assigned-to-a-user"></a>Erhalten der Richtlinien, die einem Benutzer zugewiesen werden

Führen Sie die folgenden Schritte aus, um alle Richtlinien zu sehen, die einem bestimmten Benutzer zugewiesen sind. Das folgende Beispiel zeigt, wie Sie die Richtlinien erhalten, die einem bestimmten hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Häufig gestellte Fragen

**Ich bin mit PowerShell für Teams. Wo kann ich mehr erfahren?**

Eine Übersicht über die Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht Teams PowerShell.](teams-powershell-overview.md) Weitere Informationen zu den in diesem Artikel verwendeten Cmdlets finden Sie unter:

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern](assign-policies.md)
- [Teams-Richtlinien und Richtlinienpakete für Bildung](policy-packages-edu.md)
- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
---
title: Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule
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
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Ihrer Bildungseinrichtung Richtlinien auf der Grundlage einer Gruppenmitgliedschaft oder direkt über eine Batch Zuordnung für Remote School (teleschool, Tele Schule) zuweisen.
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616939"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Eine ausführlichere Geschichte zum Zuweisen von Richtlinien in Microsoft Teams finden Sie unter [Zuweisen von Richtlinien zu Ihren Benutzern in Teams](assign-policies.md).

## <a name="overview"></a>Übersicht

Müssen Sie Ihren Kursteilnehmern und Lehrkräften Zugriff auf verschiedene Features in Microsoft Teams gewähren? Sie können die Benutzer in Ihrer Organisation anhand des Lizenztyps schnell identifizieren und Ihnen dann die entsprechende Richtlinie zuweisen. In diesem Lernprogramm erfahren Sie, wie Sie einer Besprechungsrichtlinie große Gruppen von Benutzern in ihrer Schule zuweisen. Sie können Richtlinien mit dem Microsoft Teams Admin Center und PowerShell zuweisen, und wir werden Ihnen beide Möglichkeiten zeigen.

Sie können eine Besprechungsrichtlinie einer Sicherheitsgruppe zuweisen, in der die Benutzer Mitglied oder direkt für Benutzer sind, und zwar über eine Batch Richtlinienzuordnung. Folgende Punkte werden behandelt:

- **Verwenden Sie die [Richtlinienzuweisung für Gruppen](#assign-a-policy-to-a-group) , um einer Sicherheitsgruppe eine Besprechungsrichtlinie zuzuweisen (empfohlen)**. Mit dieser Methode können Sie eine Richtlinie basierend auf der Gruppenmitgliedschaft zuweisen. Sie können einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zuweisen. Wenn Mitglieder der Gruppe hinzugefügt oder aus ihr entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Wir empfehlen, diese Methode zu verwenden, da dadurch die Zeit für das Verwalten von Richtlinien für neue Benutzer oder die Änderung der Rollen der Benutzer verringert wird. Diese Methode eignet sich am besten für Gruppen mit bis zu 50.000 Benutzern, funktioniert aber auch mit größeren Gruppen.

- **Verwenden Sie die [Zuweisung von Stapelverarbeitungs Richtlinien](assign-policies.md#assign-a-policy-to-a-batch-of-users) , um Benutzern eine Besprechungsrichtlinie in einem Massenvorgang direkt zuzuweisen**. Sie können eine Richtlinie für bis zu 5.000-Benutzer gleichzeitig zuweisen. Wenn Sie über mehr als 5.000 Benutzer verfügen, können Sie mehrere Batches übermitteln. Bei dieser Methode müssen Sie bei neuen Benutzern die Batch Zuordnung erneut ausführen, um die Richtlinie diesen neuen Benutzern zuzuweisen.

Beachten Sie, dass Benutzer in Teams automatisch die globale (org-Wide Standard)-Richtlinie für einen Teams-Richtlinientyp abrufen, sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen. Da die Kursteilnehmer häufig die größte Gruppe von Benutzern sind und häufig die restriktivsten Einstellungen erhalten, empfehlen wir, dass Sie die folgenden Schritte ausführen:

- Erstellen Sie eine benutzerdefinierte Richtlinie, die Kernfunktionen wie private Chats und Besprechungsplanung zulässt, und weisen Sie die Richtlinie ihren Mitarbeitern und Pädagogen zu.
- Weisen Sie die benutzerdefinierte Richtlinie ihren Mitarbeitern und Pädagogen zu.
- Bearbeiten und Anwenden der globalen (org-Wide Standard)-Richtlinie, um die Funktionen für Schüler zu beschränken.

Beachten Sie, dass die globale Richtlinie für alle Benutzer in ihrer Schule gelten soll, bis Sie eine benutzerdefinierte Richtlinie erstellt und ihren Mitarbeitern und Pädagogen zugewiesen haben.

In diesem Lernprogramm erhalten die Kursteilnehmer die globale Besprechungsrichtlinie, und wir weisen Mitarbeitern und Pädagogen eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen "EducatorMeetingPolicy" zu. Wir gehen davon aus, dass Sie die globale Richtlinie so geändert haben, dass Sie die Besprechungseinstellungen für Schüler zugeschnitten und [eine benutzerdefinierte Richtlinie erstellt](policy-packages-edu.md) , die die Besprechungs Erfahrung für Mitarbeiter und Pädagogen definiert.

![Screenshot der Seite "Besprechungsrichtlinien" im Team Admin Center](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Führen Sie die folgenden Schritte aus, um eine Sicherheitsgruppe für Ihre Mitarbeiter und Pädagogen zu erstellen und dann dieser Sicherheitsgruppe eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen.

### <a name="before-you-get-started"></a>Bevor Sie beginnen

> [!IMPORTANT]
> Wenn Sie einer Gruppe eine Richtlinie zuweisen, wird die Richtlinienzuweisung entsprechend den Rangfolgenregeln an Mitglieder der Gruppe weitergegeben. Wenn einem Benutzer beispielsweise direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batch Zuordnung), hat diese Richtlinie Vorrang vor einer Richtlinie, die von einer Gruppe geerbt wurde. Das bedeutet auch, dass Sie, wenn ein Benutzer über eine Besprechungsrichtlinie verfügt, die Ihnen direkt zugewiesen wurde, diese Besprechungsrichtlinie vom Benutzer entfernen müssen, bevor Sie eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können.

Bevor Sie beginnen, ist es wichtig, die [Rangfolge von Prioritätsregeln](assign-policies.md#precedence-rules) und die Rangfolge von [Gruppenaufgaben](assign-policies.md#group-assignment-ranking)zu verstehen. **Stellen Sie sicher, dass Sie die Konzepte lesen und verstehen, die [Sie über die Richtlinienzuweisung zu Gruppen wissen müssen](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.

Sie müssen alle diese Schritte ausführen, damit Ihre Mitarbeiter und Pädagogen eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können.

1. [Erstellen von Sicherheitsgruppen](#create-security-groups)
2. [Zuweisen einer Richtlinie zu einer Sicherheitsgruppe](#assign-a-policy-to-a-security-group)
3. [Entfernen Sie eine Richtlinie, die Benutzern direkt zugewiesen wurde](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>Erstellen von Sicherheitsgruppen

Erstellen Sie zunächst eine Sicherheitsgruppe für Ihre Mitarbeiter und Erzieher.

Mit [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) können Sie auf [einfache Weise Sicherheitsgruppen Pädagogen und Schüler](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in ihrer Schule erstellen. Wir empfehlen, SDS zum Erstellen der Sicherheitsgruppen zu verwenden, die Sie zum Verwalten von Richtlinien für Ihre Schule benötigen.

Wenn Sie SDS in Ihrer Umgebung nicht bereitstellen können, verwenden Sie [dieses PowerShell-Skript](scripts/powershell-script-security-groups-edu.md) , um zwei Sicherheitsgruppen zu erstellen: eine für alle Mitarbeiter und Pädagogen, denen eine Fakultäts Lizenz zugewiesen ist, und eine andere für alle Schüler, denen eine Schülerlizenz zugewiesen wurde. Sie müssen dieses Skript routinemäßig ausführen, um die Gruppen frisch und auf dem neuesten Stand zu halten.

### <a name="assign-a-policy-to-a-security-group"></a>Zuweisen einer Richtlinie zu einer Sicherheitsgruppe

#### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

> [!NOTE]
> Derzeit steht die Richtlinienzuweisung für Gruppen, die das Microsoft Teams Admin Center verwenden, nur für Teams-Anruf Richtlinien, Teams-Anruf Park Richtlinien, Teams-Richtlinien, Teams-Live-Ereignisrichtlinien, Teams-Besprechungsrichtlinien und Teams-Messagingrichtlinien zur Verfügung. Verwenden Sie für andere Richtlinientypen PowerShell.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu   >  **Besprechungsrichtlinien** für Besprechungen.
2. Wählen Sie die Registerkarte **Gruppenrichtlinien Zuweisung** aus.
3. Wählen Sie **Gruppe hinzufügen** aus, und führen Sie dann im Bereich **Richtlinie zu Gruppe zuweisen** die folgenden Aktionen aus:

    ![Screenshot des Bereichs "Einstellungen bearbeiten" mit den Besprechungsrichtlinien](media/batch-group-policy-assignment-edu-group.png)
    1. Suchen Sie im Feld **Gruppe auswählen** nach der Sicherheitsgruppe, die Ihre Mitarbeiter und Pädagogen enthält, und fügen Sie Sie hinzu.
    2. Geben Sie im Feld **Rang auswählen** den Wert **1** ein.
    3. Wählen Sie im Feld **Richtlinie auswählen** die Option **EducatorMeetingPolicy** aus.
    4. Wählen Sie über **nehmen** aus.

Wenn Sie eine Gruppenrichtlinien Zuordnung entfernen möchten, wählen Sie auf der Registerkarte **Gruppenrichtlinien Zuweisung** auf der Seite Richtlinie die Gruppenzuordnung aus, und wählen Sie dann **Entfernen** aus.

Wenn Sie die Rangfolge einer Gruppenaufgabe ändern möchten, müssen Sie zuerst die Gruppenrichtlinien Zuweisung entfernen. Führen Sie dann die obigen Schritte aus, um die Richtlinie einer Gruppe zuzuweisen.

#### <a name="using-powershell"></a>Verwendung von PowerShell

> [!NOTE]
> Derzeit steht die Richtlinienzuweisung zu Gruppen mit PowerShell nicht für alle Teamrichtlinien Typen zur Verfügung. Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie die folgenden Schritte aus, um das [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist). Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

##### <a name="assign-a-policy-to-a-group"></a>Zuweisen einer Richtlinie zu einer Gruppe

Führen Sie die folgenden Schritte aus, um der Sicherheitsgruppe, die Ihre Mitarbeiter und Pädagogen enthält, die Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen und die Zuordnungs Rangfolge auf 1 festzulegen. Sie können eine Sicherheitsgruppe mithilfe der Objekt-ID, der SIP-Adresse (Session Initiation Protocol) oder der e-Mail-Adresse angeben. In diesem Beispiel wird eine e-Mail-Adresse (Staff-Faculty@contoso.com) verwendet.

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>Entfernen einer Richtlinie, die Benutzern direkt zugewiesen wurde

Beachten Sie, dass die Richtlinie Vorrang hat, wenn einem Benutzer direkt eine Richtlinie zugewiesen wurde (entweder einzeln oder über eine Batch Aufgabe). Das bedeutet, dass Sie die Besprechungsrichtlinie des Benutzers entfernen müssen, bevor Sie eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können, wenn ein Benutzer über eine Besprechungsrichtlinie verfügt, die Ihnen direkt zugewiesen wurde.

Weitere Informationen finden Sie unter [was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).

Führen Sie die folgenden Schritte aus, um die Besprechungsrichtlinie zu entfernen, die ihren Mitarbeitern und Pädagogen direkt zugewiesen wurde.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie die folgenden Schritte aus, um das [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist). Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung mit Azure AD verwendet haben.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>Aufheben der Zuweisung einer Richtlinie, die Benutzern direkt zugewiesen wurde

Führen Sie die folgenden Schritte aus, um eine Besprechungsrichtlinie von Benutzern zu entfernen, denen diese Richtlinie direkt zugewiesen wurde. Sie können Benutzer nach e-Mail-Adresse oder Objekt-ID angeben.

In diesem Beispiel werden die Besprechungsrichtlinien von Benutzern entfernt, die durch Ihre e-Mail-Adresse angegeben werden.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

In diesem Beispiel wird die Besprechungsrichtlinie aus der Liste der Benutzer in einer Textdatei mit dem Namen user_ids.txt entfernt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>Abrufen von Richtlinienzuweisungen für eine Gruppe

Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einer bestimmten Sicherheitsgruppe zugewiesen sind. Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn die SIP-Adresse oder e-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>Abrufen der Richtlinien, die einem Benutzer zugewiesen sind

Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einem bestimmten Benutzer zugewiesen sind. Im folgenden Beispiel wird gezeigt, wie Sie die Richtlinien abrufen, die Reda@contoso.com zugewiesen sind.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>Zuweisen einer Richtlinie zu einem Benutzer Batch

Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Pädagogen eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy direkt zuzuweisen.

### <a name="using-powershell"></a>Verwendung von PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul und dem Teams PowerShell-Modul

Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, müssen Sie das Azure AD PowerShell für Graph-Modul installieren und eine Verbindung herstellen (um die Benutzer anhand der zugewiesenen Lizenzen zu identifizieren) und das Microsoft Teams PowerShell-Modul (um die Richtlinien diesen Benutzern zuzuweisen).

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul

Öffnen Sie eine erweiterte Windows PowerShell-Eingabeaufforderung (Windows PowerShell als Administrator ausführen), und führen Sie dann die folgenden Schritte aus, um das Azure Active Directory PowerShell für Graph-Modul zu installieren.

```powershell
Install-Module -Name AzureAD
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.

```powershell
Connect-AzureAD
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie die folgenden Schritte aus, um das [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist). Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```

Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung mit Azure AD verwendet haben.

#### <a name="identify-your-users"></a>Identifizieren der Benutzer

Führen Sie zunächst die folgenden Schritte aus, um Ihre Mitarbeiter und Pädagogen anhand des Lizenztyps zu identifizieren. Hier erfahren Sie, welche SKUs in Ihrer Organisation verwendet werden. Sie können dann Mitarbeiter und Pädagogen identifizieren, denen eine Fakultäts-SKU zugewiesen ist.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Was zurückgegeben wird:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

In diesem Beispiel zeigt die Ausgabe, dass die Fakultäts Lizenz SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" ist.

> [!NOTE]
> Eine Liste der Education-SKUs und SKU-IDs finden Sie unter [Education-SKU-Referenz](sku-reference-edu.md).

Als nächstes führen wir die folgenden Schritte aus, um die Benutzer zu identifizieren, die über diese Lizenz verfügen, und Sie alle zusammen zu sammeln.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>Zuweisen einer Richtlinie in Massen

Nun weisen wir Benutzern die entsprechenden Richtlinien in loser Schüttung zu. Die maximale Anzahl von Benutzern, für die Sie Richtlinien zuweisen oder aktualisieren können, ist 5.000. Wenn Sie beispielsweise über mehr als 5.000 Mitarbeiter und Pädagogen verfügen, müssen Sie mehrere Batches übermitteln.

Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Pädagogen eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Wenn Sie einen anderen Richtlinientyp in Massen zuweisen möchten, wie TeamsMessagingPolicy, müssen Sie ```PolicyType``` zu der Richtlinie, die Sie zuweisen, und ```PolicyName``` dem Richtliniennamen wechseln.

#### <a name="get-the-status-of-a-bulk-assignment"></a>Abrufen des Status einer Massen Zuordnung

Jede Massenaufgabe gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt der Richtlinienzuweisungen zu verfolgen oder eventuell auftretende Fehler zu identifizieren. Führen Sie beispielsweise die folgenden Aktionen aus:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Führen Sie die folgenden Schritte aus, um den Zuordnungsstatus jedes Benutzers im Batchvorgang anzuzeigen. Details zu den einzelnen Benutzern sind in der Eigenschaft zu finden ```UserState``` .

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>Zuweisen einer Richtlinie in loser Schüttung, wenn mehr als 5.000-Benutzer vorhanden sind

Führen Sie zunächst die folgenden Schritte aus, um zu sehen, wie viele Mitarbeiter und Pädagogen Sie haben:

```powershell
$faculty.count
```

Anstatt die vollständige Liste der Benutzer-IDs bereitzustellen, führen Sie die folgenden Schritte aus, um die erste 5.000 und dann die nächste 5.000 usw. anzugeben.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Sie können den Bereich der Benutzer-IDs ändern, bis Sie die vollständige Liste der Benutzer erreichen. Geben Sie beispielsweise ```$faculty[0..4999``` für den ersten Batch ein, verwenden Sie ```$faculty[5000..9999``` für den zweiten Batch, geben Sie ```$faculty[10000..14999``` für den dritten Batch ein, und so weiter.

#### <a name="get-the-policies-assigned-to-a-user"></a>Abrufen der Richtlinien, die einem Benutzer zugewiesen sind

Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einem bestimmten Benutzer zugewiesen sind. Im folgenden Beispiel wird gezeigt, wie Sie die Richtlinien abrufen, die Hannah@contoso.com zugewiesen sind.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Häufig gestellte Fragen

**Ich bin mit PowerShell für Teams nicht vertraut. Wo finde ich weitere Informationen?**

Eine Übersicht über die Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md). Weitere Informationen zu den in diesem Artikel verwendeten Cmdlets finden Sie unter:

- [Neu – CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [Neu – CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Ihren Benutzern](assign-policies.md)
- [Teamrichtlinien und Richtlinien Pakete für Bildungseinrichtungen](policy-packages-edu.md)
- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)

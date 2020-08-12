---
title: Entfernen der RestrictedAnonymousAccess Teams-Besprechungsrichtlinie für Benutzer
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Hier erfahren Sie, wie Sie die RestrictedAnonymousAccess Teams-Besprechungsrichtlinie von Benutzern in Ihrer Organisation entfernen.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640983"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Entfernen der RestrictedAnonymousAccess Teams-Besprechungsrichtlinie für Benutzer

[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant werden. 

Teams enthält eine integrierte Richtlinie mit dem Namen "RestrictedAnonymousAccess", die vordefinierte Einstellungen enthält, die das Einschränken von anonymen Benutzern vom Starten einer Besprechung beinhalten. (Anonyme Benutzer sind Benutzer, die nicht authentifiziert wurden.) Die vordefinierten Einstellungen in der Besprechungsrichtlinie können von Administratoren nicht bearbeitet oder geändert werden.

In diesem Artikel wird gezeigt, wie Sie die RestrictedAnonymousAccess-Besprechungsrichtlinie mithilfe von PowerShell von Benutzern entfernen, denen diese Richtlinie zugewiesen ist. Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Bevor Sie beginnen

Installieren und Herstellen einer Verbindung mit dem [Skype for Business PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366) Schritt-für-Schritt-Anleitungen finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Abrufen der Besprechungsrichtlinien Zuweisungen für Teams für Ihre Organisation

Führen Sie die folgenden Schritte aus, um die Team Besprechungsrichtlinien Zuweisungen für Ihre Organisation abzurufen.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

In diesem Beispiel wird die folgende Ausgabe zurückgegeben, die zeigt, dass zwei Benutzern die RestrictedAnonymousAccess-Besprechungsrichtlinie zugewiesen ist.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Aufheben der Zuweisung der RestrictedAnonymous-Besprechungsrichtlinie für Benutzer

Wenn Sie die RestrictedAnonymous-Besprechungsrichtlinie von Benutzern entfernen möchten, können Sie das [Grant-CSTeamsMeetingPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet verwenden, wenn Sie eine geringe Anzahl von Benutzern haben (beispielsweise weniger als 100-Benutzer). Wenn Sie eine große Anzahl von Benutzern (beispielsweise mehr als 100 Benutzer) haben, ist es effizienter, das Cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) zum Übermitteln eines Batchvorgangs zu verwenden.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Verwenden des Cmdlets "Grant-CsTeamsMeeting-Richtlinie"

Führen Sie die folgenden Schritte aus, um die RestrictedAnonymous-Besprechungsrichtlinie von Benutzern zu entfernen.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Verwenden des Cmdlets "New-CsBatchPolicyAssignmentOperation"

Bei der [Batch Richtlinienzuweisung](assign-policies.md#assign-a-policy-to-a-batch-of-users)beträgt die maximale Anzahl von Benutzern, für die Sie Richtlinien entfernen oder aktualisieren können, 5.000 gleichzeitig. Wenn Sie beispielsweise über mehr als 5.000 Benutzer verfügen, müssen Sie mehrere Batches übermitteln. Um optimale Ergebnisse zu erzielen, sollten Sie nicht mehrere Batches gleichzeitig übermitteln. Lassen Sie die Verarbeitung von Batches durchführen, bevor Sie weitere Stapel senden.

> [!NOTE]
> Das Cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) befindet sich im PowerShell-Modul von Teams. Bevor Sie diese Schritte ausführen, installieren und verbinden Sie sich mit dem [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Schritt-für-Schritt-Anleitungen finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).

Führen Sie die folgenden Befehle aus, um die RestrictedAnonymousAccess-Besprechungsrichtlinie aus einem Batch von Benutzern zu entfernen.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Abrufen des Status der Batch Zuordnung

Jede Batch Zuordnung gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt und den Status der Aufgaben zu verfolgen und eventuell auftretende Fehler zu identifizieren. Führen Sie beispielsweise die folgenden Aktionen aus:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Stellen Sie sicher, dass **ErrorCount** **0** (null) und **OverallStatus** **abgeschlossen**ist.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)

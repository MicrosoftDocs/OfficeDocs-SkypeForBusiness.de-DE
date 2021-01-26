---
title: Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie, wie Sie die Besprechungsrichtlinie "RestrictedAnonymousAccess Teams" von Benutzern in Ihrer Organisation entfernen.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806255"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern

[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um die Features zu steuern, die besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant werden. 

Teams enthält eine integrierte Richtlinie namens RestrictedAnonymousAccess, die vordefinierte Einstellungen enthält, die das Starten einer Besprechung durch anonyme Benutzer einschränken. (Anonyme Benutzer sind Benutzer, die nicht authentifiziert wurden.) Die vordefinierten Einstellungen in der Besprechungsrichtlinie können von Administratoren nicht bearbeitet oder geändert werden.

In diesem Artikel wird erläutert, wie Sie mithilfe von PowerShell die Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern entfernen, denen diese Richtlinie zugewiesen ist. Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie in [der Übersicht über Teams PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Bevor Sie beginnen

Installieren Und Herstellen einer Verbindung mit [dem Skype for Business PowerShell-Modul.](https://www.microsoft.com/download/details.aspx?id=39366) Eine schrittweise Anleitung finden Sie unter ["Installieren von Microsoft Teams PowerShell".](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Erhalten der Teams-Besprechungsrichtlinienzuweisungen für Ihre Organisation

Führen Sie die folgenden Schritte aus, um die Besprechungsrichtlinienzuweisungen für Ihre Organisation zu erhalten.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

In diesem Beispiel wird die folgende Ausgabe zurückgegeben, die zeigt, dass zwei Benutzern die Besprechungsrichtlinie "RestrictedAnonymousAccess" zugewiesen wurde.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Zuweisen der Besprechungsrichtlinie "RestrictedAnonymous" für Benutzer

Wenn Sie die Besprechungsrichtlinie "RestrictedAnonymous" von Benutzern entfernen möchten, können Sie das Cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) verwenden, wenn Sie über eine kleine Anzahl von Benutzern verfügen (z. B. weniger als 100 Benutzer). Wenn Sie über eine große Anzahl von Benutzern verfügen (z. B. mehr als 100 Benutzer), ist es effizienter, das  [Cmdlet "New-CsBatchPolicyAssignmentOperation"](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) zum Übermitteln eines Batchvorgangs zu verwenden.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Verwenden des Grant-CsTeamsMeeting Richtlinien-Cmdlets

Führen Sie Folgendes aus, um die Besprechungsrichtlinie "RestrictedAnonymous" von Benutzern zu entfernen.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Verwenden des New-CsBatchPolicyAssignmentOperation Cmdlets

Bei [der Batchrichtlinienzuweisung](assign-policies.md#assign-a-policy-to-a-batch-of-users)beträgt die maximale Anzahl von Benutzern, für die Sie Richtlinien entfernen oder aktualisieren können, 5.000 gleichzeitig. Wenn Sie beispielsweise mehr als 5.000 Benutzer haben, müssen Sie mehrere Batches übermitteln. Um optimale Ergebnisse zu erzielen, übermitteln Sie nicht mehrere Batches gleichzeitig. Lassen Sie zu, dass Batches die Verarbeitung abschließen, bevor weitere Batches übermittelt werden.

> [!NOTE]
> Das [Cmdlet "New-CsBatchPolicyAssignmentOperation"](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) befindet sich im Teams PowerShell-Modul. Bevor Sie diese Schritte ausführen, installieren Sie das Teams PowerShell-Modul, und stellen [Sie eine Verbindung mit ihm herzustellen.](https://www.powershellgallery.com/packages/MicrosoftTeams) Eine schrittweise Anleitung finden Sie unter ["Installieren von Microsoft Teams PowerShell".](teams-powershell-install.md)

Führen Sie die folgenden Befehle aus, um die Besprechungsrichtlinie "RestrictedAnonymousAccess" aus einem Stapel von Benutzern zu entfernen.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Den Status der Batchzuordnung erhalten

Jede Batchzuordnung gibt eine Vorgangs-ID zurück, mit der Sie den Fortschritt und Status der Zuordnungen nachverfolgen und mögliche Fehler ermitteln können. Führen Sie z. B. Folgendes aus:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Stellen Sie sicher, **dass "ErrorCount"** **gleich 0** (Null) und **"OverallStatus"** **abgeschlossen ist.**

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Besprechungsrichtlinien in Microsoft Teams](meeting-policies-in-teams.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)

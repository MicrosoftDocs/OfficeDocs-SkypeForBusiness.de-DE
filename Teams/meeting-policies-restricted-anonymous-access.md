---
title: Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Erfahren Sie, wie Sie die RestrictedAnonymousAccess Teams-Besprechungsrichtlinie von Benutzern in Ihrer Organisation entfernen.
ms.openlocfilehash: e5ea203e52ca1b81ed7ce37f31c9f8cb5900c131
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564103"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern

[Besprechungsrichtlinien](meeting-policies-overview.md) in Microsoft Teams werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant werden. 

Teams enthält eine integrierte Richtlinie namens RestrictedAnonymousAccess, die vordefinierte Einstellungen enthält, die das Einschränken anonymer Benutzer am Starten einer Besprechung einschließen. (Anonyme Benutzer sind Benutzer, die nicht authentifiziert wurden.) Die vordefinierten Einstellungen in der Besprechungsrichtlinie können von Administratoren nicht bearbeitet oder geändert werden.

In diesem Artikel wird beschrieben, wie Sie powerShell verwenden, um die RestrictedAnonymousAccess-Besprechungsrichtlinie von Benutzern zu entfernen, denen diese Richtlinie zugewiesen ist. Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie in der [Übersicht über Teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Bevor Sie beginnen

Installieren Sie das [Skype for Business PowerShell-Modul](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell), und stellen Sie eine Verbindung mit diesem her. Eine schrittweise Anleitung finden [Sie unter Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Abrufen der Teams-Besprechungsrichtlinienzuweisungen für Ihre Organisation

Führen Sie die folgenden Schritte aus, um die Teams-Besprechungsrichtlinienzuweisungen für Ihre Organisation abzurufen.

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

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Aufheben der Zuweisung der RestrictedAnonymous-Besprechungsrichtlinie von Benutzern

Um die RestrictedAnonymous-Besprechungsrichtlinie von Benutzern zu entfernen, können Sie das Cmdlet [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) verwenden, wenn Sie eine kleine Anzahl von Benutzern haben (z. B. weniger als 100 Benutzer). Wenn Sie über eine große Anzahl von Benutzern verfügen (z. B. mehr als 100 Benutzer), ist es effizienter, das Cmdlet  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) zum Senden eines Batchvorgangs zu verwenden.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Verwenden des Grant-CsTeamsMeeting-Richtlinien-Cmdlets

Führen Sie die folgenden Schritte aus, um die RestrictedAnonymous-Besprechungsrichtlinie von Benutzern zu entfernen.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Verwenden des cmdlets New-CsBatchPolicyAssignmentOperation

Bei [der Batchrichtlinienzuweisung](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users) beträgt die maximale Anzahl von Benutzern, für die Sie Richtlinien entfernen oder aktualisieren können, jeweils 5.000. Wenn Sie beispielsweise mehr als 5.000 Benutzer haben, müssen Sie mehrere Batches übermitteln. Senden Sie nicht mehrere Batches gleichzeitig, um optimale Ergebnisse zu erzielen. Zulassen, dass Batches die Verarbeitung abschließen, bevor weitere Batches gesendet werden.

> [!NOTE]
> Das Cmdlet ["New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) " befindet sich im Teams PowerShell-Modul. Bevor Sie diese Schritte ausführen, installieren Sie das [Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams), und stellen Sie eine Verbindung mit diesem her. Eine schrittweise Anleitung finden [Sie unter Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).

Führen Sie die folgenden Befehle aus, um die RestrictedAnonymousAccess-Besprechungsrichtlinie aus einer Gruppe von Benutzern zu entfernen.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Abrufen des Status der Batchzuordnung

Jede Batchzuordnung gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt und Status der Zuordnungen nachzuverfolgen und mögliche Fehler zu identifizieren. Führen Sie beispielsweise Folgendes aus:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Stellen Sie sicher, dass **"ErrorCount****" 0** (null) und **"OverallStatus"** **abgeschlossen** ist.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
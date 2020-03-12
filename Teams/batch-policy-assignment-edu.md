---
title: Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: Erfahren Sie, wie Sie mithilfe der Batch Richtlinienzuweisung Richtlinien für große Gruppen von Benutzern in Ihrer Bildungseinrichtung in loser Schüttung für Remote Schulen (teleschool, Tele Schule) zuweisen.
f1keywords: ''
ms.openlocfilehash: 79c36aa0e2a7a2d310756d052b8962daeaa38634
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604302"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule

Müssen Sie Ihren Kursteilnehmern und Lehrkräften Zugriff auf verschiedene Features in Microsoft Teams gewähren? Sie können die Benutzer in Ihrer Organisation anhand des Lizenztyps schnell identifizieren und Ihnen dann die entsprechende Richtlinie zuweisen. In diesem Lernprogramm erfahren Sie, wie Sie mithilfe der [Batch Richtlinienzuweisung](assign-policies.md#assign-a-policy-to-a-batch-of-users) eine Besprechungsrichtlinie Benutzern in Massen zuweisen.

Beachten Sie, dass Benutzer in Teams automatisch die globale (org-Wide Standard)-Richtlinie für einen Teams-Richtlinientyp abrufen, sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen. Da die Kursteilnehmer häufig die größte Gruppe von Benutzern sind und häufig die restriktivsten Einstellungen erhalten, empfehlen wir, dass Sie die folgenden Schritte ausführen:

- Bearbeiten und Anwenden der globalen (org-Wide Standard)-Richtlinie, um die Funktionen für Schüler zu beschränken. 
- Erstellen Sie eine benutzerdefinierte Richtlinie, die Kernfunktionen wie private Chats und Besprechungsplanung zulässt, und weisen Sie die Richtlinie ihren Mitarbeitern und Pädagogen zu.

Beachten Sie, dass die globale Richtlinie für alle Benutzer in ihrer Schule gelten soll, bis Sie eine benutzerdefinierte Richtlinie erstellt und ihren Mitarbeitern und Pädagogen zugewiesen haben.

In diesem Lernprogramm erhalten die Kursteilnehmer die globale Besprechungsrichtlinie, und wir verwenden PowerShell zum Zuweisen einer benutzerdefinierten Besprechungsrichtlinie mit dem Namen "EducatorMeetingPolicy" für Mitarbeiter und Pädagogen in Massen. Wir gehen davon aus, dass Sie die globale Richtlinie so geändert haben, dass Sie die Besprechungseinstellungen für Schüler zugeschnitten und eine benutzerdefinierte Richtlinie erstellt, die die Besprechungs Erfahrung für Mitarbeiter und Pädagogen definiert.

![Screenshot der Seite "Besprechungsrichtlinien" im Team Admin Center](media/edu-batch-policy-assignment.png)

Führen Sie die folgenden Schritte aus, um Mitarbeitern und Pädagogen massenweise eine benutzerdefinierte Besprechungsrichtlinie zuzuweisen.

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul und dem Teams PowerShell-Modul

Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, müssen Sie das Azure AD PowerShell für Graph-Modul installieren und eine Verbindung herstellen (um die Benutzer anhand der zugewiesenen Lizenzen zu identifizieren) und das Microsoft Teams PowerShell-Modul (um die Richtlinien diesen Benutzern zuzuweisen).

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul

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

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul

Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams)zu installieren. Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.

```powershell
Install-Module -Name MicrosoftTeams
```

Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.

```powershell
Connect-MicrosoftTeams
```
Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung mit Azure AD verwendet haben.

## <a name="identify-your-users"></a>Identifizieren der Benutzer

Führen Sie zunächst die folgenden Schritte aus, um Ihre Mitarbeiter und Pädagogen anhand des Lizenztyps zu identifizieren. Hier erfahren Sie, welche SKUs in Ihrer Organisation verwendet werden. Sie können dann Mitarbeiter und Pädagogen identifizieren, denen eine Fakultäts-SKU zugewiesen ist.

```powershell
Get-AzureADSubscribedSku
```

```powershell
$skus = Get-AzureADSubscribedSku
```

Was zurückgegeben wird:

```
ObjectId                                                                  SkuPartNumber      SkuId
--------                                                                  -------------      -----
ee1a846c-79e9-4bc3-9189-011ca89be890_e97c048c-37a4-45fb-ab50-022fbf07a370 M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
ee1a846c-79e9-4bc3-9189-011ca89be890_46c119d4-0379-4a9d-85e4-97c66d3f909e M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

In diesem Beispiel zeigt die Ausgabe, dass die Fakultäts Lizenz SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" ist.

> [!NOTE]
> Eine Liste der Education-SKUs und SKU-IDs finden Sie unter [Education-SKU-Referenz](sku-reference-edu.md).

Als nächstes führen wir die folgenden Schritte aus, um die Benutzer zu identifizieren, die über diese Lizenz verfügen, und Sie alle zusammen zu sammeln.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object (($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370")
```

## <a name="assign-a-policy-in-bulk"></a>Zuweisen einer Richtlinie in Massen

Nun weisen wir Benutzern die entsprechenden Richtlinien in loser Schüttung zu. Die maximale Anzahl von Benutzern, für die Sie Richtlinien zuweisen oder aktualisieren können, ist 20.000. Wenn Sie beispielsweise über mehr als 20.000 Mitarbeiter und Pädagogen verfügen, müssen Sie mehrere Batches übermitteln.

Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Pädagogen die Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Wenn Sie einen anderen Richtlinientyp in Massen zuweisen möchten, wie TeamsMessagingPolicy, müssen Sie zu ```PolicyType``` der Richtlinie, die Sie zuweisen, ```PolicyName``` und dem Richtliniennamen wechseln.

## <a name="get-the-status-of-a-bulk-assignment"></a>Abrufen des Status einer Massen Zuordnung

Jede Massenaufgabe gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt der Richtlinienzuweisungen zu verfolgen oder eventuell auftretende Fehler zu identifizieren. Führen Sie beispielsweise die folgenden Aktionen aus:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Führen Sie die folgenden Schritte aus, um den Zuordnungsstatus jedes Benutzers im Batchvorgang anzuzeigen. Details zu den einzelnen Benutzern sind in ```UserState``` der Eigenschaft zu finden.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>Zuweisen einer Richtlinie in loser Schüttung, wenn mehr als 20.000-Benutzer vorhanden sind

Führen Sie zunächst die folgenden Schritte aus, um zu sehen, wie viele Mitarbeiter und Pädagogen Sie haben:

```powershell
$faculty.count
```

Anstatt die vollständige Liste der Benutzer-IDs bereitzustellen, führen Sie die folgenden Schritte aus, um die erste 20.000 und dann die nächste 20.000 usw. anzugeben.

```powershell
Assign-CsPolicy -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identities $faculty[0..19999].ObjectId
```

Sie können den Bereich der Benutzer-IDs ändern, bis Sie die vollständige Liste der Benutzer erreichen. Geben Sie beispielsweise ```$faculty[0..19999``` für den ersten Batch ein, ```$faculty[20000..39999``` verwenden Sie für den zweiten Batch ```$faculty[40000..59999``` , geben Sie für den dritten Batch ein, und so weiter.

## <a name="get-the-policies-assigned-to-a-user"></a>Abrufen der Richtlinien, die einem Benutzer zugewiesen sind

Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einem bestimmten Benutzer zugewiesen sind. Im folgenden Beispiel wird gezeigt, wie Sie die Richtlinien abrufen, die Hannah@contoso.com zugewiesen sind.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Häufig gestellte Fragen

**Ich möchte sicherstellen, dass allen Benutzern, die Schüler, Mitarbeiter und Pädagogen sind, automatisch Lizenzen zugewiesen werden. Wie kann ich das tun?**

Das Teams-Produktteam unterstützt die Zuweisung von Richtlinien zu Sicherheitsgruppen. Zu diesem Zeitpunkt können Sie Gruppen für Ihre Schüler und Lehrer und dann die entsprechenden Richtlinien für diese Gruppen erstellen. Beachten Sie, dass explizite Benutzerzuweisungen (wie die Richtlinien, die Sie mithilfe dieses Lernprogramms zugewiesen haben) die von einer Gruppe geerbten Richtlinien außer Kraft setzen. Wenn dieses Feature unterstützt wird, erhalten Sie weitere Anweisungen dazu, wie Sie die Richtlinienzuweisung für Gruppen verwenden und Ihre Benutzer aktualisieren können, um sicherzustellen, dass Sie die geerbten Gruppenrichtlinien erhalten.

**Ich bin mit PowerShell für Teams nicht vertraut. Wo finde ich weitere Informationen?**

Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Ihren Benutzern](assign-policies.md)
- [Neu – CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
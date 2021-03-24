---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Erfahren Sie, wie Sie den Benutzerzugriff auf Teams verwalten, indem Sie Benutzern in Ihrer Organisation eine Teams-Lizenz zuweisen oder entfernen.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29cf3f6816b3c1e0b00026b1ba4ad961a6a92aa6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093539"
---
# <a name="manage-user-access-to-teams"></a>Verwalten des Benutzerzugriffs auf Microsoft Teams

Sie verwalten den Zugriff auf Teams auf Benutzerebene, indem Sie eine Microsoft Teams-Produktlizenz zuweisen oder entfernen. Mit Ausnahme der anonymen Teilnahme an Teams-Besprechungen muss jeder Benutzer in Ihrer Organisation über eine Teams-Lizenz verfügen, bevor er Teams verwenden kann. Sie können eine Teams-Lizenz für neue Benutzer zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten.

Wenn einem Benutzer standardmäßig ein Lizenzierungsplan (z. B. Microsoft 365 Enterprise E3 oder Microsoft 365 Business Premium) zugewiesen wird, wird automatisch eine Teams-Lizenz zugewiesen und der Benutzer für Teams aktiviert. Sie können Teams für einen Benutzer jederzeit deaktivieren oder aktivieren, indem Sie eine Lizenz entfernen oder zuweisen.

Verwenden Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>verwaltete Messagingrichtlinien, um zu steuern, welche Chat- und Kanalnachrichtenfeatures benutzern in Teams zur Verfügung stehen. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Nachrichtenrichtlinien für Personen in Ihrer Organisation erstellen. Weitere Informationen finden Sie unter [Verwalten von Messagingrichtlinien in Teams](messaging-policies-in-teams.md).
Sie verwalten Teams-Lizenzen im Microsoft 365 Admin Center oder mithilfe von PowerShell. Sie müssen globaler Administrator oder Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

> [!NOTE]
> Wir empfehlen, Teams für alle Benutzer zu aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen gebildet werden können. Selbst wenn Sie einen Pilot ausführen, ist es möglicherweise hilfreich, Teams für alle Benutzer aktiviert zu halten, aber nur die Kommunikation an die Pilotgruppe der Benutzer zu zielten.

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden des Microsoft 365 Admin Centers

Lizenzen auf Benutzerebene von Teams werden direkt über die Benutzerverwaltungsschnittstellen des Microsoft 365 Admin Center verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten. 

> [!IMPORTANT]
> Der Administrator muss über globale Administrator- oder Benutzerverwaltungsadministratorberechtigungen verfügen, um Microsoft Teams-Lizenzen verwalten zu können.
Verwenden Sie das Microsoft 365 Admin Center, um Teams-Lizenzen für einzelne Benutzer oder kleine Benutzergruppen gleichzeitig zu verwalten. Sie können Teams-Lizenzen auf der Seite **Lizenzen** (für bis zu 20 Benutzer zurzeit) oder auf der Seite **Aktive Benutzer** verwalten. Die methode, die Sie auswählen, hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer verwalten oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Wenn Sie Teams-Lizenzen für eine große Anzahl von Benutzern verwalten müssen, z. B. Hunderte oder Tausende von Benutzern, verwenden Sie [PowerShell](#using-powershell) oder gruppenbasierte Lizenzierung [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Zuweisen einer Teams-Lizenz

Die Schritte unterscheiden sich je nachdem, ob Sie die Seite **Lizenzen** oder die Seite **Aktive Benutzer** verwenden.  Schrittweise Anleitungen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

|||
|---------|---------|
|![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-1.png)    | ![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Entfernen einer Teams-Lizenz

Wenn Sie eine Teams-Lizenz von einem Benutzer entfernen, ist Teams für diesen Benutzer deaktiviert, und Teams wird im App-Startfeld oder auf der Startseite nicht mehr angezeigt. Ausführliche Schritte finden Sie unter [Zuweisen von Lizenzen von Benutzern .](/microsoft-365/admin/manage/remove-licenses-from-users)

|||
|---------|---------|
|![Screenshot der für einen Benutzer deaktivierten Teams-Lizenz](media/remove-teams-licenses-1.png)    | ![Screenshot der für einen Benutzer deaktivierten Teams-Lizenz](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, um Teams-Lizenzen für Benutzer in Massen zu verwalten. Sie aktivieren und deaktivieren Teams über PowerShell auf die gleiche Weise wie bei jeder anderen Serviceplanlizenz. Sie benötigen die Bezeichner für die Dienstpläne für Teams, die wie folgt aussehen:

- Microsoft Teams: TEAMS1
- Microsoft Teams für GCC: TEAMS_GOV
- Microsoft Teams für DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Zuweisen von Teams-Lizenzen in Massen

Ausführliche Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Entfernen von Teams-Lizenzen in Massen

Ausführliche Schritte finden Sie unter Deaktivieren des Zugriffs auf Dienste [mit PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) und Deaktivieren des Zugriffs auf Dienste beim Zuweisen [von Benutzerlizenzen.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Beispiel 

Das folgende Beispiel zeigt, wie Sie die [Cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) und [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) verwenden, um Teams für Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungsplan verfügen. Führen Sie beispielsweise die folgenden Schritte aus, um Teams zuerst für alle Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungsplan verfügen. Aktivieren Sie dann Teams für jeden einzelnen Benutzer, der Zugriff auf Teams haben sollte.

> [!IMPORTANT]
> Das [Cmdlet "New-MsolLicenseOptions"](/powershell/module/msonline/new-msollicenseoptions) aktiviert alle Dienste, die zuvor deaktiviert wurden, sofern sie nicht explizit in Ihrem benutzerdefinierten Skript angegeben wurden. Wenn Sie z. B. sowohl Exchange als auch Sway deaktiviert lassen möchten, während Sie Teams deaktivieren, müssen Sie dies in das Skript einbe lassen, oder Exchange und Sway werden für die von Ihnen identifizierten Benutzer aktiviert.

Führen Sie den folgenden Befehl aus, um alle verfügbaren Lizenzierungspläne in Ihrer Organisation anzeigen zu können. Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Führen Sie die folgenden Befehle aus, wobei sich der Name Ihrer Organisation und der Bezeichner für den Lizenzierungsplan befindet, den Sie im früheren \<CompanyName:License> Schritt abgerufen haben. Beispiel: ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Führen Sie den folgenden Befehl aus, um Teams für alle Benutzer zu deaktivieren, die über eine aktive Lizenz für den Lizenzierungsplan verfügen.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Verwandte Themen

- [Teams-Add-On-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Microsoft Teams-Add-On-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referenz zur Bildungs-SKU](sku-reference-edu.md)
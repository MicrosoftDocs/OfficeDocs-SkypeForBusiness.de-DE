---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
manager: SerdarSoysal
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 8e78d5905eaed7d9302ffdbf071c3dcf93f00fea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616261"
---
# <a name="manage-user-access-to-teams"></a>Verwalten des Benutzerzugriffs auf Microsoft Teams

Sie verwalten den Zugriff auf Teams auf Benutzerebene, indem Sie eine Microsoft Teams-Produktlizenz zuweisen oder entfernen. Mit Ausnahme der anonymen Teilnahme an Teams-Besprechungen muss jeder Benutzer in Ihrer Organisation über eine Teams-Lizenz verfügen, bevor er Teams verwenden kann. Sie können eine Teams-Lizenz für neue Benutzer zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten.

Wenn einem Benutzer standardmäßig ein Lizenzierungsplan (z. B. Microsoft 365 Enterprise E3 oder Microsoft 365 Business Premium) zugewiesen wird, wird automatisch eine Teams-Lizenz zugewiesen, und der Benutzer ist für Teams aktiviert. Sie können Teams für einen Benutzer deaktivieren oder aktivieren, indem Sie jederzeit eine Lizenz entfernen oder zuweisen.

Verwenden Sie Messagingrichtlinien, die über das <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a> verwaltet werden, um zu steuern, welche Chat- und Kanalnachrichtenfeatures benutzern in Teams zur Verfügung stehen. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen. Weitere Informationen finden Sie [unter Verwalten von Nachrichtenrichtlinien in Teams](messaging-policies-in-teams.md).
Sie verwalten Teams-Lizenzen im Microsoft 365 Admin Center oder mithilfe von PowerShell. Sie müssen ein globaler Administrator oder Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

> [!NOTE]
> Es wird empfohlen, Teams für alle Benutzer zu aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen gebildet werden können. Selbst wenn Sie ein Pilotprojekt ausführen, kann es immer noch hilfreich sein, Teams für alle Benutzer aktiviert zu halten, aber nur die Kommunikation an die Pilotgruppe der Benutzer zu richten.

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden der Microsoft 365 Admin Center

Microsoft Teams-Lizenzen auf Benutzerebene werden direkt über die Microsoft 365 Admin Center Benutzeroberflächen verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten. 

> [!IMPORTANT]
> Der Administrator muss über die Berechtigungen "Globaler Administrator" oder "Benutzerverwaltungsadministrator" verfügen, um Microsoft Teams-Lizenzen verwalten zu können.
Verwenden Sie die Microsoft 365 Admin Center, um Teams-Lizenzen für einzelne Benutzer oder kleine Gruppen von Benutzern gleichzeitig zu verwalten. Sie können Teams-Lizenzen auf der Seite **"Lizenzen** " (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite **"Aktive Benutzer** " verwalten. Die gewählte Methode hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Wenn Sie Teams-Lizenzen für eine große Anzahl von Benutzern verwalten müssen, z. B. Hunderte oder Tausende von Benutzern, [verwenden Sie PowerShell](#using-powershell) oder [gruppenbasierte Lizenzierung in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Zuweisen einer Teams-Lizenz

Die Schritte unterscheiden sich je nachdem, ob Sie die Seite **"Lizenzen** " oder die Seite **"Aktive Benutzer** " verwenden.  Eine schrittweise Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](/microsoft-365/admin/manage/assign-licenses-to-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Screenshot 1 der für einen Benutzer aktivierten Teams-Lizenz.](media/assign-teams-licenses-1.png)    | ![Screenshot 2 der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Entfernen einer Teams-Lizenz

> [!IMPORTANT]
> Es dauert ca. 24 Stunden, bis die Deaktivierung einer Teams-SKU wirksam wird.

Wenn Sie eine Teams-Lizenz von einem Benutzer entfernen, ist Teams für diesen Benutzer deaktiviert, und teams wird nicht mehr im App-Startfeld oder auf der Startseite angezeigt. Ausführliche Schritte finden Sie unter [Aufheben der Zuweisung von Lizenzen von Benutzern](/microsoft-365/admin/manage/remove-licenses-from-users).

|&nbsp;|&nbsp;|
|---------|---------|
|![Screenshot 1 der für einen Benutzer deaktivierten Teams-Lizenz.](media/remove-teams-licenses-1.png)    | ![Screenshot 2 der für einen Benutzer deaktivierten Teams-Lizenz](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, um Teams-Lizenzen für Benutzer massenhaft zu verwalten. Sie aktivieren und deaktivieren Teams über PowerShell auf die gleiche Weise wie für jede andere Serviceplanlizenz. Sie benötigen die Bezeichner für die Dienstpläne für Teams, die wie folgt lauten:

- Microsoft Teams: TEAMS1
- Microsoft Teams für GCC: TEAMS_GOV
- Microsoft Teams für DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Massenzuweisen von Teams-Lizenzen

Ausführliche Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Entfernen von Teams-Lizenzen in Massen

Ausführliche Schritte finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) und [Deaktivieren des Zugriffs auf Dienste beim Zuweisen von Benutzerlizenzen](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Beispiel 

Es folgt ein Beispiel für die Verwendung der Cmdlets ["New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) " und ["Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) ", um Teams für Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungsplan verfügen. Führen Sie beispielsweise die folgenden Schritte aus, um Teams zuerst für alle Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungsplan verfügen. Aktivieren Sie dann Teams für jeden einzelnen Benutzer, der Zugriff auf Teams haben soll.

> [!IMPORTANT]
> Das Cmdlet ["New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) " aktiviert alle Dienste, die zuvor deaktiviert wurden, es sei denn, sie werden in Ihrem benutzerdefinierten Skript explizit identifiziert. Wenn Sie z. B. Sowohl Exchange als auch Sway deaktiviert lassen möchten und gleichzeitig Teams deaktivieren möchten, müssen Sie dies in das Skript einschließen, oder sowohl Exchange als auch Sway für die von Ihnen identifizierten Benutzer aktiviert werden.

Führen Sie den folgenden Befehl aus, um alle verfügbaren Lizenzierungspläne in Ihrer Organisation anzuzeigen. Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).


```powershell
Get-MsolAccountSku
```

Führen Sie die folgenden Befehle aus. \<CompanyName:License> Dabei handelt es sich um den Namen Ihrer Organisation und den Bezeichner für den Lizenzierungsplan, den Sie im vorherigen Schritt abgerufen haben. Beispiel: ContosoSchool:ENTERPRISEPACK_STUDENT.

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
- [Education-SKU-Referenz](sku-reference-edu.md)

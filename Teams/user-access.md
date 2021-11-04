---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Erfahren Sie, wie Sie den Benutzerzugriff Teams Benutzerzugriff verwalten, indem Sie Benutzern in Ihrer Teams eine Teams Lizenz zuweisen oder entfernen.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 433996fe1a883bff1c019000acf912606b3ecb91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741521"
---
# <a name="manage-user-access-to-teams"></a>Verwalten des Benutzerzugriffs auf Teams

Sie verwalten den Zugriff auf Teams Auf Benutzerebene durch Zuweisen oder Entfernen einer Microsoft Teams Produktlizenz. Mit Ausnahme der Teams anonymen Teilnahme an Besprechungen muss jeder Benutzer in Ihrer Organisation über eine Lizenz Teams verfügen, damit er die Teams. Sie können eine Teams neuen Benutzern zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten.

Wenn einem Benutzer ein Lizenzierungsplan (z. B. Microsoft 365 Enterprise E3 oder Microsoft 365 Business Premium) zugewiesen wird, wird standardmäßig automatisch eine Teams-Lizenz zugewiesen und der Benutzer für Teams. Sie können benutzerfreundliche Lizenzen Teams deaktivieren oder aktivieren, indem Sie jederzeit eine Lizenz entfernen oder zuweisen.

Verwenden Sie Messagingrichtlinien, die über Teams <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>verwaltet werden, um zu steuern, welche Chat- und Kanalnachrichtenfeatures den Benutzern in ihrer Teams. Sie können die Standardrichtlinie verwenden oder mindestens eine benutzerdefinierte Messagingrichtlinie für Personen in Ihrer Organisation erstellen. Weitere Informationen finden Sie unter [Verwalten von Messagingrichtlinien in Teams.](messaging-policies-in-teams.md)
Sie verwalten Teams Lizenzen in der Microsoft 365 Admin Center oder mithilfe von PowerShell. Sie müssen ein globaler Administrator oder Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

> [!NOTE]
> Es wird empfohlen, die Teams für alle Benutzer zu aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen gebildet werden können. Selbst wenn Sie ein Pilotprojekt ausführen, kann es dennoch hilfreich sein, die Teams für alle Benutzer aktiviert zu lassen, aber die Kommunikation nur an die Pilotgruppe von Benutzern zu halten.

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden der Microsoft 365 Admin Center

Teams Lizenzen auf Benutzerebene werden direkt über die benutzerdefinierten Microsoft 365 Admin Center-Verwaltungsschnittstellen verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten. 

> [!IMPORTANT]
> Der Administrator muss über Die Berechtigungen eines globalen Administrators oder eines Benutzerverwaltungsadministrators verfügen, um die Microsoft Teams verwalten zu können.
Verwenden Sie Microsoft 365 Admin Center, um Teams Lizenzen für einzelne Benutzer oder kleine Gruppen von Benutzern gleichzeitig zu verwalten. Sie können ihre Teams auf  der Seite Lizenzen (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite **Aktive Benutzer verwalten.** Die von Ihnen wählen Methode hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Wenn Sie Teams-Lizenzen für eine große Anzahl von Benutzern verwalten müssen, z. B. Hunderte oder Tausende von Benutzern, verwenden Sie [powerShell](#using-powershell) oder gruppenbasierte Lizenzierung [in Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Zuweisen einer Teams Lizenz

Je nachdem, ob Sie die Seite Lizenzen oder die Seite Aktive Benutzer **verwenden,** unterscheiden sich **die Schritte.**  Eine schrittweise Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/microsoft-365/admin/manage/assign-licenses-to-users)

|&nbsp;|&nbsp;|
|---------|---------|
|![Screenshot 1 der Teams für einen Benutzer aktivierten Lizenz.](media/assign-teams-licenses-1.png)    | ![Screenshot 2 der Teams für einen Benutzer aktiviert](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Entfernen einer Teams Lizenz

> [!IMPORTANT]
> Das Deaktivieren einer SKU Teams etwa 24 Stunden in Kraft.

Wenn Sie eine Teams-Lizenz von einem Benutzer entfernen, wird Teams für diesen Benutzer deaktiviert, und die Teams wird nicht mehr im App-Startfeld oder auf der Startseite angezeigt. Ausführliche Schritte finden Sie unter [Zuweisen von Lizenzen von Benutzern.](/microsoft-365/admin/manage/remove-licenses-from-users)

|&nbsp;|&nbsp;|
|---------|---------|
|![Screenshot 1 der Teams für einen Benutzer deaktiviert](media/remove-teams-licenses-1.png)    | ![Screenshot 2 der Teams für einen Benutzer deaktiviert](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, Teams Massenlizenzen für Benutzer zu verwalten. Sie aktivieren und deaktivieren Teams über PowerShell auf die gleiche Weise wie bei jeder anderen Serviceplanlizenz. Sie benötigen die Bezeichner für die Dienstpläne für Teams die folgenden:

- Microsoft Teams: TEAMS1
- Microsoft Teams für GCC: TEAMS_GOV
- Microsoft Teams für DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Massen Teams zuweisen

Ausführliche Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Massen Teams von Lizenzen

Ausführliche Schritte finden Sie unter Deaktivieren des Zugriffs auf Dienste [mit PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) und Deaktivieren des Zugriffs auf Dienste beim Zuweisen [von Benutzerlizenzen.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Beispiel 

Es folgt ein Beispiel für die Verwendung der [Cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) und [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) zum Deaktivieren von Teams für Benutzer mit einem bestimmten Lizenzierungsplan. Führen Sie z. B. die folgenden Schritte aus, um Teams Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungsplan verfügen. Aktivieren Sie Teams Benutzer, die Zugriff auf ihre Daten haben sollen, Teams.

> [!IMPORTANT]
> Das [Cmdlet New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) aktiviert alle zuvor deaktivierten Dienste, sofern sie nicht explizit in Ihrem benutzerdefinierten Skript angegeben werden. Wenn Sie beispielsweise sowohl Exchange als auch Sway deaktiviert lassen möchten, während Sie Teams deaktivieren, müssen Sie dies in das Skript verwenden, da aber sowohl Exchange als auch Sway für die von Ihnen identifizierten Benutzer aktiviert werden.

Führen Sie den folgenden Befehl aus, um alle verfügbaren Lizenzierungspläne in Ihrer Organisation anzeigen. Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Führen Sie die folgenden Befehle aus. Dabei handelt es sich um den Namen Ihrer Organisation und den Bezeichner für den Lizenzierungsplan, den Sie im früheren \<CompanyName:License> Schritt abgerufen haben. Beispiel: ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Führen Sie den folgenden Befehl aus, um Teams Benutzer zu deaktivieren, die über eine aktive Lizenz für den Lizenzierungsplan verfügen.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Verwandte Themen

- [Teams von Add-On-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Microsoft Teams-Add-On-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [SKU-Referenz für Bildungseinrichtungen](sku-reference-edu.md)

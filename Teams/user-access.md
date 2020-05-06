---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Erfahren Sie, wie Sie den Benutzer Zugriff auf Teams verwalten können, indem Sie Benutzern in Ihrer Organisation eine Teams-Lizenz zuweisen oder daraus entfernen.
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042272"
---
# <a name="manage-user-access-to-teams"></a>Verwalten des Benutzerzugriffs auf Teams

Sie können den Zugriff auf Teams auf Benutzerebene verwalten, indem Sie eine Microsoft Teams-Produktlizenz zuweisen oder entfernen. Jeder Benutzer in Ihrer Organisation muss über eine Teams-Lizenz verfügen, bevor er Teams verwenden kann. Sie können neuen Benutzern eine Teams-Lizenz zuweisen, wenn neue Benutzerkonten erstellt werden oder für Benutzer mit vorhandenen Konten.

Wenn einem Benutzer ein Lizenzierungs Plan (beispielsweise Microsoft 365 Enterprise E3 oder Microsoft 365 Business Premium) zugewiesen ist, wird standardmäßig automatisch eine Teams-Lizenz zugewiesen, und der Benutzer ist für Teams aktiviert. Sie können Teams für einen Benutzer deaktivieren oder aktivieren, indem Sie eine Lizenz zu einem beliebigen Zeitpunkt entfernen oder zuweisen.

Sie verwalten Teamlizenzen im Microsoft 365 Admin Center oder mithilfe von PowerShell. Sie müssen ein globaler Administrator oder Benutzer Verwaltungs Administrator sein, um Lizenzen verwalten zu können.

> [!NOTE]
> Wir empfehlen, dass Sie Teams für alle Benutzer aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen ausgebildet werden können. Auch wenn Sie ein Pilotprojekt ausführen, ist es möglicherweise weiterhin hilfreich, Teams für alle Benutzer aktiviert zu halten, aber nur die Kommunikation mit der Pilotgruppe von Benutzern zu erreichen.

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden des Microsoft 365 admin Centers

Verwenden Sie das Microsoft 365 Admin Center, um Teams-Lizenzen für einzelne Benutzer oder kleine Benutzergruppen gleichzeitig zu verwalten. Sie können Teams-Lizenzen auf der Seite " **Lizenzen** " (für bis zu 20 Benutzer zur Zeit) oder auf der Seite " **aktive Benutzer** " verwalten. Die Methode, die Sie auswählen, hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer verwalten oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Wenn Sie Teams-Lizenzen für eine große Anzahl von Benutzern, wie etwa Hunderte oder Tausende von Benutzern, verwalten müssen, [verwenden Sie PowerShell](#using-powershell) oder [Gruppenbasierte Lizenzierung in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Zuweisen einer Lizenz für Teams

Die Schritte unterscheiden sich je nachdem, ob Sie die Seite **Lizenzen** oder **aktive Benutzer** verwenden.  Eine Schritt-für-Schritt-Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

|||
|---------|---------|
|![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-1.png)    | ![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Entfernen einer Teamlizenz

Wenn Sie eine Teams-Lizenz von einem Benutzer entfernen, werden die Teams für diesen Benutzer deaktiviert, und es werden keine Teams mehr im App-Startfeld oder auf der Startseite angezeigt. Detaillierte Anweisungen finden Sie unter aufheben [der Zuweisung von Lizenzen von Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Screenshot der Teams-Lizenz für einen Benutzer deaktiviert](media/remove-teams-licenses-1.png)    | ![Screenshot der Teams-Lizenz für einen Benutzer deaktiviert](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell zum Verwalten von Teams-Lizenzen für Benutzer in Massen. Sie aktivieren und deaktivieren Teams über PowerShell auf die gleiche Weise wie bei jeder anderen Service Plan-Lizenz. Sie benötigen die IDs für die Servicepläne für Teams, die wie folgt aussehen:

- Microsoft Teams: TEAMS1
- Microsoft Teams für gcc: TEAMS_GOV
- Microsoft Teams für DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Zuweisen von Teams-Lizenzen in Massen

Detaillierte Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Entfernen von Teams-Lizenzen in Massen

Detaillierte Anweisungen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) und [Deaktivieren des Zugriffs auf Dienste beim Zuweisen von Benutzerlizenzen](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Beispiel 

Im folgenden sehen Sie ein Beispiel für die Verwendung der Cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) und [MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) , um Teams für Benutzer mit einem bestimmten Lizenzierungs Plan zu deaktivieren. Führen Sie beispielsweise die folgenden Schritte aus, um zunächst Teams für alle Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungs Plan verfügen. Aktivieren Sie dann Teams für jeden einzelnen Benutzer, der Zugriff auf Teams haben soll.

> [!IMPORTANT]
> Das Cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) aktiviert alle Dienste, die zuvor deaktiviert wurden, es sei denn, Sie sind explizit in Ihrem benutzerdefinierten Skript angegeben. Wenn Sie beispielsweise sowohl Exchange als auch Sway deaktiviert lassen möchten, während Sie auch Teams deaktivieren, müssen Sie dies in das Skript einbeziehen, oder sowohl Exchange als auch Sway werden für die von Ihnen angegebenen Benutzer aktiviert.

Führen Sie den folgenden Befehl aus, um alle verfügbaren Lizenzierungs Pläne in Ihrer Organisation anzuzeigen. Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).

      Get-MsolAccountSku

Führen Sie die folgenden Befehle aus \<, wobei CompanyName: License> der Name Ihrer Organisation und der Bezeichner für den Lizenzierungs Plan ist, den Sie im vorherigen Schritt abgerufen haben. Beispiel: ContosoSchool: ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

Führen Sie den folgenden Befehl aus, um Teams für alle Benutzer zu deaktivieren, die über eine aktive Lizenz für den Lizenzierungs Plan verfügen.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>Verwalten von Teams auf Organisationsebene

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Verwandte Themen

- [Teams-Add-on-Lizenzen](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Add-on-Lizenzen für Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education-SKU-Referenz](sku-reference-edu.md)
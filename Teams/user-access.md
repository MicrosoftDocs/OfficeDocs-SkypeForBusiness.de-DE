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
description: Erfahren Sie, wie Sie den Benutzerzugriff auf Teams verwalten, indem Sie Benutzern in Ihrer Organisation eine Teamlizenz zuweisen oder entfernen.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d49b27de8fe6c6d13ef6ac626764b13e1fe36a0
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871014"
---
# <a name="manage-user-access-to-teams"></a>Verwalten des Benutzerzugriffs auf Teams

Sie verwalten den Zugriff auf Teams auf Benutzerebene, indem Sie eine Microsoft Teams-Produktlizenz zuweisen oder entfernen. Mit Ausnahme der anonymen Teilnahme an Teambesprechungen muss jeder Benutzer in Ihrer Organisation über eine Lizenz für Teams verfügen, damit er Teams verwenden kann. Sie können eine Teamlizenz für neue Benutzer zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten.

Wenn einem Benutzer ein Lizenzierungsplan (z. B. Microsoft 365 Enterprise E3 oder Microsoft 365 Business Premium) zugewiesen wird, wird einem Benutzer standardmäßig automatisch eine Lizenz zugewiesen und der Benutzer für Teams aktiviert. Sie können Teams für einen Benutzer deaktivieren oder aktivieren, indem Sie jederzeit eine Lizenz entfernen oder zuweisen.

Verwenden Sie messaging-Richtlinien, die über <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">das Teams Admin Center</a>verwaltet werden, um zu steuern, welche Chat- und Kanalnachrichtenfeatures benutzern in Teams zur Verfügung stehen. Sie können die Standardrichtlinie verwenden oder mindestens eine benutzerdefinierte Messagingrichtlinie für Personen in Ihrer Organisation erstellen. Weitere Informationen finden Sie unter ["Verwalten von Messagingrichtlinien in Teams".](messaging-policies-in-teams.md)
Sie verwalten Teamlizenzen im Microsoft 365 Admin Center oder mithilfe von PowerShell. Sie müssen ein globaler Administrator oder ein Benutzerverwaltungsadministrator sein, um Lizenzen verwalten zu können.

> [!NOTE]
> Wir empfehlen, Teams für alle Benutzer zu aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen gebildet werden können. Auch wenn Sie ein Pilotprojekt ausführen, kann es dennoch hilfreich sein, Teams für alle Benutzer aktiviert zu lassen, aber die Kommunikation nur an die Pilotgruppe von Benutzern zu zielvernetzen.

## <a name="using-the-microsoft-365-admin-center"></a>Verwenden des Microsoft 365 Admin Centers

Lizenzen auf Benutzerebene von Teams werden direkt über die Benutzeroberflächen des Microsoft 365 Admin Centers verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten. 

> [!IMPORTANT]
> Der Administrator muss über die Berechtigungen "Globaler Administrator" oder "Benutzerverwaltungsadministrator" verfügen, um Microsoft Teams-Lizenzen verwalten zu können.
Verwenden Sie das Microsoft 365 Admin Center, um Teams-Lizenzen für einzelne Benutzer oder kleine Gruppen von Benutzern gleichzeitig zu verwalten. Sie können Teams-Lizenzen auf **der** Seite "Lizenzen" (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite **"Aktive Benutzer"** verwalten. Die von Ihnen wählende Methode hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.

Wenn Sie die Lizenzen von Teams für eine große Anzahl von Benutzern verwalten müssen, z. B. Hunderte oder Tausende von Benutzern, verwenden Sie [PowerShell](#using-powershell) oder eine gruppenbasierte Lizenzierung [in Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Zuweisen einer Teams-Lizenz

Je nachdem, ob Sie die Seite "Lizenzen" oder die Seite "Aktive Benutzer" **verwenden,** unterscheiden **sich die Schritte.**  Eine schrittweise Anleitung finden Sie unter ["Zuweisen von Lizenzen zu Benutzern".](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

|||
|---------|---------|
|![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-1.png)    | ![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Entfernen einer Teams-Lizenz

Wenn Sie eine Lizenz für Teams von einem Benutzer entfernen, wird Teams für diesen Benutzer deaktiviert, und Teams wird nicht mehr im Startfeld oder auf der Startseite von Apps angezeigt. Ausführliche Schritte finden Sie unter ["Zuweisen von Lizenzen von Benutzern".](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)

|||
|---------|---------|
|![Screenshot der für einen Benutzer deaktivierten Teams-Lizenz](media/remove-teams-licenses-1.png)    | ![Screenshot der für einen Benutzer deaktivierten Teams-Lizenz](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie PowerShell, um Die Lizenzen von Teams für Benutzer in Massen zu verwalten. Sie aktivieren und deaktivieren Teams über PowerShell auf die gleiche Weise wie für jede andere Serviceplanlizenz. Sie benötigen die Bezeichner für die Dienstpläne für Teams, die wie folgt aussehen:

- Microsoft Teams: TEAMS1
- Microsoft Teams für GCC: TEAMS_GOV
- Microsoft Teams für DoD: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Massen zuweisen von Teamlizenzen

Ausführliche Schritte finden Sie unter ["Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell".](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Massen entfernen von Teamlizenzen

Ausführliche Schritte finden Sie unter "Deaktivieren des Zugriffs auf Dienste [mit PowerShell"](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) und "Zugriff auf Dienste deaktivieren" beim Zuweisen [von Benutzerlizenzen.](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Beispiel 

Es folgt ein Beispiel für die Verwendung der [Cmdlets "New-MsolLicenseOptions"](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) und ["Set-MsolUserLicense"](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) zum Deaktivieren von Teams für Benutzer mit einem bestimmten Lizenzierungsplan. Führen Sie z. B. die folgenden Schritte aus, um Teams zuerst für alle Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungsplan verfügen. Aktivieren Sie dann Teams für jeden einzelnen Benutzer, der Zugriff auf Teams haben soll.

> [!IMPORTANT]
> Das [Cmdlet "New-MsolLicenseOptions"](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) aktiviert alle Zuvor deaktivierten Dienste, sofern dies nicht explizit in Ihrem benutzerdefinierten Skript angegeben ist. Wenn Sie beispielsweise Sowohl Exchange als auch Sway deaktiviert lassen möchten, während Sie Teams gleichzeitig deaktivieren, müssen Sie dies in das Skript verwenden. Dann sind Exchange und Sway für die von Ihnen identifizierten Benutzer aktiviert.

Führen Sie den folgenden Befehl aus, um alle verfügbaren Lizenzierungspläne in Ihrer Organisation anzeigen. Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Führen Sie die folgenden Befehle aus. Dabei handelt es sich um den Namen Ihrer Organisation und den Bezeichner für den Lizenzplan, den Sie im früheren \<CompanyName:License> Schritt abgerufen haben. Beispiel: ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Führen Sie den folgenden Befehl aus, um Teams für alle Benutzer zu deaktivieren, die über eine aktive Lizenz für den Lizenzierungsplan verfügen.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Verwandte Themen

- [Lizenzen für Teams-Add-On](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Zuweisen von Teams-Add-On-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education-SKU-Referenz](sku-reference-edu.md)

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
ms.reviewer: ritikag
search.appverid: MET150
description: Erfahren Sie, wie Sie den Benutzer Zugriff auf Teams verwalten können, indem Sie Benutzern in Ihrer Organisation eine Teams-Lizenz zuweisen oder daraus entfernen.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d370bec6eb8a3319427c934593016f2b85d6c26
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611459"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="2bcae-103">Verwalten des Benutzerzugriffs auf Teams</span><span class="sxs-lookup"><span data-stu-id="2bcae-103">Manage user access to Teams</span></span>

<span data-ttu-id="2bcae-104">Sie können den Zugriff auf Teams auf Benutzerebene verwalten, indem Sie eine Microsoft Teams-Produktlizenz zuweisen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="2bcae-105">Mit Ausnahme der anonymen Teilnahme an Teams-Besprechungen muss jeder Benutzer in Ihrer Organisation über eine Teams-Lizenz verfügen, bevor er Teams verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="2bcae-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="2bcae-106">Sie können neuen Benutzern eine Teams-Lizenz zuweisen, wenn neue Benutzerkonten erstellt werden oder für Benutzer mit vorhandenen Konten.</span><span class="sxs-lookup"><span data-stu-id="2bcae-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="2bcae-107">Wenn einem Benutzer ein Lizenzierungs Plan (beispielsweise Microsoft 365 Enterprise E3 oder Microsoft 365 Business Premium) zugewiesen ist, wird standardmäßig automatisch eine Teams-Lizenz zugewiesen, und der Benutzer ist für Teams aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2bcae-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="2bcae-108">Sie können Teams für einen Benutzer deaktivieren oder aktivieren, indem Sie eine Lizenz zu einem beliebigen Zeitpunkt entfernen oder zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="2bcae-109">Verwenden Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Team Admin Center</a>verwaltete Nachrichtenrichtlinien, um zu steuern, welche Chat-und Kanal-Messaging Features Benutzern in Teams zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="2bcae-110">Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="2bcae-111">Weitere Informationen finden Sie unter [Verwalten von Nachrichtenrichtlinien in Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2bcae-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="2bcae-112">Sie verwalten Teamlizenzen im Microsoft 365 Admin Center oder mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bcae-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="2bcae-113">Sie müssen ein globaler Administrator oder Benutzer Verwaltungs Administrator sein, um Lizenzen verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="2bcae-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="2bcae-114">Wir empfehlen, dass Sie Teams für alle Benutzer aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen ausgebildet werden können.</span><span class="sxs-lookup"><span data-stu-id="2bcae-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="2bcae-115">Auch wenn Sie ein Pilotprojekt ausführen, ist es möglicherweise weiterhin hilfreich, Teams für alle Benutzer aktiviert zu halten, aber nur die Kommunikation mit der Pilotgruppe von Benutzern zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="2bcae-116">Verwenden des Microsoft 365 admin Centers</span><span class="sxs-lookup"><span data-stu-id="2bcae-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="2bcae-117">Teams auf Benutzerebene Lizenzen werden direkt über die Benutzer Verwaltungsschnittstellen von Microsoft 365 Admin Center verwaltet.</span><span class="sxs-lookup"><span data-stu-id="2bcae-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="2bcae-118">Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder für Benutzer mit vorhandenen Konten.</span><span class="sxs-lookup"><span data-stu-id="2bcae-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="2bcae-119">Der Administrator muss über globale Administrator-oder Benutzer Verwaltungsberechtigungen verfügen, um Microsoft Teams-Lizenzen verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="2bcae-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="2bcae-120">Verwenden Sie das Microsoft 365 Admin Center, um Teams-Lizenzen für einzelne Benutzer oder kleine Benutzergruppen gleichzeitig zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2bcae-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="2bcae-121">Sie können Teams-Lizenzen auf der Seite " **Lizenzen** " (für bis zu 20 Benutzer zur Zeit) oder auf der Seite " **aktive Benutzer** " verwalten.</span><span class="sxs-lookup"><span data-stu-id="2bcae-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="2bcae-122">Die Methode, die Sie auswählen, hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer verwalten oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="2bcae-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="2bcae-123">Wenn Sie Teams-Lizenzen für eine große Anzahl von Benutzern, wie etwa Hunderte oder Tausende von Benutzern, verwalten müssen, [verwenden Sie PowerShell](#using-powershell) oder [Gruppenbasierte Lizenzierung in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="2bcae-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="2bcae-124">Zuweisen einer Lizenz für Teams</span><span class="sxs-lookup"><span data-stu-id="2bcae-124">Assign a Teams license</span></span>

<span data-ttu-id="2bcae-125">Die Schritte unterscheiden sich je nachdem, ob Sie die Seite **Lizenzen** oder **aktive Benutzer** verwenden.</span><span class="sxs-lookup"><span data-stu-id="2bcae-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="2bcae-126">Eine Schritt-für-Schritt-Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="2bcae-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-1.png)    | ![Screenshot der für einen Benutzer aktivierten Teams-Lizenz](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="2bcae-129">Entfernen einer Teamlizenz</span><span class="sxs-lookup"><span data-stu-id="2bcae-129">Remove a Teams license</span></span>

<span data-ttu-id="2bcae-130">Wenn Sie eine Teams-Lizenz von einem Benutzer entfernen, werden die Teams für diesen Benutzer deaktiviert, und es werden keine Teams mehr im App-Startfeld oder auf der Startseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bcae-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="2bcae-131">Detaillierte Anweisungen finden Sie unter aufheben [der Zuweisung von Lizenzen von Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span><span class="sxs-lookup"><span data-stu-id="2bcae-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Screenshot der Teams-Lizenz für einen Benutzer deaktiviert](media/remove-teams-licenses-1.png)    | ![Screenshot der Teams-Lizenz für einen Benutzer deaktiviert](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="2bcae-134">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bcae-134">Using PowerShell</span></span>

<span data-ttu-id="2bcae-135">Verwenden Sie PowerShell zum Verwalten von Teams-Lizenzen für Benutzer in Massen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="2bcae-136">Sie aktivieren und deaktivieren Teams über PowerShell auf die gleiche Weise wie bei jeder anderen Service Plan-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="2bcae-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="2bcae-137">Sie benötigen die IDs für die Servicepläne für Teams, die wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2bcae-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="2bcae-138">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="2bcae-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="2bcae-139">Microsoft Teams für gcc: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="2bcae-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="2bcae-140">Microsoft Teams für DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="2bcae-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="2bcae-141">Zuweisen von Teams-Lizenzen in Massen</span><span class="sxs-lookup"><span data-stu-id="2bcae-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="2bcae-142">Detaillierte Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="2bcae-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="2bcae-143">Entfernen von Teams-Lizenzen in Massen</span><span class="sxs-lookup"><span data-stu-id="2bcae-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="2bcae-144">Detaillierte Anweisungen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) und [Deaktivieren des Zugriffs auf Dienste beim Zuweisen von Benutzerlizenzen](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="2bcae-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="2bcae-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bcae-145">Example</span></span> 

<span data-ttu-id="2bcae-146">Im folgenden sehen Sie ein Beispiel für die Verwendung der Cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) und [MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) , um Teams für Benutzer mit einem bestimmten Lizenzierungs Plan zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2bcae-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="2bcae-147">Führen Sie beispielsweise die folgenden Schritte aus, um zunächst Teams für alle Benutzer zu deaktivieren, die über einen bestimmten Lizenzierungs Plan verfügen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="2bcae-148">Aktivieren Sie dann Teams für jeden einzelnen Benutzer, der Zugriff auf Teams haben soll.</span><span class="sxs-lookup"><span data-stu-id="2bcae-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bcae-149">Das Cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) aktiviert alle Dienste, die zuvor deaktiviert wurden, es sei denn, Sie sind explizit in Ihrem benutzerdefinierten Skript angegeben.</span><span class="sxs-lookup"><span data-stu-id="2bcae-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="2bcae-150">Wenn Sie beispielsweise sowohl Exchange als auch Sway deaktiviert lassen möchten, während Sie auch Teams deaktivieren, müssen Sie dies in das Skript einbeziehen, oder sowohl Exchange als auch Sway werden für die von Ihnen angegebenen Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2bcae-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="2bcae-151">Führen Sie den folgenden Befehl aus, um alle verfügbaren Lizenzierungs Pläne in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="2bcae-152">Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="2bcae-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="2bcae-153">Führen Sie die folgenden Befehle aus, wobei der \<CompanyName:License> Name Ihrer Organisation und der Bezeichner für den Lizenzierungs Plan, den Sie im vorherigen Schritt abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="2bcae-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="2bcae-154">Beispiel: ContosoSchool: ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="2bcae-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="2bcae-155">Führen Sie den folgenden Befehl aus, um Teams für alle Benutzer zu deaktivieren, die über eine aktive Lizenz für den Lizenzierungs Plan verfügen.</span><span class="sxs-lookup"><span data-stu-id="2bcae-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="2bcae-156">Verwalten von Teams auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="2bcae-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="2bcae-157">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2bcae-157">Related topics</span></span>

- [<span data-ttu-id="2bcae-158">Teams-Add-on-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="2bcae-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="2bcae-159">Zuweisen von Add-on-Lizenzen für Teams</span><span class="sxs-lookup"><span data-stu-id="2bcae-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="2bcae-160">Anzeigen von Lizenzen und Diensten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bcae-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="2bcae-161">Produktnamen und Serviceplanbezeichner für die Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="2bcae-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="2bcae-162">Education-SKU-Referenz</span><span class="sxs-lookup"><span data-stu-id="2bcae-162">Education SKU reference</span></span>](sku-reference-edu.md)

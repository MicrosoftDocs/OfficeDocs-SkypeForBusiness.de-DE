---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: Hier erfahren Sie, wie Sie den Zugriff auf Benutzerebene pro Benutzer aktivieren oder deaktivieren.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: be2e95d7be359856d5aef4f67664ef27ee62fa74
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562613"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="7cfa9-103">Verwalten des Benutzerzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7cfa9-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7cfa9-104">Auf Benutzerebene kann Zugriff auf Microsoft-Teams, aktiviert oder deaktiviert für jeden Benutzer einzeln durch Zuweisen oder Entfernen von der Microsoft-Teams-Lizenz werden.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="7cfa9-105">Zurzeit stehen keine Richtlinienoptionen für aktivieren Teams oder eine Teilmenge der Features von Teams, oder Deaktivieren der Ebene eine einzelne Benutzer außerhalb der Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="7cfa9-106">Microsoft empfiehlt, dass Sie Teams für alle Benutzer in einem Unternehmen aktivieren, damit Teams Wiki für Projekte und anderen dynamischen Initiativen gebildet werden können.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="7cfa9-107">Auch wenn Sie Entscheidungen zu treffen pilot, möglicherweise noch ist es hilfreich zum Beibehalten von Teams, die für alle Benutzer aktiviert, jedoch nur als Ziel für die Kommunikation mit der Pilotgruppe von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="7cfa9-108">Verwalten von Teams über das Office 365 Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="7cfa9-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="7cfa9-109">Teams auf Benutzerebene Lizenzen werden direkt über die Office 365 Admin Center Benutzer Verwaltungsschnittstellen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="7cfa9-110">Ein Administrator kann Lizenzen für neue Benutzer, wenn neue Benutzerkonten erstellt werden, oder Benutzer mit vorhandenen Konten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="7cfa9-111">Der Administrator muss Office 365 globaler Administrator oder Benutzerverwaltungsadministrator Berechtigungen zum Verwalten von Lizenzen für Microsoft-Teams verfügen.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="7cfa9-p103">Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="7cfa9-115">Eine Benutzerlizenz Teams kann jederzeit deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="7cfa9-116">Nachdem die Lizenz deaktiviert ist, wird der Benutzerzugriff auf Microsoft-Teams, verhindert werden, und der Benutzer werden nicht mehr Teams in die Office 365-app-Start "und" Homepage finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center mit ausgewählter Option „Microsoft Teams“](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="7cfa9-118">Verwalten von über die PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cfa9-118">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cfa9-119">Neue MsolLicenseOptions werden aktivieren Sie alle Dienste, die zuvor deaktiviert wurden, es sei denn, Explictitly identitied in Ihrem benutzerdefinierten Skript.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-119">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="7cfa9-120">Beispiel: Wenn Sie sowohl Exchange & Schlingern beim Deaktivieren von Teams, zusätzlich deaktiviert lassen möchten enthält müssten Sie dies in das Skript oder beide Exchange & Schlingern wird aktiviert werden, für die Benutzer, den Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-120">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="7cfa9-121">Wenn Sie eine Benutzeroberfläche zur Verwaltung dieser Funktionen nutzen möchten finden Sie unter: [Reporting zu Office 365-Lizenz und Verwaltungstool-entfernen Lizenzen in einer Sammeloperation](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="7cfa9-121">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="7cfa9-122">Das Aktivieren und Deaktivieren von Microsoft Teams als Arbeitsauslastungslizenz über PowerShell funktioniert genau wie bei jeder anderen Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-122">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="7cfa9-123">Der Name des Dienstplans für Microsoft Teams lautet TEAMS1.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-123">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="7cfa9-124">Für Behörden ist der Dienstname Plan TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-124">For Government the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="7cfa9-125">(Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)</span><span class="sxs-lookup"><span data-stu-id="7cfa9-125">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="7cfa9-126">**Beispiel:** Im folgenden finden einfach einem Beispiel auf wie würden Sie Teams für alle Benutzer in einem bestimmten Lizenztyp deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-126">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="7cfa9-127">Sie müssen dies zuerst tun und dann den Lizenztyp für die Benutzer, die im Rahmen von Pilottests Zugriff haben sollen, einzeln aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-127">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="7cfa9-128">Um die in Ihrer Organisation vorhandenen Abonnementtypen anzuzeigen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="7cfa9-128">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="7cfa9-129">Tragen Sie den Namen Ihres Plans einschließlich des Organisationsnamens und des Plans für Ihre Bildungseinrichtung ein (zum Beispiel „ContosoSchool:ENTERPRISEPACK_STUDENT“), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="7cfa9-129">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="7cfa9-130">Führen Sie zum Deaktivieren von Teams für alle Benutzer mit einer aktiven Lizenz für den benannten Plan den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="7cfa9-130">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="7cfa9-132">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="7cfa9-132">Decision Point</span></span>         |<ul><li><span data-ttu-id="7cfa9-133">Was ist Ihre Organisation Planen von Teams Onboarding in der gesamten Organisation?</span><span class="sxs-lookup"><span data-stu-id="7cfa9-133">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="7cfa9-134">(Pilot- oder öffnen)</span><span class="sxs-lookup"><span data-stu-id="7cfa9-134">(Pilot or Open)</span></span></li></ul>         |
|![Symbol für „Nächste Schritte“](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="7cfa9-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7cfa9-136">Next Steps</span></span>         |<ul><li><span data-ttu-id="7cfa9-137">Wenn Sie über eine geschlossene Pilotprojekt Onboarding entscheiden, ob Sie über die Lizenzierung tun möchten, oder gezielten Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-137">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="7cfa9-138">Je nach Entscheidung, dauern evaluieren Schritte aus, um sicherzustellen, nur Benutzer, die auf Teams (falls erforderlich) zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-138">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="7cfa9-139">Dokumentieren Sie die Richtlinien für welche Benutzer stellen, die werden (oder keine) haben Zugriff auf Teams.</span><span class="sxs-lookup"><span data-stu-id="7cfa9-139">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="7cfa9-140">Verwalten von Teams auf der Ebene der Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="7cfa9-140">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]


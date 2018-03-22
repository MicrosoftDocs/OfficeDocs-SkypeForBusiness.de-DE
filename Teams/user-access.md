---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Hier erfahren Sie, wie Sie den Zugriff auf Benutzerebene pro Benutzer aktivieren oder deaktivieren.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="016ff-103">Verwalten des Benutzerzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="016ff-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="016ff-104">Auf Benutzerebene kann Zugriff auf Microsoft-Teams, aktiviert oder deaktiviert für jeden Benutzer einzeln durch Zuweisen oder Entfernen von der Microsoft-Teams-Lizenz werden.</span><span class="sxs-lookup"><span data-stu-id="016ff-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="016ff-105">Zurzeit stehen keine Richtlinienoptionen für aktivieren Teams oder eine Teilmenge der Features von Teams, oder Deaktivieren der Ebene eine einzelne Benutzer außerhalb der Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="016ff-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="016ff-106">Microsoft empfiehlt, dass Sie Teams für alle Benutzer in einem Unternehmen aktivieren, damit Teams Wiki für Projekte und anderen dynamischen Initiativen gebildet werden können.</span><span class="sxs-lookup"><span data-stu-id="016ff-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="016ff-107">Auch wenn Sie Entscheidungen zu treffen pilot, möglicherweise noch ist es hilfreich zum Beibehalten von Teams, die für alle Benutzer aktiviert, jedoch nur als Ziel für die Kommunikation mit der Pilotgruppe von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="016ff-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-directly-through-the-office-365-admin-center"></a><span data-ttu-id="016ff-108">Verwalten von direkt über das Office 365 Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="016ff-108">Manage directly through the Office 365 admin center</span></span>

<span data-ttu-id="016ff-109">Teams auf Benutzerebene Lizenzen werden direkt über die Office 365 Admin Center Benutzer Verwaltungsschnittstellen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="016ff-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="016ff-110">Ein Administrator kann Lizenzen für neue Benutzer, wenn neue Benutzerkonten erstellt werden, oder Benutzer mit vorhandenen Konten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="016ff-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="016ff-111">Der Administrator muss Office 365 globaler Administrator oder Benutzerverwaltungsadministrator Berechtigungen zum Verwalten von Lizenzen für Microsoft-Teams verfügen.</span><span class="sxs-lookup"><span data-stu-id="016ff-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="016ff-p103">Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="016ff-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="016ff-115">Eine Benutzerlizenz Teams kann jederzeit deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="016ff-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="016ff-116">Nachdem die Lizenz deaktiviert ist, wird der Benutzerzugriff auf Microsoft-Teams, verhindert werden, und der Benutzer werden nicht mehr Teams in die Office 365-app-Start "und" Homepage finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="016ff-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center mit ausgewählter Option „Microsoft Teams“](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="016ff-118">Verwalten von über die PowerShell</span><span class="sxs-lookup"><span data-stu-id="016ff-118">Manage via PowerShell</span></span>

<span data-ttu-id="016ff-119">Das Aktivieren und Deaktivieren von Microsoft Teams als Arbeitsauslastungslizenz über PowerShell funktioniert genau wie bei jeder anderen Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="016ff-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="016ff-120">Der Name des Dienstplans für Microsoft Teams lautet TEAMS1.</span><span class="sxs-lookup"><span data-stu-id="016ff-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="016ff-121">(Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)</span><span class="sxs-lookup"><span data-stu-id="016ff-121">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="016ff-122">**Beispiel:** Unten ist nur ein schnelles Beispiel auf wie würden Sie Teams für alle Benutzer in einem bestimmten Lizenztyp deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="016ff-122">**Sample:** Below is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="016ff-123">Sie müssen dies zuerst tun und dann den Lizenztyp für die Benutzer, die im Rahmen von Pilottests Zugriff haben sollen, einzeln aktivieren.</span><span class="sxs-lookup"><span data-stu-id="016ff-123">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="016ff-124">Um die in Ihrer Organisation vorhandenen Abonnementtypen anzuzeigen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="016ff-124">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="016ff-125">Tragen Sie den Namen Ihres Plans einschließlich des Organisationsnamens und des Plans für Ihre Bildungseinrichtung ein (zum Beispiel „ContosoSchool:ENTERPRISEPACK_STUDENT“), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="016ff-125">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="016ff-126">Führen Sie zum Deaktivieren von Teams für alle Benutzer mit einer aktiven Lizenz für den benannten Plan den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="016ff-126">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="016ff-128">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="016ff-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="016ff-129">Was ist Ihre Organisation Planen von Teams Onboarding in der gesamten Organisation?</span><span class="sxs-lookup"><span data-stu-id="016ff-129">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="016ff-130">(Pilot- oder öffnen)</span><span class="sxs-lookup"><span data-stu-id="016ff-130">(Pilot or Open)</span></span></li></ul>         |
|![Symbol für „Nächste Schritte“](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="016ff-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="016ff-132">Next Steps</span></span>         |<ul><li><span data-ttu-id="016ff-133">Wenn Sie das Onboarding über ein geschlossenes Pilotprojekt durchführen, entscheiden Sie, ob Sie dies über die Lizenzierung oder durch zielgerichtete Kommunikation tun möchten.</span><span class="sxs-lookup"><span data-stu-id="016ff-133">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="016ff-134">Je nach Entscheidung, dauern evaluieren Schritte aus, um sicherzustellen, nur Benutzer, die auf Teams (falls erforderlich) zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="016ff-134">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="016ff-135">Dokumentieren Sie die Richtlinien für welche Benutzer stellen, die werden (oder keine) haben Zugriff auf Teams.</span><span class="sxs-lookup"><span data-stu-id="016ff-135">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a><span data-ttu-id="016ff-136">Verwalten von Office-Sku-Switch-Ebene</span><span class="sxs-lookup"><span data-stu-id="016ff-136">Manage via Office Sku level switch</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  <span data-ttu-id="016ff-137">Melden Sie sich mit einem Konto mit globalen Administratorberechtigungen beim [Office 365 Admin Center](https://go.microsoft.com/fwlink/?linkid=854614) an.</span><span class="sxs-lookup"><span data-stu-id="016ff-137">Sign in to the [Office 365 Admin center](https://go.microsoft.com/fwlink/?linkid=854614) with an account that has Global Administrator privileges.</span></span>

2.  <span data-ttu-id="016ff-138">Wechseln Sie zu **Einstellungen** > **Dienste und Add-Ins**.</span><span class="sxs-lookup"><span data-stu-id="016ff-138">Go to **Settings** > **Services & add-ins**.</span></span>

    ![<span data-ttu-id="016ff-139">Screenshot des Abschnitts „Einstellungen“ im Office 365 Admin Center mit ausgewählter Option „Dienste und Add-Ins“</span><span class="sxs-lookup"><span data-stu-id="016ff-139">Screenshot of the Settings section in the Office 365 admin center with Services & add-ins selected.</span></span> ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  <span data-ttu-id="016ff-140">Klicken Sie auf der Seite „Dienste und Add-Ins“ auf **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="016ff-140">On the Services & add-ins page, click **Microsoft Teams**.</span></span>

    ![Screenshot der Seite „Dienste und Add-Ins“ mit ausgewählter Option „Microsoft Teams“](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  <span data-ttu-id="016ff-142">Um Microsoft Teams für die Organisation zu aktivieren, verwenden Sie die Lizenzauswahl. Wählen Sie die einzelnen Lizenzen aus, legen Sie die Umschaltfläche auf **Ein** fest, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="016ff-142">To turn on Teams for the organization use the license picker and select each license then set the toggle to **On** and then click **Save**.</span></span>

    ![Screenshot der Seite mit den Microsoft Teams-Einstellungen, auf der die Umschaltfläche auf „Ein“ festgelegt ist, um Microsoft Teams zu aktivieren](media/Services-and-addins-control-Microsoft-Teams.PNG)

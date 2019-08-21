---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
f1keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: Hier erfahren Sie, wie Sie den Zugriff auf Benutzerebene pro Benutzer aktivieren oder deaktivieren.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc5d5b7b97a8105fd8ecc3776479249175962d14
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483604"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="f2264-103">Verwalten des Benutzerzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2264-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f2264-104">Auf Benutzerebene kann der Zugriff auf Microsoft Teams für einzelne Benutzer aktiviert oder deaktiviert werden, indem die Microsoft Teams-Produktlizenz zugewiesen oder entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="f2264-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="f2264-105">Verwenden Sie im Team Admin Center verwaltete Nachrichtenrichtlinien, um zu steuern, welche Chat-und Kanal-Messaging Features Benutzern in Teams zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f2264-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="f2264-106">Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Messagingrichtlinien für Personen in Ihrer Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2264-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="f2264-107">Weitere Informationen finden Sie unter [Verwalten von Nachrichtenrichtlinien in Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f2264-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="f2264-108">Microsoft empfiehlt, dass Sie Teams für alle Benutzer in einem Unternehmen aktivieren, damit Teams organisch für Projekte und andere dynamische Initiativen ausgebildet werden können.</span><span class="sxs-lookup"><span data-stu-id="f2264-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="f2264-109">Auch wenn Sie sich für ein Pilotprojekt entscheiden, ist es möglicherweise weiterhin hilfreich, Teams für alle Benutzer aktiviert zu halten, aber nur die Kommunikation mit der Pilotgruppe von Benutzern zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f2264-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="f2264-110">Verwalten von Teams über das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="f2264-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="f2264-111">Teams auf Benutzerebene Lizenzen werden direkt über die Benutzer Verwaltungsschnittstellen von Microsoft 365 Admin Center verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f2264-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="f2264-112">Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder für Benutzer mit vorhandenen Konten.</span><span class="sxs-lookup"><span data-stu-id="f2264-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="f2264-113">Der Administrator muss über die Administratorrechte von Office 365 Global Administrator oder Benutzerverwaltung verfügen, um Microsoft Teams-Lizenzen verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="f2264-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="f2264-p104">Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f2264-p104">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Screenshot des Abschnitts "Produktlizenzen" im Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="f2264-117">Eine Benutzerlizenz für Teams kann jederzeit deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f2264-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="f2264-118">Nachdem die Lizenz deaktiviert wurde, wird der Zugriff von Benutzern auf Microsoft Teams verhindert, und der Benutzer kann keine Teams mehr im Office 365-App-Startfeld und auf der Startseite anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2264-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Screenshot mit den im Abschnitt "Produktlizenzen" ausgewählten Teams](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="f2264-120">Verwalten über PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2264-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2264-121">New-MsolLicenseOptions aktiviert alle Dienste, die zuvor deaktiviert wurden, es sei denn, explictitly identitied in Ihrem angepassten Skript.</span><span class="sxs-lookup"><span data-stu-id="f2264-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="f2264-122">Wenn Sie beispielsweise beide Exchange #a0 Sway deaktiviert lassen möchten, während Sie Additonally deaktivieren, müssten Sie dies im Skript INLCUDE oder beide Exchange-#a1 Sway wird für die von Ihnen identifizierten Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f2264-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="f2264-123">Wenn Sie eine GUI verwenden möchten, um diese Funktionalität zu verwalten, lesen Sie: [Office 365-Lizenz Berichterstattung und-Verwaltungs Tool – Zuweisen von Entfernen von Lizenzen in Massen](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="f2264-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="f2264-124">Das Aktivieren und Deaktivieren von Microsoft Teams als Arbeitsauslastungslizenz über PowerShell funktioniert genau wie bei jeder anderen Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="f2264-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="f2264-125">Der Name des Dienstplans für Microsoft Teams lautet TEAMS1.</span><span class="sxs-lookup"><span data-stu-id="f2264-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="f2264-126">Für gcc lautet der Service Plan Name TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="f2264-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="f2264-127">Für gcc ist der Service Plan Name TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="f2264-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="f2264-128">Für DoD lautet der Service Plan Name TEAMS_DOD (Weitere Informationen finden Sie unter [Deaktivieren des Zugriffs auf Dienste mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) .)</span><span class="sxs-lookup"><span data-stu-id="f2264-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="f2264-129">**Beispiel:** Im folgenden sehen Sie nur ein kurzes Beispiel, wie Sie Teams für jeden in einem bestimmten Lizenztyp deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f2264-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="f2264-130">Sie müssen dies zuerst tun und dann den Lizenztyp für die Benutzer, die im Rahmen von Pilottests Zugriff haben sollen, einzeln aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f2264-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="f2264-131">Um die in Ihrer Organisation vorhandenen Abonnementtypen anzuzeigen, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f2264-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="f2264-132">Tragen Sie den Namen Ihres Plans einschließlich des Organisationsnamens und des Plans für Ihre Bildungseinrichtung ein (zum Beispiel „ContosoSchool:ENTERPRISEPACK_STUDENT“), und führen Sie dann die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f2264-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="f2264-133">Führen Sie den folgenden Befehl aus, um Teams für alle Benutzer mit einer aktiven Lizenz für Ihren benannten Plan zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f2264-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="f2264-135">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="f2264-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="f2264-136">Was ist der Plan Ihrer Organisation für Teams, die sich in der gesamten Organisation an Bord befinden?</span><span class="sxs-lookup"><span data-stu-id="f2264-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="f2264-137">(Pilot oder Open)</span><span class="sxs-lookup"><span data-stu-id="f2264-137">(Pilot or Open)</span></span></li></ul>         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="f2264-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f2264-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="f2264-140">Wenn Sie über ein geschlossenes Pilot Projekt an Bord sind, entscheiden Sie, ob Sie dies über eine Lizenzierung oder gezielte Kommunikation tun möchten.</span><span class="sxs-lookup"><span data-stu-id="f2264-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="f2264-141">Führen Sie je nach Entscheidung die erforderlichen Schritte aus, um sicherzustellen, dass nur Pilot Benutzer, die auf Teams zugreifen dürfen (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="f2264-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="f2264-142">Dokumentieren Sie die Richtlinien für die Benutzer, die Zugriff auf Teams haben (oder nicht).</span><span class="sxs-lookup"><span data-stu-id="f2264-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="f2264-143">Verwalten von Teams auf der Office 365-Mandantenebene</span><span class="sxs-lookup"><span data-stu-id="f2264-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]


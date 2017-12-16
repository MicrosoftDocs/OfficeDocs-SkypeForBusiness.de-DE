---
title: Verwalten des Benutzerzugriffs auf Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Hier erfahren Sie, wie Sie den Zugriff auf Benutzerebene pro Benutzer aktivieren oder deaktivieren.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5bf8a487a7931ff91e754c1e84839b75535ca3c9
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="0415c-103">Verwalten des Benutzerzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0415c-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="0415c-104">Auf Benutzerebene kann der Zugriff auf Microsoft Teams pro Benutzer aktiviert oder deaktiviert werden, indem die Produktlizenz für Microsoft Teams zugewiesen oder entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="0415c-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="0415c-105">Zurzeit gibt es keine Richtlinienoptionen für das Aktivieren oder Deaktivieren von Microsoft Teams oder einer Teilmenge der Funktionen von Microsoft Teams für einzelne Benutzer außerhalb der Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="0415c-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>



> [!NOTE]
><span data-ttu-id="0415c-p101">Microsoft empfiehlt, Microsoft Teams für alle Benutzer in einer Firma zu aktivieren, damit Teams organisch für Projekte und andere dynamische Aktivitäten gebildet werden können. Auch wenn Sie sich für ein Pilotprojekt entscheiden, kann es hilfreich sein, Microsoft Teams für alle Benutzer aktiviert zu lassen, während Sie die Kommunikation auf die Pilotbenutzergruppe beschränken.</span><span class="sxs-lookup"><span data-stu-id="0415c-p101">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives. Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

<span data-ttu-id="0415c-p102">Microsoft Teams-Lizenzen auf Benutzerebene werden direkt über die Benutzerverwaltungsschnittstellen im Office 365 Admin Center verwaltet. Ein Administrator kann neuen Benutzern Lizenzen zuweisen, wenn neue Benutzerkonten erstellt werden, oder Benutzern mit vorhandenen Konten Lizenzen zuweisen. Der Administrator muss über Berechtigungen eines globalen Office 365-Administrators oder eines Benutzerverwaltungsadministrators verfügen, um Microsoft Teams-Lizenzen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0415c-p102">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces. An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts. The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="0415c-p103">Wenn einem Benutzer eine Lizenz-SKU wie E3 oder E5 zugewiesen wird, wird automatisch eine Microsoft Teams-Lizenz zugewiesen, und der Benutzer wird für Microsoft Teams aktiviert. Administratoren können alle Office 365-Dienste und -Lizenzen präzise steuern, und die Microsoft Teams-Lizenz für einen bestimmten Benutzer oder eine bestimmte Gruppe von Benutzern kann aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0415c-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="0415c-p104">Eine Microsoft Teams-Benutzerlizenz kann jederzeit deaktiviert werden. Wenn die Lizenz deaktiviert ist, wird der Zugriff der Benutzer auf Microsoft Teams verhindert, und sie können Microsoft Teams nicht mehr im App-Startprogramm und auf der Homepage von Office 365 sehen.</span><span class="sxs-lookup"><span data-stu-id="0415c-p104">A Microsoft Teams user license can be disabled at any time. Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Screenshot des Abschnitts „Produktlizenzen“ im Office 365 Admin Center mit ausgewählter Option „Microsoft Teams“](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="0415c-p105">Neben dem Office 365 Admin Center können Office 365-Administratoren auch Office 365 PowerShell verwenden, um Benutzerlizenzen zuzuweisen und zu entfernen. Verwenden Sie die folgende Syntax, um eine Lizenz zu einem Benutzer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="0415c-p105">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses. To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="0415c-119">Set-MsolUserLicense -UserPrincipalName "\<Konto\>" -AddLicenses "\<AccountSkuId\>"</span><span class="sxs-lookup"><span data-stu-id="0415c-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="0415c-120">Im folgenden Beispiel wird eine Lizenz aus dem Lizenzplan „litwareinc:ENTERPRISEPACK“ (Office 365 Enterprise E3) dem nicht über eine Lizenz verfügenden Benutzer „belindan@litwareinc.com“ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0415c-120">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="0415c-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="0415c-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="0415c-122">Weitere Details und Beispiele finden Sie unter [*Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span><span class="sxs-lookup"><span data-stu-id="0415c-122">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="0415c-123">Mit der folgenden Syntax entfernen Sie Lizenzen von einem vorhandenen Benutzerkonto:</span><span class="sxs-lookup"><span data-stu-id="0415c-123">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="0415c-124">Set-MsolUserLicense -UserPrincipalName \<Konto\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span><span class="sxs-lookup"><span data-stu-id="0415c-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="0415c-125">Im folgenden Beispiel wird die Lizenz „litwareinc:ENTERPRISEPACK“ (Office 365 Enterprise E3) vom Benutzerkonto „BelindaN@litwareinc.com“ entfernt.</span><span class="sxs-lookup"><span data-stu-id="0415c-125">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="0415c-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="0415c-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="0415c-127">Weitere Details und Beispiele finden Sie unter [*Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span><span class="sxs-lookup"><span data-stu-id="0415c-127">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="0415c-129">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="0415c-129">Decision Point</span></span>         |<ul><li><span data-ttu-id="0415c-p106">Wie sieht der Plan Ihrer Organisation für das organisationsweite Microsoft Teams-Onboarding aus? (Pilotprojekt oder offen)</span><span class="sxs-lookup"><span data-stu-id="0415c-p106">What is your organization’s plan for Microsoft Teams onboarding across the organization?  (Pilot or Open)</span></span></li></ul>         |
|![Symbol für „Nächste Schritte“](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="0415c-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0415c-133">Next Steps</span></span>         |<ul><li><span data-ttu-id="0415c-134">Wenn Sie das Onboarding über ein geschlossenes Pilotprojekt durchführen, entscheiden Sie, ob Sie dies über die Lizenzierung oder durch zielgerichtete Kommunikation tun möchten.</span><span class="sxs-lookup"><span data-stu-id="0415c-134">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="0415c-135">Stellen Sie abhängig von der Entscheidung durch die entsprechenden Schritte sicher, dass nur Pilotbenutzer auf Microsoft Teams zugreifen dürfen (wenn dies notwendig ist).</span><span class="sxs-lookup"><span data-stu-id="0415c-135">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="0415c-136">Dokumentieren Sie unten die Richtlinien dafür, welche Benutzer auf Microsoft Teams zugreifen dürfen (oder nicht zugreifen dürfen).</span><span class="sxs-lookup"><span data-stu-id="0415c-136">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |

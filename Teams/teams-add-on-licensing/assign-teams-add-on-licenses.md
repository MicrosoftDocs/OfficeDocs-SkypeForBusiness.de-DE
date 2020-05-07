---
title: Zuweisen von Teams-Add-on-Lizenzen zu Benutzern
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Erfahren Sie, wie Sie Benutzern für Features wie Audiokonferenz, Telefon System und Anrufpläne Teams Add-on-Lizenzen zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c7c455628f7595e1517fbd0cef8d2edc454ffbb
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042775"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="29246-103">Zuweisen von Teams-Add-on-Lizenzen zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="29246-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="29246-104">Add-on-Lizenzen sind Lizenzen für bestimmte Teams-Features wie Audiokonferenzen, Telefonsysteme und Anrufpläne.</span><span class="sxs-lookup"><span data-stu-id="29246-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="29246-105">In diesem Artikel wird beschrieben, wie Sie einzelnen Benutzern Add-on-Lizenzen und große Gruppen von Benutzern massenweise zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="29246-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="29246-106">Weitere Informationen finden Sie unter [Teams-Add-on-Lizenzierung](microsoft-teams-add-on-licensing.md) für Teamfunktionen, die mit Add-on-Lizenzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="29246-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="29246-107">Darüber hinaus finden Sie Informationen darüber, welche Lizenzen Sie kaufen müssen und wie Sie Sie erwerben (je nach Plan), sodass Benutzer Features wie Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihres Unternehmens erhalten können.</span><span class="sxs-lookup"><span data-stu-id="29246-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="29246-108">Nachdem Sie sich entschieden haben, welche Features für Ihre Benutzer zur Verfügung stehen, weisen Sie Ihnen die Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="29246-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="29246-109">Sie können das Microsoft 365 Admin Center oder PowerShell verwenden, um Benutzern in Ihrer Organisation Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="29246-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="29246-110">Sie müssen ein globaler Administrator oder Benutzer Verwaltungs Administrator sein, um Lizenzen verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="29246-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="29246-111">Was Sie wissen müssen, bevor Sie eine Telefonanlage, einen Anrufplan und Kommunikationsguthaben-Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="29246-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="29246-112">Bevor Sie beginnen, sehen Sie sich Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="29246-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="29246-113">Wenn Sie eine lokale PSTN-Konnektivität (Public Switched Telephone Network) für Hybrid Benutzer verwenden, müssen Sie nur eine Telefon System Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="29246-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="29246-114">Weisen Sie keine Anruf Plan Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="29246-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="29246-115">Aufgrund der Wartezeit zwischen Microsoft 365 und Microsoft Teams kann es bis zu 24 Stunden dauern, bis ein Benutzer einen Anrufplan zugewiesen hat, nachdem Sie eine Lizenz zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="29246-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="29246-116">Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen ist, [wenden Sie sich an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="29246-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="29246-117">Sie erhalten eine Fehlermeldung, wenn Sie die richtige Anzahl von Lizenzen nicht gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="29246-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="29246-118">Wenn Sie weitere Lizenzen für den Anrufplan kaufen müssen, wählen Sie die Option zum kaufen von mehr aus.</span><span class="sxs-lookup"><span data-stu-id="29246-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="29246-119">Auch wenn ihren Benutzern Enterprise E5-Lizenzen zugewiesen wurden, müssen Sie Ihnen weiterhin [Kommunikationsguthaben](../what-are-communications-credits.md) -Lizenzen zuweisen, wenn Sie Anrufe tätigen oder empfangen möchten.</span><span class="sxs-lookup"><span data-stu-id="29246-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="29246-120">Nachdem Sie Ihren Benutzern Anrufplan-oder Kommunikationsguthaben Lizenzen zugewiesen haben, müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="29246-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="29246-121">Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](../set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="29246-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="29246-122">Verwenden des Microsoft 365 admin Centers</span><span class="sxs-lookup"><span data-stu-id="29246-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="29246-123">Verwenden Sie das Microsoft 365 Admin Center, um einzelnen Benutzern oder kleinen Gruppen von Benutzern gleichzeitig Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="29246-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="29246-124">Sie können Lizenzen auf der Seite " **Lizenzen** " (für bis zu 20 Benutzer gleichzeitig) oder auf der Seite " **aktive Benutzer** " zuweisen.</span><span class="sxs-lookup"><span data-stu-id="29246-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="29246-125">Die Methode, die Sie auswählen, hängt davon ab, ob Sie Produktlizenzen für bestimmte Benutzer verwalten oder Benutzerlizenzen für bestimmte Produkte verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="29246-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span> 

<span data-ttu-id="29246-126">Eine Schritt-für-Schritt-Anleitung finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="29246-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="29246-127">Wenn Sie Lizenzen für eine große Anzahl von Benutzern, wie etwa Hunderte oder Tausende von Benutzern, zuweisen müssen, verwenden Sie PowerShell oder [Gruppenbasierte Lizenzierung in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="29246-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="29246-128">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="29246-128">Using PowerShell</span></span>

<span data-ttu-id="29246-129">Verwenden von PowerShell zum Zuweisen von Lizenzen für Benutzer in Massen.</span><span class="sxs-lookup"><span data-stu-id="29246-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="29246-130">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="29246-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="29246-131">Beispielskript</span><span class="sxs-lookup"><span data-stu-id="29246-131">Example script</span></span>

<span data-ttu-id="29246-132">Im folgenden finden Sie ein Beispiel für die Verwendung eines Skripts zum Zuweisen von Lizenzen für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="29246-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="29246-133">Installieren Sie die 64-Bit-Version des [Microsoft Online Services-Anmelde Assistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="29246-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="29246-134">Installieren Sie das Microsoft Azure Active Directory-Modul für Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29246-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="29246-135">Öffnen Sie eine erweiterte Windows PowerShell-Eingabeaufforderung (Windows PowerShell als Administrator ausführen).</span><span class="sxs-lookup"><span data-stu-id="29246-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="29246-136">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="29246-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="29246-137">Wenn Sie aufgefordert werden, den NuGet-Anbieter zu installieren, geben Sie **Y**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="29246-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="29246-138">Wenn Sie aufgefordert werden, das Modul von PSGallery zu installieren, geben Sie **Y**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="29246-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="29246-139">Führen Sie an der Windows PowerShell-Eingabeaufforderung das folgende Skript aus, um Ihren Benutzern Lizenzen zuzuweisen, wobei \<CompanyName: License> der Name Ihrer Organisation und der Bezeichner für die Lizenz ist, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="29246-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="29246-140">Beispiel: "litwareinc: MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="29246-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="29246-141">Der Bezeichner unterscheidet sich von dem Anzeigenamen der Lizenz.</span><span class="sxs-lookup"><span data-stu-id="29246-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="29246-142">Der Bezeichner für Audiokonferenzen lautet beispielsweise MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="29246-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="29246-143">Weitere Informationen finden Sie unter [Produktnamen und SKU-IDs für die Lizenzierung](#product-names-and-sku-identifiers-for-licensing).</span><span class="sxs-lookup"><span data-stu-id="29246-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="29246-144">Um beispielsweise Microsoft 365 Enterprise 1-und Audio Conferencing-Lizenzen zuzuweisen, verwenden Sie die folgende Syntax im Skript:</span><span class="sxs-lookup"><span data-stu-id="29246-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="29246-145">Wenn Sie eine Lizenz für Microsoft Business Voice (ohne Anrufplan) zuweisen möchten, verwenden Sie die folgende Syntax im Skript:</span><span class="sxs-lookup"><span data-stu-id="29246-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="29246-146">Produktnamen und SKU-IDs für die Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="29246-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="29246-147">Nachfolgend finden Sie eine unvollständige Liste der Produktnamen und der zugehörigen SKU-Bauteilnamen, die Sie als Referenz verwenden können, wenn Sie PowerShell zum Verwalten von Lizenzen in Microsoft Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="29246-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="29246-148">Weitere Informationen finden Sie unter [Anzeigen von Lizenzen und Diensten mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Produktnamen und Service Plan-IDs für Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)und [Education-SKU-Referenz](../sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="29246-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="29246-149">Produktname</span><span class="sxs-lookup"><span data-stu-id="29246-149">Product name</span></span>| <span data-ttu-id="29246-150">SKU-Teilename</span><span class="sxs-lookup"><span data-stu-id="29246-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="29246-151">Microsoft Enterprise E5 (mit Telefon System)</span><span class="sxs-lookup"><span data-stu-id="29246-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="29246-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="29246-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="29246-153">Microsoft Enterprise E5 (ohne Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="29246-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="29246-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="29246-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="29246-155">Microsoft Enterprise E5 (mit Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="29246-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="29246-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="29246-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="29246-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="29246-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="29246-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="29246-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="29246-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="29246-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="29246-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="29246-160">STANDARDPACK</span></span> |
| <span data-ttu-id="29246-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="29246-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="29246-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="29246-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="29246-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="29246-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="29246-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="29246-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="29246-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="29246-165">Microsoft 365 Business</span></span> | <span data-ttu-id="29246-166">Spb</span><span class="sxs-lookup"><span data-stu-id="29246-166">SPB</span></span>|
| <span data-ttu-id="29246-167">Microsoft Business Voice (Kanada)</span><span class="sxs-lookup"><span data-stu-id="29246-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="29246-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="29246-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="29246-169">Microsoft Business Voice (Vereinigtes Königreich)</span><span class="sxs-lookup"><span data-stu-id="29246-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="29246-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="29246-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="29246-171">Microsoft Business Voice (Vereinigte Staaten)</span><span class="sxs-lookup"><span data-stu-id="29246-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="29246-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="29246-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="29246-173">Microsoft Business-VoIP (ohne Anrufplan)</span><span class="sxs-lookup"><span data-stu-id="29246-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="29246-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="29246-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="29246-175">Microsoft Business-VoIP (ohne Anrufplan) für die Vereinigten Staaten</span><span class="sxs-lookup"><span data-stu-id="29246-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="29246-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="29246-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="29246-177">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="29246-177">Audio Conferencing</span></span> | <span data-ttu-id="29246-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="29246-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="29246-179">Audio-Konferenzgebühren pro Minute (im Voraus bezahlen)</span><span class="sxs-lookup"><span data-stu-id="29246-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="29246-180">*Erfordert das Einrichten und Aktivieren von Kommunikationsguthaben.*</span><span class="sxs-lookup"><span data-stu-id="29246-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="29246-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="29246-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="29246-182">Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="29246-182">Phone System</span></span> | <span data-ttu-id="29246-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="29246-183">MCOEV</span></span> |
| <span data-ttu-id="29246-184">Plan für Inlands-und Auslandsgespräche</span><span class="sxs-lookup"><span data-stu-id="29246-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="29246-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="29246-185">MCOPSTN2</span></span> |
| <span data-ttu-id="29246-186">Plan für Inlandsanrufe (3000 Minuten pro Nutzer/Monat für US/PR/ca, 1200 Minuten pro Nutzer/Monat für EU-Länder)</span><span class="sxs-lookup"><span data-stu-id="29246-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="29246-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="29246-187">MCOPSTN1</span></span> |
| <span data-ttu-id="29246-188">Plan für Inlandsanrufe (120 Minuten pro Nutzer/Monat für jedes Land)</span><span class="sxs-lookup"><span data-stu-id="29246-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="29246-189">*Dieser Plan steht in den Vereinigten Staaten nicht zur Verfügung.*</span><span class="sxs-lookup"><span data-stu-id="29246-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="29246-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="29246-190">MCOPSTN5</span></span> |
| <span data-ttu-id="29246-191">Plan für Inlandsanrufe (240 Minuten pro Nutzer/Monat für jedes Land)</span><span class="sxs-lookup"><span data-stu-id="29246-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="29246-192">*Dieser Plan steht in den Vereinigten Staaten nicht zur Verfügung.*</span><span class="sxs-lookup"><span data-stu-id="29246-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="29246-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="29246-193">MCOPSTN6</span></span> |
| <span data-ttu-id="29246-194">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="29246-194">Communications Credits</span></span> | <span data-ttu-id="29246-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="29246-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="29246-196">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="29246-196">Related topics</span></span>

- [<span data-ttu-id="29246-197">Lizenzierung für Teams-Add-On</span><span class="sxs-lookup"><span data-stu-id="29246-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="29246-198">Verwalten des Benutzerzugriffs auf Teams</span><span class="sxs-lookup"><span data-stu-id="29246-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="29246-199">Anzeigen von Lizenzen und Diensten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="29246-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="29246-200">Produktnamen und Serviceplanbezeichner für die Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="29246-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="29246-201">Education-SKU-Referenz</span><span class="sxs-lookup"><span data-stu-id="29246-201">Education SKU reference</span></span>](../sku-reference-edu.md)
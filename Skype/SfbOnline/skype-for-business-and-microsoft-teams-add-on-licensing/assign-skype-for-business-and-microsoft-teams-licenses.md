---
title: Zuweisen von Skype for Business-Lizenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Erfahren Sie, wie Sie Skype for Business-Lizenzen für Telefonsysteme, Audiokonferenzen, Anrufpläne und Kommunikationsguthaben zuweisen. '
ms.openlocfilehash: f2b2e2ad4952b55fade7e0b8eddb1755ea3f2cea
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887814"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="54caa-103">Zuweisen von Skype for Business-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="54caa-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="54caa-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span><span class="sxs-lookup"><span data-stu-id="54caa-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="54caa-105">It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="54caa-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54caa-106">Unter [Skype for Business-Add-on-Lizenzierung](skype-for-business-and-microsoft-teams-add-on-licensing.md) finden Sie Informationen dazu, welche Lizenzen Sie kaufen müssen und wie Sie Sie **erwerben** – je nach Ihrem Office 365-Plan –, damit Benutzer Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihres Unternehmens erhalten.</span><span class="sxs-lookup"><span data-stu-id="54caa-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="54caa-107">Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="54caa-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="54caa-108">Was Sie wissen müssen, bevor Sie Audiokonferenz-, Telefon System-und Anruf Plan Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="54caa-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="54caa-p102">**Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine **Telefonsystemlizenz** zuweisen. Weisen Sie **KEINEN** Anrufplan zu.</span><span class="sxs-lookup"><span data-stu-id="54caa-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="54caa-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="54caa-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="54caa-p104">**Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.</span><span class="sxs-lookup"><span data-stu-id="54caa-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="54caa-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="54caa-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="54caa-118">Zuweisen einer Telefonsystem- und Anrufplanlizenz für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="54caa-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="54caa-p106">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="54caa-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="54caa-121">Massenzuweisen von Telefonsystem- und Anrufplanlizenzen</span><span class="sxs-lookup"><span data-stu-id="54caa-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="54caa-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="54caa-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="54caa-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="54caa-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="54caa-128">Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="54caa-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="54caa-129">In diesem Beispiel wird eine **Enterprise E3-Lizenz** zusammen mit einer Lizenz für **Telefonsysteme** und einer Lizenz für einen **Plan für Inlandsanrufe** zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="54caa-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="54caa-130">Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert (siehe **Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan** nach dem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="54caa-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="54caa-131">Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan</span><span class="sxs-lookup"><span data-stu-id="54caa-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="54caa-132">**Produktname**</span><span class="sxs-lookup"><span data-stu-id="54caa-132">**Product name**</span></span>|<span data-ttu-id="54caa-133">**SKU-Teilename**</span><span class="sxs-lookup"><span data-stu-id="54caa-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="54caa-134">Enterprise E5 (mit Telefonsystem)</span><span class="sxs-lookup"><span data-stu-id="54caa-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="54caa-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="54caa-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="54caa-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="54caa-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="54caa-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="54caa-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="54caa-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="54caa-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="54caa-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="54caa-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="54caa-140">Skype for Business Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="54caa-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="54caa-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="54caa-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="54caa-142">Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="54caa-142">Phone System</span></span>  <br/> |<span data-ttu-id="54caa-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="54caa-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="54caa-144">Plan für Auslandsanrufe</span><span class="sxs-lookup"><span data-stu-id="54caa-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="54caa-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="54caa-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="54caa-146">Plan für Inlandsanrufe (3000 min US/1200 min EU-Pläne)</span><span class="sxs-lookup"><span data-stu-id="54caa-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="54caa-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="54caa-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="54caa-148">Plan für Inlandsanrufe (Anruf Plan für 120 min.)</span><span class="sxs-lookup"><span data-stu-id="54caa-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="54caa-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="54caa-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="54caa-150">Plan für Inlandsanrufe (Anruf Plan für 240 min.)</span><span class="sxs-lookup"><span data-stu-id="54caa-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="54caa-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="54caa-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="54caa-152">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="54caa-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="54caa-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="54caa-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="54caa-154">Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="54caa-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="54caa-155">Wichtige Informationen vor dem Zuweisen von Lizenzen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="54caa-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="54caa-p109">**Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für **Audiokonferenzen** zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.</span><span class="sxs-lookup"><span data-stu-id="54caa-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="54caa-158">Nächste Schritte: Nachdem Sie Lizenzen für **Audiokonferenzen** zugewiesen haben, müssen Sie einen Audiokonferenz-Anbieter zuweisen.</span><span class="sxs-lookup"><span data-stu-id="54caa-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="54caa-159">Siehe [Microsoft als Anbieter von Audiokonferenzen zuweisen].</span><span class="sxs-lookup"><span data-stu-id="54caa-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="54caa-160">Zuweisen einer Lizenz für Audiokonferenzen zu einem einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="54caa-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="54caa-p111">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="54caa-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="54caa-163">Massenzuweisen von Lizenzen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="54caa-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="54caa-164">Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="54caa-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="54caa-p112">Laden Sie das **Windows Azure Active Directory-Modul herunter und installieren Sie es.** Anweisungen zum Herunterladen und die cmdlet-Syntax finden Sie unter[Verwalten von Azure AD mithilfe der Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="54caa-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="54caa-167">Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="54caa-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="54caa-168">Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert.</span><span class="sxs-lookup"><span data-stu-id="54caa-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="54caa-169">Sehen Sie sich die [Produktnamen oder SKUs für Audiokonferenzen](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) an, die für die Skripterstellung für alle Produktnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54caa-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="54caa-170">In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Audiokonferenzen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="54caa-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
    #Example of text file:
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
        }
    ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="54caa-171">Für die Skripterstellung verwendete Produktnamen oder SKUs für Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="54caa-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="54caa-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="54caa-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="54caa-173">**Produktname**</span><span class="sxs-lookup"><span data-stu-id="54caa-173">**Product name**</span></span>|<span data-ttu-id="54caa-174">**SKU-Teilename**</span><span class="sxs-lookup"><span data-stu-id="54caa-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="54caa-175">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="54caa-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="54caa-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="54caa-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="54caa-177">Skype for Business Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="54caa-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="54caa-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="54caa-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="54caa-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="54caa-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="54caa-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="54caa-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="54caa-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="54caa-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="54caa-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="54caa-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="54caa-183">Enterprise E5 (ohne Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="54caa-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="54caa-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="54caa-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="54caa-185">Enterprise E5 (mit Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="54caa-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="54caa-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="54caa-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="54caa-187">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="54caa-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="54caa-188">Wichtige Informationen vor dem Zuweisen von Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="54caa-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="54caa-189">**Enterprise E5-Kunden**: selbst wenn ihren Benutzern Enterprise E5-Lizenzen zugewiesen sind, empfehlen wir Ihnen weiterhin, Ihnen **Kommunikationsguthaben** -Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="54caa-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="54caa-190">**Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="54caa-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="54caa-191">Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="54caa-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="54caa-192">Zuweisen einer Lizenz für Guthaben für Kommunikationen zu einem einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="54caa-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="54caa-193">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="54caa-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="54caa-194">Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="54caa-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="54caa-195">Zuweisen von Lizenzen für Kommunikations Kredite in loser Schüttung</span><span class="sxs-lookup"><span data-stu-id="54caa-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="54caa-196">Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für **Audiokonferenzen** an.</span><span class="sxs-lookup"><span data-stu-id="54caa-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="54caa-197">Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für **Guthaben für Kommunikationen**.</span><span class="sxs-lookup"><span data-stu-id="54caa-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="54caa-198">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="54caa-198">Related topics</span></span>
  
[<span data-ttu-id="54caa-199">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="54caa-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="54caa-200">Hinzufügen und Verwalten von Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="54caa-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 

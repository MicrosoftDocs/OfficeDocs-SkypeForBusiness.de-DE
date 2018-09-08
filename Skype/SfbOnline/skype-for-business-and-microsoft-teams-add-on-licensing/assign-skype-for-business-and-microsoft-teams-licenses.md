---
title: Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Erfahren Sie, wie Sie Skype for Business-Lizenzen für Telefonsysteme, Audiokonferenzen, Anrufpläne und Kommunikationsguthaben zuweisen. '
ms.openlocfilehash: 1131d8daf4b865d648f51b011fc8819dee55f6b9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883502"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="d22ef-103">Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="d22ef-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="d22ef-104">Dieser Artikel enthält Tipps zum Zuweisen von Lizenzen für Ihre Benutzer für Funktionen wie Audiokonferenzen Telefonsystem und plant aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="d22ef-105">Außerdem werden Skripts für die Massenzuweisung von Lizenzen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d22ef-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d22ef-106">Informationen finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-on-Lizenzierung](skype-for-business-and-microsoft-teams-add-on-licensing.md) zu **kaufen** und welche Lizenzen, die Sie kaufen müssen sie - je nach Ihrer Office 365 planen - damit Benutzer Audiokonferenzen und gebührenfreie Nummern anrufen erhalten Telefonnummern außerhalb Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="d22ef-106">See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="d22ef-107">Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="d22ef-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="d22ef-108">Was müssen Sie wissen, bevor Sie Audiokonferenzen, Telefonsystem und Planen der Aufruf von Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="d22ef-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="d22ef-p102">**Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?** In diesem Fall müssen Sie nur eine **Telefonsystemlizenz** zuweisen. Weisen Sie **KEINEN** Anrufplan zu.</span><span class="sxs-lookup"><span data-stu-id="d22ef-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="d22ef-112">**Latenz nach dem Zuweisen von Lizenzen**: Aufgrund der Latenz zwischen Office 365 und Skype for Business Online kann es nach dem Zuweisen einer Lizenz unter Umständen bis zu 24 Stunden dauern, bis einem Benutzer ein Anrufplan zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d22ef-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="d22ef-113">Wenn nach 24 Stunden aufrufen Planen der Benutzer zugewiesen ist nicht, nehmen Sie die [Kontakt-Unterstützung für Business-Produkte - Admin-Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="d22ef-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="d22ef-p104">**Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.</span><span class="sxs-lookup"><span data-stu-id="d22ef-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="d22ef-116">**Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="d22ef-117">Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="d22ef-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="d22ef-118">Zuweisen einer Telefonsystem- und Anrufplanlizenz für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d22ef-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="d22ef-p106">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d22ef-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="d22ef-121">Massenzuweisen von Telefonsystem- und Anrufplanlizenzen</span><span class="sxs-lookup"><span data-stu-id="d22ef-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="d22ef-122">Installieren Sie den **Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW**.</span><span class="sxs-lookup"><span data-stu-id="d22ef-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="d22ef-123">Ist das Modul nicht installiert?</span><span class="sxs-lookup"><span data-stu-id="d22ef-123">Don't have the module installed?</span></span> <span data-ttu-id="d22ef-124">Finden Sie unter [Microsoft Online Services-Anmeldeassistent für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="d22ef-125">Installieren Sie das **Windows Azure Active Directory-Modul**.</span><span class="sxs-lookup"><span data-stu-id="d22ef-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="d22ef-126">Ist das Modul nicht installiert?</span><span class="sxs-lookup"><span data-stu-id="d22ef-126">Don't have the module installed?</span></span> <span data-ttu-id="d22ef-127">Download-Anweisungen und die Syntax finden Sie unter [Verwalten von Azure Active Directory mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="d22ef-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="d22ef-128">Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="d22ef-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="d22ef-129">In diesem Beispiel wird eine **Enterprise E3-Lizenz** zusammen mit einer Lizenz für **Telefonsysteme** und einer Lizenz für einen **Plan für Inlandsanrufe** zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="d22ef-130">Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert (siehe **Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan** nach dem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="d22ef-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

  ```
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="d22ef-131">Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan</span><span class="sxs-lookup"><span data-stu-id="d22ef-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="d22ef-132">**Produktname**</span><span class="sxs-lookup"><span data-stu-id="d22ef-132">**Product name**</span></span>|<span data-ttu-id="d22ef-133">**SKU-Teilename**</span><span class="sxs-lookup"><span data-stu-id="d22ef-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d22ef-134">Enterprise E5 (mit Telefonsystem)</span><span class="sxs-lookup"><span data-stu-id="d22ef-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="d22ef-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d22ef-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="d22ef-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d22ef-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="d22ef-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d22ef-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="d22ef-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="d22ef-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="d22ef-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d22ef-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="d22ef-140">Skype for Business Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="d22ef-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="d22ef-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="d22ef-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="d22ef-142">Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="d22ef-142">Phone System</span></span>  <br/> |<span data-ttu-id="d22ef-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="d22ef-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="d22ef-144">Plan für Auslandsanrufe</span><span class="sxs-lookup"><span data-stu-id="d22ef-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="d22ef-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="d22ef-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="d22ef-146">Plan für Inlandsanrufe</span><span class="sxs-lookup"><span data-stu-id="d22ef-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="d22ef-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="d22ef-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="d22ef-148">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="d22ef-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="d22ef-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="d22ef-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="d22ef-150">Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="d22ef-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="d22ef-151">Wichtige Informationen vor dem Zuweisen von Lizenzen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="d22ef-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="d22ef-p109">**Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für **Audiokonferenzen** zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt. Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="d22ef-154">Nächste Schritte: Nachdem Sie **Audiokonferenzen** Lizenzen zuweisen möchten, müssen Sie kein Audiokonferenzanbieter zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="d22ef-155">Siehe [Microsoft als Anbieter von Audiokonferenzen zuweisen].</span><span class="sxs-lookup"><span data-stu-id="d22ef-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="d22ef-156">Zuweisen einer Lizenz für Audiokonferenzen zu einem einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d22ef-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="d22ef-p111">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d22ef-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="d22ef-159">Massenzuweisen von Lizenzen für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="d22ef-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="d22ef-160">Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="d22ef-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="d22ef-p112">Laden Sie das **Windows Azure Active Directory-Modul herunter und installieren Sie es.** Anweisungen zum Herunterladen und die cmdlet-Syntax finden Sie unter[Verwalten von Azure AD mithilfe der Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="d22ef-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="d22ef-163">Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="d22ef-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="d22ef-164">Die Lizenz- oder Produktnamen im Skript sind kursiv formatiert.</span><span class="sxs-lookup"><span data-stu-id="d22ef-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="d22ef-165">Finden Sie unter [Audiokonferenzen Produktnamen oder SKUs für das Skripting verwendet](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) für alle von der Produktnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="d22ef-165">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="d22ef-166">In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Audiokonferenzen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="d22ef-167">Für die Skripterstellung verwendete Produktnamen oder SKUs für Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="d22ef-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="d22ef-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="d22ef-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="d22ef-169">**Produktname**</span><span class="sxs-lookup"><span data-stu-id="d22ef-169">**Product name**</span></span>|<span data-ttu-id="d22ef-170">**SKU-Teilename**</span><span class="sxs-lookup"><span data-stu-id="d22ef-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d22ef-171">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="d22ef-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="d22ef-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="d22ef-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="d22ef-173">Skype for Business Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="d22ef-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="d22ef-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="d22ef-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="d22ef-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="d22ef-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="d22ef-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d22ef-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="d22ef-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d22ef-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="d22ef-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d22ef-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="d22ef-179">Enterprise E5 (ohne Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="d22ef-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="d22ef-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="d22ef-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="d22ef-181">Enterprise E5 (mit Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="d22ef-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="d22ef-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d22ef-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="d22ef-183">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="d22ef-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="d22ef-184">Wichtige Informationen vor dem Zuweisen von Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="d22ef-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="d22ef-185">**Enterprise-E5 Kunden**:, auch wenn Ihre Benutzer Enterprise E5 Lizenzen zugewiesen sind, empfohlen, dass die **Kommunikation haben** Lizenzen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="d22ef-186">**Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d22ef-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="d22ef-187">Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="d22ef-187">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="d22ef-188">Zuweisen einer Lizenz für Guthaben für Kommunikationen zu einem einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d22ef-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="d22ef-p115">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz. Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d22ef-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="d22ef-191">Zuweisen von Lizenzen in einer Sammeloperation Communications haben</span><span class="sxs-lookup"><span data-stu-id="d22ef-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="d22ef-p116">Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für **Audiokonferenzen** an. Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für **Guthaben für Kommunikationen**.</span><span class="sxs-lookup"><span data-stu-id="d22ef-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d22ef-194">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d22ef-194">Related topics</span></span>
  
[<span data-ttu-id="d22ef-195">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="d22ef-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="d22ef-196">Hinzufügen von Guthaben und Verwalten von Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="d22ef-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 

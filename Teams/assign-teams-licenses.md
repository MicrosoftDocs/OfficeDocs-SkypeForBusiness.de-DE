---
title: Zuweisen von Teams-Lizenzen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Hier erfahren Sie, wie Sie Lizenzen für Features wie Audio-Conferencing, Telefon System und Anrufpläne zuweisen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d51e2cf8a563c5094da923949c8e736aceeb864
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241883"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="3e8f4-103">Zuweisen von Microsoft Teams-Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="3e8f4-104">Sie können Ihren Benutzern Lizenzen für Funktionen wie Audio-Conferencing, Telefon System und Anrufpläne zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="3e8f4-105">In diesem Artikel wird erläutert, wie Sie diese Lizenzen in loser Schüttung und für einen einzelnen Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3e8f4-106">Informationen dazu, welche Lizenzen Sie kaufen müssen und wie Sie Sie erwerben, finden Sie in der [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) – je nach Ihrem Office 365-Plan –, damit Benutzer Audiokonferenzen, gebührenfreie Nummern und die Möglichkeit zum Anrufen von Telefonnummern außerhalb Ihres Unternehmens erhalten.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="3e8f4-107">Telefonsystem und Anrufpläne: Tipps und Skripts für das Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="3e8f4-108">Hier erfahren Sie, was Sie vor dem Zuweisen von Audiokonferenz-, Telefon System-und Anruf Plan Lizenzen wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="3e8f4-109">**Sie verwenden eine lokale PSTN-Anbindung für Hybridbenutzer?**</span><span class="sxs-lookup"><span data-stu-id="3e8f4-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="3e8f4-110">In diesem Fall müssen Sie nur eine Telefonsystemlizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="3e8f4-111">Weisen Sie KEINEN Anrufplan zu.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="3e8f4-112">**Wartezeit nach dem Zuweisen von Lizenzen**: aufgrund der Wartezeit zwischen Office 365 und Microsoft Teams kann es bis zu 24 Stunden dauern, bis ein Benutzer einen Anrufplan zugewiesen hat, nachdem Sie eine Lizenz zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="3e8f4-113">Wenn dem Benutzer nach 24 Stunden kein Anrufplan zugewiesen ist, wenden Sie [sich bitte an den Support für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="3e8f4-p104">**Fehlermeldungen**: Wenn Sie nicht die richtige Anzahl von Lizenzen erworben haben, wird eine Fehlermeldung angezeigt. Wenn Sie weitere Anrufplanlizenzen erwerben müssen, wählen Sie **Buy more** (Weitere kaufen) aus.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="3e8f4-116">**Nächste Schritte**: Nach dem Zuweisen von Anrufplanlizenzen zu Ihren Benutzern müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="3e8f4-117">Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="3e8f4-118">Zuweisen einer Telefonanlage und einer Anruf Plan Lizenz für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="3e8f4-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="3e8f4-119">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="3e8f4-120">Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="3e8f4-121">Zuweisen von Telefon System-und Anruf Plan Lizenzen in loser Schüttung</span><span class="sxs-lookup"><span data-stu-id="3e8f4-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="3e8f4-122">Installieren Sie den Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="3e8f4-123">Ist das Modul nicht installiert?</span><span class="sxs-lookup"><span data-stu-id="3e8f4-123">Don't have the module installed?</span></span> <span data-ttu-id="3e8f4-124">Informationen zum Herunterladen finden Sie [im Microsoft Online Services-Anmelde Assistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) .</span><span class="sxs-lookup"><span data-stu-id="3e8f4-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="3e8f4-125">Installieren Sie das Windows Azure Active Directory-Modul.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="3e8f4-126">Ist das Modul nicht installiert?</span><span class="sxs-lookup"><span data-stu-id="3e8f4-126">Don't have the module installed?</span></span> <span data-ttu-id="3e8f4-127">Informationen zum Herunterladen von Anweisungen und zur Cmdlet-Syntax finden Sie unter [Verwalten von Azure AD mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="3e8f4-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="3e8f4-128">Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="3e8f4-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="3e8f4-129">In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Telefonsysteme und einer Lizenz für einen Plan für Inlandsanrufe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="3e8f4-130">Der Name der Lizenzen oder Produktnamen im Skript wird kursiv angezeigt (siehe [Telefon System-und Anrufplan-Produktnamen oder SKUs, die für die Skripterstellung verwendet](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)werden, nach dem Beispiel).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="3e8f4-131">Für die Skripterstellung verwendete Produktnamen oder SKUs für Telefonsystem und Anrufplan</span><span class="sxs-lookup"><span data-stu-id="3e8f4-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="3e8f4-132">Produktname</span><span class="sxs-lookup"><span data-stu-id="3e8f4-132">Product name</span></span> | <span data-ttu-id="3e8f4-133">SKU-Teilename</span><span class="sxs-lookup"><span data-stu-id="3e8f4-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="3e8f4-134">Enterprise E5 (mit Telefonsystem)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="3e8f4-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="3e8f4-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="3e8f4-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3e8f4-136">Enterprise E3</span></span> | <span data-ttu-id="3e8f4-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="3e8f4-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="3e8f4-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="3e8f4-138">Enterprise E1</span></span> | <span data-ttu-id="3e8f4-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="3e8f4-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="3e8f4-140">Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="3e8f4-140">Phone System</span></span> | <span data-ttu-id="3e8f4-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="3e8f4-141">MCOEV</span></span> |
| <span data-ttu-id="3e8f4-142">Plan für Inlands #a0 Auslandsgespräche</span><span class="sxs-lookup"><span data-stu-id="3e8f4-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="3e8f4-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="3e8f4-143">MCOPSTN2</span></span> |
| <span data-ttu-id="3e8f4-144">Plan für Inlandsanrufe (3000 Minuten pro Nutzer/Monat für US/PR/ca, 1200 Minuten pro Nutzer/Monat für EU-Länder)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="3e8f4-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="3e8f4-145">MCOPSTN1</span></span> |
| <span data-ttu-id="3e8f4-146">Plan für Inlandsanrufe (120 Minuten pro Nutzer/Monat für jedes Land)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="3e8f4-147">*Hinweis: dieser Plan steht in den USA nicht zur Verfügung*.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="3e8f4-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="3e8f4-148">MCOPSTN5</span></span> |
| <span data-ttu-id="3e8f4-149">Plan für Inlandsanrufe (240 Minuten pro Nutzer/Monat für jedes Land)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="3e8f4-150">*Hinweis: dieser Plan steht in den USA nicht zur Verfügung*.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="3e8f4-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="3e8f4-151">MCOPSTN6</span></span> |
| <span data-ttu-id="3e8f4-152">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-152">Communications Credits</span></span> | <span data-ttu-id="3e8f4-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="3e8f4-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="3e8f4-154">Audiokonferenz: Tipps und Skripts für das Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="3e8f4-155">Hier erfahren Sie, was Sie vor dem Zuweisen von Lizenzen für Audiokonferenzen wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="3e8f4-156">**Drittanbieter für Audiokonferenzen**: Wenn Benutzer für die Verwendung eines Drittanbieters für Audiokonferenzen eingerichtet sind und Sie diesen Benutzern eine Lizenz für Audiokonferenzen zuweisen, werden sie auf die Verwendung von Microsoft als Audiokonferenzanbieter umgestellt.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="3e8f4-157">Diese Änderung können Sie rückgängig machen und wieder den Drittanbieter festlegen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="3e8f4-158">**Nächste Schritte**: Nachdem Sie Lizenzen für Audiokonferenzen zugewiesen haben, müssen Sie einen Audiokonferenz-Anbieter zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="3e8f4-159">Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Audiokonferenz-Anbieter](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="3e8f4-160">Zuweisen einer Audiokonferenz-Lizenz für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="3e8f4-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="3e8f4-161">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="3e8f4-162">Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="3e8f4-163">Zuweisen von Lizenzen für Audiokonferenzen im Massen Format</span><span class="sxs-lookup"><span data-stu-id="3e8f4-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="3e8f4-164">Laden Sie den [Microsoft Online Services-Anmeldeassistenten für IT-Experten RTW](https://go.microsoft.com/fwlink/?LinkId=625123) herunter, und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="3e8f4-165">Laden Sie das Windows Azure Active Directory-Modul herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="3e8f4-166">Informationen zum Herunterladen von Anweisungen und zur Cmdlet-Syntax finden Sie unter [Verwalten von Azure AD mithilfe von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="3e8f4-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="3e8f4-167">Wenn die Module installiert sind, weisen Sie die Lizenzen mithilfe der Windows PowerShell-Eingabeaufforderung und der folgenden Syntax Ihren Benutzern zu:</span><span class="sxs-lookup"><span data-stu-id="3e8f4-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="3e8f4-168">Der Name der Lizenzen oder Produktnamen im Skript wird kursiv angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="3e8f4-169">Sehen Sie sich die [Produktnamen oder SKUs für Audiokonferenzen](#audio-conferencing-product-names-or-skus-used-for-scripting) an, die für die Skripterstellung für alle Produktnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="3e8f4-170">In diesem Beispiel wird eine Enterprise E3-Lizenz zusammen mit einer Lizenz für Audiokonferenzen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="3e8f4-171">Für die Skripterstellung verwendete Produktnamen oder SKUs für Audio-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="3e8f4-172">Produktname</span><span class="sxs-lookup"><span data-stu-id="3e8f4-172">Product name</span></span> | <span data-ttu-id="3e8f4-173">SKU-Teilename</span><span class="sxs-lookup"><span data-stu-id="3e8f4-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="3e8f4-174">Audiokonferenzen (Abonnement)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="3e8f4-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="3e8f4-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="3e8f4-176">Audio-Konferenzgebühren pro Minute (im Voraus bezahlen)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="3e8f4-177">*Hinweis: die Einrichtung und Aktivierung von Kommunikationsguthaben ist erforderlich*.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="3e8f4-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="3e8f4-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="3e8f4-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="3e8f4-179">Enterprise E1</span></span> | <span data-ttu-id="3e8f4-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="3e8f4-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="3e8f4-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3e8f4-181">Enterprise E3</span></span> | <span data-ttu-id="3e8f4-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="3e8f4-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="3e8f4-183">Enterprise E5 (ohne Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="3e8f4-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="3e8f4-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="3e8f4-185">Enterprise E5 (mit Audiokonferenz)</span><span class="sxs-lookup"><span data-stu-id="3e8f4-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="3e8f4-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="3e8f4-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="3e8f4-187">Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-187">Communications Credits</span></span>

<span data-ttu-id="3e8f4-188">Hier erfahren Sie, was Sie wissen müssen, bevor Sie Lizenzen für Communications-Guthaben zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="3e8f4-189">**Enterprise E5-Kunden**: selbst wenn ihren Benutzern Enterprise E5-Lizenzen zugewiesen sind, empfehlen wir Ihnen weiterhin, Ihnen Kommunikationsguthaben-Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="3e8f4-190">**Nächste Schritte**: Nach dem Zuweisen dieser Lizenzen müssen Sie Telefonnummern für Ihre Organisation abrufen und diese Nummern den Benutzern in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="3e8f4-191">Eine schrittweise Anleitung finden Sie unter [Einrichten von Anrufplänen](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="3e8f4-192">Zuweisen einer Lizenz für Kommunikations Kredite zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="3e8f4-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="3e8f4-193">Die Schritte sind die gleichen wie beim Zuweisen einer Office 365-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="3e8f4-194">Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="3e8f4-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="3e8f4-195">Zuweisen von Lizenzen für Kommunikations Kredite in loser Schüttung</span><span class="sxs-lookup"><span data-stu-id="3e8f4-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="3e8f4-196">Sehen Sie sich das Beispielskript für das Zuweisen von Lizenzen für Audiokonferenzen an.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="3e8f4-197">Aktualisieren Sie es mit den Informationen zum Zuweisen von Lizenzen für Guthaben für Kommunikationen.</span><span class="sxs-lookup"><span data-stu-id="3e8f4-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e8f4-198">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-198">Related topics</span></span>

[<span data-ttu-id="3e8f4-199">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="3e8f4-200">Hinzufügen von Geld und Verwalten von Guthaben für Kommunikationen</span><span class="sxs-lookup"><span data-stu-id="3e8f4-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)

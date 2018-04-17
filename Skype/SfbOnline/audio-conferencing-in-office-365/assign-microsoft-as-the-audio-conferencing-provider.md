---
title: Zuweisen von Microsoft als Audiokonferenzanbieter
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: dcf0eb1c4dcbfc5de54303e7d55538d3fcd6c007
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="66765-103">Zuweisen von Microsoft als Audiokonferenzanbieter</span><span class="sxs-lookup"><span data-stu-id="66765-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="66765-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span><span class="sxs-lookup"><span data-stu-id="66765-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="66765-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span><span class="sxs-lookup"><span data-stu-id="66765-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="66765-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span><span class="sxs-lookup"><span data-stu-id="66765-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="66765-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span><span class="sxs-lookup"><span data-stu-id="66765-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="66765-108">Zuweisen von Microsoft als Audiokonferenzanbieter</span><span class="sxs-lookup"><span data-stu-id="66765-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="66765-109">Verwenden des Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="66765-109">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="66765-110">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="66765-110">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="66765-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span><span class="sxs-lookup"><span data-stu-id="66765-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="66765-112">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span><span class="sxs-lookup"><span data-stu-id="66765-112">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="66765-113">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span><span class="sxs-lookup"><span data-stu-id="66765-113">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="66765-114">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="66765-114">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66765-115">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span><span class="sxs-lookup"><span data-stu-id="66765-115">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="66765-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="66765-116">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="66765-117">Verwenden eines Windows PowerShell-Skripts für eine kleine Anzahl von Benutzern</span><span class="sxs-lookup"><span data-stu-id="66765-117">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="66765-118">Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine kleine Anzahl von Benutzern festlegen.</span><span class="sxs-lookup"><span data-stu-id="66765-118">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="66765-p104">Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern.</span><span class="sxs-lookup"><span data-stu-id="66765-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="66765-121">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66765-121">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="66765-122">Verwenden eines Windows PowerShell-Skripts für eine große Anzahl von Benutzern</span><span class="sxs-lookup"><span data-stu-id="66765-122">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="66765-123">Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine große Anzahl von Benutzern festlegen.</span><span class="sxs-lookup"><span data-stu-id="66765-123">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="66765-p105">Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern.</span><span class="sxs-lookup"><span data-stu-id="66765-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="66765-126">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span><span class="sxs-lookup"><span data-stu-id="66765-126">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="66765-127">**Beispiel 1:** Sie können dieses Skript ausführen, indem Sie eine Liste der Benutzer bereitstellen, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="66765-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="66765-128">**Beispiel 2:** Sie können dieses Skript ausführen, indem Sie eine CSV-Datei bereitstellen, die die E-Mail-Adresse (den Alias) jedes Benutzers enthält, der aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="66765-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="66765-129">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span><span class="sxs-lookup"><span data-stu-id="66765-129">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="66765-130">Here is the script:</span><span class="sxs-lookup"><span data-stu-id="66765-130">Here is the script:</span></span>

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="66765-131">Weitere Informationen zur Nutzung von Windows PowerShell finden Sie unter [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="66765-131">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66765-132">See Also</span><span class="sxs-lookup"><span data-stu-id="66765-132">Related topics</span></span>
<span data-ttu-id="66765-133">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="66765-133">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>


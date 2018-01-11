---
title: Zuweisen von Microsoft als Audiokonferenzanbieter
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: c42bf80b456517eb6305a993cbb11c3b9a245c20
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="70666-104">Zuweisen von Microsoft als Audiokonferenzanbieter</span><span class="sxs-lookup"><span data-stu-id="70666-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="70666-105">Kein Audiokonferenzanbieter stellt die *Konferenzbrücke*.</span><span class="sxs-lookup"><span data-stu-id="70666-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="70666-106">Die Konferenzbrücke bietet die Zugriffsnummer für Einwahl Telefonnummern, PINs und Konferenz-IDs für Besprechungen, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="70666-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="70666-107">Sie müssen nur Personen zu planen, oder führen Skype für Business oder Microsoft-Teams, Besprechungen, die kein Audiokonferenzanbieter zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="70666-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="70666-108">Wenn Sie sehen, dass **Microsoft** als audio Anbieter aufgeführt werden möchten, müssen Sie den Benutzer eine **Audiokonferenz** -Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="70666-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="70666-109">Wenn Sie eine **Audiokonferenz** -Lizenz an eine Person, die über einen Drittanbieter-Audiokonferenzen verfügen nicht zuweisen, wird automatisch Microsoft als Anbieter von Audiokonferenzen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="70666-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="70666-110">Sie können bei Bedarf [einen Drittanbieter als Anbieter von Audiokonferenzen zuweisen](assign-a-third-party-as-the-audio-conferencing-provider.md) .</span><span class="sxs-lookup"><span data-stu-id="70666-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="70666-111">Zuweisen von Microsoft als Audiokonferenzanbieter</span><span class="sxs-lookup"><span data-stu-id="70666-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="70666-112">Verwenden des Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="70666-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="70666-113">Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="70666-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70666-p104">Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern.</span><span class="sxs-lookup"><span data-stu-id="70666-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="70666-116">Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.</span><span class="sxs-lookup"><span data-stu-id="70666-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="70666-117">Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="70666-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="70666-118">Wählen Sie auf der Eigenschaftenseite für den Benutzer, klicken Sie unter **Anbietername** **Microsoft** in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="70666-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="70666-119">Da die Verwendung von Microsoft als Anbieter von Audiokonferenzen und mehrere Telefonnummern vorhanden sind, können Sie die Dropdownliste **Standard gebührenpflichtige Nummer** verwenden, um eine Standardnummer audio für den Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="70666-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="70666-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="70666-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="70666-121">Verwenden eines Windows PowerShell-Skripts für eine kleine Anzahl von Benutzern</span><span class="sxs-lookup"><span data-stu-id="70666-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="70666-122">Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine kleine Anzahl von Benutzern festlegen.</span><span class="sxs-lookup"><span data-stu-id="70666-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="70666-p105">Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern.</span><span class="sxs-lookup"><span data-stu-id="70666-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="70666-125">Sie können eines oder mehrere der folgenden Skripts als PowerShell-Skriptdatei speichern und diese dann ausführen.</span><span class="sxs-lookup"><span data-stu-id="70666-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="70666-126">Um den Anbieter an Microsoft für eine kleine Anzahl von Benutzern zu ändern, können Sie die [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)verwenden.</span><span class="sxs-lookup"><span data-stu-id="70666-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="70666-127">**Beispiel 1:** Sie können dieses Skript ausführen, indem Sie eine Liste der Benutzer bereitstellen, die aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="70666-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="70666-128">**Beispiel 2:** Sie können dieses Skript ausführen, indem Sie eine CSV-Datei bereitstellen, die die E-Mail-Adresse (den Alias) jedes Benutzers enthält, der aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="70666-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="70666-129">Verwenden eines Windows PowerShell-Skripts für eine große Anzahl von Benutzern</span><span class="sxs-lookup"><span data-stu-id="70666-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="70666-130">Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine große Anzahl von Benutzern festlegen.</span><span class="sxs-lookup"><span data-stu-id="70666-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="70666-p106">Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern.</span><span class="sxs-lookup"><span data-stu-id="70666-p106">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="70666-133">Sie können eines oder mehrere der folgenden Skripts als PowerShell-Skriptdatei speichern und diese dann ausführen.</span><span class="sxs-lookup"><span data-stu-id="70666-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="70666-134">**Beispiel 1:** In diesem Beispiel können Sie mit dem Skript für eine große Anzahl von Benutzern in Ihrer Organisation den Audiokonferenzanbieter von Intercall (oder einem anderen Anbieter) in **Microsoft** ändern.</span><span class="sxs-lookup"><span data-stu-id="70666-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="70666-135">Hier ist das Skript ein:</span><span class="sxs-lookup"><span data-stu-id="70666-135">Here is the script:</span></span>

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
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
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
<span data-ttu-id="70666-136">Weitere Informationen zur Nutzung von Windows PowerShell finden Sie unter [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="70666-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="70666-137">Was sollte ich noch wissen?</span><span class="sxs-lookup"><span data-stu-id="70666-137">What else should I know?</span></span>

- <span data-ttu-id="70666-138">Jedem Benutzer kann nur ein Audiokonferenzanbieter zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="70666-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="70666-p107">Sie können den Audiokonferenzanbieter jederzeit von Microsoft in einen Drittanbieter ändern. Weitere Informationen finden Sie unter [Zuweisen eines Drittanbieters für Audiokonferenzen](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="70666-p107">You can change the audio conferencing provider from Microsoft to a third-party provider at any time. To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="70666-p108">Es kann vorkommen, dass in Ihrer Organisation einige Mitarbeiter Microsoft als Audiokonferenzanbieter und andere einen Drittanbieter nutzen. Das ist jedoch komplizierter einzurichten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="70666-p108">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider. But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="70666-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="70666-143">Related topics</span></span>

[<span data-ttu-id="70666-144">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="70666-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="70666-145">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="70666-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
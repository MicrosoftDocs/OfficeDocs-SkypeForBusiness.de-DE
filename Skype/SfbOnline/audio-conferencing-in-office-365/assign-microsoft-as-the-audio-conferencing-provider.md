---
title: Zuweisen von Microsoft als Audiokonferenzanbieter
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: e5e11adb4bf02e87de316d70be48b60d3ecd1d7f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Zuweisen von Microsoft als Audiokonferenzanbieter

Um Audiokonferenzen in Office 365 mit Skype für Unternehmen und die Microsoft-Teams verwenden, müssen die Benutzer in Ihrer Organisation eine Audiokonferenz-Lizenz zugewiesen werden. Um weitere Informationen zur Lizenzierung und Kosten finden Sie unter [Testen oder erwerben Audiokonferenzen in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .

Microsoft-Audiokonferenzen liefert Zugriffsnummer für Einwahl Telefonnummern, PINs und Konferenz-IDs, die von Besprechungsteilnehmern zur Teilnahme an Besprechungen Ihrer Organisation verwendet werden können. Sie müssen nur Microsoft als Anbieter von Audiokonferenzen Personen zuweisen zu planen, oder führen Skype für Business oder Microsoft-Teams, Besprechungen, die.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Zuweisen von Microsoft als Audiokonferenzanbieter

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) Verwenden des Skype for Business Admin Center

1. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
2. Navigieren Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen**.
    
3. Wenn Sie ein Banner finden Sie unter aufgefordert werden, dass Benutzer, die eine **Audiokonferenz** haben Lizenz zugewiesen jedoch nicht, dass Microsoft legen Sie als Anbieter von Audiokonferenzen noch auf **Klicken Sie hier, um sie zu verschieben**. Wenn das Banner nicht angezeigt wird, in der **Skype für Business Administrationscenter** klicken Sie auf **Benutzer**, und wählen Sie dann den Filter für **Benutzer bereit, in der Audiokonferenz verschoben werden soll** .
    
4. Wählen Sie auf der Eigenschaftenseite für den Benutzer, klicken Sie unter **Anbietername** **Microsoft** in der Dropdown-Liste.
    
    > [!NOTE]
    > Da die Verwendung von Microsoft als Anbieter von Audiokonferenzen und mehrere Telefonnummern vorhanden sind, können Sie die Dropdownliste **Standard gebührenpflichtige Nummer** verwenden, um eine Standardnummer audio für den Benutzer auszuwählen.
  
5. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Verwenden eines Windows PowerShell-Skripts für eine kleine Anzahl von Benutzern

Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine kleine Anzahl von Benutzern festlegen.

> [!NOTE]
> Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern. 

  
Um den Anbieter an Microsoft für eine kleine Anzahl von Benutzern zu ändern, können Sie das Cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) verwenden.
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Verwenden eines Windows PowerShell-Skripts für eine große Anzahl von Benutzern
Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine große Anzahl von Benutzern festlegen.

Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern. 
  
Sie können einer PowerShell-Skriptdatei das folgende Skript speichern und führen Sie ihn unter Verwendung eines seine Eingabeparameter.

**Beispiel 1:** Sie können dieses Skript ausführen, indem Sie eine Liste der Benutzer bereitstellen, die aktualisiert werden sollen.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

**Beispiel 2:** Sie können dieses Skript ausführen, indem Sie eine CSV-Datei bereitstellen, die die E-Mail-Adresse (den Alias) jedes Benutzers enthält, der aktualisiert werden soll.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Beispiel 3:** In diesem Beispiel können dieses Skript Sie zum Ändern der Anbieter von Audiokonferenzen aus Intercall (oder einen anderen Anbieter) **Microsoft** für eine große Anzahl Benutzer in Ihrer Organisation.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Hier ist das Skript ein:

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
Weitere Informationen zur Nutzung von Windows PowerShell finden Sie unter [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="related-topics"></a>See Also
[Versuchen Sie es oder erwerben Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Skype für Business Online einrichten](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)


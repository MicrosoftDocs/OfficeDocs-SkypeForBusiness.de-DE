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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Zuweisen von Microsoft als Audiokonferenzanbieter

Kein Audiokonferenzanbieter stellt die *Konferenzbrücke*. Die Konferenzbrücke bietet die Zugriffsnummer für Einwahl Telefonnummern, PINs und Konferenz-IDs für Besprechungen, die erstellt werden. Sie müssen nur Personen zu planen, oder führen Skype für Business oder Microsoft-Teams, Besprechungen, die kein Audiokonferenzanbieter zugewiesen.
  
Wenn Sie sehen, dass **Microsoft** als audio Anbieter aufgeführt werden möchten, müssen Sie den Benutzer eine **Audiokonferenz** -Lizenz zuweisen.
  
> [!NOTE]
> Wenn Sie eine **Audiokonferenz** -Lizenz an eine Person, die über einen Drittanbieter-Audiokonferenzen verfügen nicht zuweisen, wird automatisch Microsoft als Anbieter von Audiokonferenzen zugewiesen. Sie können bei Bedarf [einen Drittanbieter als Anbieter von Audiokonferenzen zuweisen](assign-a-third-party-as-the-audio-conferencing-provider.md) .
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Zuweisen von Microsoft als Audiokonferenzanbieter

### <a name="using-the-skype-for-business-admin-center"></a>Verwenden des Skype for Business Admin Center

1. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
    > [!NOTE]
    > Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern. 
  
2. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.
    
3. Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.
    
4. Wählen Sie auf der Eigenschaftenseite für den Benutzer, klicken Sie unter **Anbietername** **Microsoft** in der Dropdown-Liste.
    
    > [!NOTE]
    > Da die Verwendung von Microsoft als Anbieter von Audiokonferenzen und mehrere Telefonnummern vorhanden sind, können Sie die Dropdownliste **Standard gebührenpflichtige Nummer** verwenden, um eine Standardnummer audio für den Benutzer auszuwählen.
  
5. Klicken Sie auf **Speichern**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Verwenden eines Windows PowerShell-Skripts für eine kleine Anzahl von Benutzern

Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine kleine Anzahl von Benutzern festlegen.

> [!NOTE]
> Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern. 
  
Sie können eines oder mehrere der folgenden Skripts als PowerShell-Skriptdatei speichern und diese dann ausführen.
  
Um den Anbieter an Microsoft für eine kleine Anzahl von Benutzern zu ändern, können Sie die [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)verwenden.
  
**Beispiel 1:** Sie können dieses Skript ausführen, indem Sie eine Liste der Benutzer bereitstellen, die aktualisiert werden sollen.
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**Beispiel 2:** Sie können dieses Skript ausführen, indem Sie eine CSV-Datei bereitstellen, die die E-Mail-Adresse (den Alias) jedes Benutzers enthält, der aktualisiert werden soll.  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Verwenden eines Windows PowerShell-Skripts für eine große Anzahl von Benutzern
Um Zeit zu sparen oder den Vorgang zu automatisieren, können Sie mit dem folgenden PowerShell-Skript Microsoft als Audiokonferenzanbieter für eine große Anzahl von Benutzern festlegen.

Wenn Sie den Anbieter in **Microsoft** ändern, werden die Audiokonferenzinformationen für den Benutzer (Konferenzkennung, gebührenpflichtige und gebührenfreie Telefonnummern) ersetzt. Sie sollten diese Informationen speichern, bevor Sie den Anbieter ändern. 
  
Sie können eines oder mehrere der folgenden Skripts als PowerShell-Skriptdatei speichern und diese dann ausführen.

**Beispiel 1:** In diesem Beispiel können Sie mit dem Skript für eine große Anzahl von Benutzern in Ihrer Organisation den Audiokonferenzanbieter von Intercall (oder einem anderen Anbieter) in **Microsoft** ändern.
    
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
Weitere Informationen zur Nutzung von Windows PowerShell finden Sie unter [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Jedem Benutzer kann nur ein Audiokonferenzanbieter zugewiesen werden.
    
- Sie können den Audiokonferenzanbieter jederzeit von Microsoft in einen Drittanbieter ändern. Weitere Informationen finden Sie unter [Zuweisen eines Drittanbieters für Audiokonferenzen](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- Es kann vorkommen, dass in Ihrer Organisation einige Mitarbeiter Microsoft als Audiokonferenzanbieter und andere einen Drittanbieter nutzen. Das ist jedoch komplizierter einzurichten und zu verwalten.
    
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
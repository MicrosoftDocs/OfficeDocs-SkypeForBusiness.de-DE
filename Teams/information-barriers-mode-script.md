---
title: Ändern des Modus für Informationsbarrieren mit einem PowerShell-Skript
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript, nachdem Sie Informationsbarrieren bereitgestellt haben, um den Modus für alle Gruppen in Ihrem Mandanten von offen in implizit zu aktualisieren.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767653"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Ändern des Modus für Informationsbarrieren mit einem PowerShell-Skript

Verwenden Sie dieses PowerShell-Skript, um den INFORMATIONSBARRIERE-Modus für alle mit Teams verbundenen Gruppen in Ihrem Mandanten zu aktualisieren. Nachdem Sie Informationsbarrieren bereitgestellt haben, müssen Sie den Modus für diese Gruppen aktualisieren. Gruppen, die vor dem Aktivieren von IB bereitgestellt wurden, werden dem *Modus "Öffnen"* zugewiesen. Im *Offenen* Modus gibt es keine anwendbaren IB-Richtlinien. Nachdem Sie IB aktiviert *haben, wird Implicit* in den Standardmodus für alle von Ihnen neu erstellten Gruppen festgelegt. Vorhandene Gruppen behalten jedoch die *Open-Modus-Konfiguration* bei. Führen Sie dieses Skript aus, um diese vorhandenen Gruppen in den *impliziten Modus zu* ändern.

In diesem Skript verwenden Sie das [Cmdlet Get-UnifiedGroup,](/powershell/module/exchange/Set-UnifiedGroup) das sich im PowerShell-Exchange Online-Modul befindet, um den Modus zu aktualisieren. Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie unter [Übersicht Teams PowerShell.](./teams-powershell-overview.md)

## <a name="sample-script"></a>Beispielskript

Sie müssen ein Arbeits- oder Schulkonto verwenden, dem die globale Administratorrolle zugewiesen wurde, damit Ihr Mandant dieses Skript ausführen kann.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```
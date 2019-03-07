---
title: PowerShell-Skript-Beispiel – erstellen und Zuweisen einer Richtlinie auf messaging
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: Verwenden Sie dieses PowerShell-Skript ein Messagingrichtlinien im Teams erstellen, und weisen Sie es Benutzern in Ihrer Organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d65deff9f424fad8fed11d7b10cbe40ced387161
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463044"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell-Skript-Beispiel – erstellen und Zuweisen einer Richtlinie auf messaging
-------------------------------------------------------------------------

Verwenden Sie dieses PowerShell-Skript ein Messagingrichtlinien im Microsoft-Teams, erstellen und Benutzern zuweisen. 

Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter [Schnellstart - Teams für Bildungseinrichtungen](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Wenn PowerShell für Sie neu ist und Sie bei den ersten Schritten Hilfe benötigen, lesen Sie [Übersicht über Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Beispielskript

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
````



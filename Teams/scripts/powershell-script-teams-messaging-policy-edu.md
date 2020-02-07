---
title: PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript zum Erstellen einer Messagingrichtlinie in Teams, und weisen Sie Sie Benutzern in Ihrer Organisation zu.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06f2dee7e7dbc4e15d544433057a8bb12b75b7c4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827413"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie
-------------------------------------------------------------------------

Verwenden Sie dieses PowerShell-Skript, um eine Messagingrichtlinie in Microsoft Teams zu erstellen und diesen Benutzern zuzuweisen. 

Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter [Schnellstart – Teams für Bildung](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

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



---
title: PowerShell-Skriptbeispiel– Erstellen & Zuweisen einer Messagingrichtlinie
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript zum Erstellen einer Messagingrichtlinie in Teams und weisen Sie sie Benutzern in Ihrer Organisation zu.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117273"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie

Verwenden Sie dieses PowerShell-Skript zum Erstellen einer Messagingrichtlinie in Microsoft Teams und weisen Sie sie Benutzern zu. 

Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter [Schnellstart – Teams Education.](../teams-quick-start-edu.yml)

Dieses Skript verwendet das [Grant-CsTeamsMessagingPolicy-Cmdlet,](/powershell/module/skype/grant-csteamsmessagingpolicy) das sich im Skype for Business Online PowerShell-Modul befindet. Unter [Teams PowerShell finden](../teams-powershell-overview.md) Sie weitere Informationen zum Verwalten von Teams mithilfe von PowerShell.


## <a name="before-you-start"></a>Bevor Sie beginnen

Laden Sie das [PowerShell Skype for Business Online-Modul](https://www.microsoft.com/download/details.aspx?id=39366)herunter, installieren Sie es, und starten Sie den Computer neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter [Verwalten Skype for Business Online mit Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="sample-script"></a>Beispielskript

```powershell
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
```

> [!NOTE]
> Sie können benutzern eine Messagingrichtlinie auch direkt im Maßstab einer Batchrichtlinienzuweisung oder einer Gruppe zuweisen, der die Benutzer mitglieder sind. Weitere Informationen finden Sie unter Zuweisen von Richtlinien zu großen Gruppen von Benutzern [in](../batch-group-policy-assignment-edu.md) Ihrer Schule und Zuweisen von Richtlinien zu Ihren Benutzern [in Teams.](../assign-policies.md)
---
title: 'Beispiel für ein PowerShell-Skript: Erstellen & Zuweisen einer Messagingrichtlinie'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript, um eine Messagingrichtlinie in Teams zu erstellen und sie Benutzern in Ihrer Organisation zuzuordnen.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804655"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie

Verwenden Sie dieses PowerShell-Skript, um eine Messagingrichtlinie in Microsoft Teams zu erstellen und sie Benutzern zuzuordnen. 

Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter ["Schnellstart – Teams für Bildungseinrichtungen".](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)

Dieses Skript verwendet das [Cmdlet Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) das sich im Skype for Business Online -PowerShell-Modul befindet. Weitere Informationen zum Verwalten von Teams mithilfe von [PowerShell](../teams-powershell-overview.md) finden Sie in der Übersicht über Teams PowerShell.


## <a name="before-you-start"></a>Bevor Sie beginnen

Laden Sie das [Skype for Business Online -PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)herunter, installieren Sie es, und starten Sie den Computer neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter ["Verwalten von Skype for Business Online mit Office 365 PowerShell".](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

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
> Sie können benutzern eine Messagingrichtlinie auch über eine Batchrichtlinienzuweisung oder eine Gruppe, deren Mitglieder sie sind, direkt im Maßstab zuweisen. Weitere Informationen finden Sie unter ["Zuweisen von Richtlinien](../batch-group-policy-assignment-edu.md) zu großen Gruppen von Benutzern in Ihrer Schule und Zuweisen von Richtlinien [zu Ihren Benutzern in Teams".](../assign-policies.md)

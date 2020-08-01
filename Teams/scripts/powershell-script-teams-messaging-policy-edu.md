---
title: PowerShell-Skriptbeispiel – erstellen & zuweisen von Nachrichtenrichtlinien
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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 318a430f6f59cbb28ffeda4336c36ae07533615b
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533740"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie

Verwenden Sie dieses PowerShell-Skript, um eine Messagingrichtlinie in Microsoft Teams zu erstellen und diesen Benutzern zuzuweisen. 

Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter [Schnellstart – Teams für Bildung](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Dieses Skript verwendet das [Grant-CsTeamsMessagingPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet, das sich im Skype for Business Online PowerShell-Modul befindet. Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie unter [Übersicht über Teams PowerShell](../teams-powershell-overview.md) .


## <a name="before-you-start"></a>Bevor Sie beginnen

Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)herunter, installieren Sie es, und starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> Sie können Benutzern auch eine Messagingrichtlinie direkt über eine Batch Richtlinienzuweisung oder eine Gruppe zuweisen, der die Benutzer angehören. Weitere Informationen finden Sie unter [Zuweisen von Richtlinien zu einer Vielzahl von Benutzern in ihrer Schule](../batch-group-policy-assignment-edu.md) und [Zuweisen von Richtlinien zu Ihren Benutzern in Teams](../assign-policies.md).

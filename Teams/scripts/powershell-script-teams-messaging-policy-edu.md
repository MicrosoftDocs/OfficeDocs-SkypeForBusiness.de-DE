---
title: PowerShell-Skriptbeispiel – Erstellen & Zuweisen einer Nachrichtenrichtlinie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Verwenden Sie dieses PowerShell-Skript, um eine Messagingrichtlinie in Teams zu erstellen und sie Benutzern in Ihrer Organisation zuzuweisen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 764de690bbf743991536416c7fed08d0b88e7e97
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825889"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie

Verwenden Sie dieses PowerShell-Skript, um eine Nachrichtenrichtlinie in Microsoft Teams zu erstellen und benutzern zuzuweisen. 

Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter ["Schnellstart – Teams für Education](../teams-quick-start-edu.yml)".

Dieses Skript verwendet das Cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy), das sich im Skype for Business Online PowerShell-Modul befindet. Weitere Informationen zum Verwalten von Teams mitHilfe von PowerShell finden Sie in der [PowerShell-Übersicht von Teams](../teams-powershell-overview.md) .


## <a name="before-you-start"></a>Bevor Sie beginnen

Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=54616) herunter, installieren Sie es, und starten Sie den Computer dann neu, wenn Sie dazu aufgefordert werden.

Weitere Informationen finden Sie unter [Verwalten Skype for Business Online mit Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> Sie können eine Messagingrichtlinie auch benutzern im großen Maßstab über eine Batchrichtlinienzuweisung oder eine Gruppe zuweisen, der die Benutzer angehören. Weitere Informationen finden [Sie unter Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule](../batch-group-policy-assignment-edu.md) und [Zuweisen von Richtlinien zu Ihren Benutzern in Teams](../policy-assignment-overview.md).
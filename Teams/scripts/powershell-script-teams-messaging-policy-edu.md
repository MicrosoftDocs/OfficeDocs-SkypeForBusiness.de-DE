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
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951060"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="e59e2-103">PowerShell-Skriptbeispiel – Erstellen und Zuweisen einer Messagingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e59e2-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="e59e2-104">Verwenden Sie dieses PowerShell-Skript, um eine Messagingrichtlinie in Microsoft Teams zu erstellen und diesen Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e59e2-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="e59e2-105">Weitere Informationen zur Verwendung dieses PowerShell-Skripts finden Sie unter [Schnellstart – Teams für Bildung](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="e59e2-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="e59e2-106">Dieses Skript verwendet das [Grant-CsTeamsMessagingPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet, das sich im Skype for Business Online PowerShell-Modul befindet.</span><span class="sxs-lookup"><span data-stu-id="e59e2-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="e59e2-107">Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie unter [Übersicht über Teams PowerShell](../teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="e59e2-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e59e2-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="e59e2-108">Before you start</span></span>

<span data-ttu-id="e59e2-109">Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)herunter, installieren Sie es, und starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="e59e2-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="e59e2-110">Weitere Informationen finden Sie unter [Verwalten von Skype for Business Online mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e59e2-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="e59e2-111">Beispielskript</span><span class="sxs-lookup"><span data-stu-id="e59e2-111">Sample script</span></span>

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
> <span data-ttu-id="e59e2-112">Sie können auch die Zuweisung von Batch Richtlinien verwenden, um eine Messagingrichtlinie für große Benutzergruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e59e2-112">You can also use batch policy assignment to assign a messaging policy to large sets of users.</span></span> <span data-ttu-id="e59e2-113">Weitere Informationen finden Sie unter [Zuweisen von Richtlinien zu einer Vielzahl von Benutzern in ihrer Schule](../batch-policy-assignment-edu.md) und [Zuweisen von Richtlinien zu Ihren Benutzern in Teams](../assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e59e2-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>

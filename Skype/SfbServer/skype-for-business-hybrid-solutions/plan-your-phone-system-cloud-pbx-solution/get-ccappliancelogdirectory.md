---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003395"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="12940-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="12940-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="12940-104">Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="12940-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="12940-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="12940-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="12940-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="12940-106">Parameters</span></span>

<span data-ttu-id="12940-107">Keine</span><span class="sxs-lookup"><span data-stu-id="12940-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="12940-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="12940-108">Examples</span></span>
<span data-ttu-id="12940-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="12940-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="12940-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="12940-110">Example 1</span></span>

<span data-ttu-id="12940-111">Das folgende Beispiel zeigt den aktuellen Ordner, in dem Protokolle für die aktuelle Appliance des Cloud Connectors gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="12940-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="12940-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12940-112">Detailed Description</span></span>
<span data-ttu-id="12940-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="12940-113"></span></span>

<span data-ttu-id="12940-114">Das Cmdlet "Get-CcApplianceLogDirectory" zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Cloud Connector-Appliance gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="12940-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="12940-115">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="12940-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="12940-116">Sie können das Verzeichnis mit dem Cmdlet „Set-CcApplianceDirectory“ ändern. </span><span class="sxs-lookup"><span data-stu-id="12940-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="12940-117">Hinweis: Es gibt kein Cmdlet, das nur den Speicherort des Protokollordners, aber nicht das Appliance-Verzeichnis ändert.</span><span class="sxs-lookup"><span data-stu-id="12940-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="12940-118">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="12940-118">Input Types</span></span>
<span data-ttu-id="12940-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12940-119"></span></span>

<span data-ttu-id="12940-p102">Keine. Das Cmdlet „Get-CcApplianceLogDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="12940-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="12940-122">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="12940-122">Return Types</span></span>
<span data-ttu-id="12940-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12940-123"></span></span>

<span data-ttu-id="12940-124">Dieser Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="12940-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12940-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12940-125">See also</span></span>
<span data-ttu-id="12940-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12940-126"></span></span>

[<span data-ttu-id="12940-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="12940-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


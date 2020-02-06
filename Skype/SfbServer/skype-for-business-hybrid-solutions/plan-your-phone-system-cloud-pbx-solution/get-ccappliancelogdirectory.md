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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800825"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="4a883-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="4a883-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="4a883-104">Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4a883-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="4a883-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4a883-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="4a883-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a883-106">Parameters</span></span>

<span data-ttu-id="4a883-107">Keine</span><span class="sxs-lookup"><span data-stu-id="4a883-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4a883-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4a883-108">Examples</span></span>
<span data-ttu-id="4a883-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4a883-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="4a883-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="4a883-110">Example 1</span></span>

<span data-ttu-id="4a883-111">Das folgende Beispiel zeigt den aktuellen Ordner, in dem Protokolle für die aktuelle Appliance des Cloud Connectors gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="4a883-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="4a883-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a883-112">Detailed Description</span></span>
<span data-ttu-id="4a883-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4a883-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="4a883-114">Das Cmdlet "Get-CcApplianceLogDirectory" zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Cloud Connector-Appliance gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4a883-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="4a883-115">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="4a883-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="4a883-116">Sie können das Verzeichnis mit dem Cmdlet „Set-CcApplianceDirectory“ ändern. </span><span class="sxs-lookup"><span data-stu-id="4a883-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="4a883-117">Hinweis: Es gibt kein Cmdlet, das nur den Speicherort des Protokollordners, aber nicht das Appliance-Verzeichnis ändert.</span><span class="sxs-lookup"><span data-stu-id="4a883-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4a883-118">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="4a883-118">Input Types</span></span>
<span data-ttu-id="4a883-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4a883-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="4a883-p102">Keine. Das Cmdlet „Get-CcApplianceLogDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="4a883-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4a883-122">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="4a883-122">Return Types</span></span>
<span data-ttu-id="4a883-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4a883-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="4a883-124">Dieser Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="4a883-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a883-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a883-125">See also</span></span>
<span data-ttu-id="4a883-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4a883-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="4a883-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4a883-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


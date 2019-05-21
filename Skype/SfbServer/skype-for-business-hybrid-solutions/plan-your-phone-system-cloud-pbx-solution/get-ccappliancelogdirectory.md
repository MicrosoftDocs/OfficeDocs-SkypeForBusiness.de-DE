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
ms.openlocfilehash: 675e89f49c7c1384edc7cfa5944c8aee3f236c79
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287370"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="46c83-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="46c83-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="46c83-104">Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="46c83-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="46c83-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="46c83-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="46c83-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="46c83-106">Parameters</span></span>

<span data-ttu-id="46c83-107">Keine</span><span class="sxs-lookup"><span data-stu-id="46c83-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="46c83-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="46c83-108">Examples</span></span>
<span data-ttu-id="46c83-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46c83-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="46c83-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="46c83-110">Example 1</span></span>

<span data-ttu-id="46c83-111">Das folgende Beispiel zeigt den aktuellen Ordner, in dem Protokolle für die aktuelle Appliance des Cloud Connectors gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="46c83-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="46c83-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46c83-112">Detailed Description</span></span>
<span data-ttu-id="46c83-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="46c83-113"></span></span>

<span data-ttu-id="46c83-114">Das Cmdlet "Get-CcApplianceLogDirectory" zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Cloud Connector-Appliance gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="46c83-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="46c83-115">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="46c83-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="46c83-116">Sie können das Verzeichnis mit dem Cmdlet „Set-CcApplianceDirectory“ ändern. </span><span class="sxs-lookup"><span data-stu-id="46c83-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="46c83-117">Hinweis: Es gibt kein Cmdlet, das nur den Speicherort des Protokollordners, aber nicht das Appliance-Verzeichnis ändert.</span><span class="sxs-lookup"><span data-stu-id="46c83-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="46c83-118">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="46c83-118">Input Types</span></span>
<span data-ttu-id="46c83-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46c83-119"></span></span>

<span data-ttu-id="46c83-p102">Keine. Das Cmdlet „Get-CcApplianceLogDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="46c83-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="46c83-122">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="46c83-122">Return Types</span></span>
<span data-ttu-id="46c83-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46c83-123"></span></span>

<span data-ttu-id="46c83-124">Dieser Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="46c83-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46c83-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46c83-125">See also</span></span>
<span data-ttu-id="46c83-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46c83-126"></span></span>

[<span data-ttu-id="46c83-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="46c83-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


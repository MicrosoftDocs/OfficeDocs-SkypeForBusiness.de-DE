---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
ms.openlocfilehash: 1c03d0f91b3a724df6ce61d216138bb281fb0b87
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885582"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="be139-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="be139-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="be139-105">Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="be139-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="be139-106">Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="be139-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="be139-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="be139-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="be139-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="be139-108">Examples</span></span>
<span data-ttu-id="be139-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="be139-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="be139-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="be139-110">Example 1</span></span>

<span data-ttu-id="be139-111">Im folgende Beispiel wird das Stammverzeichnis der Website auf \\SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="be139-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="be139-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be139-112">Detailed Description</span></span>
<span data-ttu-id="be139-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="be139-113"></span></span>

<span data-ttu-id="be139-114">Um Gateway Affinität und hohe Verfügbarkeit zu ermöglichen, können in Websites Cloud Connector Appliances kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="be139-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="be139-115">Benutzer werden anstelle von Cloud-Connector Appliances zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="be139-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="be139-116">Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="be139-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="be139-117">Verwenden Sie diesen Ordner Appliances während der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="be139-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="be139-118">In diesem Ordner sollten für alle anderen Appliances in einer Cloud-Connector-Website freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be139-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="be139-119">Der Standardordner ist C:\Users\%userprofile%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="be139-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="be139-120">Der Pfad kann mit dem Cmdlet „Get-CcSiteDirectory“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="be139-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="be139-121">Parameter</span><span class="sxs-lookup"><span data-stu-id="be139-121">Parameters</span></span>
<span data-ttu-id="be139-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="be139-122"></span></span>

|<span data-ttu-id="be139-123">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="be139-123">**Parameter**</span></span>|<span data-ttu-id="be139-124">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="be139-124">**Required**</span></span>|<span data-ttu-id="be139-125">**Typ**</span><span class="sxs-lookup"><span data-stu-id="be139-125">**Type**</span></span>|<span data-ttu-id="be139-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="be139-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="be139-127"> Path</span><span class="sxs-lookup"><span data-stu-id="be139-127">Path</span></span> <br/> | <span data-ttu-id="be139-128">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="be139-128">Required</span></span> <br/> | <span data-ttu-id="be139-129">System.String</span><span class="sxs-lookup"><span data-stu-id="be139-129">System.String</span></span> <br/> |<span data-ttu-id="be139-130">Gibt den Pfad zu dem Ordner, in dem Cloud-Connector-Website-Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="be139-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="be139-131">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="be139-131">Input Types</span></span>
<span data-ttu-id="be139-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="be139-132"></span></span>

<span data-ttu-id="be139-133">Keine.</span><span class="sxs-lookup"><span data-stu-id="be139-133">None.</span></span> <span data-ttu-id="be139-134">Das Cmdlet „Set-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="be139-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="be139-135">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="be139-135">Return Types</span></span>
<span data-ttu-id="be139-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="be139-136"></span></span>

<span data-ttu-id="be139-137">Keine </span><span class="sxs-lookup"><span data-stu-id="be139-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be139-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be139-138">See also</span></span>
<span data-ttu-id="be139-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="be139-139"></span></span>

[<span data-ttu-id="be139-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="be139-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  


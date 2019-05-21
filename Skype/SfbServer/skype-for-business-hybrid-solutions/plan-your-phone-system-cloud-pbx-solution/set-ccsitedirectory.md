---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
ms.openlocfilehash: d2627da8bcd2cae5e388571457f4d6d9eb6813c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286964"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="84f39-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="84f39-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="84f39-105">Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="84f39-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="84f39-106">Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="84f39-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="84f39-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="84f39-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="84f39-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="84f39-108">Examples</span></span>
<span data-ttu-id="84f39-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="84f39-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="84f39-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="84f39-110">Example 1</span></span>

<span data-ttu-id="84f39-111">Im folgenden Beispiel wird das Websitestamm Verzeichnis auf \\SiteShare\CloudConnector festgelegt:</span><span class="sxs-lookup"><span data-stu-id="84f39-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="84f39-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84f39-112">Detailed Description</span></span>
<span data-ttu-id="84f39-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="84f39-113"></span></span>

<span data-ttu-id="84f39-114">Zur Bereitstellung von Gateway-Affinität und höchst Verfügbarkeit können Cloud Connector-Appliances in Websites kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="84f39-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="84f39-115">Benutzer werden Websites anstelle von Cloud Connector-Appliances zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="84f39-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="84f39-116">Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="84f39-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="84f39-117">Appliances verwenden diesen Ordner während der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="84f39-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="84f39-118">Dieser Ordner sollte für alle anderen Appliances auf einer Cloud Connector-Website freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="84f39-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="84f39-119">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="84f39-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="84f39-120">Der Pfad kann mit dem Cmdlet „Get-CcSiteDirectory“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="84f39-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="84f39-121">Parameter</span><span class="sxs-lookup"><span data-stu-id="84f39-121">Parameters</span></span>
<span data-ttu-id="84f39-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="84f39-122"></span></span>

|<span data-ttu-id="84f39-123">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="84f39-123">**Parameter**</span></span>|<span data-ttu-id="84f39-124">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="84f39-124">**Required**</span></span>|<span data-ttu-id="84f39-125">**Typ**</span><span class="sxs-lookup"><span data-stu-id="84f39-125">**Type**</span></span>|<span data-ttu-id="84f39-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="84f39-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="84f39-127"> Path</span><span class="sxs-lookup"><span data-stu-id="84f39-127">Path</span></span> <br/> | <span data-ttu-id="84f39-128">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="84f39-128">Required</span></span> <br/> | <span data-ttu-id="84f39-129">System.String</span><span class="sxs-lookup"><span data-stu-id="84f39-129">System.String</span></span> <br/> |<span data-ttu-id="84f39-130">Gibt den Pfad zu dem Ordner an, in dem Cloud Connector-Website Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="84f39-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="84f39-131">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="84f39-131">Input Types</span></span>
<span data-ttu-id="84f39-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84f39-132"></span></span>

<span data-ttu-id="84f39-133">Keine.</span><span class="sxs-lookup"><span data-stu-id="84f39-133">None.</span></span> <span data-ttu-id="84f39-134">Das Cmdlet „Set-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="84f39-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="84f39-135">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="84f39-135">Return Types</span></span>
<span data-ttu-id="84f39-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84f39-136"></span></span>

<span data-ttu-id="84f39-137">Keine</span><span class="sxs-lookup"><span data-stu-id="84f39-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84f39-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84f39-138">See also</span></span>
<span data-ttu-id="84f39-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="84f39-139"></span></span>

[<span data-ttu-id="84f39-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="84f39-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  


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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824189"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="90e34-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="90e34-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="90e34-105">Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="90e34-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="90e34-106">Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="90e34-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="90e34-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="90e34-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="90e34-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="90e34-108">Examples</span></span>
<span data-ttu-id="90e34-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="90e34-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="90e34-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="90e34-110">Example 1</span></span>

<span data-ttu-id="90e34-111">Im folgenden Beispiel wird das Websitestamm Verzeichnis auf \\SiteShare\CloudConnector festgelegt:</span><span class="sxs-lookup"><span data-stu-id="90e34-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="90e34-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90e34-112">Detailed Description</span></span>
<span data-ttu-id="90e34-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="90e34-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="90e34-114">Zur Bereitstellung von Gateway-Affinität und höchst Verfügbarkeit können Cloud Connector-Appliances in Websites kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="90e34-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="90e34-115">Benutzer werden Websites anstelle von Cloud Connector-Appliances zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="90e34-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="90e34-116">Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="90e34-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="90e34-117">Appliances verwenden diesen Ordner während der Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="90e34-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="90e34-118">Dieser Ordner sollte für alle anderen Appliances auf einer Cloud Connector-Website freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="90e34-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="90e34-119">Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="90e34-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="90e34-120">Der Pfad kann mit dem Cmdlet „Get-CcSiteDirectory“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="90e34-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="90e34-121">Parameter</span><span class="sxs-lookup"><span data-stu-id="90e34-121">Parameters</span></span>
<span data-ttu-id="90e34-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="90e34-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="90e34-123">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="90e34-123">**Parameter**</span></span>|<span data-ttu-id="90e34-124">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="90e34-124">**Required**</span></span>|<span data-ttu-id="90e34-125">**Typ**</span><span class="sxs-lookup"><span data-stu-id="90e34-125">**Type**</span></span>|<span data-ttu-id="90e34-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="90e34-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="90e34-127"> Path</span><span class="sxs-lookup"><span data-stu-id="90e34-127">Path</span></span> <br/> | <span data-ttu-id="90e34-128">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="90e34-128">Required</span></span> <br/> | <span data-ttu-id="90e34-129">System.String</span><span class="sxs-lookup"><span data-stu-id="90e34-129">System.String</span></span> <br/> |<span data-ttu-id="90e34-130">Gibt den Pfad zu dem Ordner an, in dem Cloud Connector-Website Dateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="90e34-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="90e34-131">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="90e34-131">Input Types</span></span>
<span data-ttu-id="90e34-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="90e34-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="90e34-133">Keine.</span><span class="sxs-lookup"><span data-stu-id="90e34-133">None.</span></span> <span data-ttu-id="90e34-134">Das Cmdlet „Set-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="90e34-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="90e34-135">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="90e34-135">Return Types</span></span>
<span data-ttu-id="90e34-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="90e34-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="90e34-137">Keine</span><span class="sxs-lookup"><span data-stu-id="90e34-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90e34-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90e34-138">See also</span></span>
<span data-ttu-id="90e34-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="90e34-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="90e34-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="90e34-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  


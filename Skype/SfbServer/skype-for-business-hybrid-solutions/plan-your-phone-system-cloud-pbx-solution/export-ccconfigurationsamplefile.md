---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.
ms.openlocfilehash: 3154ff3492899de244c3033e4e35345132d04f20
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893307"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="d4564-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="d4564-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="d4564-p102">Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.</span><span class="sxs-lookup"><span data-stu-id="d4564-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="d4564-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="d4564-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="d4564-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4564-108">Parameters</span></span>

<span data-ttu-id="d4564-109">Keine</span><span class="sxs-lookup"><span data-stu-id="d4564-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d4564-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d4564-110">Examples</span></span>
<span data-ttu-id="d4564-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d4564-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="d4564-112">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="d4564-112">Example 1</span></span>

<span data-ttu-id="d4564-113">Im folgenden Beispiel wird lädt Beispielkonfigurationsdatei aus der Microsoft-Website und schreibt sie in das Verzeichnis Appliance der Cloud Connector Appliance:</span><span class="sxs-lookup"><span data-stu-id="d4564-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="d4564-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4564-114">Detailed Description</span></span>
<span data-ttu-id="d4564-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d4564-115"></span></span>

<span data-ttu-id="d4564-116">Die aktuelle Version von Cloud-Connector müssen Sie mehrere Parameter in der INI-Datei bereitstellen; beispielsweise Parameter wie die IP-Adressen von virtuellen Computern für Komponenten von Cloud-Connector, Komponentennamen, Gateway-Parameter und So weiter.</span><span class="sxs-lookup"><span data-stu-id="d4564-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="d4564-117">Dieses Cmdlet, wenn auf dem Hostcomputer von Cloud-Connector ausführen lädt eine INI-Beispieldatei mit Beispielen für die Konfiguration aus der Microsoft-Website.</span><span class="sxs-lookup"><span data-stu-id="d4564-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="d4564-118">Das Cmdlet schreibt die Datei in das Verzeichnis Appliance der Appliance Cloud-Connector.</span><span class="sxs-lookup"><span data-stu-id="d4564-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="d4564-119">Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.</span><span class="sxs-lookup"><span data-stu-id="d4564-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d4564-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="d4564-120">Input Types</span></span>
<span data-ttu-id="d4564-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4564-121"></span></span>

<span data-ttu-id="d4564-p104">Keine. Das Cmdlet „Export-CcConfigurationSampleFile“ akzeptiert keine Pipelineeingaben. </span><span class="sxs-lookup"><span data-stu-id="d4564-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="d4564-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="d4564-124">Return Types</span></span>
<span data-ttu-id="d4564-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4564-125"></span></span>

<span data-ttu-id="d4564-126">Keine </span><span class="sxs-lookup"><span data-stu-id="d4564-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4564-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4564-127">See also</span></span>
<span data-ttu-id="d4564-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4564-128"></span></span>

[<span data-ttu-id="d4564-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="d4564-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


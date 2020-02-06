---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801005"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="e7c57-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="e7c57-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="e7c57-p102">Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.</span><span class="sxs-lookup"><span data-stu-id="e7c57-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="e7c57-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="e7c57-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="e7c57-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7c57-108">Parameters</span></span>

<span data-ttu-id="e7c57-109">Keine</span><span class="sxs-lookup"><span data-stu-id="e7c57-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e7c57-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e7c57-110">Examples</span></span>
<span data-ttu-id="e7c57-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e7c57-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e7c57-112">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="e7c57-112">Example 1</span></span>

<span data-ttu-id="e7c57-113">Im folgenden Beispiel wird eine Beispielkonfigurationsdatei von der Microsoft-Website heruntergeladen und in das Appliance-Verzeichnis der Cloud Connector-Appliance geschrieben:</span><span class="sxs-lookup"><span data-stu-id="e7c57-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="e7c57-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7c57-114">Detailed Description</span></span>
<span data-ttu-id="e7c57-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e7c57-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e7c57-116">Für die aktuelle Version von Cloud Connector müssen Sie mehrere Parameter in der INI-Datei angeben. beispielsweise Parameter wie die IP-Adressen virtueller Computer für die Cloud-Connector-Komponenten, Komponentennamen, Gatewayparameter usw.</span><span class="sxs-lookup"><span data-stu-id="e7c57-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="e7c57-117">Wenn dieses Cmdlet auf dem Hostcomputer von Cloud Connector ausgeführt wird, wird eine Beispiel-ini-Datei mit Konfigurationsbeispielen von der Microsoft-Website heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="e7c57-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="e7c57-118">Das Cmdlet schreibt die Datei in das Appliance-Verzeichnis der Cloud Connector-Appliance.</span><span class="sxs-lookup"><span data-stu-id="e7c57-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="e7c57-119">Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.</span><span class="sxs-lookup"><span data-stu-id="e7c57-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e7c57-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="e7c57-120">Input Types</span></span>
<span data-ttu-id="e7c57-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7c57-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e7c57-p104">Keine. Das Cmdlet „Export-CcConfigurationSampleFile“ akzeptiert keine Pipelineeingaben. </span><span class="sxs-lookup"><span data-stu-id="e7c57-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="e7c57-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="e7c57-124">Return Types</span></span>
<span data-ttu-id="e7c57-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7c57-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e7c57-126">Keine </span><span class="sxs-lookup"><span data-stu-id="e7c57-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7c57-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7c57-127">See also</span></span>
<span data-ttu-id="e7c57-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e7c57-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e7c57-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="e7c57-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  


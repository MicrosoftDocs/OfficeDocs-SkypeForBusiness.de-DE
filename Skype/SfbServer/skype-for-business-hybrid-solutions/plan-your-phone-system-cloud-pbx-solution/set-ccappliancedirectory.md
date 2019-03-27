---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Das Cmdlet „Set-CcApplianceDirectory“ legt das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888182"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="faf42-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="faf42-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="faf42-p102">Das Cmdlet „Set-CcApplianceDirectory“ legt das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="faf42-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="faf42-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="faf42-107">Examples</span></span>
<span data-ttu-id="faf42-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="faf42-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="faf42-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="faf42-109">Example 1</span></span>

<span data-ttu-id="faf42-110">Im folgenden Beispiel wird das Arbeitsverzeichnis auf dem Hostserver auf „c:\cloudconnector\applianceroot“ festgelegt:</span><span class="sxs-lookup"><span data-stu-id="faf42-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="faf42-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="faf42-111">Parameters</span></span>
<span data-ttu-id="faf42-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="faf42-112"></span></span>

|<span data-ttu-id="faf42-113">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="faf42-113">**Parameter**</span></span>|<span data-ttu-id="faf42-114">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="faf42-114">**Required**</span></span>|<span data-ttu-id="faf42-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="faf42-115">**Type**</span></span>|<span data-ttu-id="faf42-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="faf42-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="faf42-117"> Path</span><span class="sxs-lookup"><span data-stu-id="faf42-117">Path</span></span> <br/> | <span data-ttu-id="faf42-118">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="faf42-118">Required</span></span> <br/> |<span data-ttu-id="faf42-119">System.String</span><span class="sxs-lookup"><span data-stu-id="faf42-119">System.String</span></span>  <br/> | <span data-ttu-id="faf42-120"> Gibt den Pfad an, in dem alle Bereitstellungsdateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="faf42-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="faf42-121">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="faf42-121">Input Types</span></span>
<span data-ttu-id="faf42-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faf42-122"></span></span>

<span data-ttu-id="faf42-p103">Keine. Das Cmdlet „Set-CcApplianceDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="faf42-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="faf42-125">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="faf42-125">Return Types</span></span>
<span data-ttu-id="faf42-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faf42-126"></span></span>

<span data-ttu-id="faf42-127">Keine </span><span class="sxs-lookup"><span data-stu-id="faf42-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="faf42-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="faf42-128">See also</span></span>
<span data-ttu-id="faf42-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="faf42-129"></span></span>

<span data-ttu-id="faf42-130">Keine</span><span class="sxs-lookup"><span data-stu-id="faf42-130">None</span></span>
  


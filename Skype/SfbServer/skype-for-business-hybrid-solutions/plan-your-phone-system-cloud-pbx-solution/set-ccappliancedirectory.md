---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Das Cmdlet „Set-CcApplianceDirectory“ legt das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824221"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="12e09-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="12e09-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="12e09-p102">Das Cmdlet „Set-CcApplianceDirectory“ legt das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="12e09-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="12e09-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="12e09-107">Examples</span></span>
<span data-ttu-id="12e09-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="12e09-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="12e09-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="12e09-109">Example 1</span></span>

<span data-ttu-id="12e09-110">Im folgenden Beispiel wird das Arbeitsverzeichnis auf dem Hostserver auf „c:\cloudconnector\applianceroot“ festgelegt:</span><span class="sxs-lookup"><span data-stu-id="12e09-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="12e09-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="12e09-111">Parameters</span></span>
<span data-ttu-id="12e09-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="12e09-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="12e09-113">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="12e09-113">**Parameter**</span></span>|<span data-ttu-id="12e09-114">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="12e09-114">**Required**</span></span>|<span data-ttu-id="12e09-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="12e09-115">**Type**</span></span>|<span data-ttu-id="12e09-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="12e09-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="12e09-117"> Path</span><span class="sxs-lookup"><span data-stu-id="12e09-117">Path</span></span> <br/> | <span data-ttu-id="12e09-118">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="12e09-118">Required</span></span> <br/> |<span data-ttu-id="12e09-119">System.String</span><span class="sxs-lookup"><span data-stu-id="12e09-119">System.String</span></span>  <br/> | <span data-ttu-id="12e09-120"> Gibt den Pfad an, in dem alle Bereitstellungsdateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="12e09-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="12e09-121">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="12e09-121">Input Types</span></span>
<span data-ttu-id="12e09-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12e09-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="12e09-p103">Keine. Das Cmdlet „Set-CcApplianceDirectory“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="12e09-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="12e09-125">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="12e09-125">Return Types</span></span>
<span data-ttu-id="12e09-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12e09-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="12e09-127">Keine </span><span class="sxs-lookup"><span data-stu-id="12e09-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12e09-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12e09-128">See also</span></span>
<span data-ttu-id="12e09-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="12e09-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="12e09-130">Keine</span><span class="sxs-lookup"><span data-stu-id="12e09-130">None</span></span>
  


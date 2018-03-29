---
title: Remove-CcLegacyServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="d4853-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="d4853-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="d4853-104">Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d4853-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="d4853-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d4853-105">Examples</span></span>
<span data-ttu-id="d4853-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d4853-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d4853-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="d4853-107">Example 1</span></span>

<span data-ttu-id="d4853-108">Im folgenden Beispiel werden für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte ältere Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben:</span><span class="sxs-lookup"><span data-stu-id="d4853-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="d4853-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="d4853-109">Example 2</span></span>

<span data-ttu-id="d4853-110">Im nächsten Beispiel werden für den Vermittlungsserver und den Edgeserver ausgestellte Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben: </span><span class="sxs-lookup"><span data-stu-id="d4853-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 

```

## <a name="parameters"></a><span data-ttu-id="d4853-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4853-111">Parameters</span></span>
<span data-ttu-id="d4853-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d4853-112"></span></span>

|<span data-ttu-id="d4853-113">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="d4853-113">**Parameter**</span></span>|<span data-ttu-id="d4853-114">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="d4853-114">**Required**</span></span>|<span data-ttu-id="d4853-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d4853-115">**Type**</span></span>|<span data-ttu-id="d4853-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d4853-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d4853-117"> Rollen</span><span class="sxs-lookup"><span data-stu-id="d4853-117">Roles</span></span> <br/> |<span data-ttu-id="d4853-118">Optional </span><span class="sxs-lookup"><span data-stu-id="d4853-118">Optional</span></span>  <br/> |<span data-ttu-id="d4853-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="d4853-119">System.Array</span></span>  <br/> | <span data-ttu-id="d4853-120"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="d4853-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d4853-121">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="d4853-121">Input Types</span></span>
<span data-ttu-id="d4853-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4853-122"></span></span>

<span data-ttu-id="d4853-p101">Keine. Das Cmdlet „Remove-CcLegacyServerCertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="d4853-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d4853-125">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="d4853-125">Return Types</span></span>
<span data-ttu-id="d4853-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4853-126"></span></span>

<span data-ttu-id="d4853-127">Keine</span><span class="sxs-lookup"><span data-stu-id="d4853-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4853-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4853-128">See also</span></span>
<span data-ttu-id="d4853-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4853-129"></span></span>

[<span data-ttu-id="d4853-130">Erneuern CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="d4853-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="d4853-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="d4853-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="d4853-132">Erneuern CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="d4853-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="d4853-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="d4853-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  


---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
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
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882460"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="f17d7-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f17d7-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="f17d7-104">Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f17d7-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="f17d7-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f17d7-105">Examples</span></span>
<span data-ttu-id="f17d7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f17d7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="f17d7-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="f17d7-107">Example 1</span></span>

<span data-ttu-id="f17d7-108">Im folgenden Beispiel werden für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte ältere Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben:</span><span class="sxs-lookup"><span data-stu-id="f17d7-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="f17d7-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="f17d7-109">Example 2</span></span>

<span data-ttu-id="f17d7-110">Im nächsten Beispiel werden für den Vermittlungsserver und den Edgeserver ausgestellte Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben: </span><span class="sxs-lookup"><span data-stu-id="f17d7-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="f17d7-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="f17d7-111">Parameters</span></span>
<span data-ttu-id="f17d7-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f17d7-112"></span></span>

|<span data-ttu-id="f17d7-113">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="f17d7-113">**Parameter**</span></span>|<span data-ttu-id="f17d7-114">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="f17d7-114">**Required**</span></span>|<span data-ttu-id="f17d7-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f17d7-115">**Type**</span></span>|<span data-ttu-id="f17d7-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f17d7-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f17d7-117"> Rollen</span><span class="sxs-lookup"><span data-stu-id="f17d7-117">Roles</span></span> <br/> |<span data-ttu-id="f17d7-118">Optional</span><span class="sxs-lookup"><span data-stu-id="f17d7-118">Optional</span></span>  <br/> |<span data-ttu-id="f17d7-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="f17d7-119">System.Array</span></span>  <br/> | <span data-ttu-id="f17d7-120"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="f17d7-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f17d7-121">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="f17d7-121">Input Types</span></span>
<span data-ttu-id="f17d7-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f17d7-122"></span></span>

<span data-ttu-id="f17d7-p101">Keine. Das Cmdlet „Remove-CcLegacyServerCertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="f17d7-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f17d7-125">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="f17d7-125">Return Types</span></span>
<span data-ttu-id="f17d7-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f17d7-126"></span></span>

<span data-ttu-id="f17d7-127">Keine </span><span class="sxs-lookup"><span data-stu-id="f17d7-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f17d7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f17d7-128">See also</span></span>
<span data-ttu-id="f17d7-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f17d7-129"></span></span>

[<span data-ttu-id="f17d7-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f17d7-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f17d7-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f17d7-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f17d7-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f17d7-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="f17d7-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f17d7-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  


---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003285"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="5061d-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5061d-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="5061d-104">Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="5061d-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="5061d-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5061d-105">Examples</span></span>
<span data-ttu-id="5061d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5061d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="5061d-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="5061d-107">Example 1</span></span>

<span data-ttu-id="5061d-108">Im folgenden Beispiel werden für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte ältere Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben:</span><span class="sxs-lookup"><span data-stu-id="5061d-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="5061d-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="5061d-109">Example 2</span></span>

<span data-ttu-id="5061d-110">Im nächsten Beispiel werden für den Vermittlungsserver und den Edgeserver ausgestellte Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben: </span><span class="sxs-lookup"><span data-stu-id="5061d-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="5061d-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="5061d-111">Parameters</span></span>
<span data-ttu-id="5061d-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5061d-112"></span></span>

|<span data-ttu-id="5061d-113">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="5061d-113">**Parameter**</span></span>|<span data-ttu-id="5061d-114">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="5061d-114">**Required**</span></span>|<span data-ttu-id="5061d-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="5061d-115">**Type**</span></span>|<span data-ttu-id="5061d-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5061d-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5061d-117"> Rollen</span><span class="sxs-lookup"><span data-stu-id="5061d-117">Roles</span></span> <br/> |<span data-ttu-id="5061d-118">Optional</span><span class="sxs-lookup"><span data-stu-id="5061d-118">Optional</span></span>  <br/> |<span data-ttu-id="5061d-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="5061d-119">System.Array</span></span>  <br/> | <span data-ttu-id="5061d-120"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="5061d-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5061d-121">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="5061d-121">Input Types</span></span>
<span data-ttu-id="5061d-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5061d-122"></span></span>

<span data-ttu-id="5061d-p101">Keine. Das Cmdlet „Remove-CcLegacyServerCertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="5061d-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5061d-125">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="5061d-125">Return Types</span></span>
<span data-ttu-id="5061d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5061d-126"></span></span>

<span data-ttu-id="5061d-127">Keine</span><span class="sxs-lookup"><span data-stu-id="5061d-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5061d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5061d-128">See also</span></span>
<span data-ttu-id="5061d-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5061d-129"></span></span>

[<span data-ttu-id="5061d-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5061d-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="5061d-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5061d-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="5061d-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5061d-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="5061d-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5061d-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  


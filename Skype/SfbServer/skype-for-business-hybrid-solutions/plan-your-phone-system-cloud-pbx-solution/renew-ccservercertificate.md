---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen geändert.
ms.openlocfilehash: 47f2bbefa6510ae49e2e4a3ddc321e288dee266e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003265"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="45a56-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="45a56-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="45a56-105">Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="45a56-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="45a56-106">Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="45a56-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="45a56-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="45a56-107">Examples</span></span>
<span data-ttu-id="45a56-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45a56-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="45a56-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="45a56-109">Example 1</span></span>

<span data-ttu-id="45a56-110">Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="45a56-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="45a56-111">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="45a56-111">Example 2</span></span>

<span data-ttu-id="45a56-112">Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="45a56-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="45a56-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45a56-113">Detailed Description</span></span>
<span data-ttu-id="45a56-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="45a56-114"></span></span>

<span data-ttu-id="45a56-115">Interne Zertifikate des Cloud Connectors, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig, nachdem Sie von einem Zertifizierungsstellendienst ausgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="45a56-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="45a56-116">Wenn Zertifikate in Kürze ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet „Renew-CcServerCertificate“ aus, um die Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="45a56-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="45a56-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="45a56-117">Parameters</span></span>
<span data-ttu-id="45a56-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="45a56-118"></span></span>

|<span data-ttu-id="45a56-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="45a56-119">**Parameter**</span></span>|<span data-ttu-id="45a56-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="45a56-120">**Required**</span></span>|<span data-ttu-id="45a56-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="45a56-121">**Type**</span></span>|<span data-ttu-id="45a56-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="45a56-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45a56-123"> Rollen</span><span class="sxs-lookup"><span data-stu-id="45a56-123">Roles</span></span>  <br/> |<span data-ttu-id="45a56-124">Optional</span><span class="sxs-lookup"><span data-stu-id="45a56-124">Optional</span></span>  <br/> |<span data-ttu-id="45a56-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="45a56-125">System.Array</span></span>  <br/> | <span data-ttu-id="45a56-126"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="45a56-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="45a56-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="45a56-127">Input Types</span></span>
<span data-ttu-id="45a56-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45a56-128"></span></span>

<span data-ttu-id="45a56-p104">Keine. Das Cmdlet „Renew-CcServerCertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="45a56-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="45a56-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="45a56-131">Return Types</span></span>
<span data-ttu-id="45a56-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45a56-132"></span></span>

<span data-ttu-id="45a56-133">Keine</span><span class="sxs-lookup"><span data-stu-id="45a56-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45a56-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45a56-134">See also</span></span>
<span data-ttu-id="45a56-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="45a56-135"></span></span>

[<span data-ttu-id="45a56-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="45a56-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="45a56-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="45a56-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="45a56-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="45a56-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


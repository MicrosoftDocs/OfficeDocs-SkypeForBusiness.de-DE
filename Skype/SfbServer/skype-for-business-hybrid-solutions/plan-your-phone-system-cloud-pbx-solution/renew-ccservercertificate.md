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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen geändert.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824261"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="df61b-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="df61b-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="df61b-105">Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="df61b-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="df61b-106">Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="df61b-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="df61b-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="df61b-107">Examples</span></span>
<span data-ttu-id="df61b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="df61b-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="df61b-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="df61b-109">Example 1</span></span>

<span data-ttu-id="df61b-110">Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="df61b-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="df61b-111">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="df61b-111">Example 2</span></span>

<span data-ttu-id="df61b-112">Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="df61b-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="df61b-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df61b-113">Detailed Description</span></span>
<span data-ttu-id="df61b-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="df61b-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="df61b-115">Interne Zertifikate des Cloud Connectors, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig, nachdem Sie von einem Zertifizierungsstellendienst ausgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="df61b-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="df61b-116">Wenn Zertifikate in Kürze ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet „Renew-CcServerCertificate“ aus, um die Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="df61b-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="df61b-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="df61b-117">Parameters</span></span>
<span data-ttu-id="df61b-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="df61b-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="df61b-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="df61b-119">**Parameter**</span></span>|<span data-ttu-id="df61b-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="df61b-120">**Required**</span></span>|<span data-ttu-id="df61b-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="df61b-121">**Type**</span></span>|<span data-ttu-id="df61b-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="df61b-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df61b-123"> Rollen</span><span class="sxs-lookup"><span data-stu-id="df61b-123">Roles</span></span>  <br/> |<span data-ttu-id="df61b-124">Optional</span><span class="sxs-lookup"><span data-stu-id="df61b-124">Optional</span></span>  <br/> |<span data-ttu-id="df61b-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="df61b-125">System.Array</span></span>  <br/> | <span data-ttu-id="df61b-126"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="df61b-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="df61b-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="df61b-127">Input Types</span></span>
<span data-ttu-id="df61b-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="df61b-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="df61b-p104">Keine. Das Cmdlet „Renew-CcServerCertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="df61b-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="df61b-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="df61b-131">Return Types</span></span>
<span data-ttu-id="df61b-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="df61b-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="df61b-133">Keine</span><span class="sxs-lookup"><span data-stu-id="df61b-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="df61b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df61b-134">See also</span></span>
<span data-ttu-id="df61b-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="df61b-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="df61b-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="df61b-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="df61b-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="df61b-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="df61b-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="df61b-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


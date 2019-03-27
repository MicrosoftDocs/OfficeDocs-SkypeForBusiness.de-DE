---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Mit diesem Befehl wurde Update-CcServerCertificate in der Cloud Connector 2.0 und spätere Versionen geändert.
ms.openlocfilehash: ad366bdf7f6c27552a8e7621ee9244762dd864eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894817"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="3aeaf-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="3aeaf-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="3aeaf-105">Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="3aeaf-105">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> <span data-ttu-id="3aeaf-106">Mit diesem Befehl wurde Update-CcServerCertificate in der Cloud Connector 2.0 und spätere Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="3aeaf-106">This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="3aeaf-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3aeaf-107">Examples</span></span>
<span data-ttu-id="3aeaf-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3aeaf-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="3aeaf-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="3aeaf-109">Example 1</span></span>

<span data-ttu-id="3aeaf-110">Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="3aeaf-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="3aeaf-111">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="3aeaf-111">Example 2</span></span>

<span data-ttu-id="3aeaf-112">Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="3aeaf-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="3aeaf-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aeaf-113">Detailed Description</span></span>
<span data-ttu-id="3aeaf-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3aeaf-114"></span></span>

<span data-ttu-id="3aeaf-115">Interne Zertifikate für den zentralen Verwaltungsspeicher, Vermittlungsserver und Edge-Server ausgestellt Cloud Connector gelten für zwei Jahre, nachdem sie aus einem Dienst Zertifizierungsstelle ausgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3aeaf-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="3aeaf-116">Wenn Zertifikate in Kürze ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet „Renew-CcServerCertificate“ aus, um die Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="3aeaf-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="3aeaf-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="3aeaf-117">Parameters</span></span>
<span data-ttu-id="3aeaf-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3aeaf-118"></span></span>

|<span data-ttu-id="3aeaf-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="3aeaf-119">**Parameter**</span></span>|<span data-ttu-id="3aeaf-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="3aeaf-120">**Required**</span></span>|<span data-ttu-id="3aeaf-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3aeaf-121">**Type**</span></span>|<span data-ttu-id="3aeaf-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3aeaf-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3aeaf-123"> Rollen</span><span class="sxs-lookup"><span data-stu-id="3aeaf-123">Roles</span></span>  <br/> |<span data-ttu-id="3aeaf-124">Optional</span><span class="sxs-lookup"><span data-stu-id="3aeaf-124">Optional</span></span>  <br/> |<span data-ttu-id="3aeaf-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="3aeaf-125">System.Array</span></span>  <br/> | <span data-ttu-id="3aeaf-126"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="3aeaf-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3aeaf-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="3aeaf-127">Input Types</span></span>
<span data-ttu-id="3aeaf-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3aeaf-128"></span></span>

<span data-ttu-id="3aeaf-p104">Keine. Das Cmdlet „Renew-CcServerCertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="3aeaf-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3aeaf-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="3aeaf-131">Return Types</span></span>
<span data-ttu-id="3aeaf-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3aeaf-132"></span></span>

<span data-ttu-id="3aeaf-133">Keine </span><span class="sxs-lookup"><span data-stu-id="3aeaf-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3aeaf-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aeaf-134">See also</span></span>
<span data-ttu-id="3aeaf-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3aeaf-135"></span></span>

[<span data-ttu-id="3aeaf-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3aeaf-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="3aeaf-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="3aeaf-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="3aeaf-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3aeaf-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


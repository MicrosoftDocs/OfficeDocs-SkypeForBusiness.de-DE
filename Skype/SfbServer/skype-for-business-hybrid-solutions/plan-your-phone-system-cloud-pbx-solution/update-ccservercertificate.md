---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese nahezu abgelaufen sind oder bereits abgelaufen sind.
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286880"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="591d5-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="591d5-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="591d5-104">Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese nahezu abgelaufen sind oder bereits abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="591d5-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="591d5-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="591d5-105">Examples</span></span>
<span data-ttu-id="591d5-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="591d5-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="591d5-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="591d5-107">Example 1</span></span>

<span data-ttu-id="591d5-108">Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="591d5-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="591d5-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="591d5-109">Example 2</span></span>

<span data-ttu-id="591d5-110">Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="591d5-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="591d5-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="591d5-111">Detailed Description</span></span>
<span data-ttu-id="591d5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="591d5-112"></span></span>

<span data-ttu-id="591d5-113">Interne Zertifikate des Cloud Connectors, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig, nachdem Sie von einem Zertifizierungsstellendienst ausgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="591d5-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="591d5-114">Wenn Zertifikate nahezu ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet Update-CcServerCertificate aus, um die Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="591d5-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="591d5-115">Dieser Befehl ersetzt das Cmdlet Renew-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="591d5-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="591d5-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="591d5-116">Parameters</span></span>
<span data-ttu-id="591d5-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="591d5-117"></span></span>

|<span data-ttu-id="591d5-118">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="591d5-118">**Parameter**</span></span>|<span data-ttu-id="591d5-119">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="591d5-119">**Required**</span></span>|<span data-ttu-id="591d5-120">**Typ**</span><span class="sxs-lookup"><span data-stu-id="591d5-120">**Type**</span></span>|<span data-ttu-id="591d5-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="591d5-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="591d5-122"> Rollen</span><span class="sxs-lookup"><span data-stu-id="591d5-122">Roles</span></span>  <br/> |<span data-ttu-id="591d5-123">Optional</span><span class="sxs-lookup"><span data-stu-id="591d5-123">Optional</span></span>  <br/> |<span data-ttu-id="591d5-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="591d5-124">System.Array</span></span>  <br/> | <span data-ttu-id="591d5-125"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="591d5-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="591d5-126">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="591d5-126">Input Types</span></span>
<span data-ttu-id="591d5-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="591d5-127"></span></span>

<span data-ttu-id="591d5-128">Keine.</span><span class="sxs-lookup"><span data-stu-id="591d5-128">None.</span></span> <span data-ttu-id="591d5-129">Das Cmdlet Update-CcServerCertificate akzeptiert keine Pipelineeingabe.</span><span class="sxs-lookup"><span data-stu-id="591d5-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="591d5-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="591d5-130">Return Types</span></span>
<span data-ttu-id="591d5-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="591d5-131"></span></span>

<span data-ttu-id="591d5-132">Keine</span><span class="sxs-lookup"><span data-stu-id="591d5-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="591d5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="591d5-133">See also</span></span>
<span data-ttu-id="591d5-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="591d5-134"></span></span>

[<span data-ttu-id="591d5-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="591d5-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="591d5-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="591d5-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="591d5-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="591d5-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


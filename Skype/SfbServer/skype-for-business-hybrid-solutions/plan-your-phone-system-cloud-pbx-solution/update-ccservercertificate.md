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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese nahezu abgelaufen sind oder bereits abgelaufen sind.
ms.openlocfilehash: da52efcd3fdf6a0793e085098bf6f72725115e9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824109"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="f2085-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f2085-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="f2085-104">Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese nahezu abgelaufen sind oder bereits abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="f2085-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="f2085-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f2085-105">Examples</span></span>
<span data-ttu-id="f2085-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f2085-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f2085-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="f2085-107">Example 1</span></span>

<span data-ttu-id="f2085-108">Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="f2085-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="f2085-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="f2085-109">Example 2</span></span>

<span data-ttu-id="f2085-110">Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:</span><span class="sxs-lookup"><span data-stu-id="f2085-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="f2085-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2085-111">Detailed Description</span></span>
<span data-ttu-id="f2085-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f2085-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f2085-113">Interne Zertifikate des Cloud Connectors, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig, nachdem Sie von einem Zertifizierungsstellendienst ausgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f2085-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="f2085-114">Wenn Zertifikate nahezu ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet Update-CcServerCertificate aus, um die Zertifikate zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="f2085-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="f2085-115">Dieser Befehl ersetzt das Cmdlet Renew-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="f2085-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f2085-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2085-116">Parameters</span></span>
<span data-ttu-id="f2085-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f2085-117"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="f2085-118">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="f2085-118">**Parameter**</span></span>|<span data-ttu-id="f2085-119">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="f2085-119">**Required**</span></span>|<span data-ttu-id="f2085-120">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f2085-120">**Type**</span></span>|<span data-ttu-id="f2085-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f2085-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2085-122"> Rollen</span><span class="sxs-lookup"><span data-stu-id="f2085-122">Roles</span></span>  <br/> |<span data-ttu-id="f2085-123">Optional</span><span class="sxs-lookup"><span data-stu-id="f2085-123">Optional</span></span>  <br/> |<span data-ttu-id="f2085-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="f2085-124">System.Array</span></span>  <br/> | <span data-ttu-id="f2085-125"> Array von Cloud Connector-Serverrollen</span><span class="sxs-lookup"><span data-stu-id="f2085-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f2085-126">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="f2085-126">Input Types</span></span>
<span data-ttu-id="f2085-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2085-127"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f2085-128">Keine.</span><span class="sxs-lookup"><span data-stu-id="f2085-128">None.</span></span> <span data-ttu-id="f2085-129">Das Cmdlet Update-CcServerCertificate akzeptiert keine Pipelineeingabe.</span><span class="sxs-lookup"><span data-stu-id="f2085-129">The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f2085-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="f2085-130">Return Types</span></span>
<span data-ttu-id="f2085-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2085-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f2085-132">Keine</span><span class="sxs-lookup"><span data-stu-id="f2085-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2085-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2085-133">See also</span></span>
<span data-ttu-id="f2085-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2085-134"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="f2085-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="f2085-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="f2085-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="f2085-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="f2085-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="f2085-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


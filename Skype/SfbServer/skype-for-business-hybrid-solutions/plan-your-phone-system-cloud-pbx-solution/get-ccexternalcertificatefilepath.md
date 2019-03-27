---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
ms.openlocfilehash: 997b5d7a39decf11a19c307f4e7a7b439069441f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882586"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="6a4c0-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="6a4c0-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="6a4c0-p102">Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.</span><span class="sxs-lookup"><span data-stu-id="6a4c0-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="6a4c0-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="6a4c0-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="6a4c0-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a4c0-108">Examples</span></span>
<span data-ttu-id="6a4c0-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4c0-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="6a4c0-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="6a4c0-110">Example 1</span></span>

<span data-ttu-id="6a4c0-111">Das folgende Beispiel zeigt den Pfad des Zertifikats für den Edgeserver an:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="6a4c0-112">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="6a4c0-112">Example 2</span></span>

<span data-ttu-id="6a4c0-113">Das folgende Beispiel zeigt das für den Vermittlungsserver festgelegte Zertifikat an:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="6a4c0-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a4c0-114">Detailed Description</span></span>
<span data-ttu-id="6a4c0-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4c0-115"></span></span>

<span data-ttu-id="6a4c0-p103">Bei der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Zertifikat des Edgeservers und optional des Vermittlungsservers angeben. Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird. Um den Pfad zu ändern, verwenden Sie das Cmdlet „Set-CcExternalCertificateFilePath“.</span><span class="sxs-lookup"><span data-stu-id="6a4c0-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6a4c0-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a4c0-119">Parameters</span></span>
<span data-ttu-id="6a4c0-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4c0-120"></span></span>

|<span data-ttu-id="6a4c0-121">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6a4c0-121">**Parameter**</span></span>|<span data-ttu-id="6a4c0-122">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="6a4c0-122">**Required**</span></span>|<span data-ttu-id="6a4c0-123">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6a4c0-123">**Type**</span></span>|<span data-ttu-id="6a4c0-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6a4c0-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6a4c0-125">Target</span><span class="sxs-lookup"><span data-stu-id="6a4c0-125">Target</span></span>  <br/> |<span data-ttu-id="6a4c0-126">Optional</span><span class="sxs-lookup"><span data-stu-id="6a4c0-126">Optional</span></span>  <br/> | <span data-ttu-id="6a4c0-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6a4c0-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="6a4c0-p104">Der Typ des angeforderten Dateipfads. Mögliche Typen:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="6a4c0-130">„EdgeServer“ (Standard)</span><span class="sxs-lookup"><span data-stu-id="6a4c0-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="6a4c0-131">„MediationServer“</span><span class="sxs-lookup"><span data-stu-id="6a4c0-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6a4c0-132">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="6a4c0-132">Input Types</span></span>
<span data-ttu-id="6a4c0-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4c0-133"></span></span>

<span data-ttu-id="6a4c0-134">Das Cmdlet „Get-CcExternalCertificateFilePath“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="6a4c0-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6a4c0-135">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="6a4c0-135">Return Types</span></span>
<span data-ttu-id="6a4c0-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4c0-136"></span></span>

<span data-ttu-id="6a4c0-137">Der Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="6a4c0-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a4c0-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a4c0-138">See also</span></span>
<span data-ttu-id="6a4c0-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4c0-139"></span></span>

[<span data-ttu-id="6a4c0-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="6a4c0-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  


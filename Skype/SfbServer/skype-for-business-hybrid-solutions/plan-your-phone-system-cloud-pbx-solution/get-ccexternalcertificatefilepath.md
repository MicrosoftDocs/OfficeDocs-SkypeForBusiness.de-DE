---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
ms.openlocfilehash: 7a471b0e4258728bfaa50558aab54955346b457c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003375"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="6b5f6-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="6b5f6-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="6b5f6-p102">Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.</span><span class="sxs-lookup"><span data-stu-id="6b5f6-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="6b5f6-107">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="6b5f6-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="6b5f6-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6b5f6-108">Examples</span></span>
<span data-ttu-id="6b5f6-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5f6-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="6b5f6-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="6b5f6-110">Example 1</span></span>

<span data-ttu-id="6b5f6-111">Das folgende Beispiel zeigt den Pfad des Zertifikats für den Edgeserver an:</span><span class="sxs-lookup"><span data-stu-id="6b5f6-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="6b5f6-112">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="6b5f6-112">Example 2</span></span>

<span data-ttu-id="6b5f6-113">Das folgende Beispiel zeigt das für den Vermittlungsserver festgelegte Zertifikat an:</span><span class="sxs-lookup"><span data-stu-id="6b5f6-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="6b5f6-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b5f6-114">Detailed Description</span></span>
<span data-ttu-id="6b5f6-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5f6-115"></span></span>

<span data-ttu-id="6b5f6-p103">Bei der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Zertifikat des Edgeservers und optional des Vermittlungsservers angeben. Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird. Um den Pfad zu ändern, verwenden Sie das Cmdlet „Set-CcExternalCertificateFilePath“.</span><span class="sxs-lookup"><span data-stu-id="6b5f6-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6b5f6-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b5f6-119">Parameters</span></span>
<span data-ttu-id="6b5f6-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5f6-120"></span></span>

|<span data-ttu-id="6b5f6-121">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6b5f6-121">**Parameter**</span></span>|<span data-ttu-id="6b5f6-122">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="6b5f6-122">**Required**</span></span>|<span data-ttu-id="6b5f6-123">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6b5f6-123">**Type**</span></span>|<span data-ttu-id="6b5f6-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6b5f6-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b5f6-125">Target</span><span class="sxs-lookup"><span data-stu-id="6b5f6-125">Target</span></span>  <br/> |<span data-ttu-id="6b5f6-126">Optional</span><span class="sxs-lookup"><span data-stu-id="6b5f6-126">Optional</span></span>  <br/> | <span data-ttu-id="6b5f6-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6b5f6-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="6b5f6-p104">Der Typ des angeforderten Dateipfads. Mögliche Typen:</span><span class="sxs-lookup"><span data-stu-id="6b5f6-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="6b5f6-130">„EdgeServer“ (Standard)</span><span class="sxs-lookup"><span data-stu-id="6b5f6-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="6b5f6-131">„MediationServer“</span><span class="sxs-lookup"><span data-stu-id="6b5f6-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6b5f6-132">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="6b5f6-132">Input Types</span></span>
<span data-ttu-id="6b5f6-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5f6-133"></span></span>

<span data-ttu-id="6b5f6-134">Das Cmdlet „Get-CcExternalCertificateFilePath“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="6b5f6-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6b5f6-135">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="6b5f6-135">Return Types</span></span>
<span data-ttu-id="6b5f6-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5f6-136"></span></span>

<span data-ttu-id="6b5f6-137">Der Befehl gibt einen Dateipfad zurück.</span><span class="sxs-lookup"><span data-stu-id="6b5f6-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6b5f6-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b5f6-138">See also</span></span>
<span data-ttu-id="6b5f6-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5f6-139"></span></span>

[<span data-ttu-id="6b5f6-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="6b5f6-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  


---
title: Erneuern CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist. Mit diesem Befehl wurde Update-CcCACertificate in der Cloud Connector 2.0 und spätere Versionen geändert.
ms.openlocfilehash: bfcf7c69e27af8ebf83c85a8c90cc46491fbc454
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="5d9e9-104">Erneuern CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5d9e9-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="5d9e9-105">Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="5d9e9-106">Mit diesem Befehl wurde Update-CcCACertificate in der Cloud Connector 2.0 und spätere Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="5d9e9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d9e9-107">Parameters</span></span>

<span data-ttu-id="5d9e9-108">Keine</span><span class="sxs-lookup"><span data-stu-id="5d9e9-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5d9e9-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5d9e9-109">Examples</span></span>
<span data-ttu-id="5d9e9-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5d9e9-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="5d9e9-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="5d9e9-111">Example 1</span></span>

<span data-ttu-id="5d9e9-112">Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert: </span><span class="sxs-lookup"><span data-stu-id="5d9e9-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="5d9e9-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d9e9-113">Detailed Description</span></span>
<span data-ttu-id="5d9e9-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5d9e9-114"></span></span>

<span data-ttu-id="5d9e9-115">Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="5d9e9-p103">Wenn das Stammzertifikat in Kürze abläuft oder bereits abgelaufen ist, führen Sie das Cmdlet „Renew-CcCACertificate“ aus, um das Zertifikat zu erneuern. Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="5d9e9-118">Wenn sich an einem PSTN-Standort mehrere Appliances befinden, führen Sie das Cmdlet „Renew-CcCACertificate“ in allen Appliances des gleichen PSTN-Standorts aus.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="5d9e9-119">Als letzten Schritt ausführen, um das Stammzertifikat in einer lokalen Datei in die erste Appliance exportieren Export-CcRootCertificate und klicken Sie dann kopieren Sie und installieren Sie das exportierte Zertifikat zu PSTN-Gateways.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5d9e9-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="5d9e9-120">Input Types</span></span>
<span data-ttu-id="5d9e9-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5d9e9-121"></span></span>

<span data-ttu-id="5d9e9-p104">Keine. Das Cmdlet „Renew-CcCACertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="5d9e9-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5d9e9-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="5d9e9-124">Return Types</span></span>
<span data-ttu-id="5d9e9-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5d9e9-125"></span></span>

<span data-ttu-id="5d9e9-126">Keine</span><span class="sxs-lookup"><span data-stu-id="5d9e9-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d9e9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d9e9-127">See also</span></span>
<span data-ttu-id="5d9e9-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5d9e9-128"></span></span>

[<span data-ttu-id="5d9e9-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="5d9e9-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="5d9e9-130">Erneuern CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="5d9e9-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="5d9e9-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="5d9e9-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


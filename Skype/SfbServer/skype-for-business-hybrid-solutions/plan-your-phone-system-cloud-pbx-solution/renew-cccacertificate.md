---
title: Renew-CcCACertificate
ms.reviewer: ''
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
ms.openlocfilehash: 616abb35d577b816368854396a201b9f07b40d12
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250892"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="bbee7-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bbee7-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="bbee7-105">Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="bbee7-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="bbee7-106">Mit diesem Befehl wurde Update-CcCACertificate in der Cloud Connector 2.0 und spätere Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="bbee7-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="bbee7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbee7-107">Parameters</span></span>

<span data-ttu-id="bbee7-108">Keine</span><span class="sxs-lookup"><span data-stu-id="bbee7-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="bbee7-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bbee7-109">Examples</span></span>
<span data-ttu-id="bbee7-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bbee7-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="bbee7-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="bbee7-111">Example 1</span></span>

<span data-ttu-id="bbee7-112">Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert: </span><span class="sxs-lookup"><span data-stu-id="bbee7-112">The following example renews the root CA certificate:</span></span> 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="bbee7-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbee7-113">Detailed Description</span></span>
<span data-ttu-id="bbee7-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bbee7-114"></span></span>

<span data-ttu-id="bbee7-115">Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.</span><span class="sxs-lookup"><span data-stu-id="bbee7-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="bbee7-p103">Wenn das Stammzertifikat in Kürze abläuft oder bereits abgelaufen ist, führen Sie das Cmdlet „Renew-CcCACertificate“ aus, um das Zertifikat zu erneuern. Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbee7-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="bbee7-118">Wenn sich an einem PSTN-Standort mehrere Appliances befinden, führen Sie das Cmdlet „Renew-CcCACertificate“ in allen Appliances des gleichen PSTN-Standorts aus.</span><span class="sxs-lookup"><span data-stu-id="bbee7-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="bbee7-119">Letzter Schritt: Führen Sie das Cmdlet „Export-CcRootCertificate“ aus, um das Stammzertifikat in eine lokale Datei in der ersten Appliance zu exportieren. Kopieren Sie dann das exportierte Zertifikat, und installieren Sie es in Ihren PSTN-Gateways.
</span><span class="sxs-lookup"><span data-stu-id="bbee7-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="bbee7-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="bbee7-120">Input Types</span></span>
<span data-ttu-id="bbee7-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bbee7-121"></span></span>

<span data-ttu-id="bbee7-p104">Keine. Das Cmdlet „Renew-CcCACertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="bbee7-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bbee7-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="bbee7-124">Return Types</span></span>
<span data-ttu-id="bbee7-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bbee7-125"></span></span>

<span data-ttu-id="bbee7-126">Keine </span><span class="sxs-lookup"><span data-stu-id="bbee7-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbee7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbee7-127">See also</span></span>
<span data-ttu-id="bbee7-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bbee7-128"></span></span>

[<span data-ttu-id="bbee7-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bbee7-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="bbee7-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bbee7-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="bbee7-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="bbee7-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


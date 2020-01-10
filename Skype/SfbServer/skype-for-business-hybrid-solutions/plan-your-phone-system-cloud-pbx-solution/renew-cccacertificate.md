---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist. Dieser Befehl wurde in Update-CcCACertificate in Cloud Connector 2,0 und höheren Versionen geändert.
ms.openlocfilehash: 493b733eab9cbd8331a93d72dc4a865f3574fbe8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003275"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="3d690-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3d690-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="3d690-105">Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="3d690-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="3d690-106">Dieser Befehl wurde in Update-CcCACertificate in Cloud Connector 2,0 und höheren Versionen geändert.</span><span class="sxs-lookup"><span data-stu-id="3d690-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="3d690-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d690-107">Parameters</span></span>

<span data-ttu-id="3d690-108">Keine</span><span class="sxs-lookup"><span data-stu-id="3d690-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3d690-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3d690-109">Examples</span></span>
<span data-ttu-id="3d690-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d690-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="3d690-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="3d690-111">Example 1</span></span>

<span data-ttu-id="3d690-112">Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert: </span><span class="sxs-lookup"><span data-stu-id="3d690-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="3d690-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d690-113">Detailed Description</span></span>
<span data-ttu-id="3d690-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3d690-114"></span></span>

<span data-ttu-id="3d690-115">Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.</span><span class="sxs-lookup"><span data-stu-id="3d690-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="3d690-p103">Wenn das Stammzertifikat in Kürze abläuft oder bereits abgelaufen ist, führen Sie das Cmdlet „Renew-CcCACertificate“ aus, um das Zertifikat zu erneuern. Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="3d690-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="3d690-118">Wenn sich an einem PSTN-Standort mehrere Appliances befinden, führen Sie das Cmdlet „Renew-CcCACertificate“ in allen Appliances des gleichen PSTN-Standorts aus.</span><span class="sxs-lookup"><span data-stu-id="3d690-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="3d690-119">Letzter Schritt: Führen Sie das Cmdlet „Export-CcRootCertificate“ aus, um das Stammzertifikat in eine lokale Datei in der ersten Appliance zu exportieren. Kopieren Sie dann das exportierte Zertifikat, und installieren Sie es in Ihren PSTN-Gateways.
</span><span class="sxs-lookup"><span data-stu-id="3d690-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3d690-120">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="3d690-120">Input Types</span></span>
<span data-ttu-id="3d690-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d690-121"></span></span>

<span data-ttu-id="3d690-p104">Keine. Das Cmdlet „Renew-CcCACertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="3d690-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3d690-124">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="3d690-124">Return Types</span></span>
<span data-ttu-id="3d690-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d690-125"></span></span>

<span data-ttu-id="3d690-126">Keine </span><span class="sxs-lookup"><span data-stu-id="3d690-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d690-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d690-127">See also</span></span>
<span data-ttu-id="3d690-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d690-128"></span></span>

[<span data-ttu-id="3d690-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="3d690-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="3d690-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="3d690-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="3d690-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="3d690-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


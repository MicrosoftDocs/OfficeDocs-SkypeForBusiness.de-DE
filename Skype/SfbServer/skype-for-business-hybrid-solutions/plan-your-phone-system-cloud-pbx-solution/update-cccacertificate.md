---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Das Cmdlet Update-CcCACertificate erneuert das Skype for Business Cloud Connector Edition-Stammzertifizierungsstellen-Zertifikat, das nahezu abgelaufen ist oder bereits abgelaufen ist.
ms.openlocfilehash: e32b910d07aa4f2370af72d0a04bb939b80b3034
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286845"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="bac27-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bac27-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="bac27-104">Das Cmdlet Update-CcCACertificate erneuert das Skype for Business Cloud Connector Edition-Stammzertifizierungsstellen-Zertifikat, das nahezu abgelaufen ist oder bereits abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="bac27-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="bac27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bac27-105">Parameters</span></span>

<span data-ttu-id="bac27-106">Keine.</span><span class="sxs-lookup"><span data-stu-id="bac27-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="bac27-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bac27-107">Examples</span></span>
<span data-ttu-id="bac27-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bac27-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="bac27-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="bac27-109">Example 1</span></span>

<span data-ttu-id="bac27-110">Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert: </span><span class="sxs-lookup"><span data-stu-id="bac27-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="bac27-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bac27-111">Detailed Description</span></span>
<span data-ttu-id="bac27-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bac27-112"></span></span>

<span data-ttu-id="bac27-113">Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.</span><span class="sxs-lookup"><span data-stu-id="bac27-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="bac27-114">Wenn das Stammzertifikat nahezu abgelaufen ist oder bereits abgelaufen ist, führen Sie das Cmdlet Update-CcCACertificate aus, um das Zertifikat zu erneuern.</span><span class="sxs-lookup"><span data-stu-id="bac27-114">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate.</span></span> <span data-ttu-id="bac27-115">Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="bac27-115">After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="bac27-116">Wenn mehrere Appliances auf derselben PSTN-Website vorhanden sind, führen Sie das Cmdlet Update-CcCACertificate in allen Appliances der gleichen PSTN-Website aus.</span><span class="sxs-lookup"><span data-stu-id="bac27-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="bac27-117">Letzter Schritt: Führen Sie das Cmdlet „Export-CcRootCertificate“ aus, um das Stammzertifikat in eine lokale Datei in der ersten Appliance zu exportieren. Kopieren Sie dann das exportierte Zertifikat, und installieren Sie es in Ihren PSTN-Gateways.
</span><span class="sxs-lookup"><span data-stu-id="bac27-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="bac27-118">Dieser Befehl ersetzt das Cmdlet Renew-CcCACertificate in Cloud Connector 2,0 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="bac27-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="bac27-119">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="bac27-119">Input Types</span></span>
<span data-ttu-id="bac27-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bac27-120"></span></span>

<span data-ttu-id="bac27-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="bac27-121">None.</span></span> <span data-ttu-id="bac27-122">Das Cmdlet Update-CcCACertificate akzeptiert keine Pipelineeingabe.</span><span class="sxs-lookup"><span data-stu-id="bac27-122">The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bac27-123">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="bac27-123">Return Types</span></span>
<span data-ttu-id="bac27-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bac27-124"></span></span>

<span data-ttu-id="bac27-125">Keine.</span><span class="sxs-lookup"><span data-stu-id="bac27-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bac27-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bac27-126">See also</span></span>
<span data-ttu-id="bac27-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bac27-127"></span></span>

[<span data-ttu-id="bac27-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bac27-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="bac27-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bac27-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="bac27-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="bac27-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


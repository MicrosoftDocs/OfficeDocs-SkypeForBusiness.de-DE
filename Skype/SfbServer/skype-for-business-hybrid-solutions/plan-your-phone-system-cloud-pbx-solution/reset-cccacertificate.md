---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Das Cmdlet „Reset-CcCACertificate“ installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.
ms.openlocfilehash: 1ed9aaa8b7caf1edd5324d082094fa247c858853
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898536"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="860c8-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="860c8-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="860c8-104">Das Cmdlet „Reset-CcCACertificate“ installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="860c8-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="860c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="860c8-105">Parameters</span></span>

<span data-ttu-id="860c8-106">Keine</span><span class="sxs-lookup"><span data-stu-id="860c8-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="860c8-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="860c8-107">Examples</span></span>
<span data-ttu-id="860c8-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="860c8-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="860c8-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="860c8-109">Example 1</span></span>

<span data-ttu-id="860c8-110">Das folgende Beispiel installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="860c8-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="860c8-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="860c8-111">Detailed Description</span></span>
<span data-ttu-id="860c8-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="860c8-112"></span></span>

<span data-ttu-id="860c8-113">Wenn das Zertifikat der Stammzertifizierungsstelle kompromittiert oder nicht mehr sicher ist, müssen Sie das Zertifikat der Stammzertifizierungsstelle und alle von der Stammzertifizierungsstelle ausgestellten Zertifikate aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="860c8-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="860c8-114">Das Cmdlet „Reset-CcCACertificate“ widerruft alle Zertifikate, deinstalliert die Zertifizierungsstelle, installiert diese neu, und bereinigt dann alle Zertifikate, die sich auf den alten Zertifizierungsstellendienst beziehen.</span><span class="sxs-lookup"><span data-stu-id="860c8-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="860c8-115">Weitere Informationen finden Sie unter "Certificate Zertifikaten oder interne Zertifikate CMS, Vermittlungsserver und Edge-Server ausgestellt werden in der Nähe Ablauf oder sind beschädigt" bei der Problembehandlung Ihrer bereitstellungs Cloud-Connector.</span><span class="sxs-lookup"><span data-stu-id="860c8-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="860c8-116">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="860c8-116">Input Types</span></span>
<span data-ttu-id="860c8-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="860c8-117"></span></span>

<span data-ttu-id="860c8-p102">Keine. Das Cmdlet „Reset-CcCACertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="860c8-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="860c8-120">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="860c8-120">Return Types</span></span>
<span data-ttu-id="860c8-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="860c8-121"></span></span>

<span data-ttu-id="860c8-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="860c8-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="860c8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="860c8-123">See also</span></span>
<span data-ttu-id="860c8-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="860c8-124"></span></span>

<span data-ttu-id="860c8-125">[Erneuern CcCACertificate](renew-cccacertificate.md) Nur Version 1.4.2</span><span class="sxs-lookup"><span data-stu-id="860c8-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="860c8-126">[Erneuern CcServerCertificate](renew-ccservercertificate.md) Nur Version 1.4.2</span><span class="sxs-lookup"><span data-stu-id="860c8-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="860c8-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 und höher</span><span class="sxs-lookup"><span data-stu-id="860c8-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="860c8-128">[Erneuern CcServerCertificate](renew-ccservercertificate.md) Version 2.0 und höher</span><span class="sxs-lookup"><span data-stu-id="860c8-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="860c8-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="860c8-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


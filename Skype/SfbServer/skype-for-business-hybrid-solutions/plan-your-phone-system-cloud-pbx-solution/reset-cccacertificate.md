---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Das Cmdlet „Reset-CcCACertificate“ installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824251"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="1c489-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="1c489-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="1c489-104">Das Cmdlet „Reset-CcCACertificate“ installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c489-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="1c489-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c489-105">Parameters</span></span>

<span data-ttu-id="1c489-106">Keine</span><span class="sxs-lookup"><span data-stu-id="1c489-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1c489-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1c489-107">Examples</span></span>
<span data-ttu-id="1c489-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1c489-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1c489-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="1c489-109">Example 1</span></span>

<span data-ttu-id="1c489-110">Das folgende Beispiel installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c489-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="1c489-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c489-111">Detailed Description</span></span>
<span data-ttu-id="1c489-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1c489-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1c489-113">Wenn das Zertifikat der Stammzertifizierungsstelle kompromittiert oder nicht mehr sicher ist, müssen Sie das Zertifikat der Stammzertifizierungsstelle und alle von der Stammzertifizierungsstelle ausgestellten Zertifikate aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1c489-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="1c489-114">Das Cmdlet „Reset-CcCACertificate“ widerruft alle Zertifikate, deinstalliert die Zertifizierungsstelle, installiert diese neu, und bereinigt dann alle Zertifikate, die sich auf den alten Zertifizierungsstellendienst beziehen.</span><span class="sxs-lookup"><span data-stu-id="1c489-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="1c489-115">Weitere Informationen finden Sie unter "Zertifizierungsstellenzertifikate oder interne Zertifikate, die für CMS, Mediation Server und Edgeserver ausgestellt wurden, sind nahezu abgelaufen oder werden bei der Problembehandlung der Cloud Connector-Bereitstellung beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="1c489-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="1c489-116">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="1c489-116">Input Types</span></span>
<span data-ttu-id="1c489-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c489-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1c489-p102">Keine. Das Cmdlet „Reset-CcCACertificate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="1c489-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1c489-120">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="1c489-120">Return Types</span></span>
<span data-ttu-id="1c489-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c489-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1c489-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="1c489-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c489-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c489-123">See also</span></span>
<span data-ttu-id="1c489-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c489-124"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1c489-125">[Erneuern-CcCACertificate](renew-cccacertificate.md) Nur Version 1.4.2</span><span class="sxs-lookup"><span data-stu-id="1c489-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="1c489-126">[Erneuern-CcServerCertificate](renew-ccservercertificate.md) Nur Version 1.4.2</span><span class="sxs-lookup"><span data-stu-id="1c489-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="1c489-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2,0 und höher</span><span class="sxs-lookup"><span data-stu-id="1c489-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="1c489-128">[Erneuern-CcServerCertificate](renew-ccservercertificate.md) Version 2,0 und höher</span><span class="sxs-lookup"><span data-stu-id="1c489-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="1c489-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="1c489-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  


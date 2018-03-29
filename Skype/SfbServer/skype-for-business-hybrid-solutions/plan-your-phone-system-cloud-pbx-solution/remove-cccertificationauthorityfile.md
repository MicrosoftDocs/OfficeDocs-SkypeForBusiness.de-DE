---
title: Remove-CcCertificationAuthorityFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Das Cmdlet Remove-CcCertificationAuthorityFile entfernt die Sicherungsdatei Certification Authority Service im Ordner "Zertifizierungsstelle" unter Freigeben Websiteverzeichnis für Skype für Business Cloud Connector Edition.
ms.openlocfilehash: 0cc2470d6ee9312646feb3d459d6fb7a4c2bb30b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="fc22c-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="fc22c-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="fc22c-104">Das Remove-CcCertificationAuthorityFile-Cmdlet entfernt die Sicherungsdatei Certification Authority Service "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" im Ordner "Zertifizierungsstelle" unter Freigeben Websiteverzeichnis für Skype für Business Cloud-Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fc22c-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="fc22c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc22c-105">Parameters</span></span>

<span data-ttu-id="fc22c-106">Keine</span><span class="sxs-lookup"><span data-stu-id="fc22c-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="fc22c-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fc22c-107">Examples</span></span>
<span data-ttu-id="fc22c-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fc22c-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="fc22c-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="fc22c-109">Example 1</span></span>

<span data-ttu-id="fc22c-110">Das folgende Beispiel entfernt die Sicherungsdatei Certification Authority Service "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" im Ordner "Zertifizierungsstelle" unter dem Websiteverzeichnis freigeben:</span><span class="sxs-lookup"><span data-stu-id="fc22c-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="fc22c-111">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="fc22c-111">Input Types</span></span>
<span data-ttu-id="fc22c-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc22c-112"></span></span>

<span data-ttu-id="fc22c-p101">Keine. Das Cmdlet „Remove-CcCertificationAuthorityFile“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="fc22c-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fc22c-115">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="fc22c-115">Return Types</span></span>
<span data-ttu-id="fc22c-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc22c-116"></span></span>

<span data-ttu-id="fc22c-117">Keine</span><span class="sxs-lookup"><span data-stu-id="fc22c-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc22c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc22c-118">See also</span></span>
<span data-ttu-id="fc22c-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fc22c-119"></span></span>

[<span data-ttu-id="fc22c-120">Sicherung CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="fc22c-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  


---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Das Cmdlet Remove-CcCertificationAuthorityFile entfernt die Sicherungsdatei des Zertifizierungsstellendiensts im Ordner "Zertifizierungsstelle" unter dem Website Freigabeverzeichnis für Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824291"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="0b107-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="0b107-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="0b107-104">Das Cmdlet Remove-CcCertificationAuthorityFile entfernt die Zertifizierungsstellen-Dienst Sicherungs&lt;Datei&gt;"SiteRootDirectory \CA\SfB CCE root. p12" im Ordner "Zertifizierungsstelle" unter dem Website Freigabeverzeichnis für Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0b107-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="0b107-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b107-105">Parameters</span></span>

<span data-ttu-id="0b107-106">Keine</span><span class="sxs-lookup"><span data-stu-id="0b107-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="0b107-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0b107-107">Examples</span></span>
<span data-ttu-id="0b107-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0b107-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0b107-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="0b107-109">Example 1</span></span>

<span data-ttu-id="0b107-110">Im folgenden Beispiel wird die Sicherungsdatei des Zertifizierungsstellen&lt;Diensts&gt;"SiteRootDirectory \CA\SfB CCE root. p12" im Ordner "Zertifizierungsstelle" unterhalb des Website Freigabe Verzeichnisses entfernt:</span><span class="sxs-lookup"><span data-stu-id="0b107-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="0b107-111">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="0b107-111">Input Types</span></span>
<span data-ttu-id="0b107-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b107-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0b107-p101">Keine. Das Cmdlet „Remove-CcCertificationAuthorityFile“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="0b107-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0b107-115">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="0b107-115">Return Types</span></span>
<span data-ttu-id="0b107-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b107-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0b107-117">Keine </span><span class="sxs-lookup"><span data-stu-id="0b107-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b107-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b107-118">See also</span></span>
<span data-ttu-id="0b107-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b107-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="0b107-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="0b107-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  


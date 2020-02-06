---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803805"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="7d31d-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="7d31d-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="7d31d-104">Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.</span><span class="sxs-lookup"><span data-stu-id="7d31d-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="7d31d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d31d-105">Parameters</span></span>

<span data-ttu-id="7d31d-106">Keine</span><span class="sxs-lookup"><span data-stu-id="7d31d-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7d31d-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7d31d-107">Examples</span></span>
<span data-ttu-id="7d31d-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7d31d-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="7d31d-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="7d31d-109">Example 1</span></span>

<span data-ttu-id="7d31d-110">Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert, und diese wird im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts gespeichert:</span><span class="sxs-lookup"><span data-stu-id="7d31d-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="7d31d-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d31d-111">Detailed Description</span></span>
<span data-ttu-id="7d31d-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d31d-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="7d31d-113">Die Sicherung der Zertifizierungsstelle kann hilfreich sein, wenn Sie beabsichtigen, eine Cloud Connector-Appliance mit demselben Zertifikat für Notfälle erneut bereitzustellen, oder wenn Sie die Appliance auf eine neue Hardware verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7d31d-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="7d31d-114">Der Befehl speichert die Kopie des Diensts für die Cloud Connector-Zertifizierungsstelle vom anzeigen Server\<auf\>"SiteRootDirectory \CA\SfB CCE root. p12".</span><span class="sxs-lookup"><span data-stu-id="7d31d-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="7d31d-115">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="7d31d-115">Input Types</span></span>
<span data-ttu-id="7d31d-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d31d-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="7d31d-p102">Keine. Das Cmdlet „Backup-CcCertificationAuthority“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="7d31d-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7d31d-119">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="7d31d-119">Return Types</span></span>
<span data-ttu-id="7d31d-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d31d-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7d31d-121">Keine </span><span class="sxs-lookup"><span data-stu-id="7d31d-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d31d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d31d-122">See also</span></span>
<span data-ttu-id="7d31d-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d31d-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="7d31d-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="7d31d-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


---
title: Sicherung CcCertificationAuthority
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="ecf12-103">Sicherung CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="ecf12-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="ecf12-104">Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.</span><span class="sxs-lookup"><span data-stu-id="ecf12-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="ecf12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecf12-105">Parameters</span></span>

<span data-ttu-id="ecf12-106">Keine</span><span class="sxs-lookup"><span data-stu-id="ecf12-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ecf12-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ecf12-107">Examples</span></span>
<span data-ttu-id="ecf12-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ecf12-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="ecf12-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="ecf12-109">Example 1</span></span>

<span data-ttu-id="ecf12-110">Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert, und diese wird im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts gespeichert:</span><span class="sxs-lookup"><span data-stu-id="ecf12-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="ecf12-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf12-111">Detailed Description</span></span>
<span data-ttu-id="ecf12-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ecf12-112"></span></span>

<span data-ttu-id="ecf12-113">Certification Authority Sicherung kann hilfreich sein, wenn Sie eine Cloud-Connector Appliance mit demselben Zertifikat bei einem Notfall erneut bereitstellen möchten, oder wenn Sie die Einheit auf neue Hardware verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="ecf12-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="ecf12-114">Der Befehl speichert die Kopie der Dienst der Cloud Connector Zertifizierungsstelle aus den Active Directory-Server für "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span><span class="sxs-lookup"><span data-stu-id="ecf12-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ecf12-115">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="ecf12-115">Input Types</span></span>
<span data-ttu-id="ecf12-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ecf12-116"></span></span>

<span data-ttu-id="ecf12-p102">Keine. Das Cmdlet „Backup-CcCertificationAuthority“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="ecf12-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ecf12-119">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="ecf12-119">Return Types</span></span>
<span data-ttu-id="ecf12-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ecf12-120"></span></span>

<span data-ttu-id="ecf12-121">Keine</span><span class="sxs-lookup"><span data-stu-id="ecf12-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ecf12-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecf12-122">See also</span></span>
<span data-ttu-id="ecf12-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ecf12-123"></span></span>

[<span data-ttu-id="ecf12-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="ecf12-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


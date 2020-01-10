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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003025"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="1a7f9-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="1a7f9-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="1a7f9-104">Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.</span><span class="sxs-lookup"><span data-stu-id="1a7f9-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="1a7f9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a7f9-105">Parameters</span></span>

<span data-ttu-id="1a7f9-106">Keine</span><span class="sxs-lookup"><span data-stu-id="1a7f9-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1a7f9-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1a7f9-107">Examples</span></span>
<span data-ttu-id="1a7f9-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1a7f9-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="1a7f9-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="1a7f9-109">Example 1</span></span>

<span data-ttu-id="1a7f9-110">Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert, und diese wird im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts gespeichert:</span><span class="sxs-lookup"><span data-stu-id="1a7f9-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="1a7f9-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a7f9-111">Detailed Description</span></span>
<span data-ttu-id="1a7f9-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1a7f9-112"></span></span>

<span data-ttu-id="1a7f9-113">Die Sicherung der Zertifizierungsstelle kann hilfreich sein, wenn Sie beabsichtigen, eine Cloud Connector-Appliance mit demselben Zertifikat für Notfälle erneut bereitzustellen, oder wenn Sie die Appliance auf eine neue Hardware verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1a7f9-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="1a7f9-114">Der Befehl speichert die Kopie des Diensts für die Cloud Connector-Zertifizierungsstelle vom anzeigen Server\<auf\>"SiteRootDirectory \CA\SfB CCE root. p12".</span><span class="sxs-lookup"><span data-stu-id="1a7f9-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="1a7f9-115">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="1a7f9-115">Input Types</span></span>
<span data-ttu-id="1a7f9-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1a7f9-116"></span></span>

<span data-ttu-id="1a7f9-p102">Keine. Das Cmdlet „Backup-CcCertificationAuthority“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="1a7f9-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1a7f9-119">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="1a7f9-119">Return Types</span></span>
<span data-ttu-id="1a7f9-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1a7f9-120"></span></span>

<span data-ttu-id="1a7f9-121">Keine </span><span class="sxs-lookup"><span data-stu-id="1a7f9-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a7f9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a7f9-122">See also</span></span>
<span data-ttu-id="1a7f9-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1a7f9-123"></span></span>

[<span data-ttu-id="1a7f9-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="1a7f9-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  


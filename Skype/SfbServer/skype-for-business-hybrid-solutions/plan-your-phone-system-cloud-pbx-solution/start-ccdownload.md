---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Das Cmdlet Start-CcDownload downloads der Skype für Business Cloud Connector Edition Bits und MSI-Datei synchron.
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893838"
---
# <a name="start-ccdownload"></a><span data-ttu-id="9c4fe-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="9c4fe-103">Start-CcDownload</span></span>
 
<span data-ttu-id="9c4fe-104">Das Cmdlet Start-CcDownload downloads der Skype für Business Cloud Connector Edition Bits und MSI-Datei synchron.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="9c4fe-105">Mit der Cloud Connector, Version 2.0 und höher können Sie auch den DownloadBitsOnly-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9c4fe-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9c4fe-106">Examples</span></span>
<span data-ttu-id="9c4fe-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9c4fe-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="9c4fe-108">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="9c4fe-108">Example 1</span></span>

<span data-ttu-id="9c4fe-109">Im folgenden Beispiel wird lädt die Cloud Connector Bits und MSI-Datei synchron aus der Downloadsite für die öffentliche Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9c4fe-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="9c4fe-110">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="9c4fe-110">Example 2</span></span>

<span data-ttu-id="9c4fe-111">Im nächste Beispiel lädt die Cloud Connector Bits und MSI-Datei synchron aus einer privaten Download-Website:</span><span class="sxs-lookup"><span data-stu-id="9c4fe-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="9c4fe-112">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="9c4fe-112">Example 3</span></span>

<span data-ttu-id="9c4fe-113">Im dritte Beispiel lädt die Cloud Connector Bits und MSI-Datei synchron aus einer privaten Download-Website.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="9c4fe-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c4fe-114">Detailed Description</span></span>
<span data-ttu-id="9c4fe-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9c4fe-115"></span></span>

<span data-ttu-id="9c4fe-116">Wenn in der Download-Website eine neue Version verfügbar ist, stellt Start CcDownload herunterladen und installieren Sie die MSI-Datei von der Downloadsite und Laden Sie die Cloud Connector Bits synchron.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="9c4fe-117">Wenn keine neue Version der MSI-Datei vorhanden ist, wird Start CcDownload nur die Cloud Connector Bits herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="9c4fe-118">Wenn die Bits Cloud Connector bereits heruntergeladen werden, wird die Start-CcDownload nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9c4fe-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c4fe-119">Parameters</span></span>
<span data-ttu-id="9c4fe-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9c4fe-120"></span></span>

|<span data-ttu-id="9c4fe-121">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="9c4fe-121">**Parameter**</span></span>|<span data-ttu-id="9c4fe-122">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="9c4fe-122">**Required**</span></span>|<span data-ttu-id="9c4fe-123">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9c4fe-123">**Type**</span></span>|<span data-ttu-id="9c4fe-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9c4fe-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c4fe-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="9c4fe-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="9c4fe-126">Optional </span><span class="sxs-lookup"><span data-stu-id="9c4fe-126">Optional</span></span> <br/> |<span data-ttu-id="9c4fe-127">System.String</span><span class="sxs-lookup"><span data-stu-id="9c4fe-127">System.String</span></span>  <br/> | <span data-ttu-id="9c4fe-128">Die vollständige URL einer bestimmten Version von Cloud-Connector in der privaten Downloadsite.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="9c4fe-129">Verwenden Sie diesen Parameter mit Bedacht – achten, welche Version von Cloud-Connector Sie herunterladen bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="9c4fe-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="9c4fe-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="9c4fe-131">Optional</span><span class="sxs-lookup"><span data-stu-id="9c4fe-131">Optional</span></span>  <br/> |<span data-ttu-id="9c4fe-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9c4fe-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9c4fe-133">Überspringen Sie den Schritt zum Herunterladen und Installieren von MSI von Download-Website, nur die Cloud Connector Bits herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9c4fe-134">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="9c4fe-134">Input Types</span></span>
<span data-ttu-id="9c4fe-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9c4fe-135"></span></span>

<span data-ttu-id="9c4fe-136">Keine.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-136">None.</span></span> <span data-ttu-id="9c4fe-137">Das Cmdlet Start-CcDownload akzeptiert keine weitergeleitete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="9c4fe-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9c4fe-138">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="9c4fe-138">Return Types</span></span>
<span data-ttu-id="9c4fe-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9c4fe-139"></span></span>

<span data-ttu-id="9c4fe-140">Keine </span><span class="sxs-lookup"><span data-stu-id="9c4fe-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9c4fe-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c4fe-141">See also</span></span>
<span data-ttu-id="9c4fe-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9c4fe-142"></span></span>

<span data-ttu-id="9c4fe-143">Keine</span><span class="sxs-lookup"><span data-stu-id="9c4fe-143">None</span></span>
  


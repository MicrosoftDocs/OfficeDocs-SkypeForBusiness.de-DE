---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Das Cmdlet "Start-CcDownload" lädt die Bits und die MSI-Datei von Skype for Business Cloud Connector Edition synchron herunter.
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286943"
---
# <a name="start-ccdownload"></a><span data-ttu-id="d2314-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="d2314-103">Start-CcDownload</span></span>
 
<span data-ttu-id="d2314-104">Das Cmdlet "Start-CcDownload" lädt die Bits und die MSI-Datei von Skype for Business Cloud Connector Edition synchron herunter.</span><span class="sxs-lookup"><span data-stu-id="d2314-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="d2314-105">Mit Cloud Connector Version 2,0 und höher können Sie auch den DownloadBitsOnly-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="d2314-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="d2314-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d2314-106">Examples</span></span>
<span data-ttu-id="d2314-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d2314-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="d2314-108">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="d2314-108">Example 1</span></span>

<span data-ttu-id="d2314-109">Im folgenden Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von der öffentlichen Download Website des Cloud Connectors heruntergeladen:</span><span class="sxs-lookup"><span data-stu-id="d2314-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="d2314-110">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="d2314-110">Example 2</span></span>

<span data-ttu-id="d2314-111">Im nächsten Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von einer privaten Download Website heruntergeladen:</span><span class="sxs-lookup"><span data-stu-id="d2314-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="d2314-112">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="d2314-112">Example 3</span></span>

<span data-ttu-id="d2314-113">Im dritten Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von einer privaten Download Website heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="d2314-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="d2314-114">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2314-114">Detailed Description</span></span>
<span data-ttu-id="d2314-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d2314-115"></span></span>

<span data-ttu-id="d2314-116">Wenn auf der Download Website eine neue Version verfügbar ist, wird die MSI-Datei von Start-CcDownload von der Download Website heruntergeladen und installiert, und die Cloud Connector-Bits werden dann synchron heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="d2314-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="d2314-117">Wenn keine neue Version der MSI-Datei vorhanden ist, werden die Cloud Connector-Bits nur von Start-CcDownload heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="d2314-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="d2314-118">Wenn die Cloud Connector-Bits bereits heruntergeladen wurden, wird Start-CcDownload nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d2314-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d2314-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2314-119">Parameters</span></span>
<span data-ttu-id="d2314-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d2314-120"></span></span>

|<span data-ttu-id="d2314-121">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="d2314-121">**Parameter**</span></span>|<span data-ttu-id="d2314-122">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="d2314-122">**Required**</span></span>|<span data-ttu-id="d2314-123">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d2314-123">**Type**</span></span>|<span data-ttu-id="d2314-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d2314-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d2314-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="d2314-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="d2314-126">Optional </span><span class="sxs-lookup"><span data-stu-id="d2314-126">Optional</span></span> <br/> |<span data-ttu-id="d2314-127">System.String</span><span class="sxs-lookup"><span data-stu-id="d2314-127">System.String</span></span>  <br/> | <span data-ttu-id="d2314-128">Die vollständige URL einer bestimmten Version von Cloud Connector auf der privaten Download Website.</span><span class="sxs-lookup"><span data-stu-id="d2314-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="d2314-129">Verwenden Sie diesen Parameter mit Bedacht – stellen Sie sicher, dass Sie wissen, welche Version von Cloud Connector Sie herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d2314-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="d2314-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="d2314-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="d2314-131">Optional</span><span class="sxs-lookup"><span data-stu-id="d2314-131">Optional</span></span>  <br/> |<span data-ttu-id="d2314-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d2314-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d2314-133">Überspringen Sie den Schritt zum herunterladen und Installieren von MSI von der Download Website, laden Sie nur die Bits für die Cloud-Connectors herunter.</span><span class="sxs-lookup"><span data-stu-id="d2314-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d2314-134">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="d2314-134">Input Types</span></span>
<span data-ttu-id="d2314-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d2314-135"></span></span>

<span data-ttu-id="d2314-136">Keine.</span><span class="sxs-lookup"><span data-stu-id="d2314-136">None.</span></span> <span data-ttu-id="d2314-137">Das Start-CcDownload-Cmdlet akzeptiert keine Pipeline-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d2314-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d2314-138">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="d2314-138">Return Types</span></span>
<span data-ttu-id="d2314-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d2314-139"></span></span>

<span data-ttu-id="d2314-140">Keine </span><span class="sxs-lookup"><span data-stu-id="d2314-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2314-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2314-141">See also</span></span>
<span data-ttu-id="d2314-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d2314-142"></span></span>

<span data-ttu-id="d2314-143">Keine</span><span class="sxs-lookup"><span data-stu-id="d2314-143">None</span></span>
  


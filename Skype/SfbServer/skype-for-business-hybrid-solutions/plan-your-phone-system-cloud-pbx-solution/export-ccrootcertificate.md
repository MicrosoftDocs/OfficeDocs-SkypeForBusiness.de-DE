---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Das Cmdlet „Export-CcRootCertificate“ exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Hostserver von Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: c2647baa9ab6762feb8f550e0d726b18ab5d3090
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889224"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="28ab3-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="28ab3-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="28ab3-104">Das Cmdlet „Export-CcRootCertificate“ exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Hostserver von Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="28ab3-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="28ab3-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="28ab3-105">Examples</span></span>
<span data-ttu-id="28ab3-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="28ab3-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="28ab3-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="28ab3-107">Example 1</span></span>

<span data-ttu-id="28ab3-p101">Im folgenden Beispiel wird der „Path“-Parameter als Verzeichnispfad festgelegt, nicht als Dateipfad. Damit wird die Datei „c:\test\CCERootCertificates.p7b“ generiert.</span><span class="sxs-lookup"><span data-stu-id="28ab3-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="28ab3-110">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28ab3-110">Detailed Description</span></span>
<span data-ttu-id="28ab3-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="28ab3-111"></span></span>

<span data-ttu-id="28ab3-p102">Mit dem Cmdlet „Export-CcRootCertificate“ können Sie die Stamm- und Zwischenzertifikate in einem Dateipfad speichern. Dies kann in Notfallwiederherstellungs-Szenarien hilfreich sein. </span><span class="sxs-lookup"><span data-stu-id="28ab3-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="28ab3-114">Parameter</span><span class="sxs-lookup"><span data-stu-id="28ab3-114">Parameters</span></span>
<span data-ttu-id="28ab3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="28ab3-115"></span></span>

|<span data-ttu-id="28ab3-116">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="28ab3-116">**Parameter**</span></span>|<span data-ttu-id="28ab3-117">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="28ab3-117">**Required**</span></span>|<span data-ttu-id="28ab3-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="28ab3-118">**Type**</span></span>|<span data-ttu-id="28ab3-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="28ab3-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28ab3-120"> Path</span><span class="sxs-lookup"><span data-stu-id="28ab3-120">Path</span></span>  <br/> |<span data-ttu-id="28ab3-121">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="28ab3-121">Required</span></span>  <br/> |<span data-ttu-id="28ab3-122">System.String</span><span class="sxs-lookup"><span data-stu-id="28ab3-122">System.String</span></span>  <br/> |<span data-ttu-id="28ab3-123">Dateipfad, in dem das Zertifikat gespeichert wird </span><span class="sxs-lookup"><span data-stu-id="28ab3-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="28ab3-124">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="28ab3-124">Input Types</span></span>
<span data-ttu-id="28ab3-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28ab3-125"></span></span>

<span data-ttu-id="28ab3-p103">Keine. Das Cmdlet „Export-CcRootCertificate“ akzeptiert keine Pipelineeingaben. </span><span class="sxs-lookup"><span data-stu-id="28ab3-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="28ab3-128">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="28ab3-128">Return Types</span></span>
<span data-ttu-id="28ab3-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28ab3-129"></span></span>

<span data-ttu-id="28ab3-130">Keine </span><span class="sxs-lookup"><span data-stu-id="28ab3-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28ab3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28ab3-131">See also</span></span>
<span data-ttu-id="28ab3-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="28ab3-132"></span></span>

<span data-ttu-id="28ab3-133">Keine</span><span class="sxs-lookup"><span data-stu-id="28ab3-133">None</span></span>
  


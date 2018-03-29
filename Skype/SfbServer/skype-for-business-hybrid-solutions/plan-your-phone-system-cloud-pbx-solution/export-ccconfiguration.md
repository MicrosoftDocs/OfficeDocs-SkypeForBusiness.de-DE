---
title: Export-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Die Skype für Business Cloud Connector Edition-Konfiguration exportiert in einer lokalen Datei auf die Skype für Hostserver Business Cloud Connector Edition.
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="f456a-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="f456a-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="f456a-104">Die Skype für Business Cloud Connector Edition-Konfiguration exportiert in einer lokalen Datei auf die Skype für Hostserver Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f456a-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="f456a-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f456a-105">Examples</span></span>
<span data-ttu-id="f456a-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f456a-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="f456a-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="f456a-107">Example 1</span></span>

<span data-ttu-id="f456a-108">Im folgende Beispiel wird den Parameter Path als einen vollständigen Dateipfad und Konfigurationen in dieser Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="f456a-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="f456a-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f456a-109">Detailed Description</span></span>
<span data-ttu-id="f456a-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f456a-110"></span></span>

<span data-ttu-id="f456a-111">Das Cmdlet Export-CcConfiguration können Sie die Cloud Connectorkonfiguration in eine Datei in einem ausgewählten Pfad zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f456a-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="f456a-112">Mit diesem Befehl wurde in der Cloud Connector Edition, Version 2.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f456a-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f456a-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="f456a-113">Parameters</span></span>
<span data-ttu-id="f456a-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f456a-114"></span></span>

|<span data-ttu-id="f456a-115">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="f456a-115">**Parameter**</span></span>|<span data-ttu-id="f456a-116">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="f456a-116">**Required**</span></span>|<span data-ttu-id="f456a-117">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f456a-117">**Type**</span></span>|<span data-ttu-id="f456a-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f456a-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f456a-119"> Path</span><span class="sxs-lookup"><span data-stu-id="f456a-119">Path</span></span>  <br/> |<span data-ttu-id="f456a-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="f456a-120">Required</span></span>  <br/> |<span data-ttu-id="f456a-121">System.String</span><span class="sxs-lookup"><span data-stu-id="f456a-121">System.String</span></span>  <br/> |<span data-ttu-id="f456a-122">Vollständigen Pfad, in dem die Cloud Connector Konfigurationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f456a-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f456a-123">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="f456a-123">Input Types</span></span>
<span data-ttu-id="f456a-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f456a-124"></span></span>

<span data-ttu-id="f456a-125">Keine.</span><span class="sxs-lookup"><span data-stu-id="f456a-125">None.</span></span> <span data-ttu-id="f456a-126">Das Cmdlet Export-CcConfiguration akzeptiert keine weitergeleitete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="f456a-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f456a-127">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="f456a-127">Return Types</span></span>
<span data-ttu-id="f456a-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f456a-128"></span></span>

<span data-ttu-id="f456a-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="f456a-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f456a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f456a-130">See also</span></span>
<span data-ttu-id="f456a-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f456a-131"></span></span>

<span data-ttu-id="f456a-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="f456a-132">Import-CcConfiguration</span></span>
  


---
title: Export-CcConfiguration
ms.reviewer: ''
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
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894237"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="3efc8-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3efc8-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="3efc8-104">Die Skype für Business Cloud Connector Edition-Konfiguration exportiert in einer lokalen Datei auf die Skype für Hostserver Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="3efc8-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3efc8-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3efc8-105">Examples</span></span>
<span data-ttu-id="3efc8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3efc8-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="3efc8-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="3efc8-107">Example 1</span></span>

<span data-ttu-id="3efc8-108">Im folgende Beispiel wird den Parameter Path als einen vollständigen Dateipfad und Konfigurationen in dieser Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="3efc8-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="3efc8-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3efc8-109">Detailed Description</span></span>
<span data-ttu-id="3efc8-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3efc8-110"></span></span>

<span data-ttu-id="3efc8-111">Das Cmdlet Export-CcConfiguration können Sie die Cloud Connectorkonfiguration in eine Datei in einem ausgewählten Pfad zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3efc8-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="3efc8-112">Mit diesem Befehl wurde in der Cloud Connector Edition, Version 2.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3efc8-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3efc8-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="3efc8-113">Parameters</span></span>
<span data-ttu-id="3efc8-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3efc8-114"></span></span>

|<span data-ttu-id="3efc8-115">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="3efc8-115">**Parameter**</span></span>|<span data-ttu-id="3efc8-116">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="3efc8-116">**Required**</span></span>|<span data-ttu-id="3efc8-117">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3efc8-117">**Type**</span></span>|<span data-ttu-id="3efc8-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3efc8-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3efc8-119"> Path</span><span class="sxs-lookup"><span data-stu-id="3efc8-119">Path</span></span>  <br/> |<span data-ttu-id="3efc8-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="3efc8-120">Required</span></span>  <br/> |<span data-ttu-id="3efc8-121">System.String</span><span class="sxs-lookup"><span data-stu-id="3efc8-121">System.String</span></span>  <br/> |<span data-ttu-id="3efc8-122">Vollständigen Pfad, in dem die Cloud Connector Konfigurationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3efc8-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3efc8-123">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="3efc8-123">Input Types</span></span>
<span data-ttu-id="3efc8-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3efc8-124"></span></span>

<span data-ttu-id="3efc8-125">Keine.</span><span class="sxs-lookup"><span data-stu-id="3efc8-125">None.</span></span> <span data-ttu-id="3efc8-126">Das Cmdlet Export-CcConfiguration akzeptiert keine weitergeleitete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="3efc8-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3efc8-127">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="3efc8-127">Return Types</span></span>
<span data-ttu-id="3efc8-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3efc8-128"></span></span>

<span data-ttu-id="3efc8-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="3efc8-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3efc8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3efc8-130">See also</span></span>
<span data-ttu-id="3efc8-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3efc8-131"></span></span>

<span data-ttu-id="3efc8-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3efc8-132">Import-CcConfiguration</span></span>
  


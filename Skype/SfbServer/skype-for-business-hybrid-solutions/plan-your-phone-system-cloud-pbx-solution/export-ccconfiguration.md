---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exportiert die Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287419"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="bafc6-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="bafc6-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="bafc6-104">Exportiert die Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver.</span><span class="sxs-lookup"><span data-stu-id="bafc6-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="bafc6-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bafc6-105">Examples</span></span>
<span data-ttu-id="bafc6-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bafc6-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="bafc6-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="bafc6-107">Example 1</span></span>

<span data-ttu-id="bafc6-108">Im folgenden Beispiel wird der path-Parameter als vollständiger Dateipfad festgelegt und Konfigurationen in diese Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="bafc6-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="bafc6-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bafc6-109">Detailed Description</span></span>
<span data-ttu-id="bafc6-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bafc6-110"></span></span>

<span data-ttu-id="bafc6-111">Mit dem Cmdlet Export-CcConfiguration können Sie die Cloud Connector-Konfiguration in einer Datei in einem ausgewählten Pfad speichern.</span><span class="sxs-lookup"><span data-stu-id="bafc6-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="bafc6-112">Dieser Befehl wurde in Cloud Connector Edition, Version 2,0, eingeführt.</span><span class="sxs-lookup"><span data-stu-id="bafc6-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bafc6-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="bafc6-113">Parameters</span></span>
<span data-ttu-id="bafc6-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bafc6-114"></span></span>

|<span data-ttu-id="bafc6-115">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="bafc6-115">**Parameter**</span></span>|<span data-ttu-id="bafc6-116">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="bafc6-116">**Required**</span></span>|<span data-ttu-id="bafc6-117">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bafc6-117">**Type**</span></span>|<span data-ttu-id="bafc6-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bafc6-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bafc6-119"> Path</span><span class="sxs-lookup"><span data-stu-id="bafc6-119">Path</span></span>  <br/> |<span data-ttu-id="bafc6-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="bafc6-120">Required</span></span>  <br/> |<span data-ttu-id="bafc6-121">System.String</span><span class="sxs-lookup"><span data-stu-id="bafc6-121">System.String</span></span>  <br/> |<span data-ttu-id="bafc6-122">Vollständiger Dateipfad, in dem die Cloud Connector-Konfigurationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bafc6-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="bafc6-123">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="bafc6-123">Input Types</span></span>
<span data-ttu-id="bafc6-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bafc6-124"></span></span>

<span data-ttu-id="bafc6-125">Keine.</span><span class="sxs-lookup"><span data-stu-id="bafc6-125">None.</span></span> <span data-ttu-id="bafc6-126">Das Cmdlet "Export-CcConfiguration" akzeptiert keine Pipeline-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="bafc6-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bafc6-127">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="bafc6-127">Return Types</span></span>
<span data-ttu-id="bafc6-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bafc6-128"></span></span>

<span data-ttu-id="bafc6-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="bafc6-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bafc6-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bafc6-130">See also</span></span>
<span data-ttu-id="bafc6-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bafc6-131"></span></span>

<span data-ttu-id="bafc6-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="bafc6-132">Import-CcConfiguration</span></span>
  


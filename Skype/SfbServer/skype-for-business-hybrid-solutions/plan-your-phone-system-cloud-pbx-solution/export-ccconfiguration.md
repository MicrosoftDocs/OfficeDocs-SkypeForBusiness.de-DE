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
ms.openlocfilehash: cb3ea5a48c4e8911dc94526f85a517082d057b6e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003435"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="6a65b-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="6a65b-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="6a65b-104">Exportiert die Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver.</span><span class="sxs-lookup"><span data-stu-id="6a65b-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="6a65b-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a65b-105">Examples</span></span>
<span data-ttu-id="6a65b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a65b-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="6a65b-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="6a65b-107">Example 1</span></span>

<span data-ttu-id="6a65b-108">Im folgenden Beispiel wird der path-Parameter als vollständiger Dateipfad festgelegt und Konfigurationen in diese Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="6a65b-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="6a65b-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a65b-109">Detailed Description</span></span>
<span data-ttu-id="6a65b-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a65b-110"></span></span>

<span data-ttu-id="6a65b-111">Mit dem Cmdlet Export-CcConfiguration können Sie die Cloud Connector-Konfiguration in einer Datei in einem ausgewählten Pfad speichern.</span><span class="sxs-lookup"><span data-stu-id="6a65b-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="6a65b-112">Dieser Befehl wurde in Cloud Connector Edition, Version 2,0, eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6a65b-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6a65b-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a65b-113">Parameters</span></span>
<span data-ttu-id="6a65b-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a65b-114"></span></span>

|<span data-ttu-id="6a65b-115">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="6a65b-115">**Parameter**</span></span>|<span data-ttu-id="6a65b-116">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="6a65b-116">**Required**</span></span>|<span data-ttu-id="6a65b-117">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6a65b-117">**Type**</span></span>|<span data-ttu-id="6a65b-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6a65b-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6a65b-119"> Path</span><span class="sxs-lookup"><span data-stu-id="6a65b-119">Path</span></span>  <br/> |<span data-ttu-id="6a65b-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="6a65b-120">Required</span></span>  <br/> |<span data-ttu-id="6a65b-121">System.String</span><span class="sxs-lookup"><span data-stu-id="6a65b-121">System.String</span></span>  <br/> |<span data-ttu-id="6a65b-122">Vollständiger Dateipfad, in dem die Cloud Connector-Konfigurationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6a65b-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6a65b-123">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="6a65b-123">Input Types</span></span>
<span data-ttu-id="6a65b-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a65b-124"></span></span>

<span data-ttu-id="6a65b-125">Keine.</span><span class="sxs-lookup"><span data-stu-id="6a65b-125">None.</span></span> <span data-ttu-id="6a65b-126">Das Cmdlet "Export-CcConfiguration" akzeptiert keine Pipeline-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="6a65b-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6a65b-127">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="6a65b-127">Return Types</span></span>
<span data-ttu-id="6a65b-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a65b-128"></span></span>

<span data-ttu-id="6a65b-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="6a65b-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a65b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a65b-130">See also</span></span>
<span data-ttu-id="6a65b-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6a65b-131"></span></span>

<span data-ttu-id="6a65b-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="6a65b-132">Import-CcConfiguration</span></span>
  


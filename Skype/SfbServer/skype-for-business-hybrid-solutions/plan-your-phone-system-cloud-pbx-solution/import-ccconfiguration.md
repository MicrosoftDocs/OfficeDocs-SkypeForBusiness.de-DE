---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287279"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="cf1a1-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf1a1-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="cf1a1-104">Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="cf1a1-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cf1a1-105">Examples</span></span>
<span data-ttu-id="cf1a1-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1a1-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="cf1a1-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="cf1a1-107">Example 1</span></span>

<span data-ttu-id="cf1a1-108">Im folgenden Beispiel wird die CloudConnector. ini aus dem Appliance-Verzeichnis der Cloud Connector-Instanz in das%SystemDrive%\ProgramData\CloudConnector-Verzeichnis kopiert:</span><span class="sxs-lookup"><span data-stu-id="cf1a1-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="cf1a1-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf1a1-109">Detailed Description</span></span>
<span data-ttu-id="cf1a1-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1a1-110"></span></span>

<span data-ttu-id="cf1a1-111">Mit diesem Cmdlet wird die CloudConnector. ini aus dem Appliance-Verzeichnis der Cloud Connector-Appliance in das%SystemDrive%\ProgramData\CloudConnector-Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="cf1a1-112">Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="cf1a1-113">Mit dem Cmdlet werden alle vorhandenen Dateien in%SystemDrive%\ProgramData\CloudConnector. überschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="cf1a1-114">Dieser Befehl gilt für Cloud Connector Edition Version 2.0.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="cf1a1-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf1a1-115">Parameters</span></span>
<span data-ttu-id="cf1a1-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1a1-116"></span></span>

|<span data-ttu-id="cf1a1-117">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="cf1a1-117">**Parameter**</span></span>|<span data-ttu-id="cf1a1-118">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="cf1a1-118">**Required**</span></span>|<span data-ttu-id="cf1a1-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="cf1a1-119">**Type**</span></span>|<span data-ttu-id="cf1a1-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cf1a1-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf1a1-121">Force</span><span class="sxs-lookup"><span data-stu-id="cf1a1-121">Force</span></span>  <br/> |<span data-ttu-id="cf1a1-122">Optional</span><span class="sxs-lookup"><span data-stu-id="cf1a1-122">Optional</span></span>  <br/> |<span data-ttu-id="cf1a1-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cf1a1-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="cf1a1-124">Vorhandene Datei in%SystemDrive%\ProgramData\CloudConnector ohne Benachrichtigung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="cf1a1-125">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="cf1a1-125">Input Types</span></span>
<span data-ttu-id="cf1a1-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1a1-126"></span></span>

<span data-ttu-id="cf1a1-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-127">None.</span></span> <span data-ttu-id="cf1a1-128">Das Cmdlet "Import-CcConfiguration" akzeptiert keine Pipeline-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cf1a1-129">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="cf1a1-129">Return Types</span></span>
<span data-ttu-id="cf1a1-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1a1-130"></span></span>

<span data-ttu-id="cf1a1-131">Keine.</span><span class="sxs-lookup"><span data-stu-id="cf1a1-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf1a1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf1a1-132">See also</span></span>
<span data-ttu-id="cf1a1-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cf1a1-133"></span></span>

<span data-ttu-id="cf1a1-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="cf1a1-134">Export-CcConfiguration</span></span>
  


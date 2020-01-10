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
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003335"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="c4c15-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4c15-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="c4c15-104">Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.</span><span class="sxs-lookup"><span data-stu-id="c4c15-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c4c15-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c4c15-105">Examples</span></span>
<span data-ttu-id="c4c15-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c4c15-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="c4c15-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="c4c15-107">Example 1</span></span>

<span data-ttu-id="c4c15-108">Im folgenden Beispiel wird die CloudConnector. ini aus dem Appliance-Verzeichnis der Cloud Connector-Instanz in das%SystemDrive%\ProgramData\CloudConnector-Verzeichnis kopiert:</span><span class="sxs-lookup"><span data-stu-id="c4c15-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="c4c15-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4c15-109">Detailed Description</span></span>
<span data-ttu-id="c4c15-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c4c15-110"></span></span>

<span data-ttu-id="c4c15-111">Mit diesem Cmdlet wird die CloudConnector. ini aus dem Appliance-Verzeichnis der Cloud Connector-Appliance in das%SystemDrive%\ProgramData\CloudConnector-Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="c4c15-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="c4c15-112">Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.</span><span class="sxs-lookup"><span data-stu-id="c4c15-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="c4c15-113">Mit dem Cmdlet werden alle vorhandenen Dateien in%SystemDrive%\ProgramData\CloudConnector. überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4c15-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="c4c15-114">Dieser Befehl gilt für Cloud Connector Edition Version 2.0.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="c4c15-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c4c15-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4c15-115">Parameters</span></span>
<span data-ttu-id="c4c15-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c4c15-116"></span></span>

|<span data-ttu-id="c4c15-117">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="c4c15-117">**Parameter**</span></span>|<span data-ttu-id="c4c15-118">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="c4c15-118">**Required**</span></span>|<span data-ttu-id="c4c15-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c4c15-119">**Type**</span></span>|<span data-ttu-id="c4c15-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c4c15-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4c15-121">Force</span><span class="sxs-lookup"><span data-stu-id="c4c15-121">Force</span></span>  <br/> |<span data-ttu-id="c4c15-122">Optional</span><span class="sxs-lookup"><span data-stu-id="c4c15-122">Optional</span></span>  <br/> |<span data-ttu-id="c4c15-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c4c15-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c4c15-124">Vorhandene Datei in%SystemDrive%\ProgramData\CloudConnector ohne Benachrichtigung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c4c15-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c4c15-125">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="c4c15-125">Input Types</span></span>
<span data-ttu-id="c4c15-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c4c15-126"></span></span>

<span data-ttu-id="c4c15-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c15-127">None.</span></span> <span data-ttu-id="c4c15-128">Das Cmdlet "Import-CcConfiguration" akzeptiert keine Pipeline-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c4c15-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c4c15-129">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="c4c15-129">Return Types</span></span>
<span data-ttu-id="c4c15-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c4c15-130"></span></span>

<span data-ttu-id="c4c15-131">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c15-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4c15-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4c15-132">See also</span></span>
<span data-ttu-id="c4c15-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c4c15-133"></span></span>

<span data-ttu-id="c4c15-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4c15-134">Export-CcConfiguration</span></span>
  


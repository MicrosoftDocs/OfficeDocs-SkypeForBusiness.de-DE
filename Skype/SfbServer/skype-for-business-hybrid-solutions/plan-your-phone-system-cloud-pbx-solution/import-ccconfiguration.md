---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importiert die Skype für Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf die Cloud Connector-Hostserver.
ms.openlocfilehash: 497568f45fad6b4363581785bf0be95eabfeaebf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233771"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="c60d8-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c60d8-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="c60d8-104">Importiert die Skype für Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf die Cloud Connector-Hostserver.</span><span class="sxs-lookup"><span data-stu-id="c60d8-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c60d8-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c60d8-105">Examples</span></span>
<span data-ttu-id="c60d8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c60d8-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="c60d8-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="c60d8-107">Example 1</span></span>

<span data-ttu-id="c60d8-108">Das folgende Beispiel kopiert die CloudConnector.ini aus dem Verzeichnis Appliance der Cloud Connector-Instanz zu %SystemDrive%\ProgramData\CloudConnector Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c60d8-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="c60d8-109">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c60d8-109">Detailed Description</span></span>
<span data-ttu-id="c60d8-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c60d8-110"></span></span>

<span data-ttu-id="c60d8-111">Dieses Cmdlet kopiert die CloudConnector.ini aus dem Verzeichnis Appliance der Appliance Cloud-Connector in das Verzeichnis %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c60d8-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="c60d8-112">Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.</span><span class="sxs-lookup"><span data-stu-id="c60d8-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="c60d8-113">Das Cmdlet überschreibt vorhandene Dateien in % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c60d8-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="c60d8-114">Dieser Befehl gilt für Cloud Connector Edition Version 2.0.1 und höher.</span><span class="sxs-lookup"><span data-stu-id="c60d8-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c60d8-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="c60d8-115">Parameters</span></span>
<span data-ttu-id="c60d8-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c60d8-116"></span></span>

|<span data-ttu-id="c60d8-117">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="c60d8-117">**Parameter**</span></span>|<span data-ttu-id="c60d8-118">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="c60d8-118">**Required**</span></span>|<span data-ttu-id="c60d8-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c60d8-119">**Type**</span></span>|<span data-ttu-id="c60d8-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c60d8-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c60d8-121">Force</span><span class="sxs-lookup"><span data-stu-id="c60d8-121">Force</span></span>  <br/> |<span data-ttu-id="c60d8-122">Optional</span><span class="sxs-lookup"><span data-stu-id="c60d8-122">Optional</span></span>  <br/> |<span data-ttu-id="c60d8-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c60d8-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c60d8-124">Vorhandene Datei %SystemDrive%\ProgramData\CloudConnector ohne Benachrichtigung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c60d8-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c60d8-125">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="c60d8-125">Input Types</span></span>
<span data-ttu-id="c60d8-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c60d8-126"></span></span>

<span data-ttu-id="c60d8-127">Keine.</span><span class="sxs-lookup"><span data-stu-id="c60d8-127">None.</span></span> <span data-ttu-id="c60d8-128">Das Cmdlet Import-CcConfiguration akzeptiert keine weitergeleitete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="c60d8-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c60d8-129">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="c60d8-129">Return Types</span></span>
<span data-ttu-id="c60d8-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c60d8-130"></span></span>

<span data-ttu-id="c60d8-131">Keine.</span><span class="sxs-lookup"><span data-stu-id="c60d8-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c60d8-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c60d8-132">See also</span></span>
<span data-ttu-id="c60d8-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c60d8-133"></span></span>

<span data-ttu-id="c60d8-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c60d8-134">Export-CcConfiguration</span></span>
  


---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Gibt die Version der Cloud Connector-Appliance zurück. "Get-CCVersion" kann nur auf dem Hostcomputer von Cloud Connector verwendet werden.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287251"
---
# <a name="get-ccversion"></a><span data-ttu-id="d2e8a-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="d2e8a-104">Get-CcVersion</span></span>
 
<span data-ttu-id="d2e8a-105">Gibt die Version der Cloud Connector-Appliance zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="d2e8a-106">"Get-CCVersion" kann nur auf dem Hostcomputer von Cloud Connector verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="d2e8a-107">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2e8a-107">Detailed Description</span></span>

<span data-ttu-id="d2e8a-108">Gibt die Version der Cloud Connector-Appliance basierend auf installierten PowerShell-Skripts, Dateien im Appliance-Verzeichnis und die auf dem Hostserver bereitgestellten virtuellen Computer zurück.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d2e8a-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2e8a-109">Parameters</span></span>

|<span data-ttu-id="d2e8a-110">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="d2e8a-110">**Parameter**</span></span>|<span data-ttu-id="d2e8a-111">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="d2e8a-111">**Required**</span></span>|<span data-ttu-id="d2e8a-112">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d2e8a-112">**Type**</span></span>|<span data-ttu-id="d2e8a-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d2e8a-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d2e8a-114">Versiontype</span><span class="sxs-lookup"><span data-stu-id="d2e8a-114">VersionType</span></span>  <br/> |<span data-ttu-id="d2e8a-115">Optional</span><span class="sxs-lookup"><span data-stu-id="d2e8a-115">Optional</span></span>  <br/> |<span data-ttu-id="d2e8a-116">System.String</span><span class="sxs-lookup"><span data-stu-id="d2e8a-116">System.String</span></span>  <br/> |<span data-ttu-id="d2e8a-117">Der Typ der Version.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-117">Type of version.</span></span> <span data-ttu-id="d2e8a-118">Der Wert des Parameters kann RunningScripts, RunningBits, BackupBits oder alle sein.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="d2e8a-119">Der Standardwert ist RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="d2e8a-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d2e8a-120">Examples</span></span>
<span data-ttu-id="d2e8a-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d2e8a-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="d2e8a-122">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="d2e8a-122">Example 1</span></span>

<span data-ttu-id="d2e8a-123">Das folgende Beispiel zeigt die Cloud Connector-Version des aktuell ausgeführten Skripts in Ihrer geöffneten PowerShell-Konsole:</span><span class="sxs-lookup"><span data-stu-id="d2e8a-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="d2e8a-124">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="d2e8a-124">Example 2</span></span>

<span data-ttu-id="d2e8a-125">Das folgende Beispiel zeigt die Cloud Connector-Version der aktuell ausgeführten Binärdateien, die auf den virtuellen Computern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="d2e8a-126">Sie können die Version in den Namen der ausgeführten virtuellen Computer in Hyper-v-Manager anzeigen:</span><span class="sxs-lookup"><span data-stu-id="d2e8a-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="d2e8a-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="d2e8a-127">Input Types</span></span>
<span data-ttu-id="d2e8a-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d2e8a-128"></span></span>

<span data-ttu-id="d2e8a-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-129">None.</span></span> <span data-ttu-id="d2e8a-130">Das Cmdlet "Get-CcVersion" akzeptiert keine Pipeline-Eingabe.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d2e8a-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="d2e8a-131">Return Types</span></span>
<span data-ttu-id="d2e8a-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d2e8a-132"></span></span>

<span data-ttu-id="d2e8a-133">Keine.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2e8a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2e8a-134">See also</span></span>
<span data-ttu-id="d2e8a-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d2e8a-135"></span></span>

<span data-ttu-id="d2e8a-136">Keine.</span><span class="sxs-lookup"><span data-stu-id="d2e8a-136">None.</span></span>
  


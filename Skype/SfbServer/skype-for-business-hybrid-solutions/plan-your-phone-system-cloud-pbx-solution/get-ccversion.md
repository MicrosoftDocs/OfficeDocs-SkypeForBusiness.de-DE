---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Gibt die Version der Cloud Connector Appliance zurück. Get-CCVersion kann nur auf dem Hostcomputer der Cloud-Verbindung verwendet werden.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233757"
---
# <a name="get-ccversion"></a><span data-ttu-id="bfebd-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="bfebd-104">Get-CcVersion</span></span>
 
<span data-ttu-id="bfebd-105">Gibt die Version der Cloud Connector Appliance zurück.</span><span class="sxs-lookup"><span data-stu-id="bfebd-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="bfebd-106">Get-CCVersion kann nur auf dem Hostcomputer der Cloud-Verbindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bfebd-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="bfebd-107">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfebd-107">Detailed Description</span></span>

<span data-ttu-id="bfebd-108">Gibt die Version der Cloud Connector Appliance basierend auf PowerShell-Skripts installiert, Dateien im Verzeichnis Appliance und die virtuellen Computer auf Hostserver bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bfebd-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bfebd-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="bfebd-109">Parameters</span></span>

|<span data-ttu-id="bfebd-110">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="bfebd-110">**Parameter**</span></span>|<span data-ttu-id="bfebd-111">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="bfebd-111">**Required**</span></span>|<span data-ttu-id="bfebd-112">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bfebd-112">**Type**</span></span>|<span data-ttu-id="bfebd-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bfebd-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bfebd-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="bfebd-114">VersionType</span></span>  <br/> |<span data-ttu-id="bfebd-115">Optional</span><span class="sxs-lookup"><span data-stu-id="bfebd-115">Optional</span></span>  <br/> |<span data-ttu-id="bfebd-116">System.String</span><span class="sxs-lookup"><span data-stu-id="bfebd-116">System.String</span></span>  <br/> |<span data-ttu-id="bfebd-117">Typ der Version.</span><span class="sxs-lookup"><span data-stu-id="bfebd-117">Type of version.</span></span> <span data-ttu-id="bfebd-118">Wert des Parameters kann RunningScripts, RunningBits, BackupBits oder alle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="bfebd-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="bfebd-119">Standardwert ist RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="bfebd-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="bfebd-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bfebd-120">Examples</span></span>
<span data-ttu-id="bfebd-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfebd-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="bfebd-122">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="bfebd-122">Example 1</span></span>

<span data-ttu-id="bfebd-123">Im folgende Beispiel zeigt die Cloud Connector Version des derzeit ausgeführten Skripts in der open-PowerShell-Konsole:</span><span class="sxs-lookup"><span data-stu-id="bfebd-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="bfebd-124">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="bfebd-124">Example 2</span></span>

<span data-ttu-id="bfebd-125">Das folgende Beispiel zeigt die Version Cloud Connector, der derzeit ausgeführten Binärdateien auf den virtuellen Computern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bfebd-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="bfebd-126">Sie können die Version in den Namen der ausgeführten virtuellen Computer im Hyper-V-Manager finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bfebd-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="bfebd-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="bfebd-127">Input Types</span></span>
<span data-ttu-id="bfebd-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfebd-128"></span></span>

<span data-ttu-id="bfebd-129">Keine.</span><span class="sxs-lookup"><span data-stu-id="bfebd-129">None.</span></span> <span data-ttu-id="bfebd-130">Das Cmdlet Get-CcVersion akzeptiert keine weitergeleitete Eingabe.</span><span class="sxs-lookup"><span data-stu-id="bfebd-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bfebd-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="bfebd-131">Return Types</span></span>
<span data-ttu-id="bfebd-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfebd-132"></span></span>

<span data-ttu-id="bfebd-133">Keine.</span><span class="sxs-lookup"><span data-stu-id="bfebd-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bfebd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfebd-134">See also</span></span>
<span data-ttu-id="bfebd-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfebd-135"></span></span>

<span data-ttu-id="bfebd-136">Keine.</span><span class="sxs-lookup"><span data-stu-id="bfebd-136">None.</span></span>
  


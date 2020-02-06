---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824149"
---
# <a name="switch-ccversion"></a><span data-ttu-id="35f96-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="35f96-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="35f96-104">Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance.</span><span class="sxs-lookup"><span data-stu-id="35f96-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="35f96-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="35f96-105">Examples</span></span>
<span data-ttu-id="35f96-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="35f96-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="35f96-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="35f96-107">Example 1</span></span>

<span data-ttu-id="35f96-108">Im folgenden Beispiel werden die Dienste der aktuell ausgeführten Appliance entladen und dann zu einer neu bereitgestellten oder Backup-Appliance gewechselt:</span><span class="sxs-lookup"><span data-stu-id="35f96-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="35f96-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="35f96-109">Example 2</span></span>

<span data-ttu-id="35f96-110">Im nächsten Beispiel werden die Dienste der aktuell ausgeführten Appliance entleert, und Dienste werden nicht mehr erzwungen, wenn das Entladen der Dienste fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="35f96-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="35f96-111">Der Befehl wechselt dann zu einer neu bereitgestellten oder Backup-Appliance:</span><span class="sxs-lookup"><span data-stu-id="35f96-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="35f96-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35f96-112">Detailed Description</span></span>
<span data-ttu-id="35f96-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="35f96-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="35f96-114">Das Cmdlet Switch-CcVersion entwässert die Cloud Connector-Dienste auf dem Vermittlungsserver und dem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="35f96-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="35f96-115">Alle laufenden Anrufe werden abgeschlossen, aber die Appliance lehnt alle neuen Anrufe ab.</span><span class="sxs-lookup"><span data-stu-id="35f96-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="35f96-116">Nach dem Entladen trennt das Cmdlet die ausgeführte Appliance vom Unternehmens-und Internet Netzwerk, deaktiviert alle virtuellen Computer, die zur Appliance gehören, und verbindet dann die Backup-Appliance mit den Unternehmens-und Internet Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="35f96-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="35f96-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="35f96-117">Parameters</span></span>
<span data-ttu-id="35f96-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="35f96-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="35f96-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="35f96-119">**Parameter**</span></span>|<span data-ttu-id="35f96-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="35f96-120">**Required**</span></span>|<span data-ttu-id="35f96-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="35f96-121">**Type**</span></span>|<span data-ttu-id="35f96-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="35f96-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="35f96-123">Force</span><span class="sxs-lookup"><span data-stu-id="35f96-123">Force</span></span> <br/> | <span data-ttu-id="35f96-124">Optional</span><span class="sxs-lookup"><span data-stu-id="35f96-124">Optional</span></span> <br/> |<span data-ttu-id="35f96-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="35f96-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="35f96-126">Beendet Dienste zwangsläufig, wenn das Entladen der Dienste fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="35f96-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="35f96-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="35f96-127">Input Types</span></span>
<span data-ttu-id="35f96-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="35f96-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="35f96-129">Keine</span><span class="sxs-lookup"><span data-stu-id="35f96-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="35f96-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="35f96-130">Return Types</span></span>
<span data-ttu-id="35f96-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="35f96-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="35f96-132">Keine </span><span class="sxs-lookup"><span data-stu-id="35f96-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35f96-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35f96-133">See also</span></span>
<span data-ttu-id="35f96-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="35f96-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="35f96-135">Keine</span><span class="sxs-lookup"><span data-stu-id="35f96-135">None</span></span>
  


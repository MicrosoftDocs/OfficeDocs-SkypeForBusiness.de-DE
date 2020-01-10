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
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance.
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003155"
---
# <a name="switch-ccversion"></a><span data-ttu-id="77471-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="77471-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="77471-104">Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance.</span><span class="sxs-lookup"><span data-stu-id="77471-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="77471-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="77471-105">Examples</span></span>
<span data-ttu-id="77471-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="77471-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="77471-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="77471-107">Example 1</span></span>

<span data-ttu-id="77471-108">Im folgenden Beispiel werden die Dienste der aktuell ausgeführten Appliance entladen und dann zu einer neu bereitgestellten oder Backup-Appliance gewechselt:</span><span class="sxs-lookup"><span data-stu-id="77471-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="77471-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="77471-109">Example 2</span></span>

<span data-ttu-id="77471-110">Im nächsten Beispiel werden die Dienste der aktuell ausgeführten Appliance entleert, und Dienste werden nicht mehr erzwungen, wenn das Entladen der Dienste fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="77471-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="77471-111">Der Befehl wechselt dann zu einer neu bereitgestellten oder Backup-Appliance:</span><span class="sxs-lookup"><span data-stu-id="77471-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="77471-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77471-112">Detailed Description</span></span>
<span data-ttu-id="77471-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="77471-113"></span></span>

<span data-ttu-id="77471-114">Das Cmdlet Switch-CcVersion entwässert die Cloud Connector-Dienste auf dem Vermittlungsserver und dem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="77471-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="77471-115">Alle laufenden Anrufe werden abgeschlossen, aber die Appliance lehnt alle neuen Anrufe ab.</span><span class="sxs-lookup"><span data-stu-id="77471-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="77471-116">Nach dem Entladen trennt das Cmdlet die ausgeführte Appliance vom Unternehmens-und Internet Netzwerk, deaktiviert alle virtuellen Computer, die zur Appliance gehören, und verbindet dann die Backup-Appliance mit den Unternehmens-und Internet Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="77471-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="77471-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="77471-117">Parameters</span></span>
<span data-ttu-id="77471-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="77471-118"></span></span>

|<span data-ttu-id="77471-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="77471-119">**Parameter**</span></span>|<span data-ttu-id="77471-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="77471-120">**Required**</span></span>|<span data-ttu-id="77471-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="77471-121">**Type**</span></span>|<span data-ttu-id="77471-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="77471-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="77471-123">Force</span><span class="sxs-lookup"><span data-stu-id="77471-123">Force</span></span> <br/> | <span data-ttu-id="77471-124">Optional</span><span class="sxs-lookup"><span data-stu-id="77471-124">Optional</span></span> <br/> |<span data-ttu-id="77471-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="77471-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="77471-126">Beendet Dienste zwangsläufig, wenn das Entladen der Dienste fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="77471-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="77471-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="77471-127">Input Types</span></span>
<span data-ttu-id="77471-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="77471-128"></span></span>

<span data-ttu-id="77471-129">Keine</span><span class="sxs-lookup"><span data-stu-id="77471-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="77471-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="77471-130">Return Types</span></span>
<span data-ttu-id="77471-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="77471-131"></span></span>

<span data-ttu-id="77471-132">Keine </span><span class="sxs-lookup"><span data-stu-id="77471-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77471-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77471-133">See also</span></span>
<span data-ttu-id="77471-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="77471-134"></span></span>

<span data-ttu-id="77471-135">Keine</span><span class="sxs-lookup"><span data-stu-id="77471-135">None</span></span>
  


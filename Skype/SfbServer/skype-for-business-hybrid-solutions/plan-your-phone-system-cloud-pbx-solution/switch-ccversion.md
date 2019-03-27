---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das Switch-CcVersion-Cmdlet trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten oder backup Einheit.
ms.openlocfilehash: 73ae9b4f93a2488dea29f3271565ac3d25759fd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872859"
---
# <a name="switch-ccversion"></a><span data-ttu-id="64b0c-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="64b0c-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="64b0c-104">Das Switch-CcVersion-Cmdlet trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten oder backup Einheit.</span><span class="sxs-lookup"><span data-stu-id="64b0c-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="64b0c-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="64b0c-105">Examples</span></span>
<span data-ttu-id="64b0c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="64b0c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="64b0c-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="64b0c-107">Example 1</span></span>

<span data-ttu-id="64b0c-108">Im folgenden Beispiel wird die Dienste der aktuellen ausgeführten Appliance verbraucht, und anschließend der Wechsel zu einer neu bereitgestellten oder backup Einheit:</span><span class="sxs-lookup"><span data-stu-id="64b0c-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="64b0c-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="64b0c-109">Example 2</span></span>

<span data-ttu-id="64b0c-110">Im nächsten Beispiel wird die Dienste der aktuellen ausgeführten Appliance verbraucht und zwangsweise Dienste beendet, wenn die Dienste ausgleichen ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="64b0c-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="64b0c-111">Der Befehl wechselt dann in einer neu bereitgestellten oder backup Einheit:</span><span class="sxs-lookup"><span data-stu-id="64b0c-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="64b0c-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64b0c-112">Detailed Description</span></span>
<span data-ttu-id="64b0c-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="64b0c-113"></span></span>

<span data-ttu-id="64b0c-114">Das Switch-CcVersion-Cmdlet verbraucht der Connector Cloud-Dienste auf dem Vermittlungsserver und Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="64b0c-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="64b0c-115">Alle ausgeführten Anrufe werden abgeschlossen, aber die Anwendung lehnt keine neuen Anrufe.</span><span class="sxs-lookup"><span data-stu-id="64b0c-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="64b0c-116">Nach dem ausgleichen, mit dem Cmdlet trennt die Verbindung der ausgeführten Appliance corporate und Internet-Netzwerke, alle virtuellen Computer, die an die Appliance gehören deaktiviert und verbindet Sie dann die Sicherung Appliance an das Unternehmen und das Internet.</span><span class="sxs-lookup"><span data-stu-id="64b0c-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="64b0c-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="64b0c-117">Parameters</span></span>
<span data-ttu-id="64b0c-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="64b0c-118"></span></span>

|<span data-ttu-id="64b0c-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="64b0c-119">**Parameter**</span></span>|<span data-ttu-id="64b0c-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="64b0c-120">**Required**</span></span>|<span data-ttu-id="64b0c-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="64b0c-121">**Type**</span></span>|<span data-ttu-id="64b0c-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="64b0c-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="64b0c-123">Force</span><span class="sxs-lookup"><span data-stu-id="64b0c-123">Force</span></span> <br/> | <span data-ttu-id="64b0c-124">Optional</span><span class="sxs-lookup"><span data-stu-id="64b0c-124">Optional</span></span> <br/> |<span data-ttu-id="64b0c-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="64b0c-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="64b0c-126">Beendet Dienste erzwingen, wenn die Dienste ausgleichen fällt aus.</span><span class="sxs-lookup"><span data-stu-id="64b0c-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="64b0c-127">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="64b0c-127">Input Types</span></span>
<span data-ttu-id="64b0c-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64b0c-128"></span></span>

<span data-ttu-id="64b0c-129">Keine </span><span class="sxs-lookup"><span data-stu-id="64b0c-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="64b0c-130">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="64b0c-130">Return Types</span></span>
<span data-ttu-id="64b0c-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64b0c-131"></span></span>

<span data-ttu-id="64b0c-132">Keine </span><span class="sxs-lookup"><span data-stu-id="64b0c-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64b0c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64b0c-133">See also</span></span>
<span data-ttu-id="64b0c-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64b0c-134"></span></span>

<span data-ttu-id="64b0c-135">Keine</span><span class="sxs-lookup"><span data-stu-id="64b0c-135">None</span></span>
  


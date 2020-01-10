---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'Das Cmdlet „Publish-CcAppliance“ ruft Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration ab und veröffentlicht sie in der Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. '
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003085"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="c23d6-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c23d6-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="c23d6-104">Das Cmdlet „Publish-CcAppliance“ ruft Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration ab und veröffentlicht sie in der Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="c23d6-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="c23d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c23d6-105">Parameters</span></span>

<span data-ttu-id="c23d6-106">Keine</span><span class="sxs-lookup"><span data-stu-id="c23d6-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c23d6-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c23d6-107">Examples</span></span>
<span data-ttu-id="c23d6-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c23d6-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="c23d6-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="c23d6-109">Example 1</span></span>

<span data-ttu-id="c23d6-110">Im folgenden Beispiel werden Informationen zu einer höheren Verfügbarkeit aus der Konfiguration des Online Mandanten abgerufen und in der Cloud Connector-Appliance auf dem Hostserver veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="c23d6-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="c23d6-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c23d6-111">Detailed Description</span></span>
<span data-ttu-id="c23d6-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c23d6-112"></span></span>

<span data-ttu-id="c23d6-p101">Die Informationen zur hohen Verfügbarkeit enthalten die Vermittlungsserver-FQDNs und die IP-Adressen des PSTN-Standorts. Neue DNS-A-Einträge werden zum AD-Server für IP-Adressen für Vermittlungsserver hinzugefügt. Neue Topologieelemente werden im zentralen Verwaltungsspeicher für die Vermittlungsserver-FQDNs und IP-Adressen aktualisiert. </span><span class="sxs-lookup"><span data-stu-id="c23d6-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="c23d6-116">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="c23d6-116">Input Types</span></span>
<span data-ttu-id="c23d6-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c23d6-117"></span></span>

<span data-ttu-id="c23d6-118">Keine.</span><span class="sxs-lookup"><span data-stu-id="c23d6-118">None.</span></span> <span data-ttu-id="c23d6-119">Das Cmdlet „Publish-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="c23d6-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c23d6-120">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="c23d6-120">Return Types</span></span>
<span data-ttu-id="c23d6-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c23d6-121"></span></span>

<span data-ttu-id="c23d6-122">Keine </span><span class="sxs-lookup"><span data-stu-id="c23d6-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c23d6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c23d6-123">See also</span></span>
<span data-ttu-id="c23d6-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c23d6-124"></span></span>

[<span data-ttu-id="c23d6-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c23d6-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="c23d6-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c23d6-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="c23d6-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c23d6-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="c23d6-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="c23d6-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  


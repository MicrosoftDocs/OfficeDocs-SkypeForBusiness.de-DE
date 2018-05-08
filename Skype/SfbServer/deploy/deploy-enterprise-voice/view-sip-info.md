---
title: Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von Informationen zu SIP-Trunks in Skype für Business Server 2015.'
ms.openlocfilehash: 9a27c5c78f15fbdc64aa52cf842697ab0b002252
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="03d2a-103">Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="03d2a-103">View information about individual SIP trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03d2a-104">**Zusammenfassung:** Informationen Sie zum Anzeigen von Informationen zu SIP-Trunks in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03d2a-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03d2a-105">SIP-Trunks dienen zum Skype für Business Server Voice over IP-Telefon Netzwerk mit im Public Switched Telephone Network, (PSTN) eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="03d2a-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="03d2a-106">In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt.</span><span class="sxs-lookup"><span data-stu-id="03d2a-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="03d2a-107">Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch.</span><span class="sxs-lookup"><span data-stu-id="03d2a-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="03d2a-108">Für Administratoren bedeutete dies, dass sie sich Informationen zu einem einzelnen SIP-Trunk anzeigen lassen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufriefen.</span><span class="sxs-lookup"><span data-stu-id="03d2a-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="03d2a-109">In Skype für Business Server können jedoch mehrere Trunks jetzt ein einzelnes PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht länger ein und dieselbe sind.</span><span class="sxs-lookup"><span data-stu-id="03d2a-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="03d2a-110">Wiederum bedeutet dies, dass das neue [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) -Cmdlet, um das Anzeigen von Informationen zu einer einzelnen SIP-Trunk Administratoren verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="03d2a-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="03d2a-111">Anzeigen von Informationen für alle SIP-Trunks</span><span class="sxs-lookup"><span data-stu-id="03d2a-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="03d2a-112">Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:</span><span class="sxs-lookup"><span data-stu-id="03d2a-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="03d2a-113">Anzeigen von Informationen für einen bestimmten SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="03d2a-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="03d2a-114">Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="03d2a-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="03d2a-115">Informationen für alle einem Pool zugeordneten SIP-Trunks anzeigen</span><span class="sxs-lookup"><span data-stu-id="03d2a-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="03d2a-116">In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="03d2a-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```



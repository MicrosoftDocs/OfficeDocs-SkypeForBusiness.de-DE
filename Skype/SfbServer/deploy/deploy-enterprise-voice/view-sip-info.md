---
title: Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von Informationen zu SIP-Trunks in Skype für Business Server.'
ms.openlocfilehash: 10f45def1727c083f89afcdba43fb9c1c4e7e45e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968698"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="57a1b-103">Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="57a1b-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="57a1b-104">**Zusammenfassung:** Informationen Sie zum Anzeigen von Informationen zu SIP-Trunks in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="57a1b-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="57a1b-105">SIP-Trunks dienen zum Skype für Business Server Voice over IP-Telefon Netzwerk mit im Public Switched Telephone Network, (PSTN) eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="57a1b-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="57a1b-106">In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt.</span><span class="sxs-lookup"><span data-stu-id="57a1b-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="57a1b-107">Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch.</span><span class="sxs-lookup"><span data-stu-id="57a1b-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="57a1b-108">Für Administratoren bedeutete dies, dass sie sich Informationen zu einem einzelnen SIP-Trunk anzeigen lassen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufriefen.</span><span class="sxs-lookup"><span data-stu-id="57a1b-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="57a1b-109">In Skype für Business Server können jedoch mehrere Trunks jetzt ein einzelnes PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht länger ein und dieselbe sind.</span><span class="sxs-lookup"><span data-stu-id="57a1b-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="57a1b-110">Wiederum bedeutet dies, dass das neue [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) -Cmdlet, um das Anzeigen von Informationen zu einer einzelnen SIP-Trunk Administratoren verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="57a1b-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="57a1b-111">Anzeigen von Informationen für alle SIP-Trunks</span><span class="sxs-lookup"><span data-stu-id="57a1b-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="57a1b-112">Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:</span><span class="sxs-lookup"><span data-stu-id="57a1b-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="57a1b-113">Anzeigen von Informationen für einen bestimmten SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="57a1b-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="57a1b-114">Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="57a1b-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="57a1b-115">Informationen für alle einem Pool zugeordneten SIP-Trunks anzeigen</span><span class="sxs-lookup"><span data-stu-id="57a1b-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="57a1b-116">In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="57a1b-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
---
title: Anzeigen von Informationen zu einzelnen SIP-Stämmen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Informationen zu SIP-Stämmen in Skype for Business Server anzeigen können.'
ms.openlocfilehash: f67fe998408b9c99311f1a86c35e08200de99431
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766928"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="38454-103">Anzeigen von Informationen zu einzelnen SIP-Stämmen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38454-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="38454-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Informationen zu SIP-Stämmen in Skype for Business Server anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="38454-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="38454-105">SIP-Trunks werden verwendet, um das Skype for Business Server Voice-over-IP-Telefon Netzwerk mit dem öffentlich geschalteten Telefonnetz (PSTN) zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="38454-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="38454-106">In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt.</span><span class="sxs-lookup"><span data-stu-id="38454-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="38454-107">Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch.</span><span class="sxs-lookup"><span data-stu-id="38454-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="38454-108">Für Administratoren bedeutete dies, dass sie sich Informationen zu einem einzelnen SIP-Trunk anzeigen lassen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufriefen.</span><span class="sxs-lookup"><span data-stu-id="38454-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="38454-109">In Skype for Business Server können nun jedoch mehrere Trunks einem einzigen PSTN-Gateway zugewiesen werden. Das bedeutet, dass Gateways und Trunks nicht mehr identisch sind.</span><span class="sxs-lookup"><span data-stu-id="38454-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="38454-110">Das bedeutet wiederum, dass Administratoren das neue Cmdlet " [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) " verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="38454-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="38454-111">Anzeigen von Informationen für alle SIP-Trunks</span><span class="sxs-lookup"><span data-stu-id="38454-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="38454-112">Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:</span><span class="sxs-lookup"><span data-stu-id="38454-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="38454-113">Anzeigen von Informationen für einen bestimmten SIP-Trunk</span><span class="sxs-lookup"><span data-stu-id="38454-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="38454-114">Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="38454-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="38454-115">Informationen für alle einem Pool zugeordneten SIP-Trunks anzeigen</span><span class="sxs-lookup"><span data-stu-id="38454-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="38454-116">In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="38454-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```

---
title: Definieren eines neuen Trunks
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Definieren Sie einen neuen Session Initiation Protocol (SIP) Trunk, indem Sie die folgenden Informationen bereitstellen:'
ms.openlocfilehash: 9b237903239786737e194755ec69025a5f6a0478
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21059042"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="2f0f2-103">Definieren eines neuen Trunks</span><span class="sxs-lookup"><span data-stu-id="2f0f2-103">Define a New Trunk</span></span>
 
<span data-ttu-id="2f0f2-104">Definieren Sie einen neuen Session Initiation Protocol (SIP) Trunk, indem Sie die folgenden Informationen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="2f0f2-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>
  
- <span data-ttu-id="2f0f2-105">**Trunkname**: eindeutiger Name in der Topologie, die diesem Trunk identifiziert werden können</span><span class="sxs-lookup"><span data-stu-id="2f0f2-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>
    
- <span data-ttu-id="2f0f2-106">**Zugeordnete PSTN-Gateway**: Wählen Sie ein PSTN-Gateway bereitgestellt und konfiguriert in Ihrer Bereitstellung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2f0f2-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>
    
- <span data-ttu-id="2f0f2-107">**Überwachungsport für IP/PSTN-Gateway**: Port, der die IP-Nebenstellenanlage oder PSTN-Gateways überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="2f0f2-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="2f0f2-108">Muss eindeutig aus allen anderen Trunk Überwachungsports in Ihrer Bereitstellung konfiguriert sein</span><span class="sxs-lookup"><span data-stu-id="2f0f2-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>
    
- <span data-ttu-id="2f0f2-109">**SIP-Transportprotokoll**: Wählen Sie aus der Liste entweder TCP oder TLS</span><span class="sxs-lookup"><span data-stu-id="2f0f2-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>
    
- <span data-ttu-id="2f0f2-110">**Zugeordneter Vermittlungsserver**: Wählen Sie aus der Liste einen Vermittlungsserver, die bereitgestellt und in der Bereitstellung konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="2f0f2-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>
    
- <span data-ttu-id="2f0f2-111">**Zugeordneter Vermittlungsserver Port**: Legen Sie den Wert für Port auf den TCP oder TLS-Portwert des Vermittlungsservers, die diesem SIP-Trunk verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="2f0f2-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="2f0f2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f0f2-112">See also</span></span>

[<span data-ttu-id="2f0f2-113">M: n-Trunk in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="2f0f2-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="2f0f2-114">Implementierung von SIP-Trunking</span><span class="sxs-lookup"><span data-stu-id="2f0f2-114">How do I implement SIP trunking?</span></span>](http://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
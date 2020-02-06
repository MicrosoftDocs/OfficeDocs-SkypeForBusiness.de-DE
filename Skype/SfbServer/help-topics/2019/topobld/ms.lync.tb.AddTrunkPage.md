---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie definieren einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen bereitstellen:'
ms.openlocfilehash: 17f6b72f1234813e717cfc72be60bb5f0352134a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794314"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="419f7-103">Definieren eines neuen Trunks</span><span class="sxs-lookup"><span data-stu-id="419f7-103">Define a New Trunk</span></span>

<span data-ttu-id="419f7-104">Sie definieren einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="419f7-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="419f7-105">**Trunk Name**: eindeutiger Name in Ihrer Topologie, mit dem dieser trunk identifiziert wird</span><span class="sxs-lookup"><span data-stu-id="419f7-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="419f7-106">**Zugeordnetes PSTN-Gateway**: Wählen Sie ein bereitgestelltes und konfiguriertes PSTN-Gateway in Ihrer Bereitstellung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="419f7-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="419f7-107">**Abhör-Port für das IP/PSTN-Gateway**: Port, den das IP-PBX-oder PSTN-Gateway anhört.</span><span class="sxs-lookup"><span data-stu-id="419f7-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="419f7-108">Muss für alle anderen trunk-Abhör Anschlüsse eindeutig sein, die in Ihrer Bereitstellung konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="419f7-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="419f7-109">**SIP-Transport Protokoll**: Wählen Sie in der Liste entweder TCP oder TLS aus.</span><span class="sxs-lookup"><span data-stu-id="419f7-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="419f7-110">**Zugeordneter Vermittlungsserver**: Wählen Sie in der Liste einen Vermittlungsserver aus, der in Ihrer Bereitstellung bereitgestellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="419f7-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="419f7-111">**Zugeordneter Vermittlungsserver-Port**: setzen Sie den Portwert gleich dem TCP-oder TLS-Portwert des Vermittlungsservers, den dieser SIP-Trunk verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="419f7-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="419f7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="419f7-112">See also</span></span>

[<span data-ttu-id="419f7-113">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="419f7-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="419f7-114">Wie kann ich SIP-Trunking implementieren?</span><span class="sxs-lookup"><span data-stu-id="419f7-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)

---
title: Definieren eines neuen Trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Definieren Sie einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen angeben:'
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218556"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="0470f-103">Definieren eines neuen Trunks</span><span class="sxs-lookup"><span data-stu-id="0470f-103">Define a New Trunk</span></span>

<span data-ttu-id="0470f-104">Definieren Sie einen neuen SIP-Trunk (Session Initiation Protocol), indem Sie die folgenden Informationen angeben:</span><span class="sxs-lookup"><span data-stu-id="0470f-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="0470f-105">**Trunkname**: Eindeutiger Name in der Topologie, mit dem der Trunk identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0470f-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="0470f-106">**Zugeordnetes PSTN-Gateway**: Wählen Sie in der Liste ein PSTN-Gateway aus, das in der Bereitstellung vorhanden und konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0470f-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="0470f-p101">**Überwachungsport für IP/PSTN-Gateway**: Port, der von der Festnetztelefonanlage oder vom PSTN-Gateway überwacht wird. Der Port muss gegenüber allen anderen Trunküberwachungsports, die in der Bereitstellung definiert sind, eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0470f-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="0470f-109">**SIP-Transportprotokoll**: Wählen Sie in der Liste entweder TCP oder TLS aus.</span><span class="sxs-lookup"><span data-stu-id="0470f-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="0470f-110">**Zugeordnete Vermittlungsserver**: Wählen Sie in der Liste eine Vermittlungsserver aus, die in Ihrer Bereitstellung bereitgestellt und konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0470f-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="0470f-111">**Zugeordneter Vermittlungsserver Port**: Legen Sie den Portwert auf den TCP-oder TLS-Portwert der Vermittlungsserver fest, die dieser SIP-Trunk verwendet.</span><span class="sxs-lookup"><span data-stu-id="0470f-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="0470f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0470f-112">See also</span></span>

[<span data-ttu-id="0470f-113">M:n-trunk trunk in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0470f-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="0470f-114">Wie kann ich das SIP-Trunking implementieren?</span><span class="sxs-lookup"><span data-stu-id="0470f-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)

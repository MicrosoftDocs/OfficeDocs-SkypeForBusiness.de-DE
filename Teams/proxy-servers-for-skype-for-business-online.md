---
title: Proxyserver für Skype for Business Online und Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers mit Teams oder Skype für Unternehmen.
ms.openlocfilehash: a09a1bf53fe4d1a38742856c051a80e5928f36ef
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640898"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="b33a9-103">Proxyserver für Skype for Business Online und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b33a9-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="b33a9-104">Dieser Artikel enthält Hinweise zur Verwendung eines Proxyservers mit Teams oder Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="b33a9-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="b33a9-105">Es wird empfohlen, keinen Proxyserver zu verwenden</span><span class="sxs-lookup"><span data-stu-id="b33a9-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="b33a9-106">Wenn es um Teams oder Skype für Business-Datenverkehr über Proxys geht, empfiehlt es sich Proxys umgangen.</span><span class="sxs-lookup"><span data-stu-id="b33a9-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="b33a9-107">Proxys machen nicht Teams oder Skype für Unternehmen sicherer, da der Datenverkehr bereits verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="b33a9-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="b33a9-108">Außerdem kann die Verwendung eines Proxys Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="b33a9-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="b33a9-109">Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen.</span><span class="sxs-lookup"><span data-stu-id="b33a9-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="b33a9-110">Probleme wie diese führt eine negative Erfahrung in solche Teams oder Skype für Geschäftsszenarien als audio und video, wobei in Echtzeit Datenströme wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="b33a9-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="b33a9-111">Wenn Sie einen Proxyserver verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="b33a9-111">If you need to use a proxy server</span></span>

<span data-ttu-id="b33a9-112">Einige Organisationen haben keine Möglichkeit, einen Proxy für Teams oder Skype für Business-Datenverkehr zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="b33a9-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="b33a9-113">Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="b33a9-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="b33a9-114">Microsoft empfiehlt außerdem dringend Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b33a9-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="b33a9-115">Verwenden Sie externe DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="b33a9-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="b33a9-116">Verwenden Sie direktes UDP-basiertes Routing.</span><span class="sxs-lookup"><span data-stu-id="b33a9-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="b33a9-117">Lassen Sie UDP-Datenverkehr zu.</span><span class="sxs-lookup"><span data-stu-id="b33a9-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="b33a9-118">Folgen die anderen Empfehlungen in unsere Netzwerken Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="b33a9-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="b33a9-119">Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b33a9-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="b33a9-120">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b33a9-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="b33a9-121">Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.</span><span class="sxs-lookup"><span data-stu-id="b33a9-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b33a9-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b33a9-122">Related topics</span></span>

[<span data-ttu-id="b33a9-123">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b33a9-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 
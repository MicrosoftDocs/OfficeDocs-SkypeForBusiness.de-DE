---
title: Proxyserver für Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht.
ms.openlocfilehash: fcae4ec366845818d515a4d78c79ea77d038a4a5
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211022"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="6886d-103">Proxyserver für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6886d-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="6886d-104">Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht.</span><span class="sxs-lookup"><span data-stu-id="6886d-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="6886d-105">Es wird empfohlen, keinen Proxyserver zu verwenden</span><span class="sxs-lookup"><span data-stu-id="6886d-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="6886d-p101">In Bezug auf Skype for Business-Datenverkehr über Proxys empfiehlt Microsoft, Proxys zu umgehen. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer.</span><span class="sxs-lookup"><span data-stu-id="6886d-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="6886d-p102">Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Solche Probleme führen zur Beeinträchtigung der Benutzerfreundlichkeit in Skype for Business-Szenarien mit Audio und Video, in denen Echtzeitstreams unerlässlich sind.</span><span class="sxs-lookup"><span data-stu-id="6886d-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="6886d-111">Wenn Sie einen Proxyserver verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="6886d-111">If you need to use a proxy server</span></span>

<span data-ttu-id="6886d-p103">In manchen Organisationen ist die Umgehung eines Proxys für Skype for Business-Datenverkehr nicht möglich. Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="6886d-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="6886d-114">Microsoft empfiehlt außerdem dringend Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6886d-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="6886d-115">Verwenden Sie externe DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="6886d-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="6886d-116">Verwenden Sie direktes UDP-basiertes Routing.</span><span class="sxs-lookup"><span data-stu-id="6886d-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="6886d-117">Lassen Sie UDP-Datenverkehr zu.</span><span class="sxs-lookup"><span data-stu-id="6886d-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="6886d-118">Folgen Sie den anderen Empfehlungen in unseren Netzwerkrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="6886d-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="6886d-119">Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6886d-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="6886d-120">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6886d-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="6886d-121">Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.</span><span class="sxs-lookup"><span data-stu-id="6886d-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6886d-122">See Also</span><span class="sxs-lookup"><span data-stu-id="6886d-122">Related topics</span></span>

[<span data-ttu-id="6886d-123">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6886d-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 
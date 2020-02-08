---
title: Proxy Server für Teams oder Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Dieser Artikel enthält Informationen zur Verwendung eines Proxyservers mit Teams oder Skype for Business.
ms.openlocfilehash: ca81c32064406af0e5bc3d614566a96ec5646a91
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863186"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="41369-103">Proxy Server für Teams oder Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="41369-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="41369-104">Dieser Artikel enthält Anleitungen zur Verwendung eines Proxyservers mit Teams oder Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="41369-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="41369-105">Es wird empfohlen, keinen Proxyserver zu verwenden</span><span class="sxs-lookup"><span data-stu-id="41369-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="41369-p101">Wenn es um Teams oder Skype for Business-Datenverkehr über Proxies geht, empfiehlt Microsoft, Proxys zu umgehen. Proxys machen Teams oder Skype for Business nicht sicherer, da der Datenverkehr bereits verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="41369-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="41369-p102">Und ein Proxy kann Probleme verursachen. Leistungsbezogene Probleme können durch Latenz und Paketverlust in die Umgebung eingeführt werden. Probleme wie diese führen zu einer negativen Erfahrung in solchen Teams oder Skype for Business-Szenarien als Audio-und Videodaten, bei denen echt Zeitströme wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="41369-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="41369-111">Wenn Sie einen Proxyserver verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="41369-111">If you need to use a proxy server</span></span>

<span data-ttu-id="41369-p103">Einige Organisationen haben keine Möglichkeit, einen Proxy für Teams oder Skype for Business-Datenverkehr zu umgehen. Wenn dies für Sie der Fall ist, müssen die oben genannten Probleme berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="41369-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="41369-114">Microsoft empfiehlt außerdem dringend Folgendes:</span><span class="sxs-lookup"><span data-stu-id="41369-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="41369-115">Verwenden Sie externe DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="41369-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="41369-116">Verwenden Sie direktes UDP-basiertes Routing.</span><span class="sxs-lookup"><span data-stu-id="41369-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="41369-117">Lassen Sie UDP-Datenverkehr zu.</span><span class="sxs-lookup"><span data-stu-id="41369-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="41369-118">Befolgen Sie die anderen Empfehlungen in unseren Netzwerkrichtlinien: [Vorbereiten des Netzwerks Ihrer Organisation für Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="41369-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="41369-119">Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.</span><span class="sxs-lookup"><span data-stu-id="41369-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="41369-120">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="41369-120">Related topics</span></span>

[<span data-ttu-id="41369-121">Office 365-Netzwerk Verbindungs Prinzipien</span><span class="sxs-lookup"><span data-stu-id="41369-121">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="41369-122">Vorbereiten des Netzwerks Ihrer Organisation für Teams</span><span class="sxs-lookup"><span data-stu-id="41369-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)

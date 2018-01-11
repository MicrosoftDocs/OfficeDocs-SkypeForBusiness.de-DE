---
title: "Proxyserver für Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht."
ms.openlocfilehash: 325e48c7bfaeffca7c34915e176772f0824903f6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="6c4f8-103">Proxyserver für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6c4f8-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="6c4f8-104">Dieser Artikel ist als Leitfaden für die Verwendung eines Proxyservers in Verbindung mit Skype for Business gedacht.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="6c4f8-105">Es wird empfohlen, keinen Proxyserver zu verwenden</span><span class="sxs-lookup"><span data-stu-id="6c4f8-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="6c4f8-p101">In Bezug auf Skype for Business-Datenverkehr über Proxys empfiehlt Microsoft, Proxys zu umgehen. Da der Datenverkehr bereits verschlüsselt ist, wird Skype for Business durch Proxys nicht sicherer.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="6c4f8-p102">Außerdem kann die Verwendung eines Proxys Probleme verursachen. Durch Latenz und Paketverluste kann es in der Umgebung zu Leistungsproblemen kommen. Solche Probleme führen zur Beeinträchtigung der Benutzerfreundlichkeit in Skype for Business-Szenarien mit Audio und Video, in denen Echtzeitstreams unerlässlich sind.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="6c4f8-111">Wenn Sie einen Proxyserver verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="6c4f8-111">If you need to use a proxy server</span></span>

<span data-ttu-id="6c4f8-p103">In manchen Organisationen ist die Umgehung eines Proxys für Skype for Business-Datenverkehr nicht möglich. Wenn dies bei Ihnen der Fall ist, müssen Sie die oben genannten Probleme berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="6c4f8-114">Microsoft empfiehlt außerdem dringend Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6c4f8-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="6c4f8-115">Verwenden Sie externe DNS-Auflösung.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="6c4f8-116">Verwenden Sie direktes UDP-basiertes Routing.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="6c4f8-117">Lassen Sie UDP-Datenverkehr zu.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="6c4f8-118">Folgen Sie den anderen Empfehlungen in unseren Netzwerkrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="6c4f8-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="6c4f8-119">Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6c4f8-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="6c4f8-120">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6c4f8-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="6c4f8-121">Wenn Sie sich an diesem Leitfaden orientieren, können Sie potenzielle Probleme auf ein Minimum reduzieren.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="6c4f8-122">Proxyanbieter mit integrierter Skype for Business-Unterstützung oder entsprechenden Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="6c4f8-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="6c4f8-123">Dieser Abschnitt enthält Informationen zu Proxyanbietern, die Produkte oder Dienste bereitstellen, die nachweislich erfolgreich für Skype for Business-Datenverkehr verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="6c4f8-124">Für Organisationen, die **Bluecoat-Proxylösungen** verwenden, wurde eine neue Firmware veröffentlicht, die verschiedene Probleme im Zusammenhang mit folgenden Aspekten behebt:</span><span class="sxs-lookup"><span data-stu-id="6c4f8-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="6c4f8-125">Abfangen von Daten über SSL</span><span class="sxs-lookup"><span data-stu-id="6c4f8-125">SSL interception</span></span>
    
  - <span data-ttu-id="6c4f8-126">OCSP-/SRL-Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="6c4f8-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="6c4f8-127">SIP über TLS</span><span class="sxs-lookup"><span data-stu-id="6c4f8-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="6c4f8-128">Unterstützung für TURN</span><span class="sxs-lookup"><span data-stu-id="6c4f8-128">support for TURN</span></span>
    
<span data-ttu-id="6c4f8-p104">Die systemeigene Unterstützung von Bluecoat für Skype for Business kann leicht aktiviert werden, sodass relevanter Datenverkehr identifiziert und entsprechend verwaltet werden kann. Dies gewährleistet optimale Authentifizierung und Signalisierung sowie einen optimalen Fluss des Mediendatenverkehrs, damit Sie hohe Benutzerfreundlichkeit ohne Sicherheitsbedenken bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="6c4f8-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="6c4f8-131">Entnehmen Sie den folgenden Link Bluecoat Proxy eines Teils der Topologie des Netzwerks ist: https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="6c4f8-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c4f8-132">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6c4f8-132">Related topics</span></span>

[<span data-ttu-id="6c4f8-133">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6c4f8-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
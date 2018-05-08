---
title: Legen Sie den Umfang der E9-1-1-Bereitstellung in Skype for Business Server 2015 fest
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Entscheidungen zur Planung einer E9-1-1-bereitstellungs in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 4836f6b91404d0c2df2eeb4b3e1deaa63f5fe094
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="1cdcd-103">Legen Sie den Umfang der E9-1-1-Bereitstellung in Skype for Business Server 2015 fest</span><span class="sxs-lookup"><span data-stu-id="1cdcd-103">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1cdcd-104">Entscheidungen zur Planung einer E9-1-1-bereitstellungs in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="1cdcd-105">Bevor Sie Skype für Unternehmen für E9-1-1 konfigurieren, müssen Sie die E9-1-1-Bereitstellung zu planen.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="1cdcd-106">Stellen Sie sich die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="1cdcd-106">Some of the questions to consider include:</span></span>
  
 <span data-ttu-id="1cdcd-107">**Was sind Richtlinien und Vorschriften in Bezug auf E9-1-1 Ihrer Organisation?**</span><span class="sxs-lookup"><span data-stu-id="1cdcd-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>
  
 <span data-ttu-id="1cdcd-108">Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als „Telefonsysteme mit mehreren Leitungen“ oder „Mehrleitungstelefonsysteme“ bezeichnet) unterscheiden sich von Staat zu Staat.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="1cdcd-109">Sie sollten wenden Sie sich mit Ihrem Team rechtlichen, die Verpflichtungen zu verstehen, die für die Bereitstellung von Skype für Unternehmen in die entsprechenden Regionen gelten.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>
    
 <span data-ttu-id="1cdcd-110">**Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**</span><span class="sxs-lookup"><span data-stu-id="1cdcd-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>
  
 <span data-ttu-id="1cdcd-p103">Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten und Standorte außerhalb der USA können ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span> 
    
 <span data-ttu-id="1cdcd-113">**Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="1cdcd-113">**How will you deploy E9-1-1 to branch sites?**</span></span>
  
 <span data-ttu-id="1cdcd-114">Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="1cdcd-115">Wenn Sie E-9-1-1-SIP-Trunks zentral haben, und ein WAN-Ausfalls auftritt, Clients anmelden zum Abrufen eines Speicherorts aus standortinformationsdienst oder die Verbindung mit dem Dienstanbieter Notdienste möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="1cdcd-116">Skype für Unternehmen bietet mehrere Strategien für die Verarbeitung von VoIP-ausfallsicherheit in Zweigstellen, einschließlich: müssen ausfallsichere Datennetzwerke, einen SIP-Trunk in jeder Zweigstelle bereitstellen oder pushen von Notrufen an das lokale Gateway out bei Ausfällen.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="1cdcd-117">Weitere Informationen hierzu finden Sie unter [Planning for Branch-Site Voice Resiliency](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cdcd-117">For details, see [Planning for Branch-Site Voice Resiliency](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>
    
 <span data-ttu-id="1cdcd-118">**Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**</span><span class="sxs-lookup"><span data-stu-id="1cdcd-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>
  
 <span data-ttu-id="1cdcd-119">Automatische Speicherort Erwerb steht nur für Clients, die im Netzwerk der Organisation, damit Ihre Organisation muss entscheiden, ob sie E9-1-1-Anrufe zwischen Skype für Clients während der lokale-Business unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="1cdcd-120">Beispielsweise können Sie Benutzer Notrufe tätigen, wenn sie von zu Hause oder aus einem Kundenstandort arbeiten?</span><span class="sxs-lookup"><span data-stu-id="1cdcd-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="1cdcd-121">Wenn ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client konfiguriert werden, um einen Speicherort für den Benutzer aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="1cdcd-122">Da diese Benutzer bereitgestellten Speicherorte gegen Master Street Address Guide (Street) prevalidated ist nicht möglich, wird der emergency Services Service Provider Verteiler müssen jedoch die Gültigkeit des Speicherorts Alternativtext mit dem Anrufer vor dem routing bestätigen der Anruf an öffentliche Sicherheit beantworten Point (PSAP).</span><span class="sxs-lookup"><span data-stu-id="1cdcd-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1cdcd-123">Skype für Business-Clients der Benutzer über VPN eine Verbindung mit Netzwerk Ihrer Organisation herstellen kann interne IP-Adressinformationen aufzunehmen, aber, da diese Adressen zum Identifizieren der aktuelle Standort des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze ausgeschlossen werden aus dem Dienst Standortinformationen.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span> 
  
 <span data-ttu-id="1cdcd-124">**Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="1cdcd-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>
  
 <span data-ttu-id="1cdcd-p106">Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter einer Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird, VoIP-Richtlinien zu.</span><span class="sxs-lookup"><span data-stu-id="1cdcd-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>
    


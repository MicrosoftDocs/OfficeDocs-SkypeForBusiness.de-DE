---
title: Definieren des Bereichs der E9-1-1-Bereitstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Entscheidungen, die für die Planung einer E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind.
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802465"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="4f227-103">Definieren des Bereichs der E9-1-1-Bereitstellung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4f227-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="4f227-104">Entscheidungen, die für die Planung einer E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4f227-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="4f227-105">Bevor Sie Skype for Business für E9-1-1 konfigurieren, müssen Sie Ihre E9-1-1-Bereitstellung planen.</span><span class="sxs-lookup"><span data-stu-id="4f227-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="4f227-106">Stellen Sie sich die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="4f227-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="4f227-107">**Was sind die Richtlinien und rechtlichen Verpflichtungen Ihrer Organisation in Bezug auf E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="4f227-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="4f227-108">Die gesetzlichen E9-1-1-Anforderungen für Nebenstellenanlagen (im E9-1-1-Jargon als „Telefonsysteme mit mehreren Leitungen“ oder „Mehrleitungstelefonsysteme“ bezeichnet) unterscheiden sich von Staat zu Staat.</span><span class="sxs-lookup"><span data-stu-id="4f227-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="4f227-109">Wenden Sie sich an ihr rechtliches Team, um sich mit den Verpflichtungen vertraut zu machen, die für Ihre Bereitstellung von Skype for Business in ihren relevanten Regionen gelten können.</span><span class="sxs-lookup"><span data-stu-id="4f227-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="4f227-110">**Welche Bereiche innerhalb Ihres Unternehmens müssen für E9-1-1 aktiviert werden?**</span><span class="sxs-lookup"><span data-stu-id="4f227-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="4f227-p103">Sie können E9-1-1 innerhalb des gesamten Unternehmens oder für ausgewählte Standorte aktivieren. Beispielsweise können für Büros in verschiedenen Staaten unterschiedliche E9-1-1-Anforderungen gelten und Standorte außerhalb der USA können ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4f227-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="4f227-113">**Wie möchten Sie E9-1-1-Zweigstellen bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="4f227-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="4f227-114">Sie müssen mit dem Konzept der VoIP-Ausfallsicherheit für Zweigstellenstandorte vertraut sein, wenn Sie E9-1-1 in einer Zweigstelle bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4f227-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="4f227-115">Wenn Sie über zentralisierte E-9-1-1-SIP-Trunks verfügen und ein WAN-Ausfall auftritt, können Clients, die sich anmelden, möglicherweise keinen Standort vom standortinformationsdienst abrufen oder eine Verbindung mit dem Notdienste-Dienstanbieter herstellen.</span><span class="sxs-lookup"><span data-stu-id="4f227-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="4f227-116">Skype for Business bietet verschiedene Strategien für die Behandlung von sprach Stabilität in Zweigniederlassungen, darunter: robustes Daten Netz, Bereitstellungeines SIP-Trunks an jedem Zweig oder Pushen von Notrufen beim Ausfall des lokalen Gateways.</span><span class="sxs-lookup"><span data-stu-id="4f227-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="4f227-117">Ausführliche Informationen finden Sie unter [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f227-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="4f227-118">**Planen Sie die Aktivierung von E9-1-1 für Benutzer außerhalb des Netzwerks?**</span><span class="sxs-lookup"><span data-stu-id="4f227-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="4f227-119">Die automatische Standorterfassung steht nur für Clients zur Verfügung, die sich im Netzwerk der Organisation befinden, sodass Ihre Organisation entscheiden muss, ob Sie E9-1-1-Anrufe unterstützt, die von Skype for Business-Clients außerhalb des Lokals getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="4f227-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="4f227-120">Möchten Sie beispielsweise Benutzern die Möglichkeit geben, Notrufe zu tätigen, wenn Sie von zu Hause oder von einem Kundenstandort aus arbeiten?</span><span class="sxs-lookup"><span data-stu-id="4f227-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="4f227-121">Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, kann der Client so konfiguriert werden, dass er den Benutzer zur Eingabe eines Speicherorts auffordert.</span><span class="sxs-lookup"><span data-stu-id="4f227-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="4f227-122">Da diese vom Benutzer bereitgestellten Speicherorte jedoch nicht mit dem Master Street Address Guide (MSAG) vorab validiert werden können, muss der Dienstanbieter für Notrufdienste die Gültigkeit des Standorts mit dem Anrufer vor dem Routing bestätigen. der Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP).</span><span class="sxs-lookup"><span data-stu-id="4f227-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="4f227-123">Skype for Business-Clients von Benutzern, die mithilfe von VPN eine Verbindung mit dem Netzwerk Ihrer Organisation herstellen, können interne IP-Adressinformationen aufnehmen, aber da diese Adressen nicht zur Identifizierung des tatsächlichen Standorts des Benutzers verwendet werden können, ist es wichtig, dass VPN-Subnetze ausgeschlossen werden. vom standortinformationsdienst aus.</span><span class="sxs-lookup"><span data-stu-id="4f227-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="4f227-124">**Möchten Sie eine Weiterleitung von Notrufen an Standorte außerhalb der USA bereitstellen?**</span><span class="sxs-lookup"><span data-stu-id="4f227-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="4f227-p106">Eine Notrufweiterleitung kann beispielsweise für Unternehmensbereiche bereitgestellt werden, für die kein Anbieter einer Notrufunterstützung zur Verfügung steht (beispielsweise an internationalen Standorten). Erstellen Sie hierzu einen neuen Standort, und weisen Sie den Standorten, die auf eine PSTN-Verwendung verweisen, bei der der Anruf durch das lokale Gateway weitergeleitet wird, VoIP-Richtlinien zu.</span><span class="sxs-lookup"><span data-stu-id="4f227-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>



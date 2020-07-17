---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786007"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="fa86d-103">Contoso-Fallstudie: standortbasiertes Routing</span><span class="sxs-lookup"><span data-stu-id="fa86d-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="fa86d-104">Location-Based Routing (LBR) ist ein Feature, das die Gebühren Umgehung auf der Grundlage der Richtlinien und des physischen Standorts des Benutzers zum Zeitpunkt des Einleitens oder Empfangens eines Anrufs beschränkt.</span><span class="sxs-lookup"><span data-stu-id="fa86d-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="fa86d-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fa86d-105">Overview</span></span>

<span data-ttu-id="fa86d-106">Contoso hat zwei Niederlassungen in einem Land, in dem es illegal ist, den PSTN-Anbieter (Public Switched Telephone Network) zu umgehen, um die Kosten für Ferngespräche zu verringern.</span><span class="sxs-lookup"><span data-stu-id="fa86d-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="fa86d-107">Das Hauptbüro verfügt über eine Internet Verbindung, die vom Hauptbüro und vom zweiten Office verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa86d-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="fa86d-108">Jede Niederlassung verfügt über einen eigenen Session Border Controller (SBC), der mit einem PSTN-Netzbetreiber verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="fa86d-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="fa86d-109">In diesem Land hatte Contoso LBR für die Bereitstellung von Skype for Business konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fa86d-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="fa86d-110">Wenn Sie feststellen möchten, wie Sie LBR für Teams konfigurieren, lesen Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fa86d-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="fa86d-111">Contoso hat festgestellt, dass Teams und Skype for Business denselben Szenarien folgen, wenn ein Anruf getätigt werden kann, wenn er empfangen werden kann, wenn ein PSTN-Anruf an einen Teams-Benutzer übertragen werden kann, und wenn Sie einen anderen Teams-Benutzer in den PSTN-Anruf übertragen können.</span><span class="sxs-lookup"><span data-stu-id="fa86d-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="fa86d-112">Für Skype for Business wurde LBR mit dem SBC-SIP-Trunk (Session Border Controller) konfiguriert, der eine Verbindung mit dem PSTN-Netzbetreiber herstellt.</span><span class="sxs-lookup"><span data-stu-id="fa86d-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="fa86d-113">Für diesen SBC hat Contoso die [Liste der zertifizierten SBCS](direct-routing-border-controllers.md) überprüft und festgestellt, dass die bereitgestellte SBC für das direkte Routing zertifiziert ist, aber nicht für die medienumgehung zertifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="fa86d-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="fa86d-114">Zur Unterstützung von LBR muss das direkte Routing auf den SBC vor Ort konfiguriert sein, es muss ein lokales Internet-Ausstieg vorhanden sein, und der SBC muss für die medienumgehung konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="fa86d-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="fa86d-115">Auf der Grundlage dieser Informationen beschloss Contoso Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fa86d-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="fa86d-116">So verzögern Sie die Aktivierung von Teams LBR, bis der vorhandene SBC für die medienumgehung zertifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="fa86d-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="fa86d-117">Contoso hat entschieden, den Hauptstandort SBC für die direkte Route zu Office 365 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa86d-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="fa86d-118">Der Hauptstandort SBC ist der Proxy-SBC für die Remotewebsite.</span><span class="sxs-lookup"><span data-stu-id="fa86d-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="fa86d-119">Contoso hat einen Drittanbieter-Berater in Indien verwendet, um die Zertifizierung der LBR-Konfiguration mit dem Telefonieunternehmen in Land zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fa86d-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="fa86d-120">Zur Unterstützung von Benutzern, die von außerhalb des Büros arbeiten, um PSTN-Anrufe zu tätigen, wurde das Unternehmen, das das Mobiltelefon ausgestellt hat, seinen Mitarbeitern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fa86d-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="fa86d-121">Die folgenden Diagramme zeigen die vor-und nach-Bereitstellungen für ein Land mit Telefonie-Regelungen, die standortbasiertes Routing erfordern:</span><span class="sxs-lookup"><span data-stu-id="fa86d-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="fa86d-122">**Ursprüngliche Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="fa86d-122">**Original deployment**</span></span>

![Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-5.png)

<span data-ttu-id="fa86d-124">**Bereitstellung mit direktem Routing**</span><span class="sxs-lookup"><span data-stu-id="fa86d-124">**Deployment with Direct Routing**</span></span>

![Diagramm, das vor dem Zustand angezeigt wird](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="fa86d-126">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="fa86d-126">Configuration:</span></span> 

<span data-ttu-id="fa86d-127">Zum Konfigurieren der Netzwerkkomponenten in Microsoft Teams befolgte Contoso die Anweisungen unter [Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="fa86d-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="fa86d-128">Contoso hat die folgenden Schritte zum Konfigurieren des standortbasierten Routings ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="fa86d-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="fa86d-129">Definieren von netzwerkregionen – es wurde eine netzwerkregion definiert.</span><span class="sxs-lookup"><span data-stu-id="fa86d-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="fa86d-130">Definieren von Netzwerk Websites – es wurden zwei Netzwerk Websites definiert.</span><span class="sxs-lookup"><span data-stu-id="fa86d-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="fa86d-131">Eine Website für jeden Office-Standort in der Region.</span><span class="sxs-lookup"><span data-stu-id="fa86d-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="fa86d-132">Netzwerk-Subnetze definieren – jede Etage innerhalb eines Office-Standorts verfügt über ein eigenes Subnetz für das kabelgebundene und drahtlose Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="fa86d-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="fa86d-133">Diese Konfiguration führte zu 20 Subnetzen für contoso.</span><span class="sxs-lookup"><span data-stu-id="fa86d-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="fa86d-134">Vertrauenswürdige IP-Adressen definieren – die externen IP-Adressen für den SBC wurden der vertrauenswürdigen IP-Adresse hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fa86d-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  


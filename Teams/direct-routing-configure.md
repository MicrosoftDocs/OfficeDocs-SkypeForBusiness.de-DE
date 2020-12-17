---
title: Konfigurieren von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie das direkte Routing von Microsoft Phone System so konfigurieren, dass die lokale Telefonie-Infrastruktur mit Microsoft Teams verbunden wird.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701293"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="ac876-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ac876-103">Configure Direct Routing</span></span>

<span data-ttu-id="ac876-104">Mit dem direkt Routing von Microsoft Phone System können Sie Ihre lokale Telefonie-Infrastruktur mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="ac876-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="ac876-105">Der Artikel listet die allgemeinen Schritte auf, die zum Verbinden eines unterstützten lokalen Session Border Controller (SBC) mit Direct Routing erforderlich sind, und wie Sie die Benutzer von Teams für die Verwendung des direkten Routings zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ac876-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ac876-106">Dieser Artikel enthält Links zu den zugehörigen Artikeln für Details.</span><span class="sxs-lookup"><span data-stu-id="ac876-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="ac876-107">Informationen dazu, ob Direct Routing die richtige Lösung für Ihre Organisation ist, finden Sie unter [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="ac876-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="ac876-108">Informationen zu den Voraussetzungen und zur Planung der Bereitstellung finden Sie unter [Planen des direkten Routings](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="ac876-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="ac876-109">Sie können auch die folgende Sitzung sehen, um zu erfahren, welche Vorteile ein direktes Routing hat, wie Sie es planen und wie es bereitgestellt wird: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="ac876-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="ac876-110">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ac876-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ac876-111">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac876-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="ac876-112">Bevor Sie die Schritte in diesen Artikeln ausführen, empfiehlt Microsoft, dass Sie sicherstellen, dass Ihr SBC bereits vom SBC-Anbieter als empfohlen konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="ac876-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="ac876-113">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ac876-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="ac876-114">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ac876-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="ac876-115">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="ac876-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="ac876-116">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ac876-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="ac876-117">Metaswitch-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ac876-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="ac876-118">Eine vollständige Liste der unterstützten SBCS finden Sie unter [Liste der für die direkte Weiterleitung zertifizierten Session Border Controller](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="ac876-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="ac876-119">Führen Sie die folgenden Schritte aus, um das Microsoft Phone-System zu konfigurieren und Benutzern die Verwendung des direkten Routings zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="ac876-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="ac876-120">**Schritt 1:**</span><span class="sxs-lookup"><span data-stu-id="ac876-120">**Step 1.**</span></span> [<span data-ttu-id="ac876-121">Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="ac876-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="ac876-122">**Schritt 2:**</span><span class="sxs-lookup"><span data-stu-id="ac876-122">**Step 2.**</span></span> [<span data-ttu-id="ac876-123">Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail</span><span class="sxs-lookup"><span data-stu-id="ac876-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="ac876-124">**Schritt 3:**</span><span class="sxs-lookup"><span data-stu-id="ac876-124">**Step 3.**</span></span> [<span data-ttu-id="ac876-125">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="ac876-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="ac876-126">**Schritt 4:**</span><span class="sxs-lookup"><span data-stu-id="ac876-126">**Step 4.**</span></span> [<span data-ttu-id="ac876-127">Übersetzen von Zahlen in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="ac876-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="ac876-128">Wenn Sie einen SBC für mehrere Mandanten konfigurieren, sollten Sie auch die [Konfiguration eines SBC für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="ac876-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="ac876-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ac876-129">Related topics</span></span>

[<span data-ttu-id="ac876-130">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="ac876-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="ac876-131">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ac876-131">Plan Direct Routing</span></span>](direct-routing-plan.md)


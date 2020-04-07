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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie das direkte Routing des Microsoft Phone-Systems konfigurieren.
ms.openlocfilehash: b596e5acb0002ad90f5c0298b56973f2490ad2e6
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170583"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="07ad8-103">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="07ad8-103">Configure Direct Routing</span></span>

<span data-ttu-id="07ad8-104">Mit dem direkt Routing von Microsoft Phone System können Sie Ihre lokale Telefonie-Infrastruktur mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="07ad8-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="07ad8-105">Der Artikel listet die allgemeinen Schritte auf, die zum Verbinden eines unterstützten lokalen Session Border Controller (SBC) mit Direct Routing erforderlich sind, und wie Sie die Benutzer von Teams für die Verwendung des direkten Routings zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (PSTN) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="07ad8-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="07ad8-106">Dieser Artikel enthält Links zu den zugehörigen Artikeln für Details.</span><span class="sxs-lookup"><span data-stu-id="07ad8-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="07ad8-107">Informationen dazu, ob Direct Routing die richtige Lösung für Ihre Organisation ist, finden Sie unter [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="07ad8-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="07ad8-108">Informationen zu den Voraussetzungen und zur Planung der Bereitstellung finden Sie unter [Planen des direkten Routings](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="07ad8-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="07ad8-109">Sie können auch die folgende Sitzung sehen, um zu erfahren, welche Vorteile ein direktes Routing hat, wie Sie es planen und wie es bereitgestellt wird: [Direktes Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="07ad8-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="07ad8-110">Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="07ad8-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="07ad8-111">Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="07ad8-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="07ad8-112">Bevor Sie die Schritte in diesen Artikeln ausführen, empfiehlt Microsoft, dass Sie sicherstellen, dass Ihr SBC bereits vom SBC-Anbieter als empfohlen konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="07ad8-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="07ad8-113">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="07ad8-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="07ad8-114">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="07ad8-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="07ad8-115">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="07ad8-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="07ad8-116">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="07ad8-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="07ad8-117">Metaswitch-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="07ad8-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="07ad8-118">Eine vollständige Liste der unterstützten SBCS finden Sie unter [Liste der für die direkte Weiterleitung zertifizierten Session Border Controller](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="07ad8-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="07ad8-119">Führen Sie die folgenden Schritte aus, um das Microsoft Phone-System zu konfigurieren und Benutzern die Verwendung des direkten Routings zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="07ad8-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="07ad8-120">**Schritt 1:**</span><span class="sxs-lookup"><span data-stu-id="07ad8-120">**Step 1.**</span></span> [<span data-ttu-id="07ad8-121">Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="07ad8-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="07ad8-122">**Schritt 2:**</span><span class="sxs-lookup"><span data-stu-id="07ad8-122">**Step 2.**</span></span> [<span data-ttu-id="07ad8-123">Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail</span><span class="sxs-lookup"><span data-stu-id="07ad8-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="07ad8-124">**Schritt 3:**</span><span class="sxs-lookup"><span data-stu-id="07ad8-124">**Step 3.**</span></span> [<span data-ttu-id="07ad8-125">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="07ad8-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="07ad8-126">**Schritt 4:**</span><span class="sxs-lookup"><span data-stu-id="07ad8-126">**Step 4.**</span></span> [<span data-ttu-id="07ad8-127">Übersetzen von Zahlen in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="07ad8-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="07ad8-128">Wenn Sie einen SBC für mehrere Mandanten konfigurieren, sollten Sie auch die [Konfiguration eines SBC für mehrere Mandanten](direct-routing-sbc-multiple-tenants.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="07ad8-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="07ad8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07ad8-129">See also</span></span>

[<span data-ttu-id="07ad8-130">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="07ad8-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="07ad8-131">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="07ad8-131">Plan Direct Routing</span></span>](direct-routing-plan.md)


---
title: Konfigurieren der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
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
description: Hier erfahren Sie, wie Sie die medienumgehung mithilfe des direkten Routings von Telefonsystemen für Microsoft Teams konfigurieren, indem Sie alle Benutzer gleichzeitig wechseln oder eine Phased approaching (empfohlen) implementieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416895"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="f47e6-103">Konfigurieren der Medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="f47e6-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="f47e6-104">Bevor Sie die medienumgehung mit Direct Routing konfigurieren, stellen Sie sicher, dass Sie [Plan für medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md)gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="f47e6-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="f47e6-105">Um die medienumgehung zu aktivieren, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="f47e6-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="f47e6-106">Stellen Sie sicher, dass Ihr SBC-Anbieter (Session Border Controller) die medienumgehung unterstützt und Anweisungen zum Konfigurieren der Umgehungsfunktion für den SBC enthält.</span><span class="sxs-lookup"><span data-stu-id="f47e6-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="f47e6-107">Informationen zu SBCS, welche die medienumgehung unterstützen, und Anweisungen finden Sie auf der Zertifizierungsseite.</span><span class="sxs-lookup"><span data-stu-id="f47e6-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="f47e6-108">Sie müssen die medienumgehung auf dem Stamm mithilfe des folgenden Befehls aktivieren: **CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="f47e6-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="f47e6-109">Stellen Sie sicher, dass die erforderlichen Anschlüsse geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="f47e6-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="f47e6-110">Migrieren von nicht gebypassten Trunks zu Bypass-fähigen Trunks</span><span class="sxs-lookup"><span data-stu-id="f47e6-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="f47e6-111">Sie können alle Benutzer gleichzeitig wechseln, oder Sie können eine Phased approached (empfohlen) implementieren.</span><span class="sxs-lookup"><span data-stu-id="f47e6-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="f47e6-112">**Alle Benutzer gleichzeitig umschalten.**</span><span class="sxs-lookup"><span data-stu-id="f47e6-112">**Switch all users at once.**</span></span> <span data-ttu-id="f47e6-113">Wenn alle Bedingungen erfüllt sind, können Sie den Bypass-Modus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f47e6-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="f47e6-114">Allerdings werden alle Ihre Produktionsbenutzer gleichzeitig gewechselt.</span><span class="sxs-lookup"><span data-stu-id="f47e6-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="f47e6-115">Da bei der Konfiguration von Trunks und Ports möglicherweise einige Probleme auftreten, kann dies auf die Benutzeroberfläche der Produktionsumgebung zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="f47e6-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="f47e6-116">**Phasen orientierter Ansatz (Empfohlen)**.</span><span class="sxs-lookup"><span data-stu-id="f47e6-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="f47e6-117">Erstellen Sie einen neuen trunk für denselben SBC (mit einem anderen Port), testen Sie ihn, und ändern Sie die Richtlinie für Online-VoIP-Routing, damit die Benutzer auf den neuen trunk verweisen können.</span><span class="sxs-lookup"><span data-stu-id="f47e6-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="f47e6-118">Dies ist die empfohlene Vorgehensweise, da Sie einen reibungsloseren Übergang und eine unterbrechungsfreie Benutzererfahrung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f47e6-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="f47e6-119">Dieser Ansatz erfordert die Konfiguration des SBC, einen neuen FQDN-Namen und die Konfiguration der Firewall.</span><span class="sxs-lookup"><span data-stu-id="f47e6-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="f47e6-120">Hinweis Sie müssen sicherstellen, dass Ihr Zertifikat beide Trunks unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f47e6-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="f47e6-121">In San benötigen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.</span><span class="sxs-lookup"><span data-stu-id="f47e6-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrieren von nicht gebypassten Trunks zu Bypass-fähigen Trunks](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="f47e6-123">Anweisungen zum Konfigurieren der Trunks und zur Durchführung der Migration finden Sie in der Dokumentation Ihres SBC-Anbieters:</span><span class="sxs-lookup"><span data-stu-id="f47e6-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="f47e6-124">AudioCodes-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="f47e6-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="f47e6-125">Oracle-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="f47e6-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="f47e6-126">Bereitstellungsdokumentation zur Multifunktionsleisten-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="f47e6-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="f47e6-127">TE-Systems (anynode)-Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="f47e6-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="f47e6-128">Eine Liste der für die direkte Weiterleitung zertifizierten Session Border Controllers (SBCS) finden Sie in [der Liste der für das direkte Routing zertifizierten Session Broder-Controller](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="f47e6-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="f47e6-129">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f47e6-129">Related topics</span></span>

[<span data-ttu-id="f47e6-130">Planen der medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="f47e6-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)




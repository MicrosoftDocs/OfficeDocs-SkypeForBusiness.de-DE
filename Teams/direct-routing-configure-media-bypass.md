---
title: Konfigurieren der Medienumgehung mit direktem Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lesen Sie dieses Thema, um Informationen zum Konfigurieren der medienumgehung mit Phone System direktem Routing.
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232695"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="ddd0b-103">Konfigurieren der Medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ddd0b-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="ddd0b-104">Vor dem Konfigurieren von Medien mit direktem Routing zu umgehen, achten Sie darauf, dass Sie [Plan für Medien mit direktem Routing umgehen](direct-routing-plan-media-bypass.md)gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="ddd0b-105">Um die medienumgehung aktivieren, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="ddd0b-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="ddd0b-106">Stellen Sie sicher, dass Hersteller Ihres Session Border Controller (SBC) Wahl die medienumgehung unterstützt und bietet Anweisungen zum Konfigurieren auf die SBC umgehen.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="ddd0b-107">Finden Sie in der Zertifizierung-Seite, um Informationen und Anweisungen SBCs, welche Schriftarten Unterstützung von Medien zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="ddd0b-108">Sie müssen die medienumgehung auf den Trunk mithilfe des folgenden Befehls aktivieren: **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="ddd0b-109">Stellen Sie sicher, dass die erforderlichen Ports geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="ddd0b-110">Migrieren von nicht umgangen Trunks zur Umgehung aktivierten trunks</span><span class="sxs-lookup"><span data-stu-id="ddd0b-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="ddd0b-111">Sie können alle Benutzer gleichzeitig wechseln oder Implementieren einer phasenweisen erreicht (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="ddd0b-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="ddd0b-112">**Wechseln Sie alle Benutzer gleichzeitig.**</span><span class="sxs-lookup"><span data-stu-id="ddd0b-112">**Switch all users at once.**</span></span> <span data-ttu-id="ddd0b-113">Wenn alle erfüllt werden, können Sie die Bypass-Modus aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="ddd0b-114">Allerdings werden alle produktionsbenutzern gleichzeitig gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="ddd0b-115">Da einige Probleme zunächst möglicherweise beim Konfigurieren von Trunks und Ports treten, möglicherweise angenehmer Produktion betroffen sein.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="ddd0b-116">**Phased Ansatz. (Empfohlen)**.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="ddd0b-117">Erstellen Sie einen neuen Trunk für den gleichen SBC (mit einem anderen Port), testen sie das Formular, und ändern Sie die online VoIP-Routingrichtlinie für die Benutzer auf den neuen Trunk.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="ddd0b-118">Dies ist die empfohlene Vorgehensweise, da es für ein fließender Übergang und einheitliche benutzererfahrung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="ddd0b-119">Bei diesem Ansatz müssen die Konfiguration der SBC, einer neuen FQDN-Namen und die Konfiguration der Firewall.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="ddd0b-120">Beachten Sie, dass Sie benötigen, um sicherzustellen, dass Ihr Zertifikat beide Trunks unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="ddd0b-121">SAN müssen Sie zwei Namen (**sbc1.contoso.com** und **sbc2.contoso.com**) oder ein Platzhalterzertifikat.</span><span class="sxs-lookup"><span data-stu-id="ddd0b-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migration von nicht umgangen Trunks zu Trunks Umgehung aktiviert)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="ddd0b-123">Anweisungen zum Konfigurieren der Trunks und Durchführen der Migration finden Sie unter der vom Hersteller Ihrer SBC-Dokumentation:</span><span class="sxs-lookup"><span data-stu-id="ddd0b-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="ddd0b-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="ddd0b-124">AudioCodes</span></span>
- <span data-ttu-id="ddd0b-125">Bändchen</span><span class="sxs-lookup"><span data-stu-id="ddd0b-125">Ribbon</span></span>
- <span data-ttu-id="ddd0b-126">TE-Systems (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="ddd0b-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="ddd0b-127">Eine Liste der für das direkte Routing certified Session Border Controller (SBCs) finden Sie unter [Liste der Sitzung Broder Controller für die direkte Weiterleitung zertifiziert](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="ddd0b-127">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="ddd0b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddd0b-128">See also</span></span>

[<span data-ttu-id="ddd0b-129">Planen Sie die medienumgehung mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ddd0b-129">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)




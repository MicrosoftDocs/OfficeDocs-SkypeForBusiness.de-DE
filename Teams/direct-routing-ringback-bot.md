---
title: Einrichten des Begrüssungs-bot für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie den Rückruf-bot für das direkte Routing verwenden, um unerwartete Stille zu verhindern, die auftreten können, wenn ein Anruf eingerichtet wird.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420955"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="4e172-103">Einrichten des Begrüssungs-bot für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="4e172-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="4e172-104">In diesem Artikel wird der Begrüssungs-bot beschrieben, mit dem Sie unerwartete Stille vermeiden können, die auftreten können, wenn es längere Zeit dauert, bis die Anrufe eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="4e172-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="4e172-105">Der Rückruf-bot steht für das direkte Routing im nicht-Media-Bypass-Modus zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4e172-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="4e172-106">Manchmal können eingehende Anrufe aus dem PSTN (Public Switched Telephone Network) an Teams-Clients länger als erwartet dauern.</span><span class="sxs-lookup"><span data-stu-id="4e172-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="4e172-107">Dies kann aus verschiedenen Gründen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4e172-107">This can occur for various reasons.</span></span> <span data-ttu-id="4e172-108">In diesem Fall hört der Anrufer möglicherweise nichts, der Team-Client klingelt nicht, und einige Telekommunikationsanbieter kündigen den Anruf möglicherweise an.</span><span class="sxs-lookup"><span data-stu-id="4e172-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="4e172-109">Der Rückruf-bot hilft, unerwartete Stille zu vermeiden, die in diesem Szenario auftreten können.</span><span class="sxs-lookup"><span data-stu-id="4e172-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="4e172-110">Für eingehende Anrufe vom PSTN an Teams-Clients spielt der Rückruf-bot ein unverwechselbares Audiosignal an den Anrufer ab, um anzugeben, dass die Mannschaft den Anruf annimmt.</span><span class="sxs-lookup"><span data-stu-id="4e172-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="4e172-111">Der Rückruf-bot generiert frühe Medien aus dem Back-End von Teams.</span><span class="sxs-lookup"><span data-stu-id="4e172-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="4e172-112">In einigen Ländern und Regionen wird Ihnen möglicherweise der Anruf in Rechnung gestellt, wenn das Medium in den Fluss geht.</span><span class="sxs-lookup"><span data-stu-id="4e172-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="4e172-113">Konfigurieren des Rückruf-bot</span><span class="sxs-lookup"><span data-stu-id="4e172-113">Configure the Ringback bot</span></span>

<span data-ttu-id="4e172-114">Verwenden Sie das Cmdlet " [festlegen-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) ", um eine zuvor definierte SBC-Konfiguration (Session Border Controller) zu ändern, oder das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) , um eine neue SBC-Konfiguration zusammen mit dem **GenerateRingingWhileLocatingUser** -Parameter zum Konfigurieren des Rückruf-bot zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e172-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="4e172-115">Um den Rückruf-bot zu aktivieren, setzen Sie den **GenerateRingingWhileLocatingUser** -Parameter auf **$true**.</span><span class="sxs-lookup"><span data-stu-id="4e172-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="4e172-116">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4e172-116">This is the default value.</span></span> 

- <span data-ttu-id="4e172-117">Um den Rückruf-bot zu deaktivieren, setzen Sie den **GenerateRingingWhileLocatingUser** -Parameter auf **$false**.</span><span class="sxs-lookup"><span data-stu-id="4e172-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="4e172-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4e172-118">Related topics</span></span>

- [<span data-ttu-id="4e172-119">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e172-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

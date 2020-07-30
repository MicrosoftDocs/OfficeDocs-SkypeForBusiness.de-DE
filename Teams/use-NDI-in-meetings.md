---
title: Verwenden von ndi in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie ndi in Microsoft Teams verwenden.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522902"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="232a7-103">Verwenden von ndi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="232a7-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="232a7-104">Die Netzwerkgeräte Schnittstelle (NDI) ist eine moderne Lösung zum Verbinden von Mediengeräten (wie einer Studio Kamera und einem Mixer).</span><span class="sxs-lookup"><span data-stu-id="232a7-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="232a7-105">Anstatt physische Verbindungen zu verwenden, ermöglicht ndi die Konnektivität über ein lokales Intranet, einschließlich auf einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="232a7-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="232a7-106">NewTek ndi® hat sich zu einer standardmäßigen Branchenlösung für die Erstellung von Live-Inhalten für Streams und hat in der professionellen Broadcast-Welt ein erhebliches Bewusstsein und Akzeptanz erlangt.</span><span class="sxs-lookup"><span data-stu-id="232a7-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="232a7-107">Skype hat zuvor ndi-Funktionalität für Skype in späten 2018 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="232a7-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="232a7-108">Microsoft Teams nutzt diese Funktion, um die Besprechungs Erfahrung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="232a7-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="232a7-109">NDI ist auf ein lokales Netzwerk limitiert und sollte nur als Teil des Produktionsworkflows, keine Broadcast-Lösung, betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="232a7-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="232a7-110">Aktivieren von ndi</span><span class="sxs-lookup"><span data-stu-id="232a7-110">Turn on NDI</span></span>

<span data-ttu-id="232a7-111">NDI erfordert zwei Schritte, die für einen Benutzer aktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="232a7-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="232a7-112">Der mandantenadministrator muss das Feature-Flag enableStreamingCallsOverNdi aktivieren.</span><span class="sxs-lookup"><span data-stu-id="232a7-112">The tenant admin must enable the feature flag enableStreamingCallsOverNdi.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="232a7-113">Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer ndi für seinen jeweiligen Client über **Einstellungs**  >  **Berechtigungen**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="232a7-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="232a7-114">Wenn ein Benutzer einer Besprechung Beitritt, wird eine Meldung angezeigt, die Sie darüber informiert, dass die Besprechung übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="232a7-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="232a7-115">Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen Sie von der Besprechung abfallen.</span><span class="sxs-lookup"><span data-stu-id="232a7-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="232a7-116">Die folgende Abbildung zeigt die Banner Nachricht, die ein Benutzer in einer Teams-Besprechung sieht.</span><span class="sxs-lookup"><span data-stu-id="232a7-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Abbildung des ndi-Banners, das in einer Teams-Besprechung angezeigt wird.](media/NDI-disclosure.png)

<span data-ttu-id="232a7-118">Das Banner enthält einen Link zu den [Microsoft-Datenschutzrichtlinien](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span><span class="sxs-lookup"><span data-stu-id="232a7-118">The banner has a link to the [Microsoft privacy policy](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="232a7-119">Unterstützte Gebietsschemas und Benutzertypen</span><span class="sxs-lookup"><span data-stu-id="232a7-119">Supported locales and user types</span></span>

<span data-ttu-id="232a7-120">NDI wird in allen Gebietsschemas unterstützt.</span><span class="sxs-lookup"><span data-stu-id="232a7-120">NDI is supported in all locales.</span></span> <span data-ttu-id="232a7-121">Die folgenden Benutzer werden in einer ndi-Besprechung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="232a7-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="232a7-122">In-Tenant – vollständige Unterstützung, bereitgestellt basierend auf Ring/Mandanten-ID/UserID (gesteuert durch Besprechungsrichtlinien + Feature-Flag)</span><span class="sxs-lookup"><span data-stu-id="232a7-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy + Feature Flag)</span></span>
- <span data-ttu-id="232a7-123">Federated – Nein (auch wenn ndi aktiviert ist)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="232a7-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="232a7-124">Freemium-Nein (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="232a7-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="232a7-125">Anonym – Nein (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="232a7-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="232a7-126">Gast – Nein (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="232a7-126">Guest – no  (default value)</span></span>

<span data-ttu-id="232a7-127"><sup>1</sup> Geräte verfügen über eine ndi-Einstellung, die standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="232a7-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="232a7-128">Wenn ein Besprechungsteilnehmer ein Gerät mit ndi off verwendet, müssen Sie ndi aktivieren.</span><span class="sxs-lookup"><span data-stu-id="232a7-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>

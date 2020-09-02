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
ms.openlocfilehash: 24e4312af520bf783c0382b7543190644bfc1ff0
ms.sourcegitcommit: 7c701fc38c8a81ac0938f666c336252c3983ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47323989"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="084e7-103">Verwenden von ndi®-Technologie in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="084e7-103">Use NDI® technology in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

 <span data-ttu-id="084e7-104">NDI® (Network Device Interface)-Technologie ist eine moderne Lösung für den Anschluss von Mediengeräten (wie Studio Kamera und Mixer).</span><span class="sxs-lookup"><span data-stu-id="084e7-104">NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="084e7-105">Anstatt physische Verbindungen zu verwenden, ermöglicht die ndi-® Technologie die Konnektivität über ein lokales Intranet, auch auf einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="084e7-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="084e7-106">NewTek ndi® Technology ist zu einer standardmäßigen Branchenlösung geworden, um Live-Inhalte für Streams zu produzieren, und hat in der professionellen Broadcast-Welt erhebliches Bewusstsein und Akzeptanz erlangt.</span><span class="sxs-lookup"><span data-stu-id="084e7-106">NewTek NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="084e7-107">Skype hat zuvor ndi-® Funktionen zu Skype in späten 2018 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="084e7-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="084e7-108">Microsoft Teams nutzt diese Funktion, um die Besprechungs Erfahrung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="084e7-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="084e7-109">NDI®-Technologie ist auf ein lokales Netzwerk limitiert und sollte nur als Teil des Produktionsworkflows, keine Broadcast-Lösung, betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="084e7-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="084e7-110">Aktivieren der ndi®-Technologie</span><span class="sxs-lookup"><span data-stu-id="084e7-110">Turn on NDI® technology</span></span>

<span data-ttu-id="084e7-111">NDI®-Technologie erfordert zwei Schritte, die für einen Benutzer aktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="084e7-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="084e7-112">Der mandantenadministrator muss die Eigenschaft "AllowNDIStreaming" in CsTeamsMeetingPolicy aktivieren.</span><span class="sxs-lookup"><span data-stu-id="084e7-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="084e7-113">Nachdem diese Änderung aufgefüllt wurde, muss der Endbenutzer die ndi-® Technologie für seinen jeweiligen Client über **Einstellungs**  >  **Berechtigungen**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="084e7-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="084e7-114">Wenn ein Benutzer einer Besprechung Beitritt, wird eine Meldung angezeigt, die Sie darüber informiert, dass die Besprechung übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="084e7-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="084e7-115">Wenn Benutzer nicht in die Übertragung einbezogen werden möchten, müssen Sie von der Besprechung abfallen.</span><span class="sxs-lookup"><span data-stu-id="084e7-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="084e7-116">Die folgende Abbildung zeigt die Banner Nachricht, die ein Benutzer in einer Teams-Besprechung sieht.</span><span class="sxs-lookup"><span data-stu-id="084e7-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Ein Bild des ndi® Technology-Banners, das in einer Teams-Besprechung angezeigt wird.](media/NDI-disclosure.png)

<span data-ttu-id="084e7-118">Das Banner enthält einen Link zu den [Microsoft-Datenschutzrichtlinien](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="084e7-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="084e7-119">Unterstützte Gebietsschemas und Benutzertypen</span><span class="sxs-lookup"><span data-stu-id="084e7-119">Supported locales and user types</span></span>

<span data-ttu-id="084e7-120">NDI®-Technologie wird in allen Gebietsschemas unterstützt.</span><span class="sxs-lookup"><span data-stu-id="084e7-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="084e7-121">Die folgenden Benutzer sind in einem ndi-®-Technologiedaten Strom enthalten, aber nicht alle Benutzer können auf den ndi-®-Technologiedaten Strom zugreifen:</span><span class="sxs-lookup"><span data-stu-id="084e7-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="084e7-122">In-Tenant – vollständige Unterstützung, bereitgestellt basierend auf Ring/Mandanten-ID/UserID (gesteuert durch die Richtlinien für Besprechungen)</span><span class="sxs-lookup"><span data-stu-id="084e7-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="084e7-123">Federated – kein Datenstrom Zugriff (auch wenn Sie über ndi® Technologie verfügen)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="084e7-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="084e7-124">Freemium-kein Datenstrom Zugriff</span><span class="sxs-lookup"><span data-stu-id="084e7-124">Freemium - no stream access</span></span>
- <span data-ttu-id="084e7-125">Anonym – kein Datenstrom Zugriff</span><span class="sxs-lookup"><span data-stu-id="084e7-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="084e7-126">Gast – kein Datenstrom Zugriff</span><span class="sxs-lookup"><span data-stu-id="084e7-126">Guest – no stream access</span></span>  

<span data-ttu-id="084e7-127"><sup>1</sup> Geräte verfügen über eine ndi-® Technologie Einstellung, die standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="084e7-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="084e7-128">Wenn ein Besprechungsteilnehmer ein Gerät mit ndi®-Technologie verwendet, müssen Sie die ndi-® Technologie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="084e7-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>

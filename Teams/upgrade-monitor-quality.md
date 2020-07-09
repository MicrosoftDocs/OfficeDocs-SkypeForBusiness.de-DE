---
title: Qualität der Benutzererfahrung | Microsoft Teams | QoS | Anrufqualität
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Der Administrator kann sich mit den Aufgaben und Aktivitäten vertraut machen, die für die Überwachung von Qualität und Verwendung von Microsoft Teams erforderlich sind.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 843acff0dafc7cd5ad2b3fd63ccc009c64716b03
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085921"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="cfe69-103">Leitfaden zur Überprüfung der Erlebnisqualität</span><span class="sxs-lookup"><span data-stu-id="cfe69-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="cfe69-104">![Diagramm mit Hervorhebung der Operation Excellence-Stufe der Upgrade-Reise](media/upgrade-banner-op-excellence.png "Etappen des Upgrade-Vorgangs mit dem Schwerpunkt auf der Stufe "Operational Excellence"")</span><span class="sxs-lookup"><span data-stu-id="cfe69-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="cfe69-105">Dieser Artikel ist Teil des "Operational Excellence"-Schritts Ihres Upgrade-Vorgangs, der beginnt, sobald Sie das Upgrade von Skype for Business auf Teams abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="cfe69-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="cfe69-106">Verbessern und Überwachen der Anrufqualität</span><span class="sxs-lookup"><span data-stu-id="cfe69-106">Improve and monitor call quality</span></span>

<span data-ttu-id="cfe69-107">[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md) umfasst eine Reihe von Aktivitäten, die in wichtigen Bereichen, in denen die Benutzererfahrung am größten ist, wie im folgenden dargestellt, die Richtlinien zur Behebung bewerten und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cfe69-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="cfe69-108">![Abbildung der wichtigsten Bereiche, die während einer Überprüfung zu untersuchen sind.](media/plan-my-service-management-image2.png "Die wichtigsten Bereiche, die während einer Prüfung der Qualität der Erfahrung zu untersuchen sind: Audio-, Zuverlässigkeits-und Nutzerumfrage Ergebnisse.")</span><span class="sxs-lookup"><span data-stu-id="cfe69-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="cfe69-109">Indem Sie die im Leitfaden beschriebenen Bereiche kontinuierlich bewerten und korrigieren, können Sie deren Potenzial verringern, die Benutzererfahrung negativ zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="cfe69-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="cfe69-110">Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="cfe69-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="cfe69-111">Unvollständige Firewall- oder Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="cfe69-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="cfe69-112">Schlechte WLAN-Abdeckung</span><span class="sxs-lookup"><span data-stu-id="cfe69-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="cfe69-113">Unzureichende Bandbreite</span><span class="sxs-lookup"><span data-stu-id="cfe69-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="cfe69-114">VPN</span><span class="sxs-lookup"><span data-stu-id="cfe69-114">VPN</span></span>

- <span data-ttu-id="cfe69-115">Verwendung nicht optimierter oder integrierter Audiogeräte</span><span class="sxs-lookup"><span data-stu-id="cfe69-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="cfe69-116">Problematische Subnetze oder Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="cfe69-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="cfe69-117">Die Anleitungen in [verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md) konzentrieren sich auf die Verwendung von Call Quality Dashboard (CQD) online als primäres Tool zur Berichterstellung und Untersuchung jedes beschriebenen Bereichs, wobei der Schwerpunkt auf Audio liegt, um Akzeptanz und Auswirkungen zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="cfe69-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="cfe69-118">Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="cfe69-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="cfe69-119">Wir empfehlen Ihnen dringend, den Qualitätschampion frühzeitig zu benennen.</span><span class="sxs-lookup"><span data-stu-id="cfe69-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="cfe69-120">Nachdem Sie nominiert wurden, sollten Sie sich mit den Inhalten vertraut machen, um die [Anrufqualität für Teams zu verbessern und zu überwachen](monitor-call-quality-qos.md).</span><span class="sxs-lookup"><span data-stu-id="cfe69-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->

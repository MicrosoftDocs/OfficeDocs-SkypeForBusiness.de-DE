---
title: Qualität der Benutzererfahrung | Microsoft Teams | QoS | Anrufqualität
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Aufgaben und Aktivitäten, die für die Überwachung von Qualität und Verwendung von Microsoft Teams erforderlich sind
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e870c6e6561bac991e7b9498ef76162ec1fa2eb9
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706975"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="f2b7b-103">Handbuch für die Überprüfung der QoE (Quality of Experience)</span><span class="sxs-lookup"><span data-stu-id="f2b7b-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="f2b7b-104">![Diagramm mit Hervorhebung der Operation Excellence-Stufe der Upgrade-Reise](media/upgrade-banner-op-excellence.png "Etappen des Upgrade-Vorgangs mit dem Schwerpunkt auf der Stufe "Operational Excellence"")</span><span class="sxs-lookup"><span data-stu-id="f2b7b-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="f2b7b-105">Dieser Artikel ist Teil des "Operational Excellence"-Schritts Ihres Upgrade-Vorgangs, der beginnt, sobald Sie das Upgrade von Skype for Business auf Teams abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="f2b7b-106">Der [Leitfaden zur Überprüfung der Qualität](https://aka.ms/qerguide) der Benutzerfreundlichkeit umfasst eine Reihe von Aktivitäten, die in wichtigen Bereichen, die am stärksten zur Verbesserung der Benutzerfreundlichkeit führen, die Behebungs Anleitung bewerten und bereitstellen, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="f2b7b-107">![Abbildung der wichtigsten Bereiche, die während einer Überprüfung zu untersuchen sind.](media/plan-my-service-management-image2.png "Die wichtigsten Bereiche, die während einer Prüfung der Qualität der Erfahrung zu untersuchen sind: Audio-, Zuverlässigkeits-und Nutzerumfrage Ergebnisse.")</span><span class="sxs-lookup"><span data-stu-id="f2b7b-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="f2b7b-108">Indem Sie die im Leitfaden beschriebenen Bereiche kontinuierlich bewerten und korrigieren, können Sie deren Potenzial verringern, die Benutzererfahrung negativ zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="f2b7b-109">Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="f2b7b-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="f2b7b-110">Unvollständige Firewall- oder Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="f2b7b-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="f2b7b-111">Schlechte WLAN-Abdeckung</span><span class="sxs-lookup"><span data-stu-id="f2b7b-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="f2b7b-112">Unzureichende Bandbreite</span><span class="sxs-lookup"><span data-stu-id="f2b7b-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="f2b7b-113">VPN</span><span class="sxs-lookup"><span data-stu-id="f2b7b-113">VPN</span></span>

- <span data-ttu-id="f2b7b-114">Verwendung nicht optimierter oder integrierter Audiogeräte</span><span class="sxs-lookup"><span data-stu-id="f2b7b-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="f2b7b-115">Problematische Subnetze oder Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="f2b7b-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="f2b7b-116">Die Anleitungen im Leitfaden zur Überprüfung der Qualität der Benutzerfreundlichkeit konzentrieren sich auf die Verwendung von Call Quality Dashboard (CQD) online als primäres Tool zur Berichterstellung und Untersuchung jedes beschriebenen Bereichs, wobei der Schwerpunkt auf Audio liegt, um Akzeptanz und Auswirkungen zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="f2b7b-117">Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="f2b7b-118">Wir empfehlen Ihnen dringend, den Qualitätschampion frühzeitig zu benennen.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="f2b7b-119">Nachdem Sie nominiert wurden, sollten Sie sich mit den Inhalten im [Leitfaden zur Überprüfung der Qualität von Erfahrungen](https://aka.ms/qerguide)vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="f2b7b-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->

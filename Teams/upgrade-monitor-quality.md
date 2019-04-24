---
title: Die Qualität des Benutzererlebnisses | Microsoft-Teams | QoS | Die Anrufqualität
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Aufgaben und Aktivitäten, die für die Qualität und zur Verwendung des Microsoft-Teams, Überwachung erforderlich
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d5b34a7dc556313108555bff4d55cee7a6f9a31
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203718"
---
<span data-ttu-id="4d78d-103">![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase erstklassige Betriebsprozesse] (media/upgrade-banner-op-excellence.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase erstklassige Betriebsprozesse")</span><span class="sxs-lookup"><span data-stu-id="4d78d-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="4d78d-104">Dieser Artikel ist Teil der erstklassige Betriebsprozesse Stufe des Ihre Upgrade Reise, wodurch gestartet wird, sobald Sie die Aktualisierung von Skype für Unternehmen auf Teams abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="4d78d-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="4d78d-105">Handbuch für die Überprüfung der QoE (Quality of Experience)</span><span class="sxs-lookup"><span data-stu-id="4d78d-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="4d78d-106">[Erleben Sie die Überprüfung Handbuch für Quality of](https://aka.ms/qerguide) enthält einen Satz von Aktivitäten, die bewerten und-Wartung Anleitungen in wichtige Bereiche, die am stärksten auf Verbessern der benutzererfahrung auswirken, wie im folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d78d-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="4d78d-107">![Die Schlüsselbereiche während einer Qualität Erfahrung Überarbeitung prüfen: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.] (media/plan-my-service-management-image2.png "Die Schlüsselbereiche während einer Qualität Erfahrung Überarbeitung prüfen: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.")</span><span class="sxs-lookup"><span data-stu-id="4d78d-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="4d78d-108">Ständig bewerten und Korrigieren von der Bereiche im Handbuch beschrieben, können Sie ihre potenzielle Möglichkeit beeinträchtigen Benutzererlebnis reduziert.</span><span class="sxs-lookup"><span data-stu-id="4d78d-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="4d78d-109">Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="4d78d-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="4d78d-110">Unvollständige Firewall- oder Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="4d78d-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="4d78d-111">Schlechte WLAN-Abdeckung</span><span class="sxs-lookup"><span data-stu-id="4d78d-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="4d78d-112">Unzureichende Bandbreite</span><span class="sxs-lookup"><span data-stu-id="4d78d-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="4d78d-113">VPN</span><span class="sxs-lookup"><span data-stu-id="4d78d-113">VPN</span></span>

- <span data-ttu-id="4d78d-114">Verwendung nicht optimierter oder integrierter Audiogeräte</span><span class="sxs-lookup"><span data-stu-id="4d78d-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="4d78d-115">Problematische Subnetze oder Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="4d78d-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="4d78d-116">Die Informationen der Qualität der Erfahrung überprüfen Handbuchs behandelt Verwendung Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche beschrieben, mit Schwerpunkt auf Audio die Annahme und Auswirkungen auf die maximieren.</span><span class="sxs-lookup"><span data-stu-id="4d78d-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="4d78d-117">Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="4d78d-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="4d78d-118">Es wird dringend empfohlen, dass am Anfang der Qualität "Champion" benennen.</span><span class="sxs-lookup"><span data-stu-id="4d78d-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="4d78d-119">Nach dem benannt wird, sollten sie beginnen mit der Inhalt die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide)vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="4d78d-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
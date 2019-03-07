---
title: Die Qualität des Benutzererlebnisses | Microsoft-Teams | QoS | Die Anrufqualität
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
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
ms.openlocfilehash: 4060c0f9171c8871ed22d15325d560616bf5fc23
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460076"
---
<span data-ttu-id="a4091-103">![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase erstklassige Betriebsprozesse] (media/upgrade-banner-op-excellence.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase erstklassige Betriebsprozesse")</span><span class="sxs-lookup"><span data-stu-id="a4091-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="a4091-104">Dieser Artikel ist Teil der erstklassige Betriebsprozesse Stufe des Ihre Upgrade Reise, wodurch gestartet wird, sobald Sie die Aktualisierung von Skype für Unternehmen auf Teams abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a4091-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="a4091-105">Quality of Experience überprüfen Guide</span><span class="sxs-lookup"><span data-stu-id="a4091-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="a4091-106">[Erleben Sie die Überprüfung Handbuch für Quality of](https://aka.ms/qerguide) enthält einen Satz von Aktivitäten, die bewerten und-Wartung Anleitungen in wichtige Bereiche, die am stärksten auf Verbessern der benutzererfahrung auswirken, wie im folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4091-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="a4091-107">![Die Schlüsselbereiche während einer Qualität Erfahrung Überarbeitung prüfen: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.] (media/plan-my-service-management-image2.png "Die Schlüsselbereiche während einer Qualität Erfahrung Überarbeitung prüfen: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.")</span><span class="sxs-lookup"><span data-stu-id="a4091-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="a4091-108">Ständig bewerten und Korrigieren von der Bereiche im Handbuch beschrieben, können Sie ihre potenzielle Möglichkeit beeinträchtigen Benutzererlebnis reduziert.</span><span class="sxs-lookup"><span data-stu-id="a4091-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="a4091-109">Die meisten bei einer Bereitstellung auftretenden Probleme mit der Benutzerfreundlichkeit können in die folgenden Kategorien eingeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="a4091-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="a4091-110">Unvollständige Firewall- oder Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="a4091-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="a4091-111">Schlechte WLAN-Abdeckung</span><span class="sxs-lookup"><span data-stu-id="a4091-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="a4091-112">Unzureichende Bandbreite</span><span class="sxs-lookup"><span data-stu-id="a4091-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="a4091-113">VPN</span><span class="sxs-lookup"><span data-stu-id="a4091-113">VPN</span></span>

- <span data-ttu-id="a4091-114">Verwendung nicht optimierter oder integrierter Audiogeräte</span><span class="sxs-lookup"><span data-stu-id="a4091-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="a4091-115">Problematische Subnetze oder Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="a4091-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="a4091-116">Die Informationen der Qualität der Erfahrung überprüfen Handbuchs behandelt Verwendung Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche beschrieben, mit Schwerpunkt auf Audio die Annahme und Auswirkungen auf die maximieren.</span><span class="sxs-lookup"><span data-stu-id="a4091-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="a4091-117">Alle zur Verbesserung der Audiowahrnehmung vorgenommenen Netzwerkoptimierungen äußern sich auch direkt als Verbesserungen bei der Video- und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="a4091-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="a4091-118">Es wird dringend empfohlen, dass am Anfang der Qualität "Champion" benennen.</span><span class="sxs-lookup"><span data-stu-id="a4091-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="a4091-119">Nach dem benannt wird, sollten sie beginnen mit der Inhalt die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide)vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="a4091-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
---
title: Quality of Experience überprüfen Guide - Microsoft-Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Aufgaben und Aktivitäten, die für die Qualität und zur Verwendung des Microsoft-Teams, Überwachung erforderlich
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42d48f9a6bd841ce2756e783e712ee01ed108c55
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862619"
---
<span data-ttu-id="36467-103">![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase erstklassige Betriebsprozesse] (media/upgrade-banner-op-excellence.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase erstklassige Betriebsprozesse")</span><span class="sxs-lookup"><span data-stu-id="36467-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="36467-104">Dieser Artikel ist Teil der erstklassige Betriebsprozesse Stufe des Ihre Upgrade Reise, wodurch gestartet wird, sobald Sie die Aktualisierung von Skype für Unternehmen auf Teams abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="36467-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="36467-105">Quality of Experience überprüfen Guide</span><span class="sxs-lookup"><span data-stu-id="36467-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="36467-106">[Erleben Sie die Überprüfung Handbuch für Quality of](https://aka.ms/qerguide) enthält einen Satz von Aktivitäten, die bewerten und-Wartung Anleitungen in wichtige Bereiche, die am stärksten auf Verbessern der benutzererfahrung auswirken, wie im folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36467-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="36467-107">![Die Schlüsselbereiche während einer Qualität Erfahrung Überarbeitung prüfen: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.] (media/plan-my-service-management-image2.png "Die Schlüsselbereiche während einer Qualität Erfahrung Überarbeitung prüfen: Audio, Zuverlässigkeit und Benutzer Umfrageergebnissen.")</span><span class="sxs-lookup"><span data-stu-id="36467-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="36467-108">Ständig bewerten und Korrigieren von der Bereiche im Handbuch beschrieben, können Sie ihre potenzielle Möglichkeit beeinträchtigen Benutzererlebnis reduziert.</span><span class="sxs-lookup"><span data-stu-id="36467-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="36467-109">Die meisten Benutzer-Erlebnis Probleme in einer Bereitstellung können in die folgenden Kategorien unterteilt werden:</span><span class="sxs-lookup"><span data-stu-id="36467-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="36467-110">Unvollständige Firewall oder der Proxyserver-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="36467-110">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="36467-111">Schlechte Wi-Fi-Abdeckung</span><span class="sxs-lookup"><span data-stu-id="36467-111">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="36467-112">Unzureichende Bandbreite</span><span class="sxs-lookup"><span data-stu-id="36467-112">Insufficient bandwidth</span></span>

-   <span data-ttu-id="36467-113">VPN</span><span class="sxs-lookup"><span data-stu-id="36467-113">VPN</span></span>

-   <span data-ttu-id="36467-114">Verwenden von nicht optimierte oder integrierte Audiogeräten</span><span class="sxs-lookup"><span data-stu-id="36467-114">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="36467-115">Problematisch Subnetze oder Netzwerkgeräte</span><span class="sxs-lookup"><span data-stu-id="36467-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="36467-116">Die Informationen der Qualität der Erfahrung überprüfen Handbuchs behandelt Verwendung Online aufrufen Quality Dashboard (CQD) als primäres Tool melden, und überprüfen Sie jeden dieser Bereiche beschrieben, mit Schwerpunkt auf Audio die Annahme und Auswirkungen auf die maximieren.</span><span class="sxs-lookup"><span data-stu-id="36467-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="36467-117">Versucht, das Netzwerk zur Verbesserung der Audioqualität Optimierungen übersetzt auch direkt in Verbesserungen bei video sowie die Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="36467-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="36467-118">Es wird dringend empfohlen, dass am Anfang der Qualität "Champion" benennen.</span><span class="sxs-lookup"><span data-stu-id="36467-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="36467-119">Nach dem benannt wird, sollten sie beginnen mit der Inhalt die [Erfahrung überprüfen Handbuch für Quality of](https://aka.ms/qerguide)vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="36467-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
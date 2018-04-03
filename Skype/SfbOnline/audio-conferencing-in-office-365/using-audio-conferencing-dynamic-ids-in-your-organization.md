---
title: Verwenden dynamische Audiokonferenzen-IDs in Ihrer Organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Der Audio-Konferenzdienst wird aktualisiert, um jeden Skype für Geschäfts- und Microsoft-Teams Besprechung mit anderen Konferenz-IDs bereitstellen. Dynamische Konferenz-IDs werden eine wesentliche Verbesserung über statische Konferenz-IDs, da sie bieten:'
ms.openlocfilehash: 418e6f486b8108791930c7843bfed8bdc56e83ef
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="c79d6-104">Verwenden dynamische Audiokonferenzen-IDs in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="c79d6-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="c79d6-105">Der Audio-Konferenzdienst wird aktualisiert, um jeden Skype für Geschäfts- und Microsoft-Teams Besprechung mit anderen Konferenz-IDs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c79d6-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="c79d6-106">Dynamische Konferenz-IDs werden eine wesentliche Verbesserung über statische Konferenz-IDs, da sie bieten:</span><span class="sxs-lookup"><span data-stu-id="c79d6-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="c79d6-107">**Erweiterte Sicherheit** Die Konferenz-IDs gelten nur für jede Skype für Business oder Microsoft-Teams Besprechung und werden beim Planen der Besprechung wird generiert.</span><span class="sxs-lookup"><span data-stu-id="c79d6-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="c79d6-108">**Eine bessere Erfahrung bei Back-to-Back- und Side-to-Side-Besprechungen** Besprechungen für einen einzelnen Organisator werden spezifische Einwahlinformationen zugewiesen. Hierdurch wird verhindert, dass die Telefonteilnehmer einer Besprechung mit den Teilnehmern einer anderen Besprechung vermischt werden, wenn die Besprechungen nah beieinander liegen.</span><span class="sxs-lookup"><span data-stu-id="c79d6-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="c79d6-109">**Nahtloser Übergang** Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert ist, funktionieren Besprechungen, die in Ihrer Organisation bereits mit statischen IDs geplant waren, auch weiterhin.</span><span class="sxs-lookup"><span data-stu-id="c79d6-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="c79d6-110">Dynamische IDs sind nur verfügbar für Benutzer, die für aktiviert sind ** Audio Conferencing ** und Microsoft als Anbieter von Audiokonferenzen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="c79d6-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="c79d6-111">Für Ihre Benutzer können Sie [Zuweisen von Microsoft als Audiokonferenzanbieter](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c79d6-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="c79d6-112">Welche Änderungen sehen die Benutzer in meiner Organisation?</span><span class="sxs-lookup"><span data-stu-id="c79d6-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="c79d6-113">Nachdem dynamische Konferenz-IDs für Ihre Organisation aktiviert wurden, neue Skype für Geschäftskunden und Microsoft-Teams, die Besprechung geplant ist, von Benutzern in Ihrer Organisation, die aktiviert sind, für die Audiokonferenz Konferenz-IDs verfügen, die von anderen werden die statische Konferenz-ID, die sie vor dem hatten.</span><span class="sxs-lookup"><span data-stu-id="c79d6-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="c79d6-114">Organisatoren statische wurden müssen vor der Konferenz-IDs erinnern Sie die Benutzer teilnehmen an einer Besprechung, die sie jetzt benötigen, verwenden eine neue Konferenz-ID in der Besprechung einladen, bevor er Beitritt zu können.</span><span class="sxs-lookup"><span data-stu-id="c79d6-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c79d6-115">Besprechungen, die von einem Benutzer mit statischen Konferenz IDs geplant wurden, bevor die Organisation IDs der statische Konferenz-IDs, damit sie weiterhin werden das Planen von Besprechungen ohne Einfluss haben weiterhin für dynamische Konferenz aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="c79d6-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="c79d6-116">Diese Beispiele zeigen Sie die neue Oberfläche für zwei Skype für Business Besprechungen, die vom gleichen Benutzer organisiert wurden, aber beide verfügen jetzt über zwei verschiedene Konferenz-IDs:</span><span class="sxs-lookup"><span data-stu-id="c79d6-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="c79d6-117">**Besprechung Nr. 1** wurde von 9:00 Uhr bis 10:00 Uhr angesetzt. Die Konferenz-ID lautet 93907123:</span><span class="sxs-lookup"><span data-stu-id="c79d6-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="c79d6-119">**Besprechung Nr. 2** wurde von demselben Benutzer von 10:00 Uhr bis 11:00 Uhr angesetzt. Die Konferenz-ID lautet 16353789:</span><span class="sxs-lookup"><span data-stu-id="c79d6-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="c79d6-121">See Also</span><span class="sxs-lookup"><span data-stu-id="c79d6-121">Related topics</span></span>

- [<span data-ttu-id="c79d6-122">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c79d6-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="c79d6-123">Add-On-Lizenzierung für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c79d6-123">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

---
title: Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informationen Sie zum Verwalten von Einstellungen für Teams live Ereignisse, die in Ihrer Organisation befinden.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94a167e8a929f2011ccaa773cd04d4e0ca6a2a0e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463668"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="8ebe6-103">Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8ebe6-103">Configure live event settings in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="8ebe6-104">Verwenden Sie Teams live Ereignisse Einstellungen zum Konfigurieren von Einstellungen für live Ereignisse, die gehalten werden in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="8ebe6-105">Sie können eine Support-URL einrichten und Konfigurieren eines Anbieters video Verteilung von Drittanbietern für.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="8ebe6-106">Diese Einstellungen gelten für alle live Ereignisse, die in Ihrer Organisation erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="8ebe6-107">Sie können diese Einstellungen in der Verwaltungskonsole von Microsoft-Teams auf einfache Weise verwalten.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8ebe6-108">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live Ereignisse Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="8ebe6-109">![Live-Ereignis-settings.png] (../media/teams-live-events-settings.png "Screenshot des Teams live Ereignisse Einstellungen, die Sie in der Microsoft-Teams-Verwaltungskonsole konfigurieren können")</span><span class="sxs-lookup"><span data-stu-id="8ebe6-109">![live-event-settings.png](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="8ebe6-110">Einrichten von Ereignis Support-URL</span><span class="sxs-lookup"><span data-stu-id="8ebe6-110">Set up event support URL</span></span>

<span data-ttu-id="8ebe6-111">Diese URL wird Live Ereignis Teilnehmer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="8ebe6-112">Fügen Sie die Support-URL für Ihre Organisation, um Teilnehmer eine Möglichkeit zum Kontaktieren des Supports während einer live-Ereignis übergeben.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Teams-Logo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="8ebe6-114">Verwenden das Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="8ebe6-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="8ebe6-115">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live-Ereignis Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="8ebe6-116">Geben Sie unter **URL unterstützen**Ihrer Organisation Support-URL ein.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="8ebe6-117">![Support-URL-Einstellung für live Ereignisse in der Verwaltungskonsole von Microsoft-Teams] (../media/teams-live-events-settings-supporturl.png "Screenshot der URL-Einstellung für Teams live Ereignisse unterstützen")</span><span class="sxs-lookup"><span data-stu-id="8ebe6-117">![Support URL setting for live events in the Microsoft Teams admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="8ebe6-118">Verwenden von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ebe6-118">Using Windows PowerShell</span></span>
<span data-ttu-id="8ebe6-119">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="8ebe6-119">Run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="8ebe6-120">Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8ebe6-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="8ebe6-121">Konfigurieren eines Anbieters Drittanbieter-video-Verteilung</span><span class="sxs-lookup"><span data-stu-id="8ebe6-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="8ebe6-122">Wenn Sie erworben und eine softwarelösung definiert Netzwerk (SDN) oder Enterprise Content Delivery Network (eCDN) Lösung über einen Microsoft video Partner einrichten, konfigurieren Sie den Anbieter für live Ereignisse im Teams.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Teams-Logo-30x30.png](../media/teams-logo-30x30.png) <span data-ttu-id="8ebe6-124">Verwenden das Microsoft-Teams, Administrationscenter</span><span class="sxs-lookup"><span data-stu-id="8ebe6-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="8ebe6-125">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Live-Ereignis Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="8ebe6-126">Führen Sie unter **video Verteilung Drittanbieter**die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8ebe6-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="8ebe6-127">![Drittanbieter - video Verteilung Anbieter Einstellungen in der Verwaltungskonsole von Microsoft-Teams] (../media/teams-live-events-settings-distribution-provider.png "Screenshot der Anbieter video Verteilung von Drittanbieter - Einstellungen für live Ereignisse")</span><span class="sxs-lookup"><span data-stu-id="8ebe6-127">![Third-party video distribution provider settings in the Microsoft Teams admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="8ebe6-128">**Verwenden Sie einen Anbieter für Drittanbieter - Verteilung** Deaktivieren Sie diese Aktivieren der video Verteilung von Drittanbieter-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="8ebe6-129">**Name des Anbieters SDN** Wählen Sie den Anbieter, den Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="8ebe6-130">**Anbieter License Product key** Geben Sie die Lizenz-ID, die Sie von Ihrem Anbieter Kontakt erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="8ebe6-131">**URL der SDN-API-Vorlage** Geben Sie die URL der API-Vorlage, die Sie von Ihrem Anbieter Kontakt erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="8ebe6-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="8ebe6-132">Verwenden von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ebe6-132">Using Windows PowerShell</span></span>
<span data-ttu-id="8ebe6-133">Möchten Sie die ID oder API-Lizenztoken und die API-Vorlage von Ihrem Anbieter Kontakt erhalten, und führen Sie eine der folgenden, abhängig von des verwendeten Anbieters:</span><span class="sxs-lookup"><span data-stu-id="8ebe6-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="8ebe6-134">**Struktur**</span><span class="sxs-lookup"><span data-stu-id="8ebe6-134">**Hive**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="8ebe6-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="8ebe6-135">**Kollective**</span></span> 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="8ebe6-136">Weitere Informationen finden Sie unter [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8ebe6-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="8ebe6-137">Wenn Sie planen, live Ereignisse erstellen, die externe Encoder verwenden, müssen Sie auch so [Konfigurieren Sie Ihren eCDN-Anbieter Microsoft-Stream](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="8ebe6-137">If you plan to create live events that use external encoders, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="8ebe6-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8ebe6-138">Related topics</span></span>
- [<span data-ttu-id="8ebe6-139">Was sind Teams live Ereignisse?</span><span class="sxs-lookup"><span data-stu-id="8ebe6-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="8ebe6-140">Planen von Teams live-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8ebe6-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="8ebe6-141">Einrichten von für Teams live Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8ebe6-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
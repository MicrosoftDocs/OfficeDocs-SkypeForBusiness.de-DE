---
title: Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie Einstellungen für Live-Ereignisse von Teams verwalten, die in Ihrer Organisation gespeichert sind.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cdfd1bc832827dbcf48e82a49ed4d02c38116bb
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827143"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="6c066-103">Konfigurieren von Einstellungen für Live-Ereignisse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c066-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="6c066-104">Verwenden Sie die Einstellungen für Live Ereignisse von Teams, um Einstellungen für Live Ereignisse zu konfigurieren, die in Ihrer Organisation stattfinden.</span><span class="sxs-lookup"><span data-stu-id="6c066-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="6c066-105">Sie können eine Support-URL einrichten und einen Drittanbieter für Videoverteilung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c066-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="6c066-106">Diese Einstellungen gelten für alle Live Ereignisse, die in Ihrer Organisation erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6c066-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="6c066-107">Sie können diese Einstellungen im Microsoft Teams Admin Center ganz einfach verwalten.</span><span class="sxs-lookup"><span data-stu-id="6c066-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6c066-108">Wechseln Sie in der linken Navigationsleiste zu **Besprechungen** > **Live Events-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="6c066-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="6c066-109">![Screenshot der Einstellungen für Live-Events in Teams](../media/teams-live-events-settings.png "Screenshot der Einstellungen für Teams-Live Ereignisse, die Sie im Microsoft Teams Admin Center konfigurieren können")</span><span class="sxs-lookup"><span data-stu-id="6c066-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="6c066-110">Einrichten der URL für die Ereignisunterstützung</span><span class="sxs-lookup"><span data-stu-id="6c066-110">Set up event support URL</span></span>

<span data-ttu-id="6c066-111">Diese URL wird für Live-Event-Teilnehmer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c066-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="6c066-112">Fügen Sie die Support-URL für Ihre Organisation hinzu, um Teilnehmern eine Möglichkeit zu geben, den Support während eines Liveereignisses zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="6c066-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) <span data-ttu-id="6c066-114">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="6c066-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6c066-115">Wechseln Sie in der linken Navigationsleiste zu**Live-Ereigniseinstellungen**für **Besprechungen** > .</span><span class="sxs-lookup"><span data-stu-id="6c066-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="6c066-116">Geben Sie unter **Support-URL**die Support-URL Ihrer Organisation ein.</span><span class="sxs-lookup"><span data-stu-id="6c066-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="6c066-117">![Support-URL-Einstellung für Live-Ereignisse im Admin Center](../media/teams-live-events-settings-supporturl.png "Screenshot der Support-URL-Einstellung für Live-Events in Teams")</span><span class="sxs-lookup"><span data-stu-id="6c066-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="6c066-118">Verwenden von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c066-118">Using Windows PowerShell</span></span>
<span data-ttu-id="6c066-119">Führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="6c066-119">Run the following:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="6c066-120">Weitere Informationen finden Sie unter [Satz-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c066-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="6c066-121">Konfigurieren eines Drittanbieters für Videoverteilung</span><span class="sxs-lookup"><span data-stu-id="6c066-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="6c066-122">Wenn Sie eine Lösung für Software Defined Network (SDN) oder Enterprise Content Delivery Network (ECDN) über einen Microsoft Video Delivery-Partner erworben und eingerichtet haben, konfigurieren Sie den Anbieter für Live Ereignisse in Teams.</span><span class="sxs-lookup"><span data-stu-id="6c066-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Ein Symbol mit dem Microsoft Teams-Logo](../media/teams-logo-30x30.png) <span data-ttu-id="6c066-124">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="6c066-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6c066-125">Wechseln Sie in der linken Navigationsleiste zu**Live-Ereigniseinstellungen**für **Besprechungen** > .</span><span class="sxs-lookup"><span data-stu-id="6c066-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="6c066-126">Führen Sie unter **Anbieter von Video Verteilern von Drittanbietern**die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6c066-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="6c066-127">![Einstellungen für Video Verteilungs Anbieter von Drittanbietern im Admin Center](../media/teams-live-events-settings-distribution-provider.png "Screenshot der Einstellungen des Drittanbieters für Videoverteiler für Live Ereignisse")</span><span class="sxs-lookup"><span data-stu-id="6c066-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="6c066-128">**Verwenden eines Dritt** Anbieters für die Verteilung Aktivieren Sie diese Option, um den Video Verteilungs Anbieter eines Drittanbieters zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6c066-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="6c066-129">**Sdn-Anbietername** Wählen Sie den von Ihnen verwendeten Anbieter aus.</span><span class="sxs-lookup"><span data-stu-id="6c066-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="6c066-130">**Anbieter-Lizenzschlüssel** Geben Sie die Lizenz-ID ein, die Sie von Ihrem Anbieter Kontakt erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="6c066-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="6c066-131">**Sdn-API-Vorlagen-URL** Geben Sie die API-Vorlagen-URL ein, die Sie von Ihrem Anbieter Kontakt erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="6c066-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="6c066-132">Verwenden von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c066-132">Using Windows PowerShell</span></span>
<span data-ttu-id="6c066-133">Rufen Sie die Lizenz-ID oder das API-Token und die API-Vorlage von Ihrem Anbieter Kontakt ab, und führen Sie je nach verwendetem Anbieter eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6c066-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="6c066-134">**Struktur**</span><span class="sxs-lookup"><span data-stu-id="6c066-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="6c066-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="6c066-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="6c066-136">Weitere Informationen finden Sie unter [Satz-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c066-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="6c066-137">Wenn Sie planen, Live Ereignisse mithilfe einer externen APP oder eines externen Geräts zu erstellen, müssen Sie auch [ihren ECDN-Anbieter mit Microsoft Stream konfigurieren](https://docs.microsoft.com/stream/network-caching).</span><span class="sxs-lookup"><span data-stu-id="6c066-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="6c066-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6c066-138">Related topics</span></span>
- [<span data-ttu-id="6c066-139">Was sind Teams-Liveereignisse?</span><span class="sxs-lookup"><span data-stu-id="6c066-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="6c066-140">Planen von Teams-Liveereignissen</span><span class="sxs-lookup"><span data-stu-id="6c066-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="6c066-141">Einrichten von Teams-Liveereignissen</span><span class="sxs-lookup"><span data-stu-id="6c066-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
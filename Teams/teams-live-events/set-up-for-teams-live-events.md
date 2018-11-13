---
title: Einrichten von für live Ereignisse in der Microsoft-Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Informationen Sie zu den Schritten für Ereignisse in der Microsoft-Teams, einschließlich der Vorbereitung Ihres Netzwerks Zuweisen von Lizenzen, Aktivieren von live-Ereignis für Benutzer planen und Einrichten von einem Anbieter eCDN live einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296380"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="520df-103">Einrichten von für live Ereignisse in der Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="520df-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="520df-104">Beim Einrichten für live Ereignisse sind mehrere Schritte, die Sie durchführen müssen:</span><span class="sxs-lookup"><span data-stu-id="520df-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="520df-105">Schritt 1: Richten Sie Ihres Netzwerks für live Ereignisse in der Microsoft-Teams ein</span><span class="sxs-lookup"><span data-stu-id="520df-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="520df-106">Die Schnellstart live Ereignisse müssen Sie zum [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="520df-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="520df-107">Schritt 2: Abrufen und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="520df-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="520df-108">Sicherzustellen, dass der richtige Lizenz Zuordnungen für [Erstellen und Planen Sie live Ereignisse zu können?](#who-can-create-and-schedule-live-events) und [können, die live Ereignisse überwachen?](#who-can-watch-live-events).</span><span class="sxs-lookup"><span data-stu-id="520df-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="520df-109">Schritt 3: Aktivieren von live-Ereignis planen für Benutzer</span><span class="sxs-lookup"><span data-stu-id="520df-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="520df-110">Planen von Live-Ereignis ist standardmäßig aktiviert, für Teams Benutzer, aber Sie möchten Benutzer externe Encoder Ereignisse planen, sind zusätzliche Schritte, die Sie durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="520df-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="520df-111">Schnellstart-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="520df-111">For quick start events</span></span>
<span data-ttu-id="520df-112">Verwenden Sie die Einstellung *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in PowerShell Teams können Sie steuern, ob der Benutzer live Ereignisse in Teams oder nicht erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="520df-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="520df-113">Weitere Informationen finden Sie Informationen zum Verwalten von TeamsMeetingBroadcastPolicy [hier](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="520df-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="520df-114">Wenn Sie eine benutzerdefinierte Richtlinie an, die Benutzern zugewiesen zugewiesen haben, erhalten die Benutzer die *globale* Richtlinie ein, die Aufzeichnung, die in der Standardeinstellung aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="520df-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="520df-115">Stellen Sie sicher, dass *AllowBroadcastScheduling* -Parameter auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="520df-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="520df-116">Weisen Sie den Benutzer die *globale* Richtlinie, ausführen:</span><span class="sxs-lookup"><span data-stu-id="520df-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="520df-117">Benutzerszenarien</span><span class="sxs-lookup"><span data-stu-id="520df-117">User scenarios</span></span>
<span data-ttu-id="520df-118">**Sollen alle Benutzer in Ihrem Unternehmen live Ereignisse erstellen können.**</span><span class="sxs-lookup"><span data-stu-id="520df-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="520df-119">Wenn Benutzer die *globalen* Richtlinie zugewiesen sind, ausführen, und stellen Sie sicher, *AllowBroadcastScheduling* \* auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="520df-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="520df-120">Wenn der Benutzer eine Richtlinie als die *globale* Richtlinie zugewiesen sind, führen Sie folgenden Befehl ein, und stellen Sie sicher, dass *- AllowBroadcastScheduling* auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="520df-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="520df-121">**Live-Ereignis Planung in Ihrer Organisation 100 % deaktiviert werden soll.**</span><span class="sxs-lookup"><span data-stu-id="520df-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="520df-122">Führen Sie deaktivieren broadcast planen:</span><span class="sxs-lookup"><span data-stu-id="520df-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="520df-123">Die *globale* Richtlinie, führen weisen Sie alle Benutzer in Ihrer Organisation zu:</span><span class="sxs-lookup"><span data-stu-id="520df-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="520df-124">**Sie möchten eine große Anzahl von Benutzern live Ereignisse erstellen können, aber verhindern, dass eine Gruppe von Benutzern erstellen möchten.**</span><span class="sxs-lookup"><span data-stu-id="520df-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="520df-125">Weisen Sie die *globale* Richtlinie mit dem **Grant-CsTeamsMeetingBroadcastPolicy** für einige Benutzer (, die Sie aktivieren möchten), aber zuerst führen Sie folgenden Befehl, und stellen Sie sicher, dass *AllowBroadcastScheduling* auf *True*festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="520df-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="520df-126">Weisen Sie mindestens ein Benutzer die *globale* Richtlinie, ausführen:</span><span class="sxs-lookup"><span data-stu-id="520df-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="520df-127">Erstellen und Zuweisen einer Richtlinie für die Deaktivierung planen, mit dem Cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** an andere Benutzer ein (deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="520df-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="520df-128">Erstellen Sie die neue Richtlinie deaktiviert, ausführen:</span><span class="sxs-lookup"><span data-stu-id="520df-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="520df-129">Deaktivieren Sie planen, ausführen:</span><span class="sxs-lookup"><span data-stu-id="520df-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="520df-130">Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:</span><span class="sxs-lookup"><span data-stu-id="520df-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="520df-131">**Sie live Ereignisse für eine große Anzahl von Benutzern deaktiviert werden soll, jedoch eine Gruppe von Benutzern, deren Erstellung zu zulassen möchten.**</span><span class="sxs-lookup"><span data-stu-id="520df-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="520df-132">Führen Sie deaktivieren broadcast planen:</span><span class="sxs-lookup"><span data-stu-id="520df-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="520df-133">Die *globale* Richtlinie, führen Sie anschließend weisen Sie diese Benutzer zu:</span><span class="sxs-lookup"><span data-stu-id="520df-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="520df-134">Erstellen und Zuweisen einer Richtlinie für die Aktivierung planen, ausführen:</span><span class="sxs-lookup"><span data-stu-id="520df-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="520df-135">Führen Sie Zeitplan aktivieren:</span><span class="sxs-lookup"><span data-stu-id="520df-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="520df-136">Diese Richtlinie, und führen Sie dann weisen Sie Benutzer zu:</span><span class="sxs-lookup"><span data-stu-id="520df-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="520df-137">Für externe Encoder-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="520df-137">For external encoder events</span></span>
<span data-ttu-id="520df-138">Sie müssen Folgendes ein, um die Planung für diese Benutzer live Ereignis zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="520df-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="520df-139">Schritt 1: Aktivieren von Microsoft-Stream für Benutzer in Ihrer Organisation \*\*</span><span class="sxs-lookup"><span data-stu-id="520df-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="520df-140">Microsoft-Stream steht als Teil von Office 365-Abonnements zu auswählbaren oder als eigenständigen Dienst.</span><span class="sxs-lookup"><span data-stu-id="520df-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="520df-141">Einzelheiten finden Sie unter [Stream Lizenzierung Overview](https://docs.microsoft.com/stream/license-overview) .</span><span class="sxs-lookup"><span data-stu-id="520df-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="520df-142">! [HINWEIS] Microsoft-Stream ist nicht in Business Essentials oder Business Premium-Plänen enthalten.</span><span class="sxs-lookup"><span data-stu-id="520df-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="520df-143">Erfahren Sie mehr dazu, wie Sie [Lizenzen für Benutzer in Office 365 zuweisen](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , damit Benutzer Microsoft Stream zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="520df-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="520df-144">Stellen Sie sicher, dass Microsoft-Stream für die Benutzer nicht ausgeschlossen wird, wie in [diesem Artikel](https://docs.microsoft.com/stream/disable-user-organization)definiert.</span><span class="sxs-lookup"><span data-stu-id="520df-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="520df-145">Schritt 2: Stellen Sie sicher, dass Benutzer über Berechtigungen zum Erstellen live-Ereignis in Microsoft Stream \*\* verfügen</span><span class="sxs-lookup"><span data-stu-id="520df-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="520df-146">In der Standardeinstellung können Administratoren externe Encoder live Ereignisse erstellen.</span><span class="sxs-lookup"><span data-stu-id="520df-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="520df-147">Microsoft-Stream-Administrator können in Stream-Objekt [für die Erstellung des live-Ereignis weitere Benutzer aktivieren](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) .</span><span class="sxs-lookup"><span data-stu-id="520df-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="520df-148">Schritt 3: Stellen Sie sicher, die Organisatoren die Unternehmensrichtlinie festlegen, indem Stream Admin \*\* zugestimmt haben live-Ereignis</span><span class="sxs-lookup"><span data-stu-id="520df-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="520df-149">Wenn ein Microsoft-Stream-Administrator [eine Unternehmensrichtlinie Richtlinien einrichten hat](https://docs.microsoft.com/stream/company-policy-and-consent) und Mitarbeiter dieser Richtlinie zu akzeptieren erfordert, bevor das Speichern von Inhalten, klicken Sie dann müssen Benutzer vor dem Erstellen einer live-Ereignis (mit der externen Encoder Produktion) in Teams.</span><span class="sxs-lookup"><span data-stu-id="520df-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="520df-150">Sicherstellen Sie bevor Sie Einführung das Feature live Ereignisse in der Organisation, dass Benutzer, die diese live Ereignisse erstellen werden die Richtlinie zugestimmt haben.</span><span class="sxs-lookup"><span data-stu-id="520df-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="520df-151">Schritt 4: Einrichten von eCDN-Anbieter für live Ereignisse in der Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="520df-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="520df-152">Wiedergabe von Videos live-Ereignis verwendet adaptive Bitrate (ABR) streaming, aber es ist eine Unicast-Stream, was bedeutet, dass jeder Viewer eigene Videostream aus dem Internet abrufen ist.</span><span class="sxs-lookup"><span data-stu-id="520df-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="520df-153">Für live Ereignisse oder Videos an große Teile Ihrer Organisation gesendet kann sehr viel Internetbandbreite Identitätsdaten durch Viewer handeln.</span><span class="sxs-lookup"><span data-stu-id="520df-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="520df-154">Für Organisationen, die diesen Internet-Datenverkehr für live Ereignisse reduzieren möchten, vertrauenswürdige live Ereignisse, die von Microsoft Solutions integriert sind video Delivery Partner, anbietet Software Netzwerke (SDNs) oder Enterprise Content Delivery Networks (eCDNs) definiert.</span><span class="sxs-lookup"><span data-stu-id="520df-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="520df-155">Diese SDN / eCDN Plattformen können Organisationen zum Optimieren der Netzwerkbandbreite ohne Beeinträchtigung Endbenutzer Erfahrungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="520df-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="520df-156">Unsere Partner helfen, eine skalierbare und effiziente video Verteilung über Ihr Unternehmensnetzwerk zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="520df-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="520df-157">**Purchase & Setup Ihrer Lösung außerhalb von Microsoft-Teams,** Hier erhalten Sie Hilfe Experten video Übermittlung durch die Nutzung von Microsoft vertrauenswürdigen video Delivery Partner skalieren.</span><span class="sxs-lookup"><span data-stu-id="520df-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="520df-158">Bevor Sie einen video Delivery-Anbieter mit Teams aktivieren können, müssen Sie erwerben und setup die Lösung SDN/eCDN äußeren und getrennt von Teams.</span><span class="sxs-lookup"><span data-stu-id="520df-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="520df-159">SDN/eCDN Folgendes können bereits integriert werden und Setup mit Microsoft-Streams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="520df-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="520df-160">**Streaming Struktur** bietet eine einfache und leistungsstarke Lösung für die Live- und on-Demand Enterprise video Verteilung.</span><span class="sxs-lookup"><span data-stu-id="520df-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="520df-161">Struktur ist eine softwarebasierte Lösung, die erfordert keine zusätzliche Hardware oder Bandbreite und auf sichere Weise Tausende von gleichzeitigen video Viewer ohne Auswirkung auf das Netzwerk zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="520df-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="520df-162">Für Kunden, die zum Verständnis, dass das Video Auswirkung in ihrem Netzwerk vor dem Kauf einer Lösung SDN/eCDN hat bietet Streaming Struktur auch eine browserbasierte Analytics Lösung zur Microsoft-Kunden.</span><span class="sxs-lookup"><span data-stu-id="520df-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="520df-163">[Erfahren Sie mehr](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span><span class="sxs-lookup"><span data-stu-id="520df-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="520df-164">**Kollective** ist eine Cloud-basierten, intelligente Peers Verteilung Plattform, die nutzt die vorhandene Netzwerkinfrastruktur zum Übermitteln von Inhalten, in vielen Formen, (live Videostreams, bei Bedarf Video, Softwareupdates, Sicherheitspatches usw.), schneller zuverlässig und mit weniger Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="520df-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="520df-165">Unsere sichere Plattform ist vertrauenswürdig, von der weltweit größten Finanzinstituten und mit keine zusätzliche Hardware, Installation und Wartung einfach sind.</span><span class="sxs-lookup"><span data-stu-id="520df-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="520df-166">[Erfahren Sie mehr](http://www.kollective.com).</span><span class="sxs-lookup"><span data-stu-id="520df-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="520df-167">**Lernen OmniCache** ermöglicht die Verteilung der nächsten Generation Netzwerk und sorgt für nahtlose Bereitstellung von Videoinhalten auf globale WANs, Netzwerkbandbreite zu optimieren und unterstützen erfolgreiches Ereignis live Übertragungen und on-Demand Ereignis Hersteller helfen Streaming.</span><span class="sxs-lookup"><span data-stu-id="520df-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="520df-168">Die Unterstützung für lernen OmniCache Schnellstart live Ereignisse wird in Kürze bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="520df-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="520df-169">[Erfahren Sie mehr](http://www.ramp.com).</span><span class="sxs-lookup"><span data-stu-id="520df-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="520df-170">Ihre Lösung gewählten eCDN unterliegt den ausgewählten **3. Anbieters Bedingungen Service und der Datenschutzrichtlinie**, Ihre Verwendung des Anbieters eCDN Lösung, welche wird steuert.</span><span class="sxs-lookup"><span data-stu-id="520df-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="520df-171">Ihre Verwendung des Anbieters eCDN Lösung werden nicht unter der Microsoft Volume licensing Begriffe oder Online Services-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="520df-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="520df-172">Wenn Sie nicht den **3. Anbieters Begriffe**zustimmen, aktivieren Sie dann nicht die eCDN-Lösung in Teams.</span><span class="sxs-lookup"><span data-stu-id="520df-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="520df-173">**Richten Sie ein eCDN für "Schnellstart" live Ereignisse** Sie können eCDN-Anbieter für live Ereignisse in Teams von PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="520df-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="520df-174">Ein einzelnes eCDN Anbieter kann für Ihre Organisation konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="520df-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="520df-175">***Struktur*** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="520df-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="520df-176">Erhalten Sie zuerst die Lizenz-ID und API-Vorlagen-URL aus der Struktur Kontakt führen Sie die folgenden:</span><span class="sxs-lookup"><span data-stu-id="520df-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="520df-177">***Kollective*** [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) -PowerShell-Cmdlets können Sie eCDN Anbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="520df-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="520df-178">Zunächst erhalten Sie das Token API und die URL der API-Vorlage aus dem Kollective Kontakt, und führen Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="520df-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="520df-179">**Richten Sie ein eCDN für "Externe Encoder" live-Ereignisse**</span><span class="sxs-lookup"><span data-stu-id="520df-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="520df-180">Wenn Sie planen, live Ereignisse erstellen, die externe Encoder verwenden, müssen Sie ebenfalls [Konfigurieren des Anbieters eCDN mit Microsoft-Stream](https://docs.microsoft.com/stream/network-caching) .</span><span class="sxs-lookup"><span data-stu-id="520df-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="520df-181">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="520df-181">Next steps</span></span>
<span data-ttu-id="520df-182">Wechseln Sie zur [Konfigurieren Teams live Ereignisse](configure-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="520df-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>

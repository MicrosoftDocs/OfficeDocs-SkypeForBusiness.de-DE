---
title: Einrichten von Cloud-Video-Interop für Microsoft-Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: In diesem Artikel wird erläutert, wie Sie planen und Einrichten von Cloud-Video-Interop für Benutzer in Ihrer Organisation können.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2090036aa5e1a05e46581d365d9b6b4aeb94b32
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294136"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="d351d-103">Einrichten von Cloud-Video-Interop für Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="d351d-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="d351d-104">Nachdem Sie [auf Ihren Partnern Cloud Video Interop ausgewählt](cloud-video-interop.md)haben, müssen Sie der Planung Ihrer Bereitstellung, Get mit provisioning Details und Partner mandantenschlüssel und Zustimmung der video Interop-App in Ihrer Organisation einrichten.</span><span class="sxs-lookup"><span data-stu-id="d351d-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="d351d-105">Im folgende Diagramm wird das Verfahren erläutert.</span><span class="sxs-lookup"><span data-stu-id="d351d-105">The following diagram outlines the process.</span></span> 

![CVI in Ihrer Organisation bereitstellen.](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="d351d-107">Planen</span><span class="sxs-lookup"><span data-stu-id="d351d-107">Plan</span></span>

<span data-ttu-id="d351d-108">Informationen zum Identifizieren eines Partners oder Partner für die Verwendung in Ihrer Organisation finden Sie unter [Cloud-Video-Interop für Microsoft-Teams](cloud-video-interop.md) .</span><span class="sxs-lookup"><span data-stu-id="d351d-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="d351d-109">Planen der Benutzer basierte/gleichzeitigen/Site breit-Aktivierung:</span><span class="sxs-lookup"><span data-stu-id="d351d-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="d351d-110">Wählen Sie für die Verwendung ein Bereitstellungsmodells Modell/gehostet</span><span class="sxs-lookup"><span data-stu-id="d351d-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="d351d-111">Wählen Sie den Lizenz Plan ideal für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="d351d-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="d351d-112">Planen der Kapazität von virtuellen Maschinen ist, dass Sie Ihr video-Infrastruktur gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="d351d-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="d351d-113">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d351d-113">Configure</span></span> 

<span data-ttu-id="d351d-114">Gehen Sie folgendermaßen vor, um Cloud Video Interop zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d351d-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="d351d-115">Abrufen von Konfigurationsinformationen von Partner/Partner haben Sie ausgewählte (mandantenschlüssel, AppIds...).</span><span class="sxs-lookup"><span data-stu-id="d351d-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="d351d-116">Sie können eine oder mehrere Interop-videopartnern in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="d351d-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="d351d-117">Stellen Sie sicher, dass das Netzwerk ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d351d-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="d351d-118">Konfigurieren Sie Ihrer Standards basierende video Firewall für Perimeter Network durchqueren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d351d-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="d351d-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d351d-119">For example:</span></span> 
    - <span data-ttu-id="d351d-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="d351d-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="d351d-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="d351d-121">Polycom RPAD</span></span>

3. <span data-ttu-id="d351d-122">Konfigurieren von integrierten Räumen mit Exchange und OTD.</span><span class="sxs-lookup"><span data-stu-id="d351d-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="d351d-123">In den meisten Fällen zusätzliche Relay eingerichtet werden müssen und in Ihrer Umgebung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d351d-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="d351d-124">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="d351d-124">Provision</span></span>
 
<span data-ttu-id="d351d-125">Die Mandanten-Taste wird der Client mit dem Dienst Partner sein.</span><span class="sxs-lookup"><span data-stu-id="d351d-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="d351d-126">Im folgenden Beispiel wird die 813878896@t.plcm.vc die Mandanten-Taste.</span><span class="sxs-lookup"><span data-stu-id="d351d-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Beispiel zu einem Mandanten](media/tenant-key-example.png) 

<span data-ttu-id="d351d-128">Sie müssen zum Ausführen der folgenden Cmdlets zum Bereitstellen des Mandanten-Schlüssels, und auch die Auswahl von Benutzern oder der gesamten Organisation Besprechungen mit video interop Koordinaten erstellen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d351d-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="d351d-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft stellt vorab erstellte Richtlinien für alle unsere unterstützte Partner, mit denen Sie die Partner für video Interop Cloud zu verwendenden festlegt.</span><span class="sxs-lookup"><span data-stu-id="d351d-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="d351d-130">Mit diesem Cmdlet können Sie die Überprüfung vor dem erstellten Richtlinien zu identifizieren, die Sie in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d351d-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="d351d-131">Sie können eine oder mehrere Benutzer mit dem Cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen diese Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d351d-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="d351d-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* Das Cmdlet Grant-CsTeamsVideoInteropServicePolicy können Sie eine vorab erstellte Richtlinie für die Verwendung in Ihrer Organisation zuweisen, oder weisen die Richtlinie auf bestimmte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d351d-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="d351d-133">\*\* [Neue CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Verwenden Sie das New-CsVideoInteropServiceProvider zum Angeben von Informationen zu unterstützten CVI Partner, dass Ihre Organisation verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d351d-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="d351d-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Verwenden Sie das Set-CsVideoInteropServiceProvider, um Informationen zu unterstützten CVI Partner zu aktualisieren, die Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d351d-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="d351d-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Rufen Sie alle Anbieter, die konfiguriert wurden, für die Verwendung innerhalb der Organisation.</span><span class="sxs-lookup"><span data-stu-id="d351d-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="d351d-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Verwenden Sie Remove-CsVideoInteropServiceProvider, um alle für Anbieterinformationen zu einem Anbieter zu entfernen, die Ihre Organisation nicht mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="d351d-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="d351d-137">Zustimmung</span><span class="sxs-lookup"><span data-stu-id="d351d-137">Consent</span></span>

<span data-ttu-id="d351d-138">Sie benötigen die Berechtigung Zustimmung für die Geräte für Videokonferenzen (VTCs) zur Teilnahme an Ihre Organisationen Besprechungen über die Partner-Dienst bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d351d-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="d351d-139">Dieses Consent Link wird auch von Ihrem Partner bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d351d-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="d351d-140">Wenn diese Schritte abgeschlossen haben, müssen die Benutzer einzeln über das Cmdlet Grant oberhalb oder alle Benutzer in der Organisation aktiviert sind, wenn Sie der Mandanten aktiviert ist, VTC Koordinaten in alle Teams Besprechungen, die sie planen.</span><span class="sxs-lookup"><span data-stu-id="d351d-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="d351d-141">Alle VTC kann diese über den entsprechenden Koordinaten Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="d351d-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="d351d-142">Name</span><span class="sxs-lookup"><span data-stu-id="d351d-142">Name</span></span>|<span data-ttu-id="d351d-143">Kurzbeschreibung der Anwendung die Berechtigung</span><span class="sxs-lookup"><span data-stu-id="d351d-143">Application Permission Short Description</span></span>| <span data-ttu-id="d351d-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d351d-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="d351d-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="d351d-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="d351d-146">Besuchen Sie Gruppe Anrufe und Besprechungen als einer app (Preview)</span><span class="sxs-lookup"><span data-stu-id="d351d-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="d351d-147">Die app in Ihrer Organisation, ohne dass ein angemeldeten Benutzer Gruppe Anrufe und geplante Besprechungen beitreten können.</span><span class="sxs-lookup"><span data-stu-id="d351d-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="d351d-148">Die app wird mit den Berechtigungen eines Benutzers Directory bei Besprechungen in Ihrem Mandanten verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="d351d-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="d351d-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="d351d-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="d351d-150">Besuchen Sie Gruppe Anrufe und Besprechungen als Gast (Preview)</span><span class="sxs-lookup"><span data-stu-id="d351d-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="d351d-151">Die app anonym Gruppe Anrufe und geplante Besprechungen in Ihrer Organisation, ohne dass ein angemeldeten Benutzer beitreten können.</span><span class="sxs-lookup"><span data-stu-id="d351d-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="d351d-152">Die app wird als Gast bei Besprechungen in Ihrem Mandanten verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="d351d-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="d351d-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="d351d-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="d351d-154">Access Mediendatenströme im Gespräch als einer app (Preview)</span><span class="sxs-lookup"><span data-stu-id="d351d-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="d351d-155">Ermöglicht die direkten Zugriff auf Mediendatenströme im Gespräch, ohne dass ein angemeldeten Benutzer erhalten-app.</span><span class="sxs-lookup"><span data-stu-id="d351d-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="d351d-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="d351d-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="d351d-157">Lesen Online-Besprechungsdetails (Preview)</span><span class="sxs-lookup"><span data-stu-id="d351d-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="d351d-158">Die app in Ihrer Organisation, ohne dass ein angemeldeten Benutzer Online Besprechungsdetails lesen können.</span><span class="sxs-lookup"><span data-stu-id="d351d-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="d351d-159">Zeitplan</span><span class="sxs-lookup"><span data-stu-id="d351d-159">Schedule</span></span>

<span data-ttu-id="d351d-160">Im nächsten Schritt planen Sie Teams-Besprechung mit video interop Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="d351d-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="d351d-161">Der aktivierte Benutzer kann Teams Besprechungen über planen:</span><span class="sxs-lookup"><span data-stu-id="d351d-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="d351d-162">Teams Meeting-add-in für Outlook</span><span class="sxs-lookup"><span data-stu-id="d351d-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="d351d-163">Teams Client Desktop- und mobilen</span><span class="sxs-lookup"><span data-stu-id="d351d-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="d351d-164">Join</span><span class="sxs-lookup"><span data-stu-id="d351d-164">Join</span></span>

<span data-ttu-id="d351d-165">Sie können Teams Besprechungen mit Ihren Geräten VTC teilnehmen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d351d-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="d351d-166">IVR (Interactive Voice Response)</span><span class="sxs-lookup"><span data-stu-id="d351d-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="d351d-167">Sie können mithilfe der tenantkey@domain des Partners IVR im einwählen.</span><span class="sxs-lookup"><span data-stu-id="d351d-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="d351d-168">Sobald Sie den IVR-Partner sind, werden Sie aufgefordert, zur Eingabe der ConferenceId VTC dann Sie die Besprechung Teams eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="d351d-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="d351d-169">Durchwahl</span><span class="sxs-lookup"><span data-stu-id="d351d-169">Direct dial</span></span>
    - <span data-ttu-id="d351d-170">Sie können direkt in die Besprechung Teams einwählen, ohne Interaktion mit der Partner IVR mit der Durchwahl-Funktion unter Verwendung der vollständigen Zeichenfolge des Tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="d351d-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="d351d-171">One Touch-Wählplan</span><span class="sxs-lookup"><span data-stu-id="d351d-171">One-touch dial</span></span>
    - <span data-ttu-id="d351d-172">Wenn Sie eine integrierte Teams Platz haben, können Sie einem Tastendruck Dial Funktionen von Ihrem Partner (ohne Geben Sie eine beliebige Zeichenfolge Dial) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d351d-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="d351d-173">Bitten Sie schließlich Teams Benutzer in Ihre Besprechungen mit der Freigabe von audio und video sowie Content.</span><span class="sxs-lookup"><span data-stu-id="d351d-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
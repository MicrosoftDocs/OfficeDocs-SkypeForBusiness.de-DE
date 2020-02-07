---
title: Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: In diesem Artikel wird erläutert, wie Sie Cloud-Video-Interop für Benutzer in Ihrer Organisation planen und einrichten können.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e937e7825000d02156c1f5ede2671711006cbdd
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825103"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="327d7-103">Einrichten von Cloud-Video-Interoperabilität für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="327d7-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="327d7-104">Nachdem Sie [Ihre Brightcove-Video-Interop-Partner (n) ausgewählt](cloud-video-interop.md)haben, müssen Sie Ihre Bereitstellung planen, mit Bereitstellungsdetails und dem Partner Mandanten Schlüssel einrichten und der Video-Interop-app in Ihrer Organisation zustimmen.</span><span class="sxs-lookup"><span data-stu-id="327d7-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="327d7-105">Das folgende Diagramm beschreibt den Prozess.</span><span class="sxs-lookup"><span data-stu-id="327d7-105">The following diagram outlines the process.</span></span> 

![Bereitstellen von CVI in Ihrer Organisation](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="327d7-107">Plan</span><span class="sxs-lookup"><span data-stu-id="327d7-107">Plan</span></span>

<span data-ttu-id="327d7-108">Informationen dazu, wie Sie einen Partner oder Partner identifizieren können, der in Ihrer Organisation verwendet werden soll, finden Sie unter [Cloud Video-Interop für Microsoft Teams](cloud-video-interop.md) .</span><span class="sxs-lookup"><span data-stu-id="327d7-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="327d7-109">So planen Sie die benutzerbasierte/Concurrent/Site Wide-Aktivierung:</span><span class="sxs-lookup"><span data-stu-id="327d7-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="327d7-110">Wählen Sie ein Bereitstellungsmodell/gehostetes Modell für ihre Verwendung aus.</span><span class="sxs-lookup"><span data-stu-id="327d7-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="327d7-111">Wählen Sie den Lizenzplan aus, der ideal für Ihre Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="327d7-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="327d7-112">Plan für die Kapazität von VMS ist, dass Sie Ihre Video Infrastruktur hosten.</span><span class="sxs-lookup"><span data-stu-id="327d7-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="327d7-113">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="327d7-113">Configure</span></span> 

<span data-ttu-id="327d7-114">Führen Sie die folgenden Schritte aus, um Brightcove-Video Interop zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="327d7-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="327d7-115">Besorgen Sie sich Konfigurationsinformationen von den von Ihnen ausgewählten Partnern/Partnern (Mandanten Schlüssel, Daten-und-dann...).</span><span class="sxs-lookup"><span data-stu-id="327d7-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="327d7-116">Sie können einen oder mehrere Video-Interop-Partner in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="327d7-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="327d7-117">Stellen Sie sicher, dass Ihr Netzwerk ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="327d7-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="327d7-118">Konfigurieren Sie Ihre standardbasierte Video Firewall für den Umkreisnetzwerk Durchlauf, um Sie zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="327d7-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="327d7-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="327d7-119">For example:</span></span> 
    - <span data-ttu-id="327d7-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="327d7-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="327d7-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="327d7-121">Polycom RPAD</span></span>

3. <span data-ttu-id="327d7-122">Konfigurieren Sie integrierte Räume mit Exchange und OTD.</span><span class="sxs-lookup"><span data-stu-id="327d7-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="327d7-123">In den meisten Fällen müssten zusätzliche Relays in Ihrer Umgebung eingerichtet und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="327d7-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="327d7-124">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="327d7-124">Provision</span></span>
 
<span data-ttu-id="327d7-125">Der Mandanten Schlüssel ist die Wählfunktion des Partner Diensts.</span><span class="sxs-lookup"><span data-stu-id="327d7-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="327d7-126">Im folgenden Beispiel ist 813878896@t.PLCM.VC der Mandanten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="327d7-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Beispiel für Mandanten Schlüssel](media/tenant-key-example.png) 

<span data-ttu-id="327d7-128">Sie müssen die folgenden Cmdlets ausführen, um den Mandanten Schlüssel bereitzustellen, und Sie können auch SELECT-Benutzer oder Ihre gesamte Organisation aktivieren, um Besprechungen mit Video-Interop-Koordinaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="327d7-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="327d7-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft stellt für jeden unserer unterstützten Partner vorgefertigte Richtlinien bereit, mit denen Sie festlegen können, welche Partner für die Cloud-Video-Interop verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="327d7-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="327d7-130">Mit diesem Cmdlet können Sie die vorab erstellten Richtlinien identifizieren, die Sie in Ihrer Organisation verwenden können.</span><span class="sxs-lookup"><span data-stu-id="327d7-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="327d7-131">Sie können diese Richtlinie einem oder mehreren Benutzern zuweisen, indem Sie das Cmdlet Grant-CsTeamsVideoInteropServicePolicy nutzen.</span><span class="sxs-lookup"><span data-stu-id="327d7-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="327d7-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* Mit dem Cmdlet Grant-CsTeamsVideoInteropServicePolicy können Sie eine vordefinierte Richtlinie für die Verwendung in Ihrer Organisation zuweisen oder die Richtlinie bestimmten Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="327d7-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="327d7-133">\*\* [Neu-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Verwenden Sie die CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner anzugeben, den Ihre Organisation verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="327d7-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="327d7-134">\*\* [Satz-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Verwenden Sie das CsVideoInteropServiceProvider, um Informationen zu einem unterstützten CVI-Partner zu aktualisieren, der in Ihrer Organisation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="327d7-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="327d7-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Rufen Sie alle Anbieter ab, die für die Verwendung innerhalb der Organisation konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="327d7-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="327d7-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Verwenden Sie Remove-CsVideoInteropServiceProvider, um alle Anbieter Informationen zu einem Anbieter zu entfernen, den Ihre Organisation nicht mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="327d7-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="327d7-137">Zustimmung</span><span class="sxs-lookup"><span data-stu-id="327d7-137">Consent</span></span>

<span data-ttu-id="327d7-138">Sie müssen die Genehmigungs Genehmigung für Video Teleconferencing Devices (VTCs) bereitstellen, um über den Partnerdienst an ihren Organisationen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="327d7-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="327d7-139">Dieser Link zur Zustimmung wird auch von Ihrem Partner zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="327d7-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="327d7-140">Wenn diese Schritte abgeschlossen sind, werden die Benutzer, die über das Grant-Cmdlet oben einzeln aktiviert sind, oder alle Benutzer in der Organisation, wenn der Mandant aktiviert ist, VTC-Koordinaten in allen von Ihnen geplanten Teams-Besprechungen haben.</span><span class="sxs-lookup"><span data-stu-id="327d7-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="327d7-141">Alle VTC können über diese Koordinaten an diesen Besprechungen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="327d7-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="327d7-142">Name</span><span class="sxs-lookup"><span data-stu-id="327d7-142">Name</span></span>|<span data-ttu-id="327d7-143">Kurzbeschreibung der Anwendungsberechtigung</span><span class="sxs-lookup"><span data-stu-id="327d7-143">Application Permission Short Description</span></span>| <span data-ttu-id="327d7-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="327d7-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="327d7-145">Calls. JoinGroupCall. all</span><span class="sxs-lookup"><span data-stu-id="327d7-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="327d7-146">Teilnehmen an Gruppen anrufen und Besprechungen als app (Preview)</span><span class="sxs-lookup"><span data-stu-id="327d7-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="327d7-147">Ermöglicht der APP die Teilnahme an Gruppen anrufen und geplanten Besprechungen in Ihrer Organisation, ohne dass ein Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="327d7-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="327d7-148">Die APP wird mit den Berechtigungen eines Verzeichnis Benutzers für Besprechungen in Ihrem Mandanten verbunden.</span><span class="sxs-lookup"><span data-stu-id="327d7-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="327d7-149">Calls. JoinGroupCallasGuest. all</span><span class="sxs-lookup"><span data-stu-id="327d7-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="327d7-150">Teilnehmen an Gruppen anrufen und Besprechungen als Gastbenutzer (Preview)</span><span class="sxs-lookup"><span data-stu-id="327d7-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="327d7-151">Ermöglicht der APP, anonym an Gruppen anrufen und geplanten Besprechungen in Ihrer Organisation teilzunehmen, ohne dass ein Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="327d7-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="327d7-152">Die APP wird als Gast zu Besprechungen in Ihrem Mandanten verbunden.</span><span class="sxs-lookup"><span data-stu-id="327d7-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="327d7-153">Calls. AccessMedia. all</span><span class="sxs-lookup"><span data-stu-id="327d7-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="327d7-154">Zugreifen auf Mediendatenströme in einem Anruf als app (Preview)</span><span class="sxs-lookup"><span data-stu-id="327d7-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="327d7-155">Ermöglicht der APP den direkten Zugriff auf Mediendatenströme in einem Anruf ohne einen angemeldeten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="327d7-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="327d7-156">OnlineMeetings. Read. all</span><span class="sxs-lookup"><span data-stu-id="327d7-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="327d7-157">Online Besprechungsdetails lesen (Preview)</span><span class="sxs-lookup"><span data-stu-id="327d7-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="327d7-158">Ermöglicht der APP, Online Besprechungsdetails in Ihrer Organisation zu lesen, ohne dass ein Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="327d7-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="327d7-159">Zeitplan</span><span class="sxs-lookup"><span data-stu-id="327d7-159">Schedule</span></span>

<span data-ttu-id="327d7-160">Als nächstes planen Sie Teams-Besprechung mit Video-Interop-Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="327d7-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="327d7-161">Der aktivierte Benutzer kann Teams-Besprechungen über Folgendes planen:</span><span class="sxs-lookup"><span data-stu-id="327d7-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="327d7-162">Teambesprechung-Add-in für Outlook</span><span class="sxs-lookup"><span data-stu-id="327d7-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="327d7-163">Teams Clientdesktop und Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="327d7-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="327d7-164">Join</span><span class="sxs-lookup"><span data-stu-id="327d7-164">Join</span></span>

<span data-ttu-id="327d7-165">Sie können mit ihren VTC-Geräten mit den folgenden Methoden an Teams-Besprechungen teilnehmen:</span><span class="sxs-lookup"><span data-stu-id="327d7-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="327d7-166">IVR (Interaktive Sprachantwort)</span><span class="sxs-lookup"><span data-stu-id="327d7-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="327d7-167">Sie können sich über die tenantkey@Domain in die IVR des Partners einwählen.</span><span class="sxs-lookup"><span data-stu-id="327d7-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="327d7-168">Sobald Sie in der Partner-IVR sind, werden Sie aufgefordert, die VTC-Konferenz-Nr einzugeben, die Sie dann mit der Teams-Besprechung verbindet.</span><span class="sxs-lookup"><span data-stu-id="327d7-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="327d7-169">Direktwahl</span><span class="sxs-lookup"><span data-stu-id="327d7-169">Direct dial</span></span>
    - <span data-ttu-id="327d7-170">Sie können sich direkt in die Teambesprechung einwählen, ohne mit der IVR des Partners zu interagieren, indem Sie die direkte Wählfunktion verwenden, indem Sie die vollständige Zeichenfolge von tenantkey verwenden. VTC ConferenceId@Domain.</span><span class="sxs-lookup"><span data-stu-id="327d7-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="327d7-171">One-Touch-Dial</span><span class="sxs-lookup"><span data-stu-id="327d7-171">One-touch dial</span></span>
    - <span data-ttu-id="327d7-172">Wenn Sie über einen integrierten TeamRoom verfügen, können Sie die von Ihrem Partner angebotenen One-Touch-Wählfunktionen nutzen (ohne eine Wählzeichenfolge eingeben zu müssen).</span><span class="sxs-lookup"><span data-stu-id="327d7-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="327d7-173">Und schließlich können Sie sich mithilfe von Audio, Video und Inhaltsfreigabe in ihren Besprechungen mit Teams besprechen.</span><span class="sxs-lookup"><span data-stu-id="327d7-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 

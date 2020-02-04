---
title: Übersicht über lync Server 2013 A/V-Konferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 405d44f9128ef4c8120a6a8389f8d566b6880b2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="1e470-102">Übersicht über A/V-Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e470-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e470-103">_**Letztes Änderungsdatum des Themas:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="1e470-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="1e470-104">A/V-Konferenzen ermöglichen Audio-und Videokommunikation in Echtzeit zwischen Ihren Benutzern.</span><span class="sxs-lookup"><span data-stu-id="1e470-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="1e470-105">Wenn Sie Konferenzen bereitstellen, können Sie auswählen, ob Sie Webkonferenzen und A/V-Konferenzen oder nur Webkonferenzen aktivieren und verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1e470-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="1e470-106">Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e470-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="1e470-107">Dies könnten z. B. Audio, Video und Panoramavideo sein.</span><span class="sxs-lookup"><span data-stu-id="1e470-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="1e470-108">Bevor Sie Benutzer für A/V-Konferenzen aktivieren, stellen Sie sicher, dass Ihr Netzwerk die resultierende Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1e470-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="1e470-109">Eine zu geringe Netzwerkbandbreite kann zu einem stark beeinträchtigten Benutzererlebnis führen.</span><span class="sxs-lookup"><span data-stu-id="1e470-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="1e470-110">Sie können die Anrufsteuerung (Call Admission Control, CAC) verwenden, um die von A/V-Konferenzen verwendete Netzwerkbandbreite zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1e470-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="1e470-111">Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise bei Verbindungen mit beschränkter Bandbreite zwischen Zentrale und Niederlassungen.</span><span class="sxs-lookup"><span data-stu-id="1e470-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="1e470-112">Ausführliche Informationen finden Sie unter Übersicht über die [Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="1e470-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="1e470-113">Details zu den Anforderungen an die Medien Bandbreite finden Sie unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="1e470-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="1e470-114">Bei Bereitstellung der Audiokonferenzfunktion in Ihrem Netzwerk benötigen Ihre Benutzer Audiogeräte (z. B. Headsets), um an einer Audiokonferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1e470-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="1e470-115">Wenn Sie Videokonferenzen bereitstellen, benötigen die Benutzer Videogeräte, wie Webcams.</span><span class="sxs-lookup"><span data-stu-id="1e470-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="1e470-116">Wir empfehlen die Verwendung von UC-Geräten (Unified Communications), die von Microsoft für alle Gerätetypen zertifiziert sind, um eine optimale Benutzererfahrung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="1e470-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="1e470-117">Details zu UC-zertifizierten Geräten finden Sie unter "Telefone und Geräte für lync" [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)unter.</span><span class="sxs-lookup"><span data-stu-id="1e470-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="1e470-118">Für Audio-oder Videogeräte, die Gerätebereitstellung und die Benutzerschulung sind wichtige Schritte, die Sie beachten und planen können.</span><span class="sxs-lookup"><span data-stu-id="1e470-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="1e470-119">In den folgenden Abschnitten werden die Features für Audio-und Videokonferenzen beschrieben, einschließlich Informationen zum Verwalten der Bandbreite und zum Auswählen der entsprechenden Clients.</span><span class="sxs-lookup"><span data-stu-id="1e470-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="1e470-120">Audiokonferenz-Features</span><span class="sxs-lookup"><span data-stu-id="1e470-120">Audio Conferencing Features</span></span>

<span data-ttu-id="1e470-121">Lync Server 2013 bietet verschiedene Features, die Sie zum Konfigurieren der Audiokonferenz-Oberfläche für den Benutzer verwenden können, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1e470-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="1e470-122">**Zuschauer Stummschaltung**   der Referent kann diese Einstellung verwenden, um alle Audio-Teilnehmer in der Konferenz stummzuschalten und die Konferenz in einen Zustand zu versetzen, in dem nicht Referenten die Stummschaltung selbst aufheben können.</span><span class="sxs-lookup"><span data-stu-id="1e470-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="1e470-123">**Conferencing Entry/Exit-Ankündigungen**   Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten diese Einstellung verwenden, um ein-und ausgehende Ankündigungen zu aktivieren oder zu deaktivieren, um Ablenkungen zu minimieren, während eine Konferenz läuft.</span><span class="sxs-lookup"><span data-stu-id="1e470-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="1e470-124">**Wenn Sie einen Benutzer hinzufügen, indem Sie**   Referenten und Teilnehmer auswählen, denen die Berechtigung erteilt wurde, können Sie den Konferenzen PSTN-Nummern hinzufügen und die Konferenz an diese Nummern anwählen.</span><span class="sxs-lookup"><span data-stu-id="1e470-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="1e470-125">Video Konferenz Features</span><span class="sxs-lookup"><span data-stu-id="1e470-125">Video Conferencing Features</span></span>

<span data-ttu-id="1e470-126">Lync Server 2013 bietet verschiedene Features, mit denen Sie die Videokonferenzfunktionalität für den Benutzer konfigurieren können, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="1e470-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="1e470-127">**Katalogansicht**   in Videokonferenzen, die mehr als zwei Personen aufweisen, sehen Benutzer automatisch alle Teilnehmer der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="1e470-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="1e470-128">Wenn die Konferenz mehr als fünf Teilnehmer hat, werden in der ersten Zeile die Videos der aktivsten Teilnehmer angezeigt und für die übrigen Teilnehmer Fotos.</span><span class="sxs-lookup"><span data-stu-id="1e470-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="1e470-129">Die Videoaushandlung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1e470-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="1e470-130">Details zum Konfigurieren oder Deaktivieren von mehrteiligen Videos finden Sie unter [Konfigurieren der Videobandbreite in lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="1e470-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="1e470-131">**Panorama Video**   wenn ein RoundTable-Videokonferenz Gerät im Konferenzraum installiert ist, bietet dieses Feature eine vollständige 360-Grad-Ansicht des Konferenzraums.</span><span class="sxs-lookup"><span data-stu-id="1e470-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="1e470-132">Panoramavideo ist nur mit Round Table verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1e470-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="1e470-133">**Referenten nur Videomodus**   Referenten können die Besprechung so konfigurieren, dass nur das Video des Referenten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1e470-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="1e470-134">Dies verhindert bei großen Besprechungen Ablenkungen, wenn mehrere Videostreams verfügbar und mit verschiedenen Quellen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1e470-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="1e470-135">Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräte aufgenommen und bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1e470-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="1e470-136">**HD-Video**   Benutzer können Auflösungen bis zu HD 1080p in zwei-Parteien-anrufen und mehrteiligen Konferenzen erleben.</span><span class="sxs-lookup"><span data-stu-id="1e470-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="1e470-137">**Video Spotlight**   -Referenten können die Besprechung so konfigurieren, dass nur das Video von einem ausgewählten Teilnehmer, der eine Videoquelle ist, von den anderen Teilnehmern der Konferenz gesehen wird.</span><span class="sxs-lookup"><span data-stu-id="1e470-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="1e470-138">Dieser Modus wird auch auf Videos angewendet, die mit Round Table-Geräten aufgenommen und bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1e470-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


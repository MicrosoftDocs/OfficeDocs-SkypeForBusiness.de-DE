---
title: Lync Server 2013 A/V-Konferenzen (Übersicht)
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
ms.openlocfilehash: f35ef9adaf4f19023ebe2220494fdb315c782515
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523262"
---
# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="a0ea0-102">Übersicht über A/V-Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0ea0-102">Overview of A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0ea0-103">_**Letztes Änderungsstand des Themas:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="a0ea0-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="a0ea0-104">A/V-Konferenzen ermöglichen die Echtzeit-Audio-und Videokommunikation zwischen Ihren Benutzern.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="a0ea0-105">Wenn Sie die Konferenzfunktion bereitstellen, können Sie entweder sowohl Webkonferenzen als auch A/V-Konferenzen oder nur Webkonferenzen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="a0ea0-106">Zum Planen von A/V-Konferenzen müssen Sie die erforderliche Netzwerkbandbreite für den Typ der Konferenzmedien kennen, die in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="a0ea0-107">Dies kann Audio-, Video-und Panorama Video umfassen.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="a0ea0-108">Bevor Sie Benutzer für A/V-Konferenzen aktivieren, müssen Sie sicherstellen, dass Ihr Netzwerk die resultierende Last verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="a0ea0-109">Ohne ausreichende Netzwerkbandbreite kann die Benutzeroberfläche stark beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="a0ea0-110">Sie können die Anrufsteuerung (Call Admission Control, CAC) verwenden, um die von A/V-Konferenzen verwendete Netzwerkbandbreite zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="a0ea0-111">Dies ist für eingeschränkte Netzwerke wichtig, beispielsweise für Verbindungen mit beschränkter Bandbreite zwischen zentralen und Zweigstellenstandorten.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="a0ea0-112">Ausführliche Informationen finden Sie unter [Overview of Call Admission Control in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="a0ea0-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="a0ea0-113">Ausführliche Informationen zu den Anforderungen an die Medien Bandbreite finden Sie unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="a0ea0-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="a0ea0-114">Wenn Sie Audiokonferenzen in Ihrem Netzwerk bereitstellen, benötigen Ihre Benutzer Audiogeräte wie Headsets, um an einer Audiokonferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="a0ea0-115">Bei der Bereitstellung von Videokonferenzen müssen Sie Videogeräte wie Webcams für Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="a0ea0-116">Es wird empfohlen, UC-Geräte (Unified Communications) zu verwenden, die von Microsoft für alle Gerätetypen zertifiziert sind, um eine optimale Benutzerfreundlichkeit sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="a0ea0-117">Ausführliche Informationen zu UC-zertifizierten Geräten finden Sie unter "Telefone und Geräte für lync" unter [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) .</span><span class="sxs-lookup"><span data-stu-id="a0ea0-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="a0ea0-118">Für Audio-oder Videogeräte sind die Gerätebereitstellung und die Benutzerschulung wichtige Schritte, die Sie berücksichtigen und planen müssen.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="a0ea0-119">In den folgenden Abschnitten werden die Funktionen für Audio-und Videokonferenzen beschrieben, einschließlich Informationen zum Verwalten der Bandbreite und zum Auswählen der entsprechenden Clients.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="a0ea0-120">Audiokonferenz-Features</span><span class="sxs-lookup"><span data-stu-id="a0ea0-120">Audio Conferencing Features</span></span>

<span data-ttu-id="a0ea0-121">Lync Server 2013 bietet verschiedene Features, mit denen Sie die Audiokonferenz-Benutzeroberfläche für den Benutzer konfigurieren können, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="a0ea0-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="a0ea0-122">**Benutzergruppe stumm**     Der Referent kann diese Einstellung verwenden, um alle Audioteiler in der Konferenz stummzuschalten und die Konferenz in einen Zustand zu versetzen, in dem nicht-Referenten sich selbst nicht entmuten können.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="a0ea0-123">**Konferenz Eintrag/Exit-Ankündigungen**     Wenn Sie Einwahlkonferenzen aktiviert haben, können Referenten diese Einstellung verwenden, um die Eingabe-und Beendigungs Ankündigungen zu aktivieren oder zu deaktivieren, um Ablenkungen während einer Konferenz zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="a0ea0-124">**Hinzufügen eines Benutzers durch auswählen**     Referenten und Teilnehmer, denen die Berechtigung erteilt wurde, können PSTN-Nummern zu den Konferenzen hinzufügen und die Konferenz für diese Nummern wählen.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="a0ea0-125">Video Konferenzfunktionen</span><span class="sxs-lookup"><span data-stu-id="a0ea0-125">Video Conferencing Features</span></span>

<span data-ttu-id="a0ea0-126">Lync Server 2013 bietet verschiedene Features, mit denen Sie die Videokonferenzumgebung für den Benutzer konfigurieren können, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="a0ea0-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="a0ea0-127">**Galerieansicht**     Bei Videokonferenzen mit mehr als zwei Personen sehen die Benutzer automatisch alle Mitglieder der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="a0ea0-128">Wenn die Konferenz über mehr als fünf Teilnehmer verfügt, wird das Video der aktivsten Teilnehmer in der obersten Zeile angezeigt, und für die anderen Teilnehmer wird nur das Foto angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="a0ea0-129">Video mit mehreren Teilern ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="a0ea0-130">Ausführliche Informationen zum Konfigurieren oder Deaktivieren von Video für mehrteilige Videos finden Sie unter [Konfigurieren der Videobandbreite in lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="a0ea0-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="a0ea0-131">**Panorama Video**     Wenn ein RoundTable-Videokonferenz Gerät im Konferenzraum installiert ist, bietet dieses Feature eine vollständige 360 Grad Ansicht des Konferenzraums.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="a0ea0-132">Der Panorama-Video Strip ist nur für RoundTable-Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="a0ea0-133">**Videomodus**     für Referenten Referenten können die Besprechung so konfigurieren, dass nur das Video des Referenten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="a0ea0-134">Dadurch werden Ablenkungen in großen Besprechungen verhindert, wenn mehrere Videostreams verfügbar sind und verschiedene Quellen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="a0ea0-135">Dieser Modus gilt auch für von RoundTable-Geräten erfasste und bereitgestellte Videos.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="a0ea0-136">**HD-Video**     Benutzer können Auflösungen bis zu HD 1080p in Gesprächen mit zwei Teilnehmern und Konferenzen in mehreren Gruppen erleben.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="a0ea0-137">**Video Spotlight**     Referenten können die Besprechung so konfigurieren, dass nur das Video eines ausgewählten Teilnehmers, der eine Videoquelle ist, von den anderen Teilnehmern in der Konferenz angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="a0ea0-138">Dieser Modus gilt auch für Videos, die von RoundTable-Geräten für Panorama Video erfasst und bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a0ea0-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


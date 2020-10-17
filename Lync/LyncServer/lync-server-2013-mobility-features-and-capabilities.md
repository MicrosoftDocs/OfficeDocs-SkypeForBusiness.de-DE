---
title: 'Lync Server 2013: Mobilitätsfeatures und-Funktionen'
description: 'Lync Server 2013: Mobilitätsfeatures und-Funktionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20713145c18260f22d9635c34af291e9a7c5ea9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550581"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="1e7cf-103">Mobilitätsfeatures und-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e7cf-103">Mobility features and capabilities in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e7cf-104">_**Letztes Änderungsstand des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="1e7cf-104">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="1e7cf-105">Das in den kumulativen Updates für lync Server 2013:2013. Februar eingeführte Mobilitätsfeature unterstützt lync 2010 Mobile-und lync 2013-Funktionen für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-105">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="1e7cf-106">Wenn Sie den lync Server 2013 Mobilitätsdienst bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-oder Nokia Symbian-Mobilgeräte verwenden, um Aktivitäten wie senden und empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-106">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="1e7cf-107">Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, Geschäftlich anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-107">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="1e7cf-108">Zu den neuen Features, die in den kumulativen Updates für lync Server 2013:2013. Februar eingeführt wurden, gehören Voice over IP (VoIP)-Funktionen und Video (H. 264) für Besprechungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-108">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="1e7cf-109">Das in den kumulativen Updates für lync Server 2013:2013. Februar eingeführte Mobilitätsfeature unterstützt lync 2013 Mobile Clientfunktionalität.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-109">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="1e7cf-110">Die kumulativen Updates für lync Server 2013:2013 Februar installieren Unified Communications-WebAPI oder UCWA.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-110">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="1e7cf-111">UCWA ist die Komponente, die für lync 2013 Mobile Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-111">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="1e7cf-112">In lync Server 2013 wird MCX für lync 2010 Mobile-Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-112">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="1e7cf-113">Kumulative Updates für lync Server 2013: Februar 2013 Einführung von UCWA als neuen Einstiegspfad für Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-113">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="1e7cf-114">Lync Server 2013 implementiert gleichzeitig den Mobilitätsdienst (MCX), der in den kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde, und bietet Unterstützung für lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-114">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="1e7cf-115">Wenn Sie die kumulativen Updates für lync Server 2013: Februar 2013 bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-Mobilgeräte verwenden, um folgende Aktivitäten auszuführen:</span><span class="sxs-lookup"><span data-stu-id="1e7cf-115">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e7cf-116">Vom Mobilitätsdienst unterstützte Features aus den kumulativen Updates für lync Server 2010: November 2011 werden mit (MCX) notiert.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-116">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="1e7cf-117">Alle aufgeführten Features werden von der UCWA unterstützt, die in den kumulativen Updates für lync Server 2013:2013. Februar eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-117">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="1e7cf-118">Senden und empfangen von Chatnachrichten (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-118">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-119">Anwesenheit anzeigen (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-119">View presence (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-120">Kontakte anzeigen (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-120">View contacts (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-121">Klicken Sie, um an einer Konferenz teilzunehmen (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-121">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-122">Anruf über Arbeit (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-122">Call via work (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-123">Reichweite für einzelne Nummern (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-123">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-124">Voicemail (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-124">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-125">Benachrichtigung über verpasste Anrufe (MCX)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-125">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="1e7cf-126">VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-126">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="1e7cf-127">Teilnehmer Video (H. 264)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-127">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e7cf-128">Lync 2010 Mobile einen Client für Nokia Symbian-Geräte bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-128">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="1e7cf-129">Lync 2013 Mobile verfügt über keinen Client für Nokia Symbian-basierte Geräte.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-129">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="1e7cf-130">Apple iPad-Benutzer haben Zugriff auf erweiterte Fähigkeiten.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-130">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="1e7cf-131">Nachdem ein iPad-Benutzer eine Besprechung mit einem audiorückruf durchgeführt hat, kann er hochgeladene Microsoft PowerPoint Präsentationen in einer Besprechung anzeigen, Anwendungen und Desktops freigeben, die Teilnehmerliste der Besprechung anzeigen und Benachrichtigungen über andere Inhaltstypen empfangen, die in der Besprechung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-131">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1e7cf-132">Bei einer einzelnen Rufnummer erhält ein Benutzer Anrufe auf einem Mobiltelefon, die zur Arbeitsnummer gewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-132">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="1e7cf-133">Bei der Funktion "Anruf über Arbeit" platziert der Benutzer einen ausgehenden Anruf vom mobilen lync-Client mithilfe einer geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-133">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="1e7cf-134">Mit "Dial-Out" sendet der Client eine Anforderung an MCX oder UCWA (basierend auf der mobilen lync-Version), um den Anruf zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-134">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="1e7cf-135">Der Server initiiert den Anruf und ruft dann den Benutzer wieder auf dem Mobiltelefon an.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-135">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="1e7cf-136">Wenn der Benutzer antwortet, beendet der Server den Anruf, indem er den anderen Teilnehmer anwählt.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-136">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="1e7cf-137">Mithilfe der Funktion "Anruf über Arbeit" können Benutzer ihre Arbeitsidentität während eines Anrufs aufrecht erhalten, was bedeutet, dass der Anrufempfänger die Mobiltelefonnummer des Anrufers nicht erkennt und der Anrufer keine ausgehenden Gebühren mehr annimmt.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-137">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1e7cf-138">Nicht alle Features werden auf sämtlichen Mobiltelefonen genau gleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-138">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="1e7cf-139">Ausführliche Informationen zu den auf mobilen Geräten unterstützten Features finden Sie in den Vergleichstabellen für mobile Clients unter <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> .</span><span class="sxs-lookup"><span data-stu-id="1e7cf-139">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="1e7cf-140">Ausführliche Informationen zu unterstützten Geräten und Betriebssystemen finden Sie in den Anforderungen unter <A href="lync-server-2013-planning-for-mobile-clients.md">Planung für mobile Clients in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-140">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1e7cf-141">Wenn Sie das Feature lync Server 2013 AutoErmittlung verwenden, können mobile Anwendungen automatisch lync Server 2013 Webdienste finden, ohne dass Benutzer die URLs in ihren Geräteeinstellungen manuell eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-141">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="1e7cf-142">Die manuelle Eingabe von URLs in den Einstellungen des mobilen Geräts wird auch unterstützt, hauptsächlich zu Problembehandlungszwecken.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-142">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e7cf-143">Die MCX und UCWA sind ﻿kostenlose Dienste, und beide werden bereitgestellt, um lync 2010 Mobile und lync 2013 Mobile Clients zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-143">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="1e7cf-144">Lync 2013 Mobile kann sich nicht bei lync Server 2010-Bereitstellungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-144">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="1e7cf-145">Lync 2010 Mobile und lync 2013 Mobile können eine lync Server 2013-Bereitstellung mit den kumulativen Updates für lync Server 2013 verwenden: 2013. Februar: wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-145">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="1e7cf-146">Das Mobilitätsfeature unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-146">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="1e7cf-147">Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-147">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="1e7cf-148">Beispielsweise kann eine verpasste sofortnachrichteneinladung zu einer Push-Benachrichtigung führen.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-148">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="1e7cf-149">MCX, UCWA, AutoErmittlungsdienst und Unterstützung für Push-Benachrichtigungen werden in lync Server 2013 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-149">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="1e7cf-150">Aktualisierte Clientfeatures, Funktionen und die Verwendung von UCWA als Mobilitäts Einstiegspunkt werden in den kumulativen Updates für lync Server 2013:2013. Februar eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-150">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


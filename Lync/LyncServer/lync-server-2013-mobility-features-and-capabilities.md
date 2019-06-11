---
title: 'Lync Server 2013: Mobilitätsfeatures und -funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="c2b94-102">Mobilitätsfeatures und -funktionen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b94-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b94-103">_**Letztes Änderungsdatum des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="c2b94-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="c2b94-104">Das Mobilitätsfeature, das in den kumulativen Updates für lync Server 2013: Februar 2013 unterstützt die lync 2010 Mobile-und lync 2013-Funktionen für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="c2b94-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="c2b94-105">Wenn Sie den lync Server 2013-Mobilitätsdienst bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-oder Nokia Symbian-Mobilgeräte verwenden, um Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsfunktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="c2b94-106">Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit anzurufen, eine Rufnummer zu erreichen, Voicemail und verpasste Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="c2b94-107">Neue Features, die in den kumulativen Updates für lync Server 2013: Februar 2013 eingeführt wurden, umfassen VoIP-Funktionen und Video (H. 264) für Besprechungsteilnehmer.</span><span class="sxs-lookup"><span data-stu-id="c2b94-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="c2b94-108">Das Mobilitätsfeature in den kumulativen Updates für lync Server 2013: Februar 2013 unterstützt die lync 2013-Funktionalität für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="c2b94-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="c2b94-109">Die kumulativen Updates für lync Server 2013: Februar 2013 Installieren der Unified Communications Web-API oder UCWA.</span><span class="sxs-lookup"><span data-stu-id="c2b94-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="c2b94-110">UCWA ist die Komponente, die für Mobile lync 2013-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2b94-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="c2b94-111">In lync Server 2013 wird MCX für Mobile lync 2010-Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="c2b94-112">Kumulative Updates für lync Server 2013: Februar 2013 Einführung von UCWA als neuen Einstiegspunkt für Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="c2b94-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="c2b94-113">Lync Server 2013 implementiert gleichzeitig den Mobilitätsdienst (Mobility Service, MCX), der in den kumulativen Updates für lync Server 2010: November 2011 eingeführt wurde, und bietet Unterstützung für lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="c2b94-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="c2b94-114">Wenn Sie die kumulativen Updates für lync Server 2013: Februar 2013 bereitstellen, können Benutzer unterstützte Apple IOS-, Android-und Windows Phone-Mobilgeräte verwenden, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c2b94-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c2b94-115">Vom Mobilitätsdienst unterstützte Features aus den kumulativen Updates für lync Server 2010: November 2011 sind mit (MCX) gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="c2b94-116">Alle aufgelisteten Features werden vom UCWA unterstützt, das in den kumulativen Updates für lync Server 2013: Februar 2013 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c2b94-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="c2b94-117">Senden und empfangen von Sofortnachrichten (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="c2b94-118">Anzeigen von Anwesenheitsinformationen (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="c2b94-119">Anzeigen von Kontakten (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="c2b94-120">Klicken Sie, um an einer Konferenz teilzunehmen (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="c2b94-121">Anruf über Arbeit (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="c2b94-122">Erreichbarkeit einer Rufnummer (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="c2b94-123">Voicemail (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="c2b94-124">Benachrichtigung über verpasste Anrufe (MCX)</span><span class="sxs-lookup"><span data-stu-id="c2b94-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="c2b94-125">Voice over IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="c2b94-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="c2b94-126">Teilnehmervideo (H.264)</span><span class="sxs-lookup"><span data-stu-id="c2b94-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2b94-127">Lync 2010 Mobile hat einen Client für Nokia Symbian-Geräte bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c2b94-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="c2b94-128">Lync 2013 Mobile hat keinen Client für Nokia Symbian-basierte Geräte.</span><span class="sxs-lookup"><span data-stu-id="c2b94-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="c2b94-129">Apple iPad-Benutzer erhalten Zugriff auf Erweiterte Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="c2b94-130">Nach dem teilnehmen an einer Besprechung mithilfe des audiorückrufs kann ein iPad-Benutzer hochgeladene Microsoft PowerPoint-Präsentationen in einer Besprechung anzeigen, Anwendungen und Desktops freigeben, die Teilnehmerliste der Besprechung anzeigen und Benachrichtigungen zu anderen Inhaltstypen empfangen. , die in der Besprechung freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c2b94-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c2b94-131">Mit einer einzelnen Rufnummer erhält ein Nutzer Anrufe auf einem Mobiltelefon, das in die geschäftliche Rufnummer gewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="c2b94-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="c2b94-132">Bei Anrufen über Arbeit platziert der Benutzer einen ausgehenden Anruf vom lync Mobile-Client unter Verwendung einer geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer.</span><span class="sxs-lookup"><span data-stu-id="c2b94-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="c2b94-133">Beim Einwählen sendet der Client eine Anforderung an MCX oder UCWA (basierend auf der lync Mobile-Version), um den Anruf zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="c2b94-134">Der Server initiiert den Anruf und ruft den Benutzer dann wieder auf dem Mobiltelefon an.</span><span class="sxs-lookup"><span data-stu-id="c2b94-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="c2b94-135">Wenn der Benutzer antwortet, schließt der Server den Anruf ab, indem er die andere Partei anwählt.</span><span class="sxs-lookup"><span data-stu-id="c2b94-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="c2b94-136">Durch die Verwendung von Anruf über die Arbeit können Benutzer Ihre geschäftliche Identität während eines Anrufs aufrecht erhalten, was bedeutet, dass der Anrufempfänger die Handynummer des Anrufers nicht sieht, und der Anrufer die Gebühren für ausgehende Anrufe vermeidet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c2b94-137">Nicht alle Features funktionieren auf allen mobilen Geräten genau gleich.</span><span class="sxs-lookup"><span data-stu-id="c2b94-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="c2b94-138">Details zu den auf mobilen Geräten unterstützten Features finden Sie in <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>den Vergleichstabellen für mobile Clients unter.</span><span class="sxs-lookup"><span data-stu-id="c2b94-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="c2b94-139">Ausführliche Informationen zu unterstützten Geräten und Betriebssystemen finden Sie in den Anforderungs Themen unter <A href="lync-server-2013-planning-for-mobile-clients.md">Planen für mobile Clients in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c2b94-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c2b94-140">Wenn Sie das Feature für die AutoErmittlung in lync Server 2013 verwenden, können mobile Anwendungen lync Server 2013-Webdienste automatisch finden, ohne dass die Benutzer die URLs manuell in Ihre Geräteeinstellungen eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="c2b94-141">Die manuelle Eingabe von URLs in Einstellungen für mobile Geräte wird ebenfalls unterstützt, hauptsächlich zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="c2b94-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c2b94-142">MCX und UCWA sind ﻿kostenlose Dienste, die beide zur Unterstützung von lync 2010 Mobile-und lync 2013-mobilen Clients bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c2b94-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="c2b94-143">Lync 2013 Mobile kann sich bei lync Server 2010-Bereitstellungen nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="c2b94-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="c2b94-144">Lync 2010 Mobile und lync 2013 Mobile können eine lync Server 2013-Bereitstellung mit den kumulierten Updates für lync Server 2013 verwenden: Februar 2013 angewendet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="c2b94-145">Die Mobilitätsfunktion unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="c2b94-146">Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="c2b94-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="c2b94-147">So kann beispielsweise eine verpasste sofortnachrichteneinladung zu einer Push-Benachrichtigung führen.</span><span class="sxs-lookup"><span data-stu-id="c2b94-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="c2b94-148">MCX, UCWA, AutoErmittlungsdienst und Support für Push-Benachrichtigungen werden in lync Server 2013 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c2b94-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="c2b94-149">Aktualisierte Clientfeatures, Funktionen und die Verwendung von UCWA als Mobilitäts Einstiegspunkt werden in den kumulativen Updates für lync Server 2013: Februar 2013 vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="c2b94-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


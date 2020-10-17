---
title: 'Lync Server 2013: häufig gestellte Fragen zur großen Besprechungs Unterstützung'
description: 'Lync Server 2013: häufig gestellte Fragen zur Unterstützung großer Besprechungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8d206400b46fc32a3af7b21ad7d50663e85d069
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557551"
---
# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="118fd-103">FAQ für umfangreiche Besprechungs Unterstützung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="118fd-103">Large meeting support FAQ for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="118fd-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="118fd-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="118fd-105">Die folgenden Abschnitte enthalten Antworten auf häufige Fragen zum Erstellen und Ausführen großer Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="118fd-105">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="118fd-106">Frage: Wie viele Benutzer können an einer großen Besprechung teilnehmen?</span><span class="sxs-lookup"><span data-stu-id="118fd-106">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="118fd-107">Das lync Server Benutzermodell gibt die Begrenzungen von 250 Benutzern in einem freigegebenen Pool oder 1000-Benutzern in einem Pool an, der für große Besprechungen reserviert ist, aber diese Zahlen stellen nur die Anzahl der getesteten Benutzer dar und nur für die spezifische Hardware, die wir in unseren Tests verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="118fd-107">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="118fd-108">Basierend auf unseren Tests empfehlen wir diese Grenzwerte für maximale Größe.</span><span class="sxs-lookup"><span data-stu-id="118fd-108">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="118fd-109">Sie steuern jedoch die tatsächliche Anzahl von Teilnehmern, die in Besprechungen in Ihrer Organisation zulässig sind, indem Sie eine oder mehrere Konferenzrichtlinien konfigurieren (die Sie mit Windows PowerShell-Cmdlets im lync Server-Verwaltungsshell oder mithilfe der lync Server-Systemsteuerung konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="118fd-109">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="118fd-110">Die Nummer, die Sie in einer konferenzrichtlinie angeben, kann eine beliebige 32-Bit-ganze Zahl zwischen 1 und 4.294.967.295 sein, die empfohlene Größe liegt jedoch zwischen 2 und 250 Teilnehmern, einschließlich; der Standardwert lautet 250.</span><span class="sxs-lookup"><span data-stu-id="118fd-110">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="118fd-111">Frage: Wie viele Besprechungen oder andere Arbeitsauslastungen sind für einen dedizierten Pool für große Besprechungen zulässig?</span><span class="sxs-lookup"><span data-stu-id="118fd-111">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="118fd-p102">Um bei großen Besprechungen mit bis zu 1000 Teilnehmern die beste Benutzererfahrung zu erzielen, wird empfohlen, in einem dedizierten Pool für große Besprechungen jeweils immer nur eine große Besprechung zu hosten. Zudem wird empfohlen, keine anderen Arbeitsauslastungen im Pool auszuführen, während eine große Besprechung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="118fd-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="118fd-114">Frage: Sollten die Organisatoren großer Besprechungen auf dem dedizierten Pool verwaltet werden?</span><span class="sxs-lookup"><span data-stu-id="118fd-114">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="118fd-p103">Nein. Es wird empfohlen, auf dem dedizierten Pool nur die Mitarbeiter zu verwalten, die für die Planung großer Besprechungen verantwortlich sind, und keine anderen Benutzer. Hierdurch wird verhindert, dass anderer Datenverkehr aus Echtzeitkommunikationen zu Problemen bei großen Besprechungen führt, die im Pool gehostet werden. Große Besprechungen im dedizierten Pool sollten mit einem Benutzerkonto geplant werden, das dem für die Planung großer Besprechungen zuständigen Personal zugewiesen ist. Sie sollten das Benutzerkonto des Besprechungsorganisators (der Benutzer, der eine große Besprechung anfordert) als Referenten für die große Besprechung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="118fd-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="118fd-120">Frage: Welche Medienmodalitäten können in einer großen Besprechung verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="118fd-120">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="118fd-121">Große Besprechungen mit bis zu 1000 Benutzern können Audio, Video, PowerPoint-Freigabe, Whiteboards und den Abruf von Anwesenheitsinformationen umfassen.</span><span class="sxs-lookup"><span data-stu-id="118fd-121">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="118fd-122">Frage: Kann ich in großen Besprechungen einen Gruppenchat verwenden?</span><span class="sxs-lookup"><span data-stu-id="118fd-122">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="118fd-123">Ja.</span><span class="sxs-lookup"><span data-stu-id="118fd-123">Yes.</span></span> <span data-ttu-id="118fd-124">Jedoch kann eine große Anzahl von Chatnachrichten, insbesondere wenn diese von sehr vielen Besprechungsteilnehmern gesendet werden, die Benutzerfreundlichkeit beeinträchtigen, da es Probleme mit dem schnellen Textbildlauf im Chatfester geben kann.</span><span class="sxs-lookup"><span data-stu-id="118fd-124">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="118fd-125">Durch das Senden einer großen Anzahl von Chatnachrichten an bis zu 1000 Benutzer kann zudem eine beträchtliche Serverlast entstehen, die zu einer Leistungsbeeinträchtigung führen kann.</span><span class="sxs-lookup"><span data-stu-id="118fd-125">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="118fd-126">Im Allgemeinen ist Chat nur für Fragen und Antworten erforderlich (Q \& As).</span><span class="sxs-lookup"><span data-stu-id="118fd-126">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="118fd-127">Können Benutzer an einer großen Besprechung teilnehmen, indem sie sich über ein Telefon einwählen?</span><span class="sxs-lookup"><span data-stu-id="118fd-127">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="118fd-128">Ja.</span><span class="sxs-lookup"><span data-stu-id="118fd-128">Yes.</span></span> <span data-ttu-id="118fd-129">Wenn der lync Server 2013 Pool ordnungsgemäß bereitgestellt und für Einwahlkonferenzen aktiviert ist, können Benutzer an den großen Besprechungen teilnehmen, indem Sie sich einwählen.</span><span class="sxs-lookup"><span data-stu-id="118fd-129">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="118fd-130">Unsere Tests haben ergeben, dass sich in einem Zeitraum von 10 Minuten bis zu 15 % der 1000 Benutzer einwählen konnten.</span><span class="sxs-lookup"><span data-stu-id="118fd-130">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="118fd-131">Frage: Kann ich große Topologien in einer virtuellen Topologie hosten?</span><span class="sxs-lookup"><span data-stu-id="118fd-131">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="118fd-132">Wir haben keine großen Besprechungen in einer virtuellen Topologie gehostet. Daher wird die Verwendung virtueller Computer zum Hosten eines dedizierten Pools für große Besprechungen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="118fd-132">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


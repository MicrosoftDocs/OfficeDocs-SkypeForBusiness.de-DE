---
title: 'Lync Server 2013: häufig gestellte Fragen zum Support für große Besprechungen'
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
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="1a2dc-102">Häufig gestellte Fragen zu Besprechungs Support für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a2dc-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a2dc-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1a2dc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1a2dc-104">Die folgenden Abschnitte enthalten Antworten auf häufig gestellte Fragen zum Erstellen und Ausführen großer Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="1a2dc-105">F: wie viele Benutzer können an einer großen Besprechung teilnehmen?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="1a2dc-106">Das lync Server-Benutzermodell gibt Grenzwerte für 250-Benutzer in einem freigegebenen Pool oder 1000-Benutzern in einem Pool an, die für große Besprechungen reserviert sind, aber diese Zahlen stellen nur die Anzahl der getesteten Benutzer und nur für den spezifischen Satz von Hardware dar, den wir in unseren Tests verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="1a2dc-107">Basierend auf unseren Tests empfehlen wir diese Grenzwerte für maximale Größen.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="1a2dc-108">Sie steuern jedoch die tatsächliche Anzahl der Teilnehmer, die in Besprechungen in Ihrer Organisation zulässig sind, indem Sie eine oder mehrere Konferenzrichtlinien konfigurieren (die Sie mithilfe von Windows PowerShell-Cmdlets in der lync Server-Verwaltungsshell oder mithilfe von lync Server konfigurieren. Control Panel).</span><span class="sxs-lookup"><span data-stu-id="1a2dc-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="1a2dc-109">Die Zahl, die Sie in einer konferenzrichtlinie angeben, kann eine beliebige 32-Bit-Ganzzahl zwischen 1 und 4.294.967.295 sein, aber die empfohlene Größe liegt zwischen 2 und 250 Teilnehmern inklusive; der Standardwert ist 250.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="1a2dc-110">F: wie viele Besprechungen oder andere Arbeitslasten kann ich in einem Pool haben, der großen Besprechungen gewidmet ist?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="1a2dc-111">Um eine optimale Benutzererfahrung in umfangreichen Besprechungen mit bis zu 1000 Teilnehmern zu gewährleisten, empfehlen wir, nur eine einzige große Besprechung in einem Pool zu hosten, der für große Besprechungen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="1a2dc-112">Wir empfehlen auch, keine anderen Arbeitsauslastungen für diesen Pool auszuführen, wenn die große Besprechung gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="1a2dc-113">F: sollten sich die Organisatoren großer Besprechungen im dedizierten Pool befinden?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="1a2dc-114">Nummer</span><span class="sxs-lookup"><span data-stu-id="1a2dc-114">No.</span></span> <span data-ttu-id="1a2dc-115">Es wird empfohlen, keine anderen Benutzer als die dedizierten Mitarbeiter zu unterhalten, die die Planung von umfangreichen Besprechungen im dedizierten Pool verwalten.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="1a2dc-116">Dadurch wird verhindert, dass der andere Echt Zeit Kommunikationsverkehr Probleme mit umfangreichen Besprechungen verursacht, die im Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="1a2dc-117">Sie sollten große Besprechungen im dedizierten Pool mithilfe eines Benutzerkontos des umfangreichen Besprechungs Planungs Personals planen.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="1a2dc-118">Sie sollten das Benutzerkonto des Besprechungsorganisators (der Benutzer, der eine große Besprechung anfordert) als Referent für die große Besprechung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="1a2dc-119">F: welche Medien Modalitäten kann ich in einer umfangreichen Besprechung verwenden?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="1a2dc-120">Große Besprechungen mit bis zu 1000 Benutzern können Audio, Video, PowerPoint-Freigabe, Whiteboards und Anwesenheits Abfragen umfassen.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="1a2dc-121">F: kann ich Gruppen-Instant Messaging (im) in umfangreichen Besprechungen verwenden?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="1a2dc-122">Ja.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-122">Yes.</span></span> <span data-ttu-id="1a2dc-123">Eine große Anzahl von Sofortnachrichten, vor allem, wenn Sie von einer Vielzahl von Besprechungsteilnehmern gesendet werden, kann sich aufgrund von Problemen mit dem schnellen Text Bildlauf im Chatfenster auf die Benutzerfreundlichkeit auswirken.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="1a2dc-124">Durch die Bereitstellung einer großen Anzahl von Sofortnachrichten an bis zu 1000-Benutzer können auch signifikante Serverlasten eingeführt werden, die sich auf die Leistung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="1a2dc-125">Im Allgemeinen ist Chatnachrichten nur für Fragen und Antworten (Q\&as) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="1a2dc-126">Können Benutzer an umfangreichen Besprechungen teilnehmen, indem Sie sich über ein Telefon einwählen?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="1a2dc-127">Ja.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-127">Yes.</span></span> <span data-ttu-id="1a2dc-128">Wenn der lync Server 2013-Pool ordnungsgemäß bereitgestellt und für Einwahlkonferenzen aktiviert ist, können Benutzer an den umfangreichen Besprechungen teilnehmen, indem Sie sich einwählen.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="1a2dc-129">Unsere Tests haben gezeigt, dass bis zu 15% der 1000-Nutzer über einen Zeitraum von 10 Minuten an der groß Besprechung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="1a2dc-130">F: kann ich große Besprechungen in einer virtuellen Topologie hosten?</span><span class="sxs-lookup"><span data-stu-id="1a2dc-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="1a2dc-131">Wir haben keine umfangreichen Besprechungen in einer virtuellen Topologie getestet, daher unterstützen wir nicht die Verwendung virtueller Computer, um einen dedizierten Pool für große Besprechungen zu hosten.</span><span class="sxs-lookup"><span data-stu-id="1a2dc-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: System Nutzungsberichte'
description: 'Lync Server 2013: System Nutzungsberichte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fffaf22dacbc68958e64090fd4c7d44e32f8ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562591"
---
# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="84b6a-103">System Nutzungsberichte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-103">System usage reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84b6a-104">_**Letztes Änderungsstand des Themas:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="84b6a-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="84b6a-105">In den System Nutzungsberichten werden System Nutzungsinformationen basierend auf den von der lync Server gesammelten KDS-Daten (Call Detail Recording) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="84b6a-105">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84b6a-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84b6a-106">In This Section</span></span>

  - [<span data-ttu-id="84b6a-107">Bericht über Benutzerregistrierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-107">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="84b6a-108">Enthält eine Zusammenfassung der Benutzerkonnektivität mit der lync Server 2013 Bereitstellung basierend auf Registrierungs Ereignissen wie Benutzeranmeldungen.</span><span class="sxs-lookup"><span data-stu-id="84b6a-108">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="84b6a-109">Der Bericht bietet eine Möglichkeit, sowohl interne als auch externe Anmeldungen anzuzeigen und die Anzahl der angemeldeten Benutzer mit der Anzahl der Benutzer lync Server 2013 zu vergleichen, die den Dienst tatsächlich während der Anmeldung verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="84b6a-109">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="84b6a-110">Zusammenfassender Bericht über Peer-to-Peer-Aktivitäten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-110">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="84b6a-p102">Enthält eine Zusammenfassung der Peer-zu-Peer-Sofortnachrichten-, Audio-, Video-, Dateiübertragungs- und Anwendungsfreigabesitzungen. An Peer-zu-Peer-Sitzungen sind nur zwei Benutzer beteiligt.</span><span class="sxs-lookup"><span data-stu-id="84b6a-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="84b6a-113">Zusammenfassender Konferenzbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-113">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="84b6a-114">Bietet eine Übersicht über alle Konferenzaktivitäten.</span><span class="sxs-lookup"><span data-stu-id="84b6a-114">Provides a summary of all conference activities.</span></span> <span data-ttu-id="84b6a-115">Eine Konferenz ist eine Sitzung mit mindestens drei Teilnehmern.</span><span class="sxs-lookup"><span data-stu-id="84b6a-115">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="84b6a-116">Zusammenfassender PSTN-Konferenzbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-116">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="84b6a-p104">Bietet eine Übersicht über alle PSTN-Konferenzen. Dies sind Konferenzen, bei denen sich mindestens ein Benutzer über das Festnetz (Public Switched Telephone Network, PSTN) einwählt. Sie werden auch als *Einwahlkonferenzen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="84b6a-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="84b6a-119">Verwendungsbericht für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-119">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="84b6a-120">Enthält eine Übersicht über die Verwendung von Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="84b6a-120">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="84b6a-121">Das Reaktionsgruppenanwendung bietet Ihnen die Möglichkeit, Telefonanrufe automatisch an Entitäten wie ein Helpdesk oder eine Kunden Unterstützungsleitung weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="84b6a-121">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="84b6a-122">Inventurbericht über IP-Telefone in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-122">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="84b6a-123">Enthält Informationen zu den derzeit in der Organisation verwendeten IP-Telefonen.</span><span class="sxs-lookup"><span data-stu-id="84b6a-123">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="84b6a-124">Der Bericht basiert auf Telefon Registrierungen und Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="84b6a-124">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="84b6a-125">Es sollte nicht als vollständiger bestand betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="84b6a-125">It should not be considered a complete inventory.</span></span> <span data-ttu-id="84b6a-126">Beispielsweise haben Sie möglicherweise Telefone entfernt, die noch im Bericht aufgeführt sind, da Sie sich mindestens einmal angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="84b6a-126">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="84b6a-127">Ebenso können Sie auch neue Telefone haben, die nicht im Bericht angezeigt werden, nur weil sich Benutzer noch nicht bei lync Server mit ihren neuen Telefonen angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="84b6a-127">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="84b6a-128">Anrufsteuerungsbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b6a-128">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="84b6a-p107">Enthält eine Liste der Peer-zu-Peer- und Konferenzaktivitäten, für die Anrufsteuerung (Call Admission Control, CAC) verwendet wird. Mithilfe der Anrufsteuerung können Sie feststellen, ob ausgehend von etwaigen Bandbreiteneinschränkungen Echtzeitkommunikationssitzungen (z. B. Sprach- oder Videoanrufe) hergestellt werden können sollen.</span><span class="sxs-lookup"><span data-stu-id="84b6a-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


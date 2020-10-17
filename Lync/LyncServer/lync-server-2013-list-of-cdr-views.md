---
title: 'Lync Server 2013: Liste der KDS-Ansichten'
description: 'Lync Server 2013: Liste der KDS-Ansichten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550081"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="add6d-103">Liste der KDS-Ansichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="add6d-103">List of CDR views in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="add6d-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="add6d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="add6d-105">Ansichten bieten eine einfache Möglichkeit, auf Informationen zu den am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der KDS-Datenbank zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="add6d-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="add6d-106">Es wird empfohlen, Ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt die tatsächlichen KDS-Datenbanktabellen zu verwenden. Das liegt daran, dass die Datenbankansichten eher die Abwärtskompatibilität mit zukünftigen Versionen von lync Server aufrecht erhalten.</span><span class="sxs-lookup"><span data-stu-id="add6d-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="add6d-107">Sichtname</span><span class="sxs-lookup"><span data-stu-id="add6d-107">View Name</span></span></th>
<th><span data-ttu-id="add6d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="add6d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="add6d-109"><a href="lync-server-2013-clientversions-view.md">Client Versions-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-109"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-110">Gibt Informationen zu den in einer Kommunikationssitzung verwendeten Clientsoftwareanwendungen/Geräten zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-110">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-111"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-111"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-112">Gibt Informationen zu der Anzahl der von Benutzern in einer Konferenz gesendeten Nachrichten zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-112">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-113"><a href="lync-server-2013-conferences-view.md">Ansicht "Konferenzen" in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-113"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-114">Gibt Konferenzinformationen zurück, einschließlich Startzeit, Endzeit und Konferenzorganisator.</span><span class="sxs-lookup"><span data-stu-id="add6d-114">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-115"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-115"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-116">Gibt Sitzungsdetails zu allen Konferenzsitzungen zurück, einschließlich Start- und Endzeit, Benutzer-IDs, Antwortcodes und Diagnose-IDs.</span><span class="sxs-lookup"><span data-stu-id="add6d-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-117"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-117"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-118">Gibt Informationen zu den in einer Konferenz verwendeten Konferenz-URIs zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-118">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-119"><a href="lync-server-2013-errorreport-view.md">ErrorReport-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-119"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-120">Gibt Informationen zu Fehlern zurück, die in einer Sitzung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="add6d-120">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-121"><a href="lync-server-2013-filetransfers-view.md">Filetransfers-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-121"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-122">Gibt Informationen zu Dateiübertragungssitzungen zurück. Hierzu gehören der Dateiname und Angaben dazu, ob die Übertragung akzeptiert, abgelehnt oder abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="add6d-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-123"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-123"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-124">Gibt Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-124">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-125"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-125"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-126">Gibt kombinierte Informationen zu Aktivitäten zum Beitreten oder Verlassen einer Konferenz zurück (jeder Konferenzbeitritt ist entsprechend mit dem Verlassen einer Konferenz gepaart).</span><span class="sxs-lookup"><span data-stu-id="add6d-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-127"><a href="lync-server-2013-mcus-view.md">MCU-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-127"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-128">Gibt Informationen zu Konferenzservern zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-128">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-129"><a href="lync-server-2013-media-view.md">Medienansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-129"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-130">Gibt Informationen zu den Medientypen zurück, die in Peer-zu-Peer-Kommunikationssitzungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="add6d-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-131"><a href="lync-server-2013-progressreport-view.md">ProgressReport-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-131"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-132">Gibt Informationen zu beendeten Konferenzsitzungen zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-132">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-133"><a href="lync-server-2013-registration-view.md">Registrierungs Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-133"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-134">Gibt Informationen zu Registrierungen mit lync Server zurück.</span><span class="sxs-lookup"><span data-stu-id="add6d-134">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-135"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-135"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-136">Gibt Informationen zu Peer-zu-Peer-Sitzungen zurück, einschließlich Telefonanrufen von VoIP zu VoIP, Chatsitzungen mit zwei Teilnehmern oder anderen Peer-zu-Peer-Kommunikationssitzungen.</span><span class="sxs-lookup"><span data-stu-id="add6d-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="add6d-137"><a href="lync-server-2013-user-view.md">Benutzeransicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-137"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-138">Gibt Informationen zu den Benutzern zurück, die an Kommunikationssitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="add6d-138">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="add6d-139"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="add6d-139"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="add6d-140">Gibt Informationen zu Peer-to-Peer-Sitzungen zurück, an denen mindestens ein VoIP-Benutzer beteiligt war.</span><span class="sxs-lookup"><span data-stu-id="add6d-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


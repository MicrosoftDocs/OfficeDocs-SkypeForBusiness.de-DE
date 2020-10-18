---
title: 'Lync Server 2013: ProgressReport-Ansicht'
description: 'Lync Server 2013: ProgressReport-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579791"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="df2f5-103">ProgressReport-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df2f5-103">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df2f5-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="df2f5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="df2f5-105">Die ProgressReport-Ansicht speichert Informationen über abgeschlossene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="df2f5-105">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="df2f5-106">Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt.</span><span class="sxs-lookup"><span data-stu-id="df2f5-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="df2f5-107">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="df2f5-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df2f5-108">Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="df2f5-108">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df2f5-109">Spalte</span><span class="sxs-lookup"><span data-stu-id="df2f5-109">Column</span></span></th>
<th><span data-ttu-id="df2f5-110">Datentyp</span><span class="sxs-lookup"><span data-stu-id="df2f5-110">Data Type</span></span></th>
<th><span data-ttu-id="df2f5-111">Details</span><span class="sxs-lookup"><span data-stu-id="df2f5-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df2f5-112"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-113">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="df2f5-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="df2f5-p102">Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="df2f5-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df2f5-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-117">int</span><span class="sxs-lookup"><span data-stu-id="df2f5-117">int</span></span></p></td>
<td><p><span data-ttu-id="df2f5-p103">ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="df2f5-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df2f5-120"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-120"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-121">int</span><span class="sxs-lookup"><span data-stu-id="df2f5-121">int</span></span></p></td>
<td><p><span data-ttu-id="df2f5-122">ID zum Bestimmen des Fortschrittsberichts.</span><span class="sxs-lookup"><span data-stu-id="df2f5-122">ID to identify the progress report.</span></span> <span data-ttu-id="df2f5-123">Wird zum Unterscheiden von Fortschrittsberichten desselben Fehlerberichts verwendet.</span><span class="sxs-lookup"><span data-stu-id="df2f5-123">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df2f5-124"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-124"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-125">int</span><span class="sxs-lookup"><span data-stu-id="df2f5-125">int</span></span></p></td>
<td><p><span data-ttu-id="df2f5-126">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="df2f5-126">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df2f5-127"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-127"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df2f5-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df2f5-129">Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="df2f5-129">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df2f5-130"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-130"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="df2f5-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="df2f5-132">Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="df2f5-132">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df2f5-133"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-133"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="df2f5-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="df2f5-135">Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="df2f5-135">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df2f5-136"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-136"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-137">int</span><span class="sxs-lookup"><span data-stu-id="df2f5-137">int</span></span></p></td>
<td><p><span data-ttu-id="df2f5-138">Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="df2f5-138">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df2f5-139"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="df2f5-139"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="df2f5-140">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="df2f5-140">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="df2f5-141">Zusätzliche Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="df2f5-141">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: ProgressReport-Ansicht'
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
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="88291-102">ProgressReport-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88291-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88291-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="88291-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="88291-104">In der ProgressReport-Ansicht werden Informationen zu abgeschlossenen Sitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="88291-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="88291-105">Fortschrittsberichte werden nur für Anrufe und Sitzungen geschrieben, die von lync Server 2013 für diagnostische Zwecke nützlich sein können.</span><span class="sxs-lookup"><span data-stu-id="88291-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="88291-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="88291-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88291-107">Die Felder "Fehler", "ErrorReportSeq" und "ProgressReportSeq" beziehen sich nicht unbedingt auf Fehler, sondern auf Nachrichten, die den Status von anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="88291-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88291-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="88291-108">Column</span></span></th>
<th><span data-ttu-id="88291-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="88291-109">Data Type</span></span></th>
<th><span data-ttu-id="88291-110">Details</span><span class="sxs-lookup"><span data-stu-id="88291-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88291-111"><strong>Fehlerzeit</strong></span><span class="sxs-lookup"><span data-stu-id="88291-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-112">datetime</span><span class="sxs-lookup"><span data-stu-id="88291-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="88291-113">Zeitpunkt des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="88291-113">Time of error occurred.</span></span> <span data-ttu-id="88291-114">Wird in Verbindung mit ErrorReportSeq verwendet, um einen Fehler eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="88291-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88291-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88291-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-116">int</span><span class="sxs-lookup"><span data-stu-id="88291-116">int</span></span></p></td>
<td><p><span data-ttu-id="88291-117">Die ID-Nummer, um den Fehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="88291-117">ID number to identify the error.</span></span> <span data-ttu-id="88291-118">Wird in Verbindung mit Fehlerzeit verwendet, um einen Fehler eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="88291-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88291-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88291-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-120">int</span><span class="sxs-lookup"><span data-stu-id="88291-120">int</span></span></p></td>
<td><p><span data-ttu-id="88291-121">ID zum Identifizieren des Statusberichts</span><span class="sxs-lookup"><span data-stu-id="88291-121">ID to identify the progress report.</span></span> <span data-ttu-id="88291-122">Wird verwendet, um Fortschrittsberichte desselben Fehlerberichts zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="88291-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88291-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="88291-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-124">int</span><span class="sxs-lookup"><span data-stu-id="88291-124">int</span></span></p></td>
<td><p><span data-ttu-id="88291-125">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="88291-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88291-126"><strong>Quelle</strong></span><span class="sxs-lookup"><span data-stu-id="88291-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88291-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="88291-128">Name des Servers, der den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="88291-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88291-129"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="88291-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88291-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="88291-131">Der Name der Anwendung, die den Fehler verursacht hat (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="88291-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88291-132"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="88291-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="88291-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="88291-134">Eindeutiger Bezeichner, in dem die Verknüpfungszeit Informationen für die verschiedenen an einer Konferenz beteiligten Komponenten korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="88291-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88291-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="88291-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-136">int</span><span class="sxs-lookup"><span data-stu-id="88291-136">int</span></span></p></td>
<td><p><span data-ttu-id="88291-137">Zeit (in Millisekunden), die für eine bestimmte Komponente erforderlich ist, um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="88291-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88291-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="88291-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="88291-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="88291-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="88291-140">Weitere Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="88291-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


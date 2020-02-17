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
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="9d03e-102">ProgressReport-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d03e-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d03e-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9d03e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9d03e-104">Die ProgressReport-Ansicht speichert Informationen über abgeschlossene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="9d03e-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="9d03e-105">Fortschrittsberichte werden nur für Anrufe geschrieben und für Sitzungen, die Lync Server 2013 als hilfreich für Diagnosezwecke ermittelt.</span><span class="sxs-lookup"><span data-stu-id="9d03e-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="9d03e-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9d03e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9d03e-107">Die Felder ErrorTime, ErrorReportSeq und ProgressReportSeq verweisen nicht notwendigerweise auf Fehler, sondern auf Nachrichten, die den Status von Anrufen oder Nachrichten angeben.</span><span class="sxs-lookup"><span data-stu-id="9d03e-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d03e-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="9d03e-108">Column</span></span></th>
<th><span data-ttu-id="9d03e-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9d03e-109">Data Type</span></span></th>
<th><span data-ttu-id="9d03e-110">Details</span><span class="sxs-lookup"><span data-stu-id="9d03e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d03e-111"><strong>Fehler</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="9d03e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="9d03e-p102">Zeitpunkt des Fehlers. Wird zusammen mit "ErrorReportSeq" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9d03e-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d03e-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-116">int</span><span class="sxs-lookup"><span data-stu-id="9d03e-116">int</span></span></p></td>
<td><p><span data-ttu-id="9d03e-p103">ID-Nummer zum Bestimmen des Fehlers. Wird zusammen mit "ErrorTime" verwendet, um einen Fehler eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9d03e-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d03e-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-120">int</span><span class="sxs-lookup"><span data-stu-id="9d03e-120">int</span></span></p></td>
<td><p><span data-ttu-id="9d03e-121">ID zum Bestimmen des Fortschrittsberichts.</span><span class="sxs-lookup"><span data-stu-id="9d03e-121">ID to identify the progress report.</span></span> <span data-ttu-id="9d03e-122">Wird zum Unterscheiden von Fortschrittsberichten desselben Fehlerberichts verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d03e-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d03e-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-124">int</span><span class="sxs-lookup"><span data-stu-id="9d03e-124">int</span></span></p></td>
<td><p><span data-ttu-id="9d03e-125">Diagnose-ID für den Fehlerbericht.</span><span class="sxs-lookup"><span data-stu-id="9d03e-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d03e-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9d03e-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9d03e-128">Name des Servers, von dem der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="9d03e-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d03e-129"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9d03e-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9d03e-131">Name der Anwendung, von der der Fehler stammt (wenn der Bericht von einer Serverkomponente gesendet wurde).</span><span class="sxs-lookup"><span data-stu-id="9d03e-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d03e-132"><strong>Telemetrie</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9d03e-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9d03e-134">Eindeutiger Bezeichner, der die Informationen über den Zeitpunkt des Beitritts für verschiedene in einer Konferenz beteiligten Komponenten korreliert.</span><span class="sxs-lookup"><span data-stu-id="9d03e-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d03e-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-136">int</span><span class="sxs-lookup"><span data-stu-id="9d03e-136">int</span></span></p></td>
<td><p><span data-ttu-id="9d03e-137">Für eine bestimmte Komponente erforderliche Zeit (in Millisekunden), um an einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9d03e-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d03e-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="9d03e-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="9d03e-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9d03e-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9d03e-140">Zusätzliche Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="9d03e-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


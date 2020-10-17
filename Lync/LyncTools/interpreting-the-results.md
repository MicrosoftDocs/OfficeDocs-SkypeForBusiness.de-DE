---
title: Interpretieren der Ergebnisse
description: Interpretieren der Ergebnisse.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565341"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="5cc9c-103">Interpretieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="5cc9c-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cc9c-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="5cc9c-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="5cc9c-105">Das lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) verfügt über zahlreiche Leistungsindikatoren, die Sie verwenden können, um zu verstehen, was der Client ausführt und ob Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="5cc9c-106">Client Indikatoren</span><span class="sxs-lookup"><span data-stu-id="5cc9c-106">Client Counters</span></span>

<span data-ttu-id="5cc9c-107">Jede Instanz von LyncPerfTool.exe, die ausgeführt wird, verfügt über eine separate Instanz der Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="5cc9c-108">Jede Instanz hat ihren Namen durch die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="5cc9c-109">Wenn die Clients überladen sind, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="5cc9c-110">Um diese Probleme zu vermeiden, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="5cc9c-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="5cc9c-111">Überwachen Sie die CPU und die Arbeitsspeicherauslastung auf den Clientcomputern.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="5cc9c-112">Wenn die CPU konstant über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="5cc9c-113">Wenn der Speicherplatzbedarf hoch ist, können Probleme auftreten, wenn die Auslagerungsdatei nicht groß genug ist.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="5cc9c-114">Stellen Sie sicher, dass die Commit-Gebühr nicht auf den Computer beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="5cc9c-115">Wenn Sie Arbeitsspeichergrenzwerte verwenden, sollten Sie die Größe der Auslagerungsdatei erhöhen oder die Anzahl der Benutzer reduzieren.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="5cc9c-116">In den folgenden Tabellen sind die wichtigsten LyncPerfTool-Leistungsindikatoren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="5cc9c-117">**Allgemeine Informationen**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-118"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-119"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-120">In Minuten verbrachte Zeit</span><span class="sxs-lookup"><span data-stu-id="5cc9c-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-121">Zeitaufwand seit Beginn des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-122">Aktive Endpunkte</span><span class="sxs-lookup"><span data-stu-id="5cc9c-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-123">Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-124">Fehlgeschlagene Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="5cc9c-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-125">Gesamtzahl der Endpunkt Anmeldungsfehler.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-126">Anmeldeversuche</span><span class="sxs-lookup"><span data-stu-id="5cc9c-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-127">Gesamtzahl der Endpunkt Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-128">Endpunkte getrennt</span><span class="sxs-lookup"><span data-stu-id="5cc9c-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-129">Die Gesamtzahl der Endpunkte, die getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-130">**Anwesenheitsinformationen**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-131"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-132"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-133">SetPresence-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-134">Die Gesamtzahl der Anwesenheits Änderungsversuche.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-134">Total number of presence change attempts.</span></span> <span data-ttu-id="5cc9c-135">Informationen zu verschiedenen Arten von Anwesenheitsänderungen finden Sie unter SetPresence (Anwesenheits) Aufrufe Leistungsindikator.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-136">NNN-Antworten für SetPresence</span><span class="sxs-lookup"><span data-stu-id="5cc9c-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-137">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-138">GetPresence-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-139">Die Gesamtzahl der Versuche zum Abrufen von Anwesenheits Anfragen.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-140">NNN-Antworten für GetPresence</span><span class="sxs-lookup"><span data-stu-id="5cc9c-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-141">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-142">**Informationen zum Adressbuchdienst**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-142">**Address Book service Information**</span></span>

<span data-ttu-id="5cc9c-143">Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Dateidownloads für den Adressbuchdienst (ABS) und Adressbuch-Webabfragedienst Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-144"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-145"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-146">Versuchtes ABS Full/Delta file Downloads</span><span class="sxs-lookup"><span data-stu-id="5cc9c-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-147">Die Gesamtzahl der versuchten Downloadanforderungen für vollständige oder Deltadateien.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-148">ABS Full/Delta Datei Downloads erfolgreich</span><span class="sxs-lookup"><span data-stu-id="5cc9c-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-149">Die Gesamtzahl der versuchten Downloadanforderungen für vollständige oder Deltadateien.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-150">Adressbuch-Webabfragedienst zugehörige Indikatoren</span><span class="sxs-lookup"><span data-stu-id="5cc9c-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-151">Adressbuchdatei-Download bezogene Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-152">Versuchtes ABS WS-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-153">Die Gesamtzahl der versuchten Adressbuch-Webabfragedienst Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-154">ABS WS-Aufrufe erfolgreich</span><span class="sxs-lookup"><span data-stu-id="5cc9c-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-155">Die Gesamtzahl der Adressbuch-Webabfragedienst Anforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-156">ABS WS-Aufrufe fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="5cc9c-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-157">Die Gesamtzahl der Adressbuch-Webabfragedienst Anforderungen, die einen Fehlerantwort Code zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-158">**Informationen zur Verteilerliste (DL)**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-159"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-160"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-161">Anrufe versucht</span><span class="sxs-lookup"><span data-stu-id="5cc9c-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-162">Die Gesamtzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung (dlx).</span><span class="sxs-lookup"><span data-stu-id="5cc9c-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-163">Erfolgreiche Aufrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-164">Die Gesamtzahl der dlx-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-165">Anrufe sind fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="5cc9c-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-166">Die Gesamtzahl der dlx-Webdienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-167">**VoIP-Basisinformationen**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="5cc9c-168">Die unten aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Aufrufen von Vermittlungsserver, A/V-Konferenzserver, Edgeserver, Reaktionsgruppenanwendung und der automatischen Telefonzentrale für Konferenzen, wenn diese Szenarien aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-169"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-170"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-171">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-172">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die derzeit fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-173">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="5cc9c-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-174">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die bereits beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-175">Anrufe abgelehnt</span><span class="sxs-lookup"><span data-stu-id="5cc9c-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-176">Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-177">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-178">Die Gesamtzahl der versuchten eingehenden/ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-179">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="5cc9c-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-180">Gesamtzahl der eingerichteten eingehenden/ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-181">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="5cc9c-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-182">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-183">VoIP-Durchlauf Rate (%)</span><span class="sxs-lookup"><span data-stu-id="5cc9c-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-184">Gesamtzahl der eingestellten Anrufe/Gesamtzahl der Anrufe wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-185">**Anrufinformationen für den Reaktionsgruppendienst**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-186"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-187"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-188">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-189">Die Gesamtzahl der aktiven Anrufe an die Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-190">Anrufe versucht</span><span class="sxs-lookup"><span data-stu-id="5cc9c-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-191">Die Gesamtzahl der versuchten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-192">**Anrufinformationen für Chatnachrichten**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-193"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-194"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-195">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-196">Gesamtzahl der laufenden eingehenden/ausgehenden Sofortnachrichten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-197">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="5cc9c-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-198">Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe, die bereits beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-199">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="5cc9c-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-200">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-201">Empfangene/Gesendete Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="5cc9c-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-202">Die Gesamtzahl der empfangenen oder gesendeten Nachrichten für alle Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-203">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-204">Die Gesamtzahl der versuchten eingehenden/ausgehenden Sofortnachrichten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-205">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="5cc9c-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-206">Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe, die eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-207">**Informationen zum App-Freigabe Anruf**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-208"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-209"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-210">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-211">Die Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-212">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="5cc9c-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-213">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde bereits beendet.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-214">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="5cc9c-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-215">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-216">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-217">Die Gesamtzahl der versuchten eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-218">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="5cc9c-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-219">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe, die eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-220">**Informationen zu CAA-anrufen**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-221"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-222"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-223">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-224">Die Gesamtzahl der eingehenden und ausgehenden PSTN-Anrufe (Public Switched Telephone Network), die derzeit fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-225">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="5cc9c-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-226">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe, die bereits beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-227">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="5cc9c-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-228">Die Gesamtzahl der versuchten eingehenden/ausgehenden PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-229">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="5cc9c-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-230">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe, die eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-231">**Konferenz Informationen**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-232"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-233"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-234">Aktive Sofortnachrichtenkonferenzen</span><span class="sxs-lookup"><span data-stu-id="5cc9c-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-235">Gesamtzahl der laufenden Sofortnachrichtenkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-236">Aktive Audio/Video Konferenzen</span><span class="sxs-lookup"><span data-stu-id="5cc9c-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-237">Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).</span><span class="sxs-lookup"><span data-stu-id="5cc9c-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-238">Aktive Anwendungsfreigabe Konferenzen</span><span class="sxs-lookup"><span data-stu-id="5cc9c-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-239">Die Gesamtzahl der laufenden Konferenzen für die Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-240">Anzahl der Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="5cc9c-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-241">Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-242">Ausfall des Konferenz Zeitplans</span><span class="sxs-lookup"><span data-stu-id="5cc9c-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-243">Die Gesamtzahl der Fehler beim Planen einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-244">Konferenz Fehler beitreten</span><span class="sxs-lookup"><span data-stu-id="5cc9c-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-245">Die Gesamtzahl der Fehler beim Versuch, eine Verbindung mit einer Konferenz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cc9c-246">**UCWA-Client Indikatoren**</span><span class="sxs-lookup"><span data-stu-id="5cc9c-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cc9c-247"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5cc9c-248"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="5cc9c-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cc9c-249">Gesamtanzahl der erfolgreichen IMMCU-Joins</span><span class="sxs-lookup"><span data-stu-id="5cc9c-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-250">Die Gesamtzahl der beigetretenen Sofortnachrichtenkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cc9c-251">Gesamtanzahl der erfolgreichen DMCU-Joins</span><span class="sxs-lookup"><span data-stu-id="5cc9c-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5cc9c-252">Die Gesamtzahl der A/V-Konferenzen, die beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="5cc9c-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


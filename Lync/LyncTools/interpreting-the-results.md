---
title: Interpretieren der Ergebnisse
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
ms.openlocfilehash: f3a15880de861b850d3e0355491e85219ba3579d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499912"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="a9b5c-102">Interpretieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="a9b5c-102">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9b5c-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a9b5c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a9b5c-104">Das lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) verfügt über zahlreiche Leistungsindikatoren, die Sie verwenden können, um zu verstehen, was der Client ausführt und ob Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="a9b5c-105">Client Indikatoren</span><span class="sxs-lookup"><span data-stu-id="a9b5c-105">Client Counters</span></span>

<span data-ttu-id="a9b5c-106">Jede Instanz von LyncPerfTool.exe, die ausgeführt wird, verfügt über eine separate Instanz der Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="a9b5c-107">Jede Instanz hat ihren Namen durch die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="a9b5c-108">Wenn die Clients überladen sind, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="a9b5c-109">Um diese Probleme zu vermeiden, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a9b5c-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="a9b5c-110">Überwachen Sie die CPU und die Arbeitsspeicherauslastung auf den Clientcomputern.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="a9b5c-111">Wenn die CPU konstant über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="a9b5c-112">Wenn der Speicherplatzbedarf hoch ist, können Probleme auftreten, wenn die Auslagerungsdatei nicht groß genug ist.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="a9b5c-113">Stellen Sie sicher, dass die Commit-Gebühr nicht auf den Computer beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="a9b5c-114">Wenn Sie Arbeitsspeichergrenzwerte verwenden, sollten Sie die Größe der Auslagerungsdatei erhöhen oder die Anzahl der Benutzer reduzieren.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="a9b5c-115">In den folgenden Tabellen sind die wichtigsten LyncPerfTool-Leistungsindikatoren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="a9b5c-116">**Allgemeine Informationen**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-117"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-118"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-119">In Minuten verbrachte Zeit</span><span class="sxs-lookup"><span data-stu-id="a9b5c-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-120">Zeitaufwand seit Beginn des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-121">Aktive Endpunkte</span><span class="sxs-lookup"><span data-stu-id="a9b5c-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-122">Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-123">Fehlgeschlagene Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="a9b5c-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-124">Gesamtzahl der Endpunkt Anmeldungsfehler.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-125">Anmeldeversuche</span><span class="sxs-lookup"><span data-stu-id="a9b5c-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-126">Gesamtzahl der Endpunkt Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-127">Endpunkte getrennt</span><span class="sxs-lookup"><span data-stu-id="a9b5c-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-128">Die Gesamtzahl der Endpunkte, die getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-129">**Anwesenheitsinformationen**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-130"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-131"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-132">SetPresence-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-133">Die Gesamtzahl der Anwesenheits Änderungsversuche.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-133">Total number of presence change attempts.</span></span> <span data-ttu-id="a9b5c-134">Informationen zu verschiedenen Arten von Anwesenheitsänderungen finden Sie unter SetPresence (Anwesenheits) Aufrufe Leistungsindikator.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-135">NNN-Antworten für SetPresence</span><span class="sxs-lookup"><span data-stu-id="a9b5c-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-136">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-137">GetPresence-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-138">Die Gesamtzahl der Versuche zum Abrufen von Anwesenheits Anfragen.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-139">NNN-Antworten für GetPresence</span><span class="sxs-lookup"><span data-stu-id="a9b5c-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-140">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-141">**Informationen zum Adressbuchdienst**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-141">**Address Book service Information**</span></span>

<span data-ttu-id="a9b5c-142">Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Dateidownloads für den Adressbuchdienst (ABS) und Adressbuch-Webabfragedienst Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-143"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-144"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-145">Versuchtes ABS Full/Delta file Downloads</span><span class="sxs-lookup"><span data-stu-id="a9b5c-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-146">Die Gesamtzahl der versuchten Downloadanforderungen für vollständige oder Deltadateien.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-147">ABS Full/Delta Datei Downloads erfolgreich</span><span class="sxs-lookup"><span data-stu-id="a9b5c-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-148">Die Gesamtzahl der versuchten Downloadanforderungen für vollständige oder Deltadateien.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-149">Adressbuch-Webabfragedienst zugehörige Indikatoren</span><span class="sxs-lookup"><span data-stu-id="a9b5c-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-150">Adressbuchdatei-Download bezogene Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-151">Versuchtes ABS WS-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-152">Die Gesamtzahl der versuchten Adressbuch-Webabfragedienst Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-153">ABS WS-Aufrufe erfolgreich</span><span class="sxs-lookup"><span data-stu-id="a9b5c-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-154">Die Gesamtzahl der Adressbuch-Webabfragedienst Anforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-155">ABS WS-Aufrufe fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="a9b5c-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-156">Die Gesamtzahl der Adressbuch-Webabfragedienst Anforderungen, die einen Fehlerantwort Code zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-157">**Informationen zur Verteilerliste (DL)**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-158"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-159"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-160">Anrufe versucht</span><span class="sxs-lookup"><span data-stu-id="a9b5c-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-161">Die Gesamtzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung (dlx).</span><span class="sxs-lookup"><span data-stu-id="a9b5c-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-162">Erfolgreiche Aufrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-163">Die Gesamtzahl der dlx-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-164">Anrufe sind fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="a9b5c-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-165">Die Gesamtzahl der dlx-Webdienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-166">**VoIP-Basisinformationen**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="a9b5c-167">Die unten aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Aufrufen von Vermittlungsserver, A/V-Konferenzserver, Edgeserver, Reaktionsgruppenanwendung und der automatischen Telefonzentrale für Konferenzen, wenn diese Szenarien aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-168"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-169"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-170">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-171">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die derzeit fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-172">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="a9b5c-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-173">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die bereits beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-174">Anrufe abgelehnt</span><span class="sxs-lookup"><span data-stu-id="a9b5c-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-175">Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-176">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-177">Die Gesamtzahl der versuchten eingehenden/ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-178">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="a9b5c-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-179">Gesamtzahl der eingerichteten eingehenden/ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-180">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="a9b5c-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-181">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-182">VoIP-Durchlauf Rate (%)</span><span class="sxs-lookup"><span data-stu-id="a9b5c-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-183">Gesamtzahl der eingestellten Anrufe/Gesamtzahl der Anrufe wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-184">**Anrufinformationen für den Reaktionsgruppendienst**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-185"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-186"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-187">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-188">Die Gesamtzahl der aktiven Anrufe an die Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-189">Anrufe versucht</span><span class="sxs-lookup"><span data-stu-id="a9b5c-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-190">Die Gesamtzahl der versuchten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-191">**Anrufinformationen für Chatnachrichten**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-192"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-193"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-194">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-195">Gesamtzahl der laufenden eingehenden/ausgehenden Sofortnachrichten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-196">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="a9b5c-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-197">Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe, die bereits beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-198">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="a9b5c-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-199">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-200">Empfangene/Gesendete Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="a9b5c-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-201">Die Gesamtzahl der empfangenen oder gesendeten Nachrichten für alle Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-202">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-203">Die Gesamtzahl der versuchten eingehenden/ausgehenden Sofortnachrichten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-204">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="a9b5c-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-205">Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe, die eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-206">**Informationen zum App-Freigabe Anruf**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-207"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-208"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-209">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-210">Die Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-211">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="a9b5c-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-212">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde bereits beendet.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-213">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="a9b5c-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-214">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-215">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-216">Die Gesamtzahl der versuchten eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-217">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="a9b5c-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-218">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe, die eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-219">**Informationen zu CAA-anrufen**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-220"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-221"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-222">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-223">Die Gesamtzahl der eingehenden und ausgehenden PSTN-Anrufe (Public Switched Telephone Network), die derzeit fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-224">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="a9b5c-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-225">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe, die bereits beendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-226">Versuchten eingehenden/ausgehenden Anrufe</span><span class="sxs-lookup"><span data-stu-id="a9b5c-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-227">Die Gesamtzahl der versuchten eingehenden/ausgehenden PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-228">Eingehende/ausgehende Anrufe wurden hergestellt</span><span class="sxs-lookup"><span data-stu-id="a9b5c-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-229">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe, die eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-230">**Konferenz Informationen**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-231"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-232"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-233">Aktive Sofortnachrichtenkonferenzen</span><span class="sxs-lookup"><span data-stu-id="a9b5c-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-234">Gesamtzahl der laufenden Sofortnachrichtenkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-235">Aktive Audio/Video Konferenzen</span><span class="sxs-lookup"><span data-stu-id="a9b5c-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-236">Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).</span><span class="sxs-lookup"><span data-stu-id="a9b5c-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-237">Aktive Anwendungsfreigabe Konferenzen</span><span class="sxs-lookup"><span data-stu-id="a9b5c-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-238">Die Gesamtzahl der laufenden Konferenzen für die Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-239">Anzahl der Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="a9b5c-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-240">Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-241">Ausfall des Konferenz Zeitplans</span><span class="sxs-lookup"><span data-stu-id="a9b5c-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-242">Die Gesamtzahl der Fehler beim Planen einer Konferenz.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-243">Konferenz Fehler beitreten</span><span class="sxs-lookup"><span data-stu-id="a9b5c-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-244">Die Gesamtzahl der Fehler beim Versuch, eine Verbindung mit einer Konferenz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9b5c-245">**UCWA-Client Indikatoren**</span><span class="sxs-lookup"><span data-stu-id="a9b5c-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b5c-246"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a9b5c-247"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="a9b5c-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b5c-248">Gesamtanzahl der erfolgreichen IMMCU-Joins</span><span class="sxs-lookup"><span data-stu-id="a9b5c-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-249">Die Gesamtzahl der beigetretenen Sofortnachrichtenkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b5c-250">Gesamtanzahl der erfolgreichen DMCU-Joins</span><span class="sxs-lookup"><span data-stu-id="a9b5c-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a9b5c-251">Die Gesamtzahl der A/V-Konferenzen, die beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="a9b5c-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


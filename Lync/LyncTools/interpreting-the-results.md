---
title: Interpretieren der Ergebnisse
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="11150-102">Interpretieren der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="11150-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11150-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="11150-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="11150-104">Das lync Server 2013-Stress-und-Leistungs Tool (LyncPerfTool. exe) bietet zahlreiche Leistungsindikatoren, mit denen Sie verstehen können, was der Client tut und ob Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="11150-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="11150-105">Client-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="11150-105">Client Counters</span></span>

<span data-ttu-id="11150-106">Jede Instanz von LyncPerfTool. exe, die ausgeführt wird, verfügt über eine separate Instanz der Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="11150-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="11150-107">Jede Instanz wird durch ihre Prozess-ID benannt.</span><span class="sxs-lookup"><span data-stu-id="11150-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="11150-108">Wenn die Clients überladen sind, können Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="11150-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="11150-109">Gehen Sie wie folgt vor, um diese Probleme zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="11150-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="11150-110">Überwachen Sie die CPU und die Speicherauslastung auf den Clientcomputern.</span><span class="sxs-lookup"><span data-stu-id="11150-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="11150-111">Wenn die CPU konstant über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="11150-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="11150-112">Bei einem hohen Speicherbedarf können Probleme auftreten, wenn die Auslagerungsdatei nicht groß genug ist.</span><span class="sxs-lookup"><span data-stu-id="11150-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="11150-113">Überprüfen Sie, ob die Commit-Belastung auf dem Computer nicht auf das Limit trifft.</span><span class="sxs-lookup"><span data-stu-id="11150-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="11150-114">Wenn Sie Speichergrenzwerte verwenden, können Sie die Größe der Auslagerungsdatei erhöhen oder die Anzahl der Benutzer reduzieren.</span><span class="sxs-lookup"><span data-stu-id="11150-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="11150-115">In den folgenden Tabellen sind die wichtigsten LyncPerfTool-Leistungsindikatoren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="11150-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="11150-116">**Allgemeine Informationen**</span><span class="sxs-lookup"><span data-stu-id="11150-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-117"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-118"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-119">In Minuten verbrachte Zeit</span><span class="sxs-lookup"><span data-stu-id="11150-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="11150-120">Die Zeit, die seit dem Start des Prozesses aufgewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="11150-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-121">Aktive Endpunkte</span><span class="sxs-lookup"><span data-stu-id="11150-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="11150-122">Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="11150-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-123">Fehlgeschlagene Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="11150-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="11150-124">Die Gesamtzahl der Endpunkt Anmeldungsfehler.</span><span class="sxs-lookup"><span data-stu-id="11150-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-125">Anmeldeversuche</span><span class="sxs-lookup"><span data-stu-id="11150-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="11150-126">Die Gesamtzahl der Endpunkt Anmeldeversuche.</span><span class="sxs-lookup"><span data-stu-id="11150-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-127">Endpunkte getrennt</span><span class="sxs-lookup"><span data-stu-id="11150-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="11150-128">Die Gesamtzahl der Endpunkte, die getrennt wurden.</span><span class="sxs-lookup"><span data-stu-id="11150-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-129">**Anwesenheitsinformationen**</span><span class="sxs-lookup"><span data-stu-id="11150-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-130"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-131"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-132">SetPresence-Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="11150-133">Die Gesamtzahl der Anwesenheits Änderungsversuche.</span><span class="sxs-lookup"><span data-stu-id="11150-133">Total number of presence change attempts.</span></span> <span data-ttu-id="11150-134">Informationen zu unterschiedlichen Arten von Anwesenheitsänderungen finden Sie im Leistungsindikator SetPresence (Presence Type) Calls.</span><span class="sxs-lookup"><span data-stu-id="11150-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-135">NNN-Antworten für SetPresence</span><span class="sxs-lookup"><span data-stu-id="11150-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="11150-136">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="11150-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-137">GetPresence-Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="11150-138">Die Gesamtzahl der Versuche, Anwesenheits Anfragen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="11150-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-139">NNN-Antworten für GetPresence</span><span class="sxs-lookup"><span data-stu-id="11150-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="11150-140">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="11150-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-141">**Informationen zum Adressbuchdienst**</span><span class="sxs-lookup"><span data-stu-id="11150-141">**Address Book service Information**</span></span>

<span data-ttu-id="11150-142">Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Dateidownloads für den Adressbuchdienst (ABS) und für Adressbuch-Webabfrage Dienstanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11150-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-143"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-144"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-145">Vollständige/Delta-Datei Downloads versucht</span><span class="sxs-lookup"><span data-stu-id="11150-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-146">Die Gesamtzahl der vollständigen oder Deltadatei Downloadanforderungen wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="11150-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-147">Vollständige/Delta-Datei Downloads erfolgreich</span><span class="sxs-lookup"><span data-stu-id="11150-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="11150-148">Die Gesamtzahl der vollständigen oder Deltadatei Downloadanforderungen wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="11150-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-149">Verwandte Leistungsindikatoren des Adressbuch-Webabfrage Diensts</span><span class="sxs-lookup"><span data-stu-id="11150-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="11150-150">Verwandte Leistungsindikatoren für Adressbuchdateien herunterladen.</span><span class="sxs-lookup"><span data-stu-id="11150-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-151">Versuchter ABS WS-Anruf</span><span class="sxs-lookup"><span data-stu-id="11150-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-152">Die Gesamtzahl der versuchten Adressbuch-Webabfrage Dienstanforderungen.</span><span class="sxs-lookup"><span data-stu-id="11150-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-153">ABS WS-Aufrufe erfolgreich</span><span class="sxs-lookup"><span data-stu-id="11150-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="11150-154">Die Gesamtzahl der Adressbuch-Webabfrage Dienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="11150-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-155">ABS WS-Anrufe nicht möglich</span><span class="sxs-lookup"><span data-stu-id="11150-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="11150-156">Die Gesamtzahl der Adressbuch-Webabfrage Dienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="11150-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-157">**Informationen zur Verteilerliste (DL)**</span><span class="sxs-lookup"><span data-stu-id="11150-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-158"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-159"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-160">Anrufversuche</span><span class="sxs-lookup"><span data-stu-id="11150-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-161">Gesamtzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung (dlx).</span><span class="sxs-lookup"><span data-stu-id="11150-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-162">Anrufe erfolgreich</span><span class="sxs-lookup"><span data-stu-id="11150-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="11150-163">Die Gesamtzahl der dlx-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="11150-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-164">Anruf fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="11150-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="11150-165">Die Gesamtzahl der dlx-Webdienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="11150-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-166">**VoIP-Grundinformationen**</span><span class="sxs-lookup"><span data-stu-id="11150-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="11150-167">Die nachstehend aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Anrufe an den Vermittlungsserver, A/V-Konferenzserver, den Edgeserver, die Antwortgruppen Anwendung und die automatische Konferenzzentrale, wenn diese Szenarien aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="11150-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-168"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-169"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-170">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="11150-171">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die derzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11150-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-172">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="11150-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="11150-173">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe wurde bereits beendet.</span><span class="sxs-lookup"><span data-stu-id="11150-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-174">Anrufe abgelehnt</span><span class="sxs-lookup"><span data-stu-id="11150-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="11150-175">Die Gesamtzahl der eingehenden Sprachanrufe wurde abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="11150-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-176">Ein-und ausgehende Anrufe wurden versucht</span><span class="sxs-lookup"><span data-stu-id="11150-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-177">Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="11150-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-178">Eingehende/ausgehende Anrufe eingerichtet</span><span class="sxs-lookup"><span data-stu-id="11150-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="11150-179">Gesamtzahl der festgelegten eingehenden/ausgehenden Sprachanrufe.</span><span class="sxs-lookup"><span data-stu-id="11150-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-180">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="11150-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="11150-181">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="11150-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-182">VoIP-Durchlauf Rate (%)</span><span class="sxs-lookup"><span data-stu-id="11150-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="11150-183">Gesamtzahl der eingestellten Anrufe/Gesamtzahl der Anrufe.</span><span class="sxs-lookup"><span data-stu-id="11150-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-184">**Informationen zum Reaktionsgruppendienst**</span><span class="sxs-lookup"><span data-stu-id="11150-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-185"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-186"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-187">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="11150-188">Die Gesamtzahl aktiver Anrufe an die reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="11150-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-189">Anrufversuche</span><span class="sxs-lookup"><span data-stu-id="11150-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-190">Gesamtzahl der versuchten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="11150-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-191">**Sofortnachrichten (im)-Anrufinformationen**</span><span class="sxs-lookup"><span data-stu-id="11150-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-192"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-193"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-194">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="11150-195">Gesamtzahl der laufenden eingehenden/ausgehenden Sofortnachrichten.</span><span class="sxs-lookup"><span data-stu-id="11150-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-196">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="11150-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="11150-197">Die Gesamtzahl der eingehenden/ausgehenden Instant Messaging-Anrufe wurde bereits beendet.</span><span class="sxs-lookup"><span data-stu-id="11150-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-198">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="11150-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="11150-199">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="11150-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-200">Empfangene/Gesendete Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="11150-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="11150-201">Die Gesamtzahl der Nachrichten, die für alle Sitzungen empfangen oder gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="11150-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-202">Ein-und ausgehende Anrufe wurden versucht</span><span class="sxs-lookup"><span data-stu-id="11150-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-203">Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="11150-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-204">Eingehende/ausgehende Anrufe eingerichtet</span><span class="sxs-lookup"><span data-stu-id="11150-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="11150-205">Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe wurde eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="11150-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-206">**App-Freigabe-Anrufinformationen**</span><span class="sxs-lookup"><span data-stu-id="11150-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-207"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-208"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-209">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="11150-210">Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="11150-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-211">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="11150-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="11150-212">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde bereits beendet.</span><span class="sxs-lookup"><span data-stu-id="11150-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-213">Empfangene Anrufe nnn</span><span class="sxs-lookup"><span data-stu-id="11150-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="11150-214">Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="11150-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-215">Ein-und ausgehende Anrufe wurden versucht</span><span class="sxs-lookup"><span data-stu-id="11150-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-216">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Aufrufe wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="11150-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-217">Eingehende/ausgehende Anrufe eingerichtet</span><span class="sxs-lookup"><span data-stu-id="11150-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="11150-218">Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="11150-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-219">**CAA-Anrufinformationen**</span><span class="sxs-lookup"><span data-stu-id="11150-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-220"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-221"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-222">Aktive Anrufe</span><span class="sxs-lookup"><span data-stu-id="11150-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="11150-223">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe (Public Switched Telephone Network), die derzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11150-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-224">Anrufe beendet</span><span class="sxs-lookup"><span data-stu-id="11150-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="11150-225">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde bereits beendet.</span><span class="sxs-lookup"><span data-stu-id="11150-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-226">Ein-und ausgehende Anrufe wurden versucht</span><span class="sxs-lookup"><span data-stu-id="11150-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="11150-227">Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde versucht.</span><span class="sxs-lookup"><span data-stu-id="11150-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-228">Eingehende/ausgehende Anrufe eingerichtet</span><span class="sxs-lookup"><span data-stu-id="11150-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="11150-229">Gesamtzahl der festgelegten eingehenden/ausgehenden PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="11150-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-230">**Konferenz Informationen**</span><span class="sxs-lookup"><span data-stu-id="11150-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-231"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-232"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-233">Aktive Instant Messaging-Konferenzen</span><span class="sxs-lookup"><span data-stu-id="11150-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="11150-234">Gesamtzahl der laufenden Instant Messaging-Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="11150-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-235">Aktive Audio/Video Konferenzen</span><span class="sxs-lookup"><span data-stu-id="11150-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="11150-236">Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).</span><span class="sxs-lookup"><span data-stu-id="11150-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-237">Aktive Anwendungsfreigabe Konferenzen</span><span class="sxs-lookup"><span data-stu-id="11150-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="11150-238">Gesamtzahl der laufenden Konferenz zur Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="11150-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-239">Anzahl der Teilnehmer</span><span class="sxs-lookup"><span data-stu-id="11150-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="11150-240">Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="11150-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11150-241">Konferenzplan Fehler</span><span class="sxs-lookup"><span data-stu-id="11150-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="11150-242">Die Gesamtzahl der Fehler bei dem Versuch, eine Konferenz zu planen.</span><span class="sxs-lookup"><span data-stu-id="11150-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-243">Konferenz Fehler teilnehmen</span><span class="sxs-lookup"><span data-stu-id="11150-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="11150-244">Die Gesamtzahl der Fehler bei dem Versuch, eine Verbindung mit einer Konferenz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="11150-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11150-245">**UCWA-Client-Leistungsindikatoren**</span><span class="sxs-lookup"><span data-stu-id="11150-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11150-246"><strong>Leistungsindikator</strong></span><span class="sxs-lookup"><span data-stu-id="11150-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="11150-247"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="11150-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11150-248">Gesamtzahl der IMMCU-Joins erfolgreich</span><span class="sxs-lookup"><span data-stu-id="11150-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="11150-249">Die Gesamtzahl der Teilnahmen an Instant Messaging-Konferenzen.</span><span class="sxs-lookup"><span data-stu-id="11150-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11150-250">Gesamtzahl der DMCU-Joins erfolgreich</span><span class="sxs-lookup"><span data-stu-id="11150-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="11150-251">Die Gesamtzahl der A/V-Konferenzen, die beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="11150-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


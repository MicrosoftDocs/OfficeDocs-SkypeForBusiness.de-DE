---
title: 'Lync Server 2013: UCWA-Ereignisse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="4e527-102">UCWA-Ereignisse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e527-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e527-103">_**Letztes Änderungsdatum des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="4e527-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4e527-104">Lync Server 2013 verwendet die Unified Communications Web-API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontakt suchen bis zur Aktualisierung der Anwesenheitsinformationen für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="4e527-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="4e527-p101">UCWA zeichnet Einträge zum Betriebsverhalten als die Ereignistypen „Information“, „Warnung“ und „Fehler“ auf. In der folgenden Tabelle sind die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="4e527-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e527-107">Ereigniskennung</span><span class="sxs-lookup"><span data-stu-id="4e527-107">Event ID</span></span></th>
<th><span data-ttu-id="4e527-108">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="4e527-108">Event Type</span></span></th>
<th><span data-ttu-id="4e527-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="4e527-109">Summary</span></span></th>
<th><span data-ttu-id="4e527-110">Ursache und Lösung</span><span class="sxs-lookup"><span data-stu-id="4e527-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e527-111">20001</span><span class="sxs-lookup"><span data-stu-id="4e527-111">20001</span></span></p></td>
<td><p><span data-ttu-id="4e527-112">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-113">UCWA initialisiert</span><span class="sxs-lookup"><span data-stu-id="4e527-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="4e527-114">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-114">N/A</span></span></p>
<p><span data-ttu-id="4e527-115">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-116">20002</span><span class="sxs-lookup"><span data-stu-id="4e527-116">20002</span></span></p></td>
<td><p><span data-ttu-id="4e527-117">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-117">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-118">Unerwartete Ausnahme während der Initialisierung von UCWA</span><span class="sxs-lookup"><span data-stu-id="4e527-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="4e527-119">Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4e527-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="4e527-120">Überprüfen Sie die Ausnahmedetails im zugehörigen Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4e527-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-121">20003</span><span class="sxs-lookup"><span data-stu-id="4e527-121">20003</span></span></p></td>
<td><p><span data-ttu-id="4e527-122">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-122">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-123">In der UCWA ist eine nicht behandelte Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4e527-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="4e527-124">Eine nicht behandelte Ausnahme ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4e527-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="4e527-p102">Starten Sie den Server neu. Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</span><span class="sxs-lookup"><span data-stu-id="4e527-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-127">20004</span><span class="sxs-lookup"><span data-stu-id="4e527-127">20004</span></span></p></td>
<td><p><span data-ttu-id="4e527-128">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-128">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-129">Kein Zugriff auf Exchange zum Abrufen des HD-Fotos</span><span class="sxs-lookup"><span data-stu-id="4e527-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4e527-130">Keine Verbindung mit Exchange verfügbar</span><span class="sxs-lookup"><span data-stu-id="4e527-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4e527-131">Sicherstellen, dass eine Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="4e527-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-132">20005</span><span class="sxs-lookup"><span data-stu-id="4e527-132">20005</span></span></p></td>
<td><p><span data-ttu-id="4e527-133">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-134">Wiederherstellung nach dem Fehler beim Zugriff auf Exchange zum Abrufen des HD-Fotos ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4e527-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-136">20006</span><span class="sxs-lookup"><span data-stu-id="4e527-136">20006</span></span></p></td>
<td><p><span data-ttu-id="4e527-137">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-137">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-138">Kein Zugriff auf Exchange zum Suchen von Kontakten</span><span class="sxs-lookup"><span data-stu-id="4e527-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="4e527-139">Keine Verbindung mit Exchange verfügbar</span><span class="sxs-lookup"><span data-stu-id="4e527-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4e527-140">Sicherstellen, dass eine Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="4e527-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-141">20007</span><span class="sxs-lookup"><span data-stu-id="4e527-141">20007</span></span></p></td>
<td><p><span data-ttu-id="4e527-142">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-143">Wiederherstellung nach dem Fehler beim Suchen von Kontakten in Exchange ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="4e527-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-145">20008</span><span class="sxs-lookup"><span data-stu-id="4e527-145">20008</span></span></p></td>
<td><p><span data-ttu-id="4e527-146">Warnung</span><span class="sxs-lookup"><span data-stu-id="4e527-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="4e527-147">Versuchen, mehr Anwesenheitsabonnements pro Anwendung als zulässig abzuschließen</span><span class="sxs-lookup"><span data-stu-id="4e527-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="4e527-148">Versuchen, mehr Anwesenheitsabonnements pro Anwendung als zulässig abzuschließen</span><span class="sxs-lookup"><span data-stu-id="4e527-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="4e527-149">Clients auf unnötige Abonnements überprüfen</span><span class="sxs-lookup"><span data-stu-id="4e527-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-150">20009</span><span class="sxs-lookup"><span data-stu-id="4e527-150">20009</span></span></p></td>
<td><p><span data-ttu-id="4e527-151">Warnung</span><span class="sxs-lookup"><span data-stu-id="4e527-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="4e527-152">Versuchen, mehr Anwesenheitsabonnements pro Batch als zulässig abzuschließen</span><span class="sxs-lookup"><span data-stu-id="4e527-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="4e527-153">Versuchen, mehr Anwesenheitsabonnements pro Batch als zulässig abzuschließen</span><span class="sxs-lookup"><span data-stu-id="4e527-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="4e527-154">Clients auf unnötige Abonnements überprüfen</span><span class="sxs-lookup"><span data-stu-id="4e527-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-155">20010</span><span class="sxs-lookup"><span data-stu-id="4e527-155">20010</span></span></p></td>
<td><p><span data-ttu-id="4e527-156">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-156">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-157">In-Band-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="4e527-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="4e527-158">In-Band-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="4e527-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="4e527-159">Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</span><span class="sxs-lookup"><span data-stu-id="4e527-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-160">20011</span><span class="sxs-lookup"><span data-stu-id="4e527-160">20011</span></span></p></td>
<td><p><span data-ttu-id="4e527-161">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-161">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-162">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="4e527-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="4e527-163">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="4e527-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="4e527-164">Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</span><span class="sxs-lookup"><span data-stu-id="4e527-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-165">20012</span><span class="sxs-lookup"><span data-stu-id="4e527-165">20012</span></span></p></td>
<td><p><span data-ttu-id="4e527-166">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-166">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-167">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="4e527-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="4e527-168">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="4e527-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="4e527-169">Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</span><span class="sxs-lookup"><span data-stu-id="4e527-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-170">20013</span><span class="sxs-lookup"><span data-stu-id="4e527-170">20013</span></span></p></td>
<td><p><span data-ttu-id="4e527-171">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-171">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-172">IM MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e527-173">IM MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e527-174">Prüfen, ob IM MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-175">20014</span><span class="sxs-lookup"><span data-stu-id="4e527-175">20014</span></span></p></td>
<td><p><span data-ttu-id="4e527-176">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-177">Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit IM MCU ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-178">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-179">20015</span><span class="sxs-lookup"><span data-stu-id="4e527-179">20015</span></span></p></td>
<td><p><span data-ttu-id="4e527-180">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-180">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-181">AV MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e527-182">AV MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e527-183">Prüfen, ob AV MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-184">20016</span><span class="sxs-lookup"><span data-stu-id="4e527-184">20016</span></span></p></td>
<td><p><span data-ttu-id="4e527-185">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-186">Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit AV MCU ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-187">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-188">20017</span><span class="sxs-lookup"><span data-stu-id="4e527-188">20017</span></span></p></td>
<td><p><span data-ttu-id="4e527-189">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-189">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-190">AS MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e527-191">AS MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e527-192">Prüfen, ob AS MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-193">20018</span><span class="sxs-lookup"><span data-stu-id="4e527-193">20018</span></span></p></td>
<td><p><span data-ttu-id="4e527-194">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-195">Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit AS MCU ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-196">-</span><span class="sxs-lookup"><span data-stu-id="4e527-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-197">20019</span><span class="sxs-lookup"><span data-stu-id="4e527-197">20019</span></span></p></td>
<td><p><span data-ttu-id="4e527-198">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-198">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-199">Data MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e527-200">Data MCU ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e527-201">Prüfen, ob Data MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-202">20020</span><span class="sxs-lookup"><span data-stu-id="4e527-202">20020</span></span></p></td>
<td><p><span data-ttu-id="4e527-203">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-204">Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit Date MCU ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-205">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4e527-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-206">20021</span><span class="sxs-lookup"><span data-stu-id="4e527-206">20021</span></span></p></td>
<td><p><span data-ttu-id="4e527-207">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-207">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-208">Teilnahme an IM MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-209">Teilnahme an IM MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="4e527-210">Prüfen, ob IM MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-211">20022</span><span class="sxs-lookup"><span data-stu-id="4e527-211">20022</span></span></p></td>
<td><p><span data-ttu-id="4e527-212">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-212">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-213">Teilnahme an AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-214">Teilnahme an AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="4e527-215">Prüfen, ob AV MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-216">20023</span><span class="sxs-lookup"><span data-stu-id="4e527-216">20023</span></span></p></td>
<td><p><span data-ttu-id="4e527-217">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-217">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-218">Teilnahme an AS MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-219">Teilnahme an AS MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="4e527-220">Prüfen, ob AS MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-221">20024</span><span class="sxs-lookup"><span data-stu-id="4e527-221">20024</span></span></p></td>
<td><p><span data-ttu-id="4e527-222">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-222">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-223">Teilnahme an Data MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4e527-224">Teilnahme an Data MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="4e527-225">Prüfen, ob Data MCU ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e527-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-226">20025</span><span class="sxs-lookup"><span data-stu-id="4e527-226">20025</span></span></p></td>
<td><p><span data-ttu-id="4e527-227">Fehler</span><span class="sxs-lookup"><span data-stu-id="4e527-227">Error</span></span></p></td>
<td><p><span data-ttu-id="4e527-228">Kein Zugriff auf Active Directory zum Abrufen des Fotos</span><span class="sxs-lookup"><span data-stu-id="4e527-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4e527-229">Die Verbindung mit Active Directory ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e527-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="4e527-230">Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4e527-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e527-231">20026</span><span class="sxs-lookup"><span data-stu-id="4e527-231">20026</span></span></p></td>
<td><p><span data-ttu-id="4e527-232">Information</span><span class="sxs-lookup"><span data-stu-id="4e527-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e527-233">Wiederherstellung nach dem Fehler beim Zugriff auf Active Directory zum Abrufen des Fotos ausgeführt</span><span class="sxs-lookup"><span data-stu-id="4e527-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4e527-234">-</span><span class="sxs-lookup"><span data-stu-id="4e527-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e527-235">20027</span><span class="sxs-lookup"><span data-stu-id="4e527-235">20027</span></span></p></td>
<td><p><span data-ttu-id="4e527-236">Warnung</span><span class="sxs-lookup"><span data-stu-id="4e527-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="4e527-237">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="4e527-238">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="4e527-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="4e527-239">Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</span><span class="sxs-lookup"><span data-stu-id="4e527-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


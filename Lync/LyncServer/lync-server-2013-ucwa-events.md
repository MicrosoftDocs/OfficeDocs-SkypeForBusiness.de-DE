---
title: 'Lync Server 2013: UCWA-Ereignisse'
description: 'Lync Server 2013: UCWA-Ereignisse.'
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
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548851"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="0f872-103">UCWA-Ereignisse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f872-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f872-104">_**Letztes Änderungsstand des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="0f872-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="0f872-105">Lync Server 2013 verwendet das Unified Communications Web API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontakt suchen bis zur Aktualisierung der Anwesenheitsinformationen für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="0f872-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="0f872-106">In UCWA werden Datensätze des Betriebsverhaltens als Ereignistypen Information, Warnung und Fehler geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f872-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="0f872-107">In der folgenden Tabelle werden die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="0f872-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f872-108">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0f872-108">Event ID</span></span></th>
<th><span data-ttu-id="0f872-109">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="0f872-109">Event Type</span></span></th>
<th><span data-ttu-id="0f872-110">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="0f872-110">Summary</span></span></th>
<th><span data-ttu-id="0f872-111">Ursache und Lösung</span><span class="sxs-lookup"><span data-stu-id="0f872-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f872-112">20001</span><span class="sxs-lookup"><span data-stu-id="0f872-112">20001</span></span></p></td>
<td><p><span data-ttu-id="0f872-113">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-114">UCWA initialisiert</span><span class="sxs-lookup"><span data-stu-id="0f872-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="0f872-115">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-115">N/A</span></span></p>
<p><span data-ttu-id="0f872-116">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-117">20002</span><span class="sxs-lookup"><span data-stu-id="0f872-117">20002</span></span></p></td>
<td><p><span data-ttu-id="0f872-118">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-118">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-119">UCWA bei der Initialisierung ist eine unerwartete Ausnahme aufgetreten</span><span class="sxs-lookup"><span data-stu-id="0f872-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="0f872-120">Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f872-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="0f872-121">Überprüfen Sie die Ausnahmedetails im zugeordneten Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0f872-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-122">20003</span><span class="sxs-lookup"><span data-stu-id="0f872-122">20003</span></span></p></td>
<td><p><span data-ttu-id="0f872-123">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-123">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-124">UCWA hat eine nicht behandelte Ausnahme gefunden</span><span class="sxs-lookup"><span data-stu-id="0f872-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="0f872-125">Eine unbehandelte Ausnahme ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f872-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="0f872-126">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="0f872-126">Restart the server.</span></span> <span data-ttu-id="0f872-127">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="0f872-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-128">20004</span><span class="sxs-lookup"><span data-stu-id="0f872-128">20004</span></span></p></td>
<td><p><span data-ttu-id="0f872-129">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-129">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-130">Zugriff auf Exchange für HD-Foto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="0f872-131">Die Verbindung mit Exchange ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0f872-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="0f872-132">Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="0f872-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-133">20005</span><span class="sxs-lookup"><span data-stu-id="0f872-133">20005</span></span></p></td>
<td><p><span data-ttu-id="0f872-134">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-135">Wiederherstellung nach dem Fehler beim Zugriff auf Exchange für HD-Foto</span><span class="sxs-lookup"><span data-stu-id="0f872-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="0f872-136">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-137">20006</span><span class="sxs-lookup"><span data-stu-id="0f872-137">20006</span></span></p></td>
<td><p><span data-ttu-id="0f872-138">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-138">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-139">Zugriff auf Exchange für Kontakt Suche nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="0f872-140">Die Verbindung mit Exchange ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0f872-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="0f872-141">Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="0f872-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-142">20007</span><span class="sxs-lookup"><span data-stu-id="0f872-142">20007</span></span></p></td>
<td><p><span data-ttu-id="0f872-143">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-144">Wiederherstellung nach dem Fehler beim Suchen des Kontakts in Exchange</span><span class="sxs-lookup"><span data-stu-id="0f872-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="0f872-145">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-146">20008</span><span class="sxs-lookup"><span data-stu-id="0f872-146">20008</span></span></p></td>
<td><p><span data-ttu-id="0f872-147">Warnung</span><span class="sxs-lookup"><span data-stu-id="0f872-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="0f872-148">Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="0f872-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="0f872-149">Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="0f872-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="0f872-150">Überprüfen der Clients auf unnötige Abonnements</span><span class="sxs-lookup"><span data-stu-id="0f872-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-151">20009</span><span class="sxs-lookup"><span data-stu-id="0f872-151">20009</span></span></p></td>
<td><p><span data-ttu-id="0f872-152">Warnung</span><span class="sxs-lookup"><span data-stu-id="0f872-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="0f872-153">Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</span><span class="sxs-lookup"><span data-stu-id="0f872-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="0f872-154">Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</span><span class="sxs-lookup"><span data-stu-id="0f872-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="0f872-155">Überprüfen der Clients auf unnötige Abonnements</span><span class="sxs-lookup"><span data-stu-id="0f872-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-156">20010</span><span class="sxs-lookup"><span data-stu-id="0f872-156">20010</span></span></p></td>
<td><p><span data-ttu-id="0f872-157">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-157">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-158">Inband-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="0f872-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="0f872-159">Inband-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="0f872-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="0f872-160">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="0f872-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-161">20011</span><span class="sxs-lookup"><span data-stu-id="0f872-161">20011</span></span></p></td>
<td><p><span data-ttu-id="0f872-162">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-162">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-163">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="0f872-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="0f872-164">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="0f872-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="0f872-165">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="0f872-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-166">20012</span><span class="sxs-lookup"><span data-stu-id="0f872-166">20012</span></span></p></td>
<td><p><span data-ttu-id="0f872-167">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-167">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-168">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="0f872-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="0f872-169">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="0f872-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="0f872-170">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="0f872-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-171">20013</span><span class="sxs-lookup"><span data-stu-id="0f872-171">20013</span></span></p></td>
<td><p><span data-ttu-id="0f872-172">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-172">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-173">IM MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="0f872-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0f872-174">IM MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="0f872-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="0f872-175">Überprüfen, ob im MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-176">20014</span><span class="sxs-lookup"><span data-stu-id="0f872-176">20014</span></span></p></td>
<td><p><span data-ttu-id="0f872-177">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-178">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Sofortnachrichten-MCU</span><span class="sxs-lookup"><span data-stu-id="0f872-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-179">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-180">20015</span><span class="sxs-lookup"><span data-stu-id="0f872-180">20015</span></span></p></td>
<td><p><span data-ttu-id="0f872-181">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-181">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-182">AV MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="0f872-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0f872-183">AV MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="0f872-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="0f872-184">Prüfen, ob AV MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-185">20016</span><span class="sxs-lookup"><span data-stu-id="0f872-185">20016</span></span></p></td>
<td><p><span data-ttu-id="0f872-186">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-187">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AV MCU</span><span class="sxs-lookup"><span data-stu-id="0f872-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-188">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-189">20017</span><span class="sxs-lookup"><span data-stu-id="0f872-189">20017</span></span></p></td>
<td><p><span data-ttu-id="0f872-190">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-190">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-191">Da MCU nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="0f872-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0f872-192">Da MCU nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="0f872-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="0f872-193">Anzeigen, ob as MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-194">20018</span><span class="sxs-lookup"><span data-stu-id="0f872-194">20018</span></span></p></td>
<td><p><span data-ttu-id="0f872-195">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-196">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AS MCU</span><span class="sxs-lookup"><span data-stu-id="0f872-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-197">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-198">20019</span><span class="sxs-lookup"><span data-stu-id="0f872-198">20019</span></span></p></td>
<td><p><span data-ttu-id="0f872-199">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-199">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-200">Data MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="0f872-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0f872-201">Data MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="0f872-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="0f872-202">Überprüfen, ob Data MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-203">20020</span><span class="sxs-lookup"><span data-stu-id="0f872-203">20020</span></span></p></td>
<td><p><span data-ttu-id="0f872-204">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-205">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Data MCU</span><span class="sxs-lookup"><span data-stu-id="0f872-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-206">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-207">20021</span><span class="sxs-lookup"><span data-stu-id="0f872-207">20021</span></span></p></td>
<td><p><span data-ttu-id="0f872-208">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-208">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-209">Teilnahme an Chat MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-210">Teilnahme an Chat MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="0f872-211">Überprüfen, ob im MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-212">20022</span><span class="sxs-lookup"><span data-stu-id="0f872-212">20022</span></span></p></td>
<td><p><span data-ttu-id="0f872-213">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-213">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-214">Beitritt zur AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-215">Beitritt zur AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="0f872-216">Prüfen, ob AV MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-217">20023</span><span class="sxs-lookup"><span data-stu-id="0f872-217">20023</span></span></p></td>
<td><p><span data-ttu-id="0f872-218">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-218">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-219">Beitritt zur MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-220">Beitritt zur MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="0f872-221">Anzeigen, ob as MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-222">20024</span><span class="sxs-lookup"><span data-stu-id="0f872-222">20024</span></span></p></td>
<td><p><span data-ttu-id="0f872-223">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-223">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-224">Beitreten zu Daten-MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="0f872-225">Beitreten zu Daten-MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="0f872-226">Überprüfen, ob Data MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0f872-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-227">20025</span><span class="sxs-lookup"><span data-stu-id="0f872-227">20025</span></span></p></td>
<td><p><span data-ttu-id="0f872-228">Error</span><span class="sxs-lookup"><span data-stu-id="0f872-228">Error</span></span></p></td>
<td><p><span data-ttu-id="0f872-229">Zugriff auf Active Directory für Foto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="0f872-230">Die Verbindung mit Active Directory ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0f872-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="0f872-231">Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0f872-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f872-232">20026</span><span class="sxs-lookup"><span data-stu-id="0f872-232">20026</span></span></p></td>
<td><p><span data-ttu-id="0f872-233">Informations</span><span class="sxs-lookup"><span data-stu-id="0f872-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="0f872-234">Wiederherstellung nach dem Fehler beim Zugriff auf Active Directory für Foto</span><span class="sxs-lookup"><span data-stu-id="0f872-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="0f872-235">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0f872-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f872-236">20027</span><span class="sxs-lookup"><span data-stu-id="0f872-236">20027</span></span></p></td>
<td><p><span data-ttu-id="0f872-237">Warnung</span><span class="sxs-lookup"><span data-stu-id="0f872-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="0f872-238">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="0f872-239">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="0f872-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="0f872-240">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="0f872-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


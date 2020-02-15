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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="44e49-102">UCWA-Ereignisse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e49-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e49-103">_**Letztes Änderungsstand des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="44e49-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="44e49-104">Lync Server 2013 verwendet das Unified Communications Web API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontakt suchen bis zur Aktualisierung der Anwesenheitsinformationen für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="44e49-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="44e49-105">In UCWA werden Datensätze des Betriebsverhaltens als Ereignistypen Information, Warnung und Fehler geschrieben.</span><span class="sxs-lookup"><span data-stu-id="44e49-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="44e49-106">In der folgenden Tabelle werden die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="44e49-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e49-107">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="44e49-107">Event ID</span></span></th>
<th><span data-ttu-id="44e49-108">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="44e49-108">Event Type</span></span></th>
<th><span data-ttu-id="44e49-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="44e49-109">Summary</span></span></th>
<th><span data-ttu-id="44e49-110">Ursache und Lösung</span><span class="sxs-lookup"><span data-stu-id="44e49-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e49-111">20001</span><span class="sxs-lookup"><span data-stu-id="44e49-111">20001</span></span></p></td>
<td><p><span data-ttu-id="44e49-112">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-113">UCWA initialisiert</span><span class="sxs-lookup"><span data-stu-id="44e49-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="44e49-114">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-114">N/A</span></span></p>
<p><span data-ttu-id="44e49-115">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-116">20002</span><span class="sxs-lookup"><span data-stu-id="44e49-116">20002</span></span></p></td>
<td><p><span data-ttu-id="44e49-117">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-117">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-118">UCWA bei der Initialisierung ist eine unerwartete Ausnahme aufgetreten</span><span class="sxs-lookup"><span data-stu-id="44e49-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="44e49-119">Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="44e49-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="44e49-120">Überprüfen Sie die Ausnahmedetails im zugeordneten Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="44e49-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-121">20003</span><span class="sxs-lookup"><span data-stu-id="44e49-121">20003</span></span></p></td>
<td><p><span data-ttu-id="44e49-122">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-122">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-123">UCWA hat eine nicht behandelte Ausnahme gefunden</span><span class="sxs-lookup"><span data-stu-id="44e49-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="44e49-124">Eine unbehandelte Ausnahme ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="44e49-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="44e49-125">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="44e49-125">Restart the server.</span></span> <span data-ttu-id="44e49-126">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="44e49-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-127">20004</span><span class="sxs-lookup"><span data-stu-id="44e49-127">20004</span></span></p></td>
<td><p><span data-ttu-id="44e49-128">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-128">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-129">Zugriff auf Exchange für HD-Foto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="44e49-130">Die Verbindung mit Exchange ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44e49-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="44e49-131">Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="44e49-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-132">20005</span><span class="sxs-lookup"><span data-stu-id="44e49-132">20005</span></span></p></td>
<td><p><span data-ttu-id="44e49-133">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-134">Wiederherstellung nach dem Fehler beim Zugriff auf Exchange für HD-Foto</span><span class="sxs-lookup"><span data-stu-id="44e49-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="44e49-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-136">20006</span><span class="sxs-lookup"><span data-stu-id="44e49-136">20006</span></span></p></td>
<td><p><span data-ttu-id="44e49-137">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-137">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-138">Zugriff auf Exchange für Kontakt Suche nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="44e49-139">Die Verbindung mit Exchange ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44e49-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="44e49-140">Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="44e49-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-141">20007</span><span class="sxs-lookup"><span data-stu-id="44e49-141">20007</span></span></p></td>
<td><p><span data-ttu-id="44e49-142">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-143">Wiederherstellung nach dem Fehler beim Suchen des Kontakts in Exchange</span><span class="sxs-lookup"><span data-stu-id="44e49-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="44e49-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-145">20008</span><span class="sxs-lookup"><span data-stu-id="44e49-145">20008</span></span></p></td>
<td><p><span data-ttu-id="44e49-146">Warnung</span><span class="sxs-lookup"><span data-stu-id="44e49-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="44e49-147">Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="44e49-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="44e49-148">Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="44e49-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="44e49-149">Überprüfen der Clients auf unnötige Abonnements</span><span class="sxs-lookup"><span data-stu-id="44e49-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-150">20009</span><span class="sxs-lookup"><span data-stu-id="44e49-150">20009</span></span></p></td>
<td><p><span data-ttu-id="44e49-151">Warnung</span><span class="sxs-lookup"><span data-stu-id="44e49-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="44e49-152">Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</span><span class="sxs-lookup"><span data-stu-id="44e49-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="44e49-153">Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</span><span class="sxs-lookup"><span data-stu-id="44e49-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="44e49-154">Überprüfen der Clients auf unnötige Abonnements</span><span class="sxs-lookup"><span data-stu-id="44e49-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-155">20010</span><span class="sxs-lookup"><span data-stu-id="44e49-155">20010</span></span></p></td>
<td><p><span data-ttu-id="44e49-156">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-156">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-157">Inband-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="44e49-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="44e49-158">Inband-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="44e49-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="44e49-159">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="44e49-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-160">20011</span><span class="sxs-lookup"><span data-stu-id="44e49-160">20011</span></span></p></td>
<td><p><span data-ttu-id="44e49-161">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-161">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-162">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="44e49-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="44e49-163">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="44e49-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="44e49-164">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="44e49-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-165">20012</span><span class="sxs-lookup"><span data-stu-id="44e49-165">20012</span></span></p></td>
<td><p><span data-ttu-id="44e49-166">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-166">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-167">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="44e49-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="44e49-168">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="44e49-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="44e49-169">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="44e49-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-170">20013</span><span class="sxs-lookup"><span data-stu-id="44e49-170">20013</span></span></p></td>
<td><p><span data-ttu-id="44e49-171">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-171">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-172">IM MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44e49-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44e49-173">IM MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44e49-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="44e49-174">Überprüfen, ob im MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-175">20014</span><span class="sxs-lookup"><span data-stu-id="44e49-175">20014</span></span></p></td>
<td><p><span data-ttu-id="44e49-176">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-177">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Sofortnachrichten-MCU</span><span class="sxs-lookup"><span data-stu-id="44e49-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-178">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-179">20015</span><span class="sxs-lookup"><span data-stu-id="44e49-179">20015</span></span></p></td>
<td><p><span data-ttu-id="44e49-180">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-180">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-181">AV MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44e49-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44e49-182">AV MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44e49-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="44e49-183">Prüfen, ob AV MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-184">20016</span><span class="sxs-lookup"><span data-stu-id="44e49-184">20016</span></span></p></td>
<td><p><span data-ttu-id="44e49-185">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-186">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AV MCU</span><span class="sxs-lookup"><span data-stu-id="44e49-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-187">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-188">20017</span><span class="sxs-lookup"><span data-stu-id="44e49-188">20017</span></span></p></td>
<td><p><span data-ttu-id="44e49-189">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-189">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-190">Da MCU nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="44e49-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44e49-191">Da MCU nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="44e49-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="44e49-192">Anzeigen, ob as MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-193">20018</span><span class="sxs-lookup"><span data-stu-id="44e49-193">20018</span></span></p></td>
<td><p><span data-ttu-id="44e49-194">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-195">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AS MCU</span><span class="sxs-lookup"><span data-stu-id="44e49-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-196">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-197">20019</span><span class="sxs-lookup"><span data-stu-id="44e49-197">20019</span></span></p></td>
<td><p><span data-ttu-id="44e49-198">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-198">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-199">Data MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44e49-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="44e49-200">Data MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44e49-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="44e49-201">Überprüfen, ob Data MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-202">20020</span><span class="sxs-lookup"><span data-stu-id="44e49-202">20020</span></span></p></td>
<td><p><span data-ttu-id="44e49-203">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-204">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Data MCU</span><span class="sxs-lookup"><span data-stu-id="44e49-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-205">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-206">20021</span><span class="sxs-lookup"><span data-stu-id="44e49-206">20021</span></span></p></td>
<td><p><span data-ttu-id="44e49-207">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-207">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-208">Teilnahme an Chat MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-209">Teilnahme an Chat MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="44e49-210">Überprüfen, ob im MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-211">20022</span><span class="sxs-lookup"><span data-stu-id="44e49-211">20022</span></span></p></td>
<td><p><span data-ttu-id="44e49-212">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-212">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-213">Beitritt zur AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-214">Beitritt zur AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="44e49-215">Prüfen, ob AV MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-216">20023</span><span class="sxs-lookup"><span data-stu-id="44e49-216">20023</span></span></p></td>
<td><p><span data-ttu-id="44e49-217">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-217">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-218">Beitritt zur MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-219">Beitritt zur MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="44e49-220">Anzeigen, ob as MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-221">20024</span><span class="sxs-lookup"><span data-stu-id="44e49-221">20024</span></span></p></td>
<td><p><span data-ttu-id="44e49-222">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-222">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-223">Beitreten zu Daten-MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="44e49-224">Beitreten zu Daten-MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="44e49-225">Überprüfen, ob Data MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="44e49-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-226">20025</span><span class="sxs-lookup"><span data-stu-id="44e49-226">20025</span></span></p></td>
<td><p><span data-ttu-id="44e49-227">Fehler</span><span class="sxs-lookup"><span data-stu-id="44e49-227">Error</span></span></p></td>
<td><p><span data-ttu-id="44e49-228">Zugriff auf Active Directory für Foto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="44e49-229">Die Verbindung mit Active Directory ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44e49-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="44e49-230">Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="44e49-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e49-231">20026</span><span class="sxs-lookup"><span data-stu-id="44e49-231">20026</span></span></p></td>
<td><p><span data-ttu-id="44e49-232">Informations</span><span class="sxs-lookup"><span data-stu-id="44e49-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="44e49-233">Wiederherstellung nach dem Fehler beim Zugriff auf Active Directory für Foto</span><span class="sxs-lookup"><span data-stu-id="44e49-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="44e49-234">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="44e49-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e49-235">20027</span><span class="sxs-lookup"><span data-stu-id="44e49-235">20027</span></span></p></td>
<td><p><span data-ttu-id="44e49-236">Warnung</span><span class="sxs-lookup"><span data-stu-id="44e49-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="44e49-237">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="44e49-238">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="44e49-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="44e49-239">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="44e49-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


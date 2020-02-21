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
ms.openlocfilehash: 950d52dfe86ebf4d5b8b53677248528f1ef49047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="a1c3f-102">UCWA-Ereignisse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c3f-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1c3f-103">_**Letztes Änderungsstand des Themas:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a1c3f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="a1c3f-104">Lync Server 2013 verwendet das Unified Communications Web API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontakt suchen bis zur Aktualisierung der Anwesenheitsinformationen für mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="a1c3f-105">In UCWA werden Datensätze des Betriebsverhaltens als Ereignistypen Information, Warnung und Fehler geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="a1c3f-106">In der folgenden Tabelle werden die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1c3f-107">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="a1c3f-107">Event ID</span></span></th>
<th><span data-ttu-id="a1c3f-108">Ereignistyp</span><span class="sxs-lookup"><span data-stu-id="a1c3f-108">Event Type</span></span></th>
<th><span data-ttu-id="a1c3f-109">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a1c3f-109">Summary</span></span></th>
<th><span data-ttu-id="a1c3f-110">Ursache und Lösung</span><span class="sxs-lookup"><span data-stu-id="a1c3f-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-111">20001</span><span class="sxs-lookup"><span data-stu-id="a1c3f-111">20001</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-112">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-113">UCWA initialisiert</span><span class="sxs-lookup"><span data-stu-id="a1c3f-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-114">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-114">N/A</span></span></p>
<p><span data-ttu-id="a1c3f-115">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-116">20002</span><span class="sxs-lookup"><span data-stu-id="a1c3f-116">20002</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-117">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-117">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-118">UCWA bei der Initialisierung ist eine unerwartete Ausnahme aufgetreten</span><span class="sxs-lookup"><span data-stu-id="a1c3f-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-119">Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="a1c3f-120">Überprüfen Sie die Ausnahmedetails im zugeordneten Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-121">20003</span><span class="sxs-lookup"><span data-stu-id="a1c3f-121">20003</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-122">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-122">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-123">UCWA hat eine nicht behandelte Ausnahme gefunden</span><span class="sxs-lookup"><span data-stu-id="a1c3f-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-124">Eine unbehandelte Ausnahme ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="a1c3f-125">Starten Sie den Server neu.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-125">Restart the server.</span></span> <span data-ttu-id="a1c3f-126">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="a1c3f-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-127">20004</span><span class="sxs-lookup"><span data-stu-id="a1c3f-127">20004</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-128">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-128">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-129">Zugriff auf Exchange für HD-Foto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-130">Die Verbindung mit Exchange ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a1c3f-131">Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="a1c3f-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-132">20005</span><span class="sxs-lookup"><span data-stu-id="a1c3f-132">20005</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-133">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-134">Wiederherstellung nach dem Fehler beim Zugriff auf Exchange für HD-Foto</span><span class="sxs-lookup"><span data-stu-id="a1c3f-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-136">20006</span><span class="sxs-lookup"><span data-stu-id="a1c3f-136">20006</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-137">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-137">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-138">Zugriff auf Exchange für Kontakt Suche nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-139">Die Verbindung mit Exchange ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a1c3f-140">Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="a1c3f-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-141">20007</span><span class="sxs-lookup"><span data-stu-id="a1c3f-141">20007</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-142">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-143">Wiederherstellung nach dem Fehler beim Suchen des Kontakts in Exchange</span><span class="sxs-lookup"><span data-stu-id="a1c3f-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-145">20008</span><span class="sxs-lookup"><span data-stu-id="a1c3f-145">20008</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-146">Warnung</span><span class="sxs-lookup"><span data-stu-id="a1c3f-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-147">Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-148">Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="a1c3f-149">Überprüfen der Clients auf unnötige Abonnements</span><span class="sxs-lookup"><span data-stu-id="a1c3f-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-150">20009</span><span class="sxs-lookup"><span data-stu-id="a1c3f-150">20009</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-151">Warnung</span><span class="sxs-lookup"><span data-stu-id="a1c3f-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-152">Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</span><span class="sxs-lookup"><span data-stu-id="a1c3f-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-153">Versuchen, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren</span><span class="sxs-lookup"><span data-stu-id="a1c3f-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="a1c3f-154">Überprüfen der Clients auf unnötige Abonnements</span><span class="sxs-lookup"><span data-stu-id="a1c3f-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-155">20010</span><span class="sxs-lookup"><span data-stu-id="a1c3f-155">20010</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-156">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-156">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-157">Inband-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="a1c3f-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-158">Inband-Daten können nicht abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="a1c3f-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="a1c3f-159">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="a1c3f-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-160">20011</span><span class="sxs-lookup"><span data-stu-id="a1c3f-160">20011</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-161">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-161">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-162">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="a1c3f-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-163">Anwesenheit kann nicht abonniert werden</span><span class="sxs-lookup"><span data-stu-id="a1c3f-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="a1c3f-164">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="a1c3f-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-165">20012</span><span class="sxs-lookup"><span data-stu-id="a1c3f-165">20012</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-166">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-166">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-167">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="a1c3f-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-168">Fehler beim Registrieren des Endpunkts</span><span class="sxs-lookup"><span data-stu-id="a1c3f-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="a1c3f-169">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="a1c3f-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-170">20013</span><span class="sxs-lookup"><span data-stu-id="a1c3f-170">20013</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-171">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-171">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-172">IM MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="a1c3f-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-173">IM MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="a1c3f-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="a1c3f-174">Überprüfen, ob im MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-175">20014</span><span class="sxs-lookup"><span data-stu-id="a1c3f-175">20014</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-176">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-177">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Sofortnachrichten-MCU</span><span class="sxs-lookup"><span data-stu-id="a1c3f-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-178">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-179">20015</span><span class="sxs-lookup"><span data-stu-id="a1c3f-179">20015</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-180">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-180">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-181">AV MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="a1c3f-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-182">AV MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="a1c3f-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="a1c3f-183">Prüfen, ob AV MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-184">20016</span><span class="sxs-lookup"><span data-stu-id="a1c3f-184">20016</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-185">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-186">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AV MCU</span><span class="sxs-lookup"><span data-stu-id="a1c3f-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-187">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-188">20017</span><span class="sxs-lookup"><span data-stu-id="a1c3f-188">20017</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-189">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-189">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-190">Da MCU nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="a1c3f-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-191">Da MCU nicht verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="a1c3f-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="a1c3f-192">Anzeigen, ob as MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-193">20018</span><span class="sxs-lookup"><span data-stu-id="a1c3f-193">20018</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-194">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-195">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit AS MCU</span><span class="sxs-lookup"><span data-stu-id="a1c3f-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-196">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-197">20019</span><span class="sxs-lookup"><span data-stu-id="a1c3f-197">20019</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-198">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-198">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-199">Data MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="a1c3f-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-200">Data MCU ist nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="a1c3f-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="a1c3f-201">Überprüfen, ob Data MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-202">20020</span><span class="sxs-lookup"><span data-stu-id="a1c3f-202">20020</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-203">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-204">Wiederherstellung nach dem Fehler beim Herstellen einer Verbindung mit Data MCU</span><span class="sxs-lookup"><span data-stu-id="a1c3f-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-205">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-206">20021</span><span class="sxs-lookup"><span data-stu-id="a1c3f-206">20021</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-207">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-207">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-208">Teilnahme an Chat MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-209">Teilnahme an Chat MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="a1c3f-210">Überprüfen, ob im MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-211">20022</span><span class="sxs-lookup"><span data-stu-id="a1c3f-211">20022</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-212">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-212">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-213">Beitritt zur AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-214">Beitritt zur AV MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="a1c3f-215">Prüfen, ob AV MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-216">20023</span><span class="sxs-lookup"><span data-stu-id="a1c3f-216">20023</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-217">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-217">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-218">Beitritt zur MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-219">Beitritt zur MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="a1c3f-220">Anzeigen, ob as MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-221">20024</span><span class="sxs-lookup"><span data-stu-id="a1c3f-221">20024</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-222">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-222">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-223">Beitreten zu Daten-MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-224">Beitreten zu Daten-MCU nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="a1c3f-225">Überprüfen, ob Data MCU ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="a1c3f-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-226">20025</span><span class="sxs-lookup"><span data-stu-id="a1c3f-226">20025</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-227">Fehler</span><span class="sxs-lookup"><span data-stu-id="a1c3f-227">Error</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-228">Zugriff auf Active Directory für Foto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-229">Die Verbindung mit Active Directory ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="a1c3f-230">Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a1c3f-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1c3f-231">20026</span><span class="sxs-lookup"><span data-stu-id="a1c3f-231">20026</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-232">Informations</span><span class="sxs-lookup"><span data-stu-id="a1c3f-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-233">Wiederherstellung nach dem Fehler beim Zugriff auf Active Directory für Foto</span><span class="sxs-lookup"><span data-stu-id="a1c3f-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-234">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a1c3f-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1c3f-235">20027</span><span class="sxs-lookup"><span data-stu-id="a1c3f-235">20027</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-236">Warnung</span><span class="sxs-lookup"><span data-stu-id="a1c3f-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-237">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="a1c3f-238">Deserialisierung nicht möglich</span><span class="sxs-lookup"><span data-stu-id="a1c3f-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="a1c3f-239">Wenn das Problem fortbesteht, wenden Sie sich an den Produktsupport</span><span class="sxs-lookup"><span data-stu-id="a1c3f-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


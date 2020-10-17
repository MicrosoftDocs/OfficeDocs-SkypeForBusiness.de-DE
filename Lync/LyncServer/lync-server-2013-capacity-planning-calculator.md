---
title: Lync Server 2013 Kapazitäts planungsrechner
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512822"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="27cc5-102">Verwenden des Kapazitäts Planungs Rechners für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27cc5-102">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27cc5-103">_**Letztes Änderungsstand des Themas:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="27cc5-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="27cc5-104">Der Rechner zur Kapazitätsplanung von Microsoft® lync™ Server 2013 steht zum Download zur Verfügung <https://www.microsoft.com/download/details.aspx?id=36828> .</span><span class="sxs-lookup"><span data-stu-id="27cc5-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="27cc5-105">Es wurde entwickelt, um Sie bei der Ermittlung von Server Anforderungen basierend auf der Anzahl von Benutzern und Kommunikationsmodalitäten zu unterstützen, die in Ihrer Organisation aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="27cc5-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="27cc5-106">Sie geben das Profil Ihrer Organisation ein, und der Rechner enthält Empfehlungen, die Sie bei der Planung Ihrer Topologie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="27cc5-107">Die vom Rechner erstellten Empfehlungen dienen nur zu Planungszwecken.</span><span class="sxs-lookup"><span data-stu-id="27cc5-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="27cc5-108">Die tatsächliche Auslastungssimulation ist erforderlich, um sicherzustellen, dass lync Server 2013 angemessen bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="27cc5-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="27cc5-109">Verwenden Sie zum Ausführen von Belastungstests unter simulierter Last das [Tool lync Server 2013 Stress and Performance](https://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="27cc5-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="27cc5-110">Nachdem Sie Ihr Benutzerprofil und die Modalitäten festgelegt haben, die Sie für Ihre Benutzer aktivieren möchten, ist es an der Zeit, den Rechner zu verwenden, um die Anzahl der benötigten Server, Arbeitsspeicher und Bandbreite zu planen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="27cc5-111">Diese Version des Rechners bietet keine Anleitung für Datenträger-e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="27cc5-112">Dieser Rechner ergänzt die [Microsoft lync Server](https://go.microsoft.com/fwlink/?linkid=282725) und [Microsoft lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="27cc5-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="27cc5-113">Verwenden Sie den Rechner, nachdem Sie das Handbuch überprüft und eine empfohlene Topologie mithilfe des Planungstools erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="27cc5-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="27cc5-114">Sie können am meisten von dem Rechner profitieren, wenn Sie genaue, detaillierte Informationen zu Ihrem bestimmten Benutzerprofil haben.</span><span class="sxs-lookup"><span data-stu-id="27cc5-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="27cc5-115">Beispielsweise kann der Prozentsatz an sprachaktivierten Benutzern, durchschnittliche Anrufe pro Benutzer und Stunde, Anrufdauer und der Prozentsatz gleichzeitiger Benutzer in Konferenzen einen großen Unterschied in den Server Anforderungen mit sich bringen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="27cc5-116">Die Genauigkeit der vom Rechner erstellten Empfehlungen hängt von der Genauigkeit der von Ihnen bereitgestellten Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="27cc5-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="27cc5-117">Verwenden des Kapazitäts Rechners</span><span class="sxs-lookup"><span data-stu-id="27cc5-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="27cc5-118">Der Rechner ist eine Microsoft Excel® Kalkulationstabelle.</span><span class="sxs-lookup"><span data-stu-id="27cc5-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="27cc5-119">Orange gefärbte Zellen werden von Ihnen eingegeben.</span><span class="sxs-lookup"><span data-stu-id="27cc5-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="27cc5-120">Es werden Standardwerte eingegeben (80.000 Benutzer in einem Pool mit zwölf Front-End-Servern), Sie können diese Werte jedoch entsprechend den Anforderungen Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="27cc5-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="27cc5-121">Das Nutzungsmodell enthält die folgenden Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="27cc5-121">The usage model contains the following sections.</span></span> <span data-ttu-id="27cc5-122">Geben Sie zum Berechnen der Kapazitätsanforderungen wie beschrieben Daten ein:</span><span class="sxs-lookup"><span data-stu-id="27cc5-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="27cc5-123">**Instant Messaging und Anwesenheit**</span><span class="sxs-lookup"><span data-stu-id="27cc5-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="27cc5-124">Geben Sie unter Anzahl der Benutzer die Anzahl der Benutzer ein, die gleichzeitig angemeldet sein sollen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="27cc5-125">Diese Nummer ist normalerweise 80% der Gesamtzahl der gestellten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="27cc5-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="27cc5-126">In den meisten Fällen sind 100% ihrer gleichzeitigen Benutzer für Sofortnachrichten und Anwesenheitsinformationen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="27cc5-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="27cc5-127">Der Standardwert ist 80.000.</span><span class="sxs-lookup"><span data-stu-id="27cc5-127">The default is 80,000.</span></span>

  - <span data-ttu-id="27cc5-128">Durchschnittliche Anzahl von Kontakten in der Kontaktliste gibt die Anzahl der Kontakte an, die für die Überprüfung der Systemanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27cc5-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="27cc5-129">Diese Nummer kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="27cc5-129">This number is not changeable.</span></span>

<span data-ttu-id="27cc5-130">**Enterprise-VoIP**</span><span class="sxs-lookup"><span data-stu-id="27cc5-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="27cc5-131">Geben Sie unter für Enterprise-VoIP aktivierte Benutzer den Prozentsatz der Benutzer ein, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="27cc5-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="27cc5-132">Der Standardwert ist 60%.</span><span class="sxs-lookup"><span data-stu-id="27cc5-132">The default is 60%.</span></span>

  - <span data-ttu-id="27cc5-133">Geben Sie im Durchschnitt Anzahl der Anrufe pro Benutzer pro Stunde (Spitzenwert) die Anzahl der Anrufe pro Stunde ein, die der durchschnittliche Benutzer in Zeiten der Spitzenauslastung an der Teilnahme erwartet.</span><span class="sxs-lookup"><span data-stu-id="27cc5-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="27cc5-134">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="27cc5-134">The default is 4.</span></span>

  - <span data-ttu-id="27cc5-135">Geben Sie in Prozentsatz der Anrufe, die die medienumgehung verwenden, den Prozentsatz der Anrufe ein, die von Ihren Benutzern getätigt werden und die Vermittlungsserver umgehen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="27cc5-136">Der Standardwert ist 65%.</span><span class="sxs-lookup"><span data-stu-id="27cc5-136">The default is 65%.</span></span>

  - <span data-ttu-id="27cc5-137">Geben Sie in Prozentsatz der VoIP-Benutzer, die an UC-PSTN-anrufen beteiligt sind, den Prozentsatz der Anrufe Ihrer Organisation ein, bei denen es sich um UC-PSTN-Telefonanrufe handelt.</span><span class="sxs-lookup"><span data-stu-id="27cc5-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="27cc5-138">Der Standardwert ist 60%</span><span class="sxs-lookup"><span data-stu-id="27cc5-138">The default is 60%</span></span>

  - <span data-ttu-id="27cc5-139">In Prozentsatz der an UC-UC-Anrufe beteiligten Sprachbenutzer zeigt den Prozentsatz der Benutzer an, die für Enterprise-VoIP aktiviert sind und nur für UC-UC-Anrufe aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="27cc5-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="27cc5-140">Diese Nummer wird basierend auf den Angaben berechnet, die Sie für den Prozentsatz der für UC-PSTN-Anrufe aktivierten VoIP-Benutzer eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="27cc5-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="27cc5-141">**Konferenzen**</span><span class="sxs-lookup"><span data-stu-id="27cc5-141">**Conferencing**</span></span>

  - <span data-ttu-id="27cc5-142">Geben Sie in Prozentsatz der Benutzer in gleichzeitigen Konferenzen den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen werden.</span><span class="sxs-lookup"><span data-stu-id="27cc5-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="27cc5-143">Der Standardwert ist 5%.</span><span class="sxs-lookup"><span data-stu-id="27cc5-143">The default is 5%.</span></span>

  - <span data-ttu-id="27cc5-144">Geben Sie in Prozentsatz der Konferenzen mit nur Gruppen-Chat (keine Stimme) den Prozentsatz der Konferenzen ein, deren Konferenzen nur Chatnachrichten umfassen sollen. Das bedeutet, dass keine Audio-Komponente enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="27cc5-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="27cc5-145">Der Standardwert ist 10%</span><span class="sxs-lookup"><span data-stu-id="27cc5-145">The default is 10%</span></span>

  - <span data-ttu-id="27cc5-146">Geben Sie in Prozentsatz der Benutzer, die Einwahlkonferenzen verwenden, den Prozentsatz der gleichzeitigen Teilnehmer an Konferenzen ein, die Einwahlkonferenzen verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="27cc5-147">Der Standardwert ist 15%.</span><span class="sxs-lookup"><span data-stu-id="27cc5-147">The default is 15%.</span></span>

  - <span data-ttu-id="27cc5-148">Geben Sie in Prozentsatz der Konferenzen, die Voice verwenden, den Prozentsatz der Konferenzen ein, die eine Audio-Komponente enthalten sollen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="27cc5-149">Wenn 20% Ihrer VoIP-Konferenzen auch reguläre Videos enthalten, aktivieren Sie das Kontrollkästchen einschließlich Video (keine Mehrfachansicht).</span><span class="sxs-lookup"><span data-stu-id="27cc5-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="27cc5-150">Wenn 20% ihrer Konferenzen auch Multi-View-Video enthalten, aktivieren Sie das Kontrollkästchen einschließlich Multiview-Ansicht.</span><span class="sxs-lookup"><span data-stu-id="27cc5-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="27cc5-151">Wenn 50% Ihrer VoIP-Konferenzen auch die Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen einschließlich Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="27cc5-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="27cc5-152">Wenn 20% Ihrer VoIP-Konferenzen Datenuploads umfassen, beispielsweise Microsoft PowerPoint® Präsentationen, aktivieren Sie das Kontrollkästchen einschließlich Webkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="27cc5-153">**Mobilität**</span><span class="sxs-lookup"><span data-stu-id="27cc5-153">**Mobility**</span></span>

  - <span data-ttu-id="27cc5-154">Geben Sie in Prozentsatz der für Mobilität aktivierten Benutzer den Prozentsatz der Benutzer ein, die zum Herstellen einer Verbindung mit lync Server über mobile Geräte aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="27cc5-155">Der Standardwert ist 40%.</span><span class="sxs-lookup"><span data-stu-id="27cc5-155">The default is 40%.</span></span>

<span data-ttu-id="27cc5-156">Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitäts Rechner Ihre Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="27cc5-157">Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher-und Bandbreitenanforderungen basierend auf Tests an, die in lync Server 2013 Performance Labs ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="27cc5-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="27cc5-158">Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variation wird getestet und validiert.</span><span class="sxs-lookup"><span data-stu-id="27cc5-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="27cc5-159">Die folgenden Werte werden berechnet:</span><span class="sxs-lookup"><span data-stu-id="27cc5-159">The following values are calculated:</span></span>

  - <span data-ttu-id="27cc5-160">Front-End-CPU: Prozentsatz der CPU-Auslastung, wenn die gesamte Last von einem Front-End-Server der gleichen Spezifikationen wie der Server, der in Microsoft Tests verwendet wurde, verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="27cc5-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="27cc5-161">Netzwerk in Mbit/s: Bandbreitenanforderungen in Megabit pro Sekunde (Mbit/s) für die entsprechende Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="27cc5-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="27cc5-162">Arbeitsspeicher in GB: erforderlicher Arbeitsspeicher in Gigabyte (GB) für die entsprechende Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="27cc5-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="27cc5-163">Die grünen Zellen zeigen Empfehlungen für das von Ihnen eingegebene Nutzungsmodell an.</span><span class="sxs-lookup"><span data-stu-id="27cc5-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="27cc5-164">Gesamtzahl der Front-End-Server: die erforderliche Anzahl physischer Server basiert auf dedizierten Servern, auf denen lync Server 2013 mit Dualprozessor, Hex-Kern, mit 2.260 Megazyklen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="27cc5-165">Beachten Sie, dass die Aktivierung von Hyperthreading empfohlen wird und dass die Leistung für Server verbessert wurde, die Audio/Video unterstützen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="27cc5-166">Edgeserver: die Anzahl der erforderlichen Edgeserver, basierend auf 30% aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="27cc5-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="27cc5-167">Dieser Prozentsatz kann im Rechner nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="27cc5-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="27cc5-168">Archivierung/Anruf Detail Aufzeichnung/Quality of Experience Services Store: die Anzahl der Speicher, die für Archivierungs-oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="27cc5-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="27cc5-169">Back-End-Datenbankserver erforderlich (erforderliche Pools): die Anzahl der Back-End-Datenbankserver, die zur Unterstützung der ausgewählten Arbeitsauslastung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="27cc5-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="27cc5-170">Darüber hinaus werden in der Zeile neben Gesamt-Front-End-Server Weitere Informationen zur Last auf den Servern und im Netzwerk für alle geplanten Arbeitslasten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="27cc5-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="27cc5-171">Durchschnittliche CPU-Auslastung: die durchschnittliche CPU-Auslastung pro Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="27cc5-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="27cc5-172">Netzwerk in Mbit/s: die erforderliche Bandbreitenzuweisung zur Unterstützung des von Ihnen eingegebenen Nutzungs Modells.</span><span class="sxs-lookup"><span data-stu-id="27cc5-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="27cc5-173">Arbeitsspeicher in GB: Arbeitsspeicher in Gigabyte, erforderlich für jeden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="27cc5-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="27cc5-174">Berechnen der Leistungskennzahlen für Ihre Prozessoren</span><span class="sxs-lookup"><span data-stu-id="27cc5-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="27cc5-175">Bei allen CPU-Nutzungszahlen in der Tabelle wird davon ausgegangen, dass jeder Server über einen Dualprozessor, einen Hex-Kern mit 2,26 GHz, mindestens 32 GB Arbeitsspeicher sowie 8 oder mehr Festplatten mit 10.000-RPM mit mindestens 72 GB freiem Speicherplatz verfügt.</span><span class="sxs-lookup"><span data-stu-id="27cc5-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="27cc5-176">Wenn Ihre Server unterschiedliche Prozessoren haben, können Sie die Zahlen so anpassen, dass Sie mit Ihrer Hardware übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="27cc5-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


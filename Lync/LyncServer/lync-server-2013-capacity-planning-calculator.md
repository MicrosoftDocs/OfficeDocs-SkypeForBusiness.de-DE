---
title: Lync Server 2013-Kapazitäts planungsrechner
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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="f10aa-102">Verwenden des Kapazitäts Planungs Rechners für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f10aa-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f10aa-103">_**Letztes Änderungsdatum des Themas:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="f10aa-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="f10aa-104">Der Microsoft® lync™ Server 2013 <http://www.microsoft.com/en-us/download/details.aspx?id=36828>-Kapazitäts planungsrechner steht zum Download zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f10aa-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="f10aa-105">Es wurde entwickelt, um Ihnen bei der Ermittlung der Server Anforderungen zu helfen, die auf der Anzahl der Benutzer und Kommunikationsmodalitäten basieren, die in Ihrer Organisation aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f10aa-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="f10aa-106">Sie geben das Profil Ihrer Organisation ein, und der Rechner bietet Empfehlungen, die Ihnen bei der Planung Ihrer Topologie helfen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="f10aa-107">Die vom Rechner erstellten Empfehlungen dienen nur zu Planungszwecken.</span><span class="sxs-lookup"><span data-stu-id="f10aa-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="f10aa-108">Eine tatsächliche Auslastungssimulation ist erforderlich, um sicherzustellen, dass lync Server 2013 angemessen bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f10aa-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="f10aa-109">Verwenden Sie zum Ausführen von Belastungstests unter einer simulierten Belastung das [Stress-und Leistungs Tool lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="f10aa-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="f10aa-110">Nachdem Sie Ihr Benutzerprofil und die Modalitäten festgelegt haben, die Sie für Ihre Benutzer aktivieren möchten, ist es an der Zeit, den Rechner zu verwenden, um die Anzahl der benötigten Server, Arbeitsspeicher und Bandbreite zu planen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="f10aa-111">Diese Version des Rechners bietet keine Anleitungen in Hinblick auf Datenträger-E/A-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="f10aa-112">Dieser Rechner ergänzt den [Microsoft lync Server](http://go.microsoft.com/fwlink/?linkid=282725) und [Microsoft lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="f10aa-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="f10aa-113">Verwenden Sie den Rechner, nachdem Sie die Anleitung gelesen und mithilfe des Planungstools eine empfohlene Topologie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f10aa-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="f10aa-p105">Den besten Nutzen erzielen Sie mit dem Rechner, wenn Sie genaue und ausführliche Informationen zu Ihrem speziellen Benutzerprofil haben. Beispielsweise können der Prozentsatz von VoIP-aktivierten Benutzern, der Durchschnitt der Anrufe pro Benutzer und Stunde, die Anrufdauer und der Prozentsatz von gleichzeitigen Benutzern in Konferenzen einen großen Unterschied hinsichtlich der Serveranforderungen ausmachen. Die Genauigkeit der Empfehlungen, die vom Rechner erstellt werden, hängt von der Genauigkeit der Informationen ab, die Sie bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="f10aa-p105">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="f10aa-117">Arbeiten mit dem Kapazitätsrechner</span><span class="sxs-lookup"><span data-stu-id="f10aa-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="f10aa-118">Der Rechner ist eine Microsoft Excel®-Kalkulationstabelle.</span><span class="sxs-lookup"><span data-stu-id="f10aa-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="f10aa-119">Orange farbige Zellen sind für die Eingabe von Ihnen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="f10aa-120">Es werden Standardwerte eingegeben (80.000-Benutzer in einem Pool mit zwölf Front-End-Servern), aber Sie können diese Werte entsprechend den Anforderungen Ihrer Organisation ändern.</span><span class="sxs-lookup"><span data-stu-id="f10aa-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="f10aa-121">Das Nutzungsmodell enthält die folgenden Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="f10aa-121">The usage model contains the following sections.</span></span> <span data-ttu-id="f10aa-122">Um Ihre Kapazitätsanforderungen zu berechnen, geben Sie Daten wie beschrieben ein:</span><span class="sxs-lookup"><span data-stu-id="f10aa-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="f10aa-123">**Chat und Anwesenheit**</span><span class="sxs-lookup"><span data-stu-id="f10aa-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="f10aa-124">Geben Sie unter Anzahl der Benutzer die Anzahl der Benutzer ein, die gleichzeitig angemeldet sein sollen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="f10aa-125">Diese Anzahl entspricht meist 80 % der Gesamtzahl der bereitgestellten Nutzer.</span><span class="sxs-lookup"><span data-stu-id="f10aa-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="f10aa-126">In den meisten Situationen werden 100 % der gleichzeitigen Nutzer für Chat und Anwesenheit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f10aa-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="f10aa-127">Der Standardwert ist 80.000.</span><span class="sxs-lookup"><span data-stu-id="f10aa-127">The default is 80,000.</span></span>

  - <span data-ttu-id="f10aa-128">Durchschnittliche Anzahl von Kontakten in der Kontaktliste gibt die Anzahl von Kontakten an, die zur Überprüfung Ihrer Systemanforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f10aa-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="f10aa-129">Diese Nummer kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-129">This number is not changeable.</span></span>

<span data-ttu-id="f10aa-130">**Enterprise-VoIP**</span><span class="sxs-lookup"><span data-stu-id="f10aa-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="f10aa-131">Geben Sie in für Enterprise-VoIP aktivierte Benutzer den Prozentsatz der Benutzer ein, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f10aa-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f10aa-132">Der Standardwert ist 60 %.</span><span class="sxs-lookup"><span data-stu-id="f10aa-132">The default is 60%.</span></span>

  - <span data-ttu-id="f10aa-133">Geben Sie in durchschnittliche Anzahl der Anrufe pro Benutzer pro Stunde (Peak) die Anzahl der Anrufe pro Stunde ein, an denen der durchschnittliche Benutzer in Zeiten der Spitzenlast teilnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="f10aa-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="f10aa-134">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="f10aa-134">The default is 4.</span></span>

  - <span data-ttu-id="f10aa-135">Geben Sie in Prozentsatz der Anrufe, die Medienumgehung nutzen den Prozentsatz der Anrufe ein, die von Ihren Nutzern getätigt, aber nicht über den Vermittlungsserver abgewickelt werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="f10aa-136">Der Standardwert ist 65%.</span><span class="sxs-lookup"><span data-stu-id="f10aa-136">The default is 65%.</span></span>

  - <span data-ttu-id="f10aa-137">Geben Sie in Prozentsatz der VoIP-Nutzer, die an UC-PSTN-Anrufen beteiligt sind den Prozentsatz der Anrufe in Ihrer Organisation ein, die Anrufe über das UC-Telefonfestnetz (UC-PSTN) sind.</span><span class="sxs-lookup"><span data-stu-id="f10aa-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="f10aa-138">Der Standardwert ist 60%.</span><span class="sxs-lookup"><span data-stu-id="f10aa-138">The default is 60%</span></span>

  - <span data-ttu-id="f10aa-139">In Prozent der Sprachbenutzer, die an UC-UC-anrufen beteiligt sind, wird der Prozentsatz der Benutzer angezeigt, die für Enterprise-VoIP aktiviert sind und nur für UC-UC-Anrufe aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="f10aa-140">Diese Anzahl wird auf Basis des Werts berechnet, den Sie in Prozentsatz der VoIP-Nutzer, die an UC-PSTN-Anrufen beteiligt sind eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f10aa-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="f10aa-141">**Konferenzen**</span><span class="sxs-lookup"><span data-stu-id="f10aa-141">**Conferencing**</span></span>

  - <span data-ttu-id="f10aa-142">Geben Sie in Prozent der Benutzer in parallelen Konferenzen den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="f10aa-143">Der Standardwert ist 5 %.</span><span class="sxs-lookup"><span data-stu-id="f10aa-143">The default is 5%.</span></span>

  - <span data-ttu-id="f10aa-144">Geben Sie in Prozent der Konferenzen mit nur Gruppen-Chat (keine Stimme) den Prozentsatz der Konferenzen ein, deren Konferenzen nur Chatnachrichten einbeziehen sollen. Das bedeutet, dass keine Audiokomponente enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f10aa-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="f10aa-145">Der Standardwert ist 10%.</span><span class="sxs-lookup"><span data-stu-id="f10aa-145">The default is 10%</span></span>

  - <span data-ttu-id="f10aa-146">Geben Sie in Prozent der Benutzer, die Einwahlkonferenzen verwenden, den Prozentsatz der gleichzeitigen Teilnehmer in Konferenzen ein, die Einwahlkonferenzen verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="f10aa-147">Der Standardwert ist 15 %.</span><span class="sxs-lookup"><span data-stu-id="f10aa-147">The default is 15%.</span></span>

  - <span data-ttu-id="f10aa-148">Geben Sie in Prozent der Konferenzen, die Voice verwenden, den Prozentsatz der Konferenzen ein, die eine Audio-Komponente enthalten sollen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="f10aa-149">Wenn 20 % Ihrer VoIP-Konferenzen auch normale Videoelemente umfassen, aktivieren Sie das Kontrollkästchen Einschließlich Video (kein Multiview).</span><span class="sxs-lookup"><span data-stu-id="f10aa-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="f10aa-150">Wenn 20 % Ihrer Konferenzen auch Multiview-Videoelemente umfassen, aktivieren Sie das Kontrollkästchen Einschließlich Multiview.</span><span class="sxs-lookup"><span data-stu-id="f10aa-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="f10aa-151">Wenn 50 % Ihrer VoIP-Konferenzen auch Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen Einschließlich Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="f10aa-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="f10aa-152">Wenn 20% ihrer Sprachkonferenzen Datenuploads wie Microsoft PowerPoint-® Präsentationen einschließen, aktivieren Sie das Kontrollkästchen einschließlich Webkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="f10aa-153">**Mobilität**</span><span class="sxs-lookup"><span data-stu-id="f10aa-153">**Mobility**</span></span>

  - <span data-ttu-id="f10aa-154">Geben Sie in Prozent der Benutzer, die für Mobilität aktiviert sind, den Prozentsatz der Benutzer ein, die für die Verbindung zu lync Server mithilfe mobiler Geräte aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="f10aa-155">Der Standardwert ist 40 %.</span><span class="sxs-lookup"><span data-stu-id="f10aa-155">The default is 40%.</span></span>

<span data-ttu-id="f10aa-156">Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitäts Rechner Ihre Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="f10aa-157">Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher-und Bandbreitenanforderungen basierend auf Tests an, die in lync Server 2013 Performance Labs ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="f10aa-158">Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variation wird getestet und validiert.</span><span class="sxs-lookup"><span data-stu-id="f10aa-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="f10aa-159">Die folgenden Werte werden berechnet:</span><span class="sxs-lookup"><span data-stu-id="f10aa-159">The following values are calculated:</span></span>

  - <span data-ttu-id="f10aa-160">Front-End-CPU: Prozentsatz der CPU-Auslastung, wenn der gesamte Ladevorgang von einem Front-End-Server mit den gleichen Spezifikationen wie der in Microsoft-Tests verwendete Server gehandhabt wurde.</span><span class="sxs-lookup"><span data-stu-id="f10aa-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="f10aa-161">Netzwerk in MBit/s: Bandbreitenanforderungen in Megabit pro Sekunde (MBit/s) für die entsprechende Arbeitsauslastung.</span><span class="sxs-lookup"><span data-stu-id="f10aa-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="f10aa-162">Arbeitsspeicher in GB: Arbeitsspeicher in Gigabyte (GB), der für die entsprechende Arbeitsauslastung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f10aa-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="f10aa-163">In den grünen Zellen werden Empfehlungen für das Nutzungsmodell angezeigt, das Sie eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f10aa-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="f10aa-164">Gesamtzahl der Front-End-Server: die Anzahl der erforderlichen physikalischen Server basiert auf dedizierten Servern mit lync Server 2013 mit Dualprozessor, Hex-Core und 2.260 Megazyklen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="f10aa-165">Es wird empfohlen, Hyperthreading zu aktivieren, denn damit lässt sich nachweislich die Leistung von Servern verbessern, die Audio/Video unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="f10aa-166">Edgeserver: die Anzahl der erforderlichen Edgeserver, basierend auf 30% aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="f10aa-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="f10aa-167">Dieser Prozentsatz kann im Rechner nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f10aa-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="f10aa-168">Speicher für die Dienste Archivierung/Aufzeichnung von Kommunikationsdatensätzen/Quality of Experience: Die Anzahl von Speichern, die für Archivierungs- oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f10aa-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="f10aa-169">Erforderliche Back-End-Datenbankserver (erforderliche Pools): Die Anzahl von Back-End-Datenbankservern, die erforderlich sind, damit die ausgewählte Auslastung unterstützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f10aa-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="f10aa-170">Die Zeile neben „Gesamtzahl der Front-End-Server“ enthält zusätzlich weitere Informationen zu der Last auf den Servern und im Netzwerk für alle geplanten Auslastungen zusammengenommen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="f10aa-171">Durchschnittliche CPU-Auslastung: Die durchschnittliche CPU-Nutzung pro Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="f10aa-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="f10aa-172">Netzwerk in MBit/s: Die Bandbreitenzuteilung, die erforderlich ist, damit das von Ihnen eingegebene Nutzungsmodell unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f10aa-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="f10aa-173">Arbeitsspeicher in GB: Der Arbeitsspeicher in Gigabyte, der für jeden Front-End-Server erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f10aa-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="f10aa-174">Anpassen an Ihre Prozessoren</span><span class="sxs-lookup"><span data-stu-id="f10aa-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="f10aa-175">Für alle CPU-Nutzungswerte auf dem Arbeitsblatt wird angenommen, dass jeder Server einen Dualprozessor mit sechs Kernen und 2,26 GHz, mindestens 32 GB Arbeitsspeicher und mindestens 8 10.000-U/min-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz hat.</span><span class="sxs-lookup"><span data-stu-id="f10aa-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="f10aa-176">Wenn Ihre Server andere Prozessoren haben, können Sie die Werte entsprechend Ihrer Hardware anpassen.</span><span class="sxs-lookup"><span data-stu-id="f10aa-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


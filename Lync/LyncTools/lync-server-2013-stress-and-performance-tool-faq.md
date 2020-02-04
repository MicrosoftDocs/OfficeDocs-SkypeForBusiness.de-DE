---
title: Häufig gestellte Fragen zu lync Server 2013 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9138a23ee1fa45f3da827832b568852952b0ae4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="25935-102">Häufig gestellte Fragen zu lync Server 2013 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="25935-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25935-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="25935-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="25935-104">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="25935-104">Frequently Asked Questions</span></span>

<span data-ttu-id="25935-105">Hier finden Sie einige häufig gestellte Fragen zum lync Server 2013-Tool Stress und Leistung.</span><span class="sxs-lookup"><span data-stu-id="25935-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="25935-106">Kann ich LyncPerfTool. exe in Production ausführen?</span><span class="sxs-lookup"><span data-stu-id="25935-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="25935-107">Wir empfehlen dies nicht.</span><span class="sxs-lookup"><span data-stu-id="25935-107">We do not recommend this.</span></span> <span data-ttu-id="25935-108">Dieses Tool hat Auswirkungen auf die Serverleistung, Sicherheit und Benutzerfreundlichkeit.</span><span class="sxs-lookup"><span data-stu-id="25935-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="25935-109">Ich habe mich zum ersten Mal bei meinen Benutzern angemeldet.</span><span class="sxs-lookup"><span data-stu-id="25935-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="25935-110">Warum werden die Server mit einer derart großen Auslastung ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="25935-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="25935-111">Wenn sich die Benutzer zum ersten Mal anmelden, werden weitere Vorgänge ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="25935-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="25935-112">Dadurch wird die Leistung auf dem Microsoft SQL Server-Back-End-Server beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="25935-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="25935-113">Wir empfehlen, dass Sie einen kurzen Test ausführen, bei dem alle Benutzer angemeldet sind, und dann die Clients neu starten, bevor Sie Ergebnisse messen.</span><span class="sxs-lookup"><span data-stu-id="25935-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="25935-114">Wir unterstützen nicht mehr als 12 gleichzeitige Benutzeranmeldesitzungen pro Sekunde, dies hängt aber von Ihrer Hardwarekonfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="25935-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="25935-115">Für meine Clients ist der Arbeitsspeicher knapp.</span><span class="sxs-lookup"><span data-stu-id="25935-115">My clients are running out of memory.</span></span> <span data-ttu-id="25935-116">Was soll ich tun?</span><span class="sxs-lookup"><span data-stu-id="25935-116">What should I do?</span></span>

<span data-ttu-id="25935-117">Wenn auf Ihren Clients der Arbeitsspeicher knapp wird, müssen Sie die Anzahl der Benutzer pro Computer verringern.</span><span class="sxs-lookup"><span data-stu-id="25935-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="25935-118">Meine Clients sind immer mit einer CPU von 100 Prozent.</span><span class="sxs-lookup"><span data-stu-id="25935-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="25935-119">Was soll ich tun?</span><span class="sxs-lookup"><span data-stu-id="25935-119">What should I do?</span></span>

<span data-ttu-id="25935-120">Wenn Ihre Clients mit einer sehr großen CPU ausgeführt werden, nachdem sich alle Benutzer angemeldet haben, müssen Sie die Anzahl der Benutzer pro Computer reduzieren.</span><span class="sxs-lookup"><span data-stu-id="25935-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="25935-121">Hohe CPU-Spitzen sind akzeptabel, aber wenn Sie unterstützt werden, müssen Sie die Auslastung reduzieren.</span><span class="sxs-lookup"><span data-stu-id="25935-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="25935-122">Kann ich das Tool auf dem Server selbst ausführen?</span><span class="sxs-lookup"><span data-stu-id="25935-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="25935-123">Nummer</span><span class="sxs-lookup"><span data-stu-id="25935-123">No.</span></span> <span data-ttu-id="25935-124">Dieses Szenario wird nicht unterstützt und kann aufgrund eines binären Konflikts fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="25935-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="25935-125">Da der Punkt darin besteht, den Ressourcenverbrauch auf dem Server zu messen, würde das Ausführen des Tools die Maße bedeutungslos machen.</span><span class="sxs-lookup"><span data-stu-id="25935-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="25935-126">Kann ich LyncPerfTool. exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?</span><span class="sxs-lookup"><span data-stu-id="25935-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="25935-127">Ja.</span><span class="sxs-lookup"><span data-stu-id="25935-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="25935-128">Was bedeutet mpop?</span><span class="sxs-lookup"><span data-stu-id="25935-128">What does MPOP mean?</span></span>

<span data-ttu-id="25935-129">MPOP steht für mehrere Anwesenheits Punkte.</span><span class="sxs-lookup"><span data-stu-id="25935-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="25935-130">Damit soll das Szenario simuliert werden, in dem Benutzer von mehreren Computern bei lync 2013 angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="25935-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="25935-131">Beachten Sie, dass in LyncPerfTool. exe jeder Endpunkt das Standardprofil verwendet (das Profil wird jedoch nicht zwischen den beiden Anwesenheits Punkten aufgeteilt).</span><span class="sxs-lookup"><span data-stu-id="25935-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="25935-132">Ich habe LyncPerfTool. exe gestartet, aber es geschieht nichts.</span><span class="sxs-lookup"><span data-stu-id="25935-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="25935-133">Was ist los?</span><span class="sxs-lookup"><span data-stu-id="25935-133">What’s going on?</span></span>

<span data-ttu-id="25935-134">Überprüfen Sie den Indikator Gesamtzahl aktiver Endpunkte auf den Clients, um festzustellen, ob die Benutzer eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="25935-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="25935-135">Wenn Benutzer keine Verbindung herstellen, überprüfen Sie Ihre lync Server 2013-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="25935-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="25935-136">Dieses Problem tritt in der Regel auf, weil der Servername, das Benutzerpräfix oder das Kennwort falsch ist.</span><span class="sxs-lookup"><span data-stu-id="25935-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="25935-137">Beachten Sie, dass externe Clients den Zugriffs Proxy als TargetServer-Wert angeben sollten.</span><span class="sxs-lookup"><span data-stu-id="25935-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="25935-138">Überprüfen Sie den Port in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="25935-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="25935-139">Woran erkenne ich, dass etwas passiert?</span><span class="sxs-lookup"><span data-stu-id="25935-139">How do I know something is happening?</span></span>

<span data-ttu-id="25935-140">Die verschiedenen LyncPerfTool-Leistungsindikatoren geben an, ob Benutzer eine Verbindung herstellen und Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="25935-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="25935-141">Eine einfache Möglichkeit zur Überprüfung besteht jedoch darin, sich mit lync 2013 bei einem der Konten anzumelden und die gewünschte Aktion durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="25935-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="25935-142">Ich habe Live Communications Server 2007 R2-Kapazitäts Planungs Tools und/oder lync Server 2010 installiert.</span><span class="sxs-lookup"><span data-stu-id="25935-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="25935-143">Ist das in Ordnung?</span><span class="sxs-lookup"><span data-stu-id="25935-143">Is that OK?</span></span>

<span data-ttu-id="25935-144">Nummer</span><span class="sxs-lookup"><span data-stu-id="25935-144">No.</span></span> <span data-ttu-id="25935-145">Es gibt Interoperabilitätsprobleme, und Sie müssen alle vorherigen Versionen dieses Produkts deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="25935-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="25935-146">Werden die Stress-und Leistungstools die CAA-Anruf Informationsserver-Topologie einrichten?</span><span class="sxs-lookup"><span data-stu-id="25935-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="25935-147">Nummer</span><span class="sxs-lookup"><span data-stu-id="25935-147">No.</span></span> <span data-ttu-id="25935-148">Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten und simulieren die Benutzerauslastung.</span><span class="sxs-lookup"><span data-stu-id="25935-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="25935-149">Was ist die maximale Anzahl von Benutzern, die von den Tools unterstützt werden?</span><span class="sxs-lookup"><span data-stu-id="25935-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="25935-150">Wir haben bis zu insgesamt 80.000-Benutzer erstellt und Tests mit insgesamt 30.000 Benutzern durchgeführt, die diese Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="25935-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="25935-151">Wir empfehlen maximal 120.000-Benutzer, auch wenn die technischen Einschränkungen je nach verfügbarer Client-und Server Hardware einen höheren Wert zulassen.</span><span class="sxs-lookup"><span data-stu-id="25935-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


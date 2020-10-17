---
title: FAQ für lync Server 2013 Stress and Performance Tool
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
ms.openlocfilehash: 445448633bc35b8071455ccd0c8e6ff93c3862b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509212"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="0f5bf-102">FAQ für lync Server 2013 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0f5bf-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f5bf-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="0f5bf-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="0f5bf-104">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0f5bf-104">Frequently Asked Questions</span></span>

<span data-ttu-id="0f5bf-105">Hier finden Sie einige häufig gestellte Fragen zum lync Server 2013 Stress-und Leistungs Tool.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="0f5bf-106">Kann ich LyncPerfTool.exe in der Produktion ausführen?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="0f5bf-107">Dies wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-107">We do not recommend this.</span></span> <span data-ttu-id="0f5bf-108">Dieses Tool wirkt sich auf die Serverleistung, die Sicherheit und die Benutzerfreundlichkeit aus.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="0f5bf-109">Ich werde meine Benutzer zum ersten Mal anmelden.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="0f5bf-110">Warum werden die Server mit einer derart hohen Auslastung betrieben?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="0f5bf-111">Wenn sich die Benutzer zum ersten Mal anmelden, treten zusätzliche Vorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="0f5bf-112">Dadurch wird die Leistung auf dem Microsoft SQL Server Back-End-Server beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="0f5bf-113">Es wird empfohlen, dass Sie einen kurzen Test ausführen, der sich auf alle Benutzer anmeldet, und die Clients dann neu starten, bevor Sie Ergebnisse messen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="0f5bf-114">Es werden nicht mehr als 12 gleichzeitige Benutzeranmeldesitzungen pro Sekunde unterstützt, dies hängt jedoch von Ihrer Hardwarekonfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="0f5bf-115">Meine Clients haben keinen Arbeitsspeicher mehr.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-115">My clients are running out of memory.</span></span> <span data-ttu-id="0f5bf-116">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-116">What should I do?</span></span>

<span data-ttu-id="0f5bf-117">Wenn auf Ihren Clients kein Arbeitsspeicher mehr vorhanden ist, müssen Sie die Anzahl der Benutzer pro Computer reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="0f5bf-118">Meine Clients befinden sich immer bei 100 Prozent CPU.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="0f5bf-119">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-119">What should I do?</span></span>

<span data-ttu-id="0f5bf-120">Wenn Ihre Clients mit einer sehr hohen CPU-Leistung betrieben werden, nachdem sich alle Benutzer angemeldet haben, müssen Sie die Anzahl der Benutzer pro Computer reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="0f5bf-121">Hohe CPU-Spitzen sind akzeptabel, wenn Sie jedoch aufrecht erhalten werden, müssen Sie die Last reduzieren.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="0f5bf-122">Kann ich das Tool auf dem Server selbst ausführen?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="0f5bf-123">Nein.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-123">No.</span></span> <span data-ttu-id="0f5bf-124">Dieses Szenario wird nicht unterstützt und kann aufgrund eines binären Konflikts fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="0f5bf-125">Da es sich dabei um die Messung des Ressourcenverbrauchs auf dem Server handelt, würde das Tool dort durchführen, sodass die Messungen bedeutungslos wären.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="0f5bf-126">Kann ich LyncPerfTool.exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="0f5bf-127">Ja.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="0f5bf-128">Was bedeutet mpop?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-128">What does MPOP mean?</span></span>

<span data-ttu-id="0f5bf-129">MPOP steht für mehrere Points of Presence.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="0f5bf-130">Es soll das Szenario simulieren, in dem Benutzer bei lync 2013 von mehreren Computern angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="0f5bf-131">Beachten Sie, dass in LyncPerfTool.exe jeder Endpunkt das Standardprofil verwendet (das Profil wird jedoch nicht zwischen den beiden Points of Presence geteilt).</span><span class="sxs-lookup"><span data-stu-id="0f5bf-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="0f5bf-132">Ich habe angefangen LyncPerfTool.exe aber nichts geschieht.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="0f5bf-133">Was ist denn nun los?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-133">What’s going on?</span></span>

<span data-ttu-id="0f5bf-134">Überprüfen Sie den Indikator Gesamtanzahl aktiver Endpunkte für die Clients, um zu sehen, ob die Benutzer eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="0f5bf-135">Wenn Benutzer keine Verbindung herstellen, überprüfen Sie die lync Server 2013 Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="0f5bf-136">Dieses Problem tritt in der Regel auf, weil der Servername, das Benutzerpräfix oder das Kennwort falsch ist.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="0f5bf-137">Beachten Sie, dass externe Clients den Zugriffs Proxy als TargetServer-Wert angeben sollten.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="0f5bf-138">Überprüfen Sie den Port in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="0f5bf-139">Woher weiß ich, dass etwas passiert?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-139">How do I know something is happening?</span></span>

<span data-ttu-id="0f5bf-140">Die verschiedenen LyncPerfTool-Leistungsindikatoren geben an, ob Benutzer eine Verbindung herstellen und Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="0f5bf-141">Eine einfache Möglichkeit zum Überprüfen besteht jedoch darin, sich mit lync 2013 bei einem der Konten anzumelden und die gewünschte Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="0f5bf-142">Ich habe Live Communications Server Tools zur Kapazitätsplanung für 2007 R2 und/oder lync Server 2010 installiert.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="0f5bf-143">Ist das in Ordnung?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-143">Is that OK?</span></span>

<span data-ttu-id="0f5bf-144">Nein.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-144">No.</span></span> <span data-ttu-id="0f5bf-145">Es gibt Interoperabilitätsprobleme, und Sie müssen alle Vorgängerversionen dieses Produkts deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="0f5bf-146">Werden mit den Stress-und Leistungstools die CAA-Topologie für Anruf Informationsserver eingerichtet?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="0f5bf-147">Nein.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-147">No.</span></span> <span data-ttu-id="0f5bf-148">Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten und simulieren die Benutzerlast.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="0f5bf-149">Wie hoch ist die maximale Anzahl von Benutzern, die von den Tools unterstützt werden?</span><span class="sxs-lookup"><span data-stu-id="0f5bf-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="0f5bf-150">Mit diesen Tools haben wir insgesamt 80.000-Benutzer erstellt und Tests von insgesamt 30.000 Benutzern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="0f5bf-151">Es werden maximal 120.000 Benutzer vorgeschlagen, wobei die technischen Einschränkungen je nach verfügbarer Client-und Server Hardware einen höheren Wert ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0f5bf-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


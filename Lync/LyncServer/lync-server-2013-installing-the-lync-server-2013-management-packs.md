---
title: 'Lync Server 2013: Installieren der lync Server 2013-Verwaltungspakete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc102eccdbaa941e2691df88899c0cc01348838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="4c1af-102">Installieren der lync Server 2013-Verwaltungspakete</span><span class="sxs-lookup"><span data-stu-id="4c1af-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c1af-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4c1af-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4c1af-104">System Center Operations Manager kann nur einen kleinen Teil des Windows-Betriebssystems überwachen.</span><span class="sxs-lookup"><span data-stu-id="4c1af-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="4c1af-105">Sie können die Funktionen von System Center Operations Manager jedoch erweitern, indem Sie Management Packs installieren, Software, die festlegt, welche Elemente von System Center Operations Manager überwacht werden können, einschließlich der Art und Weise, wie diese Elemente überwacht werden sollen und wie Warnungen angezeigt werden sollen. ausgelöst und gemeldet.</span><span class="sxs-lookup"><span data-stu-id="4c1af-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="4c1af-106">Microsoft lync Server 2013 umfasst zwei System Center Operations Manager-Verwaltungspakete, die die folgenden Funktionen bieten:</span><span class="sxs-lookup"><span data-stu-id="4c1af-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="4c1af-107">Das Komponenten-und Benutzer Verwaltungspaket (Microsoft.ls.2013.Monitoring.ComponentAndUser.MP) verfolgt lync-Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Anruf Detaildatensätzen (CDR) oder der Quality of Experience (QoE) protokolliert wurden. Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="4c1af-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="4c1af-108">Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Sofortnachricht oder SMS-Messaging benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="4c1af-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="4c1af-109">SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem mobilen Gerät an ein anderes zu senden.</span><span class="sxs-lookup"><span data-stu-id="4c1af-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c1af-110">Weitere Informationen zum Konfigurieren der Operations Manager-Benachrichtigung finden Sie unter Konfigurieren der Benachrichtigung in der <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>TechNet-Bibliothek unter.</span><span class="sxs-lookup"><span data-stu-id="4c1af-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="4c1af-111">Das aktive Überwachungspaket (Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP) testet proaktiv wichtige lync Server-Komponenten wie die Anmeldung am System, den Austausch von Sofortnachrichten oder das tätigen von Anrufen an ein Telefon, das sich auf dem öffentlich geschalteten Telefon befindet. Netzwerk (PSTN).</span><span class="sxs-lookup"><span data-stu-id="4c1af-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="4c1af-112">Diese Tests werden mithilfe der Cmdlets für synthetische lync Server-Transaktionen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4c1af-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="4c1af-113">Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="4c1af-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="4c1af-114">Wenn diese simulierte Nachrichten Unterhaltung fehlschlägt, wird eine Benachrichtigung generiert.</span><span class="sxs-lookup"><span data-stu-id="4c1af-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="4c1af-115">Zu den beiden in lync Server 2013 enthaltenen Management Packs gehören eine große Anzahl von Verbesserungen hinsichtlich der Management Packs, die mit Microsoft lync Server 2010 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c1af-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="4c1af-116">Das lync Server 2013-Komponenten-Management Pack ist beispielsweise nicht darauf limitiert, lync Server selbst zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="4c1af-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="4c1af-117">Neben dem Überwachen von Ereignisprotokollen und Leistungsindikatoren für lync Server kann das Komponenten-Management Pack auch die Leistung von wichtigen Elementen wie:</span><span class="sxs-lookup"><span data-stu-id="4c1af-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="4c1af-118">**Internetinformationsdienste (IIS)-**   Benachrichtigungen werden ausgegeben, wenn Internetinformationsdienste offline geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4c1af-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="4c1af-119">Dies ist wichtig, da die lync Server-Webdienste von IIS abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="4c1af-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="4c1af-120">**Benachrichtigungen zur Prozessnutzung**   werden ausgegeben, wenn Systemressourcen (wie verfügbarer Arbeitsspeicher) langsam ablaufen.</span><span class="sxs-lookup"><span data-stu-id="4c1af-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="4c1af-121">Diese Benachrichtigungen werden selbst dann ausgestellt, wenn lync Server nicht für die Verwendung des Systems mit großem Nutzen verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="4c1af-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="4c1af-122">**Benachrichtigungen über Computer Fehlerereignisse**   werden bei einem Hardware-oder Softwareproblem ausgegeben, das die Lebensfähigkeit eines Servers gefährdet.</span><span class="sxs-lookup"><span data-stu-id="4c1af-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="4c1af-123">Lync Server-Administratoren werden beispielsweise benachrichtigt, wenn ein Server den Eindruck hat, dass ein Festplattenfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="4c1af-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="4c1af-124">Die neuen Management Packs verfügen auch über eine verbesserte Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="4c1af-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="4c1af-125">Zu den neuen Berichten für lync Server 2013 gehören:</span><span class="sxs-lookup"><span data-stu-id="4c1af-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="4c1af-126">**Bericht zur Verfügbarkeit von Szenarien bis zum**   Ende dieser Bericht enthält Informationen zur Verfügbarkeit/Uptime für wichtige lync Server-Dienste wie Registrierung oder Anwesenheit.</span><span class="sxs-lookup"><span data-stu-id="4c1af-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="4c1af-127">**Kapazitäts Bericht**   mithilfe von Leistungsindikatorinformationen werden in diesem Bericht Trends für Systemkomponenten wie Speicherverfügbarkeit und Prozessorauslastung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4c1af-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="4c1af-128">**Komponentenbericht**   dieser Bericht listet die obersten Warnungs Generatoren auf, die nach lync Server-Komponente gruppiert sind.</span><span class="sxs-lookup"><span data-stu-id="4c1af-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="4c1af-129">Zusätzlich zu diesen vordefinierten Berichten melden die Management Packs für lync Server 2013 automatisch Warnungen für die Zuverlässigkeit von Anrufen (Metriken, die mit der Anruf Detail Aufzeichnung gemessen werden) und QoE-Zustände (Metriken, die nach der Qualität der Erfahrung gemessen werden).</span><span class="sxs-lookup"><span data-stu-id="4c1af-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="4c1af-130">Wenn Sie die Anruf Detail Aufzeichnung aktiviert haben, können Sie die Zuverlässigkeits Benachrichtigungen für Anrufe überprüfen, indem Sie die folgenden Schritte in der System Center Operations Manager-Konsole ausführen:</span><span class="sxs-lookup"><span data-stu-id="4c1af-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="4c1af-131">Erweitern Sie **Überwachung**, erweitern Sie **Microsoft lync Server 2013 Health**, erweitern Sie die **Anruf Zuverlässigkeit und die Medienqualität**, und klicken Sie dann auf **Anruf Zuverlässigkeit**.</span><span class="sxs-lookup"><span data-stu-id="4c1af-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="4c1af-132">Führen Sie die folgenden Schritte über die System Center Operations Manager-Konsole aus, um die Benachrichtigung über die Qualität der Erfahrung anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="4c1af-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="4c1af-133">Erweitern Sie **Überwachung**, erweitern Sie **Microsoft lync Server 2013 Health**, erweitern Sie die **Anruf Zuverlässigkeit und Medienqualität**, und erweitern Sie dann **Medienqualität**.</span><span class="sxs-lookup"><span data-stu-id="4c1af-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="4c1af-134">Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in Microsoft lync Server 2010 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c1af-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="4c1af-135">Dies bedeutet, dass sich jeder System Center-Agent im wesentlichen selbst erkennt und seine Existenz dem zentralen Verwaltungs Server meldet.</span><span class="sxs-lookup"><span data-stu-id="4c1af-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="4c1af-136">Die Verwendung der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht auch die unterschiedlichen Versionen der lync Server-Verwaltungspakete (beispielsweise Management Packs für lync Server 2010 und Management Packs für lync Server 2013), um koexistieren.</span><span class="sxs-lookup"><span data-stu-id="4c1af-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


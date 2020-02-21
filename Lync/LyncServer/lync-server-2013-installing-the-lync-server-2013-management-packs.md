---
title: 'Lync Server 2013: Installieren der lync Server 2013 Management Packs'
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
ms.openlocfilehash: e2a6cd3ca0c58a6101d6e46e253e3edf09dec025
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="be6e1-102">Installieren der lync Server 2013 Management Packs</span><span class="sxs-lookup"><span data-stu-id="be6e1-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be6e1-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="be6e1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="be6e1-104">System Center Operations Manager kann nur einen kleinen Teil des Windows-Betriebssystems überwachen.</span><span class="sxs-lookup"><span data-stu-id="be6e1-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="be6e1-105">Sie können die Funktionen von System Center Operations Manager jedoch erweitern, indem Sie Management Packs installieren, Software, die bestimmt, welche Elemente von System Center Operations Manager überwacht werden können, einschließlich der Art und Weise, wie diese Elemente überwacht werden sollen und wie Warnungen ausgelöst und gemeldet.</span><span class="sxs-lookup"><span data-stu-id="be6e1-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="be6e1-106">Microsoft lync Server 2013 enthält zwei System Center Operations Manager-Management Packs, die die folgenden Funktionen bieten:</span><span class="sxs-lookup"><span data-stu-id="be6e1-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="be6e1-107">Das Component and User Management Pack (Microsoft.ls.2013.Monitoring.ComponentAndUser.MP) verfolgt lync Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Kommunikationsdatensätzen (KDS) oder der Quality of Experience (QoE) protokolliert wurden. Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="be6e1-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="be6e1-108">Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Chatnachrichten oder SMS-Messaging benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="be6e1-109">SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem Mobilgerät an ein anderes zu senden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be6e1-110">Weitere Informationen zum Konfigurieren von Operations Manager-Benachrichtigungen finden Sie unter Konfigurieren der Benachrichtigung in der <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>TechNet-Bibliothek unter.</span><span class="sxs-lookup"><span data-stu-id="be6e1-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="be6e1-111">Das Active Monitoring Pack (Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP) testet die Schlüssel lync Server Komponenten, beispielsweise die Anmeldung am System, den Austausch von Chatnachrichten oder das tätigen von Anrufen an ein Telefon auf dem öffentlichen Switched Phone proaktiv. Netzwerk (PSTN).</span><span class="sxs-lookup"><span data-stu-id="be6e1-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="be6e1-112">Diese Tests werden mithilfe der Cmdlets für synthetische Transaktionen lync Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be6e1-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="be6e1-113">Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="be6e1-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="be6e1-114">Wenn bei dieser simulierten Nachrichtenunterhaltung ein Fehler auftritt, wird eine Benachrichtigung erzeugt.</span><span class="sxs-lookup"><span data-stu-id="be6e1-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="be6e1-115">Die beiden in lync Server 2013 enthaltenen Management Packs umfassen eine große Anzahl von Verbesserungen hinsichtlich der mit Microsoft lync Server 2010 verwendeten Management Packs.</span><span class="sxs-lookup"><span data-stu-id="be6e1-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="be6e1-116">Beispielsweise ist das Management Pack für die lync Server 2013-Komponente nicht auf die Überwachung lync Server selbstlimitiert.</span><span class="sxs-lookup"><span data-stu-id="be6e1-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="be6e1-117">Zusätzlich zur Überwachung von Ereignisprotokollen und Leistungsindikatoren für lync Server kann das Component Management Pack auch die Leistung von und Warnungen für wichtige Elemente wie die folgenden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="be6e1-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="be6e1-118">**Internet Information Services (IIS)**   Warnungen werden ausgegeben, wenn Internet Informationsdienste offline geschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="be6e1-119">Dies ist wichtig, da die lync Server-Webdienste von IIS abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="be6e1-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="be6e1-120">**Warnungen zur Prozess Verwendung**   werden ausgegeben, wenn Systemressourcen (wie der verfügbare Arbeitsspeicher) langsam beginnen zu laufen.</span><span class="sxs-lookup"><span data-stu-id="be6e1-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="be6e1-121">Diese Warnungen werden auch dann ausgegeben, wenn lync Server nicht für die hohe Systemauslastung verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="be6e1-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="be6e1-122">\*\*\*\*   Bei einem Hardware-oder Softwareproblem, das die Lebensfähigkeit eines Servers gefährdet, werden Warnungen zu Computer Fehlern ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="be6e1-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="be6e1-123">Beispielsweise werden lync Server Administratoren benachrichtigt, wenn ein Server in Gefahr zu sein scheint, dass ein Festplattenfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="be6e1-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="be6e1-124">Die neuen Management Packs verfügen außerdem über eine erweiterte Berichtsfunktion.</span><span class="sxs-lookup"><span data-stu-id="be6e1-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="be6e1-125">Zu den neuen Berichten für lync Server 2013 gehören:</span><span class="sxs-lookup"><span data-stu-id="be6e1-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="be6e1-126">**End-to-End-Szenario-Verfügbarkeitsbericht**   in diesem Bericht wird die Verfügbarkeit/Uptime für wichtige lync Server Dienste wie Registrierung oder Anwesenheit erläutert.</span><span class="sxs-lookup"><span data-stu-id="be6e1-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="be6e1-127">**Kapazitäts Bericht**   mit Leistungsindikatorinformationen zeigt dieser Bericht Trends für Systemkomponenten wie Arbeitsspeicher Verfügbarkeit und Prozessorauslastung.</span><span class="sxs-lookup"><span data-stu-id="be6e1-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="be6e1-128">**Komponentenbericht**   in diesem Bericht werden die wichtigsten Warnungs Generatoren aufgelistet, die nach lync Server Komponente gruppiert sind.</span><span class="sxs-lookup"><span data-stu-id="be6e1-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="be6e1-129">Zusätzlich zu diesen vorgefertigten Berichten melden die Management Packs für lync Server 2013 automatisch Warnungen für die Zuverlässigkeit von Anrufen (Metriken, die bei der Aufzeichnung von Kommunikationsdatensätzen gemessen werden) und QoE-Zustände (Metriken, gemessen an der Qualität der Erfahrung).</span><span class="sxs-lookup"><span data-stu-id="be6e1-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="be6e1-130">Wenn Sie die Aufzeichnung von Anrufdetails aktiviert haben, können Sie Benachrichtigungen über die Anruf Zuverlässigkeit überprüfen, indem Sie das folgende Verfahren in der System Center Operations Manager-Konsole ausführen:</span><span class="sxs-lookup"><span data-stu-id="be6e1-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="be6e1-131">Erweitern Sie **Überwachen**, **Zustand Microsoft Lync Server 2013** und **Anrufzuverlässigkeit und Medienqualität**, und klicken Sie dann auf **Anrufzuverlässigkeit**.</span><span class="sxs-lookup"><span data-stu-id="be6e1-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="be6e1-132">Führen Sie dieses Verfahren in der System Center Operations Manager-Konsole aus, um die Quality of Experience-Warnungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="be6e1-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="be6e1-133">Erweitern Sie **Überwachen**, **Zustand Microsoft Lync Server 2013** und **Anrufzuverlässigkeit und Medienqualität**, und erweitern Sie dann **Medienqualität**.</span><span class="sxs-lookup"><span data-stu-id="be6e1-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="be6e1-134">Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in Microsoft lync Server 2010 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be6e1-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="be6e1-135">Dies bedeutet, dass sich jeder System Center-Agent im wesentlichen selbst erkennt und seine Existenz dem zentralen Verwaltungs Server meldet.</span><span class="sxs-lookup"><span data-stu-id="be6e1-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="be6e1-136">Das Verwenden der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht auch unterschiedliche Versionen der lync Server Management Packs (beispielsweise Management Packs für lync Server 2010 und Management Packs für lync Server 2013), um Koexistenz.</span><span class="sxs-lookup"><span data-stu-id="be6e1-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


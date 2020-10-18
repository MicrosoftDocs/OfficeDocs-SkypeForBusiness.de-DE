---
title: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten'
description: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f2a1812d76a49d487bea35acae3e22ea403f105
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580041"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="6e617-103">Anzeigen und Analysieren von Monitoring Server-Berichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e617-103">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e617-104">_**Letztes Änderungsstand des Themas:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="6e617-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="6e617-105">In Monitoring Server Berichten werden verschiedene Maßnahmen zur Sprachqualität bereitgestellt, um die QoE-Überwachung zu überwachen, die den Endbenutzern zugestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6e617-105">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="6e617-106">Darüber hinaus enthält Monitoring Server mehrere integrierte Berichte, die Ihre Organisation verwenden kann, um Trends im Zusammenhang mit der Verwendung und Medienqualität im Netzwerk Ihres Unternehmens zu beobachten und Probleme mit der Medienqualität zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6e617-106">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="6e617-107">Ein primärer Bestandteil des Aufhaltens von Monitoring Server Berichten, die für tägliche und wöchentliche Vorgänge interessant sind, ist das Anzeigen und Analysieren von Medien Qualitätsberichten, insbesondere:</span><span class="sxs-lookup"><span data-stu-id="6e617-107">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="6e617-108">QoE-Zusammenfassung/Trend Berichte</span><span class="sxs-lookup"><span data-stu-id="6e617-108">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="6e617-109">QoE-Leistungsberichte</span><span class="sxs-lookup"><span data-stu-id="6e617-109">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="6e617-110">Anzeigen von Berichten vom Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="6e617-110">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="6e617-111">Suchen Sie in einem Webbrowser nach den Servern, die die SQL Reporting Services hosten.</span><span class="sxs-lookup"><span data-stu-id="6e617-111">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="6e617-112">Zeigen Sie die erforderlichen Berichte auf dem Browser Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="6e617-112">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="6e617-113">Optional Exportieren Sie einen Bericht, indem Sie die Exportoption und das erforderliche Ausgabeformat auswählen.</span><span class="sxs-lookup"><span data-stu-id="6e617-113">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="6e617-114">Konfigurieren der Aufzeichnung von Anrufdetails (KDS)</span><span class="sxs-lookup"><span data-stu-id="6e617-114">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="6e617-115">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Berechtigungen verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6e617-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6e617-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e617-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6e617-117">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="6e617-118">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="6e617-118">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="6e617-119">Um die Bereinigung zu aktivieren, wählen Sie **für Monitoring Server die Option Löschen aus**.</span><span class="sxs-lookup"><span data-stu-id="6e617-119">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="6e617-120">In **Keep Call Detail Recordings for Maximum Duration (Days):** wählen Sie die maximale Anzahl von Tagen aus, für die die Aufzeichnung von Gesprächs Details aufbewahrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e617-120">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="6e617-121">Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6e617-121">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="6e617-122">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="6e617-123">Konfigurieren von QoE</span><span class="sxs-lookup"><span data-stu-id="6e617-123">Configure QoE</span></span>

1.  <span data-ttu-id="6e617-124">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="6e617-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6e617-125">Ausführliche Informationen finden Sie unter Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="6e617-125">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="6e617-126">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e617-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6e617-127">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="6e617-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="6e617-128">Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-128">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="6e617-129">Um die Bereinigung zu aktivieren, wählen Sie **für Monitoring Server die Option Löschen aus**.</span><span class="sxs-lookup"><span data-stu-id="6e617-129">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="6e617-130">In **Keep Call Detail Recordings for Maximum Duration (Days):** wählen Sie die maximale Anzahl von Tagen aus, für die QoE-Daten aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6e617-130">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="6e617-131">Klicken Sie auf Commit ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e617-131">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="6e617-132">Ändern der Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6e617-132">Change the archiving policy</span></span>

1.  <span data-ttu-id="6e617-133">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6e617-133">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6e617-134">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e617-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6e617-135">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="6e617-135">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="6e617-136">Klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-136">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6e617-137">Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6e617-137">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="6e617-138">Aktivieren oder deaktivieren Sie das Kontrollkästchen **interne Kommunikation archivieren** , um die interne Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e617-138">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="6e617-139">Aktivieren oder deaktivieren Sie das Kontrollkästchen **externe Kommunikation archivieren** , um die externe Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e617-139">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="6e617-140">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-140">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="6e617-141">Anwenden einer Archivierungsrichtlinie auf einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="6e617-141">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="6e617-142">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6e617-142">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6e617-143">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e617-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="6e617-144">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6e617-144">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="6e617-145">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-145">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6e617-146">Wählen Sie im Abschnitt **lync Server Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6e617-146">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="6e617-147">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6e617-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e617-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e617-148">See Also</span></span>


[<span data-ttu-id="6e617-149">Verwenden von Überwachungsberichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e617-149">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="6e617-150">Bericht über die Server Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e617-150">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="6e617-151">Vergleichsbericht über Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e617-151">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


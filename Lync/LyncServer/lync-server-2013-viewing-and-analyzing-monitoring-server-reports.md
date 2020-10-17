---
title: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten'
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
ms.openlocfilehash: 7416b54e7b1ddb5bfc41c07502802c7c120a93ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523572"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="7e107-102">Anzeigen und Analysieren von Monitoring Server-Berichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e107-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e107-103">_**Letztes Änderungsstand des Themas:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="7e107-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="7e107-104">In Monitoring Server Berichten werden verschiedene Maßnahmen zur Sprachqualität bereitgestellt, um die QoE-Überwachung zu überwachen, die den Endbenutzern zugestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7e107-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="7e107-105">Darüber hinaus enthält Monitoring Server mehrere integrierte Berichte, die Ihre Organisation verwenden kann, um Trends im Zusammenhang mit der Verwendung und Medienqualität im Netzwerk Ihres Unternehmens zu beobachten und Probleme mit der Medienqualität zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7e107-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="7e107-106">Ein primärer Bestandteil des Aufhaltens von Monitoring Server Berichten, die für tägliche und wöchentliche Vorgänge interessant sind, ist das Anzeigen und Analysieren von Medien Qualitätsberichten, insbesondere:</span><span class="sxs-lookup"><span data-stu-id="7e107-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="7e107-107">QoE-Zusammenfassung/Trend Berichte</span><span class="sxs-lookup"><span data-stu-id="7e107-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="7e107-108">QoE-Leistungsberichte</span><span class="sxs-lookup"><span data-stu-id="7e107-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="7e107-109">Anzeigen von Berichten vom Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="7e107-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="7e107-110">Suchen Sie in einem Webbrowser nach den Servern, die die SQL Reporting Services hosten.</span><span class="sxs-lookup"><span data-stu-id="7e107-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="7e107-111">Zeigen Sie die erforderlichen Berichte auf dem Browser Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="7e107-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="7e107-112">Optional Exportieren Sie einen Bericht, indem Sie die Exportoption und das erforderliche Ausgabeformat auswählen.</span><span class="sxs-lookup"><span data-stu-id="7e107-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="7e107-113">Konfigurieren der Aufzeichnung von Anrufdetails (KDS)</span><span class="sxs-lookup"><span data-stu-id="7e107-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="7e107-114">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Berechtigungen verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="7e107-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7e107-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e107-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7e107-116">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="7e107-117">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="7e107-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="7e107-118">Um die Bereinigung zu aktivieren, wählen Sie **für Monitoring Server die Option Löschen aus**.</span><span class="sxs-lookup"><span data-stu-id="7e107-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="7e107-119">In **Keep Call Detail Recordings for Maximum Duration (Days):** wählen Sie die maximale Anzahl von Tagen aus, für die die Aufzeichnung von Gesprächs Details aufbewahrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e107-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="7e107-120">Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7e107-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="7e107-121">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="7e107-122">Konfigurieren von QoE</span><span class="sxs-lookup"><span data-stu-id="7e107-122">Configure QoE</span></span>

1.  <span data-ttu-id="7e107-123">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="7e107-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7e107-124">Ausführliche Informationen finden Sie unter Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="7e107-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="7e107-125">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e107-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7e107-126">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="7e107-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="7e107-127">Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="7e107-128">Um die Bereinigung zu aktivieren, wählen Sie **für Monitoring Server die Option Löschen aus**.</span><span class="sxs-lookup"><span data-stu-id="7e107-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="7e107-129">In **Keep Call Detail Recordings for Maximum Duration (Days):** wählen Sie die maximale Anzahl von Tagen aus, für die QoE-Daten aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7e107-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="7e107-130">Klicken Sie auf Commit ausführen.</span><span class="sxs-lookup"><span data-stu-id="7e107-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="7e107-131">Ändern der Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7e107-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="7e107-132">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e107-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7e107-133">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e107-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7e107-134">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="7e107-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="7e107-135">Klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7e107-136">Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7e107-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="7e107-137">Aktivieren oder deaktivieren Sie das Kontrollkästchen **interne Kommunikation archivieren** , um die interne Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e107-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="7e107-138">Aktivieren oder deaktivieren Sie das Kontrollkästchen **externe Kommunikation archivieren** , um die externe Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e107-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="7e107-139">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="7e107-140">Anwenden einer Archivierungsrichtlinie auf einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="7e107-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="7e107-141">Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e107-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7e107-142">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e107-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7e107-143">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7e107-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="7e107-144">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7e107-145">Wählen Sie im Abschnitt **lync Server Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7e107-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="7e107-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7e107-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e107-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e107-147">See Also</span></span>


[<span data-ttu-id="7e107-148">Verwenden von Überwachungsberichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e107-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="7e107-149">Bericht über die Server Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e107-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="7e107-150">Vergleichsbericht über Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e107-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


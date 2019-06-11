---
title: 'Lync Server 2013: anzeigen und Analysieren von Monitoring Server-Berichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="20b79-102">Anzeigen und Analysieren von Monitoring Server-Berichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b79-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20b79-103">_**Letztes Änderungsdatum des Themas:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="20b79-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="20b79-104">Monitoring Server-Berichte bieten verschiedene Maßnahmen zur Sprachqualität, um die QoE zu überwachen, die an Endbenutzer übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="20b79-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="20b79-105">Darüber hinaus enthält Monitoring Server mehrere integrierte Berichte, die Ihre Organisation verwenden kann, um die Trends zur Verwendung und Medienqualität im Netzwerk Ihrer Organisation zu beobachten und Probleme mit der Medienqualität zu beheben.</span><span class="sxs-lookup"><span data-stu-id="20b79-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="20b79-106">Ein primärer Bestandteil des Haltens von Monitoring Server-Berichten, die für tägliche und wöchentliche Vorgänge interessant sind, ist das Anzeigen und Analysieren von Berichten zur Medienqualität, insbesondere:</span><span class="sxs-lookup"><span data-stu-id="20b79-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="20b79-107">QoE-Zusammenfassung/Trend Berichte</span><span class="sxs-lookup"><span data-stu-id="20b79-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="20b79-108">QoE-Leistungsberichte</span><span class="sxs-lookup"><span data-stu-id="20b79-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="20b79-109">Anzeigen von Berichten vom Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="20b79-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="20b79-110">Suchen Sie in einem Webbrowser nach den Servern, die die SQL Reporting Services hosten.</span><span class="sxs-lookup"><span data-stu-id="20b79-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="20b79-111">Zeigen Sie die erforderlichen Berichte über den Browser-Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="20b79-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="20b79-112">Optional Exportieren eines Berichts durch Auswählen der Exportoption und des erforderlichen Ausgabeformats</span><span class="sxs-lookup"><span data-stu-id="20b79-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="20b79-113">Konfigurieren der Anrufdetailaufzeichnung (CDR)</span><span class="sxs-lookup"><span data-stu-id="20b79-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="20b79-114">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Berechtigungen verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="20b79-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="20b79-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20b79-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="20b79-116">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="20b79-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="20b79-117">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="20b79-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="20b79-118">Wenn Sie die Bereinigung aktivieren möchten, wählen Sie die Option **zum Entfernen von Überwachungs Servern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="20b79-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="20b79-119">Unter " **Anrufdetails aufzeichnen" für maximale Dauer (Tage):** wählen Sie die maximale Anzahl von Tagen aus, für die Anruf Detail Aufzeichnungen aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20b79-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="20b79-120">Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20b79-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="20b79-121">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="20b79-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="20b79-122">Konfigurieren von QoE</span><span class="sxs-lookup"><span data-stu-id="20b79-122">Configure QoE</span></span>

1.  <span data-ttu-id="20b79-123">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="20b79-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="20b79-124">Ausführliche Informationen finden Sie unter Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="20b79-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="20b79-125">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20b79-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="20b79-126">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="20b79-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="20b79-127">Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="20b79-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="20b79-128">Wenn Sie die Bereinigung aktivieren möchten, wählen Sie die Option **zum Entfernen von Überwachungs Servern aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="20b79-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="20b79-129">In " **Anrufdetails aufzeichnen" für maximale Dauer (Tage):** wählen Sie die maximale Anzahl von Tagen aus, die QoE-Daten beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20b79-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="20b79-130">Klicken Sie auf Commit ausführen.</span><span class="sxs-lookup"><span data-stu-id="20b79-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="20b79-131">Ändern der Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="20b79-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="20b79-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="20b79-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="20b79-133">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20b79-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="20b79-134">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="20b79-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="20b79-135">Klicken Sie in der Liste der Richtlinien auf **Global**, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="20b79-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="20b79-136">Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="20b79-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="20b79-137">Aktivieren oder deaktivieren Sie das Kontrollkästchen **interne Kommunikation archivieren** , um die interne Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="20b79-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="20b79-138">Wenn Sie die externe Archivierung für die Bereitstellung aktivieren oder deaktivieren möchten, aktivieren oder deaktivieren Sie das Kontrollkästchen **externe Kommunikation archivieren** .</span><span class="sxs-lookup"><span data-stu-id="20b79-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="20b79-139">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="20b79-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="20b79-140">Anwenden einer Archivierungsrichtlinie auf einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="20b79-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="20b79-141">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="20b79-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="20b79-142">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20b79-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="20b79-143">Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="20b79-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="20b79-144">Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="20b79-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="20b79-145">Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="20b79-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="20b79-146">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="20b79-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20b79-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20b79-147">See Also</span></span>


[<span data-ttu-id="20b79-148">Verwenden von Überwachungsberichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b79-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="20b79-149">Bericht zur Server Leistung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b79-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="20b79-150">Bericht zum Vergleich der Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b79-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


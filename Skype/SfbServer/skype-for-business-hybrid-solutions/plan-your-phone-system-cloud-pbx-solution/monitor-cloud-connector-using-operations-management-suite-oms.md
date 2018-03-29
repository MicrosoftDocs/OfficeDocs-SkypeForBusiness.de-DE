---
title: Überwachen von Cloud-Connector mithilfe von Operationen Management Suite (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lesen Sie in diesem Thema erfahren, wie Ihre Cloud-Connector-Version 2.1 und höher Bereitstellung überwachen, mithilfe von Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 5e03504f27eadbb235c1b5c84e8c7a19d66aea7d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="7af91-103">Überwachen von Cloud-Connector mithilfe von Operationen Management Suite (OMS)</span><span class="sxs-lookup"><span data-stu-id="7af91-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>
 
<span data-ttu-id="7af91-104">Lesen Sie in diesem Thema erfahren, wie Ihre Cloud-Connector-Version 2.1 und höher Bereitstellung überwachen, mithilfe von Microsoft Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="7af91-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>
  
<span data-ttu-id="7af91-105">Sie können nun Ihre Cloud-Connector-Version 2.1 und höher Bereitstellung mithilfe von Operationen Management Suite (OMS), eine Cloud von Microsoft IT-Management-Lösung überwachen.</span><span class="sxs-lookup"><span data-stu-id="7af91-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="7af91-106">OMS-Protokoll Analytics können Sie zum Überwachen und analysieren die Verfügbarkeit und Leistung von Ressourcen, einschließlich der physischen und virtuellen Computern.</span><span class="sxs-lookup"><span data-stu-id="7af91-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="7af91-107">Weitere Informationen zu OMS und Protokoll Analytics, finden Sie unter [Was Vorgänge Management Suite (OMS) ist?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="7af91-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>
  
<span data-ttu-id="7af91-108">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="7af91-108">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="7af91-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7af91-109">Prerequisites</span></span>
    
- <span data-ttu-id="7af91-110">Konfigurieren von Cloud-Connector zur Verwendung von OMS</span><span class="sxs-lookup"><span data-stu-id="7af91-110">Configure Cloud Connector to use OMS</span></span>
    
- <span data-ttu-id="7af91-111">Konfigurieren von OMS</span><span class="sxs-lookup"><span data-stu-id="7af91-111">Configure OMS</span></span>
    
- <span data-ttu-id="7af91-112">Analysieren der Benachrichtigungen in das Protokoll Analytics repository</span><span class="sxs-lookup"><span data-stu-id="7af91-112">Analyze the alerts in your Log Analytics repository</span></span>
    
- <span data-ttu-id="7af91-113">Empfohlene monitoring set</span><span class="sxs-lookup"><span data-stu-id="7af91-113">Recommended monitoring set</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="7af91-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7af91-114">Prerequisites</span></span>

<span data-ttu-id="7af91-115">Bevor Sie zum Überwachen der bereitstellungs Cloud Connector OMS verwenden können, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7af91-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>
  
- <span data-ttu-id="7af91-116">**Ein Azure-Konto und einem OMS-Arbeitsbereich.**</span><span class="sxs-lookup"><span data-stu-id="7af91-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="7af91-117">Wenn Sie bereits ein Azure-Konto besitzen, müssen Sie die Verwendung von OMS-Protokoll Analytics erstellen.</span><span class="sxs-lookup"><span data-stu-id="7af91-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="7af91-118">Informationen dazu, wie Sie ein Azure-Konto erstellen und Einrichten von einem OMS-Arbeitsbereich finden Sie unter [Erste Schritte mit einem Protokoll Analytics Arbeitsbereich](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="7af91-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>
    
- <span data-ttu-id="7af91-119">**Cloud-Connector Version 2.1 oder höher**</span><span class="sxs-lookup"><span data-stu-id="7af91-119">**Cloud Connector version 2.1 or later**</span></span>
    
- <span data-ttu-id="7af91-120">**Protokoll Analytics neue Protokoll Suche** ist erforderlich für die Überwachung von Cloud-Connector.</span><span class="sxs-lookup"><span data-stu-id="7af91-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="7af91-121">Weitere Informationen finden Sie unter [Upgrade Azure Protokoll Analytics Arbeitsbereich mit neue Log-Suche](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="7af91-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>
    
## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="7af91-122">Konfigurieren von Cloud-Connector zur Verwendung von OMS</span><span class="sxs-lookup"><span data-stu-id="7af91-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="7af91-123">Sie müssen die Cloud Connector lokale Umgebung zur Verwendung von OMS konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7af91-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="7af91-124">Zu diesem Zweck benötigen Sie Ihre OMS Workspace-ID und Schlüssel, den Sie mithilfe des OMS-Portal finden: Einstellungen –\>Datenquellen verbunden –\> Windows-Servern:</span><span class="sxs-lookup"><span data-stu-id="7af91-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>
  
![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
<span data-ttu-id="7af91-126">Konfiguration von Cloud-Connector zur Verwendung von OMS, hängt von Ihrem Szenario:</span><span class="sxs-lookup"><span data-stu-id="7af91-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>
  
- <span data-ttu-id="7af91-127">**Wenn Sie eine neue Cloud-Connector Appliance installieren oder Sie eine Einheit erneut bereitstellen möchten**, gehen Sie folgendermaßen vor dem Ausführen von Install-CcAppliance vor:</span><span class="sxs-lookup"><span data-stu-id="7af91-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>
    
1. <span data-ttu-id="7af91-128">Legen Sie in der Datei CloudConnector.ini [allgemeine] Abschnitt des OMSEnabled-Parameters auf true fest.</span><span class="sxs-lookup"><span data-stu-id="7af91-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>
    
    <span data-ttu-id="7af91-129">Jedes Mal Cloud-Connector bereitgestellt oder aktualisiert, versucht er, den OMS-Agenten automatisch auf den virtuellen Computern zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7af91-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="7af91-130">Aktivieren Sie dieses Feature, sodass der OMS-Agent die automatische Aktualisierung von Cloud-Connector überstehen kann.</span><span class="sxs-lookup"><span data-stu-id="7af91-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>
    
2. <span data-ttu-id="7af91-131">Um die OMS-ID und Schlüssel zu konfigurieren, führen Sie Set-CcCredential - AccountType OMSWorkspace aus.</span><span class="sxs-lookup"><span data-stu-id="7af91-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
- <span data-ttu-id="7af91-132">**Wenn Sie einen OMS-Agenten auf einer vorhandenen Cloud Connector Appliance installieren**, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7af91-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>
    
1. <span data-ttu-id="7af91-133">Legen Sie in der Datei CloudConnector.ini [allgemeine] Abschnitt OMSEnabled = True.</span><span class="sxs-lookup"><span data-stu-id="7af91-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 
    
2. <span data-ttu-id="7af91-134">Import-CcConfiguration ausführen.</span><span class="sxs-lookup"><span data-stu-id="7af91-134">Run Import-CcConfiguration.</span></span> 
    
3. <span data-ttu-id="7af91-135">Führen Sie Install-CcOMSAgent aus.</span><span class="sxs-lookup"><span data-stu-id="7af91-135">Run Install-CcOMSAgent.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7af91-136">Wenn die Anmeldeinformationen des OMSWorkspace nicht festgelegt wurde, werden Sie für die Anmeldeinformationen aufgefordert, wenn Sie Install-CcOMSAgent ausführen.</span><span class="sxs-lookup"><span data-stu-id="7af91-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 
  
- <span data-ttu-id="7af91-137">**Wenn Sie die OMS Workspace-ID oder der Schlüssel in einer Cloud-Connector Appliance aktualisieren möchten installiert, die bereits einen OMS-Agent:**</span><span class="sxs-lookup"><span data-stu-id="7af91-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>
    
1. <span data-ttu-id="7af91-138">Um die OMS-ID und Schlüssel zu konfigurieren, führen Sie Set-CcCredential - AccountType OMSWorkspace aus.</span><span class="sxs-lookup"><span data-stu-id="7af91-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
2. <span data-ttu-id="7af91-139">Führen Sie zum Anwenden von Updates installieren CcOMSAgent aus.</span><span class="sxs-lookup"><span data-stu-id="7af91-139">To apply the updates, run Install-CcOMSAgent.</span></span> 
    
- <span data-ttu-id="7af91-140">**Stellen Sie sicher, dass die Agents wie folgt verbunden sind, in allen Szenarien:**</span><span class="sxs-lookup"><span data-stu-id="7af91-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>
    
    <span data-ttu-id="7af91-141">Wechseln Sie in das Portal OMS zu Einstellungen -\> verbundene Datenquellen -\> Windows-Servern.</span><span class="sxs-lookup"><span data-stu-id="7af91-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="7af91-142">Sehen Sie eine Liste der verbundenen Computer ein.</span><span class="sxs-lookup"><span data-stu-id="7af91-142">You will see a list of connected machines.</span></span> 
    
## <a name="configure-oms"></a><span data-ttu-id="7af91-143">Konfigurieren von OMS</span><span class="sxs-lookup"><span data-stu-id="7af91-143">Configure OMS</span></span>

<span data-ttu-id="7af91-144">Im nächsten Schritt müssen Sie die OMS-Konfiguration mithilfe des OMS-Portals angeben.</span><span class="sxs-lookup"><span data-stu-id="7af91-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="7af91-145">Insbesondere müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="7af91-145">Specifically, you will need to:</span></span>
  
- <span data-ttu-id="7af91-146">Geben Sie Informationen zur Ereignisprotokolle und Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="7af91-146">Specify information about event logs and performance counters.</span></span>
    
- <span data-ttu-id="7af91-147">Erstellen Sie Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="7af91-147">Create alerts.</span></span> 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="7af91-148">Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="7af91-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="7af91-149">Im Portal OMS müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="7af91-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>
  
1. <span data-ttu-id="7af91-150">Wechseln Sie zu Einstellungen -\>Daten -\>Windows-Ereignisprotokolle, und fügen Sie die Ereignisprotokolle auf:</span><span class="sxs-lookup"><span data-stu-id="7af91-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 
    
  - <span data-ttu-id="7af91-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="7af91-151">Lync Server</span></span>
    
  - <span data-ttu-id="7af91-152">Anwendung</span><span class="sxs-lookup"><span data-stu-id="7af91-152">Application</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7af91-153">Sie müssen die Lync Server manuell in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="7af91-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="7af91-154">Es wird nicht als Option in der Dropdown-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7af91-154">It does not appear as an option in the drop-down list.</span></span> 
  
    <span data-ttu-id="7af91-155">Weitere Informationen finden Sie unter [Windows-Ereignisprotokoll-Datenquellen im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="7af91-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>
    
2. <span data-ttu-id="7af91-156">Wechseln Sie zu Einstellungen -\>Daten -\> Windows-Leistungsindikatoren und Leistungsindikatoren für hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7af91-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 
    
  - <span data-ttu-id="7af91-157">**OS level-Leistungsindikatoren**.</span><span class="sxs-lookup"><span data-stu-id="7af91-157">**OS level counters**.</span></span> <span data-ttu-id="7af91-158">Können Sie OS Ebene Leistungsindikatoren wie Prozessorverwendung, die Speicherverwendung, Netzwerkauslastung, hinzufügen oder vorhandene Lösungen wie Kapazität und Leistung, Leistung Netzwerkmonitor ohne explizit Leistungsindikatoren hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="7af91-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="7af91-159">Unabhängig davon, wie Sie sie überwachen möchten empfiehlt es sich, dass Sie die OS Leistungsindikatoren überwachen.</span><span class="sxs-lookup"><span data-stu-id="7af91-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>
    
  - <span data-ttu-id="7af91-160">**Skype für Business Leistungsindikatoren**.</span><span class="sxs-lookup"><span data-stu-id="7af91-160">**Skype for Business counters**.</span></span> <span data-ttu-id="7af91-161">Es gibt zahlreiche von Skype für Unternehmen bereitgestellten Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="7af91-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="7af91-162">Anmeldung an einem beliebigen Vermittlungsserver und dem Systemmonitor öffnen, um diese Indikatoren finden.</span><span class="sxs-lookup"><span data-stu-id="7af91-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="7af91-163">Mit diesen Zählern beginnen mit "LS:".</span><span class="sxs-lookup"><span data-stu-id="7af91-163">These counters start with "LS:".</span></span> <span data-ttu-id="7af91-164">Microsoft empfiehlt, dass Sie mit den folgenden Leistungsindikatoren Kapazität mindestens starten, und fügen andere Personen, die von Interesse sind:</span><span class="sxs-lookup"><span data-stu-id="7af91-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>
    
    <span data-ttu-id="7af91-165">Aktive Anrufe gesamt:</span><span class="sxs-lookup"><span data-stu-id="7af91-165">Total active calls:</span></span>
    
  - <span data-ttu-id="7af91-166">LS:MediationServer - eingehende Calls(_Total)\- aktuellen</span><span class="sxs-lookup"><span data-stu-id="7af91-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
  - <span data-ttu-id="7af91-167">LS:MediationServer - ausgehende Calls(_Total)\- aktuellen</span><span class="sxs-lookup"><span data-stu-id="7af91-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
    <span data-ttu-id="7af91-168">Total medienumgehung aktiven Anrufe:</span><span class="sxs-lookup"><span data-stu-id="7af91-168">Total active media bypass calls:</span></span>
    
  - <span data-ttu-id="7af91-169">LS:MediationServer - eingehende Calls(_Total)\- Active medienumgehung Anrufe</span><span class="sxs-lookup"><span data-stu-id="7af91-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 
    
  - <span data-ttu-id="7af91-170">LS:MediationServer - ausgehende Calls(_Total)\- Active medienumgehung Anrufe</span><span class="sxs-lookup"><span data-stu-id="7af91-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7af91-171">Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="7af91-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="7af91-172">Sie werden nicht als Optionen in der Dropdown-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7af91-172">They do not appear as options in the drop-down list.</span></span> 
  
    <span data-ttu-id="7af91-173">Weitere Informationen finden Sie unter [Windows und Linux Leistung Datenquellen im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="7af91-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>
    
### <a name="create-alerts"></a><span data-ttu-id="7af91-174">Benachrichtigungen erstellen</span><span class="sxs-lookup"><span data-stu-id="7af91-174">Create alerts</span></span>

<span data-ttu-id="7af91-175">Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebnisse Benachrichtigungen und Benachrichtigungen für metrischen Maßeinheiten.</span><span class="sxs-lookup"><span data-stu-id="7af91-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="7af91-176">Weitere Informationen zum Erstellen von Warnungen finden Sie unter [Arbeiten mit Warnung Regeln in Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="7af91-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>
  
<span data-ttu-id="7af91-177">Beim Erstellen von Warnungen, sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="7af91-177">You should consider the following when creating alerts:</span></span>
  
- <span data-ttu-id="7af91-178">Stellen Sie sicher, dass die Benachrichtigung eine Benachrichtigung für die Anzahl der Ergebnisse ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="7af91-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 
    
- <span data-ttu-id="7af91-179">Die Demo Abfragen erfordern, dass "Anzahl der Ergebnisse" zu "größer als 0" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7af91-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 
    
- <span data-ttu-id="7af91-180">Es wird empfohlen, dass Sie Zeitfenster und benachrichtigungshäufigkeit auf 5 Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7af91-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 
    
- <span data-ttu-id="7af91-181">Es wird empfohlen, dass Sie nicht "Unterdrücken Benachrichtigungen" Demo Warnungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7af91-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 
    
- <span data-ttu-id="7af91-182">Warnung Standardszenarien Microsoft empfiehlt ein Paar von Benachrichtigungen erstellen: eine Fehlermeldung und Zurücksetzen einer Warnung.</span><span class="sxs-lookup"><span data-stu-id="7af91-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="7af91-183">Wählen Sie die fehlerbenachrichtigung für Schweregrad Kritisch. Wählen Sie für die Warnung zurücksetzen Schweregrad Information aus.</span><span class="sxs-lookup"><span data-stu-id="7af91-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>
    
<span data-ttu-id="7af91-184">In den folgenden Abschnitten wird beschrieben, wie zum Beispiel für Warnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7af91-184">The following sections describe how to create sample alerts.</span></span>
  
 <span data-ttu-id="7af91-185">**Erstellen einer Warnung Paar: "RTCMEDSRV wird nicht ausgeführt, in der Vermittlungsserver" und "RTCMEDSRV wieder Ausführung in hat Vermittlungsserver"**</span><span class="sxs-lookup"><span data-stu-id="7af91-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>
  
<span data-ttu-id="7af91-186">Diese Warnung Paar zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7af91-186">To create this alert pair:</span></span>
  
- <span data-ttu-id="7af91-187">Die Abfrage für die Fehlermeldung ist:</span><span class="sxs-lookup"><span data-stu-id="7af91-187">The query for the error alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="7af91-188">Die Abfrage verwendet die Computer Filter *, auf dem Computer "MediationServer" enthält* .</span><span class="sxs-lookup"><span data-stu-id="7af91-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="7af91-189">Der Filter wählt nur auf den Computer, dessen Name die Zeichenfolge "MediationServer" enthält.</span><span class="sxs-lookup"><span data-stu-id="7af91-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>
    
     <span data-ttu-id="7af91-190">Sie ersetzen Sie den Filter durch Ihren eigenen Computer Filter oder einfach zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7af91-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="7af91-191">Sie können komplexe Zeichenfolge Filter ohne reguläre Ausdrücke zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7af91-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="7af91-192">Weitere Informationen finden Sie unter [Operatoren](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="7af91-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="7af91-193">Sie können auch auswählen, reguläre Ausdrücke verwendet.</span><span class="sxs-lookup"><span data-stu-id="7af91-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="7af91-194">Darüber hinaus können Sie eine Computergruppe erstellen, indem eine Suchabfrage zu speichern und diese Gruppe als Ihren Computer Filter in der Warnung Abfrage.</span><span class="sxs-lookup"><span data-stu-id="7af91-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="7af91-195">Weitere Informationen finden Sie unter [Computergruppen im Protokoll Analytics melden Suchvorgänge](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="7af91-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>
    
    <span data-ttu-id="7af91-196">Für jeden Computer die Abfrage Fehler Ruft das letzte Ereignisprotokoll für den RTCMEDSRV Service Anfang und Stop-service.</span><span class="sxs-lookup"><span data-stu-id="7af91-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="7af91-197">Wird zurückgegeben, die eine melden, wenn das letzte Ereignis Service Stop-Ereignis; nothing wird zurückgegeben, wenn das letzte Ereignis Service Start-Ereignis ist.</span><span class="sxs-lookup"><span data-stu-id="7af91-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="7af91-198">Kurz gesagt, würde die Abfrage eine Liste der Server zurück, deren RTCMEDSRV im Zeitfenster beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7af91-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 
    
- <span data-ttu-id="7af91-199">Die Abfrage für die Benachrichtigung zurücksetzen ist:</span><span class="sxs-lookup"><span data-stu-id="7af91-199">The query for the reset alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="7af91-200">Die Reset-Abfrage ist genau das gegenteilige, was der Abfrage Fehler.</span><span class="sxs-lookup"><span data-stu-id="7af91-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="7af91-201">Für jeden Computer wird es eine zurück, wenn das letzte Ereignis ist Ereignis den Dienst zu starten. nothing wird zurückgegeben, wenn das letzte Ereignis Service Stop-Ereignis ist.</span><span class="sxs-lookup"><span data-stu-id="7af91-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>
    
 <span data-ttu-id="7af91-202">**Erstellen einer Warnung Paar: "zu viele gleichzeitige Anrufe in Vermittlungsserver" und "gleichzeitiger Anrufe auf zurückgegriffen normaler Auslastung"**</span><span class="sxs-lookup"><span data-stu-id="7af91-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>
  
<span data-ttu-id="7af91-203">So erstellen Sie diese Warnung:</span><span class="sxs-lookup"><span data-stu-id="7af91-203">To create this alert:</span></span>
  
- <span data-ttu-id="7af91-204">Die Abfrage für die Fehlermeldung ist:</span><span class="sxs-lookup"><span data-stu-id="7af91-204">The query for the error alert is:</span></span>
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="7af91-205">Für jeden Computer erhalten die Abfrage den letzten Leistungsindikatoren für eingehende Anrufe und ausgehende Anrufe und Summe diese beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="7af91-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="7af91-206">Wird zurückgegeben, die eine melden, wenn der Summenwert 500; überschreitet nothing wird zurückgegeben, wenn dies nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="7af91-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="7af91-207">Kurz gesagt, würde die Abfrage eine Liste der Server zurück, deren gleichzeitige Anrufe zu viele im Zeitfenster sind.</span><span class="sxs-lookup"><span data-stu-id="7af91-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>
    
- <span data-ttu-id="7af91-208">Die Abfrage für die Benachrichtigung zurücksetzen ist:</span><span class="sxs-lookup"><span data-stu-id="7af91-208">The query for the reset alert is:</span></span>
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    <span data-ttu-id="7af91-209">Die Reset-Abfrage ist genau das gegenteilige, was der Abfrage Fehler.</span><span class="sxs-lookup"><span data-stu-id="7af91-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="7af91-210">Für jeden Computer erhalten die Abfrage den letzten Leistungsindikatoren für eingehende Anrufe und ausgehende Anrufe und Summe diese beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="7af91-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="7af91-211">Es wird ein Protokoll, wenn der Summenwert ist kleiner als 500 zurückgeben. Es gibt nichts anders zurück.</span><span class="sxs-lookup"><span data-stu-id="7af91-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>
    
 <span data-ttu-id="7af91-212">**Erstellen einer Warnung: "CPU-Auslastung \> 90 oder RTCMEDIARELAY im Server beendet" Benachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="7af91-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>
  
<span data-ttu-id="7af91-213">Um diese Warnung zu erstellen, ist die Abfrage:</span><span class="sxs-lookup"><span data-stu-id="7af91-213">To create this alert, the query is:</span></span>
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="7af91-214">Die Abfrage erhalten alle Prozessor Usage Leistungsindikator und Service Stop-Ereignis von allen Computern und zurückgeben, die jemals ein Protokoll überschreitet entweder Prozessorverwendung 90 % oder Dienst beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7af91-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="7af91-215">Analysieren der Benachrichtigungen in das Protokoll Analytics repository</span><span class="sxs-lookup"><span data-stu-id="7af91-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="7af91-216">Verwenden Sie zum Analysieren von Benachrichtigungen in Ihrem Repository der Alert-Management-Lösung.</span><span class="sxs-lookup"><span data-stu-id="7af91-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="7af91-217">Weitere Informationen finden Sie unter [Alert-Management-Lösung in Betrieb Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="7af91-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>
  
## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="7af91-218">Empfohlene monitoring Mindestsatz</span><span class="sxs-lookup"><span data-stu-id="7af91-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="7af91-219">Um Probleme mit Ereignisprotokollen und Leistungsindikatoren zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="7af91-219">To identify issues with event logs and performance counters:</span></span> 
  
- <span data-ttu-id="7af91-220">**Ereignisprotokolle.**</span><span class="sxs-lookup"><span data-stu-id="7af91-220">**Event logs.**</span></span> <span data-ttu-id="7af91-221">Für jedes Problem sollte ein paar Ereignisse mit einem Satz von Ereignissen, um anzugeben, dass etwas falsch ist, während die andere gibt an, dass alles ist.</span><span class="sxs-lookup"><span data-stu-id="7af91-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="7af91-222">Für jeden angegebenen Zeitraum, es ist das letzte Ereignis aufgezeichnet, mit denen angegeben wird, ob der für diesen Zeitraum ist.</span><span class="sxs-lookup"><span data-stu-id="7af91-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>
    
- <span data-ttu-id="7af91-223">**Leistungsindikatoren.**</span><span class="sxs-lookup"><span data-stu-id="7af91-223">**Performance Counters.**</span></span> <span data-ttu-id="7af91-224">Es sollte ein Schwellenwert für die überwachten Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="7af91-224">There should be a threshold for the monitored counters.</span></span>
    
<span data-ttu-id="7af91-225">Die folgende Tabelle enthält die Dienste, dass Microsoft empfiehlt die Überwachung durch die Stopp und Start-Ereignis-IDs aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="7af91-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7af91-226">Dienstname</span><span class="sxs-lookup"><span data-stu-id="7af91-226">Service Name</span></span>  <br/> |<span data-ttu-id="7af91-227">Ziel-Serverrolle</span><span class="sxs-lookup"><span data-stu-id="7af91-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="7af91-228">Ereignis-ID beenden</span><span class="sxs-lookup"><span data-stu-id="7af91-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="7af91-229">Start-Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7af91-229">Start Event ID</span></span>  <br/> |
|<span data-ttu-id="7af91-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="7af91-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="7af91-231">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="7af91-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="7af91-232">25003</span><span class="sxs-lookup"><span data-stu-id="7af91-232">25003</span></span>  <br/> |<span data-ttu-id="7af91-233">25002</span><span class="sxs-lookup"><span data-stu-id="7af91-233">25002</span></span>  <br/> |
|<span data-ttu-id="7af91-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="7af91-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="7af91-235">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="7af91-235">Edge Server</span></span>  <br/> |<span data-ttu-id="7af91-236">12289</span><span class="sxs-lookup"><span data-stu-id="7af91-236">12289</span></span>  <br/> |<span data-ttu-id="7af91-237">12288</span><span class="sxs-lookup"><span data-stu-id="7af91-237">12288</span></span>  <br/> |
|<span data-ttu-id="7af91-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="7af91-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="7af91-239">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="7af91-239">Edge Server</span></span>  <br/> |<span data-ttu-id="7af91-240">19003</span><span class="sxs-lookup"><span data-stu-id="7af91-240">19003</span></span>  <br/> |<span data-ttu-id="7af91-241">19002</span><span class="sxs-lookup"><span data-stu-id="7af91-241">19002</span></span>  <br/> |
|<span data-ttu-id="7af91-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="7af91-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="7af91-243">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="7af91-243">Edge Server</span></span>  <br/> |<span data-ttu-id="7af91-244">22003</span><span class="sxs-lookup"><span data-stu-id="7af91-244">22003</span></span>  <br/> |<span data-ttu-id="7af91-245">22002</span><span class="sxs-lookup"><span data-stu-id="7af91-245">22002</span></span>  <br/> |
   
<span data-ttu-id="7af91-246">Die folgende Tabelle enthält die Netzwerkprobleme, die Microsoft überwachen empfiehlt:</span><span class="sxs-lookup"><span data-stu-id="7af91-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7af91-247">Name des Monitors</span><span class="sxs-lookup"><span data-stu-id="7af91-247">Monitor Name</span></span>  <br/> |<span data-ttu-id="7af91-248">Ziel-Serverrolle</span><span class="sxs-lookup"><span data-stu-id="7af91-248">Target Server Role</span></span>  <br/> |<span data-ttu-id="7af91-249">Ereignis-ID-Ausdruck Erfolg</span><span class="sxs-lookup"><span data-stu-id="7af91-249">Success Event ID expression</span></span>  <br/> |<span data-ttu-id="7af91-250">Ausdruck, der Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7af91-250">Error Event ID expression</span></span>  <br/> |<span data-ttu-id="7af91-251">Fehler bei diesem Beispiel wird</span><span class="sxs-lookup"><span data-stu-id="7af91-251">Failure example</span></span>  <br/> |
|<span data-ttu-id="7af91-252">Vermittlungsserver zu Verbindungsproblemen gateway</span><span class="sxs-lookup"><span data-stu-id="7af91-252">Mediation Server to gateway connectivity failure</span></span>  <br/> |<span data-ttu-id="7af91-253">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="7af91-253">Mediation Server</span></span>  <br/> |<span data-ttu-id="7af91-254">25062</span><span class="sxs-lookup"><span data-stu-id="7af91-254">25062</span></span> || <span data-ttu-id="7af91-255">25002</span><span class="sxs-lookup"><span data-stu-id="7af91-255">25002</span></span>  <br/> |<span data-ttu-id="7af91-256">25061</span><span class="sxs-lookup"><span data-stu-id="7af91-256">25061</span></span>  <br/> |<span data-ttu-id="7af91-257">Fehler bei MS PING (Option) Gateway</span><span class="sxs-lookup"><span data-stu-id="7af91-257">MS PING (option) Gateway failed</span></span>  <br/> |
|<span data-ttu-id="7af91-258">Vermittlungsserver an Gateway rufen Sie nach Abschluss Fehler</span><span class="sxs-lookup"><span data-stu-id="7af91-258">Mediation Server to gateway call completion failure</span></span>  <br/> |<span data-ttu-id="7af91-259">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="7af91-259">Mediation Server</span></span>  <br/> |<span data-ttu-id="7af91-260">25064</span><span class="sxs-lookup"><span data-stu-id="7af91-260">25064</span></span> || <span data-ttu-id="7af91-261">25002</span><span class="sxs-lookup"><span data-stu-id="7af91-261">25002</span></span>  <br/> |<span data-ttu-id="7af91-262">25063</span><span class="sxs-lookup"><span data-stu-id="7af91-262">25063</span></span>  <br/> |<span data-ttu-id="7af91-263">MS möchten, müssen Sie Gateway aufrufen, ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="7af91-263">MS trying to make call to Gateway failed</span></span>  <br/> |
|<span data-ttu-id="7af91-264">Kritische Netzwerkprobleme</span><span class="sxs-lookup"><span data-stu-id="7af91-264">Critical network problems</span></span>  <br/> |<span data-ttu-id="7af91-265">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="7af91-265">Edge Server</span></span>  <br/> |<span data-ttu-id="7af91-266">14353</span><span class="sxs-lookup"><span data-stu-id="7af91-266">14353</span></span> || <span data-ttu-id="7af91-267">12288</span><span class="sxs-lookup"><span data-stu-id="7af91-267">12288</span></span>  <br/> |<span data-ttu-id="7af91-268">14624</span><span class="sxs-lookup"><span data-stu-id="7af91-268">14624</span></span>  <br/> |<span data-ttu-id="7af91-269">Transport TLS konnte nicht gestartet werden auf lokale IP-Adresse 192.168.231.14 an Port 5061</span><span class="sxs-lookup"><span data-stu-id="7af91-269">Transport TLS has failed to start on local IP address 192.168.231.14 at port 5061</span></span>  <br/> |
   
<span data-ttu-id="7af91-270">Im folgenden werden die Anruf-Kapazität Leistungsindikatoren, die überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7af91-270">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="7af91-271">Sollten weniger, die Veröffentlichung dieser Nummern werden 500 für die Cloud Connector standard Edition; weniger als 50 für Cloud Connector minimale Edition.</span><span class="sxs-lookup"><span data-stu-id="7af91-271">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>
  
- <span data-ttu-id="7af91-272">LS:MediationServer - eingehende Calls(_Total)\- aktuellen</span><span class="sxs-lookup"><span data-stu-id="7af91-272">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="7af91-273">LS:MediationServer - ausgehende Calls(_Total)\- aktuellen</span><span class="sxs-lookup"><span data-stu-id="7af91-273">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="7af91-274">LS:MediationServer - eingehende Calls(_Total)\- Active medienumgehung Anrufe</span><span class="sxs-lookup"><span data-stu-id="7af91-274">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>
    
- <span data-ttu-id="7af91-275">LS:MediationServer - ausgehende Calls(_Total)\- Active medienumgehung Anrufe</span><span class="sxs-lookup"><span data-stu-id="7af91-275">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7af91-276">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7af91-276">See also</span></span>

<span data-ttu-id="7af91-277">Weitere Informationen zum Arbeiten mit OMS finden Sie unter den folgenden:</span><span class="sxs-lookup"><span data-stu-id="7af91-277">For more information about working with OMS, see the following:</span></span>
  
- [<span data-ttu-id="7af91-278">Suchen nach Daten anhand Protokolldateien Suchvorgänge in Protokoll Analytics</span><span class="sxs-lookup"><span data-stu-id="7af91-278">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [<span data-ttu-id="7af91-279">Azure Protokoll Analytics-Sprachreferenz (engl.)</span><span class="sxs-lookup"><span data-stu-id="7af91-279">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)
    
- [<span data-ttu-id="7af91-280">Grundlegendes zu Warnungen im Protokoll Analytics</span><span class="sxs-lookup"><span data-stu-id="7af91-280">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [<span data-ttu-id="7af91-281">Verbinden von Computern mit Windows mit dem Protokoll Analytics-Dienst in Azure</span><span class="sxs-lookup"><span data-stu-id="7af91-281">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    


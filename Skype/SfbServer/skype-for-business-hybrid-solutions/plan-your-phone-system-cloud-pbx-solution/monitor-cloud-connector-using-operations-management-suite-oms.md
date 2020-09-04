---
title: Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS).
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector-Version 2,1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359091"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="6d7be-103">Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="6d7be-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="6d7be-104">Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="6d7be-105">Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="6d7be-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="6d7be-106">Lesen Sie dieses Thema, um zu erfahren, wie Sie Ihre Cloud Connector-Version 2,1 und höher mithilfe von Microsoft Operations Management Suite (OMS) überwachen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="6d7be-107">Sie können jetzt Ihre Cloud Connector-Version 2,1 und höher mithilfe von Operations Management Suite (OMS), einer Microsoft Cloud-IT-Verwaltungslösung, überwachen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="6d7be-108">Mit der OMS-Protokollanalyse können Sie die Verfügbarkeit und Leistung von Ressourcen, einschließlich physischer und virtueller Computer, überwachen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="6d7be-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="6d7be-109">Weitere Informationen zu OMS und zur Protokollanalyse finden Sie unter [Was ist Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="6d7be-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="6d7be-110">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="6d7be-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="6d7be-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6d7be-111">Prerequisites</span></span>

- <span data-ttu-id="6d7be-112">Konfigurieren von Cloud Connector für die Verwendung von OMS</span><span class="sxs-lookup"><span data-stu-id="6d7be-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="6d7be-113">Konfigurieren von OMS</span><span class="sxs-lookup"><span data-stu-id="6d7be-113">Configure OMS</span></span>

- <span data-ttu-id="6d7be-114">Analysieren der Warnungen in Ihrem Protokollanalyse-Repository</span><span class="sxs-lookup"><span data-stu-id="6d7be-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="6d7be-115">Empfohlene Überwachungsgruppe</span><span class="sxs-lookup"><span data-stu-id="6d7be-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d7be-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6d7be-116">Prerequisites</span></span>

<span data-ttu-id="6d7be-117">Bevor Sie OMS zum Überwachen Ihrer Cloud Connector-Bereitstellung verwenden können, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6d7be-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="6d7be-118">**Ein Azure-Konto und ein OMS-Arbeitsbereich.**</span><span class="sxs-lookup"><span data-stu-id="6d7be-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="6d7be-119">Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie eine erstellen, um die OMS-Protokollanalyse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d7be-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="6d7be-120">Informationen zum Erstellen eines Azure-Kontos und zum Einrichten eines OMS-Arbeitsbereichs finden Sie unter [Erste Schritte mit einem Log Analytics-Arbeitsbereich](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="6d7be-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="6d7be-121">**Cloud Connector Version 2,1 oder höher**</span><span class="sxs-lookup"><span data-stu-id="6d7be-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="6d7be-122">**Log Analytics die neue Protokollsuche** ist für die Cloud Connector-Überwachung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6d7be-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="6d7be-123">Weitere Informationen finden Sie unter [Aktualisieren des Azure Log Analytics-Arbeitsbereichs auf die neue Protokollsuche](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="6d7be-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="6d7be-124">Konfigurieren von Cloud Connector für die Verwendung von OMS</span><span class="sxs-lookup"><span data-stu-id="6d7be-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="6d7be-125">Sie müssen Ihre lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6d7be-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="6d7be-126">Dazu benötigen Sie die OMS-Arbeitsbereichs-ID und den Schlüssel, die Sie über das OMS-Portal wie folgt finden: Settings-- \> Connected sources-- \> Windows Servers:</span><span class="sxs-lookup"><span data-stu-id="6d7be-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="6d7be-128">Wie Sie Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:</span><span class="sxs-lookup"><span data-stu-id="6d7be-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="6d7be-129">**Wenn Sie eine neue Cloud Connector-Appliance installieren oder eine Appliance erneut bereitstellen möchten**, führen Sie die folgenden Schritte aus, bevor Sie Install-ccappliance "ausführen:</span><span class="sxs-lookup"><span data-stu-id="6d7be-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="6d7be-130">Legen Sie im Abschnitt CloudConnector.ini Datei [common] den Parameter OMSEnabled auf true fest.</span><span class="sxs-lookup"><span data-stu-id="6d7be-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="6d7be-131">Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, wird versucht, den OMS-Agent automatisch auf den VMS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="6d7be-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="6d7be-132">Aktivieren Sie dieses Feature, damit der OMS-Agent das automatische Update für Cloud Connector überleben kann.</span><span class="sxs-lookup"><span data-stu-id="6d7be-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="6d7be-133">Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie die Einstellung-CcCredential-AccountType OMSWorkspace aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="6d7be-134">**Wenn Sie einen OMS-Agent in einer vorhandenen Cloud Connector-Appliance installieren**, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6d7be-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="6d7be-135">Legen Sie im Abschnitt CloudConnector.ini Datei [common] OMSEnabled = true fest.</span><span class="sxs-lookup"><span data-stu-id="6d7be-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="6d7be-136">Führen Sie Import-CcConfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="6d7be-137">Führen Sie Install-CcOMSAgent aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="6d7be-138">Wenn die OMSWorkspace-Anmeldeinformationen noch nie festgelegt wurden, werden Sie zur Eingabe der Anmeldeinformationen aufgefordert, wenn Sie Install-CcOMSAgent ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="6d7be-139">**Wenn Sie die OMS-Arbeitsbereichs-ID oder den Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**</span><span class="sxs-lookup"><span data-stu-id="6d7be-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="6d7be-140">Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie die Einstellung-CcCredential-AccountType OMSWorkspace aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="6d7be-141">Um die Updates zu übernehmen, führen Sie Install-CcOMSAgent aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="6d7be-142">**Stellen Sie für alle Szenarien sicher, dass die Agents wie folgt verbunden sind:**</span><span class="sxs-lookup"><span data-stu-id="6d7be-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="6d7be-143">Wechseln Sie im OMS-Portal zu Einstellungen – \> verbundene Quellen – \> Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="6d7be-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="6d7be-144">Es wird eine Liste der verbundenen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d7be-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="6d7be-145">Konfigurieren von OMS</span><span class="sxs-lookup"><span data-stu-id="6d7be-145">Configure OMS</span></span>

<span data-ttu-id="6d7be-146">Als nächstes müssen Sie die OMS-Konfiguration mithilfe des OMS-Portals angeben.</span><span class="sxs-lookup"><span data-stu-id="6d7be-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="6d7be-147">Konkret gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6d7be-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="6d7be-148">Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.</span><span class="sxs-lookup"><span data-stu-id="6d7be-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="6d7be-149">Benachrichtigungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="6d7be-150">Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="6d7be-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="6d7be-151">Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="6d7be-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="6d7be-152">Wechseln Sie zu Einstellungen- \> Daten- \> Windows-Ereignisprotokolle, und fügen Sie Ereignisprotokolle für hinzu:</span><span class="sxs-lookup"><span data-stu-id="6d7be-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="6d7be-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="6d7be-153">Lync Server</span></span>

   - <span data-ttu-id="6d7be-154">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d7be-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="6d7be-155">Sie müssen lync Server manuell in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="6d7be-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="6d7be-156">Es wird nicht als Option in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d7be-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="6d7be-157">Weitere Informationen finden Sie unter [Windows-Ereignisprotokoll-Datenquellen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="6d7be-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="6d7be-158">Wechseln Sie zu Einstellungen- \> Daten- \> Windows-Leistungsindikatoren, und fügen Sie Leistungsindikatoren für hinzu:</span><span class="sxs-lookup"><span data-stu-id="6d7be-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="6d7be-159">**Leistungsindikatoren auf Betriebssystemebene**.</span><span class="sxs-lookup"><span data-stu-id="6d7be-159">**OS level counters**.</span></span> <span data-ttu-id="6d7be-160">Sie können Leistungsindikatoren auf Betriebssystemebene hinzufügen, beispielsweise Prozessorauslastung, Speicherauslastung, Netzwerkauslastung oder vorhandene Lösungen wie Kapazität und Leistung, Netzwerk Leistungsüberwachung ohne explizites Hinzufügen von Leistungsindikatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d7be-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="6d7be-161">Unabhängig davon, wie Sie diese überwachen möchten, empfiehlt Microsoft, diese Betriebssystem-Leistungsindikatoren zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="6d7be-162">**Skype for Business Zähler**.</span><span class="sxs-lookup"><span data-stu-id="6d7be-162">**Skype for Business counters**.</span></span> <span data-ttu-id="6d7be-163">Es gibt zahlreiche Leistungsindikatoren, die von Skype for Business bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6d7be-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="6d7be-164">Sie finden diese Leistungsindikatoren, indem Sie sich bei jeder Vermittlungsserver anmelden und den System Monitor öffnen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="6d7be-165">Diese Indikatoren beginnen mit "ls:".</span><span class="sxs-lookup"><span data-stu-id="6d7be-165">These counters start with "LS:".</span></span> <span data-ttu-id="6d7be-166">Microsoft empfiehlt, dass Sie mindestens mit den folgenden Kapazitäts Indikatoren beginnen und weitere interessante hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="6d7be-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="6d7be-167">Aktive Aufrufe insgesamt:</span><span class="sxs-lookup"><span data-stu-id="6d7be-167">Total active calls:</span></span>

       - <span data-ttu-id="6d7be-168">LS: MediationServer-eingehende Anrufe (_Total) \- aktuell</span><span class="sxs-lookup"><span data-stu-id="6d7be-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="6d7be-169">LS: MediationServer-ausgehende Anrufe (_Total) \- aktuell</span><span class="sxs-lookup"><span data-stu-id="6d7be-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="6d7be-170">Gesamtzahl aktiver Medien Umgehungs Aufrufe:</span><span class="sxs-lookup"><span data-stu-id="6d7be-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="6d7be-171">LS: MediationServer-eingehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe</span><span class="sxs-lookup"><span data-stu-id="6d7be-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="6d7be-172">LS: MediationServer-ausgehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe</span><span class="sxs-lookup"><span data-stu-id="6d7be-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="6d7be-173">Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="6d7be-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="6d7be-174">Sie werden in der Dropdownliste nicht als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d7be-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="6d7be-175">Weitere Informationen finden Sie unter [Windows und Linux Performance Data Sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) .</span><span class="sxs-lookup"><span data-stu-id="6d7be-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="6d7be-176">Erstellen von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="6d7be-176">Create alerts</span></span>

<span data-ttu-id="6d7be-177">Es gibt zwei Arten von Warnungen in OMS: Anzahl der Ergebnis Warnungen und Metriken für die Messung von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="6d7be-178">Weitere Informationen zum Erstellen von Warnungen finden Sie unter [Working with Alert Rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="6d7be-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="6d7be-179">Beachten Sie beim Erstellen von Warnungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6d7be-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="6d7be-180">Stellen Sie sicher, dass es sich bei der Warnung um eine Anzahl von Ergebnis Warnungen handelt, bei der es sich um die Standardauswahl handelt.</span><span class="sxs-lookup"><span data-stu-id="6d7be-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="6d7be-181">Die Demo-Abfragen erfordern, dass "number of Results" auf "größer als 0" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6d7be-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="6d7be-182">Es wird empfohlen, dass Sie sowohl Zeitfenster als auch Warnungs Häufigkeit auf 5 Minuten festlegen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="6d7be-183">Es wird empfohlen, die Option "Warnungen unterdrücken" für Demo Warnungen nicht zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d7be-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="6d7be-184">Für typische Warnungs Szenarien empfiehlt Microsoft das Erstellen eines Warnungs Paars: eine Fehlermeldung und eine Warnung für einen Reset.</span><span class="sxs-lookup"><span data-stu-id="6d7be-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="6d7be-185">Wählen Sie für die Fehlermeldung Schweregrad kritisch aus. Wählen Sie für die Warnung zurücksetzen die Option Severity Level Information aus.</span><span class="sxs-lookup"><span data-stu-id="6d7be-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="6d7be-186">In den folgenden Abschnitten wird beschrieben, wie Sie Beispielwarnungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="6d7be-187">**Erstellen eines Warnungs Paars: "RTCMEDSRV wird nicht auf Vermittlungsservern" und "RTCMEDSRV wird wieder in den Vermittlungsservern" gestartet.**</span><span class="sxs-lookup"><span data-stu-id="6d7be-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="6d7be-188">So erstellen Sie dieses Warnungs paar:</span><span class="sxs-lookup"><span data-stu-id="6d7be-188">To create this alert pair:</span></span>

- <span data-ttu-id="6d7be-189">Die Abfrage für die Fehlermeldung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6d7be-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="6d7be-190">Die Abfrage verwendet den Computerfilter  *, auf dem Computer "MediationServer" enthält*  .</span><span class="sxs-lookup"><span data-stu-id="6d7be-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="6d7be-191">Der Filter wählt nur den Computer aus, dessen Name die Zeichenfolge "MediationServer" enthält.</span><span class="sxs-lookup"><span data-stu-id="6d7be-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="6d7be-192">Sie würden den Filter durch ihren eigenen Computerfilter ersetzen oder einfach entfernen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="6d7be-193">Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen.</span><span class="sxs-lookup"><span data-stu-id="6d7be-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="6d7be-194">Weitere Informationen finden Sie unter [String Operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="6d7be-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="6d7be-195">Sie können auch festlegen, dass reguläre Ausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d7be-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="6d7be-196">Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als Computerfilter in ihrer Warnungs Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d7be-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="6d7be-197">Weitere Informationen finden Sie unter [Computer Gruppen in Log Analytics-Suchprotokoll suchen](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="6d7be-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="6d7be-198">Für jeden Computer Ruft die Fehler Abfrage das letzte Ereignisprotokoll sowohl für den RTCMEDSRV-Dienststart als auch für den Dienst Stopp ab.</span><span class="sxs-lookup"><span data-stu-id="6d7be-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="6d7be-199">Wenn das letzte Ereignis das Dienstbeendigungsereignis ist, wird ein Protokoll zurückgegeben. Es gibt Nothing zurück, wenn das letzte Ereignis das Dienststart Ereignis ist.</span><span class="sxs-lookup"><span data-stu-id="6d7be-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="6d7be-200">Kurz gesagt, würde die Abfrage eine Liste von Servern zurückgeben, deren RTCMEDSRV im Zeitfenster angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="6d7be-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="6d7be-201">Die Abfrage für die Zurücksetzungs Warnung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6d7be-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="6d7be-202">Die Reset-Abfrage macht genau das Gegenteil der Fehler Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6d7be-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="6d7be-203">Für jeden Computer wird eine zurückgegeben, wenn das letzte Ereignis das Dienststart Ereignis ist; andernfalls false. Es gibt Nothing zurück, wenn das letzte Ereignis das Dienstbeendigungsereignis ist.</span><span class="sxs-lookup"><span data-stu-id="6d7be-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="6d7be-204">**Erstellen eines Warnungs Paars: "zu viele gleichzeitige Anrufe in Vermittlungsservern" und "gleichzeitige Anrufe fallen wieder auf normale Last"**</span><span class="sxs-lookup"><span data-stu-id="6d7be-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="6d7be-205">So erstellen Sie diese Warnung:</span><span class="sxs-lookup"><span data-stu-id="6d7be-205">To create this alert:</span></span>

- <span data-ttu-id="6d7be-206">Die Abfrage für die Fehlermeldung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6d7be-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="6d7be-207">Für jeden Computer Ruft die Abfrage die letzten Leistungsindikatoren für eingehende und ausgehende Anrufe ab und summiert diese beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="6d7be-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="6d7be-208">Wenn der Summenwert 500 überschreitet, wird ein Protokoll zurückgegeben. Wenn dies nicht der Fall ist, wird Nothing zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6d7be-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="6d7be-209">Kurz gesagt, würde die Abfrage eine Liste von Servern zurückgeben, deren gleichzeitige Anrufe zu viele im Zeitfenster sind.</span><span class="sxs-lookup"><span data-stu-id="6d7be-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="6d7be-210">Die Abfrage für die Zurücksetzungs Warnung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6d7be-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="6d7be-211">Die Reset-Abfrage macht genau das Gegenteil der Fehler Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6d7be-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="6d7be-212">Für jeden Computer Ruft die Abfrage die letzten Leistungsindikatoren für eingehende und ausgehende Anrufe ab und summiert diese beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="6d7be-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="6d7be-213">Wenn der Summenwert kleiner als 500 ist, wird ein Protokoll zurückgegeben. Andernfalls wird nichts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6d7be-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="6d7be-214">**Warnung erstellen: "CPU-Auslastung \> 90 oder RTCMEDIARELAY in Servern angehalten"-Warnung**</span><span class="sxs-lookup"><span data-stu-id="6d7be-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="6d7be-215">Zum Erstellen dieser Warnung lautet die Abfrage wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6d7be-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="6d7be-216">Die Abfrage ruft alle Prozessor Nutzungszähler-und Dienst Stoppereignisse von allen Computern ab und gibt ein Protokoll zurück, wenn die Prozessorauslastung 90% überschreitet oder der Dienst jemals angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="6d7be-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="6d7be-217">Analysieren der Warnungen in Ihrem Protokollanalyse-Repository</span><span class="sxs-lookup"><span data-stu-id="6d7be-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="6d7be-218">Verwenden Sie die Warnungs Verwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="6d7be-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="6d7be-219">Weitere Informationen finden Sie unter [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .</span><span class="sxs-lookup"><span data-stu-id="6d7be-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="6d7be-220">Empfohlener minimaler Überwachungs Satz</span><span class="sxs-lookup"><span data-stu-id="6d7be-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="6d7be-221">So identifizieren Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren:</span><span class="sxs-lookup"><span data-stu-id="6d7be-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="6d7be-222">**Ereignisprotokolle.**</span><span class="sxs-lookup"><span data-stu-id="6d7be-222">**Event logs.**</span></span> <span data-ttu-id="6d7be-223">Bei jedem Problem sollte ein Ereignispaar vorhanden sein, wobei eine Gruppe von Ereignissen darauf hinweist, dass etwas falsch ist, während die andere angibt, dass alles gut ist.</span><span class="sxs-lookup"><span data-stu-id="6d7be-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="6d7be-224">Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob für diesen Zeitraum ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6d7be-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="6d7be-225">**Leistungsindikatoren.**</span><span class="sxs-lookup"><span data-stu-id="6d7be-225">**Performance Counters.**</span></span> <span data-ttu-id="6d7be-226">Für die überwachten Leistungsindikatoren sollte ein Schwellenwert vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6d7be-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="6d7be-227">In der folgenden Tabelle sind die Dienste aufgeführt, die von Microsoft überwachen empfohlen werden, indem die Ereignis-IDs Stop und Start aufgelistet werden:</span><span class="sxs-lookup"><span data-stu-id="6d7be-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="6d7be-228">Dienst Name</span><span class="sxs-lookup"><span data-stu-id="6d7be-228">Service Name</span></span>  <br/> |<span data-ttu-id="6d7be-229">Ziel Server Rolle</span><span class="sxs-lookup"><span data-stu-id="6d7be-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="6d7be-230">Ereignis-ID beenden</span><span class="sxs-lookup"><span data-stu-id="6d7be-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="6d7be-231">Start Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6d7be-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6d7be-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="6d7be-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="6d7be-233">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="6d7be-234">25003</span><span class="sxs-lookup"><span data-stu-id="6d7be-234">25003</span></span>  <br/> |<span data-ttu-id="6d7be-235">25002</span><span class="sxs-lookup"><span data-stu-id="6d7be-235">25002</span></span>  <br/> |
|<span data-ttu-id="6d7be-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="6d7be-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="6d7be-237">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-237">Edge Server</span></span>  <br/> |<span data-ttu-id="6d7be-238">12289</span><span class="sxs-lookup"><span data-stu-id="6d7be-238">12289</span></span>  <br/> |<span data-ttu-id="6d7be-239">12288</span><span class="sxs-lookup"><span data-stu-id="6d7be-239">12288</span></span>  <br/> |
|<span data-ttu-id="6d7be-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="6d7be-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="6d7be-241">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-241">Edge Server</span></span>  <br/> |<span data-ttu-id="6d7be-242">19003</span><span class="sxs-lookup"><span data-stu-id="6d7be-242">19003</span></span>  <br/> |<span data-ttu-id="6d7be-243">19002</span><span class="sxs-lookup"><span data-stu-id="6d7be-243">19002</span></span>  <br/> |
|<span data-ttu-id="6d7be-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="6d7be-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="6d7be-245">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-245">Edge Server</span></span>  <br/> |<span data-ttu-id="6d7be-246">22003</span><span class="sxs-lookup"><span data-stu-id="6d7be-246">22003</span></span>  <br/> |<span data-ttu-id="6d7be-247">22002</span><span class="sxs-lookup"><span data-stu-id="6d7be-247">22002</span></span>  <br/> |

<span data-ttu-id="6d7be-248">In der folgenden Tabelle sind die Netzwerkprobleme aufgeführt, die von Microsoft überwachen empfohlen werden:</span><span class="sxs-lookup"><span data-stu-id="6d7be-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="6d7be-249">Monitor Name</span><span class="sxs-lookup"><span data-stu-id="6d7be-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="6d7be-250">Ziel Server Rolle</span><span class="sxs-lookup"><span data-stu-id="6d7be-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="6d7be-251">Erfolgsereignis-ID-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="6d7be-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="6d7be-252">Fehlerereignis-ID-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="6d7be-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="6d7be-253">Fehler Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d7be-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="6d7be-254">Vermittlungsserver auf Gateway-Verbindungsfehler</span><span class="sxs-lookup"><span data-stu-id="6d7be-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="6d7be-255">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="6d7be-256">25062</span><span class="sxs-lookup"><span data-stu-id="6d7be-256">25062</span></span>                              |                                  | <span data-ttu-id="6d7be-257">25002</span><span class="sxs-lookup"><span data-stu-id="6d7be-257">25002</span></span>  <br/>           |
| <span data-ttu-id="6d7be-258">Vermittlungsserver zu Gateway-Anruf Abschluss Fehler</span><span class="sxs-lookup"><span data-stu-id="6d7be-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="6d7be-259">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="6d7be-260">25064</span><span class="sxs-lookup"><span data-stu-id="6d7be-260">25064</span></span>                              |                                  | <span data-ttu-id="6d7be-261">25002</span><span class="sxs-lookup"><span data-stu-id="6d7be-261">25002</span></span>  <br/>           |
| <span data-ttu-id="6d7be-262">Wichtige Netzwerkprobleme</span><span class="sxs-lookup"><span data-stu-id="6d7be-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="6d7be-263">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6d7be-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="6d7be-264">14353</span><span class="sxs-lookup"><span data-stu-id="6d7be-264">14353</span></span>                              |                                  | <span data-ttu-id="6d7be-265">12288</span><span class="sxs-lookup"><span data-stu-id="6d7be-265">12288</span></span>  <br/>           |

<span data-ttu-id="6d7be-266">Im folgenden sind die Leistungsindikatoren für die Anrufkapazität aufgeführt, die überwacht werden sollten.</span><span class="sxs-lookup"><span data-stu-id="6d7be-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="6d7be-267">Diese Zahlen sollten niedriger sein als 500 für Cloud Connector Standard Edition; kleiner als 50 für Cloud Connector Minimum Edition.</span><span class="sxs-lookup"><span data-stu-id="6d7be-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="6d7be-268">LS: MediationServer-eingehende Anrufe (_Total) \- aktuell</span><span class="sxs-lookup"><span data-stu-id="6d7be-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="6d7be-269">LS: MediationServer-ausgehende Anrufe (_Total) \- aktuell</span><span class="sxs-lookup"><span data-stu-id="6d7be-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="6d7be-270">LS: MediationServer-eingehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe</span><span class="sxs-lookup"><span data-stu-id="6d7be-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="6d7be-271">LS: MediationServer-ausgehende Anrufe (_Total) \- aktive Medien Umgehungs Aufrufe</span><span class="sxs-lookup"><span data-stu-id="6d7be-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="6d7be-272">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="6d7be-272">See also</span></span>

<span data-ttu-id="6d7be-273">Weitere Informationen zum Arbeiten mit OMS finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6d7be-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="6d7be-274">Suchen von Daten mithilfe von Protokoll suchen in der Protokollanalyse</span><span class="sxs-lookup"><span data-stu-id="6d7be-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="6d7be-275">Azure Log Analytics – Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="6d7be-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="6d7be-276">Grundlegendes zu Warnungen in Protokollanalysen</span><span class="sxs-lookup"><span data-stu-id="6d7be-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="6d7be-277">Verbinden von Windows-Computern mit dem Log Analytics-Dienst in Azure</span><span class="sxs-lookup"><span data-stu-id="6d7be-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)



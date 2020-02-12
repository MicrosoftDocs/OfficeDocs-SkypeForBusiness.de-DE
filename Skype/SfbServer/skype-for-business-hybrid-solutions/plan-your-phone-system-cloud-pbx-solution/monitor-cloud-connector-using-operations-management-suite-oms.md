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
description: In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector-Version 2,1 und spätere Bereitstellung mithilfe von Microsoft Operations Management Suite (OMS) überwachen.
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888634"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="66567-103">Überwachen von Cloud Connector mithilfe der Operations Management Suite (OMS).</span><span class="sxs-lookup"><span data-stu-id="66567-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="66567-104">In diesem Thema erfahren Sie, wie Sie Ihre Cloud Connector-Version 2,1 und spätere Bereitstellung mithilfe von Microsoft Operations Management Suite (OMS) überwachen.</span><span class="sxs-lookup"><span data-stu-id="66567-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="66567-105">Sie können jetzt die Bereitstellung von Cloud Connector, Version 2,1 und höher, mithilfe von Operations Management Suite (OMS), einer Microsoft Cloud-IT-Verwaltungslösung, überwachen.</span><span class="sxs-lookup"><span data-stu-id="66567-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="66567-106">Mithilfe der OMS-Protokollanalyse können Sie die Verfügbarkeit und Leistung von Ressourcen, einschließlich physischer und virtueller Computer, überwachen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="66567-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="66567-107">Weitere Informationen zu OMS und zur Protokollanalyse finden Sie unter [Was ist Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="66567-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="66567-108">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="66567-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="66567-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="66567-109">Prerequisites</span></span>

- <span data-ttu-id="66567-110">Konfigurieren des Cloud Connectors für die Verwendung von OMS</span><span class="sxs-lookup"><span data-stu-id="66567-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="66567-111">Konfigurieren von OMS</span><span class="sxs-lookup"><span data-stu-id="66567-111">Configure OMS</span></span>

- <span data-ttu-id="66567-112">Analysieren der Warnungen in Ihrem Protokollanalyse-Repository</span><span class="sxs-lookup"><span data-stu-id="66567-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="66567-113">Empfohlener Überwachungs Satz</span><span class="sxs-lookup"><span data-stu-id="66567-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66567-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="66567-114">Prerequisites</span></span>

<span data-ttu-id="66567-115">Bevor Sie OMS zum Überwachen Ihrer Cloud Connector-Bereitstellung verwenden können, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="66567-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="66567-116">**Ein Azure-Konto und ein OMS-Arbeitsbereich**</span><span class="sxs-lookup"><span data-stu-id="66567-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="66567-117">Wenn Sie noch nicht über ein Azure-Konto verfügen, müssen Sie eins erstellen, um OMS-Protokollanalyse verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="66567-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="66567-118">Informationen dazu, wie Sie ein Azure-Konto erstellen und einen OMS-Arbeitsbereich einrichten, finden Sie unter [Erste Schritte mit einem Protokollanalyse-Arbeitsbereich](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span><span class="sxs-lookup"><span data-stu-id="66567-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="66567-119">**Cloud Connector, Version 2,1 oder höher**</span><span class="sxs-lookup"><span data-stu-id="66567-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="66567-120">Protokollanalyse für die Überwachung des Cloud-Connectors ist eine **neue Protokollsuche** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="66567-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="66567-121">Weitere Informationen finden Sie unter [Aktualisieren des Azure Log Analytics-Arbeitsbereichs auf eine neue Protokollsuche](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span><span class="sxs-lookup"><span data-stu-id="66567-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="66567-122">Konfigurieren des Cloud Connectors für die Verwendung von OMS</span><span class="sxs-lookup"><span data-stu-id="66567-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="66567-123">Sie müssen die lokale Cloud Connector-Umgebung für die Verwendung von OMS konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="66567-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="66567-124">Dazu benötigen Sie die OMS-Arbeitsbereichs-ID und den Schlüssel, die Sie mithilfe des OMS-Portals wie folgt finden können: Einstellungen –\>verbundene Quellen –\> Windows-Server:</span><span class="sxs-lookup"><span data-stu-id="66567-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Screenshot für Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="66567-126">Wie Sie den Cloud Connector für die Verwendung von OMS konfigurieren, hängt von Ihrem Szenario ab:</span><span class="sxs-lookup"><span data-stu-id="66567-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="66567-127">**Wenn Sie eine neue Cloud Connector-Appliance installieren oder eine Appliance erneut bereitstellen möchten**, führen Sie die folgenden Schritte aus, bevor Sie Install-CcAppliance ausführen:</span><span class="sxs-lookup"><span data-stu-id="66567-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="66567-128">Legen Sie im Abschnitt CloudConnector. ini-Datei [common] den OMSEnabled-Parameter auf true fest.</span><span class="sxs-lookup"><span data-stu-id="66567-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="66567-129">Jedes Mal, wenn Cloud Connector bereitgestellt oder aktualisiert wird, versucht der OMS-Agent automatisch auf den VMS zu installieren.</span><span class="sxs-lookup"><span data-stu-id="66567-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="66567-130">Aktivieren Sie dieses Feature, damit der OMS-Agent die automatische Aktualisierung des Cloud Connectors überleben kann.</span><span class="sxs-lookup"><span data-stu-id="66567-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="66567-131">Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie "Satz-CcCredential-AccountType OMSWorkspace" aus.</span><span class="sxs-lookup"><span data-stu-id="66567-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="66567-132">**Wenn Sie einen OMS-Agent auf einer vorhandenen Cloud Connector-Appliance installieren**, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="66567-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="66567-133">Legen Sie im Abschnitt CloudConnector. ini-Datei [common] OMSEnabled = true fest.</span><span class="sxs-lookup"><span data-stu-id="66567-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="66567-134">Führen Sie Import-CcConfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="66567-134">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="66567-135">Führen Sie Install-CcOMSAgent aus.</span><span class="sxs-lookup"><span data-stu-id="66567-135">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="66567-136">Wenn die OMSWorkspace-Anmeldeinformationen noch nie eingerichtet wurden, werden Sie beim Ausführen von install-CcOMSAgent zur Eingabe der Anmeldeinformationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="66567-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="66567-137">**Wenn Sie die OMS-Arbeitsbereichs-ID oder den Schlüssel in einer Cloud Connector-Appliance aktualisieren möchten, die bereits einen OMS-Agent installiert hat:**</span><span class="sxs-lookup"><span data-stu-id="66567-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="66567-138">Um die OMS-ID und den Schlüssel zu konfigurieren, führen Sie "Satz-CcCredential-AccountType OMSWorkspace" aus.</span><span class="sxs-lookup"><span data-stu-id="66567-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="66567-139">Führen Sie zum Anwenden der Updates die CcOMSAgent-Installation aus.</span><span class="sxs-lookup"><span data-stu-id="66567-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="66567-140">**Überprüfen Sie in allen Szenarien, ob die Agents wie folgt verbunden sind:**</span><span class="sxs-lookup"><span data-stu-id="66567-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="66567-141">Wechseln Sie im OMS-Portal zu Einstellungen –\> verbundene Quellen –\> Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="66567-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="66567-142">Es wird eine Liste der verbundenen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66567-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="66567-143">Konfigurieren von OMS</span><span class="sxs-lookup"><span data-stu-id="66567-143">Configure OMS</span></span>

<span data-ttu-id="66567-144">Als nächstes müssen Sie Ihre OMS-Konfiguration mithilfe des OMS-Portals angeben.</span><span class="sxs-lookup"><span data-stu-id="66567-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="66567-145">Insbesondere müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="66567-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="66567-146">Geben Sie Informationen zu Ereignisprotokollen und Leistungsindikatoren an.</span><span class="sxs-lookup"><span data-stu-id="66567-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="66567-147">Erstellen von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="66567-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="66567-148">Angeben von Informationen zu Ereignisprotokollen und Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="66567-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="66567-149">Im OMS-Portal müssen Sie Informationen zu den Ereignisprotokollen und Leistungsindikatoren wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="66567-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="66567-150">Wechseln Sie zu Einstellungen\>-Daten\>-Windows-Ereignisprotokolle, und fügen Sie Ereignisprotokolle für Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="66567-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="66567-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="66567-151">Lync Server</span></span>

   - <span data-ttu-id="66567-152">Anwendung</span><span class="sxs-lookup"><span data-stu-id="66567-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="66567-153">Sie müssen lync Server manuell in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="66567-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="66567-154">Sie wird in der Dropdownliste nicht als Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66567-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="66567-155">Weitere Informationen finden Sie unter [Windows-Ereignisprotokoll-Datenquellen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) .</span><span class="sxs-lookup"><span data-stu-id="66567-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="66567-156">Wechseln Sie zu Einstellungen\>-Daten\> -Windows-Leistungsindikatoren, und fügen Sie Leistungsindikatoren hinzu für:</span><span class="sxs-lookup"><span data-stu-id="66567-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="66567-157">**Zähler für Betriebssystemebene**.</span><span class="sxs-lookup"><span data-stu-id="66567-157">**OS level counters**.</span></span> <span data-ttu-id="66567-158">Sie können Zähler auf Betriebssystemebene hinzufügen, beispielsweise Prozessorauslastung, Speicherauslastung, Netzwerkauslastung, oder Sie können vorhandene Lösungen wie Kapazität und Leistung, Netzwerk Leistungs Monitor verwenden, ohne explizit Leistungsindikatoren hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="66567-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="66567-159">Unabhängig davon, wie Sie sich entscheiden, diese zu überwachen, empfiehlt Microsoft, diese Betriebssystem Zähler zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="66567-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="66567-160">**Skype for Business-Leistungsindikatoren**</span><span class="sxs-lookup"><span data-stu-id="66567-160">**Skype for Business counters**.</span></span> <span data-ttu-id="66567-161">Skype for Business stellt zahlreiche Leistungsindikatoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="66567-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="66567-162">Sie können diese Leistungsindikatoren finden, indem Sie sich bei einem beliebigen Vermittlungs Server anmelden und den System Monitor öffnen.</span><span class="sxs-lookup"><span data-stu-id="66567-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="66567-163">Diese Leistungsindikatoren beginnen mit "ls:".</span><span class="sxs-lookup"><span data-stu-id="66567-163">These counters start with "LS:".</span></span> <span data-ttu-id="66567-164">Microsoft empfiehlt, dass Sie mindestens mit den folgenden Kapazitäts Zählern beginnen und andere Personen hinzufügen, die von Interesse sind:</span><span class="sxs-lookup"><span data-stu-id="66567-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="66567-165">Aktive Anrufe insgesamt:</span><span class="sxs-lookup"><span data-stu-id="66567-165">Total active calls:</span></span>

       - <span data-ttu-id="66567-166">LS: MediationServer-eingehende Anrufe (_Total\- ) aktuell</span><span class="sxs-lookup"><span data-stu-id="66567-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="66567-167">LS: MediationServer-ausgehende Anrufe (_Total\- ) aktuell</span><span class="sxs-lookup"><span data-stu-id="66567-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="66567-168">Gesamtzahl der aktiven Medien Umgehungs Anrufe:</span><span class="sxs-lookup"><span data-stu-id="66567-168">Total active media bypass calls:</span></span>

       - <span data-ttu-id="66567-169">LS: MediationServer-eingehende Anrufe (_Total\- ) Active Media Bypass-Anrufe</span><span class="sxs-lookup"><span data-stu-id="66567-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="66567-170">LS: MediationServer-ausgehende Anrufe (_Total\- ) Active Media Bypass-Anrufe</span><span class="sxs-lookup"><span data-stu-id="66567-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="66567-171">Sie müssen die Leistungsindikatoren manuell in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="66567-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="66567-172">Sie werden in der Dropdownliste nicht als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="66567-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="66567-173">Weitere Informationen finden Sie unter [Windows-und Linux-Leistungsdatenquellen in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) .</span><span class="sxs-lookup"><span data-stu-id="66567-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="66567-174">Erstellen von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="66567-174">Create alerts</span></span>

<span data-ttu-id="66567-175">Es gibt zwei Arten von Benachrichtigungen in OMS: Anzahl der Ergebnisse und Metriken für die Messung.</span><span class="sxs-lookup"><span data-stu-id="66567-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="66567-176">Weitere Informationen zum Erstellen von Benachrichtigungen finden Sie unter [Arbeiten mit Warnungsregeln in der Protokollanalyse](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span><span class="sxs-lookup"><span data-stu-id="66567-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="66567-177">Beim Erstellen von Benachrichtigungen sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="66567-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="66567-178">Stellen Sie sicher, dass es sich bei der Benachrichtigung um eine Anzahl von Ergebnissen handelt, bei der es sich um die Standardauswahl handelt.</span><span class="sxs-lookup"><span data-stu-id="66567-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="66567-179">Bei den Demo-Abfragen muss "Anzahl der Ergebnisse" auf "größer als 0" festgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="66567-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="66567-180">Es wird empfohlen, dass Sie sowohl Zeitfenster als auch Warnungs Häufigkeit auf 5 Minuten einstellen.</span><span class="sxs-lookup"><span data-stu-id="66567-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="66567-181">Es wird empfohlen, dass Sie die Option "Benachrichtigungen unterdrücken" nicht für Demo Benachrichtigungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="66567-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="66567-182">Für typische Benachrichtigungsszenarien empfiehlt Microsoft, ein Warnungs paar zu erstellen: eine Fehlermeldung und eine Benachrichtigung zum Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="66567-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="66567-183">Wählen Sie für die Fehlermeldung Schweregrad kritisch aus. Wählen Sie für die Warnung zurücksetzen die Option Schweregrad Information aus.</span><span class="sxs-lookup"><span data-stu-id="66567-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="66567-184">In den folgenden Abschnitten wird beschrieben, wie Beispiel Benachrichtigungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="66567-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="66567-185">**Erstellen eines Warnungs Paars: "RTCMEDSRV wird nicht auf Vermittlungsservern ausgeführt" und "RTCMEDSRV ist wieder in der Ausführung in Vermittlungsservern"**</span><span class="sxs-lookup"><span data-stu-id="66567-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="66567-186">So erstellen Sie dieses Warnungs paar:</span><span class="sxs-lookup"><span data-stu-id="66567-186">To create this alert pair:</span></span>

- <span data-ttu-id="66567-187">Die Abfrage für die Fehlermeldung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="66567-187">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="66567-188">Die Abfrage verwendet den Computerfilter *, auf dem Computer "MediationServer" enthält* .</span><span class="sxs-lookup"><span data-stu-id="66567-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="66567-189">Der Filter markiert nur den Computer, dessen Name die Zeichenfolge "MediationServer" enthält.</span><span class="sxs-lookup"><span data-stu-id="66567-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="66567-190">Ersetzen Sie den Filter durch ihren eigenen Computerfilter, oder entfernen Sie ihn einfach.</span><span class="sxs-lookup"><span data-stu-id="66567-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="66567-191">Sie können komplexe Zeichenfolgenfilter ohne reguläre Ausdrücke erstellen.</span><span class="sxs-lookup"><span data-stu-id="66567-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="66567-192">Weitere Informationen finden Sie unter [Zeichenfolgenoperatoren](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span><span class="sxs-lookup"><span data-stu-id="66567-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="66567-193">Sie können auch die Verwendung regulärer Ausdrücke auswählen.</span><span class="sxs-lookup"><span data-stu-id="66567-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="66567-194">Darüber hinaus können Sie eine Computergruppe erstellen, indem Sie eine Suchabfrage speichern und diese Gruppe als ihren Computerfilter in ihrer Warnungs Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="66567-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="66567-195">Weitere Informationen finden Sie unter [Computer Gruppen in Log-Analyse-Protokoll suchen](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span><span class="sxs-lookup"><span data-stu-id="66567-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="66567-196">Für jeden Computer erhält die Fehler Abfrage das letzte Ereignisprotokoll sowohl für den Start des RTCMEDSRV-Diensts als auch für den Dienst Stopp.</span><span class="sxs-lookup"><span data-stu-id="66567-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="66567-197">Wenn es sich bei dem letzten Ereignis um das Dienst Stoppereignis handelt, gibt es ein Protokoll zurück. Wenn es sich bei dem letzten Ereignis um das Startereignis des Diensts handelt, wird Nothing zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66567-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="66567-198">Kurz gesagt: die Abfrage gibt eine Liste der Server zurück, deren RTCMEDSRV im Zeitfenster angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="66567-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="66567-199">Die Abfrage für die Reset-Benachrichtigung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="66567-199">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="66567-200">Die Zurücksetzungs Abfrage führt genau das Gegenteil der Fehler Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="66567-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="66567-201">Für jeden Computer wird ein Wert zurückgegeben, wenn es sich bei dem letzten Ereignis um das Dienststart Ereignis handelt. Wenn es sich bei dem letzten Ereignis um das Dienst Stoppereignis handelt, wird Nothing zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66567-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="66567-202">**Erstellen eines Warnungs Paars: "zu viele gleichzeitige Anrufe in Vermittlungsservern" und "gleichzeitige Anrufe fallen auf normale Last zurück"**</span><span class="sxs-lookup"><span data-stu-id="66567-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="66567-203">So erstellen Sie diese Benachrichtigung:</span><span class="sxs-lookup"><span data-stu-id="66567-203">To create this alert:</span></span>

- <span data-ttu-id="66567-204">Die Abfrage für die Fehlermeldung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="66567-204">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="66567-205">Die Abfrage ruft für jeden Computer die letzten Leistungsindikatoren für eingehenden und ausgehenden Anruf ab und addiert diese beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="66567-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="66567-206">Wenn der Summenwert 500 überschreitet, wird ein Protokoll zurückgegeben. Wenn dies nicht der Fall ist, wird Nothing zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66567-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="66567-207">Kurz gesagt: die Abfrage gibt eine Liste der Server zurück, deren gleichzeitige Anrufe im Zeitfenster zu viele sind.</span><span class="sxs-lookup"><span data-stu-id="66567-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="66567-208">Die Abfrage für die Reset-Benachrichtigung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="66567-208">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="66567-209">Die Zurücksetzungs Abfrage führt genau das Gegenteil der Fehler Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="66567-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="66567-210">Die Abfrage ruft für jeden Computer die letzten Leistungsindikatoren für eingehenden und ausgehenden Anruf ab und addiert diese beiden Werte.</span><span class="sxs-lookup"><span data-stu-id="66567-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="66567-211">Wenn der Sum-Wert kleiner als 500 ist, wird ein Protokoll zurückgegeben. Andernfalls wird nichts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66567-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="66567-212">**Erstellen einer Benachrichtigung: "CPU- \> Auslastung 90 oder RTCMEDIARELAY in den Servern angehalten"**</span><span class="sxs-lookup"><span data-stu-id="66567-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="66567-213">Um diese Benachrichtigung zu erstellen, lautet die Abfrage wie folgt:</span><span class="sxs-lookup"><span data-stu-id="66567-213">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="66567-214">Die Abfrage ruft alle Prozessor Nutzungszähler und Dienst Stoppereignisse von allen Computern ab und gibt ein Protokoll zurück, wenn entweder die Prozessorauslastung 90% überschreitet oder der Dienst jemals beendet wird.</span><span class="sxs-lookup"><span data-stu-id="66567-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="66567-215">Analysieren der Warnungen in Ihrem Protokollanalyse-Repository</span><span class="sxs-lookup"><span data-stu-id="66567-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="66567-216">Verwenden Sie die Warnungs Verwaltungslösung, um die Warnungen in Ihrem Repository zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="66567-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="66567-217">Weitere Informationen finden Sie unter [Warnungs Verwaltungslösung in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .</span><span class="sxs-lookup"><span data-stu-id="66567-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="66567-218">Empfohlener minimaler Überwachungs Satz</span><span class="sxs-lookup"><span data-stu-id="66567-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="66567-219">So ermitteln Sie Probleme mit Ereignisprotokollen und Leistungsindikatoren:</span><span class="sxs-lookup"><span data-stu-id="66567-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="66567-220">**Ereignisprotokolle**</span><span class="sxs-lookup"><span data-stu-id="66567-220">**Event logs.**</span></span> <span data-ttu-id="66567-221">Bei jedem Problem sollte ein Ereignispaar vorhanden sein, bei dem eine Gruppe von Ereignissen angibt, dass etwas falsch ist, während die andere Person angibt, dass alles gut ist.</span><span class="sxs-lookup"><span data-stu-id="66567-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="66567-222">Für einen bestimmten Zeitraum ist es das letzte aufgezeichnete Ereignis, das angibt, ob für diesen Zeitraum ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="66567-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="66567-223">**Leistungsindikatoren**</span><span class="sxs-lookup"><span data-stu-id="66567-223">**Performance Counters.**</span></span> <span data-ttu-id="66567-224">Für die überwachten Leistungsindikatoren sollte ein Schwellenwert vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="66567-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="66567-225">In der folgenden Tabelle sind die Dienste aufgeführt, die Microsoft überwachen empfiehlt, indem Sie die Start-und Stoppereignis-IDs auflisten:</span><span class="sxs-lookup"><span data-stu-id="66567-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="66567-226">Dienst Name</span><span class="sxs-lookup"><span data-stu-id="66567-226">Service Name</span></span>  <br/> |<span data-ttu-id="66567-227">Ziel Server Rolle</span><span class="sxs-lookup"><span data-stu-id="66567-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="66567-228">Ereignis-ID beenden</span><span class="sxs-lookup"><span data-stu-id="66567-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="66567-229">Ereignis-ID starten</span><span class="sxs-lookup"><span data-stu-id="66567-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66567-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="66567-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="66567-231">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="66567-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="66567-232">25003</span><span class="sxs-lookup"><span data-stu-id="66567-232">25003</span></span>  <br/> |<span data-ttu-id="66567-233">25002</span><span class="sxs-lookup"><span data-stu-id="66567-233">25002</span></span>  <br/> |
|<span data-ttu-id="66567-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="66567-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="66567-235">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="66567-235">Edge Server</span></span>  <br/> |<span data-ttu-id="66567-236">12289</span><span class="sxs-lookup"><span data-stu-id="66567-236">12289</span></span>  <br/> |<span data-ttu-id="66567-237">12288</span><span class="sxs-lookup"><span data-stu-id="66567-237">12288</span></span>  <br/> |
|<span data-ttu-id="66567-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="66567-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="66567-239">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="66567-239">Edge Server</span></span>  <br/> |<span data-ttu-id="66567-240">19003</span><span class="sxs-lookup"><span data-stu-id="66567-240">19003</span></span>  <br/> |<span data-ttu-id="66567-241">19002</span><span class="sxs-lookup"><span data-stu-id="66567-241">19002</span></span>  <br/> |
|<span data-ttu-id="66567-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="66567-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="66567-243">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="66567-243">Edge Server</span></span>  <br/> |<span data-ttu-id="66567-244">22003</span><span class="sxs-lookup"><span data-stu-id="66567-244">22003</span></span>  <br/> |<span data-ttu-id="66567-245">22002</span><span class="sxs-lookup"><span data-stu-id="66567-245">22002</span></span>  <br/> |

<span data-ttu-id="66567-246">In der folgenden Tabelle sind die Netzwerkprobleme aufgeführt, die von Microsoft überwacht werden sollten:</span><span class="sxs-lookup"><span data-stu-id="66567-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="66567-247">Monitor Name</span><span class="sxs-lookup"><span data-stu-id="66567-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="66567-248">Ziel Server Rolle</span><span class="sxs-lookup"><span data-stu-id="66567-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="66567-249">Erfolgsereignis-ID-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="66567-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="66567-250">Fehlerereignis-ID-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="66567-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="66567-251">Beispiel für Fehler</span><span class="sxs-lookup"><span data-stu-id="66567-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="66567-252">Verbindungsfehler beim Vermittlungs Server zum Gateway</span><span class="sxs-lookup"><span data-stu-id="66567-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="66567-253">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="66567-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="66567-254">25062</span><span class="sxs-lookup"><span data-stu-id="66567-254">25062</span></span>                              |                                  | <span data-ttu-id="66567-255">25002</span><span class="sxs-lookup"><span data-stu-id="66567-255">25002</span></span>  <br/>           |
| <span data-ttu-id="66567-256">Fehler bei Vermittlungs Server zum Gateway-Anruf Abschluss</span><span class="sxs-lookup"><span data-stu-id="66567-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="66567-257">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="66567-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="66567-258">25064</span><span class="sxs-lookup"><span data-stu-id="66567-258">25064</span></span>                              |                                  | <span data-ttu-id="66567-259">25002</span><span class="sxs-lookup"><span data-stu-id="66567-259">25002</span></span>  <br/>           |
| <span data-ttu-id="66567-260">Kritische Netzwerkprobleme</span><span class="sxs-lookup"><span data-stu-id="66567-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="66567-261">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="66567-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="66567-262">14353</span><span class="sxs-lookup"><span data-stu-id="66567-262">14353</span></span>                              |                                  | <span data-ttu-id="66567-263">12288</span><span class="sxs-lookup"><span data-stu-id="66567-263">12288</span></span>  <br/>           |

<span data-ttu-id="66567-264">Im folgenden sind die Leistungsindikatoren für die Anrufkapazität aufgeführt, die überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="66567-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="66567-265">Diese Zahlen sollten kürzer sein als 500 für Cloud Connector Standard Edition; weniger als 50 für Cloud Connector mindestens Edition.</span><span class="sxs-lookup"><span data-stu-id="66567-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="66567-266">LS: MediationServer-eingehende Anrufe (_Total\- ) aktuell</span><span class="sxs-lookup"><span data-stu-id="66567-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="66567-267">LS: MediationServer-ausgehende Anrufe (_Total\- ) aktuell</span><span class="sxs-lookup"><span data-stu-id="66567-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="66567-268">LS: MediationServer-eingehende Anrufe (_Total\- ) Active Media Bypass-Anrufe</span><span class="sxs-lookup"><span data-stu-id="66567-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="66567-269">LS: MediationServer-ausgehende Anrufe (_Total\- ) Active Media Bypass-Anrufe</span><span class="sxs-lookup"><span data-stu-id="66567-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="66567-270">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66567-270">See also</span></span>

<span data-ttu-id="66567-271">Weitere Informationen zum Arbeiten mit OMS finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="66567-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="66567-272">Suchen von Daten mithilfe von Protokoll suchen in der Protokollanalyse</span><span class="sxs-lookup"><span data-stu-id="66567-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="66567-273">Azure Log Analytics-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="66567-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="66567-274">Grundlegendes zu Warnungen in der Protokollanalyse</span><span class="sxs-lookup"><span data-stu-id="66567-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="66567-275">Verbinden von Windows-Computern mit dem Protokollanalyse Dienst in Azure</span><span class="sxs-lookup"><span data-stu-id="66567-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)



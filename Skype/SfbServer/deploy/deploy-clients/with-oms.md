---
title: Bereitstellen der Verwaltung von Skype Room System V2 mit OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: In diesem Artikel wird erläutert, wie in Microsoft Operations Management Suite mit Weise integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräte bereitstellen.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="8a03d-103">Bereitstellen der Verwaltung von Skype Room System V2 mit OMS</span><span class="sxs-lookup"><span data-stu-id="8a03d-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="8a03d-104">In diesem Artikel wird erläutert, wie in Microsoft Operations Management Suite mit Weise integrierte, End-to-End-Verwaltung von Skype Raum Systemen v2 Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="8a03d-p101">Sie können Microsoft Operations Management Suite (OMS) so konfigurieren, dass grundlegende Telemetriedaten bereitgestellt werden, die Ihnen bei der Verwaltung von Geräten für Skype-Besprechungsräume helfen. Wenn Ihre Verwaltungslösung heranreift, können Sie zusätzliche Daten- und Verwaltungsfunktionen erwerben, um eine detailliertere Ansicht der Geräteleistung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="8a03d-107">Allgemein müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a03d-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="8a03d-108">Konfigurieren von Geräten für die OMS-Verwaltung </span><span class="sxs-lookup"><span data-stu-id="8a03d-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="8a03d-109">Zuordnen benutzerdefinierter Felder</span><span class="sxs-lookup"><span data-stu-id="8a03d-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="8a03d-110">Definieren der SRS V2-Ansichten in OMS</span><span class="sxs-lookup"><span data-stu-id="8a03d-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="8a03d-111">Suchen und Aufzeichnen von Gerätestandorten, -funktionen und -konfigurationen</span><span class="sxs-lookup"><span data-stu-id="8a03d-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="8a03d-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="8a03d-112"></span></span>

<span data-ttu-id="8a03d-p102">Im ersten Schritt erstellen Sie eine detaillierte Datenbank aller Geräte im System, der Details zu ihren Funktionen und Konfigurationen und der Standorte. In mittleren Organisationen kann ein Arbeitsblatt für diese Aufgabe ausreichen. Wenn Sie in einer größeren Organisation arbeiten, müssen Sie möglicherweise Inventarverwaltungstools und Dienste von Drittanbietern in Betracht ziehen. Wichtig ist, dass Sie den Standort und alle relevanten Details jedes Geräts aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="8a03d-117">Anschließend können Sie diese Informationen nutzen, um Techniker zu entsenden und Gerätepatches und -upgrades zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8a03d-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="8a03d-118">Konfigurieren von Geräten für die OMS-Verwaltung </span><span class="sxs-lookup"><span data-stu-id="8a03d-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="8a03d-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="8a03d-119"></span></span>

<span data-ttu-id="8a03d-120">Führen Sie für jedes Gerät SRS wie unter [an den Log Analytics-Dienst in Azure-Computern mit Windows eine Verbindung herstellen](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span><span class="sxs-lookup"><span data-stu-id="8a03d-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="8a03d-121">Konfigurieren von OMS zum Erfassen von Geräteereignisprotokollen</span><span class="sxs-lookup"><span data-stu-id="8a03d-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="8a03d-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="8a03d-122"></span></span>

<span data-ttu-id="8a03d-123">Sie müssen speziell zum Sammeln von Ereignisprotokollen von SRS Geräte entsprechend den Schritten unter [Windows-Ereignisprotokoll-Datenquellen im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)OMS konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8a03d-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="8a03d-124">Ereignisprotokoll SRS auswählen ist "Skype Raum System", und überprüfen Sie die Optionsfelder für alle Typen: Fehler, Warnung und Informationen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="8a03d-125">Zuordnen benutzerdefinierter Felder</span><span class="sxs-lookup"><span data-stu-id="8a03d-125">Map custom fields</span></span>
<span data-ttu-id="8a03d-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="8a03d-126"></span></span>

<span data-ttu-id="8a03d-127">Bevor die Kacheln, die in den [Ansichten in OMS definieren die SRS v2](with-oms.md#Views) erstellt verwendet werden können, müssen Sie benutzerdefinierte Felder für die Ansicht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="8a03d-128">Einzelheiten zum Erstellen von benutzerdefinierter Feldern finden Sie unter [benutzerdefinierte Felder im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) .</span><span class="sxs-lookup"><span data-stu-id="8a03d-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="8a03d-129">Verwenden Sie die unten aufgeführten Zuordnungen, OMS automatisch die _CF hinzufügen, wenn Sie das neue Feld zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8a03d-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8a03d-130">Denken Sie daran, dass alle JSON und OMS Felder Groß-/Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8a03d-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="8a03d-131">**Zuordnen von benutzerdefinierten Feldern**</span><span class="sxs-lookup"><span data-stu-id="8a03d-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="8a03d-132">**JSON-Feld**</span><span class="sxs-lookup"><span data-stu-id="8a03d-132">**JSON field**</span></span>|<span data-ttu-id="8a03d-133">**OMS-benutzerdefiniertes Feld**</span><span class="sxs-lookup"><span data-stu-id="8a03d-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8a03d-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a03d-134">Description</span></span>  <br/> |<span data-ttu-id="8a03d-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="8a03d-136">ResourceState</span></span>  <br/> |<span data-ttu-id="8a03d-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-138">-Parameterwert</span><span class="sxs-lookup"><span data-stu-id="8a03d-138">OperationName</span></span>  <br/> |<span data-ttu-id="8a03d-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="8a03d-140">OperationResult</span></span>  <br/> |<span data-ttu-id="8a03d-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-142">OS</span><span class="sxs-lookup"><span data-stu-id="8a03d-142">OS</span></span>  <br/> |<span data-ttu-id="8a03d-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-144">OSVersion</span><span class="sxs-lookup"><span data-stu-id="8a03d-144">OSVersion</span></span>  <br/> |<span data-ttu-id="8a03d-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-146">Alias</span><span class="sxs-lookup"><span data-stu-id="8a03d-146">Alias</span></span>  <br/> |<span data-ttu-id="8a03d-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-148">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8a03d-148">DisplayName</span></span>  <br/> |<span data-ttu-id="8a03d-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="8a03d-150">AppVersion</span></span>  <br/> |<span data-ttu-id="8a03d-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-152">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="8a03d-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="8a03d-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="8a03d-154">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="8a03d-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="8a03d-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="8a03d-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="8a03d-156">Definieren der SRS V2-Ansichten in OMS</span><span class="sxs-lookup"><span data-stu-id="8a03d-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="8a03d-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="8a03d-157"></span></span>

<span data-ttu-id="8a03d-158">Nachdem Daten erfasst werden und benutzerdefinierte Felder zugeordnet sind, können OMS-Ansicht-Designer Sie ein Dashboard mit Kacheln zum Überwachen von Ereignissen, SRS v2 entwickeln.</span><span class="sxs-lookup"><span data-stu-id="8a03d-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="8a03d-159">Verwenden Sie Designer anzeigen, um die folgenden Kacheln erstellen, finden Sie unter [Use Ansicht-Designer zum Erstellen von benutzerdefinierter Ansichten im Protokoll Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="8a03d-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="8a03d-160">Erstellen einer Kachel, die fehlerfreie Geräte anzeigt</span><span class="sxs-lookup"><span data-stu-id="8a03d-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="8a03d-161">Definieren Sie den Fall: </span><span class="sxs-lookup"><span data-stu-id="8a03d-161">Define the case:</span></span> 
    
    <span data-ttu-id="8a03d-162">Diese Kachel zeigt alle Geräte an, die in den letzten zehn Minuten eine Taktnachricht gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="8a03d-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="8a03d-163">Weisen Sie einen Gruppentitel zu. </span><span class="sxs-lookup"><span data-stu-id="8a03d-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="8a03d-164">Aktivieren Sie das neue Gruppe</span><span class="sxs-lookup"><span data-stu-id="8a03d-164">Check the new group box</span></span>
    
4. <span data-ttu-id="8a03d-165">Fügen Sie den Legendentext für die Kachel hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a03d-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="8a03d-166">Geben Sie die Kachelabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="8a03d-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="8a03d-167">Geben Sie die Listenabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="8a03d-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="8a03d-168">Definieren Sie den Spaltentitelnamen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="8a03d-169">Definieren der Wert der Spalte Titel</span><span class="sxs-lookup"><span data-stu-id="8a03d-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="8a03d-170">Geben Sie die Navigationsabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="8a03d-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="8a03d-171">Erstellen der Kachel, die Geräte mit Konnektivitätsproblemen anzeigt</span><span class="sxs-lookup"><span data-stu-id="8a03d-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="8a03d-172">Definieren Sie den Fall: </span><span class="sxs-lookup"><span data-stu-id="8a03d-172">Define the case:</span></span> 
    
    <span data-ttu-id="8a03d-p106">Diese Kachel zeigt alle Geräte an, die nicht in den letzten zehn Minuten eine Taktnachricht gesendet haben. Bei diesen Geräten liegen möglicherweise Probleme mit der Netzwerk-, Exchange- oder Skype for Business-Konnektivität vor.</span><span class="sxs-lookup"><span data-stu-id="8a03d-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="8a03d-175">Weisen Sie einen Gruppentitel zu. </span><span class="sxs-lookup"><span data-stu-id="8a03d-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="8a03d-176">Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“.</span><span class="sxs-lookup"><span data-stu-id="8a03d-176">Do not check the new group box.</span></span> <span data-ttu-id="8a03d-177">Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.</span><span class="sxs-lookup"><span data-stu-id="8a03d-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="8a03d-178">Fügen Sie den Legendentext für die Kachel hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a03d-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="8a03d-179">Geben Sie die Kachelabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="8a03d-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="8a03d-180">Geben Sie die Listenabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="8a03d-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="8a03d-181">Definieren Sie den Spaltentitelnamen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="8a03d-182">Definieren Sie den Spaltentitelwert. </span><span class="sxs-lookup"><span data-stu-id="8a03d-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="8a03d-183">Geben Sie die Navigationsabfrage ein.</span><span class="sxs-lookup"><span data-stu-id="8a03d-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="8a03d-184">Auflisten von Geräten mit Hardwarefehler </span><span class="sxs-lookup"><span data-stu-id="8a03d-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="8a03d-185">Definieren Sie den Fall: </span><span class="sxs-lookup"><span data-stu-id="8a03d-185">Define the case:</span></span> 
    
   <span data-ttu-id="8a03d-186">Diese Kachel zeigt alle Geräte, die eine Meldung angezeigt, eine einen oder mehrere Komponente Hardwareprobleme in den letzten 10 Minuten gesendet.</span><span class="sxs-lookup"><span data-stu-id="8a03d-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="8a03d-187">Weisen Sie einen Gruppentitel zu. </span><span class="sxs-lookup"><span data-stu-id="8a03d-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="8a03d-188">Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“.</span><span class="sxs-lookup"><span data-stu-id="8a03d-188">Do not check the new group box.</span></span> <span data-ttu-id="8a03d-189">Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.</span><span class="sxs-lookup"><span data-stu-id="8a03d-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="8a03d-190">Kachellegende: </span><span class="sxs-lookup"><span data-stu-id="8a03d-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="8a03d-191">Kachelabfrage</span><span class="sxs-lookup"><span data-stu-id="8a03d-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="8a03d-192">Listenabfrage:</span><span class="sxs-lookup"><span data-stu-id="8a03d-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="8a03d-193">Spaltentitelname: </span><span class="sxs-lookup"><span data-stu-id="8a03d-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="8a03d-194">Spaltentitelwert: </span><span class="sxs-lookup"><span data-stu-id="8a03d-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="8a03d-195">Navigationsabfrage: </span><span class="sxs-lookup"><span data-stu-id="8a03d-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="8a03d-196">Auflisten von Geräten mit App-Fehler  </span><span class="sxs-lookup"><span data-stu-id="8a03d-196">List devices with an App error</span></span>

1. <span data-ttu-id="8a03d-197">Definieren Sie den Fall:</span><span class="sxs-lookup"><span data-stu-id="8a03d-197">Define the case:</span></span> 
    
   <span data-ttu-id="8a03d-198">Diese Kachel zeigt alle SRS-Geräte an, die in den letzten zehn Minuten mindestens einen App-Komponentenfehler gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="8a03d-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="8a03d-199">Weisen Sie einen Gruppentitel zu. </span><span class="sxs-lookup"><span data-stu-id="8a03d-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="8a03d-200">Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“.</span><span class="sxs-lookup"><span data-stu-id="8a03d-200">Do not check the new group box.</span></span> <span data-ttu-id="8a03d-201">Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.</span><span class="sxs-lookup"><span data-stu-id="8a03d-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="8a03d-202">Kachellegende: </span><span class="sxs-lookup"><span data-stu-id="8a03d-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="8a03d-203">Kachelabfrage: </span><span class="sxs-lookup"><span data-stu-id="8a03d-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="8a03d-204">Listenabfrage: </span><span class="sxs-lookup"><span data-stu-id="8a03d-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="8a03d-205">Spaltentitelname: </span><span class="sxs-lookup"><span data-stu-id="8a03d-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="8a03d-206">Spaltentitelwert: </span><span class="sxs-lookup"><span data-stu-id="8a03d-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="8a03d-207">Navigationsabfrage:</span><span class="sxs-lookup"><span data-stu-id="8a03d-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="8a03d-208">Auflisten von Geräten, die neu gestartet werden mussten</span><span class="sxs-lookup"><span data-stu-id="8a03d-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="8a03d-209">Definieren Sie den Fall:</span><span class="sxs-lookup"><span data-stu-id="8a03d-209">Define the case:</span></span> 
    
   <span data-ttu-id="8a03d-210">Diese Kachel zeigt alle SRS-Geräte, die in den letzten 24 Stunden neu gestartet wurden, sowie die Anzahl der Neustarts an.</span><span class="sxs-lookup"><span data-stu-id="8a03d-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="8a03d-211">Weisen Sie einen Gruppentitel zu. </span><span class="sxs-lookup"><span data-stu-id="8a03d-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="8a03d-212">Aktivieren Sie nicht das Kontrollkästchen „Neue Gruppe“.</span><span class="sxs-lookup"><span data-stu-id="8a03d-212">Do not check the new group box.</span></span> <span data-ttu-id="8a03d-213">Dies haben Sie bereits beim Erstellen von Kachel 1 getan, und dies ist nicht erneut notwendig.</span><span class="sxs-lookup"><span data-stu-id="8a03d-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="8a03d-214">Kachellegende: </span><span class="sxs-lookup"><span data-stu-id="8a03d-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="8a03d-215">Kachelabfrage: </span><span class="sxs-lookup"><span data-stu-id="8a03d-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="8a03d-216">Listenabfrage: </span><span class="sxs-lookup"><span data-stu-id="8a03d-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="8a03d-217">Spaltentitelname: </span><span class="sxs-lookup"><span data-stu-id="8a03d-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="8a03d-218">Spaltentitelwert: </span><span class="sxs-lookup"><span data-stu-id="8a03d-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="8a03d-219">Navigationsabfrage: </span><span class="sxs-lookup"><span data-stu-id="8a03d-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="8a03d-p111">Damit ist die Erstellung der Ansicht abgeschlossen. Die zurzeit verfügbaren Warnungen werden alle auf mindestens einer dieser Kacheln angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a03d-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="8a03d-222">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8a03d-222">See also</span></span>
<span data-ttu-id="8a03d-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="8a03d-223"></span></span>

#### 

[<span data-ttu-id="8a03d-224">Planen der Verwaltung von Skype Raum Systemen v2 mit OMS</span><span class="sxs-lookup"><span data-stu-id="8a03d-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="8a03d-225">Verwalten von Skype Raum Systemen v2 Geräte mit OMS</span><span class="sxs-lookup"><span data-stu-id="8a03d-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)


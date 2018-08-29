---
title: Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In diesem Thema werden die Tools in der Skype für Business Server 2015 Resource Kit, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung beschrieben. Die Skype für Business Server 2015 Resource Kit können Sie Routineaufgaben für IT-Administratoren erleichtern, die Bereitstellung und Verwaltung von Skype für Business Server 2015. Beispielsweise kann das Tool Web Conf Data verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden. Mithilfe des SEFAUtil-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir empfehlen IT-Administratoren mit diesen Tools Skype für Business Server 2015 effektiver verwalten.
ms.openlocfilehash: e259e4252274621ac3593cfb379ddc89ee37544c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257808"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="3940b-107">Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3940b-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="3940b-108">In diesem Thema werden die Tools in der Skype für Business Server 2015 Resource Kit, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3940b-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="3940b-109">Die Skype für Business Server 2015 Resource Kit können Sie Routineaufgaben für IT-Administratoren erleichtern, die Bereitstellung und Verwaltung von Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3940b-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="3940b-110">Beispielsweise kann das Tool **Web Conf Data** verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="3940b-111">Mithilfe des **SEFAUtil**-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten.</span><span class="sxs-lookup"><span data-stu-id="3940b-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="3940b-112">Wir empfehlen IT-Administratoren mit diesen Tools Skype für Business Server 2015 effektiver verwalten.</span><span class="sxs-lookup"><span data-stu-id="3940b-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="3940b-113">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="3940b-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="3940b-114">Um die Skype für Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) aus dem Download Center herunter.</span><span class="sxs-lookup"><span data-stu-id="3940b-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="3940b-p103">Führen Sie **OCSResKit.msi ** aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: **%ProgramFiles%\Skype for Business Server 2015\ResKit**. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die über Hilfsdateien verfügen, befinden sich in eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="3940b-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="3940b-119">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="3940b-119">Supported Environments</span></span>

<span data-ttu-id="3940b-120">Auf einem Server, der für Skype für Business Server 2015, normalerweise auf einem verwendet wird, um das Ausführen von Skype für Business Server 2015 benötigt erfüllt, sollte die Skype für Business Server 2015 Resource Kit installiert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="3940b-121">Resource Kit-Tools – Übersicht</span><span class="sxs-lookup"><span data-stu-id="3940b-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="3940b-122">Es folgt eine Liste der Tools, die in der Skype für Business Server 2015 Resource Kit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3940b-123">Im folgenden Abschnitt wird jedes Tool mit seinen Anforderungen und Beispielanwendungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3940b-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="3940b-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3940b-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="3940b-125">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="3940b-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="3940b-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="3940b-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="3940b-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="3940b-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="3940b-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3940b-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="3940b-129">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="3940b-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="3940b-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3940b-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="3940b-131">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="3940b-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="3940b-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3940b-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="3940b-133">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="3940b-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="3940b-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="3940b-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="3940b-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3940b-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="3940b-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3940b-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="3940b-137">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="3940b-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="3940b-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="3940b-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="3940b-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="3940b-139">ABSConfig</span></span>
<span data-ttu-id="3940b-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-140"></span></span>

<span data-ttu-id="3940b-141">Das Dienst Adressbuchkonfiguration-Tool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren Adressbuchdienst-Konfiguration in Skype für Business Server 2015 anpassen kann.</span><span class="sxs-lookup"><span data-stu-id="3940b-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="3940b-142">Mit diesem Tool können außerdem Skype für Business Server 2015 Administratoren die Standardeinstellungen für den Adressbuchdienst wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3940b-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-143">Description</span></span>

<span data-ttu-id="3940b-144">ABSConfig ist eine graphical User Interface-Anwendung, die ermöglicht Administratoren, Active Directory Domain Services Attribute konfigurieren, die im Zusammenhang mit Adressbuchdienst.</span><span class="sxs-lookup"><span data-stu-id="3940b-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="3940b-145">Dies sind die primären Verwendungsszenarien für das Tool:</span><span class="sxs-lookup"><span data-stu-id="3940b-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="3940b-146">So aktivieren Sie Administratoren Attribute in Active Directory-Domänendiensten die Attribute für Skype für Business Server 2015 zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3940b-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="3940b-147">Administratoren das Angeben des Attributs in Active Directory Domain Services ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder aus diesen ausgeschlossen werden soll</span><span class="sxs-lookup"><span data-stu-id="3940b-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="3940b-148">Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen</span><span class="sxs-lookup"><span data-stu-id="3940b-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="3940b-149">Das Tool ABSConfig kann mithilfe der Datei ABSConfig.exe gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="3940b-150">Das Tool zur Registerkarte **Attribute konfigurieren** wird geöffnet. Diese Tabelle enthält die Optionen zum Zuordnen von Attribute von Active Directory-Domänendienste zu Attributfelder für Skype für Business Server 2015 und welche Benutzer ein-oder ausschließen in Adressbuchdienst-Dateien basierend auf bestimmten Attribut Filter angeben.</span><span class="sxs-lookup"><span data-stu-id="3940b-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="3940b-151">Außerdem bietet die Optionen zum Anpassen der Wert der Telefonnummer an, die in der Adressbuch-Datei eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="3940b-152">Die Option **Wiederherstellen** kann Administratoren Adressbuchdienst Standardwerte wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3940b-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="3940b-153">Erneut Zuordnung von Active Directory-Attributen zu verschiedenen OC Feldnamen wird nur Arbeit für Address Book Dateidownload und wird vom Adressbuch-Webabfragedienst nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3940b-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-154">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-154">Output</span></span>

<span data-ttu-id="3940b-155">ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3940b-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="3940b-156">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-156">Purpose</span></span>

<span data-ttu-id="3940b-157">ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen von Skype für Business Server 2015 Adressbuchdienst.</span><span class="sxs-lookup"><span data-stu-id="3940b-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-158">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="3940b-159">Computer</span><span class="sxs-lookup"><span data-stu-id="3940b-159">Computer</span></span>

<span data-ttu-id="3940b-160">ABSConfig kann nur von einer Domäne gehörenden Computer ausgeführt werden, Skype für Business Server 2015 installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="3940b-161">Im Fall von Skype für Business Server 2015, Enterprise Edition, kann dieses Tool auf jedem Front-End-Server ausgeführt werden, die den Adressbuchdienst während des Setups aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3940b-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="3940b-162">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="3940b-162">Network</span></span>

<span data-ttu-id="3940b-163">Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3940b-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="3940b-164">Software</span><span class="sxs-lookup"><span data-stu-id="3940b-164">Software</span></span>

<span data-ttu-id="3940b-165">Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert werden:</span><span class="sxs-lookup"><span data-stu-id="3940b-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="3940b-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3940b-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="3940b-167">Benutzer</span><span class="sxs-lookup"><span data-stu-id="3940b-167">Users</span></span>

<span data-ttu-id="3940b-168">Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype für Business Server 2015 Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3940b-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-169">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-169">Examples</span></span>

<span data-ttu-id="3940b-p108">ABSConfig kann durch Eingeben von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.</span><span class="sxs-lookup"><span data-stu-id="3940b-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

![Das Tool ABSConfig.exe](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="3940b-173">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-173">Summary</span></span>

<span data-ttu-id="3940b-174">Das Tool ABSConfig bietet Administratoren ein schnelles und einfach zu verwendenden Tools zum Anpassen von Skype für Business Server 2015 Adressbuchdienst.</span><span class="sxs-lookup"><span data-stu-id="3940b-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="3940b-175">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="3940b-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="3940b-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-176"></span></span>

<span data-ttu-id="3940b-177">Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Elemente anzeigen:</span><span class="sxs-lookup"><span data-stu-id="3940b-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="3940b-178">Alle konfigurierten Skype für Business Server 2015 Bandbreitenrichtlinie Services (Authentifizierung und Core) in der Topologie</span><span class="sxs-lookup"><span data-stu-id="3940b-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="3940b-179">Die Verbindungen, die jeder Dienst mit anderen Bandbreiten-Richtliniendiensten und Edgeservern herstellt</span><span class="sxs-lookup"><span data-stu-id="3940b-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="3940b-180">Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die von den einzelnen Bandbreiten-Richtliniendiensten gemeldete Echtzeit-Bandbreitennutzung</span><span class="sxs-lookup"><span data-stu-id="3940b-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="3940b-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-181">Description</span></span>

<span data-ttu-id="3940b-p109">Das Tool Bandwidth Policy Service Monitor ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Administratoren starten das Tool durch Ausführen der Datei „PDPMonUI.exe“.</span><span class="sxs-lookup"><span data-stu-id="3940b-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="3940b-p110">Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreiten-Richtliniendienste in der Topologie zu ermitteln. Nach Abschluss der anfänglichen Aktualisierung wird der linke Bereich im Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.</span><span class="sxs-lookup"><span data-stu-id="3940b-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="3940b-p111">Wenn Administratoren einen bestimmten Bandbreiten-Richtliniendienst auswählen, werden im rechten Bereich die Informationen zu dem jeweiligen Dienst angezeigt. Dieser Bereich enthält außerdem zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="3940b-188">Registerkarte „Machine Info“</span><span class="sxs-lookup"><span data-stu-id="3940b-188">Machine Info Tab</span></span>

<span data-ttu-id="3940b-189">Auf der Registerkarte **Machine Info** werden die Details des ausgewählten Bandbreiten-Richtliniendiensts angezeigt sowie die Liste und die Zustände aller Verbindungen, die der ausgewählte Bandbreiten-Richtliniendienst mit anderen Diensten herstellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="3940b-190">Registerkarte „Topology Info“</span><span class="sxs-lookup"><span data-stu-id="3940b-190">Topology Info Tab</span></span>

<span data-ttu-id="3940b-p112">Auf der Registerkarte **Topology Info** wird eine Liste aller Verbindungen angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Bandbreitenkapazität für Audio und Video angezeigt. Zusätzlich wird die zurzeit verwendete Bandbreite in KB/s und als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierungen zum Hervorheben von Verbindungen, deren Nutzung fast der Kapazität entspricht. So können Administratoren solche Verbindungen schnell erkennen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="3940b-195">Wenn das Tool Bandbreite Richtlinie Service Monitor Fehler beim Verbinden mit den konfigurierten Bandbreitenrichtlinie Dienste auftritt, wird nicht die Informationen in den **Computer Info** und die **Topologie Info** Registerkarten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="3940b-196">Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht.</span><span class="sxs-lookup"><span data-stu-id="3940b-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="3940b-197">In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="3940b-198">Beide Registerkarten enthalten einen Zeitstempel **Last Updated**, mit dessen Hilfe Administratoren bestimmen können, wann die Daten für einen bestimmten Bandbreiten-Richtliniendienst zum letzten Mal aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3940b-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-199">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-199">Output</span></span>

<span data-ttu-id="3940b-200">Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt auf der grafischen Hauptbenutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="3940b-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-201">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-201">Purpose</span></span>

<span data-ttu-id="3940b-p114">Das Tool Bandwidth Policy Service Monitor soll Administratoren Einblick in den Zustand jedes Bandbreiten-Richtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeit-Bandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-204">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-204">Requirements</span></span>

<span data-ttu-id="3940b-205">Das Tool Bandbreite Richtlinie Service Monitor muss auf einem Computer ausgeführt werden, die Bestandteil der Skype für Business Server-Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="3940b-206">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-206">Summary</span></span>

<span data-ttu-id="3940b-207">Das Tool Bandwidth Policy Service Monitor kann eine wertvolle Ressource für Administratoren sein, um den Zustand aller Bandbreiten-Richtliniendienste in der Topologie untersuchen zu können. Wichtiger noch ist, dass die Echtzeit-Bandbreitenauslastung für die Verbindungen ermittelt werden kann, die in den Netzwerkkonfigurationseinstellungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="3940b-208">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="3940b-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="3940b-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-209"></span></span>

<span data-ttu-id="3940b-p115">Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Muster des Bandbreitenverbrauchs analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-212">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-212">Description</span></span>

<span data-ttu-id="3940b-p116">Bandwidth Utilization Analyzer ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Dieses Tool erzeugt Berichte speziell für die Audionutzung über das Netzwerk und hilft bei der Kapazitätsplanung. Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-216">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-216">Output</span></span>

<span data-ttu-id="3940b-217">Bandwidth Utilization Analyzer bietet grafische Diagramme der Bandbreitenkapazität und -auslastung durch Audio für alle WAN-Verbindungen, die im System konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-218">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-218">Purpose</span></span>

<span data-ttu-id="3940b-219">In jeder Sprach- und Videodaten Bereitstellung ist es wichtig, überwachen und verstehen, die Entwicklung der Auslastung der Bandbreite der Mediendatenverkehr über das Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="3940b-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="3940b-220">Genau dies ermöglicht das Tool Bandwidth Utilization Analyzer Administratoren.</span><span class="sxs-lookup"><span data-stu-id="3940b-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="3940b-221">Das Tool bietet folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="3940b-221">This tool does the following:</span></span>

- <span data-ttu-id="3940b-222">Erzeugung spezifischer Berichte für die Audionutzung über das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="3940b-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="3940b-223">Hilfe bei einer effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="3940b-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3940b-224">Bandwidth Utilization Analyzer kann aus Bandbreitenkapazitäts- und -auslastungsberichten die folgenden grafischen Diagramme generieren:</span><span class="sxs-lookup"><span data-stu-id="3940b-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="3940b-225">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="3940b-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="3940b-226">Gefiltert nach ausgewählten WAN-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="3940b-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="3940b-227">Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="3940b-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="3940b-228">Gefiltert nach WAN-Verbindungen, die nicht die gesamte bereitgestellte Bandbreite nutzen</span><span class="sxs-lookup"><span data-stu-id="3940b-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="3940b-229">Gefiltert nach WAN-Verbindungen, die kritische Grenzwerte erreicht haben (eine Bandbreitenauslastung von mehr als 90 % der Bandbreitenkapazität der WAN-Verbindung)</span><span class="sxs-lookup"><span data-stu-id="3940b-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="3940b-230">Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts</span><span class="sxs-lookup"><span data-stu-id="3940b-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="3940b-231">Gefiltert nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="3940b-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="3940b-232">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3940b-232">Applications</span></span>

<span data-ttu-id="3940b-233">Bandwidth Utilization Analyzer besteht aus den zwei folgenden Anwendungen (Tools):</span><span class="sxs-lookup"><span data-stu-id="3940b-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="3940b-234">**WanLinkLogCollector.exe** dieses Tool ermöglicht die Benutzer die erforderliche Informationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="3940b-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="3940b-235">**BandwidthUtilizationAnalyzer.xlsm** Bericht für eine Microsoft Excel-Kalkulationstabelle wird durch WanLinkLogCollector.exe automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="3940b-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="3940b-236">Mit dieser Anwendung können Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anwenden.</span><span class="sxs-lookup"><span data-stu-id="3940b-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="3940b-237">Phasen der Verwendung von Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="3940b-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3940b-238">Es gibt zwei Phasen bei der Verwendung von Bandwidth Utilization Analyzer:</span><span class="sxs-lookup"><span data-stu-id="3940b-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="3940b-239">Erfassen von Protokollen mithilfe von „WanLinkLogCollector.exe“</span><span class="sxs-lookup"><span data-stu-id="3940b-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="3940b-240">Anpassen von Berichten mithilfe von „BandwidthUtilizationAnalyzer.xlsm“</span><span class="sxs-lookup"><span data-stu-id="3940b-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3940b-241">„BandwidthUtilizationAnalyzer.xlsm“ sollte auf keinen Fall manuell von Endbenutzern gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="3940b-242">Starten von Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="3940b-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3940b-243">Starten Sie „WanLinkLogCollector.exe“ an der Eingabeaufforderung oder mithilfe von Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="3940b-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="3940b-244">**Verwenden von „WanLinkLogCollector.exe“**</span><span class="sxs-lookup"><span data-stu-id="3940b-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="3940b-245">„WanLinkLogCollector.exe“ wird in drei Schritten verwendet:</span><span class="sxs-lookup"><span data-stu-id="3940b-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="3940b-246">**Melden Sie sich die Zeitachse** Geben Sie den Zeitplan an, dem der Bericht für generiert werden soll</span><span class="sxs-lookup"><span data-stu-id="3940b-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="3940b-247">**Geben Sie die Dateiverzeichnisse** Bereitstellen von Informationen zum Dateispeicherort</span><span class="sxs-lookup"><span data-stu-id="3940b-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="3940b-248">**Sammeln Sie die Protokolle und starten Sie den Bericht-viewer** Führen Sie den Befehl zum Generieren von Berichten</span><span class="sxs-lookup"><span data-stu-id="3940b-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="3940b-249">Schritt 1 – Protokollieren des Zeitraums</span><span class="sxs-lookup"><span data-stu-id="3940b-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="3940b-250">Durch die Protokollierung des Zeitraums können die Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben. </span><span class="sxs-lookup"><span data-stu-id="3940b-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="3940b-251">**Startdatum** Dies ist das Startdatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 1. August 2010.</span><span class="sxs-lookup"><span data-stu-id="3940b-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="3940b-252">**Enddatum** Dies ist das Enddatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 30. September 2010.</span><span class="sxs-lookup"><span data-stu-id="3940b-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Start- und Enddatum in der Bandbreitennutzung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="3940b-254">Schritt 2 – Angeben der Dateiverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="3940b-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="3940b-255">Die folgenden Dateiverzeichnisse können von den Benutzern wie gezeigt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="3940b-256">**Speicherort für Protokolldateien Server** Der Ordnerspeicherort, in dem die Bandbreite Richtlinie Serverprotokolle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="3940b-257">Dies ist in der Regel in \<Dateiserver\>\\< Choice der FE\>\AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="3940b-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="3940b-258">**Temporären Dateispeicherort** Am temporären Dateispeicherort, in dem temporäre Dateien gespeichert sind, während der Bericht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

![Dateiverzeichnisse in der Bandbreitennutzungsanalyse](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> <span data-ttu-id="3940b-260">Stellen Sie sicher, dass den Benutzern des Tools ausreichender Dateizugriff auf den Speicherort der Serverprotokolle und der temporären Dateien gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="3940b-261">Schritt 3 – Erfassen der Protokolle und Starten der Berichtanzeige</span><span class="sxs-lookup"><span data-stu-id="3940b-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="3940b-p120">Um die Protokolle zu erfassen und die Berichtanzeige zu starten, klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.</span><span class="sxs-lookup"><span data-stu-id="3940b-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

![Sammeln von Daten in der Bandbreitennutzungsanalyse](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="3940b-265">Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-265">When the input validation is successful, the message shown below is displayed.</span></span>

![In Protokollen erfasste Benachrichtigung im Bandbreitendienstprogramm](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="3940b-p121">Klicken Sie auf **OK**. „BandwidthUtilizationAnalyzer.xlsm“ wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**.</span><span class="sxs-lookup"><span data-stu-id="3940b-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="3940b-271">Verwenden von „BandwidthUtilizationAnalyzer.xlsm“</span><span class="sxs-lookup"><span data-stu-id="3940b-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="3940b-272">Wenn „BandwidthUtilizationAnalyzer.xlsm“ automatisch gestartet wurde, klicken Sie wie unten gezeigt auf **Refresh**.</span><span class="sxs-lookup"><span data-stu-id="3940b-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="3940b-p122">Wenn ein Dateiordner geöffnet wird, wählen Sie die Datei „consolidated.csv“ an dem Speicherort aus, der in dem unten gezeigten Meldungsfeld angegeben ist. Dort wird außerdem der Speicherort **C:\Temp** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>

     ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="3940b-277">Klicken Sie auf **Import**.</span><span class="sxs-lookup"><span data-stu-id="3940b-277">Click **Import**.</span></span>

4. <span data-ttu-id="3940b-p123">Das grafische Diagramm wird automatisch generiert. Es ist verfügbar, sobald der Hintergrundaktivitäts-Mauszeiger nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>

     ![Anwenden von Filtern in der Berichtsansicht](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="3940b-281">Anwenden von Filtern auf die Berichtsansicht</span><span class="sxs-lookup"><span data-stu-id="3940b-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="3940b-282">Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden nachfolgend beschrieben:</span><span class="sxs-lookup"><span data-stu-id="3940b-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Anwenden von Filtern in der Berichtsansicht](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="3940b-284">**Name** Filtern nach WAN-Verbindungen (der Filter befindet sich rechts von der Grafik). Das Präfix identifiziert die folgenden Verbindungstypen, siehe im vertikalen (blauen) Feld:</span><span class="sxs-lookup"><span data-stu-id="3940b-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

  - <span data-ttu-id="3940b-285">**S Site** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="3940b-285">**S Site** The WAN link from a network site to a network region</span></span>

  - <span data-ttu-id="3940b-286">**IS Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="3940b-286">**IS Inter-Site** The WAN link between two network sites</span></span>

  - <span data-ttu-id="3940b-287">**R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="3940b-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="3940b-288">**Exceeded limit** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung die Bandbreitenkapazität übersteigt</span><span class="sxs-lookup"><span data-stu-id="3940b-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="3940b-289">**Critical levels** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mindestens 90 % der Bandbreitenkapazität erreicht hat</span><span class="sxs-lookup"><span data-stu-id="3940b-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="3940b-290">**Under-utilized** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="3940b-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="3940b-291">**Link type** Filtern nach den folgenden WAN-Verbindungstypen:</span><span class="sxs-lookup"><span data-stu-id="3940b-291">**Link type** Filter by the following WAN links types:</span></span>

  - <span data-ttu-id="3940b-292">
            Typ **Network site**</span><span class="sxs-lookup"><span data-stu-id="3940b-292">**Network site** type</span></span>

  - <span data-ttu-id="3940b-293">
            Typ **Inter-site**</span><span class="sxs-lookup"><span data-stu-id="3940b-293">**Inter-site** type</span></span>

  - <span data-ttu-id="3940b-294">
            Typ **Inter-Region link**</span><span class="sxs-lookup"><span data-stu-id="3940b-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="3940b-295">**Region** Filtern nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="3940b-295">**Region** Filter by network region</span></span>

<span data-ttu-id="3940b-296">Die folgenden Abbildungen zeigen die oben beschriebenen Filter.</span><span class="sxs-lookup"><span data-stu-id="3940b-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="3940b-p124">Filtern nach **Name**. Wählen Sie die Liste der Verbindungen aus, die in dem Diagramm angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

![Filtern nach Name in BandwidthUtilizationAnalyzer](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="3940b-p125">Filtern nach **Exceeded limit**. Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p125">Filter by **Exceeded limit**. Select **True** to enforce the filter.</span></span>

![Filtern nach Exceeded Limit](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="3940b-p126">Filtern nach **Critical levels**. Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p126">Filter by **Critical levels**. Select **True** to enforce the filter.</span></span>

![Filtern nach Critical Levels](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="3940b-p127">Filtern nach **Under utilized**. Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p127">Filter by **Under utilized**. Select **True** to enforce the filter.</span></span>

![Filtern nach Under Utilized](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="3940b-p128">Filtern nach **Link Type**. Wählen Sie die Typen aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p128">Filter by **Link Type**. Select the type or types that need to be displayed.</span></span>

![Filtern nach Link Type](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="3940b-p129">Filtern nach **Region**. Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p129">Filter by **Region**. Select a list of regions whose links need to be displayed.</span></span>

![Filtern nach Region](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="3940b-315">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-315">Requirements</span></span>

- <span data-ttu-id="3940b-316">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="3940b-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="3940b-317">Microsoft Excel 2010 oder Excel 2007</span><span class="sxs-lookup"><span data-stu-id="3940b-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="3940b-318">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-318">Summary</span></span>

<span data-ttu-id="3940b-p130">Bandwidth Utilization Analyzer wird verwendet, um die Bandbreitenauslastung durch Audio für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann auch die Bandbreitenauslastung durch Video im Netzwerk dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="3940b-321">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="3940b-321">Call Parkometer</span></span>
<span data-ttu-id="3940b-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-322"></span></span>

<span data-ttu-id="3940b-323">Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Datenbank mit den Orbits der geparkten Anrufe ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3940b-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-324">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-324">Description</span></span>

<span data-ttu-id="3940b-325">Call Parkometer ist ein Tool zum Nachverfolgen der zurzeit geparkten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="3940b-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="3940b-326">Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS).</span><span class="sxs-lookup"><span data-stu-id="3940b-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="3940b-327">Dieses Command-Line Tool bietet Lese- und Schreibzugriff auf den Orbit CPS SQL Server-Datenbank von einem Computer lokale oder Remote verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="3940b-p132">Alle Optionen schließen sich gegenseitig aus. Befehlszeilensyntax:</span><span class="sxs-lookup"><span data-stu-id="3940b-p132">All options are mutually exclusive. Command-line syntax is as follows:</span></span>

- <span data-ttu-id="3940b-330">**o -** Parameter – alle Bereiche, die für diesen Pool konfiguriert orbit Listen.</span><span class="sxs-lookup"><span data-stu-id="3940b-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="3940b-331">**-n** -Parameter – alle derzeit verwendeten Listen Orbits in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="3940b-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="3940b-332">Folgende Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3940b-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3940b-333">Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person</span><span class="sxs-lookup"><span data-stu-id="3940b-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="3940b-334">Der Hostname des Anrufparkservers, auf dem der Anruf geparkt ist</span><span class="sxs-lookup"><span data-stu-id="3940b-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="3940b-335">Der Zeitstempel, aus dem hervorgeht, wann der Anruf geparkt wurde</span><span class="sxs-lookup"><span data-stu-id="3940b-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="3940b-336">Parameter **-f** – die Anzahl der derzeit kostenlose Orbits im Pool aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="3940b-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="3940b-337">**R - \<n\> ** Parameter – Listet die \<n\> letzten geparkt Anrufe.</span><span class="sxs-lookup"><span data-stu-id="3940b-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="3940b-338">Folgende Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3940b-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="3940b-339">SIP-URI der geparkten Person</span><span class="sxs-lookup"><span data-stu-id="3940b-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="3940b-340">SIP-URI der parkenden Person</span><span class="sxs-lookup"><span data-stu-id="3940b-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="3940b-341">Der Hostname des Anrufparkservers, auf dem der Anruf geparkt wurde</span><span class="sxs-lookup"><span data-stu-id="3940b-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="3940b-342">Der Zeitstempel, aus dem hervorgeht, wann der Anruf herangeholt oder abgebrochen wurde</span><span class="sxs-lookup"><span data-stu-id="3940b-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="3940b-343">**-t\<n\> ** Parameter - getestet, reservieren eine Orbit in die Datenbank Auswahl von der zugewiesenen orbitnummern anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-344">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-344">Output</span></span>

<span data-ttu-id="3940b-345">Abhängig von den Eingabeparametern, die an der Eingabeaufforderung angegeben werden, zeigt Call Parkometer folgende Ausgaben an:</span><span class="sxs-lookup"><span data-stu-id="3940b-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="3940b-346">Alle für diesen Pool konfigurierten Orbitbereiche</span><span class="sxs-lookup"><span data-stu-id="3940b-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="3940b-347">Zurzeit geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="3940b-347">Currently parked calls</span></span>

- <span data-ttu-id="3940b-348">Anzahl der freien (verfügbaren) Orbits</span><span class="sxs-lookup"><span data-stu-id="3940b-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="3940b-349">Zuletzt geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="3940b-349">Recently parked calls</span></span>

- <span data-ttu-id="3940b-350">Für das Testen einheitlicher und zufälliger Orbitwerte reservierte Orbits</span><span class="sxs-lookup"><span data-stu-id="3940b-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-351">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-351">Purpose</span></span>

<span data-ttu-id="3940b-p135">Das Anrufparkserver-Tool soll Befehlszeilenzugriff auf die Anrufparkserver-Datenbank ermöglichen. Administratoren können die Anrufparkserver-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-354">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-354">Requirements</span></span>

<span data-ttu-id="3940b-355">Wenn das Tool auf dem gleichen Computer wie der Anrufparkserver ausgeführt wird, gelten keine Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="3940b-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="3940b-356">Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die SQL Server-Datenbank von Skype für Business Server 2015 verwendet Remotezugriff konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="3940b-357">Anruf Parkometer muss mit einer SQL Server-Datenbank-Verbindungszeichenfolge für die Verbindung zu des Pools SQL Server konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="3940b-358">Diese SQL Server-Datenbank-Verbindungszeichenfolge ist in der Konfigurationsdatei **parkometer.exe.config**definiert. Es muss im gleichen Verzeichnis platziert werden parkometer.exe gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="3940b-359">Die folgende XML-Datei ist ein Beispiel für eine parkometer.exe.config. Die Parameter, die konfiguriert werden müssen sind Benutzernamen ein (beispielsweise Mydomain\Administrator), Kennwort (z. B. Mypassword) und Hostnamen (z. B. "Myserver").</span><span class="sxs-lookup"><span data-stu-id="3940b-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
   <add key="SQL" value="server=myserver\RTC;
database=cpsdyn;
User Id=mydomain\Administrator;
Password=mypassword.;
Integrated Security=false;"/>
  </appSettings>
</configuration>
```

### <a name="examples"></a><span data-ttu-id="3940b-360">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-360">Examples</span></span>

<span data-ttu-id="3940b-361">Bereiche für den anrufparkorbit bereitgestellt: der -o Parameter Listet alle orbitbereiche, die für diesen Pool konfiguriert sind, siehe</span><span class="sxs-lookup"><span data-stu-id="3940b-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Orbitbereiche in der Anrufparkuhr](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="3940b-363">Derzeit geparkt Anrufe: - n-Parameter werden alle derzeit verwendeten Orbits für diesen Pool aufgelistet, siehe</span><span class="sxs-lookup"><span data-stu-id="3940b-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Aktuell in der Anrufparkuhr geparkte Anrufe](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="3940b-365">Anzahl der freien Orbits: der Parameter-f Listet die Anzahl der derzeit kostenlose Orbits im Pool, siehe</span><span class="sxs-lookup"><span data-stu-id="3940b-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Freie Orbitbereiche in der Anrufparkuhr](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="3940b-367">Kürzlich geparkt Anrufe: R - \<n\> Parameterlisten der \<n\> letzten Anrufe geparkt, siehe</span><span class="sxs-lookup"><span data-stu-id="3940b-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Zuletzt in der Anrufparkuhr geparkte Anrufe](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="3940b-369">Testen der Orbit Reservierung: -t \<n\> Parameter getestet, reservieren eine orbitbereiche in der Datenbank, siehe</span><span class="sxs-lookup"><span data-stu-id="3940b-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testorbitreservierungen in der Anrufparkuhr](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="3940b-371">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-371">Summary</span></span>

<span data-ttu-id="3940b-372">Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="3940b-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="3940b-373">DBAnalyze</span></span>
<span data-ttu-id="3940b-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-374"></span></span>

### <a name="description"></a><span data-ttu-id="3940b-375">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-375">Description</span></span>

<span data-ttu-id="3940b-376">Dbanalyze aus ist ein Befehlszeilentool, mit dem Administratoren die Analyseberichte über die Skype für Business Server 2015 Datenbanken zu erfassen kann.</span><span class="sxs-lookup"><span data-stu-id="3940b-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="3940b-377">DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:</span><span class="sxs-lookup"><span data-stu-id="3940b-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="3940b-378">**Diagnose-Modus** Erstellt einen Bericht, enthält Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten- und Protokolldateien Dateigrößen, die Sicherung im letzten Kontakt Verteilung auf Servern mit Microsoft Office Communications Server, die Durchschnittliche Anzahl von Berechtigungen, Kontakte, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, nicht ordnungsgemäß verwaltete Benutzer, die Benutzer, die weitergeleitet werden können, werden die durchschnittliche Anzahl der Konferenzen pro Benutzer, geplante Konferenzen und aktiven Konferenzen organisiert, und die Version der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3940b-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3940b-379">Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="3940b-380">**Datenmodus Benutzer** Berichte Kontakt, Container, Abonnements, Publikation, Berechtigung und Kontaktgruppe Daten für einen angegebenen Benutzer oder für Benutzer, die diesen Benutzer in ihre Kontakt- und Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="3940b-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="3940b-381">Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="3940b-382">**Konferenzmodus** Berichte detaillierte Daten zu einer bestimmten Konferenz, einschließlich aller Zeit planen Details zu der Konferenz, die Liste eingeladenen Benutzer, die Liste der Medientypen zulässig für die Konferenz, aktive MCUs (multipoint Control Einheiten), die Liste der aktiven Teilnehmer und jeweils Signalisierung Zustand des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="3940b-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="3940b-383">**Decodieren Besprechungs-ID** Decodiert ein öffentliches Telefonfestnetz (PSTN) meeting-ID, die durch die Option **/pstnid** angegeben wird, aber stellt keine Verbindung zum Back-End ausführliche Informationen her.</span><span class="sxs-lookup"><span data-stu-id="3940b-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="3940b-384">**Auflösen der Konferenz** Decodiert eine PSTN-besprechungs-ID, die durch die Option **/pstnid** angegeben ist und zeigt Informationen über die Konferenz von der ID angegeben</span><span class="sxs-lookup"><span data-stu-id="3940b-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="3940b-385">**MCUs-Modus** ID, Medientyp, URL, Heartbeat-Status, Konferenz laden und Teilnehmer Load-Berichte für jede MCU im Pool.</span><span class="sxs-lookup"><span data-stu-id="3940b-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="3940b-386">**Festplatten Fragmentierung-Modus** Zeigt den Fragmentierung Status aller Festplatten.</span><span class="sxs-lookup"><span data-stu-id="3940b-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="3940b-p139">Dieses Tool kann zum Diagnostizieren verschiedener Probleme verwendet werden oder Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A verwalteten Benutzer auf Server B verwaltete Benutzer als Kontakte wählen, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen den Servern zu verringern.</span><span class="sxs-lookup"><span data-stu-id="3940b-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-389">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-389">Output</span></span>

<span data-ttu-id="3940b-390">Dieses Tool gibt vordefinierte Berichte über die Skype für Business Server 2015 Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="3940b-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="3940b-391">**Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="3940b-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-392">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-392">Purpose</span></span>

<span data-ttu-id="3940b-393">Um Dbanalyze.exe zu installieren, kopieren Sie sie in einen lokalen Ordner, und führen Sie das Tool.</span><span class="sxs-lookup"><span data-stu-id="3940b-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="3940b-394">Wenn das Tool verwenden möchten, führen Sie den folgenden Befehl an der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="3940b-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="3940b-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Die Beschreibungen für die Befehlszeilenoptionen sind unten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3940b-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Befehlszeilenoptionen für Dbanalyze.exe](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="3940b-397">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-397">Requirements</span></span>

 <span data-ttu-id="3940b-398">**Computer** Dbanalyze aus kann nur von einer Domäne gehörenden Computer ausgeführt werden, Skype für Business Server 2015 installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="3940b-399">**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="3940b-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="3940b-400">**Software** Skype für Business Server 2015 Softwarekomponenten muss installiert sein, vor dem Ausführen von Dbanalyze aus.</span><span class="sxs-lookup"><span data-stu-id="3940b-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="3940b-401">**Benutzer** Die nachstehende Tabelle zeigt den Administratoren besitzen die erforderlichen Berechtigungen zum Skype für Business Server 2015 Datenbanken zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3940b-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Berechtigungstabelle für Dbanalyze.exe](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="3940b-403">Für den **/report:disk**-Modus ist ein lokales Administratorkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3940b-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-404">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-404">Examples</span></span>

<span data-ttu-id="3940b-405">Hier sind Beispiele für gültige „Dbanalyze.exe“-Befehle:</span><span class="sxs-lookup"><span data-stu-id="3940b-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="3940b-406">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-406">Summary</span></span>

<span data-ttu-id="3940b-407">DBAnalyzer bietet Administratoren eine schnelle und einfache Skype für Business Server 2015 Datenbanken zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="3940b-408">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="3940b-408">Import Storage Service Data</span></span>
<span data-ttu-id="3940b-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-409"></span></span>

<span data-ttu-id="3940b-410">Mit dem Resource Kit-Tool „ImportStorageServiceData“ können Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, wieder zurück in den Speicherdienst importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-411">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-411">Description</span></span>

<span data-ttu-id="3940b-412">Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein.</span><span class="sxs-lookup"><span data-stu-id="3940b-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="3940b-413">Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets „StorageServiceFullFlush“ (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein.</span><span class="sxs-lookup"><span data-stu-id="3940b-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="3940b-414">Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollen Wenn keines der Datenbankgröße Storage Service (LYSS) auf den front-Ends ist über die normale Ebene, da dadurch wahrscheinlich nur weitere Daten wieder exportiert werden sollen verursacht. Darüber hinaus sollte die Fehler können, die die Speicherung Service Warteschlange beigetragen haben wachsen verursacht Probleme zunächst (zum Beispiel Exchange Endpunkt Fehler, Netzwerkprobleme oder andere Probleme) aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="3940b-415">**Szenario 1:** während des Failovers Pool Dateien möglicherweise geleert Skalieren von Speicherdienst für jeden Front-End.</span><span class="sxs-lookup"><span data-stu-id="3940b-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="3940b-416">Nach dem Failover abgeschlossen ist, sollte das Tool ausgeführt werden, um die Daten erneut importieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="3940b-417">**Szenario 2:** Daten wird geleert automatisch jeden Tag oder als Reaktion auf Speicherdienst Datenbank überschreiten bestimmte Schwellenwerte Größe (z. B. 60 % 80 %, 90 % voll).</span><span class="sxs-lookup"><span data-stu-id="3940b-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="3940b-418">Diese Daten automatisch wurden sollten routinemäßig erneut vom Administrator importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="3940b-419">In der obigen Situation Wenn das monitoring SCOM nicht bereitgestellt wird, sind Ereignisse für Skype für Business Server Speicherdienst im Zusammenhang mit Daten aus der Speicherdienst geleert wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="3940b-420">Ereignis-IDs der 32075 (vollständige Schreibvorgang wurde gestartet wird), 32076 (vollständige Flush abgeschlossen ist), 32082 (Wartung Level flush gestartet), 32083 (zu leeren vollständige Wartung Level), 32089 (Fehler aufgrund der Datenbank füllen leeren).</span><span class="sxs-lookup"><span data-stu-id="3940b-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="3940b-421">Beachten Sie, dass diese Ereignis-Ids mit der RTM-Version übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3940b-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="3940b-422">Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien, die Sie übertragen wurden. Diese Daten sollten routinemäßig dieses Tool back beispielsweise einmal pro Woche mit importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="3940b-423">Für die Version Onlinedienst Wenn Health monitoring Pack für SCOM für Skype für Business Server bereitgestellt wird, sind neue Warnungen, die möglicherweise ausgelöst werden die bitten Sie den Administrator, um die Daten wurden wieder Speicherdienst erneutes importieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="3940b-424">Im Ereignisprotokoll wird ein entsprechendes Ereignis vorhanden sein, auf dem Front-End-Server, der Warnung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3940b-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="3940b-425">Das Ereignis erhalten eine Beschreibung des Pfads zur übergeordneten unter dem die Daten wurden Dateien befinden, sind sowie wie viele Dateien vorhanden sind, die die Warnungen Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3940b-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="3940b-426">Die Warnung Kriterium darstellen, ist es wurden X oder mehrere Dateien unter dem bestimmten übergeordneten Pfad die sind am wenigsten Y Tage (wobei X und Y sind innerhalb der StorageService Voreinstellung jedoch überschrieben werden kann, indem Sie die Datei APPCONFIG ändern.) Zwei Beispiele für Ereignisse, die die Integrität Warnung ausgelöst werden können, mit dem Unterschied, deren übergeordneten Pfad nachfolgend.</span><span class="sxs-lookup"><span data-stu-id="3940b-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="3940b-427">Eine Möglichkeit ist unter Web-Service-Dateifreigabe, während die anderen Möglichkeit das lokale Verzeichnis Anwendungsdaten von jedem Front-End ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="3940b-428">(beispielsweise c:\ProgramData\Microsoft\Skype für Business Server 2015\StorageService).</span><span class="sxs-lookup"><span data-stu-id="3940b-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="3940b-429">Der Administrator wird dieses Tool Reskit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="3940b-430">Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="3940b-431">Wir empfehlen die Ausführung dieses Tools, wenn die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="3940b-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="3940b-432">Darüber hinaus kann dieses Tool zwei bis drei Minuten für den Import einer Datendatei benötigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="3940b-433">Denken Sie hieran, wenn Sie die voraussichtliche Ausführungsdauer des Tools schätzen.</span><span class="sxs-lookup"><span data-stu-id="3940b-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="3940b-434">Die von dem Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="3940b-435">Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB übersteigen kann.</span><span class="sxs-lookup"><span data-stu-id="3940b-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Beispielereignisse für das Ereignisprotokoll des Speicherservers](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="3940b-437">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-437">Requirements</span></span>

<span data-ttu-id="3940b-438">Installieren Sie die Skype für Business Server 2015 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="3940b-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="3940b-439">Das Tool wird ausgeführt auf Domäne gehörenden Computer, auf dem Skype für Business Server und Skype für Business Server-Verwaltungsshell installiert.</span><span class="sxs-lookup"><span data-stu-id="3940b-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="3940b-440">Das Tool verwendet ein Cmdlet aus der-Verwaltungsshell auf um allen Front-End-Servern im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="3940b-441">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, die die **RtcLocal** -Datenbank installiert hat.</span><span class="sxs-lookup"><span data-stu-id="3940b-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="3940b-442">Diese Datenbank wird vom Programm verwendet, um den Speicherort der WEBSERVICE Dateifreigabe für den Pool abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3940b-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="3940b-443">Darüber hinaus muss vor der Verwendung des Tools, jedem Front-End-Server aktivieren, Windows PowerShell-Remoting mit **Enable-psremoting sieht** auf jedem Front-End-Server als auch den Computer aus, dem das Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="3940b-444">Andernfalls werden von diesem Tool remote Windows PowerShell-Befehle fehl.</span><span class="sxs-lookup"><span data-stu-id="3940b-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="3940b-445">Windows PowerShell-Remoting kann deaktiviert werden auf allen Front-End-Servern im Pool nachdem der Importvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="3940b-446">Schließlich muss das Tool aufrufen Anmeldeinformationen Lese-/Schreibberechtigung für die Webservice-Dateifreigabe für den Pool verfügen, die sie für dieses Tool ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="3940b-447">Andernfalls wird das Tool Berechtigung e/a-Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="3940b-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="3940b-448">Unter Windows Server 2012 ist Windows PowerShell-Remoting standardmäßig, jedoch nicht auf dem Betriebssystem Windows Server 2008 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3940b-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-449">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-449">Examples</span></span>

```
>  C:\StorageService>ImportStorageServiceData.exe
Description:
This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
Additional Options:
-Verbose                    : Turn verbose output on.

-StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )

-FileSharePath              : Import only all data from just under the UNC path specified.

ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
Using NetNamedPipeBinding...
OnTopologyChanged Event received
Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService

Front Ends:
server.vdomain.com
server2.vdomain.com
server1.vdomain.com
server3.vdomain.com
Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
# Files found: 8
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
Items deserialized: 20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
3832e4__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
86684d3832e4__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
ain.com, queueItems=20

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
287dd6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
b46a42287dd6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml

Items deserialized: 20

[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1

All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
d251e6__0.xml

All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
e08a15d251e6__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0

Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=1
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
17c220__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
949ff817c220__0.xml

Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml

Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
6d5317__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
749be66d5317__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
Items deserialized: 20
[cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
ain.com, queueItems=20
All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
86b565__0.xml
All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
657eda86b565__0.xml
Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
vices-1\StorageService
Importing files for: server.vdomain.com
No files founds.
Importing files for: server2.vdomain.com
No files founds.
Importing files for: server1.vdomain.com
No files founds.
Importing files for: server3.vdomain.com
No files founds.
Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
Log20120910_1609SS
Tool has finished execution.
>  C:\StorageService>
```

## <a name="lcssync"></a><span data-ttu-id="3940b-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="3940b-450">LCSSync</span></span>
<span data-ttu-id="3940b-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-451"></span></span>

<span data-ttu-id="3940b-452">Das Tool LCSSync unterstützt Skype für Business Server 2015 Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="3940b-453">Dieses Tool dient zum Synchronisieren von Benutzern und Gruppen aus verschiedenen Benutzergesamtstrukturen als Active Directory-Domänendienste-Kontaktobjekt und der zentralen Gesamtstruktur, in Skype für Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-454">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-454">Description</span></span>

 <span data-ttu-id="3940b-455">LCSSync Verwendungsmöglichkeiten der synchronisierten Active Directory-Domänendienste Kontaktobjekte in der zentralen Gesamtstruktur so aktivieren Benutzer für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="3940b-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="3940b-456">Um das einmalige Anmelden zu ermöglichen, muss das primäre Benutzerkonto das Active Directory-Domänendienste-Kontaktobjekt in der zentralen Gesamtstruktur für Skype für Business Server 2015 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="3940b-457">Dieses Tool hilft bei der Durchführung dieser Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="3940b-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="3940b-458">Das Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.</span><span class="sxs-lookup"><span data-stu-id="3940b-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="3940b-459">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-459">Summary</span></span>

<span data-ttu-id="3940b-460">Das Tool LCSSync unterstützt Skype für Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="3940b-461">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="3940b-461">Lookup User Console</span></span>
<span data-ttu-id="3940b-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-462"></span></span>

<span data-ttu-id="3940b-463">Das LookupUserConsole-Verwaltungstool zeigt interne Skype für Business Server Routinginformationen über einzelne Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3940b-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="3940b-464">Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und beim Routing zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-465">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-465">Description</span></span>

 <span data-ttu-id="3940b-466">LookupUserConsole.exe ausgeführt wird ein Eingabeaufforderungsfenster geöffnet, die SIP-Adressen akzeptiert und versucht, interne Skype Business Server routing Informationen über diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="3940b-467">Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.</span><span class="sxs-lookup"><span data-stu-id="3940b-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-468">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-468">Requirements</span></span>

<span data-ttu-id="3940b-469">Installieren Sie die Skype für Business Server 2015 Resource Kit enthalten.</span><span class="sxs-lookup"><span data-stu-id="3940b-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="3940b-470">Das Tool wird ausgeführt auf Domäne gehörenden Computer, auf dem Skype für Business Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-471">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-471">Examples</span></span>

<span data-ttu-id="3940b-472">C:\Programme\Microsoft Files\Skype für Business Server 2015\ResKit\>LookupUserConsole.exe</span><span class="sxs-lookup"><span data-stu-id="3940b-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```
> sip:john.doe@vdomain.com

  Execution time (ms):                            171.094
  Exeuction result:                               Success
  SIP URI:                                        sip:john.doe@vdomain.com
  User info:
    SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
    Grouping ID:                                  00000000-0000-0000-0000-...
    Line URI:                                     <null>
    Policy assignment:                            TenantId={00000000--0000-000....
    SIP enabled:                                  True
    UC enabled:                                   False
    Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
    Active cluster:                               pool0.vdomain.com
    Backup registrar cluster:                     <null>
    Deployment location:                          <null>
    Home Front-End FQDN:                          SERVER.vdomain.com
    Primary Registrar cluster:                    pool0.vdomain.com
    Remote Director external SIP FQDN:            <null>
    Remote Director internal SIP FQDN:            <null>
    Remote Director Web FQDN:                     <null>
    Routing group ID:                             4501e04e-ae48-5605-9346...
    Service tag ID:                               1266953005
    User Front-End resolved:                      True
    User in local forest:                         True
    User in remote forest:                        False
    User in split domain:                         False
    User-Services cluster:                        pool0.vdomain.com

> sip:nouser@vdomain.com

  Execution time (ms):                            948.7574
  Exeuction result:                               UserDoesNotExist

> exit
```

## <a name="msturnping"></a><span data-ttu-id="3940b-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="3940b-473">MsTurnPing</span></span>
<span data-ttu-id="3940b-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-474"></span></span>

<span data-ttu-id="3940b-475">Das Tool MSTurnPing ermöglicht es einem Administrator der Skype für die Kommunikationssoftware Business Server 2015 zum Überprüfen des Status des Servers mit der a/v-Edgeserver und Audio-Video-Authentifizierung Dienste als auch auf den Servern, die Bandbreitenrichtlinie ausgeführt werden Dienste in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="3940b-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-476">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-476">Description</span></span>

<span data-ttu-id="3940b-477">Das Tool MSTurnPing ermöglicht es einem Administrator der Skype für die Kommunikationssoftware Business Server 2015 zum Überprüfen des Status des Servers mit der a/v-Edgeserver und Audio-Video-Authentifizierung Dienste als auch auf den Servern, die Bandbreitenrichtlinie ausgeführt werden Dienste in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="3940b-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="3940b-478">Mit dem Tool können Administratoren die folgenden Tests durchführen:</span><span class="sxs-lookup"><span data-stu-id="3940b-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="3940b-479">A/V-Edgeservertest: Das Tool führt mit allen A/V-Edgeservern in der Topologie die folgenden Tests durch:</span><span class="sxs-lookup"><span data-stu-id="3940b-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

  - <span data-ttu-id="3940b-480">Überprüfen, dass die Skype für Business Server Audio/Video-Authentifizierungsdienst kann die richtige Anmeldeinformationen ausstellen gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

  - <span data-ttu-id="3940b-481">Überprüfen, dass die Skype für Business Server a/v-edgedienst bereits gestartet, sodass die Ressourcen auf die externe Schnittstelle erfolgreich zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="3940b-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="3940b-482">Test für Bandbreiten-Richtliniendienste: Das Tool führt mit allen Servern in der Topologie, auf denen die Bandbreiten-Richtliniendienste ausgeführt werden, die folgenden Tests durch:</span><span class="sxs-lookup"><span data-stu-id="3940b-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

  - <span data-ttu-id="3940b-483">Überprüfen, dass die Skype für Business Server-Bandbreitenrichtliniendienst (Authentifizierung) kann die richtige Anmeldeinformationen ausstellen gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

  - <span data-ttu-id="3940b-484">Überprüfen, dass die Skype für Business Server-Bandbreitenrichtliniendienst (Core) bereits gestartet, sodass das Bandbreite Kontrollkästchen erfolgreich ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="3940b-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="3940b-485">Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist. </span><span class="sxs-lookup"><span data-stu-id="3940b-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-486">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-486">Output</span></span>

<span data-ttu-id="3940b-487">Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="3940b-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="3940b-488">Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3940b-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3940b-489">Die Testergebnisse Computer, auf denen die Skype für Business Server 2015 Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="3940b-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="3940b-490">Die Testergebnisse Computer, auf denen die Skype für Business Server 2015 a/v-edgedienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="3940b-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="3940b-491">Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="3940b-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="3940b-492">Die Testergebnisse Computer, auf denen die Skype für 2015-Bandbreitenrichtliniendienst für Business Server (Authentifizierung) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="3940b-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="3940b-493">Die Testergebnisse Computer, auf denen die Skype für 2015-Bandbreitenrichtliniendienst für Business Server (Core) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="3940b-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-494">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-494">Requirements</span></span>

- <span data-ttu-id="3940b-495">Dieses Tool muss auf einem Computer ausgeführt werden, der zur Topologie gehört und auf dem sich der lokale Speicher befindet.</span><span class="sxs-lookup"><span data-stu-id="3940b-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="3940b-496">Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-497">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-497">Examples</span></span>

<span data-ttu-id="3940b-498">Hier ist ein Beispiel für die Tooleingabe.</span><span class="sxs-lookup"><span data-stu-id="3940b-498">The following is an example of the tool input.</span></span>

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="3940b-499">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-499">Summary</span></span>

<span data-ttu-id="3940b-500">Dieses Tool kann eine wertvolle Ressource Skype für Business Server 2015 Administratoren sein, die den Status der Server, auf dem a/v ausgeführt werden und Bandbreite Richtlinie Dienste überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="3940b-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="3940b-501">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="3940b-501">Network Configuration Viewer</span></span>
<span data-ttu-id="3940b-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-502"></span></span>

<span data-ttu-id="3940b-503">Viewer für Netzwerke Konfiguration kann verwendet werden von Skype für Business Server 2015 Communications Software Administratoren Anruf Admission Control (, CAC)-Netzwerktopologie für ein Unternehmen anzeigen, die bereitgestellt wird, um Kommunikation in Echtzeit-Sitzungen, z. B. zulassen VoIP- oder Videoanrufe basierend auf angegebenen Bandbreitenkapazität.</span><span class="sxs-lookup"><span data-stu-id="3940b-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="3940b-504">Skype für Business Server 2015 Administratoren definieren CAC-Richtlinien, die von den Diensten Bandbreitenrichtlinie erzwungen werden, die mit Skype für Business Server 2015 installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-505">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-505">Description</span></span>

<span data-ttu-id="3940b-506">Mit Network Configuration Viewer („NetworkConfigurationViewer.exe“) können Administratoren die folgenden Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="3940b-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="3940b-507">Laden und CAC-Netzwerktopologie aus einer Skype für Business Server 2015 Bereitstellung in einem Grafikformat anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="3940b-508">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat</span><span class="sxs-lookup"><span data-stu-id="3940b-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="3940b-509">Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger</span><span class="sxs-lookup"><span data-stu-id="3940b-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="3940b-510">Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format</span><span class="sxs-lookup"><span data-stu-id="3940b-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="3940b-511">Anzeigen von Konfigurationsdaten der CAC-Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="3940b-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="3940b-512">Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht</span><span class="sxs-lookup"><span data-stu-id="3940b-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="3940b-513">Definieren benutzerdefinierter Connectors für Verbindungen in der CAC-Netzwerktopologie (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen)</span><span class="sxs-lookup"><span data-stu-id="3940b-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="3940b-514">Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="3940b-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-515">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-515">Purpose</span></span>

<span data-ttu-id="3940b-516">Anzeigen der Verbindungen in der CAC-Netzwerktopologie des Unternehmens auf einer grafischen Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="3940b-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-517">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-517">Examples</span></span>

 <span data-ttu-id="3940b-518">**Laden und Anzeigen der CAC Netzwerktopologie aus einer Skype für die Bereitstellung in einem Grafikformat Business Server 2015**: Skype für Business Server 2015 Administratoren kann laden und Anzeigen von CAC Topologie Netzwerkkonfiguration auf eine beliebige Skype für Business Server 2015 Computer durch verwenden die Option **Netzwerkkonfiguration herunterladen** aus, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="3940b-519">Das Tool nicht laden oder Anzeigen einer Konfigurations bei der Bereitstellung auf einem Computer, die keine Verbindung mit der Skype für Business Server 2015 Konfigurationsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="3940b-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Herunterladen der Netzwerkkonfiguration](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="3940b-521">**Laden und anzeigen CAC Netzwerktopologie aus einer Bandbreitenrichtlinie Server-Protokolldatei in einem Grafikformat:** Skype für Business Server 2015 Bandbreitenrichtlinie Server speichern die Netzwerktopologie CAC als Teil der Protokollierungsmechanismen unter der Skype für Business Server 2015 Dateispeicherort freigeben.</span><span class="sxs-lookup"><span data-stu-id="3940b-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="3940b-522">Skype für Business Server 2015-Administratoren kann eine solche Datei in einem Grafikformat anzeigen, mithilfe der Option **Open Netzwerkkonfiguration** wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Öffnen einer Bandbreitenrichtlinienserver-Protokolldatei](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="3940b-524">Speichern und CAC-Netzwerktopologie in XML-Format auf dem Datenträger speichern: Skype für Business Server 2015-Administratoren kann die CAC Netzwerk Topologie Konfiguration-Datei in einem XML-Format speichern, mithilfe der Option zum **Speichern einer Kopie der Netzwerkkonfiguration** wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="3940b-525">Die gespeicherte Konfigurationsdatei kann dann offline als Grafik angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Speichern der Netzwerkkonfiguration als XML-Datei](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="3940b-527">Speichern und Store CAC Netzwerktopologie JPG- oder BMP-Format: Skype für Business Server 2015-Administratoren kann die Netzwerkkonfiguration Topologie CAC in einem Grafikformat (JPG und BMP-Dateiformate) mithilfe des Netzwerkkonfiguration speichern **Diagramms als speichern Bild** option wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Speichern der Netzwerkkonfiguration als Bild](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="3940b-529">**Ansicht CAC Netzwerk topologiekonfigurationsdaten:** Skype für Business Server 2015-Administratoren kann verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerkstandorten, Bandbreite Profile und Website Subnetz-IP-Adressen in einem Textformat anzeigen mithilfe der Option Ansicht Netzwerkkonfiguration Daten wie dargestellt unten.</span><span class="sxs-lookup"><span data-stu-id="3940b-529">**View CAC network topology configuration data:** Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Anzeigen von Netzwerkkonfigurationsdaten](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="3940b-531">**Netzwerktopologie ausgezeichnet Strukturansicht Ansicht CAC:** Skype für Business Server 2015 Administratoren kann verwandte Netzwerkkonfigurationsdaten ausgezeichnet Ansicht graphical Struktur anzeigen, mithilfe der Systemsteuerung auf der linken Seite des Toolfensters wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="3940b-533">**Definieren benutzerdefinierte Konnektoren für die Anrufsteuerung Netzwerk-Topologie Links (beispielsweise Standort-zu-Region und regional-Standort-zu-Standort-Verknüpfungen):** Skype für Business Server 2015-Administratoren kann benutzerdefinierte graphical Connectors für CAC Netzwerk Konfiguration WAN-Verbindungen mithilfe der Option Einstellungen wie folgt definieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="3940b-534">Dies erleichtert die Unterscheidung zwischen verschiedenen Netzwerkverbindungstypen, die in der Netzwerkkonfiguration bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="3940b-536">**Ansicht CAC netzwerkstandortinformationen Topologie und Regionsinformationen bereitgestellten Bandbreitenrichtlinien:** Skype für Business Server 2015-Administratoren kann verwandte CAC netzwerkregionsinformationen, Websiteinformationen und CAC Bandbreite, die Bereitstellung von Informationen mithilfe der unten gezeigten Optionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="3940b-537">(Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)</span><span class="sxs-lookup"><span data-stu-id="3940b-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="3940b-539">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-539">Summary</span></span>

<span data-ttu-id="3940b-540">Dieses Tool kann eine wertvolle Ressource Skype für Business Server 2015 Administratoren sein, die in einem Grafikformat CAC-Netzwerktopologie für ihre Bereitstellung anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="3940b-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="3940b-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="3940b-541">Response Group Agent Live</span></span>
<span data-ttu-id="3940b-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-542"></span></span>

<span data-ttu-id="3940b-543">Die Anwendung "Reaktionsgruppe" ermöglicht Agents nützlich Echtzeitinformationen mit den integrierten Web-Dienst zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3940b-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="3940b-544">Leider ist keine grafisch dieser Daten außerhalb der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3940b-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="3940b-545">Das Antwort Gruppe Agent Live Resource Kit-Tool löst dieses Problem, indem er eine einfache und graphical Möglichkeit Zugriff auf diese Informationen, die in Echtzeit Skype Business Communications Software Informationen wie die Anwesenheit von anderen Agents erweitert.</span><span class="sxs-lookup"><span data-stu-id="3940b-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-546">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-546">Description</span></span>

<span data-ttu-id="3940b-547">Response Group Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet.</span><span class="sxs-lookup"><span data-stu-id="3940b-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="3940b-548">Hierbei handelt es sich wird eine erweiterte Version der Seite Agentgruppen (Zugriff über Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="3940b-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-549">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-549">Purpose</span></span>

<span data-ttu-id="3940b-p161">Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agent-Gruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agent-Gruppen zugreifen. Dabei erfahren sie beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Response Group Agent Live zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="3940b-553">Funktionen</span><span class="sxs-lookup"><span data-stu-id="3940b-553">Features</span></span>

<span data-ttu-id="3940b-554">Das Tool Antwort Gruppe Agent Live baut auf der reaktionsgruppendienst und die Skype für Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="3940b-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="3940b-555">Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst zur Verfügung gestellt werden (beispielsweise Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).</span><span class="sxs-lookup"><span data-stu-id="3940b-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="3940b-556">Die Abbildung unten zeigt die Hauptoberfläche von Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3940b-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Das Tool „Reaktionsgruppen-Agent Live“](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="3940b-558">Folgende drei Hauptfeatures stehen Agents in Response Group Agent Live zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="3940b-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="3940b-559">**Sign-in/Out:** Im Gegensatz zu der Seite Agent-Gruppen (Zugriff über Skype für Business Server 2015) können nur Agenten-Anmeldung oder alle Gruppen gleichzeitig Antwort Gruppe Agent Live.</span><span class="sxs-lookup"><span data-stu-id="3940b-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="3940b-560">Diese Anwendung bietet drei Verfahren für Agents zum Signieren in oder out:</span><span class="sxs-lookup"><span data-stu-id="3940b-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="3940b-561">Klicken auf die Schaltflächen zum An-/Abmelden (grün und rot) in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="3940b-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="3940b-562">Klicken auf das Taskleistensymbol mit der rechten Maustaste und Auswählen von „Sign-in“ oder „Sign-out“</span><span class="sxs-lookup"><span data-stu-id="3940b-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="3940b-563">Verwenden konfigurierbarer Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="3940b-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="3940b-564">**Gruppenmitgliedschaft:** Bei eine agentgruppe ausgewählt ist, werden Antwort Gruppe Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="3940b-565">Wenn Skype für Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden in der Antwort Gruppe Agent Live Anwesenheitsinformationen und der Visitenkarte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="3940b-566">Agents können direkt von dort aus eine Chatnachricht senden oder andere Agents anrufen.</span><span class="sxs-lookup"><span data-stu-id="3940b-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="3940b-p165">**Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Statistiken werden minütlich aktualisiert. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der aktuellen Anzahl der wartenden Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-571">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-571">Requirements</span></span>

<span data-ttu-id="3940b-572">Response Group Agent Live erfordert .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="3940b-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="3940b-573">Darüber hinaus um die Anwesenheits- und Kontaktinformationen Karte-Features nutzen zu können, Skype für Unternehmen muss lokal installiert werden (und ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="3940b-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="3940b-574">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3940b-574">Configuration</span></span>

<span data-ttu-id="3940b-p167">Response Group Agent Live kann mithilfe des Dialogfelds „Options“ in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus können Administratoren die Standardhostadresse definieren, indem sie die Eigenschaft „defaultHostAddress“ in der Datei „RGAgentLive.exe.config“ direkt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3940b-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="3940b-p168">Die Abbildung unten zeigt das Dialogfeld „Options“, in dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld können Sie zugreifen, indem Sie auf der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche „Options“ klicken.</span><span class="sxs-lookup"><span data-stu-id="3940b-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Das Dialogfeld mit Optionen für „Reaktionsgruppen-Agent Live“](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="3940b-580">Folgende drei unterschiedliche Einstellungen können in der Konfiguration von Response Group Agent Live angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="3940b-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="3940b-581">Hosten von Adresse: Dies ist üblicherweise im Web pool-FQDN, der Agent im home-Pool angehören.</span><span class="sxs-lookup"><span data-stu-id="3940b-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="3940b-582">Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).</span><span class="sxs-lookup"><span data-stu-id="3940b-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="3940b-583">Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="3940b-584">Die einzige Einschränkung ist, dass beide Tastenkombinationen Schlüssels "Windows-Logo" (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="3940b-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="3940b-585">Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-586">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-586">Examples</span></span>

<span data-ttu-id="3940b-587">Die Abbildung unten zeigt, wie Sie andere Agents anrufen oder ihnen eine Chatnachricht senden, indem Sie mit der rechten Maustaste im rechten Bereich auf den Kontakt klicken.</span><span class="sxs-lookup"><span data-stu-id="3940b-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Anruf tätigen oder Chatnachricht senden](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="3940b-589">Die Abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Anzeigen von Warteschlangeninformationen](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="3940b-591">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-591">Summary</span></span>

<span data-ttu-id="3940b-592">Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="3940b-593">Mit dem Tool Antwort Gruppe Agent Live Resource Kit kann Skype für Business Server 2015 Administratoren ihre Agents mit einer Windows-Anwendung bereitstellen, das zum Ausführen von Aufgaben in einer Weise schneller und grafische ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3940b-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="3940b-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="3940b-594">SEFAUtil</span></span>
<span data-ttu-id="3940b-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-595"></span></span>

<span data-ttu-id="3940b-596">SEFAUtil (sekundäre Erweiterung der Aktivierung des Features) ist ein Befehlszeilentool, mit dem Skype Business Server 2015 Communications-Software-Administratoren und Helpdesk-Agents Delegaten klingeln, anrufweiterleitung, Gleichzeitiges Klingeln konfigurieren kann, Rufen Sie teamanrufgruppen-Einstellungen und Gruppe Pickup im Namen einer Skype für Business Server 2015 Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3940b-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3940b-597">Das Tool ermöglicht auch Administratoren die Einstellungen Anrufrouting Abfragen, die für einen bestimmten Benutzer veröffentlicht werden. Das Tool SEFAUtil ermöglicht dem Administrator, Enable, Disable, ändern Anruf weiterleiten oder Gleichzeitiges Anrufen im Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3940b-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="3940b-598">Der Administrator kann das Ziel (in Form einer SIP-URI) angeben oder eine Ziel, die bereits vom Benutzer veröffentlicht wurde verwenden.</span><span class="sxs-lookup"><span data-stu-id="3940b-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="3940b-599">Dieses Tool ermöglicht auch Administratoren hinzufügen oder Entfernen von Stellvertretungen oder Team-anrufgruppe Mitglieder im Auftrag des Benutzers. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.</span><span class="sxs-lookup"><span data-stu-id="3940b-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="3940b-600">SEFAUtil (sekundäre Erweiterung der Aktivierung des Features) ermöglicht Skype für Business Server 2015 Administratoren und Helpdesk-Agents konfigurieren Delegaten klingeln, anrufweiterleitung, Gleichzeitiges Klingeln, teamanrufe-Einstellungen und Pickup-Anruf im Namen einer Skype gruppieren für Benutzer Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3940b-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="3940b-601">Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-602">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-602">Description</span></span>

<span data-ttu-id="3940b-603">Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool. Es ist keine unterstützenden GUI.</span><span class="sxs-lookup"><span data-stu-id="3940b-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="3940b-604">Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="3940b-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="3940b-605">Die Features in dieses Tool ermöglichen Administratoren und Helpdesk-Agenten, die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="3940b-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="3940b-606">Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Stellvertretung, gleichzeitiges Klingeln, Teamanruf- und Gruppenanrufannahme)</span><span class="sxs-lookup"><span data-stu-id="3940b-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="3940b-607">Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (einschließlich Ziel und Timer für „Keine Antwort“)</span><span class="sxs-lookup"><span data-stu-id="3940b-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="3940b-608">Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="3940b-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="3940b-609">Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3940b-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="3940b-610">Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="3940b-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="3940b-611">Neu in Skype für Business Server 2015 SEFAUtil tool</span><span class="sxs-lookup"><span data-stu-id="3940b-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3940b-612">Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)</span><span class="sxs-lookup"><span data-stu-id="3940b-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3940b-613">Neu in Skype für Business Server 2015 SEFAUtil tool</span><span class="sxs-lookup"><span data-stu-id="3940b-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="3940b-614">Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="3940b-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="3940b-615">Neu in Skype für Business Server 2015 SEFAUtil tool</span><span class="sxs-lookup"><span data-stu-id="3940b-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="3940b-616">Für das Tool gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="3940b-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="3940b-617">Unterstützt nur für Benutzer in einer Skype für Business Server-Pool verwaltet</span><span class="sxs-lookup"><span data-stu-id="3940b-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="3940b-618">Keine Unterstützung für die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="3940b-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="3940b-619">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-619">Output</span></span>

<span data-ttu-id="3940b-p175">Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-622">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-622">Purpose</span></span>

<span data-ttu-id="3940b-623">Hier sind einige der Hauptszenarien, in denen dieses Tool eingesetzt werden kann:</span><span class="sxs-lookup"><span data-stu-id="3940b-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="3940b-624">Bob ist Führungskraft und an Skype für Telefonie Business Server verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="3940b-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="3940b-625">In seiner vorhandenen Nebenstellenanlage hat er Stellvertretungen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="3940b-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="3940b-626">Als Teil der Wechsel zu Skype für Business Server 2015 kann der Administrator Bobs routing seine vorhandenem Delegierung Konfiguration entsprechend konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="3940b-p177">Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anruf eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum, alle Anrufe an ihre Büronummer an ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="3940b-631">Joes Anrufe an seine Dienstnummer sollte werden auf seinem mobilen Voicemail, wenn er bei der Arbeit ist; Dinge werden jedoch in den meisten anderen Stellen ordnungsgemäß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3940b-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="3940b-632">Der Helpdesk-Techniker Routingkonfiguration des Joe angezeigt und feststellt, dass Joe Gleichzeitiges Klingeln an seinem Mobiltelefon konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="3940b-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="3940b-633">Der Techniker bittet Joe über die mobilen Abdeckung in seinem Büro und feststellen, dass die gleichzeitige Klingeln Regel ist, wodurch die Anrufe beim seine Netzwerk Abdeckung schlecht ist Joes mobilen Voicemail weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="3940b-634">Mike wird ein neuer Mitarbeiter bei Contoso und er wird ein neues Team auf dem alle Mitglieder für Team-anrufgruppe konfiguriert sind, wenn für Skype für Business Server 2015 aktiviert ist, beitreten, der Administrator ist seine teamanrufgruppe Clientgruppen Einbeziehung seiner neuen Teammitglieder festlegen , der Administrator darüber hinaus als Mitglied einer teamanrufgruppe für jedes Mitglied in seinem Team Mike hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3940b-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="3940b-635">Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso besteht darin, allen Anrufern vom ersten Anruf an persönlichen Service zu bieten.</span><span class="sxs-lookup"><span data-stu-id="3940b-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="3940b-636">Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, kann das gleichzeitige Klingeln auf allen Telefonen bei Teamanrufen sehr störend für das Team sein.</span><span class="sxs-lookup"><span data-stu-id="3940b-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="3940b-637">Um den besten Service bereitzustellen, ohne Beeinträchtigung der Teammitglieder, nutzt die Skype für Business Server 2015 Administrator der Gruppe anrufen Pickup-Funktion.</span><span class="sxs-lookup"><span data-stu-id="3940b-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="3940b-638">Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit.</span><span class="sxs-lookup"><span data-stu-id="3940b-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="3940b-639">Wenn nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.</span><span class="sxs-lookup"><span data-stu-id="3940b-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-640">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-640">Requirements</span></span>

<span data-ttu-id="3940b-p180">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="3940b-644">Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="3940b-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="3940b-645">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört.</span><span class="sxs-lookup"><span data-stu-id="3940b-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="3940b-646">Bei Bedarf kann hinzufügen, die einen Pool einen neuen vertrauenswürdigen Anwendungspool über die Skype für Business Server-Verwaltungsshell das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="3940b-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

  ```
  New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
  ```

    > [!NOTE]
    > <span data-ttu-id="3940b-647">Auf allen Computern, auf denen das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="3940b-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="3940b-648">In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein.</span><span class="sxs-lookup"><span data-stu-id="3940b-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="3940b-649">Um SEFAUtil als eine neue vertrauenswürdige Anwendung definieren möchten, verwenden Sie die Skype für Business Server-Verwaltungsshell, und führen Sie das folgende Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3940b-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

  ```
  New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
  ```

    > [!NOTE]
    > <span data-ttu-id="3940b-650">Gegebenenfalls kann ein anderer Port verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-650">A different port can be used if needed.</span></span>

3. <span data-ttu-id="3940b-651">Die Topologieänderungen müssen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-651">The topology changes need to be enabled.</span></span> <span data-ttu-id="3940b-652">Aktivieren der Topologie kann über die Skype für Business Server-Verwaltungsshell erfolgen durch das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="3940b-652">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

  ```
  Enable-CsToplogy
  ```

4. <span data-ttu-id="3940b-653">Falls erforderlich, installieren Sie die Skype für Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil (der Server muss Bestandteil einer vertrauenswürdigen Anwendungspool) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-653">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="3940b-654">Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-654">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="3940b-655">Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-655">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="3940b-656">Standardmäßig wird das Tool im gespeichert: "...\Programme\Microsoft Files\Skype für Business Server 2015\Reskit".</span><span class="sxs-lookup"><span data-stu-id="3940b-656">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="3940b-657">Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="3940b-657">To display the call forwarding settings of a user, use the following command:</span></span>

  ```
  SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
  ```

    <span data-ttu-id="3940b-658">Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-658">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="3940b-659">Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="3940b-659">Group Call Pickup</span></span>

<span data-ttu-id="3940b-660">Gruppe aufrufen Pickup-erfordert zusätzliche Konfiguration in Skype für Business Server 2015 für die Funktion vollständig aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3940b-660">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="3940b-661">Bevor Sie Benutzern Annahmegruppen zuweisen, sollten Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nachlesen.</span><span class="sxs-lookup"><span data-stu-id="3940b-661">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-662">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-662">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="3940b-663">Anzeigen aktueller Anrufbehandlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3940b-663">Display Current Call Handling Settings</span></span>

<span data-ttu-id="3940b-664">Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="3940b-664">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="3940b-665">In diesem Beispiel wird die **Option/Server** die Skype für Business Server für die Verbindung angeben.</span><span class="sxs-lookup"><span data-stu-id="3940b-665">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="3940b-666">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-666">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="3940b-667">Festlegen des Ziels für Anrufweiterleitung/Keine Antwort</span><span class="sxs-lookup"><span data-stu-id="3940b-667">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="3940b-668">In diesem Beispiel wird der Anruf weiterleiten/Nein-Antwort Ziel und die anrufverzögerung.</span><span class="sxs-lookup"><span data-stu-id="3940b-668">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="3940b-669">Die Option/Server ist hier nicht enthalten. SEFAUtil versucht, AutoErmittlung der Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3940b-669">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="3940b-670">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-670">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="3940b-671">Aktivieren der sofortigen Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="3940b-671">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="3940b-672">Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3940b-672">This example immediately enables call-forwarding to another user.</span></span>

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="3940b-673">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-673">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="3940b-674">Deaktivieren der sofortigen Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="3940b-674">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="3940b-675">Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="3940b-675">This example immediately disables call forwarding.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="3940b-676">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-676">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="3940b-677">Hinzufügen eines Benutzers als Stellvertretung und Einrichten von gleichzeitigem Klingeln bei Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="3940b-677">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="3940b-678">Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das gleichzeitige Klingeln bei Stellvertretungen ein.</span><span class="sxs-lookup"><span data-stu-id="3940b-678">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="3940b-679">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-679">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="3940b-680">Ändern der Regel für gleichzeitiges Klingeln bei Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="3940b-680">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="3940b-681">Dieses Beispiel ändert die Regel für gleichzeitiges Klingeln bei Stellvertretungen, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.</span><span class="sxs-lookup"><span data-stu-id="3940b-681">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="3940b-682">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-682">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="3940b-683">Entfernen der Stellvertretung</span><span class="sxs-lookup"><span data-stu-id="3940b-683">Remove the Delegate</span></span>

<span data-ttu-id="3940b-684">Dieses Beispiel entfernt die Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="3940b-684">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="3940b-685">Wenn die letzte Stellvertretung entfernt wurde, wird das Anrufen von Stellvertretungen automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3940b-685">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="3940b-686">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-686">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="3940b-687">Hinzufügen einer Stellvertretung und Einrichten der Regel „Anrufweiterleitung an Stellvertretungen“</span><span class="sxs-lookup"><span data-stu-id="3940b-687">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="3940b-688">Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel „Anrufweiterleitung an Stellvertretungen“ ein.</span><span class="sxs-lookup"><span data-stu-id="3940b-688">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="3940b-689">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-689">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="3940b-690">Aktivieren von gleichzeitigem Klingeln und Festlegen einer Zielnummer</span><span class="sxs-lookup"><span data-stu-id="3940b-690">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="3940b-691">Diese Beispiel aktiviert gleichzeitiges Klingeln und legt eine Zielnummer für diese Funktion fest.</span><span class="sxs-lookup"><span data-stu-id="3940b-691">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="3940b-692">Um die Zielnummer für gleichzeitiges Klingeln eines Benutzers zu ändern, für den gleichzeitiges Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter „/enablesimulring“. Andernfalls wird die Zielnummer nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="3940b-692">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="3940b-693">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-693">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="3940b-694">Deaktivieren von gleichzeitigem Klingeln</span><span class="sxs-lookup"><span data-stu-id="3940b-694">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="3940b-695">Dieses Beispiel deaktiviert gleichzeitiges Klingeln.</span><span class="sxs-lookup"><span data-stu-id="3940b-695">This example disables simultaneous ringing.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="3940b-696">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-696">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="3940b-697">Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Teamanrufgruppen-Mitglieder</span><span class="sxs-lookup"><span data-stu-id="3940b-697">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="3940b-698">Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert gleichzeitiges Klingeln für die Teamanrufgruppe.</span><span class="sxs-lookup"><span data-stu-id="3940b-698">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3940b-699">Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für gleichzeitiges Klingeln automatisch auf gleichzeitiges Klingeln für die Teamanrufgruppe umgestellt.</span><span class="sxs-lookup"><span data-stu-id="3940b-699">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="3940b-700">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-700">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="3940b-701">Entfernen eines Mitglieds aus der Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="3940b-701">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="3940b-702">Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3940b-702">This example removes a team member of the team-call group of a user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="3940b-703">Wenn das einzige Mitglied der Teamanrufgruppe entfernt wird, wird automatisch das gleichzeitige Klingeln für die Teamanrufgruppe deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3940b-703">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="3940b-704">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-704">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="3940b-705">Festlegen der Anrufverzögerung für die Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="3940b-705">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="3940b-706">Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.</span><span class="sxs-lookup"><span data-stu-id="3940b-706">This example changes the delayed ring to the team-call group time setting.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="3940b-707">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-707">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="3940b-708">Aktivieren des Teamanrufs</span><span class="sxs-lookup"><span data-stu-id="3940b-708">Enable Team-Call</span></span>

<span data-ttu-id="3940b-709">Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3940b-709">This example enables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="3940b-710">Wenn teamanrufgruppe des Benutzers keine Member aufweist, nicht teamanrufgruppe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3940b-710">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="3940b-711">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-711">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="3940b-712">Deaktivieren des Teamanrufs</span><span class="sxs-lookup"><span data-stu-id="3940b-712">Disable Team-Call</span></span>

<span data-ttu-id="3940b-713">Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3940b-713">This example disables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="3940b-714">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-714">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="3940b-715">Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="3940b-715">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="3940b-716">Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="3940b-716">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="3940b-717">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="3940b-717">**Output**</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="3940b-718">Deaktivieren der Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="3940b-718">Disable Group Call Pickup</span></span>

<span data-ttu-id="3940b-719">Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3940b-719">This example disables Group Call Pickup for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="3940b-p187">Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend wieder aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters „/enablegrouppickup“ zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3940b-p187">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="3940b-722">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="3940b-722">SYSPrep.ps1</span></span>
<span data-ttu-id="3940b-723"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-723"></span></span>

### <a name="description"></a><span data-ttu-id="3940b-724">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-724">Description</span></span>

<span data-ttu-id="3940b-725">SYSPrep.ps1 ist ein Windows PowerShell-Skript, das die folgenden Skype Business Server 2015 erforderliche Komponenten auf Ihrem Computer der Windows Server 2008-Betriebssystem installiert.</span><span class="sxs-lookup"><span data-stu-id="3940b-725">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="3940b-726">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3940b-726">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="3940b-727">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3940b-727">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="3940b-728">Windows PowerShell, Version 3.0</span><span class="sxs-lookup"><span data-stu-id="3940b-728">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="3940b-729">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="3940b-729">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="3940b-730">Updates für Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="3940b-730">Internet Information Server Updates</span></span>

- <span data-ttu-id="3940b-731">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3940b-731">Windows Identity Foundation</span></span>

- <span data-ttu-id="3940b-732">Skype für Business Server 2015 Hauptdateien</span><span class="sxs-lookup"><span data-stu-id="3940b-732">Skype for Business Server 2015 Core files</span></span>

 <span data-ttu-id="3940b-733">Zwar ähnelt der Skriptname dem des Systemvorbereitungsprogramms für die Microsoft Windows-Betriebssysteme, doch sind beide unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="3940b-733">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="3940b-734">Mit diesem Skript wird nur die erforderlichen Komponenten für Skype für Business Server 2015 installieren.</span><span class="sxs-lookup"><span data-stu-id="3940b-734">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="3940b-735">Sobald diese installiert sind, kann mit dem Windows-Tool für die Systemvorbereitung ein Image des Servers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-735">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-736">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-736">Requirements</span></span>

<span data-ttu-id="3940b-737">Vor dem Ausführen des Skripts SYSPrep.ps1, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (beispielsweise **D:\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="3940b-737">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="3940b-738">In diesem Ordner muss auch enthalten eine Kopie der Skype für Dateien, Business Server 2015, insbesondere **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="3940b-738">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="3940b-739">Die erforderlichen Dateien können Sie an folgenden Orten herunterladen:</span><span class="sxs-lookup"><span data-stu-id="3940b-739">The prerequisite files can be downloaded from the following locations:</span></span>

|<span data-ttu-id="3940b-740">**Erforderliche Komponente**</span><span class="sxs-lookup"><span data-stu-id="3940b-740">**Prerequisite**</span></span>|<span data-ttu-id="3940b-741">**Standort**</span><span class="sxs-lookup"><span data-stu-id="3940b-741">**Location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3940b-742">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3940b-742">Microsoft .Net Framework 4.5</span></span>  <br/> |https://go.microsoft.com/?linkid=9816306  <br/> |
|<span data-ttu-id="3940b-743">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3940b-743">Microsoft SQL Server Express 2008 R2</span></span>  <br/> |https://www.microsoft.com/en-us/download/details.aspx?id=23650  <br/> |
|<span data-ttu-id="3940b-744">Windows PowerShell, Version 3.0</span><span class="sxs-lookup"><span data-stu-id="3940b-744">Windows Powershell version 3.0</span></span>  <br/> |https://www.microsoft.com/en-us/download/details.aspx?id=34595  <br/> |
|<span data-ttu-id="3940b-745">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="3940b-745">Visual C++ 2010 Redistributable</span></span>  <br/> |https://www.microsoft.com/en-us/download/details.aspx?id=5555  <br/> |
|<span data-ttu-id="3940b-746">Updates für Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="3940b-746">Internet Information Server Updates</span></span>  <br/> |https://www.microsoft.com/en-us/download/details.aspx?id=34869  <br/> |
|<span data-ttu-id="3940b-747">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="3940b-747">Windows Identity Foundation</span></span>  <br/> |https://www.microsoft.com/en-us/download/details.aspx?id=17331  <br/> |
|<span data-ttu-id="3940b-748">Skype für Business Server 2015 Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3940b-748">Skype for Business Server 2015 Setup.exe</span></span>  <br/> |<span data-ttu-id="3940b-749">Kopieren von Skype für Business Server 2015 Medien</span><span class="sxs-lookup"><span data-stu-id="3940b-749">Copy from Skype for Business Server 2015 media</span></span>  <br/> |

### <a name="parameter"></a><span data-ttu-id="3940b-750">Parameter</span><span class="sxs-lookup"><span data-stu-id="3940b-750">Parameter</span></span>

<span data-ttu-id="3940b-751">Der Parameter **- SetupFolder** nimmt als Argument an den Speicherort des erforderlichen Dateien</span><span class="sxs-lookup"><span data-stu-id="3940b-751">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-752">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-752">Examples</span></span>

<span data-ttu-id="3940b-753">Zum Ausführen des Skripts SYSPrep.ps1 und die Skype Business Server 2015 erforderliche Komponenten installieren, führen Sie den folgenden Befehl aus einer Eingabeaufforderung mit erhöhten Rechten aus:</span><span class="sxs-lookup"><span data-stu-id="3940b-753">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="3940b-754">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="3940b-754">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="3940b-755"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-755"></span></span>

<span data-ttu-id="3940b-756">Das nicht zugewiesene Nummer Ankündigungen Migrationstool ermöglicht eine Skype Business Server 2015 Administrator verschieben Sie die Konfiguration nicht zugewiesener Nummern, die von der ankündigungsanwendung aus einer Quelle Skype für zu Business Server oder Pool bedient wird ein Ziel Skype für Business Server oder Pool.</span><span class="sxs-lookup"><span data-stu-id="3940b-756">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-757">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-757">Description</span></span>

<span data-ttu-id="3940b-758">Das Tool Unassigned Number Announcements Migration ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.</span><span class="sxs-lookup"><span data-stu-id="3940b-758">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="3940b-759">Bei Ausführung des Unassigned Number Announcements Migration-Skripts werden folgende Vorgänge durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="3940b-759">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="3940b-760">Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Dateispeicher des Zielservers oder -pools</span><span class="sxs-lookup"><span data-stu-id="3940b-760">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3940b-761">Die Audiodateien werden aus dem Quellpool entfernt, sobald sie in der Zielpool kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="3940b-761">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="3940b-762">Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Zielserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="3940b-762">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="3940b-763">Erneutes Zuweisen aller nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool verwaltet wird, zum Zielserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="3940b-763">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="3940b-764">Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.</span><span class="sxs-lookup"><span data-stu-id="3940b-764">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-765">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-765">Output</span></span>

<span data-ttu-id="3940b-766">Das Skript **Move-CsAnnouncementConfiguration** gibt an, in der Skype für Business Server-Verwaltungsshell-Fenster aus, in dem sie den Erfolg oder das Fehlschlagen des Migrationsvorgangs ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="3940b-766">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="3940b-p190">Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich in das Ziel verschobenen nicht zugewiesenen Nummernbereiche in funktionsfähiger Form am Ziel, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.</span><span class="sxs-lookup"><span data-stu-id="3940b-p190">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="3940b-769">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="3940b-769">Purpose</span></span>

<span data-ttu-id="3940b-770">Das Unassigned Number Announcements Migration-Skript kann in den drei folgenden Szenarien eingesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="3940b-770">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="3940b-771">**Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype für Business Server:** Contoso ist bei der Migration zu Skype für Business Server 2015 und im Rahmen des Migrationsvorgangs der Skype für Business Server Administrator möchte die von der ankündigungsanwendung von Lync bedient nicht zugewiesener Nummern Konfiguration verschieben Zu den neuen Skype für die Bereitstellung von Business Server 2015 Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3940b-771">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3940b-772">Um die Konfigurationseinstellungen zu verschieben, verwendet der Skype für Business Server-Administrator das nicht zugewiesene Nummer Ankündigungen Migration Tool.</span><span class="sxs-lookup"><span data-stu-id="3940b-772">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="3940b-773">**Rollbacks einer bereitstellungs von Skype für Business Server 2015 zu Lync Server 2013:** Fälligkeitsdatum unerwarteten Faktoren verfügt über einen Rollback die Migration zu den neuen Skype für die Bereitstellung von Business Server 2015 Contoso.</span><span class="sxs-lookup"><span data-stu-id="3940b-773">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="3940b-774">Um mit dem Dienst Systemausfallzeit zu minimieren, verwendet die Skype für Business Server-Administrator das nicht zugewiesene Nummer Ankündigungen Migrationstool die Konfiguration aus der Skype für Business Server 2015 Bereitstellung der Lync Server 2013-Bereitstellung Rollback zu.</span><span class="sxs-lookup"><span data-stu-id="3940b-774">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="3940b-775">**Verschieben von Daten zwischen Bereitstellungen:** Contoso wird gerade Ersetzen von allen Servern eines Pools mit neueren Servern.</span><span class="sxs-lookup"><span data-stu-id="3940b-775">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="3940b-776">Verschieben Sie ihre Strategie besteht darin, eine neue Skype für Business Server 2015-Pool bereitstellen alle Daten vom alten auf den neuen Pool, und klicken Sie dann verwerfen der alten Pools.</span><span class="sxs-lookup"><span data-stu-id="3940b-776">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="3940b-777">Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mit dem Tool Unassigned Number Announcements Migration aus dem alten Pool in den neuen verschoben.</span><span class="sxs-lookup"><span data-stu-id="3940b-777">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="3940b-778">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-778">Requirements</span></span>

<span data-ttu-id="3940b-779">Hier sind die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:</span><span class="sxs-lookup"><span data-stu-id="3940b-779">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="3940b-780">Das Skript muss von einem Computer ausgeführt werden, Skype für Business Server-Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="3940b-780">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="3940b-781">Der ankündigungsanwendung wurde erfolgreich in die Quell- und Skype für Business Server oder Pools bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-781">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="3940b-782">Skript „Move-CsAnnouncementConfiguration“</span><span class="sxs-lookup"><span data-stu-id="3940b-782">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="3940b-783">Das Skript „Move-CsAnnouncementConfiguration“ erfordert die in der Tabelle unten beschriebenen zwei Parameter. </span><span class="sxs-lookup"><span data-stu-id="3940b-783">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Parameter „Move-CsAnnouncementConfiguration“](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="3940b-785">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-785">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="3940b-786">Verschieben Sie die nicht zugewiesenen Nummern Ansagen Konfiguration aus einem Lync Server 2013-Pool in einen Skype für Business Serverpool 2015</span><span class="sxs-lookup"><span data-stu-id="3940b-786">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="3940b-787">Dieses Beispiel verschiebt die nicht zugewiesenen Nummern Ansagen aus dem Quellpool (Lync Server 2013) an die Zielpool (Skype für Business Server 2015).</span><span class="sxs-lookup"><span data-stu-id="3940b-787">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com

```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="3940b-788">Verschieben der nicht zugewiesenen Nummern Ansagen Konfigurations aus einer Skype für Business Serverpool 2015 in einer Lync Server 2013-Pool</span><span class="sxs-lookup"><span data-stu-id="3940b-788">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="3940b-789">Dieses Beispiel verschiebt die nicht zugewiesenen Nummern Ansagen aus dem Quellpool (Skype für Business Server 2015) an die Zielpool (Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="3940b-789">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="3940b-790">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="3940b-790">Web Conf Data</span></span>
<span data-ttu-id="3940b-791"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="3940b-791"></span></span>

<span data-ttu-id="3940b-792">Das Tool zum Web Conf Daten kann der Administrator von Skype für die Kommunikationssoftware Business Server 2015 mehr Kontrolle über die Daten des Organisators Webkonferenzen zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="3940b-792">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="3940b-793">Szenarien umfassen die Möglichkeit, einen bestimmten Benutzer Besprechungsdaten basierend auf einer Zeitkriterien Stempel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3940b-793">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="3940b-794">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3940b-794">Description</span></span>

<span data-ttu-id="3940b-795">Mit diesem Tool können Administratoren die folgenden Vorgänge durchführen:</span><span class="sxs-lookup"><span data-stu-id="3940b-795">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="3940b-796">Suchen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="3940b-796">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="3940b-797">Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="3940b-797">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="3940b-798">Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind und deren Alter einen bestimmten Wert überschreitet</span><span class="sxs-lookup"><span data-stu-id="3940b-798">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="3940b-799">Verschieben aller Webkonferenzdaten, die einem Benutzern zugeordnet sind, wenn diese Benutzer aus einem Pool in einen anderen verschoben werden</span><span class="sxs-lookup"><span data-stu-id="3940b-799">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

> [!NOTE]
> <span data-ttu-id="3940b-800">Resource Kit-Tools für Lync Server 2010 unterstützt das Verschieben von allen Web Conferencing Daten mit einem einzelnen Benutzer verknüpft ist, wenn der Benutzer von einem Pool in einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-800">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="3940b-801">Diese Funktionalität wird von diesem Tool wird der Parameter **MoveConferenceData** jetzt veraltet.</span><span class="sxs-lookup"><span data-stu-id="3940b-801">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="3940b-802">Weitere Informationen zu diesem Parameter finden Sie unter [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3940b-802">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="3940b-p196">Das Tool löscht Besprechungsdaten nur für inaktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-p196">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="3940b-p197">Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-p197">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="3940b-807">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3940b-807">Output</span></span>

<span data-ttu-id="3940b-808">Dieses Tool gibt die Ergebnisse der folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="3940b-808">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="3940b-809">Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, deren Organisator dieser Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="3940b-809">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="3940b-810">Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-810">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="3940b-811">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3940b-811">Requirements</span></span>

<span data-ttu-id="3940b-812">Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator zurzeit verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="3940b-812">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="3940b-813">Das Tool muss mit Administratorrechten und mit Zugriff auf den Inhaltsdateispeicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-813">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="3940b-814">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3940b-814">Examples</span></span>

<span data-ttu-id="3940b-815">In der folgenden Tabelle werden die Parameter beschrieben, die zum Teil in den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3940b-815">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parameter für das Webkonferenzdaten-Tool](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="3940b-p198">Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="3940b-p198">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="3940b-p199">Oben sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3940b-p199">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="3940b-821">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3940b-821">Summary</span></span>

<span data-ttu-id="3940b-822">Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="3940b-822">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>



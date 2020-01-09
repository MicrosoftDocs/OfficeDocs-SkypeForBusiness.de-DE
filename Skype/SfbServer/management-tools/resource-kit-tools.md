---
title: Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit hilft Ihnen, Routineaufgaben für IT-Administratoren zu vereinfachen, die Skype for Business Server 2015 bereitstellen und verwalten. Beispielsweise kann das Tool Web Conf Data verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden. Mithilfe des SEFAUtil-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.
ms.openlocfilehash: 0087f4286246833f0266ad0c78636bad00167756
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992532"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="b9276-107">Dokumentation zu den Tools im Resource Kit von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9276-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="b9276-108">In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="b9276-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="b9276-109">Das Skype for Business Server 2015 Resource Kit hilft Ihnen, Routineaufgaben für IT-Administratoren zu vereinfachen, die Skype for Business Server 2015 bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="b9276-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="b9276-110">Beispielsweise kann das Tool **Web Conf Data** verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="b9276-111">Mithilfe des **SEFAUtil**-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten.</span><span class="sxs-lookup"><span data-stu-id="b9276-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="b9276-112">Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="b9276-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="b9276-113">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="b9276-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="b9276-114">Um das Skype for Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) aus dem Download Center herunter.</span><span class="sxs-lookup"><span data-stu-id="b9276-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="b9276-p103">Führen Sie \*\*OCSResKit.msi \*\* aus, um eine einfache Installation durchzuführen. Die MSI-Datei installiert alle Tools im folgenden Pfad: **%ProgramFiles%\Skype for Business Server 2015\ResKit**. Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner. Tools, die über Hilfsdateien verfügen, befinden sich in eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="b9276-p103">Run **OCSResKit.msi** to do a simple installation. The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**. Tools that are self-contained executables are in this folder. Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="b9276-119">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="b9276-119">Supported Environments</span></span>

<span data-ttu-id="b9276-120">Das Resource Kit für Skype for Business Server 2015 sollte auf einem Server installiert werden, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, in der Regel für die Ausführung von Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9276-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="b9276-121">Resource Kit-Tools – Übersicht</span><span class="sxs-lookup"><span data-stu-id="b9276-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="b9276-122">Im folgenden finden Sie eine Liste der Tools, die im Skype for Business Server 2015 Resource Kit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="b9276-123">Im folgenden Abschnitt wird jedes Tool mit seinen Anforderungen und Beispielanwendungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9276-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="b9276-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="b9276-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="b9276-125">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="b9276-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="b9276-126">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="b9276-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="b9276-127">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="b9276-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="b9276-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="b9276-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="b9276-129">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="b9276-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="b9276-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="b9276-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="b9276-131">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="b9276-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="b9276-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="b9276-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="b9276-133">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="b9276-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="b9276-134">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="b9276-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="b9276-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="b9276-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="b9276-136">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="b9276-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="b9276-137">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="b9276-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="b9276-138">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="b9276-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="b9276-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="b9276-139">ABSConfig</span></span>
<span data-ttu-id="b9276-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-140"></span></span>

<span data-ttu-id="b9276-141">Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in Skype for Business Server 2015 anpassen können.</span><span class="sxs-lookup"><span data-stu-id="b9276-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="b9276-142">Mit diesem Tool können auch Administratoren von Skype for Business Server 2015 die Standardeinstellungen für den Adressbuchdienst wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b9276-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-143">Description</span></span>

<span data-ttu-id="b9276-144">ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienst Attribute konfigurieren können, die mit dem Adressbuchdienst verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="b9276-145">Dies sind die primären Verwendungsszenarien für das Tool:</span><span class="sxs-lookup"><span data-stu-id="b9276-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="b9276-146">So können Administratoren Attribute in den Active Directory-Domänendiensten den Attributen für Skype for Business Server 2015 zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b9276-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="b9276-147">Administratoren das Angeben des Attributs in Active Directory Domain Services ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder aus diesen ausgeschlossen werden soll</span><span class="sxs-lookup"><span data-stu-id="b9276-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="b9276-148">Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen</span><span class="sxs-lookup"><span data-stu-id="b9276-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="b9276-149">Das ABSConfig-Tool kann mithilfe der Datei "ABSConfig. exe" gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="b9276-150">Das Tool wird auf der Registerkarte **Attribute konfigurieren** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen von Active Directory-Domänendienst Attributen zu den Attributfeldern für Skype for Business Server 2015 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern enthalten oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9276-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="b9276-151">Darüber hinaus gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9276-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="b9276-152">Mit der Option **Standard wiederherstellen** können Administratoren die Einstellungen des Adressbuchdiensts auf Standardwerte zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="b9276-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="b9276-153">Die erneute Zuordnung von anzeigen Attributen zu unterschiedlichen OC-Feldnamen funktioniert nur für den Download von Adressbuchdateien und wird von der Adressbuch-Webabfrage nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b9276-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-154">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-154">Output</span></span>

<span data-ttu-id="b9276-155">ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b9276-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```PowerShell
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="b9276-156">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-156">Purpose</span></span>

<span data-ttu-id="b9276-157">ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen des Skype for Business Server 2015-Adressbuchdiensts.</span><span class="sxs-lookup"><span data-stu-id="b9276-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-158">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="b9276-159">Computer</span><span class="sxs-lookup"><span data-stu-id="b9276-159">Computer</span></span>

<span data-ttu-id="b9276-160">ABSConfig kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="b9276-161">Im Fall von Skype for Business Server 2015, Enterprise Edition, kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="b9276-162">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b9276-162">Network</span></span>

<span data-ttu-id="b9276-163">Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9276-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="b9276-164">Software</span><span class="sxs-lookup"><span data-stu-id="b9276-164">Software</span></span>

<span data-ttu-id="b9276-165">Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert werden:</span><span class="sxs-lookup"><span data-stu-id="b9276-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="b9276-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9276-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="b9276-167">Benutzer</span><span class="sxs-lookup"><span data-stu-id="b9276-167">Users</span></span>

<span data-ttu-id="b9276-168">Administratoren, die über die erforderlichen Berechtigungen verfügen, um die Bereitstellung von Skype for Business Server 2015 zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-169">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-169">Examples</span></span>

<span data-ttu-id="b9276-p108">ABSConfig kann durch Eingeben von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.</span><span class="sxs-lookup"><span data-stu-id="b9276-p108">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

![Das Tool "ABSConfig. exe".](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="b9276-173">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-173">Summary</span></span>

<span data-ttu-id="b9276-174">Das ABSConfig-Tool bietet Administratoren ein schnelles und einfach zu Bedientool zum Anpassen des Skype for Business Server 2015-Adressbuchdiensts.</span><span class="sxs-lookup"><span data-stu-id="b9276-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="b9276-175">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="b9276-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="b9276-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-176"></span></span>

<span data-ttu-id="b9276-177">Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Elemente anzeigen:</span><span class="sxs-lookup"><span data-stu-id="b9276-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="b9276-178">Alle konfigurierten Skype for Business Server 2015-Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie</span><span class="sxs-lookup"><span data-stu-id="b9276-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="b9276-179">Die Verbindungen, die jeder Dienst mit anderen Bandbreiten-Richtliniendiensten und Edgeservern herstellt</span><span class="sxs-lookup"><span data-stu-id="b9276-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="b9276-180">Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die von den einzelnen Bandbreiten-Richtliniendiensten gemeldete Echtzeit-Bandbreitennutzung</span><span class="sxs-lookup"><span data-stu-id="b9276-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="b9276-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-181">Description</span></span>

<span data-ttu-id="b9276-p109">Das Tool Bandwidth Policy Service Monitor ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Administratoren starten das Tool durch Ausführen der Datei „PDPMonUI.exe“.</span><span class="sxs-lookup"><span data-stu-id="b9276-p109">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="b9276-p110">Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreiten-Richtliniendienste in der Topologie zu ermitteln. Nach Abschluss der anfänglichen Aktualisierung wird der linke Bereich im Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.</span><span class="sxs-lookup"><span data-stu-id="b9276-p110">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="b9276-p111">Wenn Administratoren einen bestimmten Bandbreiten-Richtliniendienst auswählen, werden im rechten Bereich die Informationen zu dem jeweiligen Dienst angezeigt. Dieser Bereich enthält außerdem zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-p111">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="b9276-188">Registerkarte „Machine Info“</span><span class="sxs-lookup"><span data-stu-id="b9276-188">Machine Info Tab</span></span>

<span data-ttu-id="b9276-189">Auf der Registerkarte **Machine Info** werden die Details des ausgewählten Bandbreiten-Richtliniendiensts angezeigt sowie die Liste und die Zustände aller Verbindungen, die der ausgewählte Bandbreiten-Richtliniendienst mit anderen Diensten herstellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="b9276-190">Registerkarte „Topology Info“</span><span class="sxs-lookup"><span data-stu-id="b9276-190">Topology Info Tab</span></span>

<span data-ttu-id="b9276-p112">Auf der Registerkarte **Topology Info** wird eine Liste aller Verbindungen angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Bandbreitenkapazität für Audio und Video angezeigt. Zusätzlich wird die zurzeit verwendete Bandbreite in KB/s und als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierungen zum Hervorheben von Verbindungen, deren Nutzung fast der Kapazität entspricht. So können Administratoren solche Verbindungen schnell erkennen.</span><span class="sxs-lookup"><span data-stu-id="b9276-p112">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="b9276-195">Wenn das Tool für den bandbreitenrichtliniendienst Monitor beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreitenrichtlinien Dienste einen Fehler auftritt, werden die Informationen in den **Computer Informationen** und auf den Registerkarteninformationen zur **Topologie** nicht ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b9276-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="b9276-196">Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht.</span><span class="sxs-lookup"><span data-stu-id="b9276-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="b9276-197">In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="b9276-198">Beide Registerkarten enthalten einen Zeitstempel **Last Updated**, mit dessen Hilfe Administratoren bestimmen können, wann die Daten für einen bestimmten Bandbreiten-Richtliniendienst zum letzten Mal aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9276-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-199">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-199">Output</span></span>

<span data-ttu-id="b9276-200">Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt auf der grafischen Hauptbenutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="b9276-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-201">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-201">Purpose</span></span>

<span data-ttu-id="b9276-p114">Das Tool Bandwidth Policy Service Monitor soll Administratoren Einblick in den Zustand jedes Bandbreiten-Richtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeit-Bandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-p114">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-204">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-204">Requirements</span></span>

<span data-ttu-id="b9276-205">Das Tool für bandbreitenrichtliniendienst Monitor muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server-Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="b9276-206">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-206">Summary</span></span>

<span data-ttu-id="b9276-207">Das Tool Bandwidth Policy Service Monitor kann eine wertvolle Ressource für Administratoren sein, um den Zustand aller Bandbreiten-Richtliniendienste in der Topologie untersuchen zu können. Wichtiger noch ist, dass die Echtzeit-Bandbreitenauslastung für die Verbindungen ermittelt werden kann, die in den Netzwerkkonfigurationseinstellungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="b9276-208">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="b9276-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="b9276-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-209"></span></span>

<span data-ttu-id="b9276-p115">Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Muster des Bandbreitenverbrauchs analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b9276-p115">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-212">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-212">Description</span></span>

<span data-ttu-id="b9276-p116">Bandwidth Utilization Analyzer ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Dieses Tool erzeugt Berichte speziell für die Audionutzung über das Netzwerk und hilft bei der Kapazitätsplanung. Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-p116">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-216">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-216">Output</span></span>

<span data-ttu-id="b9276-217">Bandwidth Utilization Analyzer bietet grafische Diagramme der Bandbreitenkapazität und -auslastung durch Audio für alle WAN-Verbindungen, die im System konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-218">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-218">Purpose</span></span>

<span data-ttu-id="b9276-219">Bei jeder sprach-und Videobereitstellung ist es wichtig, den Trend der Bandbreitennutzung von Mediendatenverkehr im gesamten Unternehmensnetzwerk zu überwachen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="b9276-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="b9276-220">Genau dies ermöglicht das Tool Bandwidth Utilization Analyzer Administratoren.</span><span class="sxs-lookup"><span data-stu-id="b9276-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="b9276-221">Das Tool bietet folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="b9276-221">This tool does the following:</span></span>

- <span data-ttu-id="b9276-222">Erzeugung spezifischer Berichte für die Audionutzung über das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b9276-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="b9276-223">Hilfe bei einer effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="b9276-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="b9276-224">Bandwidth Utilization Analyzer kann aus Bandbreitenkapazitäts- und -auslastungsberichten die folgenden grafischen Diagramme generieren:</span><span class="sxs-lookup"><span data-stu-id="b9276-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="b9276-225">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="b9276-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="b9276-226">Gefiltert nach ausgewählten WAN-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="b9276-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="b9276-227">Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="b9276-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="b9276-228">Gefiltert nach WAN-Verbindungen, die nicht die gesamte bereitgestellte Bandbreite nutzen</span><span class="sxs-lookup"><span data-stu-id="b9276-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="b9276-229">Gefiltert nach WAN-Verbindungen, die kritische Grenzwerte erreicht haben (eine Bandbreitenauslastung von mehr als 90 % der Bandbreitenkapazität der WAN-Verbindung)</span><span class="sxs-lookup"><span data-stu-id="b9276-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="b9276-230">Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts</span><span class="sxs-lookup"><span data-stu-id="b9276-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="b9276-231">Gefiltert nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="b9276-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="b9276-232">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b9276-232">Applications</span></span>

<span data-ttu-id="b9276-233">Bandwidth Utilization Analyzer besteht aus den zwei folgenden Anwendungen (Tools):</span><span class="sxs-lookup"><span data-stu-id="b9276-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="b9276-234">**WanLinkLogCollector. exe** mit diesem Tool kann der Benutzer die erforderlichen Informationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="b9276-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="b9276-235">**BandwidthUtilizationAnalyzer. xlsm** ein Microsoft Excel-Kalkulationstabellen-softwarebericht wird automatisch von WanLinkLogCollector. exe gestartet.</span><span class="sxs-lookup"><span data-stu-id="b9276-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="b9276-236">Mit dieser Anwendung können Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anwenden.</span><span class="sxs-lookup"><span data-stu-id="b9276-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="b9276-237">Phasen der Verwendung von Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="b9276-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b9276-238">Es gibt zwei Phasen bei der Verwendung von Bandwidth Utilization Analyzer:</span><span class="sxs-lookup"><span data-stu-id="b9276-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="b9276-239">Erfassen von Protokollen mithilfe von „WanLinkLogCollector.exe“</span><span class="sxs-lookup"><span data-stu-id="b9276-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="b9276-240">Anpassen von Berichten mithilfe von „BandwidthUtilizationAnalyzer.xlsm“</span><span class="sxs-lookup"><span data-stu-id="b9276-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9276-241">„BandwidthUtilizationAnalyzer.xlsm“ sollte auf keinen Fall manuell von Endbenutzern gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="b9276-242">Starten von Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="b9276-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="b9276-243">Starten Sie „WanLinkLogCollector.exe“ an der Eingabeaufforderung oder mithilfe von Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="b9276-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="b9276-244">**Verwenden von „WanLinkLogCollector.exe“**</span><span class="sxs-lookup"><span data-stu-id="b9276-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="b9276-245">„WanLinkLogCollector.exe“ wird in drei Schritten verwendet:</span><span class="sxs-lookup"><span data-stu-id="b9276-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="b9276-246">**Protokollieren der Zeitachse** Bereitstellen der Zeitachse, für die der Bericht generiert werden muss</span><span class="sxs-lookup"><span data-stu-id="b9276-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="b9276-247">**Angeben der Dateiverzeichnisse** Bereitstellen von Dateispeicherort Informationen</span><span class="sxs-lookup"><span data-stu-id="b9276-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="b9276-248">**Sammeln der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts</span><span class="sxs-lookup"><span data-stu-id="b9276-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="b9276-249">Schritt 1 – Protokollieren des Zeitraums</span><span class="sxs-lookup"><span data-stu-id="b9276-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="b9276-250">Durch die Protokollierung des Zeitraums können die Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben. </span><span class="sxs-lookup"><span data-stu-id="b9276-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="b9276-251">**Startdatum** Dies ist das Startdatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 1. August 2010.</span><span class="sxs-lookup"><span data-stu-id="b9276-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="b9276-252">**Enddatum** Dies ist das Enddatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 30. September 2010.</span><span class="sxs-lookup"><span data-stu-id="b9276-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Anfangs-und Endtermine in der Bandbreitennutzung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="b9276-254">Schritt 2 – Angeben der Dateiverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="b9276-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="b9276-255">Die folgenden Dateiverzeichnisse können von den Benutzern wie gezeigt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="b9276-256">**Speicherort für Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="b9276-257">Dies ist in der \<Regel in\> \\ Fileserver<Wahl\>von FE \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="b9276-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="b9276-258">**Speicherort für temporären Dateispeicher** Der Speicherort der temporären Datei, in dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

![Dateiverzeichnisse in der Bandbreitennutzung Anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> <span data-ttu-id="b9276-260">Stellen Sie sicher, dass den Benutzern des Tools ausreichender Dateizugriff auf den Speicherort der Serverprotokolle und der temporären Dateien gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="b9276-261">Schritt 3 – Erfassen der Protokolle und Starten der Berichtanzeige</span><span class="sxs-lookup"><span data-stu-id="b9276-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="b9276-p120">Um die Protokolle zu erfassen und die Berichtanzeige zu starten, klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.</span><span class="sxs-lookup"><span data-stu-id="b9276-p120">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

![Sammeln von Daten in der Bandbreitennutzung Analy](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="b9276-265">Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Protokolliert die gesammelte Benachrichtigung in der Bandbreiten-utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="b9276-p121">Klicken Sie auf **OK**. „BandwidthUtilizationAnalyzer.xlsm“ wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**.</span><span class="sxs-lookup"><span data-stu-id="b9276-p121">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="b9276-271">Verwenden von „BandwidthUtilizationAnalyzer.xlsm“</span><span class="sxs-lookup"><span data-stu-id="b9276-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="b9276-272">Wenn „BandwidthUtilizationAnalyzer.xlsm“ automatisch gestartet wurde, klicken Sie wie unten gezeigt auf **Refresh**.</span><span class="sxs-lookup"><span data-stu-id="b9276-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="b9276-p122">Wenn ein Dateiordner geöffnet wird, wählen Sie die Datei „consolidated.csv“ an dem Speicherort aus, der in dem unten gezeigten Meldungsfeld angegeben ist. Dort wird außerdem der Speicherort **C:\Temp** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-p122">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below. It also shows the location as **C:\Temp**.</span></span>

     ![Öffnen eines Ordners in BandwidthUtilizationAnalyzer](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="b9276-277">Klicken Sie auf **Import**.</span><span class="sxs-lookup"><span data-stu-id="b9276-277">Click **Import**.</span></span>

4. <span data-ttu-id="b9276-p123">Das grafische Diagramm wird automatisch generiert. Es ist verfügbar, sobald der Hintergrundaktivitäts-Mauszeiger nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-p123">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>

     ![Anwenden von Filtern in der Berichtsansicht](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="b9276-281">Anwenden von Filtern auf die Berichtsansicht</span><span class="sxs-lookup"><span data-stu-id="b9276-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="b9276-282">Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden nachfolgend beschrieben:</span><span class="sxs-lookup"><span data-stu-id="b9276-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Anwenden von Filtern in der Berichtsansicht](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="b9276-284">**Name** Filtern nach WAN-Verbindungen (der Filter befindet sich rechts von der Grafik). Das Präfix identifiziert die folgenden Verbindungstypen, siehe im vertikalen (blauen) Feld:</span><span class="sxs-lookup"><span data-stu-id="b9276-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="b9276-285">**S Site** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="b9276-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="b9276-286">**IS Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="b9276-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="b9276-287">**R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="b9276-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="b9276-288">**Exceeded limit** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung die Bandbreitenkapazität übersteigt</span><span class="sxs-lookup"><span data-stu-id="b9276-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="b9276-289">**Critical levels** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mindestens 90 % der Bandbreitenkapazität erreicht hat</span><span class="sxs-lookup"><span data-stu-id="b9276-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="b9276-290">**Under-utilized** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="b9276-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="b9276-291">**Link type** Filtern nach den folgenden WAN-Verbindungstypen:</span><span class="sxs-lookup"><span data-stu-id="b9276-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="b9276-292">
            Typ **Network site**</span><span class="sxs-lookup"><span data-stu-id="b9276-292">**Network site** type</span></span>

   - <span data-ttu-id="b9276-293">
            Typ **Inter-site**</span><span class="sxs-lookup"><span data-stu-id="b9276-293">**Inter-site** type</span></span>

   - <span data-ttu-id="b9276-294">
            Typ \*\*Inter-Region link**</span><span class="sxs-lookup"><span data-stu-id="b9276-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="b9276-295">**Region** Filtern nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="b9276-295">**Region** Filter by network region</span></span>

<span data-ttu-id="b9276-296">Die folgenden Abbildungen zeigen die oben beschriebenen Filter.</span><span class="sxs-lookup"><span data-stu-id="b9276-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="b9276-p124">Filtern nach **Name**. Wählen Sie die Liste der Verbindungen aus, die in dem Diagramm angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9276-p124">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

![Filtern nach Name in BandwidthUtilizationAnalyzer](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="b9276-300">Filtern nach **Exceeded limit**.</span><span class="sxs-lookup"><span data-stu-id="b9276-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="b9276-301">Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b9276-301">Select **True** to enforce the filter.</span></span>

![Filterung nach Überschreitung des Grenzwerts.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="b9276-303">Filtern nach **Critical levels**.</span><span class="sxs-lookup"><span data-stu-id="b9276-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="b9276-304">Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b9276-304">Select **True** to enforce the filter.</span></span>

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="b9276-306">Filtern nach **Under utilized**.</span><span class="sxs-lookup"><span data-stu-id="b9276-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="b9276-307">Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b9276-307">Select **True** to enforce the filter.</span></span>

![Filtern nach unter verwendet.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="b9276-309">Filtern nach **Link Type**.</span><span class="sxs-lookup"><span data-stu-id="b9276-309">Filter by **Link Type**.</span></span> <span data-ttu-id="b9276-310">Wählen Sie die Typen aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9276-310">Select the type or types that need to be displayed.</span></span>

![Filtern nach Verknüpfungstyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="b9276-312">Filtern nach **Region**.</span><span class="sxs-lookup"><span data-stu-id="b9276-312">Filter by **Region**.</span></span> <span data-ttu-id="b9276-313">Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b9276-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="b9276-315">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-315">Requirements</span></span>

- <span data-ttu-id="b9276-316">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="b9276-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="b9276-317">Microsoft Excel 2010 oder Excel 2007</span><span class="sxs-lookup"><span data-stu-id="b9276-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="b9276-318">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-318">Summary</span></span>

<span data-ttu-id="b9276-p130">Bandwidth Utilization Analyzer wird verwendet, um die Bandbreitenauslastung durch Audio für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann auch die Bandbreitenauslastung durch Video im Netzwerk dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-p130">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="b9276-321">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="b9276-321">Call Parkometer</span></span>
<span data-ttu-id="b9276-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-322"></span></span>

<span data-ttu-id="b9276-323">Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Datenbank mit den Orbits der geparkten Anrufe ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b9276-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-324">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-324">Description</span></span>

<span data-ttu-id="b9276-325">Call Parkometer ist ein Tool zum Nachverfolgen der zurzeit geparkten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="b9276-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="b9276-326">Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS).</span><span class="sxs-lookup"><span data-stu-id="b9276-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="b9276-327">Dieses Befehlszeilentool bietet Lese-und Schreibzugriff auf die CPS-Orbit-SQL Server-Datenbank von einem lokalen oder Remote verbundenen Computer.</span><span class="sxs-lookup"><span data-stu-id="b9276-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="b9276-328">Alle Optionen schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="b9276-328">All options are mutually exclusive.</span></span> <span data-ttu-id="b9276-329">Befehlszeilensyntax:</span><span class="sxs-lookup"><span data-stu-id="b9276-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="b9276-330">**-o-** Parameter – listet alle für diesen Pool konfigurierten Umlaufbahn Bereiche auf.</span><span class="sxs-lookup"><span data-stu-id="b9276-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="b9276-331">**-n-** Parameter – listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf.</span><span class="sxs-lookup"><span data-stu-id="b9276-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="b9276-332">Folgende Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b9276-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="b9276-333">Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person</span><span class="sxs-lookup"><span data-stu-id="b9276-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="b9276-334">Der Hostname des Anrufparkservers, auf dem der Anruf geparkt ist</span><span class="sxs-lookup"><span data-stu-id="b9276-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="b9276-335">Der Zeitstempel, aus dem hervorgeht, wann der Anruf geparkt wurde</span><span class="sxs-lookup"><span data-stu-id="b9276-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="b9276-336">**-f-** Parameter: Listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf.</span><span class="sxs-lookup"><span data-stu-id="b9276-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="b9276-337">**-r \<n\> -** Parameter: listet \<die\> n letzten geparkten Anrufe auf.</span><span class="sxs-lookup"><span data-stu-id="b9276-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="b9276-338">Folgende Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b9276-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="b9276-339">SIP-URI der geparkten Person</span><span class="sxs-lookup"><span data-stu-id="b9276-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="b9276-340">SIP-URI der parkenden Person</span><span class="sxs-lookup"><span data-stu-id="b9276-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="b9276-341">Der Hostname des Anrufparkservers, auf dem der Anruf geparkt wurde</span><span class="sxs-lookup"><span data-stu-id="b9276-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="b9276-342">Der Zeitstempel, aus dem hervorgeht, wann der Anruf herangeholt oder abgebrochen wurde</span><span class="sxs-lookup"><span data-stu-id="b9276-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="b9276-343">\*\*-t\<n\> \*\* Parameter – testet, wie eine Umlaufbahn in der Datenbank reserviert wird, um die Zufälligkeit der zugewiesenen Orbit-Nummern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-344">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-344">Output</span></span>

<span data-ttu-id="b9276-345">Abhängig von den Eingabeparametern, die an der Eingabeaufforderung angegeben werden, zeigt Call Parkometer folgende Ausgaben an:</span><span class="sxs-lookup"><span data-stu-id="b9276-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="b9276-346">Alle für diesen Pool konfigurierten Orbitbereiche</span><span class="sxs-lookup"><span data-stu-id="b9276-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="b9276-347">Zurzeit geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="b9276-347">Currently parked calls</span></span>

- <span data-ttu-id="b9276-348">Anzahl der freien (verfügbaren) Orbits</span><span class="sxs-lookup"><span data-stu-id="b9276-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="b9276-349">Zuletzt geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="b9276-349">Recently parked calls</span></span>

- <span data-ttu-id="b9276-350">Für das Testen einheitlicher und zufälliger Orbitwerte reservierte Orbits</span><span class="sxs-lookup"><span data-stu-id="b9276-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-351">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-351">Purpose</span></span>

<span data-ttu-id="b9276-p135">Das Anrufparkserver-Tool soll Befehlszeilenzugriff auf die Anrufparkserver-Datenbank ermöglichen. Administratoren können die Anrufparkserver-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-p135">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-354">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-354">Requirements</span></span>

<span data-ttu-id="b9276-355">Wenn das Tool auf dem gleichen Computer wie der Anrufparkserver ausgeführt wird, gelten keine Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="b9276-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="b9276-356">Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Skype for Business Server 2015 verwendete SQL Server-Datenbank so konfiguriert sein, dass der Remotezugriff zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="b9276-357">Anruf Parkometer muss mit einer SQL Server-Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9276-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="b9276-358">Diese SQL Server-Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Sie muss sich im gleichen Verzeichnis befinden, in dem sich parkometer. exe befindet.</span><span class="sxs-lookup"><span data-stu-id="b9276-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="b9276-359">Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (beispielsweise mydomain\Administrator), Kennwort (beispielsweise mypassword) und Hostname (beispielsweise MyServer).</span><span class="sxs-lookup"><span data-stu-id="b9276-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

```xml
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

### <a name="examples"></a><span data-ttu-id="b9276-360">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-360">Examples</span></span>

<span data-ttu-id="b9276-361">Bereitgestellte Umlaufbahn Bereiche: der Parameter-o listet alle für diesen Pool konfigurierten Umlaufbahn Bereiche auf (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="b9276-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Umlaufbahn Bereiche in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="b9276-363">Derzeit geparkte Anrufe: der Parameter-n listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="b9276-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Zurzeit geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="b9276-365">Anzahl der freien Umlaufbahnen: der Parameter-f zeigt die Anzahl der derzeit freien Umlaufbahnen im Pool an (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="b9276-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Freie Umlaufbahnen in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="b9276-367">Zuletzt geparkte Anrufe: der Parameter \<-\> r n listet \<die\> n letzten geparkten Anrufe auf, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Vor kurzem geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="b9276-369">Test Orbit-Reservierung: der- \<t\> n-Parameter testet, wie eine Umlaufbahn in der Datenbank reserviert wird (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="b9276-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testen Sie Orbit-Reservierungen in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="b9276-371">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-371">Summary</span></span>

<span data-ttu-id="b9276-372">Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="b9276-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="b9276-373">DBAnalyze</span></span>
<span data-ttu-id="b9276-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-374"></span></span>

### <a name="description"></a><span data-ttu-id="b9276-375">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-375">Description</span></span>

<span data-ttu-id="b9276-376">Dbanalyze ist ein Befehlszeilentool, das Administratoren hilft, Analyseberichte zu den Skype for Business Server 2015-Datenbanken zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="b9276-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="b9276-377">DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:</span><span class="sxs-lookup"><span data-stu-id="b9276-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="b9276-378">**Diagnosemodus** Erstellt einen Bericht, der Informationen zu Tabellen enthält (Anzahl der Datensätze, Fragmentierung, Datengröße, und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern, auf denen Microsoft Office Communications Server ausgeführt wird, die durchschnittliche Anzahl der Berechtigungen, Kontakte, Container, Abonnements, Publikationen, Endpunkte pro Benutzer, nicht ordnungsgemäß vernetzte Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, und die Datenbankversion.</span><span class="sxs-lookup"><span data-stu-id="b9276-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9276-379">Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="b9276-380">**Benutzerdaten Modus** Meldet Kontakt-, Container-, Abonnement-, Veröffentlichungs-, Genehmigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben.</span><span class="sxs-lookup"><span data-stu-id="b9276-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="b9276-381">Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="b9276-382">**Konferenzmodus** Meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Details zur Terminplanung für die Konferenz, der Liste der eingeladenen Personen, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und des Signalisierungs Status jedes Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="b9276-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="b9276-383">**Decodieren der Besprechungs-ID** Decodiert eine vom **/pstnid** -Schalter angegebene PSTN-Besprechungs-ID (Public Switched Telephone Network), aber keine Verbindung zum Back-End, um detaillierte Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9276-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="b9276-384">**Konferenz auflösen** Dekodiert eine vom **/pstnid** -Schalter angegebene PSTN-Besprechungs-ID und zeigt Informationen zu der Konferenz an, die von der ID angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="b9276-385">**MCU-Modus** Meldet die ID, den Medientyp, die URL, den Heartbeat-Status, die Konferenz Auslastung und die Teilnehmer Auslastung für jede MCU im Pool.</span><span class="sxs-lookup"><span data-stu-id="b9276-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="b9276-386">**Datenträger-Fragmentierungs Modus** Zeigt den Fragmentierungs Status aller Datenträger an.</span><span class="sxs-lookup"><span data-stu-id="b9276-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="b9276-p139">Dieses Tool kann zum Diagnostizieren verschiedener Probleme verwendet werden oder Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A verwalteten Benutzer auf Server B verwaltete Benutzer als Kontakte wählen, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen den Servern zu verringern.</span><span class="sxs-lookup"><span data-stu-id="b9276-p139">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-389">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-389">Output</span></span>

<span data-ttu-id="b9276-390">Dieses Tool gibt vordefinierte Berichte über die Skype for Business Server 2015-Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="b9276-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="b9276-391">**Pfad**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span><span class="sxs-lookup"><span data-stu-id="b9276-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-392">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-392">Purpose</span></span>

<span data-ttu-id="b9276-393">Wenn Sie Dbanalyze. exe installieren möchten, kopieren Sie Sie in einen lokalen Ordner, und führen Sie dann das Tool aus.</span><span class="sxs-lookup"><span data-stu-id="b9276-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="b9276-394">Führen Sie den folgenden Befehl in der Befehlszeile aus, um das Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9276-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="b9276-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Befehlszeilenoptionen für "Dbanalyze. exe".](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="b9276-397">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b9276-397">Requirements</span></span>

 <span data-ttu-id="b9276-398">**Computer** Dbanalyze kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem Skype for Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="b9276-399">**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9276-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="b9276-400">**Software** Die Softwarekomponenten von Skype for Business Server 2015 müssen vor der Ausführung von Dbanalyze installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="b9276-401">**Benutzer** In der folgenden Tabelle sind die Administratoren aufgeführt, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="b9276-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Berechtigungstabelle für "Dbanalyze. exe".](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="b9276-403">Für den **/report:disk**-Modus ist ein lokales Administratorkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9276-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-404">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-404">Examples</span></span>

<span data-ttu-id="b9276-405">Hier sind Beispiele für gültige „Dbanalyze.exe“-Befehle:</span><span class="sxs-lookup"><span data-stu-id="b9276-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="b9276-406">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-406">Summary</span></span>

<span data-ttu-id="b9276-407">Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse von Skype for Business Server 2015-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="b9276-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="b9276-408">Import Storage Service Data</span><span class="sxs-lookup"><span data-stu-id="b9276-408">Import Storage Service Data</span></span>
<span data-ttu-id="b9276-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-409"></span></span>

<span data-ttu-id="b9276-410">Mit dem Resource Kit-Tool „ImportStorageServiceData“ können Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, wieder zurück in den Speicherdienst importiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-411">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-411">Description</span></span>

<span data-ttu-id="b9276-412">Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein.</span><span class="sxs-lookup"><span data-stu-id="b9276-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="b9276-413">Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets „StorageServiceFullFlush“ (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein.</span><span class="sxs-lookup"><span data-stu-id="b9276-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="b9276-414">Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, weil dies wahrscheinlich dazu führt, dass mehr Daten wieder exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange anwächst, zunächst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).</span><span class="sxs-lookup"><span data-stu-id="b9276-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="b9276-415">**Szenario 1:** während des Pool-Failovers können Dateien für jedes Front-End vom Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="b9276-416">Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="b9276-417">**Szenario 2:** die Daten werden jeden Tag automatisch geleert oder als Antwort auf eine Speicherdienst Datenbank, die bestimmte Größengrenzwerte überschreitet (beispielsweise 60%, 80%, 90% voll).</span><span class="sxs-lookup"><span data-stu-id="b9276-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="b9276-418">Diese automatisch geleerten Daten sollten vom Administrator routinemäßig erneut importiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="b9276-419">Wenn das SCOM-Überwachungspaket nicht bereitgestellt wird, gibt es in der obigen Situation Ereignisse für den Skype for Business Server-Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="b9276-420">Ereignis-IDs von 32075 (vollständiger Flush-Vorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Maintenance Level Flush Complete), 32089 (Flush ist aufgrund des Auffüllens der Datenbank aufgetreten).</span><span class="sxs-lookup"><span data-stu-id="b9276-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="b9276-421">Hinweis Diese Ereignis-IDs entsprechen der RTM-Version.</span><span class="sxs-lookup"><span data-stu-id="b9276-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="b9276-422">Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien vorhanden sind, die geleert wurden. Diese Daten sollten routinemäßig mit diesem Tool wieder importiert werden, beispielsweise einmal pro Woche.</span><span class="sxs-lookup"><span data-stu-id="b9276-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="b9276-423">Wenn für die Online Dienstversion die Statusüberwachung SCOM Pack für Skype for Business Server bereitgestellt wird, gibt es neue Benachrichtigungen, die vom Administrator aufgefordert werden, die leeren Daten wieder in den Speicherdienst zu importieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="b9276-424">Im Ereignisprotokoll auf dem Front-End-Server befindet sich ein entsprechendes Ereignis, das die Benachrichtigung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="b9276-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="b9276-425">Das Ereignis enthält eine Beschreibung des übergeordneten Pfads, unter dem sich die gelesenen Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b9276-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="b9276-426">Bei den Warnungskriterien handelt es sich um x oder mehr Dateien unter dem bestimmten übergeordneten Pfad, die mindestens Y Tage alt sind (wobei x und Y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei überschrieben werden können). Nachfolgend werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können, wobei der Unterschied der übergeordnete Pfad ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="b9276-427">Eine Möglichkeit ist unter Web Service File Share zu finden, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="b9276-428">(Beispiel: c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="b9276-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="b9276-429">Der Administrator führt dann dieses reskit-Tool aus.</span><span class="sxs-lookup"><span data-stu-id="b9276-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="b9276-430">Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="b9276-431">Wir empfehlen die Ausführung dieses Tools, wenn die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="b9276-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="b9276-432">Darüber hinaus kann dieses Tool zwei bis drei Minuten für den Import einer Datendatei benötigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="b9276-433">Denken Sie hieran, wenn Sie die voraussichtliche Ausführungsdauer des Tools schätzen.</span><span class="sxs-lookup"><span data-stu-id="b9276-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="b9276-434">Die von dem Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="b9276-435">Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB übersteigen kann.</span><span class="sxs-lookup"><span data-stu-id="b9276-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Beispiel Ereignisse für das Speicher Server-Ereignisprotokoll.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="b9276-437">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b9276-437">Requirements</span></span>

<span data-ttu-id="b9276-438">Installieren Sie die Skype for Business Server 2015 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="b9276-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="b9276-439">Das Tool wird auf von der Domäne verbundenen Computern ausgeführt, auf denen Skype for Business Server und die Skype for Business Server-Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="b9276-440">Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="b9276-441">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="b9276-442">Diese Datenbank wird vom Tool verwendet, um den Speicherort der Webservice-Dateifreigabe für den Pool abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b9276-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="b9276-443">Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools zunächst Windows PowerShell-Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer aktivieren, von dem aus das Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="b9276-444">Andernfalls schlagen die Remote-Windows PowerShell-Befehle dieses Tools fehl.</span><span class="sxs-lookup"><span data-stu-id="b9276-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="b9276-445">Windows PowerShell-Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="b9276-446">Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über die Berechtigung "Lesen/Schreiben" für die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="b9276-447">Andernfalls schlägt das Tool mit IO-Berechtigungsfehlern fehl.</span><span class="sxs-lookup"><span data-stu-id="b9276-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="b9276-448">Unter Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht unter dem BetriebssystemWindows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="b9276-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-449">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-449">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="b9276-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="b9276-450">LCSSync</span></span>
<span data-ttu-id="b9276-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-451"></span></span>

<span data-ttu-id="b9276-452">Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="b9276-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="b9276-453">Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als ein Active Directory-Domänendienst-Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der Skype for Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-454">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-454">Description</span></span>

 <span data-ttu-id="b9276-455">LCSSync verwendet die synchronisierten Active Directory-Domänendienste-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer für Skype for Business Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="b9276-456">Zum Bereitstelleneiner einmaligen Anmeldung muss das primäre Benutzerkonto dem Active Directory-Domänendienst-Kontaktobjekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="b9276-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="b9276-457">Dieses Tool hilft bei der Durchführung dieser Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="b9276-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="b9276-458">Das Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.</span><span class="sxs-lookup"><span data-stu-id="b9276-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="b9276-459">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-459">Summary</span></span>

<span data-ttu-id="b9276-460">Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015 in einer Multi-Forest-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b9276-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="b9276-461">Lookup User Console</span><span class="sxs-lookup"><span data-stu-id="b9276-461">Lookup User Console</span></span>
<span data-ttu-id="b9276-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-462"></span></span>

<span data-ttu-id="b9276-463">Das LookupUserConsole-Tool zeigt interne Skype for Business Server-Routinginformationen zu bestimmten Benutzern an.</span><span class="sxs-lookup"><span data-stu-id="b9276-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="b9276-464">Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und beim Routing zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-465">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-465">Description</span></span>

 <span data-ttu-id="b9276-466">Durch Ausführen von LookupUserConsole. exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne Skype for Business Server-Routinginformationen in Bezug auf diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="b9276-467">Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b9276-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-468">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-468">Requirements</span></span>

<span data-ttu-id="b9276-469">Installieren Sie das Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="b9276-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="b9276-470">Das Tool wird auf von der Domäne verbundenen Computern ausgeführt, auf denen Skype for Business Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-471">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-471">Examples</span></span>

<span data-ttu-id="b9276-472">C:\Program Files\Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="b9276-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="b9276-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="b9276-473">MsTurnPing</span></span>
<span data-ttu-id="b9276-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-474"></span></span>

<span data-ttu-id="b9276-475">Das MSTurnPing-Tool ermöglicht es einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-476">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-476">Description</span></span>

<span data-ttu-id="b9276-477">Das MSTurnPing-Tool ermöglicht es einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="b9276-478">Mit dem Tool können Administratoren die folgenden Tests durchführen:</span><span class="sxs-lookup"><span data-stu-id="b9276-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="b9276-479">A/V-Edgeservertest: Das Tool führt mit allen A/V-Edgeservern in der Topologie die folgenden Tests durch:</span><span class="sxs-lookup"><span data-stu-id="b9276-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="b9276-480">Überprüfen, ob der Skype for Business Server-Audio/Video-Authentifizierungsdienst gestartet wurde, und kann korrekte Anmeldeinformationen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="b9276-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="b9276-481">Überprüfen, ob der Skype for Business Server-Audio/Video-Edgedienst gestartet wurde und die Ressourcen auf dem externen Edge erfolgreich zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="b9276-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="b9276-482">Test für Bandbreiten-Richtliniendienste: Das Tool führt mit allen Servern in der Topologie, auf denen die Bandbreiten-Richtliniendienste ausgeführt werden, die folgenden Tests durch:</span><span class="sxs-lookup"><span data-stu-id="b9276-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="b9276-483">Überprüfen, ob der Skype for Business Server-bandbreitenrichtliniendienst (Authentication) gestartet wurde und geeignete Anmeldeinformationen ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="b9276-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="b9276-484">Überprüfen, ob der Skype for Business Server-bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="b9276-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="b9276-485">Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist. </span><span class="sxs-lookup"><span data-stu-id="b9276-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-486">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-486">Output</span></span>

<span data-ttu-id="b9276-487">Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="b9276-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="b9276-488">Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b9276-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="b9276-489">Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b9276-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="b9276-490">Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio/Video-Edgedienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b9276-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="b9276-491">Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b9276-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="b9276-492">Die Testergebnisse der Computer, die den Skype for Business Server 2015-bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b9276-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="b9276-493">Die Testergebnisse der Computer, die den Skype for Business Server 2015-bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b9276-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-494">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-494">Requirements</span></span>

- <span data-ttu-id="b9276-495">Dieses Tool muss auf einem Computer ausgeführt werden, der zur Topologie gehört und auf dem sich der lokale Speicher befindet.</span><span class="sxs-lookup"><span data-stu-id="b9276-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="b9276-496">Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-497">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-497">Examples</span></span>

<span data-ttu-id="b9276-498">Hier ist ein Beispiel für die Tooleingabe.</span><span class="sxs-lookup"><span data-stu-id="b9276-498">The following is an example of the tool input.</span></span>

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="b9276-499">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-499">Summary</span></span>

<span data-ttu-id="b9276-500">Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="b9276-501">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="b9276-501">Network Configuration Viewer</span></span>
<span data-ttu-id="b9276-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-502"></span></span>

<span data-ttu-id="b9276-503">Die Netzwerkkonfigurations-Anzeige kann von Skype for Business Server 2015 Communications Software-Administratoren verwendet werden, um die Anruf Zulassungs Steuerung (CAC)-Netzwerktopologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zu ermöglichen, wie etwa Sprach-oder Videoanrufe auf der Grundlage der angegebenen Bandbreitenkapazität.</span><span class="sxs-lookup"><span data-stu-id="b9276-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="b9276-504">Skype for Business Server 2015-Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit Skype for Business Server 2015 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-505">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-505">Description</span></span>

<span data-ttu-id="b9276-506">Mit Network Configuration Viewer („NetworkConfigurationViewer.exe“) können Administratoren die folgenden Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="b9276-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="b9276-507">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format.</span><span class="sxs-lookup"><span data-stu-id="b9276-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="b9276-508">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat</span><span class="sxs-lookup"><span data-stu-id="b9276-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="b9276-509">Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger</span><span class="sxs-lookup"><span data-stu-id="b9276-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="b9276-510">Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format</span><span class="sxs-lookup"><span data-stu-id="b9276-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="b9276-511">Anzeigen von Konfigurationsdaten der CAC-Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="b9276-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="b9276-512">Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht</span><span class="sxs-lookup"><span data-stu-id="b9276-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="b9276-513">Definieren benutzerdefinierter Connectors für Verbindungen in der CAC-Netzwerktopologie (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen)</span><span class="sxs-lookup"><span data-stu-id="b9276-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="b9276-514">Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="b9276-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-515">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-515">Purpose</span></span>

<span data-ttu-id="b9276-516">Anzeigen der Verbindungen in der CAC-Netzwerktopologie des Unternehmens auf einer grafischen Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="b9276-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-517">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-517">Examples</span></span>

 <span data-ttu-id="b9276-518">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format**: Skype for Business Server 2015-Administratoren können die Konfiguration der CAC-Netzwerktopologie auf jedem Skype for Business Server 2015-Computer mithilfe der Option **Netzwerkkonfiguration herunterladen** wie in der folgenden Abbildung dargestellt laden und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="b9276-519">Bei der Bereitstellung auf einem Computer, der keine Verbindung zum Skype for Business Server 2015-Konfigurationsspeicher hat, kann das Tool keine derartige Konfiguration herunterladen oder anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Herunterladen der Netzwerkkonfiguration.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="b9276-521">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format:** Skype for Business Server 2015 Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Dateifreigabespeicherort von Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9276-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="b9276-522">Skype for Business Server 2015-Administratoren können eine solche Datei in einem grafischen Format anzeigen, indem Sie die Option **Netzwerkkonfiguration öffnen** verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Öffnen einer Protokolldatei für den Bandbreitenrichtlinien Server](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="b9276-524">Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015-Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="b9276-525">Die gespeicherte Konfigurationsdatei kann dann offline als Grafik angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Speichern Sie die Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="b9276-527">Speichern und Speichern von CAC-Netzwerktopologie-Diagrammen im JPG-oder BMP-Format: Skype for Business Server 2015-Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie die Option **Netzwerk Konfigurations Diagramm als Bild speichern** verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Speichern der Netzwerkkonfiguration als Bild](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="b9276-529"><strong>Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:</strong> Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerk Websites, Bandbreiten Profile und IP-Adressen von Standort-Subnetzen in einem Text Format anzeigen, indem Sie die Option Netzwerkkonfigurationsdaten anzeigen verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Anzeigen von Netzwerkkonfigurationsdaten](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="b9276-531">**Anzeigen der CAC-Netzwerktopologie in einer Struktur Ansichtsformatvorlage:** Skype for Business Server 2015-Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsstil anzeigen, indem Sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="b9276-533">**Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Website-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links):** Skype for Business Server 2015-Administratoren können benutzerdefinierte grafische Connectors für CAC-Netzwerkkonfigurations-WAN-Links definieren, indem Sie die Einstellungen-Option verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="b9276-534">Dies erleichtert die Unterscheidung zwischen verschiedenen Netzwerkverbindungstypen, die in der Netzwerkkonfiguration bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="b9276-536">**Anzeigen der Informationen zur CAC-Netzwerktopologie, der Regionsinformationen und der bereitgestellten Bandbreitenrichtlinien:** Skype for Business Server 2015-Administratoren können verwandte CAC-Netzwerk Regionsinformationen, Website Informationen und Informationen zur Bereitstellung von CAC-Bandbreiten mithilfe der nachstehend aufgeführten Optionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="b9276-537">(Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)</span><span class="sxs-lookup"><span data-stu-id="b9276-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="b9276-539">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-539">Summary</span></span>

<span data-ttu-id="b9276-540">Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015-Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9276-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="b9276-541">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="b9276-541">Response Group Agent Live</span></span>
<span data-ttu-id="b9276-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-542"></span></span>

<span data-ttu-id="b9276-543">Die reaktionsgruppenanwendung bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b9276-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="b9276-544">Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9276-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="b9276-545">Das Tool für den Reaktionsgruppen-Agent Live Resource Kit behebt dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die durch Echtzeitinformationen zu Skype for Business-Kommunikationssoftware, wie etwa das vorhanden sein anderer Agents, verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-546">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-546">Description</span></span>

<span data-ttu-id="b9276-547">Response Group Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet.</span><span class="sxs-lookup"><span data-stu-id="b9276-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="b9276-548">Es handelt sich um eine erweiterte Version der Seite "Agentengruppen" (Zugriff über Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b9276-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-549">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-549">Purpose</span></span>

<span data-ttu-id="b9276-p161">Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agent-Gruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agent-Gruppen zugreifen. Dabei erfahren sie beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Response Group Agent Live zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-p161">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="b9276-553">Funktionen</span><span class="sxs-lookup"><span data-stu-id="b9276-553">Features</span></span>

<span data-ttu-id="b9276-554">Das Live Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem Skype for Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="b9276-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="b9276-555">Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst zur Verfügung gestellt werden (beispielsweise Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).</span><span class="sxs-lookup"><span data-stu-id="b9276-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="b9276-556">Die Abbildung unten zeigt die Hauptoberfläche von Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="b9276-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Das Live Tool für Reaktionsgruppen-Agents](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="b9276-558">Folgende drei Hauptfeatures stehen Agents in Response Group Agent Live zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b9276-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="b9276-559">**Anmeldung/** Abmeldung: Anders als bei der Seite "Agentengruppen" (barrierefrei über Skype for Business Server 2015) können sich die Agents für Reaktionsgruppen-Agents Live nur an-und abmelden.</span><span class="sxs-lookup"><span data-stu-id="b9276-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="b9276-560">Diese Anwendung bietet drei schnelle Methoden zum Anmelden oder Abmelden für Agents:</span><span class="sxs-lookup"><span data-stu-id="b9276-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="b9276-561">Klicken auf die Schaltflächen zum An-/Abmelden (grün und rot) in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="b9276-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="b9276-562">Klicken auf das Taskleistensymbol mit der rechten Maustaste und Auswählen von „Sign-in“ oder „Sign-out“</span><span class="sxs-lookup"><span data-stu-id="b9276-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="b9276-563">Verwenden konfigurierbarer Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="b9276-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="b9276-564">**Gruppenmitgliedschaft:** Wenn eine Agentengruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an.</span><span class="sxs-lookup"><span data-stu-id="b9276-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="b9276-565">Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="b9276-566">Agents können direkt von dort aus eine Chatnachricht senden oder andere Agents anrufen.</span><span class="sxs-lookup"><span data-stu-id="b9276-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="b9276-p165">**Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Statistiken werden minütlich aktualisiert. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der aktuellen Anzahl der wartenden Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-p165">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-571">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-571">Requirements</span></span>

<span data-ttu-id="b9276-572">Response Group Agent Live erfordert .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="b9276-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="b9276-573">Um die Anwesenheits-und Visitenkarten Funktionen nutzen zu können, muss Skype for Business lokal installiert sein (und ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="b9276-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="b9276-574">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b9276-574">Configuration</span></span>

<span data-ttu-id="b9276-p167">Response Group Agent Live kann mithilfe des Dialogfelds „Options“ in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus können Administratoren die Standardhostadresse definieren, indem sie die Eigenschaft „defaultHostAddress“ in der Datei „RGAgentLive.exe.config“ direkt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b9276-p167">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="b9276-p168">Die Abbildung unten zeigt das Dialogfeld „Options“, in dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld können Sie zugreifen, indem Sie auf der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche „Options“ klicken.</span><span class="sxs-lookup"><span data-stu-id="b9276-p168">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Das Dialogfeld "Live Optionen" des Reaktionsgruppen-Agents](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="b9276-580">Folgende drei unterschiedliche Einstellungen können in der Konfiguration von Response Group Agent Live angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="b9276-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="b9276-581">Host Adresse: Dies ist in der Regel der FQDN des webpools, der zum Home-Pool des Agents gehört.</span><span class="sxs-lookup"><span data-stu-id="b9276-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="b9276-582">Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).</span><span class="sxs-lookup"><span data-stu-id="b9276-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="b9276-583">Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="b9276-584">Die einzige Einschränkung besteht darin, dass beide Tastenkombinationen die "Windows-Logo"-Taste (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="b9276-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="b9276-585">Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-586">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-586">Examples</span></span>

<span data-ttu-id="b9276-587">Die Abbildung unten zeigt, wie Sie andere Agents anrufen oder ihnen eine Chatnachricht senden, indem Sie mit der rechten Maustaste im rechten Bereich auf den Kontakt klicken.</span><span class="sxs-lookup"><span data-stu-id="b9276-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Tätigen eines Anrufs oder Senden einer Chatnachricht](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="b9276-589">Die Abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b9276-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Anzeigen von Warteschlangeninformationen](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="b9276-591">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-591">Summary</span></span>

<span data-ttu-id="b9276-592">Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="b9276-593">Mit dem Live Resource Kit-Tool für Reaktionsgruppen-Agents können Skype for Business Server 2015-Administratoren ihren Agenten eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben auf eine schnellere und grafische Weise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b9276-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="b9276-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="b9276-594">SEFAUtil</span></span>
<span data-ttu-id="b9276-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-595"></span></span>

<span data-ttu-id="b9276-596">SEFAUtil (Secondary Extension Feature Activation) ist ein Befehlszeilentool, mit dem Skype for Business Server 2015 Communications Software-Administratoren und Helpdesk-Agents Stellvertretungen, Anrufweiterleitung und gleichzeitiges Klingeln konfigurieren können. Einstellungen für Teamanrufe und Gruppenanruf Abholung im Auftrag eines Skype for Business Server 2015-Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b9276-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="b9276-597">Das Tool ermöglicht es Administratoren auch, die für einen bestimmten Benutzer veröffentlichten Anrufweiterleitungseinstellungen abzufragen. Das SEFAUtil-Tool ermöglicht es dem Administrator, die Anrufweiterleitung zu aktivieren/zu deaktivieren/zu ändern oder gleichzeitig im Namen des Benutzers Klingeln zu lassen.</span><span class="sxs-lookup"><span data-stu-id="b9276-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="b9276-598">Der Administrator kann das Ziel (in Form eines SIP-URIs) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="b9276-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="b9276-599">Dieses Tool ermöglicht es Administratoren auch, Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzuzufügen oder zu entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9276-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="b9276-600">SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht es Skype for Business Server 2015-Administratoren und Helpdesk-Agents, Stellvertretungen, Anrufweiterleitung, gleichzeitiges Klingeln, Einstellungen für den Team Anruf und Abholung des Gruppenanrufs im Auftrag eines Skype zu konfigurieren. für Business Server 2015-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b9276-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="b9276-601">Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-602">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-602">Description</span></span>

<span data-ttu-id="b9276-603">Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="b9276-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="b9276-604">Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="b9276-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="b9276-605">Mit den Features in diesem Tool können Administratoren und Helpdesk-Agents die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b9276-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="b9276-606">Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Stellvertretung, gleichzeitiges Klingeln, Teamanruf- und Gruppenanrufannahme)</span><span class="sxs-lookup"><span data-stu-id="b9276-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="b9276-607">Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (einschließlich Ziel und Timer für „Keine Antwort“)</span><span class="sxs-lookup"><span data-stu-id="b9276-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="b9276-608">Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="b9276-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="b9276-609">Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b9276-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="b9276-610">Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b9276-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9276-611">Neu im Skype for Business Server 2015 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="b9276-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="b9276-612">Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)</span><span class="sxs-lookup"><span data-stu-id="b9276-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9276-613">Neu im Skype for Business Server 2015 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="b9276-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="b9276-614">Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="b9276-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b9276-615">Neu im Skype for Business Server 2015 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="b9276-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="b9276-616">Für das Tool gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="b9276-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="b9276-617">Nur für Benutzer unterstützt, die in einem Skype for Business-Server Pool verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="b9276-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="b9276-618">Keine Unterstützung für die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="b9276-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="b9276-619">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-619">Output</span></span>

<span data-ttu-id="b9276-p175">Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="b9276-p175">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-622">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-622">Purpose</span></span>

<span data-ttu-id="b9276-623">Hier sind einige der Hauptszenarien, in denen dieses Tool eingesetzt werden kann:</span><span class="sxs-lookup"><span data-stu-id="b9276-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="b9276-624">Bob ist Executive und wurde in die Skype for Business Server-Telefonie verschoben.</span><span class="sxs-lookup"><span data-stu-id="b9276-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="b9276-625">In seiner vorhandenen Nebenstellenanlage hat er Stellvertretungen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b9276-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="b9276-626">Im Rahmen des Umzugs in Skype for Business Server 2015 kann der Administrator Bobs Routing so konfigurieren, dass seine bereits vorhandene Delegierungs Konfiguration wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="b9276-p177">Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anruf eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum, alle Anrufe an ihre Büronummer an ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b9276-p177">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="b9276-631">Joes Anrufe an seine geschäftliche Rufnummer gehen zu seinem mobilen Anrufbeantworter, wenn er bei der Arbeit ist; in den meisten anderen Speicherorten scheint es jedoch richtig zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b9276-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="b9276-632">Der Helpdesk-Techniker ist in der Lage, Joes Routing-Konfiguration anzuzeigen, und erkennt, dass Joe das gleichzeitige Klingeln für sein Mobiltelefon konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="b9276-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="b9276-633">Der Techniker fragt Joe nach der mobilen Berichterstattung in seinem Büro und kann feststellen, dass die gleichzeitige Anruf Regel ist, was bewirkt, dass Anrufe an die Mobile Voicemail von Joe weitergeleitet werden, wenn die Netzwerkabdeckung schlecht ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="b9276-634">Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, bei dem alle Mitglieder für Teamanrufe konfiguriert sind, wenn es für Skype for Business Server 2015 aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass er alle seine neuen Teammitglieder umfasst. Darüber hinaus fügt der Administrator Mike als Team Anruf-Gruppenmitglied für alle Mitglieder in seinem Team hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9276-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="b9276-635">Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso besteht darin, allen Anrufern vom ersten Anruf an persönlichen Service zu bieten.</span><span class="sxs-lookup"><span data-stu-id="b9276-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="b9276-636">Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, kann das gleichzeitige Klingeln auf allen Telefonen bei Teamanrufen sehr störend für das Team sein.</span><span class="sxs-lookup"><span data-stu-id="b9276-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="b9276-637">Um den besten Service bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der Skype for Business Server 2015-Administrator die Funktion für Gruppenanruf-Pickups.</span><span class="sxs-lookup"><span data-stu-id="b9276-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="b9276-638">Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit.</span><span class="sxs-lookup"><span data-stu-id="b9276-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="b9276-639">Wenn nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.</span><span class="sxs-lookup"><span data-stu-id="b9276-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-640">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b9276-640">Requirements</span></span>

<span data-ttu-id="b9276-p180">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-p180">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="b9276-644">Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="b9276-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="b9276-645">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört.</span><span class="sxs-lookup"><span data-stu-id="b9276-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="b9276-646">Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:</span><span class="sxs-lookup"><span data-stu-id="b9276-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```PowerShell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="b9276-647">Auf allen Computern, auf denen das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="b9276-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="b9276-648">In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein.</span><span class="sxs-lookup"><span data-stu-id="b9276-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="b9276-649">Wenn Sie SEFAUtil als neue vertrauenswürdige Anwendung definieren möchten, verwenden Sie die Skype for Business Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="b9276-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```PowerShell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="b9276-650">Gegebenenfalls kann ein anderer Port verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9276-651">Pool-FQDN: der FQDN des Servers oder Pools, der die SEFAUtil-Anwendung hosten soll (in der Regel ein Skype for Business-Front-End-Server #a0 oder Pool).</span><span class="sxs-lookup"><span data-stu-id="b9276-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="b9276-652">Pool Registrar FQDN: der FQDN des Skype for Business-Front-End-Servers oder-Pools, der diesem Anwendungspool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="b9276-653">Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="b9276-654">Die Topologieänderungen müssen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="b9276-655">Das Aktivieren der Topologie-Änderungen kann über die Skype for Business Server-Verwaltungsshell erfolgen, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="b9276-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```PowerShell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="b9276-656">Falls erforderlich, installieren Sie die Skype for Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).</span><span class="sxs-lookup"><span data-stu-id="b9276-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="b9276-657">Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="b9276-658">Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="b9276-659">Standardmäßig befindet sich das Tool in: ". ..\Programme\Microsoft Files\Skype for Business Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="b9276-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="b9276-660">Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="b9276-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="b9276-661">Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="b9276-662">Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="b9276-662">Group Call Pickup</span></span>

<span data-ttu-id="b9276-663">Für die Gruppenanruf Abholung ist in Skype for Business Server 2015 eine zusätzliche Konfiguration erforderlich, damit die Funktion vollständig aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9276-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="b9276-664">Bevor Sie Benutzern Annahmegruppen zuweisen, sollten Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nachlesen.</span><span class="sxs-lookup"><span data-stu-id="b9276-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-665">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="b9276-666">Anzeigen aktueller Anrufbehandlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b9276-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="b9276-667">Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="b9276-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="b9276-668">In diesem Beispiel wird der Server-Schalter verwendet, um den Skype for Business-Server anzugeben, **mit dem eine** Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9276-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="b9276-669">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-669">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="b9276-670">Festlegen des Ziels für Anrufweiterleitung/Keine Antwort</span><span class="sxs-lookup"><span data-stu-id="b9276-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="b9276-671">In diesem Beispiel wird das Ziel des Anruf Weiterleitungs-/Nein-Anrufs und die Klingelverzögerung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b9276-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="b9276-672">Hier wird der Schalter//////-Schalter nicht bereitgestellt. SEFAUtil versucht, die Skype for Business Server 2015-AutoErmittlung zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b9276-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="b9276-673">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-673">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="b9276-674">Aktivieren der sofortigen Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="b9276-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="b9276-675">Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b9276-675">This example immediately enables call-forwarding to another user.</span></span>

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="b9276-676">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-676">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="b9276-677">Deaktivieren der sofortigen Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="b9276-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="b9276-678">Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="b9276-678">This example immediately disables call forwarding.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="b9276-679">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-679">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="b9276-680">Hinzufügen eines Benutzers als Stellvertretung und Einrichten von gleichzeitigem Klingeln bei Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="b9276-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="b9276-681">Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das gleichzeitige Klingeln bei Stellvertretungen ein.</span><span class="sxs-lookup"><span data-stu-id="b9276-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="b9276-682">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-682">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="b9276-683">Ändern der Regel für gleichzeitiges Klingeln bei Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="b9276-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="b9276-684">Dieses Beispiel ändert die Regel für gleichzeitiges Klingeln bei Stellvertretungen, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.</span><span class="sxs-lookup"><span data-stu-id="b9276-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="b9276-685">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-685">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="b9276-686">Entfernen der Stellvertretung</span><span class="sxs-lookup"><span data-stu-id="b9276-686">Remove the Delegate</span></span>

<span data-ttu-id="b9276-687">Dieses Beispiel entfernt die Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="b9276-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="b9276-688">Wenn die letzte Stellvertretung entfernt wurde, wird das Anrufen von Stellvertretungen automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b9276-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="b9276-689">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-689">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="b9276-690">Hinzufügen einer Stellvertretung und Einrichten der Regel „Anrufweiterleitung an Stellvertretungen“</span><span class="sxs-lookup"><span data-stu-id="b9276-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="b9276-691">Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel „Anrufweiterleitung an Stellvertretungen“ ein.</span><span class="sxs-lookup"><span data-stu-id="b9276-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="b9276-692">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-692">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="b9276-693">Aktivieren von gleichzeitigem Klingeln und Festlegen einer Zielnummer</span><span class="sxs-lookup"><span data-stu-id="b9276-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="b9276-694">Diese Beispiel aktiviert gleichzeitiges Klingeln und legt eine Zielnummer für diese Funktion fest.</span><span class="sxs-lookup"><span data-stu-id="b9276-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="b9276-695">Um die Zielnummer für gleichzeitiges Klingeln eines Benutzers zu ändern, für den gleichzeitiges Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter „/enablesimulring“. Andernfalls wird die Zielnummer nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="b9276-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="b9276-696">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-696">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="b9276-697">Deaktivieren von gleichzeitigem Klingeln</span><span class="sxs-lookup"><span data-stu-id="b9276-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="b9276-698">Dieses Beispiel deaktiviert gleichzeitiges Klingeln.</span><span class="sxs-lookup"><span data-stu-id="b9276-698">This example disables simultaneous ringing.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="b9276-699">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-699">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="b9276-700">Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Teamanrufgruppen-Mitglieder</span><span class="sxs-lookup"><span data-stu-id="b9276-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="b9276-701">Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert gleichzeitiges Klingeln für die Teamanrufgruppe.</span><span class="sxs-lookup"><span data-stu-id="b9276-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="b9276-702">Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für gleichzeitiges Klingeln automatisch auf gleichzeitiges Klingeln für die Teamanrufgruppe umgestellt.</span><span class="sxs-lookup"><span data-stu-id="b9276-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="b9276-703">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-703">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="b9276-704">Entfernen eines Mitglieds aus der Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="b9276-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="b9276-705">Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b9276-705">This example removes a team member of the team-call group of a user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="b9276-706">Wenn das einzige Mitglied der Teamanrufgruppe entfernt wird, wird automatisch das gleichzeitige Klingeln für die Teamanrufgruppe deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b9276-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="b9276-707">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-707">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="b9276-708">Festlegen der Anrufverzögerung für die Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="b9276-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="b9276-709">Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.</span><span class="sxs-lookup"><span data-stu-id="b9276-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="b9276-710">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-710">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="b9276-711">Aktivieren des Teamanrufs</span><span class="sxs-lookup"><span data-stu-id="b9276-711">Enable Team-Call</span></span>

<span data-ttu-id="b9276-712">Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b9276-712">This example enables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="b9276-713">Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, ist die Teamanruffunktion nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b9276-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="b9276-714">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="b9276-715">Deaktivieren des Teamanrufs</span><span class="sxs-lookup"><span data-stu-id="b9276-715">Disable Team-Call</span></span>

<span data-ttu-id="b9276-716">Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b9276-716">This example disables team-call for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="b9276-717">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-717">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="b9276-718">Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="b9276-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="b9276-719">Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="b9276-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="b9276-720">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="b9276-720">**Output**</span></span>

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="b9276-721">Deaktivieren der Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="b9276-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="b9276-722">Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b9276-722">This example disables Group Call Pickup for a given user.</span></span>

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="b9276-p188">Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend wieder aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters „/enablegrouppickup“ zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b9276-p188">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="b9276-725">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="b9276-725">SYSPrep.ps1</span></span>
<span data-ttu-id="b9276-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-726"></span></span>

### <a name="description"></a><span data-ttu-id="b9276-727">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-727">Description</span></span>

<span data-ttu-id="b9276-728">"SYSPrep. ps1" ist ein Windows PowerShell-Skript, mit dem die folgenden Skype for Business Server 2015-Voraussetzungen auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="b9276-729">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b9276-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="b9276-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="b9276-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="b9276-731">Windows PowerShell, Version 3.0</span><span class="sxs-lookup"><span data-stu-id="b9276-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="b9276-732">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="b9276-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="b9276-733">Updates für Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="b9276-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="b9276-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b9276-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="b9276-735">Skype for Business Server 2015-Core-Dateien</span><span class="sxs-lookup"><span data-stu-id="b9276-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="b9276-736">Zwar ähnelt der Skriptname dem des Systemvorbereitungsprogramms für die Microsoft Windows-Betriebssysteme, doch sind beide unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="b9276-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="b9276-737">Mit diesem Skript werden nur die erforderlichen Voraussetzungen für Skype for Business Server 2015 installiert.</span><span class="sxs-lookup"><span data-stu-id="b9276-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="b9276-738">Sobald diese installiert sind, kann mit dem Windows-Tool für die Systemvorbereitung ein Image des Servers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-739">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-739">Requirements</span></span>

<span data-ttu-id="b9276-740">Bevor Sie das SYSPrep. ps1-Skript ausführen, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (beispielsweise **D:\setup)**.</span><span class="sxs-lookup"><span data-stu-id="b9276-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="b9276-741">Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015-Dateien, insbesondere **Setup. exe** , beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b9276-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="b9276-742">Die erforderlichen Dateien können Sie an folgenden Orten herunterladen:</span><span class="sxs-lookup"><span data-stu-id="b9276-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="b9276-743">**Erforderliche Komponente**</span><span class="sxs-lookup"><span data-stu-id="b9276-743">**Prerequisite**</span></span>                                | <span data-ttu-id="b9276-744">**Standort**</span><span class="sxs-lookup"><span data-stu-id="b9276-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="b9276-745">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b9276-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="b9276-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b9276-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="b9276-747">Windows PowerShell, Version 3.0</span><span class="sxs-lookup"><span data-stu-id="b9276-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="b9276-748">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="b9276-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="b9276-749">Updates für Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="b9276-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="b9276-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b9276-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="b9276-751">Skype for Business Server 2015 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="b9276-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="b9276-752">Kopieren von Skype for Business Server 2015-Medien</span><span class="sxs-lookup"><span data-stu-id="b9276-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="b9276-753">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9276-753">Parameter</span></span>

<span data-ttu-id="b9276-754">Der **-SetupFolder-** Parameter verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.</span><span class="sxs-lookup"><span data-stu-id="b9276-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-755">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-755">Examples</span></span>

<span data-ttu-id="b9276-756">Führen Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl aus, um das Skript "SYSPrep. ps1" auszuführen und die Voraussetzungen für Skype for Business Server 2015 zu installieren:</span><span class="sxs-lookup"><span data-stu-id="b9276-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="b9276-757">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="b9276-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="b9276-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-758"></span></span>

<span data-ttu-id="b9276-759">Mit dem Migrationstool "nicht zugewiesene Nummern Ankündigungen" kann ein Skype for Business Server 2015-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von einem Skype for Business-Quellserver oder-Pool zu einem Ziel des Skype for Business-Servers oder-Pools.</span><span class="sxs-lookup"><span data-stu-id="b9276-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-760">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-760">Description</span></span>

<span data-ttu-id="b9276-761">Das Tool Unassigned Number Announcements Migration ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.</span><span class="sxs-lookup"><span data-stu-id="b9276-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="b9276-762">Bei Ausführung des Unassigned Number Announcements Migration-Skripts werden folgende Vorgänge durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="b9276-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="b9276-763">Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Dateispeicher des Zielservers oder -pools</span><span class="sxs-lookup"><span data-stu-id="b9276-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9276-764">Die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9276-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="b9276-765">Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Zielserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="b9276-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="b9276-766">Erneutes Zuweisen aller nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool verwaltet wird, zum Zielserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="b9276-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="b9276-767">Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.</span><span class="sxs-lookup"><span data-stu-id="b9276-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-768">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-768">Output</span></span>

<span data-ttu-id="b9276-769">Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster "Skype for Business Server-Verwaltungsshell" an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="b9276-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="b9276-p191">Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich in das Ziel verschobenen nicht zugewiesenen Nummernbereiche in funktionsfähiger Form am Ziel, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.</span><span class="sxs-lookup"><span data-stu-id="b9276-p191">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="b9276-772">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="b9276-772">Purpose</span></span>

<span data-ttu-id="b9276-773">Das Unassigned Number Announcements Migration-Skript kann in den drei folgenden Szenarien eingesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="b9276-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="b9276-774">**Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso ist dabei, zu Skype for Business Server 2015 zu migrieren, und im Rahmen des Migrationsprozesses möchte der Skype for Business Server-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2013-Bereitstellung auf die neue Bereitstellung von Skype for Business Server 2015 verschieben.</span><span class="sxs-lookup"><span data-stu-id="b9276-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="b9276-775">Um die Konfigurationseinstellungen zu verschieben, verwendet der Skype for Business Server-Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="b9276-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="b9276-776">**Rollback einer Bereitstellung von Skype for Business Server 2015 auf lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration auf die neue Skype for Business Server 2015-Bereitstellung zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="b9276-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="b9276-777">Um die Unterbrechungen des Diensts zu minimieren, verwendet der Skype for Business Server-Administrator das Migrationstool "nicht zugewiesene Nummern Ankündigungen", um die Konfiguration von der Skype for Business Server 2015-Bereitstellung auf die lync Server 2013-Bereitstellung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="b9276-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="b9276-778">**Verschieben von Daten zwischen Bereitstellungen:** Contoso ersetzt alle Server eines Pools durch neuere Server.</span><span class="sxs-lookup"><span data-stu-id="b9276-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="b9276-779">Ihre Strategie ist die Bereitstellungeines neuen Skype for Business Server 2015-Pools, das Verschieben aller Daten aus dem alten in den neuen Pool und das anschließende verwerfen des alten Pools.</span><span class="sxs-lookup"><span data-stu-id="b9276-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="b9276-780">Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mit dem Tool Unassigned Number Announcements Migration aus dem alten Pool in den neuen verschoben.</span><span class="sxs-lookup"><span data-stu-id="b9276-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="b9276-781">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b9276-781">Requirements</span></span>

<span data-ttu-id="b9276-782">Hier sind die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:</span><span class="sxs-lookup"><span data-stu-id="b9276-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="b9276-783">Das Skript muss von einem Computer ausgeführt werden, auf dem die Skype for Business Server-Verwaltungsshell installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="b9276-784">Die Ankündigungs Anwendung muss erfolgreich in den Skype for Business-Servern oder-Pools für Quell-und Zielserver bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="b9276-785">Skript „Move-CsAnnouncementConfiguration“</span><span class="sxs-lookup"><span data-stu-id="b9276-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="b9276-786">Das Skript „Move-CsAnnouncementConfiguration“ erfordert die in der Tabelle unten beschriebenen zwei Parameter. </span><span class="sxs-lookup"><span data-stu-id="b9276-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![Move-CsAnnouncementConfiguration-Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="b9276-788">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="b9276-789">Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem lync Server 2013-Pool zu einem Skype for Business Server 2015-Pool</span><span class="sxs-lookup"><span data-stu-id="b9276-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="b9276-790">In diesem Beispiel werden die nicht zugewiesenen Nummern Ankündigungen aus dem Quell Pool (lync Server 2013) in den Ziel Pool (Skype for Business Server 2015) verschoben.</span><span class="sxs-lookup"><span data-stu-id="b9276-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="b9276-791">Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem Skype for Business Server 2015-Pool in einen lync Server 2013-Pool</span><span class="sxs-lookup"><span data-stu-id="b9276-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="b9276-792">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (Skype for Business Server 2015) in den Ziel Pool (lync Server 2013) verschoben.</span><span class="sxs-lookup"><span data-stu-id="b9276-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="b9276-793">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="b9276-793">Web Conf Data</span></span>
<span data-ttu-id="b9276-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="b9276-794"></span></span>

<span data-ttu-id="b9276-795">Das Tool Web conf Data ermöglicht einem Administrator der Skype for Business Server 2015-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die mit den Webkonferenzen eines Organisators verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b9276-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="b9276-796">Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers auf Grundlage eines Zeitstempel Kriteriums zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b9276-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="b9276-797">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9276-797">Description</span></span>

<span data-ttu-id="b9276-798">Mit diesem Tool können Administratoren die folgenden Vorgänge durchführen:</span><span class="sxs-lookup"><span data-stu-id="b9276-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="b9276-799">Suchen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="b9276-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="b9276-800">Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="b9276-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="b9276-801">Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind und deren Alter einen bestimmten Wert überschreitet</span><span class="sxs-lookup"><span data-stu-id="b9276-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="b9276-802">Verschieben aller Webkonferenzdaten, die einem Benutzern zugeordnet sind, wenn diese Benutzer aus einem Pool in einen anderen verschoben werden</span><span class="sxs-lookup"><span data-stu-id="b9276-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

> [!NOTE]
> <span data-ttu-id="b9276-803">Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool zu einem anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="b9276-804">Diese Funktionalität ist jetzt aus diesem Tool für den **MoveConferenceData** -Parameter veraltet.</span><span class="sxs-lookup"><span data-stu-id="b9276-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="b9276-805">Details zu diesem Parameter finden Sie unter dem Cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b9276-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="b9276-p197">Das Tool löscht Besprechungsdaten nur für inaktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-p197">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="b9276-p198">Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-p198">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="b9276-810">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b9276-810">Output</span></span>

<span data-ttu-id="b9276-811">Dieses Tool gibt die Ergebnisse der folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="b9276-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="b9276-812">Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, deren Organisator dieser Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="b9276-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="b9276-813">Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="b9276-814">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9276-814">Requirements</span></span>

<span data-ttu-id="b9276-815">Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator zurzeit verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="b9276-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="b9276-816">Das Tool muss mit Administratorrechten und mit Zugriff auf den Inhaltsdateispeicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="b9276-817">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b9276-817">Examples</span></span>

<span data-ttu-id="b9276-818">In der folgenden Tabelle werden die Parameter beschrieben, die zum Teil in den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9276-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parameter des Web conf-Datentools.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="b9276-p199">Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="b9276-p199">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="b9276-p200">Oben sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b9276-p200">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="b9276-824">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b9276-824">Summary</span></span>

<span data-ttu-id="b9276-825">Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="b9276-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>



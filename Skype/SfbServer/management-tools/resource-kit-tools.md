---
title: Dokumentation zu Skype for Business Server 2015 Resource Kit-Tools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Das Skype for Business Server 2015 Resource Kit unterstützt IT-Administratoren bei der Bereitstellung und Verwaltung von Skype for Business Server 2015 bei der Vereinfachung von Routineaufgaben. Beispielsweise kann das Tool webconf-Daten verwendet werden, um Daten, die von Benutzern während einer Onlinebesprechung hochgeladen werden, ganz einfach zu steuern. Das SEFAUtil-Tool kann zum Einrichten von Delegate-Anrufweiterleitung und-Beantwortung für Benutzer verwendet werden. Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.
ms.openlocfilehash: ab43d8e951308fab5a4aefc25d9dad2804ea5d0e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005990"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a><span data-ttu-id="539e3-107">Dokumentation zu Skype for Business Server 2015 Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="539e3-107">Skype for Business Server 2015 Resource Kit Tools Documentation</span></span>

<span data-ttu-id="539e3-108">In diesem Thema werden die Tools im Skype for Business Server 2015 Resource Kit beschrieben, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="539e3-108">This topic describes the tools in the Skype for Business Server 2015 Resource Kit, including the purpose of each tool, and examples of its use.</span></span> <span data-ttu-id="539e3-109">Das Skype for Business Server 2015 Resource Kit unterstützt IT-Administratoren bei der Bereitstellung und Verwaltung von Skype for Business Server 2015 bei der Vereinfachung von Routineaufgaben.</span><span class="sxs-lookup"><span data-stu-id="539e3-109">The Skype for Business Server 2015 Resource Kit helps to make routine tasks easier for IT administrators who deploy and manage Skype for Business Server 2015.</span></span> <span data-ttu-id="539e3-110">Beispielsweise kann das Tool **webconf-Daten** verwendet werden, um Daten, die von Benutzern während einer Onlinebesprechung hochgeladen werden, ganz einfach zu steuern.</span><span class="sxs-lookup"><span data-stu-id="539e3-110">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="539e3-111">Das **SEFAUtil** -Tool kann zum Einrichten von Delegate-Anrufweiterleitung und-Beantwortung für Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-111">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="539e3-112">Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um Skype for Business Server 2015 effektiver zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="539e3-112">We encourage IT administrators to use these tools to more effectively manage Skype for Business Server 2015.</span></span>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="539e3-113">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="539e3-113">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="539e3-114">Um das Skype for Business Server 2015 Resource Kit zu installieren, laden Sie [OCSReskit. msi](https://www.microsoft.com/download/details.aspx?id=52631) aus dem Download Center herunter.</span><span class="sxs-lookup"><span data-stu-id="539e3-114">To install the Skype for Business Server 2015 Resource Kit, download [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) from the Download Center.</span></span>

<span data-ttu-id="539e3-115">Führen Sie **OCSResKit. msi** aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="539e3-115">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="539e3-116">Die MSI-Installation aller Tools im folgenden Pfad: **% Program Files%\Skype for Business Server 2015 \ reskit**.</span><span class="sxs-lookup"><span data-stu-id="539e3-116">The .msi installs all the tools in the following path: **%Program Files%\Skype for Business Server 2015\ResKit**.</span></span> <span data-ttu-id="539e3-117">Tools mit eigenständigen ausführbaren Dateien befinden sich in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="539e3-117">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="539e3-118">Tools, die auch unterstützende Dateien haben, befinden sich in ihren eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="539e3-118">Tools that also have supporting files are in their own subfolders.</span></span>

## <a name="supported-environments"></a><span data-ttu-id="539e3-119">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="539e3-119">Supported Environments</span></span>

<span data-ttu-id="539e3-120">Das Skype for Business Server 2015 Resource Kit sollte auf einem Server installiert sein, der die für Skype for Business Server 2015 erforderlichen Spezifikationen erfüllt, in der Regel wird Skype for Business Server 2015 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="539e3-120">The Skype for Business Server 2015 Resource Kit should be installed on a server that meets the specifications required for Skype for Business Server 2015, usually one being used to run Skype for Business Server 2015.</span></span>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="539e3-121">Resource Kit-Tools (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="539e3-121">Resource Kit Tools Overview</span></span>

<span data-ttu-id="539e3-122">Im folgenden finden Sie eine Liste der im Skype for Business Server 2015 Resource Kit bereitgestellten Tools.</span><span class="sxs-lookup"><span data-stu-id="539e3-122">The following is a list of the tools that are provided in the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="539e3-123">Die folgenden Abschnitte enthalten eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung.</span><span class="sxs-lookup"><span data-stu-id="539e3-123">A description of each tool, including the requirements and example usage is covered in the following sections.</span></span>

- [<span data-ttu-id="539e3-124">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="539e3-124">ABSConfig</span></span>](resource-kit-tools.md#ABSConfig)

- [<span data-ttu-id="539e3-125">Bandbreitenrichtlinie-Dienst Monitor</span><span class="sxs-lookup"><span data-stu-id="539e3-125">Bandwidth Policy Service Monitor</span></span>](resource-kit-tools.md#bpsm)

- [<span data-ttu-id="539e3-126">Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="539e3-126">Bandwidth Utilization Analyzer</span></span>](resource-kit-tools.md#bua)

- [<span data-ttu-id="539e3-127">Parkometer aufrufen</span><span class="sxs-lookup"><span data-stu-id="539e3-127">Call Parkometer</span></span>](resource-kit-tools.md#callpark)

- [<span data-ttu-id="539e3-128">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="539e3-128">DBAnalyze</span></span>](resource-kit-tools.md#dba)

- [<span data-ttu-id="539e3-129">Importieren von Speicherdienst Daten</span><span class="sxs-lookup"><span data-stu-id="539e3-129">Import Storage Service Data</span></span>](resource-kit-tools.md#Issd)

- [<span data-ttu-id="539e3-130">LCSSync</span><span class="sxs-lookup"><span data-stu-id="539e3-130">LCSSync</span></span>](resource-kit-tools.md#LCSSync)

- [<span data-ttu-id="539e3-131">Lookup-Benutzerkonsole</span><span class="sxs-lookup"><span data-stu-id="539e3-131">Lookup User Console</span></span>](resource-kit-tools.md#LUC)

- [<span data-ttu-id="539e3-132">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="539e3-132">MsTurnPing</span></span>](resource-kit-tools.md#MsTurnPing)

- [<span data-ttu-id="539e3-133">Netzwerk Konfigurationsanzeige</span><span class="sxs-lookup"><span data-stu-id="539e3-133">Network Configuration Viewer</span></span>](resource-kit-tools.md#NCV)

- [<span data-ttu-id="539e3-134">Reaktionsgruppen-Agent Live</span><span class="sxs-lookup"><span data-stu-id="539e3-134">Response Group Agent Live</span></span>](resource-kit-tools.md#RGAL)

- [<span data-ttu-id="539e3-135">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="539e3-135">SEFAUtil</span></span>](resource-kit-tools.md#SEFAUtil)

- [<span data-ttu-id="539e3-136">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="539e3-136">SYSPrep.ps1</span></span>](resource-kit-tools.md#SYSPrep)

- [<span data-ttu-id="539e3-137">Migration nicht zugewiesener Nummern Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="539e3-137">Unassigned Number Announcements Migration</span></span>](resource-kit-tools.md#UNAM)

- [<span data-ttu-id="539e3-138">Webconf-Daten</span><span class="sxs-lookup"><span data-stu-id="539e3-138">Web Conf Data</span></span>](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a><span data-ttu-id="539e3-139">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="539e3-139">ABSConfig</span></span>
<span data-ttu-id="539e3-140"><a name="ABSConfig"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-140"><a name="ABSConfig"> </a></span></span>

<span data-ttu-id="539e3-141">Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in Skype for Business Server 2015 anpassen können.</span><span class="sxs-lookup"><span data-stu-id="539e3-141">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Skype for Business Server 2015.</span></span> <span data-ttu-id="539e3-142">Mit diesem Tool können Skype for Business Server 2015 Administratoren auch die Standardeinstellungen für den Adressbuchdienst wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-142">This tool also enables Skype for Business Server 2015 administrators to restore the default Address Book Service settings.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-143">Description</span></span>

<span data-ttu-id="539e3-144">ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienste Attribute konfigurieren können, die sich auf den Adressbuchdienst beziehen.</span><span class="sxs-lookup"><span data-stu-id="539e3-144">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="539e3-145">Die primären Szenarien für das Tool lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="539e3-145">The primary scenarios for the tool are the following:</span></span>

- <span data-ttu-id="539e3-146">Damit Administratoren den Attributen für Skype for Business Server 2015 Attribute in Active Directory-Domänendienste zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="539e3-146">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Skype for Business Server 2015.</span></span>

- <span data-ttu-id="539e3-147">Damit Administratoren das Active Directory-Domänendienste Attribut angeben können, das in die Adressbuchdienst Dateien eingeschlossen oder ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="539e3-147">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

- <span data-ttu-id="539e3-148">Damit Administratoren Standardeinstellungen für den Adressbuchdienst wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="539e3-148">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="539e3-149">Das ABSConfig-Tool kann mithilfe der Datei ABSConfig. exe gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-149">The ABSConfig tool can be started by using the ABSConfig.exe file.</span></span> <span data-ttu-id="539e3-150">Das Tool wird auf der Registerkarte **Configure Attributes** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen Active Directory-Domänendienste Attribute zu den Attributfeldern für Skype for Business Server 2015 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern eingeschlossen oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="539e3-150">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Skype for Business Server 2015 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="539e3-151">Außerdem gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="539e3-151">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="539e3-152">Die Option **Standardeinstellungen wiederherstellen** ermöglicht Administratoren das Wiederherstellen von Einstellungen für den Adressbuchdienst auf Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="539e3-152">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

> [!NOTE]
> <span data-ttu-id="539e3-153">Das erneute Zuordnen von AD-Attributen zu unterschiedlichen OC-Feldnamen funktioniert nur beim Herunterladen von Adressbuchdateien und wird von der Adressbuch-Webabfrage nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="539e3-153">Re-mapping of AD attributes to different OC Field Names will only work for Address Book File Download, and is not supported by Address Book Web Query.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-154">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-154">Output</span></span>

<span data-ttu-id="539e3-155">In ABSConfig wird die Konfiguration des Adressbuchdiensts in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="539e3-155">ABSConfig stores the Address Book Service configuration in the database.</span></span>

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a><span data-ttu-id="539e3-156">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-156">Purpose</span></span>

<span data-ttu-id="539e3-157">ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen Skype for Business Server 2015 Adressbuchdiensts.</span><span class="sxs-lookup"><span data-stu-id="539e3-157">ABSConfig provides a quick and easy way to customize Skype for Business Server 2015 Address Book Service.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-158">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-158">Requirements</span></span>

#### <a name="computer"></a><span data-ttu-id="539e3-159">Computer</span><span class="sxs-lookup"><span data-stu-id="539e3-159">Computer</span></span>

<span data-ttu-id="539e3-160">ABSConfig kann nur von einem Computer ausgeführt werden, der der Domäne angehört und auf dem Skype for Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-160">ABSConfig can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span> <span data-ttu-id="539e3-161">Im Fall von Skype for Business Server 2015 Enterprise Edition kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-161">In the case of Skype for Business Server 2015, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

#### <a name="network"></a><span data-ttu-id="539e3-162">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="539e3-162">Network</span></span>

<span data-ttu-id="539e3-163">Der Computer sollte in der Lage sein, eine Verbindung mit der Front-End-Pool-und Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-163">The computer should be able to connect to the Front End pool and back-end database.</span></span>

#### <a name="software"></a><span data-ttu-id="539e3-164">Software</span><span class="sxs-lookup"><span data-stu-id="539e3-164">Software</span></span>

<span data-ttu-id="539e3-165">Die folgenden Softwarekomponenten müssen installiert sein, bevor Sie das ABSConfig-Tool ausführen:</span><span class="sxs-lookup"><span data-stu-id="539e3-165">The following software components must be installed before running the ABSConfig tool:</span></span>

- <span data-ttu-id="539e3-166">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="539e3-166">Skype for Business Server 2015</span></span>

#### <a name="users"></a><span data-ttu-id="539e3-167">Benutzer</span><span class="sxs-lookup"><span data-stu-id="539e3-167">Users</span></span>

<span data-ttu-id="539e3-168">Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der Skype for Business Server 2015-Bereitstellung verfügen.</span><span class="sxs-lookup"><span data-stu-id="539e3-168">Administrators who have the permissions required to update the Skype for Business Server 2015 deployment.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-169">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-169">Examples</span></span>

<span data-ttu-id="539e3-170">ABSConfig kann gestartet werden, indem Sie **ABSConfig. exe** an einer Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="539e3-170">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="539e3-171">Unten sehen Sie die Benutzeroberfläche des ABSConfig-Tools.</span><span class="sxs-lookup"><span data-stu-id="539e3-171">Shown below is the ABSConfig tool user interface.</span></span>

![Das Tool ABSConfig. exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a><span data-ttu-id="539e3-173">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-173">Summary</span></span>

<span data-ttu-id="539e3-174">Mit dem ABSConfig-Tool können Administratoren schnell und einfach Tools verwenden, um Skype for Business Server 2015 Adressbuchdienst anzupassen.</span><span class="sxs-lookup"><span data-stu-id="539e3-174">The ABSConfig tool provides administrators a quick and easy to use tool to customize Skype for Business Server 2015 Address Book Service.</span></span>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="539e3-175">Bandbreitenrichtlinie-Dienst Monitor</span><span class="sxs-lookup"><span data-stu-id="539e3-175">Bandwidth Policy Service Monitor</span></span>
<span data-ttu-id="539e3-176"><a name="bpsm"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-176"><a name="bpsm"> </a></span></span>

<span data-ttu-id="539e3-177">Das Tool Bandbreitenrichtlinien-Dienstüberwachung soll Administratoren die Möglichkeit geben, eine Liste der folgenden anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="539e3-177">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1. <span data-ttu-id="539e3-178">Alle konfigurierten Skype for Business Server 2015 Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie</span><span class="sxs-lookup"><span data-stu-id="539e3-178">All the configured Skype for Business Server 2015 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2. <span data-ttu-id="539e3-179">Die Verbindungen, die von jedem Dienst für andere Bandbreitenrichtlinien Dienste und für die Edgeserver erstellt werden</span><span class="sxs-lookup"><span data-stu-id="539e3-179">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3. <span data-ttu-id="539e3-180">Alle Links, die im Netzwerk Konfigurationsdokument konfiguriert sind, sowie die Echtzeitbandbreite, die von den einzelnen Bandbreitenrichtlinien Diensten gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="539e3-180">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

### <a name="description"></a><span data-ttu-id="539e3-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-181">Description</span></span>

<span data-ttu-id="539e3-182">Das Tool Bandwidth Policy Service Monitor wird als GUI-basierte Anwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="539e3-182">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="539e3-183">Administratoren starten das Tool durch Ausführung von PDPMonUI. exe.</span><span class="sxs-lookup"><span data-stu-id="539e3-183">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="539e3-184">Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreitenrichtlinien Dienste in der Topologie zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="539e3-184">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="539e3-185">Nachdem die anfängliche Aktualisierung abgeschlossen ist, wird der Bereich links neben dem Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="539e3-185">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="539e3-186">Wenn Administratoren einen bestimmten bandbreitenrichtliniendienst auswählen, zeigt der Bereich auf der rechten Seite die Informationen zu diesem bestimmten Dienst an.</span><span class="sxs-lookup"><span data-stu-id="539e3-186">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="539e3-187">Dieser Bereich verfügt auch über zwei Hauptregisterkarten, in denen Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-187">That pane also has two main tabs that display information.</span></span>

#### <a name="machine-info-tab"></a><span data-ttu-id="539e3-188">Registerkarte "Machine Info"</span><span class="sxs-lookup"><span data-stu-id="539e3-188">Machine Info Tab</span></span>

<span data-ttu-id="539e3-189">Auf der Registerkarte **Computer Informationen** werden die Details des ausgewählten Bandbreitenrichtlinien Diensts sowie die Liste und der Status aller Verbindungen angezeigt, die vom ausgewählten bandbreitenrichtliniendienst für andere Dienste vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="539e3-189">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

#### <a name="topology-info-tab"></a><span data-ttu-id="539e3-190">Registerkarte "Topologieinformationen"</span><span class="sxs-lookup"><span data-stu-id="539e3-190">Topology Info Tab</span></span>

<span data-ttu-id="539e3-191">Auf der Registerkarte **Topologieinformationen** wird eine Liste aller Links angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-191">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="539e3-192">Für jeden Link wird die Kapazität der Audio-und Videobandbreite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-192">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="539e3-193">Darüber hinaus wird die derzeit verwendete Bandbreite sowohl in Kbit/s als auch als Prozentsatz der Kapazität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-193">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="539e3-194">Das Tool verwendet Farbcodierung, um Links hervorzuheben, deren Auslastung der Kapazität nahe liegt, sodass Administratoren solche Links schnell isolieren können.</span><span class="sxs-lookup"><span data-stu-id="539e3-194">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

> [!NOTE]
>  <span data-ttu-id="539e3-195">Wenn beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreitenrichtlinien Dienste beim bandbreitenrichtliniendienst Monitor ein Fehler auftritt, werden die Informationen in den Registerkarten **Computer Info** und **Topologieinformationen** nicht aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="539e3-195">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the **Machine Info** and the **Topology Info** tabs won't be populated.</span></span> <span data-ttu-id="539e3-196">Es kann jedoch sein, dass das Tool anfänglich eine Verbindung herstellen kann, aber die Verbindung mit dem Dienst anschließend verloren geht.</span><span class="sxs-lookup"><span data-stu-id="539e3-196">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="539e3-197">In diesen Fällen werden Administratoren möglicherweise veraltete Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-197">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="539e3-198">Auf jeder Registerkarte gibt es einen **letzten aktualisierten** Zeitstempel, mit dem Administratoren sehen können, wann die Daten zuletzt für einen bestimmten bandbreitenrichtliniendienst aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="539e3-198">There is a **Last Updated** time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-199">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-199">Output</span></span>

<span data-ttu-id="539e3-200">Es gibt keine Befehlszeilenausgabe; die Programmausgabe ist in der Haupt grafischen Benutzeroberfläche (Graphical User Interface, GUI) enthalten.</span><span class="sxs-lookup"><span data-stu-id="539e3-200">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-201">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-201">Purpose</span></span>

<span data-ttu-id="539e3-202">Der Zweck des Bandwidth Policy Service Monitor-Tools besteht darin, Administratoren Einblick in den Status der einzelnen Bandbreitenrichtlinien Dienste zu gewähren, die in der Topologie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-202">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="539e3-203">Darüber hinaus können Administratoren die Echtzeitbandbreite für alle im Netzwerk Konfigurationsdokument definierten Links sehen.</span><span class="sxs-lookup"><span data-stu-id="539e3-203">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-204">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-204">Requirements</span></span>

<span data-ttu-id="539e3-205">Das Tool für Bandbreitenrichtlinien-Dienstüberwachung muss auf einem Computer ausgeführt werden, der Teil der Skype for Business Server Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-205">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Skype for Business Server topology.</span></span>

### <a name="summary"></a><span data-ttu-id="539e3-206">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-206">Summary</span></span>

<span data-ttu-id="539e3-207">Das Tool Bandbreitenrichtlinien-Dienstüberwachung kann eine wertvolle Ressource für Administratoren sein, damit Sie den Status aller Bandbreitenrichtlinien Dienste in der Topologie überprüfen können-und was noch wichtiger ist-Sie können eine Echtzeitbandbreite für die Links erhalten, die in den Netzwerkkonfigurationseinstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="539e3-207">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="539e3-208">Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="539e3-208">Bandwidth Utilization Analyzer</span></span>
<span data-ttu-id="539e3-209"><a name="bua"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-209"><a name="bua"> </a></span></span>

<span data-ttu-id="539e3-210">Bandwidth Auslastung Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-210">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="539e3-211">Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und die Planung von Bandbreitenkapazitäten zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="539e3-211">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-212">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-212">Description</span></span>

<span data-ttu-id="539e3-213">Bandbreiten Auslastungsanalyse wird als GUI-basierte Anwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="539e3-213">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="539e3-214">Dieses Tool generiert Berichte speziell für die audionutzung im gesamten Netzwerk und hilft bei der Kapazitätsplanung.</span><span class="sxs-lookup"><span data-stu-id="539e3-214">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="539e3-215">Außerdem wird die Bandbreitenkapazität durchlaufen, die verschiedenen Links zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-215">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-216">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-216">Output</span></span>

<span data-ttu-id="539e3-217">Bandbreiten Auslastungsanalyse bietet Grafik Al-Plots mit Bandbreitenkapazität und-Nutzung für alle im System konfigurierten WAN-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="539e3-217">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-218">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-218">Purpose</span></span>

<span data-ttu-id="539e3-219">In jeder sprach-und Videobereitstellung ist es wichtig, den Trend der Bandbreitenauslastung des Mediendaten Verkehrs im gesamten Unternehmensnetzwerk zu überwachen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="539e3-219">In any voice and video deployment, it's critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="539e3-220">Das Tool Bandbreiten Auslastungsanalyse ermöglicht es einem Administrator, genau dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="539e3-220">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="539e3-221">Dieses Tool führt folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="539e3-221">This tool does the following:</span></span>

- <span data-ttu-id="539e3-222">Generiert spezifische Berichte für die audionutzung im gesamten Netzwerk</span><span class="sxs-lookup"><span data-stu-id="539e3-222">Generates specific reports for audio utilization across the network</span></span>

- <span data-ttu-id="539e3-223">Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Links zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-223">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="539e3-224">Bandbreiten Auslastungsanalyse kann grafische Plots von Bandbreitenkapazität und Auslastungsberichten generieren. Dabei handelt es sich um folgende:</span><span class="sxs-lookup"><span data-stu-id="539e3-224">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

- <span data-ttu-id="539e3-225">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="539e3-225">All the WAN links in the enterprise network</span></span>

- <span data-ttu-id="539e3-226">Gefiltert nach ausgewählten WAN-Verbindungen, die ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="539e3-226">Filtered by selected WAN links that have been chosen</span></span>

- <span data-ttu-id="539e3-227">Gefiltert nach WAN-Verbindungen, die die Link Kapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="539e3-227">Filtered by WAN links that have exceeded link capacity</span></span>

- <span data-ttu-id="539e3-228">Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite unter Verwenden</span><span class="sxs-lookup"><span data-stu-id="539e3-228">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

- <span data-ttu-id="539e3-229">Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (Bandbreitenauslastung, die größer ist als 90% der Bandbreitenkapazität der WAN-Verbindung)</span><span class="sxs-lookup"><span data-stu-id="539e3-229">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

- <span data-ttu-id="539e3-230">Gefiltert nach WAN-Linktyp – Netzwerkstandort Verknüpfungen, interregionale Links und Links innerhalb eines Standorts</span><span class="sxs-lookup"><span data-stu-id="539e3-230">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

- <span data-ttu-id="539e3-231">Gefiltert nach netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="539e3-231">Filtered by network region</span></span>

#### <a name="applications"></a><span data-ttu-id="539e3-232">Applications</span><span class="sxs-lookup"><span data-stu-id="539e3-232">Applications</span></span>

<span data-ttu-id="539e3-233">Bandbreiten Auslastungsanalyse verfügt über die beiden folgenden Anwendungen (Tools):</span><span class="sxs-lookup"><span data-stu-id="539e3-233">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

- <span data-ttu-id="539e3-234">**"Wanlinklogcollector. exe** mit diesem Tool können die Benutzer die erforderlichen Informationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="539e3-234">**WanLinkLogCollector.exe** This tool enables its user to input the required information.</span></span>

- <span data-ttu-id="539e3-235">**"Bandwidthutilizationanalyzer. xlsm** ein Microsoft Excel-Tabellenkalkulationssoftware Bericht wird automatisch von" wanlinklogcollector. exe gestartet.</span><span class="sxs-lookup"><span data-stu-id="539e3-235">**BandwidthUtilizationAnalyzer.xlsm** A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="539e3-236">Diese Anwendung ermöglicht dem Benutzer das Anwenden von Filtern auf den Bericht, wie weiter unten in diesem Artikel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-236">This application allows the user to apply filters to the report as shown later in this article.</span></span>

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="539e3-237">Phasen der Verwendung des Analyseprogramms für Bandbreitenauslastung</span><span class="sxs-lookup"><span data-stu-id="539e3-237">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="539e3-238">Es gibt zwei Phasen bei der Verwendung des Bandbreiten Auslastungsanalyse Programms:</span><span class="sxs-lookup"><span data-stu-id="539e3-238">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

- <span data-ttu-id="539e3-239">Sammeln von Protokollen, die mithilfe von "wanlinklogcollector. exe ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="539e3-239">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

- <span data-ttu-id="539e3-240">Anpassen von Berichten, die mithilfe von "bandwidthutilizationanalyzer. xlsm ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="539e3-240">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="539e3-241">Es wird dringend empfohlen, dass "bandwidthutilizationanalyzer. xlsm nicht von Endbenutzern manuell gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-241">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>

#### <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="539e3-242">Starten der Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="539e3-242">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="539e3-243">Starten Sie "wanlinklogcollector. exe an der Eingabeaufforderung oder mithilfe von Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="539e3-243">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

 <span data-ttu-id="539e3-244">**Verwenden von "wanlinklogcollector. exe**</span><span class="sxs-lookup"><span data-stu-id="539e3-244">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="539e3-245">Es gibt drei Schritte zur Verwendung von "wanlinklogcollector. exe:</span><span class="sxs-lookup"><span data-stu-id="539e3-245">There are three steps to using WanLinkLogCollector.exe:</span></span>

1. <span data-ttu-id="539e3-246">**Protokollieren des Zeitplans** Geben Sie die Zeitachse an, für die der Bericht generiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="539e3-246">**Log the timeline** Provide the timeline that the report needs to be generated for</span></span>

2. <span data-ttu-id="539e3-247">**Angeben der Dateiverzeichnisse** Angeben von Dateispeicherort Informationen</span><span class="sxs-lookup"><span data-stu-id="539e3-247">**Specify the file directories** Provide file location information</span></span>

3. <span data-ttu-id="539e3-248">**Erfassen der Protokolle und Starten der Berichtsanzeige** Ausführen des Befehls zum Generieren des Berichts</span><span class="sxs-lookup"><span data-stu-id="539e3-248">**Collect the logs and launch the report viewer** Execute the command to generate the report</span></span>

#### <a name="step-1---log-the-timeline"></a><span data-ttu-id="539e3-249">Schritt 1 – Protokollieren der Zeitachse</span><span class="sxs-lookup"><span data-stu-id="539e3-249">Step 1 - Log the timeline</span></span>

<span data-ttu-id="539e3-250">Durch die Protokollierung der Zeitachse kann der Benutzer des Tools Folgendes angeben: wie in der Abbildung unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-250">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1. <span data-ttu-id="539e3-251">**Start Datum** Dies ist der Anfangstermin des Zeitplans, für den der Bericht generiert werden soll. Beispiel: August 1, 2010.</span><span class="sxs-lookup"><span data-stu-id="539e3-251">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2. <span data-ttu-id="539e3-252">**Enddatum** Dies ist das Enddatum des Zeitplans, für den der Bericht generiert werden soll. Beispiel: 30. September 2010.</span><span class="sxs-lookup"><span data-stu-id="539e3-252">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>

     ![Start-und Enddatum in der Bandbreitenauslastung A](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="539e3-254">Schritt 2 – angeben der Dateiverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="539e3-254">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="539e3-255">Die folgenden Dateiverzeichnisse können vom Benutzer wie dargestellt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-255">The following file directories can be specified by the user as shown.</span></span>

- <span data-ttu-id="539e3-256">**Speicherort der Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-256">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="539e3-257">Dies ist in der \<Regel in\> \\ Fileserver<Auswahl\>von FE \AppServerFiles\PDP.</span><span class="sxs-lookup"><span data-stu-id="539e3-257">This is typically in \<fileserver\>\\<choice of FE\>\AppServerFiles\PDP.</span></span>

- <span data-ttu-id="539e3-258">**Speicherplatz für temporäre Dateien** Der temporäre Dateispeicherort, an dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-258">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

    ![Dateiverzeichnisse in der Bandbreitenauslastung Anal](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

    > [!NOTE]
    > <span data-ttu-id="539e3-260">Stellen Sie sicher, dass der Benutzer des Tools über einen ausreichenden Dateizugriff auf die Serverprotokolle und den temporären Dateispeicherordner verfügt.</span><span class="sxs-lookup"><span data-stu-id="539e3-260">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="539e3-261">Schritt 3: Erfassen der Protokolle und Starten der Berichtanzeige</span><span class="sxs-lookup"><span data-stu-id="539e3-261">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="539e3-262">Um die Protokolle zu sammeln und die Berichtsanzeige zu starten, klicken Sie wie unten gezeigt auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="539e3-262">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="539e3-263">In diesem Schritt werden die erforderlichen Daten erfasst.</span><span class="sxs-lookup"><span data-stu-id="539e3-263">This step collects the required data.</span></span>

![Sammeln von Daten in der Bandbreitenauslastung Anal](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

<span data-ttu-id="539e3-265">Wenn die Eingabeüberprüfung erfolgreich ist, wird die unten gezeigte Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-265">When the input validation is successful, the message shown below is displayed.</span></span>

![Protokolliert erfasste Benachrichtigung in der Bandbreite utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

<span data-ttu-id="539e3-267">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="539e3-267">Click **OK**.</span></span> <span data-ttu-id="539e3-268">"Bandwidthutilizationanalyzer. xlsm wird automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="539e3-268">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="539e3-269">Befolgen Sie die Anweisungen im Meldungsfeld.</span><span class="sxs-lookup"><span data-stu-id="539e3-269">Follow the instructions in the message box.</span></span> <span data-ttu-id="539e3-270">Ausführliche Informationen finden Sie unter **using "bandwidthutilizationanalyzer. xlsm** im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="539e3-270">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>


### <a name="using-bandwidthutilizationanalyzerxlsm"></a><span data-ttu-id="539e3-271">Verwenden von "bandwidthutilizationanalyzer. xlsm</span><span class="sxs-lookup"><span data-stu-id="539e3-271">Using BandwidthUtilizationAnalyzer.xlsm</span></span>

1. <span data-ttu-id="539e3-272">Wenn "bandwidthutilizationanalyzer. xlsm automatisch gestartet wird, klicken Sie wie unten gezeigt auf **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="539e3-272">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>

     !["Bandwidthutilizationanalyzer. xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. <span data-ttu-id="539e3-274">Wenn ein Datei Ordner geöffnet wird, wählen Sie konsolidiert. CSV aus dem Speicherort aus, der im Meldungsfeld angegeben ist, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-274">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="539e3-275">Außerdem wird der Speicherort als **C:\temp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-275">It also shows the location as **C:\Temp**.</span></span>

     ![Öffnen eines Ordners in "bandwidthutilizationanalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. <span data-ttu-id="539e3-277">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="539e3-277">Click **Import**.</span></span>

4. <span data-ttu-id="539e3-278">Die grafische Darstellung wird automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="539e3-278">The graphical plot is automatically generated.</span></span> <span data-ttu-id="539e3-279">Sie ist verfügbar, wenn der Zeiger für die Hintergrundarbeit ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-279">It is available when the working-in-the-background pointer disappears.</span></span>

     ![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="539e3-281">Anwenden von Filtern auf die Berichtsansicht</span><span class="sxs-lookup"><span data-stu-id="539e3-281">Applying Filters to the Report View</span></span>

<span data-ttu-id="539e3-282">Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden wie folgt beschrieben:</span><span class="sxs-lookup"><span data-stu-id="539e3-282">The filters that can be applied to the report view as shown below are described as follows:</span></span>

![Anwenden von Filtern in der Berichtsansicht.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. <span data-ttu-id="539e3-284">**Name** Nach WAN-Links Filtern (der Filter befindet sich auf der rechten Seite des Diagramms). Das Präfix kennzeichnet die folgenden Verknüpfungstypen; Siehe vertikales Feld (blau):</span><span class="sxs-lookup"><span data-stu-id="539e3-284">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>

   - <span data-ttu-id="539e3-285">**S-Website** Die WAN-Verbindung von einem Netzwerkstandort zu einer netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="539e3-285">**S Site** The WAN link from a network site to a network region</span></span>

   - <span data-ttu-id="539e3-286">**Ist Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="539e3-286">**IS Inter-Site** The WAN link between two network sites</span></span>

   - <span data-ttu-id="539e3-287">**R Inter-Region** Die WAN-Verbindung zwischen zwei netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="539e3-287">**R Inter-Region** The WAN link between two network region</span></span>

2. <span data-ttu-id="539e3-288">**Überschreitungs Grenzwert** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mehr als die Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="539e3-288">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3. <span data-ttu-id="539e3-289">**Kritische Ebenen** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung 90% oder mehr als die Bandbreitenkapazität erreicht hat</span><span class="sxs-lookup"><span data-stu-id="539e3-289">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4. <span data-ttu-id="539e3-290">Nicht **ausgelastet** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25% der Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="539e3-290">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5. <span data-ttu-id="539e3-291">**Verknüpfungstyp** Filtern Sie nach den folgenden WAN-Verbindungstypen:</span><span class="sxs-lookup"><span data-stu-id="539e3-291">**Link type** Filter by the following WAN links types:</span></span>

   - <span data-ttu-id="539e3-292">Typ des **Netzwerkstandorts**</span><span class="sxs-lookup"><span data-stu-id="539e3-292">**Network site** type</span></span>

   - <span data-ttu-id="539e3-293">**Standortübergreifender** Typ</span><span class="sxs-lookup"><span data-stu-id="539e3-293">**Inter-site** type</span></span>

   - <span data-ttu-id="539e3-294">**Zwischen Regionen-Linktyp**</span><span class="sxs-lookup"><span data-stu-id="539e3-294">**Inter-Region link** type</span></span>

6. <span data-ttu-id="539e3-295">**Region** Nach netzwerkregion Filtern</span><span class="sxs-lookup"><span data-stu-id="539e3-295">**Region** Filter by network region</span></span>

<span data-ttu-id="539e3-296">Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.</span><span class="sxs-lookup"><span data-stu-id="539e3-296">The following figures show the previously described filters.</span></span>

<span data-ttu-id="539e3-297">Nach **Name**filtern.</span><span class="sxs-lookup"><span data-stu-id="539e3-297">Filter by **Name**.</span></span> <span data-ttu-id="539e3-298">Wählen Sie die Liste der Links aus, die im Diagramm angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="539e3-298">Select the list of links that need to be displayed in the graph.</span></span>

![Filtern nach Namen in "bandwidthutilizationanalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

<span data-ttu-id="539e3-300">Filtern nach **überschreitungs Grenzwert**.</span><span class="sxs-lookup"><span data-stu-id="539e3-300">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="539e3-301">Wählen Sie **true** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="539e3-301">Select **True** to enforce the filter.</span></span>

![Filterung nach Überschreitung des Grenzwerts.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

<span data-ttu-id="539e3-303">Nach **kritischen Ebenen**filtern.</span><span class="sxs-lookup"><span data-stu-id="539e3-303">Filter by **Critical levels**.</span></span> <span data-ttu-id="539e3-304">Wählen Sie **true** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="539e3-304">Select **True** to enforce the filter.</span></span>

![Filtern nach kritischen Ebenen.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

<span data-ttu-id="539e3-306">Filtern nach **unter verwendet**.</span><span class="sxs-lookup"><span data-stu-id="539e3-306">Filter by **Under utilized**.</span></span> <span data-ttu-id="539e3-307">Wählen Sie **true** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="539e3-307">Select **True** to enforce the filter.</span></span>

![Filterung nach unter verwendet.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

<span data-ttu-id="539e3-309">Nach **Linktyp**filtern.</span><span class="sxs-lookup"><span data-stu-id="539e3-309">Filter by **Link Type**.</span></span> <span data-ttu-id="539e3-310">Wählen Sie die Typen aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="539e3-310">Select the type or types that need to be displayed.</span></span>

![Filterung nach Linktyp.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

<span data-ttu-id="539e3-312">Filtern nach **Region**.</span><span class="sxs-lookup"><span data-stu-id="539e3-312">Filter by **Region**.</span></span> <span data-ttu-id="539e3-313">Wählen Sie eine Liste der Regionen aus, deren Verknüpfungen angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="539e3-313">Select a list of regions whose links need to be displayed.</span></span>

![Filtern nach Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a><span data-ttu-id="539e3-315">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-315">Requirements</span></span>

- <span data-ttu-id="539e3-316">Die Microsoft .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="539e3-316">The .NET Framework 3.5</span></span>

- <span data-ttu-id="539e3-317">Microsoft Excel 2010 oder Excel 2007</span><span class="sxs-lookup"><span data-stu-id="539e3-317">Microsoft Excel 2010 or Excel 2007</span></span>

### <a name="summary"></a><span data-ttu-id="539e3-318">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-318">Summary</span></span>

<span data-ttu-id="539e3-319">Bandbreiten Auslastungsanalyse wird verwendet, um die Nutzung der Audiobandbreite für UC-Datenverkehr über das Netzwerk darzustellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-319">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="539e3-320">Dieses Tool kann verwendet werden, um die Nutzung der Videobandbreite auch im Netzwerk zu melden.</span><span class="sxs-lookup"><span data-stu-id="539e3-320">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

## <a name="call-parkometer"></a><span data-ttu-id="539e3-321">Parkometer aufrufen</span><span class="sxs-lookup"><span data-stu-id="539e3-321">Call Parkometer</span></span>
<span data-ttu-id="539e3-322"><a name="callpark"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-322"><a name="callpark"> </a></span></span>

<span data-ttu-id="539e3-323">Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Orbit-Datenbank für das Parken von Anrufen bietet.</span><span class="sxs-lookup"><span data-stu-id="539e3-323">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-324">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-324">Description</span></span>

<span data-ttu-id="539e3-325">Call Parkometer ist ein Tool zum Nachverfolgen von zurzeit geparkten anrufen.</span><span class="sxs-lookup"><span data-stu-id="539e3-325">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="539e3-326">Außerdem werden Statistiken zu Orbits und zur Verwendung durch den Anruf Park Server (CPS) gesammelt.</span><span class="sxs-lookup"><span data-stu-id="539e3-326">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="539e3-327">Dieses Befehlszeilentool bietet sowohl Lese-als auch Schreibzugriff auf die CPS-Umlaufbahn SQL Server Datenbank von einem lokalen oder Remote verbundenen Computer.</span><span class="sxs-lookup"><span data-stu-id="539e3-327">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="539e3-328">Alle Optionen schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-328">All options are mutually exclusive.</span></span> <span data-ttu-id="539e3-329">Die Befehlszeilensyntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="539e3-329">Command-line syntax is as follows:</span></span>

- <span data-ttu-id="539e3-330">**-o-** Parameter – listet alle orbitbereiche auf, die für diesen Pool konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-330">**-o** parameter—lists all orbit ranges configured for this pool.</span></span>

- <span data-ttu-id="539e3-331">**-n-** Parameter – listet alle aktuell verwendeten Umlaufbahnen in diesem Pool auf.</span><span class="sxs-lookup"><span data-stu-id="539e3-331">**-n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="539e3-332">Die angezeigten Informationen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="539e3-332">The information displayed is as follows:</span></span>

  - <span data-ttu-id="539e3-333">SIP-URI (Uniform Resource Identifier) der parkee und Parker.</span><span class="sxs-lookup"><span data-stu-id="539e3-333">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>

  - <span data-ttu-id="539e3-334">Hostname des CPS, in dem der Anruf geparkt wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-334">Host name of the CPS where the call is parked.</span></span>

  - <span data-ttu-id="539e3-335">Zeitstempel des Zeitraums, in dem der Anruf geparkt wurde.</span><span class="sxs-lookup"><span data-stu-id="539e3-335">Time stamp of when the call was parked.</span></span>

- <span data-ttu-id="539e3-336">**-f-** Parameter – listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf.</span><span class="sxs-lookup"><span data-stu-id="539e3-336">**-f** parameter—lists the number of currently free orbits in the pool.</span></span>

- <span data-ttu-id="539e3-337">\*\*-r \<n\> \*\* Parameter – listet die \<n\> zuletzt geparkten Anrufe auf.</span><span class="sxs-lookup"><span data-stu-id="539e3-337">**-r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="539e3-338">Die angezeigten Informationen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="539e3-338">The information displayed is as follows:</span></span>

  - <span data-ttu-id="539e3-339">SIP-URI des geparkten.</span><span class="sxs-lookup"><span data-stu-id="539e3-339">Parkee SIP URI.</span></span>

  - <span data-ttu-id="539e3-340">Parker-SIP-URI.</span><span class="sxs-lookup"><span data-stu-id="539e3-340">Parker SIP URI.</span></span>

  - <span data-ttu-id="539e3-341">Hostname des CPS, in dem der Anruf geparkt wurde.</span><span class="sxs-lookup"><span data-stu-id="539e3-341">Host name of the CPS where the call was parked.</span></span>

  - <span data-ttu-id="539e3-342">Zeitstempel für den Zeitpunkt, zu dem der Anruf abgerufen oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="539e3-342">Time stamp of when the call was retrieved or dropped.</span></span>

- <span data-ttu-id="539e3-343">\*\*-t\<n\> \*\* Parameter-testet das Reservieren einer Umlaufbahn in der Datenbank, um die Zufälligkeit der zugewiesenen Umlaufbahn Nummern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="539e3-343">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-344">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-344">Output</span></span>

<span data-ttu-id="539e3-345">Abhängig von den Eingabeparametern, die an einer Eingabeaufforderung angegeben werden, zeigt Call Parkometer die folgende Ausgabe an:</span><span class="sxs-lookup"><span data-stu-id="539e3-345">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

- <span data-ttu-id="539e3-346">Alle Umlaufbahn Bereiche, die für diesen Pool konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="539e3-346">All orbit ranges that are configured for this pool</span></span>

- <span data-ttu-id="539e3-347">Zurzeit geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="539e3-347">Currently parked calls</span></span>

- <span data-ttu-id="539e3-348">Anzahl freier (verfügbarer) Umlaufbahnen</span><span class="sxs-lookup"><span data-stu-id="539e3-348">Number of free (available) orbits</span></span>

- <span data-ttu-id="539e3-349">Zuletzt geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="539e3-349">Recently parked calls</span></span>

- <span data-ttu-id="539e3-350">Reservierte Umlaufbahnen zum Testen von einheitlichen und zufälligen Umlaufbahn Werten</span><span class="sxs-lookup"><span data-stu-id="539e3-350">Reserved orbits for testing uniform and random orbit values</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-351">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-351">Purpose</span></span>

<span data-ttu-id="539e3-352">Der Zweck des CPS-Tools besteht darin, den Befehlszeilenzugriff auf die CPS-Datenbank bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-352">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="539e3-353">Der Administrator kann die CPS-Verwendung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-353">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-354">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-354">Requirements</span></span>

<span data-ttu-id="539e3-355">Es gibt keine Anforderungen, wenn dieses Tool auf demselben Computer ausgeführt wird, auf dem CPS ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-355">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="539e3-356">Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von Skype for Business Server 2015 verwendete SQL Server Datenbank so konfiguriert werden, dass der Remotezugriff zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-356">If this tool is run on a remote computer, the SQL Server database used by Skype for Business Server 2015 must be configured to allow remote access.</span></span> <span data-ttu-id="539e3-357">Der Aufruf Parkometer muss mit einer SQL Server Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-357">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool's SQL Server.</span></span> <span data-ttu-id="539e3-358">Diese SQL Server Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Es muss sich in demselben Verzeichnis befinden, in dem sich parkometer. exe befindet.</span><span class="sxs-lookup"><span data-stu-id="539e3-358">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="539e3-359">Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (beispielsweise mydomain\Administrator), Kennwort (beispielsweise mypassword) und Hostname (beispielsweise MyServer).</span><span class="sxs-lookup"><span data-stu-id="539e3-359">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

### <a name="examples"></a><span data-ttu-id="539e3-360">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-360">Examples</span></span>

<span data-ttu-id="539e3-361">Bereitgestellte Umlaufbahn Bereiche: der-o-Parameter listet alle orbitbereiche auf, die für diesen Pool konfiguriert sind (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="539e3-361">Deployed orbit ranges: the -o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

![Orbitbereiche in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

<span data-ttu-id="539e3-363">Zurzeit geparkte Anrufe: der Parameter-n listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="539e3-363">Currently parked calls: the -n parameter lists all currently used orbits on this pool as shown</span></span>

![Zurzeit geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

<span data-ttu-id="539e3-365">Anzahl der freien Umlaufbahnen: der-f-Parameter listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="539e3-365">Number of free orbits: the -f parameter lists the number of currently free orbits in the pool as shown</span></span>

![Freie Umlaufbahnen in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

<span data-ttu-id="539e3-367">Zuletzt geparkte Anrufe: der Parameter \<-\> r n listet \<die\> n zuletzt geparkten Anrufe wie dargestellt auf.</span><span class="sxs-lookup"><span data-stu-id="539e3-367">Recently parked calls: the -r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

![Zuletzt geparkte Anrufe in Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

<span data-ttu-id="539e3-369">Test Orbit-Reservierung: der- \<t\> n-Parameter testet, wie in der Abbildung gezeigt, eine Umlaufbahn in der Datenbank reserviert</span><span class="sxs-lookup"><span data-stu-id="539e3-369">Test orbit reservation: the -t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

![Testen Sie die Orbit-Reservierungen in der Anruf Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a><span data-ttu-id="539e3-371">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-371">Summary</span></span>

<span data-ttu-id="539e3-372">Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Server für das Parken von Anrufen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-372">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

## <a name="dbanalyze"></a><span data-ttu-id="539e3-373">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="539e3-373">DBAnalyze</span></span>
<span data-ttu-id="539e3-374"><a name="dba"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-374"><a name="dba"> </a></span></span>

### <a name="description"></a><span data-ttu-id="539e3-375">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-375">Description</span></span>

<span data-ttu-id="539e3-376">Dbanalyze ist ein Befehlszeilentool, mit dem Administratoren Analyseberichte zu den Skype for Business Server 2015 Datenbanken sammeln können.</span><span class="sxs-lookup"><span data-stu-id="539e3-376">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Skype for Business Server 2015 databases.</span></span> <span data-ttu-id="539e3-377">Dbanalyze verfügt über die folgenden Modi: Diagnose, Benutzerdaten, Konferenz, MCU und Datenträgerfragmentierung:</span><span class="sxs-lookup"><span data-stu-id="539e3-377">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

- <span data-ttu-id="539e3-378">**Diagnosemodus** Erstellt einen Bericht mit Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern mit Microsoft Office Communications Server, die durchschnittliche Anzahl von Berechtigungen, Kontakte, Container, Abonnements, Publikationen, Endpunkte pro Benutzer, nicht ordnungsgemäß verwaltete Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplante Konferenzen, aktive Konferenzen, und die Datenbankversion.</span><span class="sxs-lookup"><span data-stu-id="539e3-378">**Diagnostic mode** Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can't be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>

    > [!NOTE]
    > <span data-ttu-id="539e3-379">Die Ausführung des Diagnosemodus kann sich auf die Serverleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="539e3-379">Running diagnostic mode can affect server performance.</span></span>

- <span data-ttu-id="539e3-380">**Benutzerdaten Modus** Meldet Kontakt-, Container-, Abonnement-, Publikations-, Berechtigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben.</span><span class="sxs-lookup"><span data-stu-id="539e3-380">**User data mode** Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="539e3-381">In diesem Modus werden auch Zusammenfassungsdaten für Konferenzen gemeldet, die ein Benutzer organisiert oder dazu eingeladen wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-381">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

- <span data-ttu-id="539e3-382">**Konferenzmodus** Meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Terminplanzeit Details für die Konferenz, der Einladungsliste, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und des Signalisierungs Status jedes Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="539e3-382">**Conference mode** Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant's signaling state.</span></span>

- <span data-ttu-id="539e3-383">**Decodieren der Besprechungs-ID** Decodiert eine PSTN-Besprechungs-ID (Public Switched Telephone Network), die durch den **Parameter/pstnid** -Switch angegeben wird, aber keine Verbindung zum Back-End für detaillierte Informationen.</span><span class="sxs-lookup"><span data-stu-id="539e3-383">**Decode Meeting ID** Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

- <span data-ttu-id="539e3-384">**Konferenz auflösen** Decodiert eine von der **Parameter/pstnid** -Option angegebene PSTN-Besprechungs-ID und zeigt Informationen über die durch die ID angegebene Konferenz an.</span><span class="sxs-lookup"><span data-stu-id="539e3-384">**Resolve conference** Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

- <span data-ttu-id="539e3-385">**MCU-Modus** Meldet die ID, den Medientyp, die URL, den Takt Status, die Konferenz Last und die Teilnehmer Auslastung für jede MCU im Pool.</span><span class="sxs-lookup"><span data-stu-id="539e3-385">**MCUs mode** Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

- <span data-ttu-id="539e3-386">**Datenträger Fragmentierungs Modus** Zeigt den Fragmentierungs Status aller Datenträger an.</span><span class="sxs-lookup"><span data-stu-id="539e3-386">**Disk fragmentation mode** Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="539e3-387">Dieses Tool kann verwendet werden, um verschiedene Probleme zu diagnostizieren oder Administratoren bei der Kapazitätsplanung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="539e3-387">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="539e3-388">Wenn beispielsweise die meisten der Benutzer, die sich auf dem Server a befinden, Benutzer auf Server b als Kontakte verwaltet haben, kann der Administrator die Benutzer auf Server a auf Server b umstellen, um den serverübergreifenden Datenverkehr zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-388">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-389">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-389">Output</span></span>

<span data-ttu-id="539e3-390">Dieses Tool gibt vordefinierte Berichte zur Skype for Business Server 2015 Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-390">This tool outputs predefined reports about the Skype for Business Server 2015 database.</span></span> <span data-ttu-id="539e3-391">**Pfad**:%ProgramFiles%\Skype for Business Server 2015 \ reskit</span><span class="sxs-lookup"><span data-stu-id="539e3-391">**Path**: %ProgramFiles%\Skype for Business Server 2015\Reskit</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-392">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-392">Purpose</span></span>

<span data-ttu-id="539e3-393">Um Dbanalyze. exe zu installieren, kopieren Sie Sie in einen lokalen Ordner, und führen Sie das Tool aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-393">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="539e3-394">Führen Sie den folgenden Befehl an der Befehlszeile aus, um das Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="539e3-394">To use the tool, run the following command from the command line.</span></span> <span data-ttu-id="539e3-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Die Beschreibungen der Befehlszeilenoptionen werden unten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-395">`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` The descriptions for the command-line options are shown below.</span></span>

![Befehlszeilenoptionen für Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a><span data-ttu-id="539e3-397">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-397">Requirements</span></span>

 <span data-ttu-id="539e3-398">**Computer** Dbanalyze kann nur von einem Computer ausgeführt werden, der der Domäne angehört und auf dem Skype for Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-398">**Computer** DBAnalyze can be run only from a domain-joined computer that has Skype for Business Server 2015 installed.</span></span>

 <span data-ttu-id="539e3-399">**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-399">**Network** The computer should be able to connect to the back-end database.</span></span>

 <span data-ttu-id="539e3-400">**Software** Skype for Business Server 2015 Softwarekomponenten müssen vor dem Ausführen von Dbanalyze installiert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-400">**Software** Skype for Business Server 2015 software components must be installed before running DBAnalyze.</span></span>

 <span data-ttu-id="539e3-401">**Benutzer** Die folgende Tabelle zeigt die Administratoren, die über die erforderlichen Berechtigungen für den Zugriff auf Skype for Business Server 2015-Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="539e3-401">**Users**The table below shows the administrators who have the necessary permissions to access Skype for Business Server 2015 databases.</span></span>

![Berechtigungstabelle für Dbanalyze. exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> <span data-ttu-id="539e3-403">Für/Report ist ein lokales Administratorkonto erforderlich **: Datenträger** Modus.</span><span class="sxs-lookup"><span data-stu-id="539e3-403">A local administrator account is required for **/report:disk** mode.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-404">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-404">Examples</span></span>

<span data-ttu-id="539e3-405">Im folgenden sind Beispiele für gültige Dbanalyze. exe-Befehle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="539e3-405">The following are examples of valid Dbanalyze.exe commands:</span></span>

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a><span data-ttu-id="539e3-406">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-406">Summary</span></span>

<span data-ttu-id="539e3-407">Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse Skype for Business Server 2015 Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="539e3-407">DBAnalyzer provides administrators a quick and easy to analyze Skype for Business Server 2015 databases.</span></span>

## <a name="import-storage-service-data"></a><span data-ttu-id="539e3-408">Importieren von Speicherdienst Daten</span><span class="sxs-lookup"><span data-stu-id="539e3-408">Import Storage Service Data</span></span>
<span data-ttu-id="539e3-409"><a name="Issd"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-409"><a name="Issd"> </a></span></span>

<span data-ttu-id="539e3-410">Das ImportStorageServiceData Resource Kit-Tool ermöglicht das erneute Importieren von Warteschlangen-und Endpunkt Daten, die aus dem Speicherdienst (LYSS) wieder in den Speicherdienst geleert wurden.</span><span class="sxs-lookup"><span data-stu-id="539e3-410">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-411">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-411">Description</span></span>

<span data-ttu-id="539e3-412">Die aus dem Speicherdienst gelöschten Daten konnten auf der Grundlage des Warteschlangenelement Status oder der Datenbankgröße automatisch (regelmäßig) sein.</span><span class="sxs-lookup"><span data-stu-id="539e3-412">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="539e3-413">Möglicherweise ist dies auf den manuellen Aufruf des Cmdlets "Pool Failover" oder auf das StorageServiceFullFlush-Cmdlet zurückzuführen, das vom Pool-Failover-Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-413">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="539e3-414">Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, da dies wahrscheinlich dazu führt, dass mehr Daten zurück exportiert werden. Außerdem sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange ansteigt, zuerst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).</span><span class="sxs-lookup"><span data-stu-id="539e3-414">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

 <span data-ttu-id="539e3-415">**Szenario 1:** während des Pool Failovers können Dateien für jedes Front-End aus dem Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-415">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="539e3-416">Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-416">After failover is completed, the tool should be run to re-import the data.</span></span>

 <span data-ttu-id="539e3-417">**Szenario 2:** die Daten werden jeden Tag automatisch oder als Reaktion auf die Speicherdienst Datenbank geleert, die bestimmte größenschwellenwerte überschreitet (beispielsweise 60%, 80%, 90% vollständig).</span><span class="sxs-lookup"><span data-stu-id="539e3-417">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="539e3-418">Diese automatisch gespülten Daten sollten vom Administrator routinemäßig erneut importiert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-418">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="539e3-419">Wenn das Monitoring-SCOM-Paket nicht bereitgestellt ist, gibt es in der obigen Situation Ereignisse für Skype for Business Server Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-419">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Skype for Business Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="539e3-420">Ereignis-IDs von 32075 (vollständiger Löschvorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Wartungsebene ist leer), 32089 (Flush erfolgte aufgrund des Füllens der Datenbank).</span><span class="sxs-lookup"><span data-stu-id="539e3-420">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="539e3-421">Hinweis Diese Ereignis-IDs entsprechen der RTM-Version.</span><span class="sxs-lookup"><span data-stu-id="539e3-421">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="539e3-422">Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien geleert wurden. Diese Daten sollten mit diesem Tool routinemäßig wieder importiert werden, beispielsweise einmal pro Woche.</span><span class="sxs-lookup"><span data-stu-id="539e3-422">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="539e3-423">Wenn für die Online Dienstversion die SCOM Pack for Skype for Business Server-Integritätsüberwachung bereitgestellt wird, werden möglicherweise neue Warnungen ausgelöst, die den Administrator auffordern, die gelöschten Daten wieder in den Speicherdienst zu importieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-423">For the Online Service release, if health monitoring SCOM pack for Skype for Business Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="539e3-424">Im Ereignisprotokoll auf dem Front-End-Server, der die Warnung ausgelöst hat, ist ein entsprechendes Ereignis vorhanden.</span><span class="sxs-lookup"><span data-stu-id="539e3-424">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="539e3-425">Das Ereignis gibt eine Beschreibung des übergeordneten Pfads an, unter dem sich die geleerten Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="539e3-425">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="539e3-426">Die Warnungskriterien sind, dass es x oder mehr Dateien unter dem bestimmten übergeordneten Pfad gibt, die mindestens Y Tage alt sind (wobei x und y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei außer Kraft gesetzt werden können). Im folgenden werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können: der Unterschied ist der übergeordnete Pfad.</span><span class="sxs-lookup"><span data-stu-id="539e3-426">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="539e3-427">Eine Möglichkeit besteht unter Webdienst-Dateifreigabe, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-427">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="539e3-428">(beispielsweise c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService).</span><span class="sxs-lookup"><span data-stu-id="539e3-428">( for example c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService ).</span></span> <span data-ttu-id="539e3-429">Der Administrator führt dann dieses reskit-Tool aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-429">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="539e3-430">Dieses Tool erhöht die CPU-und e/a-Last auf dem Front-End, auf dem es ausgeführt wird, sowie anderen Front-Ends in der Situation, dass die Daten nicht dem Front-End gehören, auf dem das Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-430">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="539e3-431">Es wird empfohlen, dieses Tool Ausführung, wenn die Front-Ends nicht unter starker CPU-und e/a-Last stehen, beispielsweise außerhalb der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="539e3-431">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="539e3-432">Zweitens kann dieses Tool 2 bis 3 Minuten, um eine Datendatei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-432">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="539e3-433">Beachten Sie dies, wenn Sie schätzen, wie lange das Tool in Betrieb sein wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-433">Keep this in mind when estimating how long tool will be running.</span></span> <span data-ttu-id="539e3-434">Die vom Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-434">The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="539e3-435">Löschen Sie es, wenn keine Fehler gemeldet werden, da die Protokolldatei zehn MB oder mehr sein kann.</span><span class="sxs-lookup"><span data-stu-id="539e3-435">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

![Beispiele für Ereignisprotokoll Ereignisse des Speicherservers.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a><span data-ttu-id="539e3-437">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-437">Requirements</span></span>

<span data-ttu-id="539e3-438">Installieren Sie die Skype for Business Server 2015 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="539e3-438">Install the Skype for Business Server 2015 Resource Kit tools.</span></span> <span data-ttu-id="539e3-439">Das Tool wird auf Computern mit Domänenbeitritt ausgeführt, auf denen Skype for Business Server und Skype for Business Server Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-439">The tool runs on domain-joined machines where Skype for Business Server and Skype for Business Server Management Shell are installed.</span></span> <span data-ttu-id="539e3-440">Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-440">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="539e3-441">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-441">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="539e3-442">Diese Datenbank wird vom Tool zum Abrufen des Speicherorts der Webservice-Dateifreigabe für den Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="539e3-442">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.</span></span> <span data-ttu-id="539e3-443">Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools Windows PowerShell Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer, von dem aus das Tool ausgeführt wird, aktivieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-443">Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="539e3-444">Andernfalls tritt für Remote Windows PowerShell-Befehle dieses Tools ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="539e3-444">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="539e3-445">Windows PowerShell Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="539e3-445">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="539e3-446">Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über Lese-/Schreibzugriff auf die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-446">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="539e3-447">Andernfalls kann das Tool mit e/a-Berechtigungsfehlern fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="539e3-447">Otherwise the tool will fail with IO Permission errors.</span></span>

> [!NOTE]
> <span data-ttu-id="539e3-448">In Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht auf dem Betriebssystem Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="539e3-448">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-449">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-449">Examples</span></span>

```console
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

## <a name="lcssync"></a><span data-ttu-id="539e3-450">LCSSync</span><span class="sxs-lookup"><span data-stu-id="539e3-450">LCSSync</span></span>
<span data-ttu-id="539e3-451"><a name="LCSSync"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-451"><a name="LCSSync"> </a></span></span>

<span data-ttu-id="539e3-452">Das LCSSync-Tool hilft bei der Bereitstellung Skype for Business Server 2015 Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="539e3-452">The LCSSync tool helps to deploy Skype for Business Server 2015 communications software in a multi-forest environment.</span></span> <span data-ttu-id="539e3-453">Dieses Tool dient zum Synchronisieren von Benutzern und Gruppen aus unterschiedlichen Benutzergesamtstrukturen als Active Directory-Domänendienste Kontaktobjekt mit einer zentralen Gesamtstruktur, in der Skype for Business Server 2015 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-453">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Skype for Business Server 2015 is installed.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-454">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-454">Description</span></span>

 <span data-ttu-id="539e3-455">LCSSync verwendet die synchronisierten Active Directory-Domänendienste Contact-Objekte in der zentralen Gesamtstruktur, um Benutzer für Skype for Business Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-455">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Skype for Business Server.</span></span> <span data-ttu-id="539e3-456">Um die einmalige Anmeldung bereitstellen zu können, muss das primäre Benutzerkonto dem Active Directory-Domänendienste Contact-Objekt in der zentralen Gesamtstruktur für Skype for Business Server 2015 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-456">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Skype for Business Server 2015.</span></span> <span data-ttu-id="539e3-457">Dieses Tool unterstützt Sie bei der Durchführung dieser Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="539e3-457">This tool helps perform that mapping.</span></span> <span data-ttu-id="539e3-458">Dieses Tool enthält Vorlagen zum Erstellen von Verwaltungs-Agents auf dem Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="539e3-458">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

### <a name="summary"></a><span data-ttu-id="539e3-459">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-459">Summary</span></span>

<span data-ttu-id="539e3-460">Das LCSSync-Tool hilft bei der Bereitstellung von Skype for Business Server 2015 in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="539e3-460">The LCSSync tool helps to deploy Skype for Business Server 2015 in a multi-forest environment.</span></span>

## <a name="lookup-user-console"></a><span data-ttu-id="539e3-461">Lookup-Benutzerkonsole</span><span class="sxs-lookup"><span data-stu-id="539e3-461">Lookup User Console</span></span>
<span data-ttu-id="539e3-462"><a name="LUC"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-462"><a name="LUC"> </a></span></span>

<span data-ttu-id="539e3-463">Das LookupUserConsole-Tool zeigt interne Skype for Business Server Routinginformationen zu bestimmten Benutzern an.</span><span class="sxs-lookup"><span data-stu-id="539e3-463">The LookupUserConsole tool displays internal Skype for Business Server routing information about specific users.</span></span> <span data-ttu-id="539e3-464">Diese Informationen können für den Microsoft-Support persönlich hilfreich sein, wenn Sie Bereitstellungs-und Routingprobleme diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-464">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-465">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-465">Description</span></span>

 <span data-ttu-id="539e3-466">Durch die Ausführung von LookupUserConsole. exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne Skype for Business Server Routinginformationen anzuzeigen, die Sie betreffen.</span><span class="sxs-lookup"><span data-stu-id="539e3-466">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Skype for Business Server routing information relating them.</span></span> <span data-ttu-id="539e3-467">Geben Sie **Exit** ein, um das LookupUserConsole-Tool zu beenden.</span><span class="sxs-lookup"><span data-stu-id="539e3-467">Type **exit** to quit the LookupUserConsole tool.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-468">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-468">Requirements</span></span>

<span data-ttu-id="539e3-469">Installieren Sie das Skype for Business Server 2015 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="539e3-469">Install the Skype for Business Server 2015 Resource Kit.</span></span> <span data-ttu-id="539e3-470">Das Tool wird auf Computern mit Domänenbeitritt ausgeführt, auf denen Skype for Business Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-470">The tool runs on domain-joined machines where Skype for Business Server is installed.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-471">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-471">Examples</span></span>

<span data-ttu-id="539e3-472">C:\Program Files\Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="539e3-472">C:\Program Files\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe</span></span>

```console
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

## <a name="msturnping"></a><span data-ttu-id="539e3-473">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="539e3-473">MsTurnPing</span></span>
<span data-ttu-id="539e3-474"><a name="MsTurnPing"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-474"><a name="MsTurnPing"> </a></span></span>

<span data-ttu-id="539e3-475">Mit dem MSTurnPing-Tool kann ein Administrator von Skype for Business Server 2015 Kommunikationssoftware den Status der Server, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste durchführen, sowie die Server überprüfen, auf denen Bandbreitenrichtlinien Dienste in der Topologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-475">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-476">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-476">Description</span></span>

<span data-ttu-id="539e3-477">Mit dem MSTurnPing-Tool kann ein Administrator von Skype for Business Server 2015 Kommunikationssoftware den Status der Server, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste durchführen, sowie die Server überprüfen, auf denen Bandbreitenrichtlinien Dienste in der Topologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-477">The MSTurnPing tool allows an administrator of Skype for Business Server 2015 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="539e3-478">Das Tool ermöglicht es dem Administrator, die folgenden Tests auszuführen:</span><span class="sxs-lookup"><span data-stu-id="539e3-478">The tool allows the administrator to perform the following tests:</span></span>

1. <span data-ttu-id="539e3-479">A/v-Edgeserver Test: das Tool führt Tests für alle A/v-Edgeserver in der Topologie aus, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="539e3-479">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>

   - <span data-ttu-id="539e3-480">Überprüfen, ob der Skype for Business Server Audio/Video-Authentifizierungsdienst gestartet wurde, und Sie können ordnungsgemäße Anmeldeinformationen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="539e3-480">Verifying that the Skype for Business Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="539e3-481">Überprüfen, ob der Skype for Business Server Audio/Video-Edgedienst gestartet wurde, und die Ressourcen auf dem externen edgevorgang erfolgreich zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="539e3-481">Verifying that the Skype for Business Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2. <span data-ttu-id="539e3-482">Bandbreitenrichtliniendienst Test: das Tool führt Tests für alle Server aus, auf denen die Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="539e3-482">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>

   - <span data-ttu-id="539e3-483">Überprüfen, ob der Skype for Business Server bandbreitenrichtliniendienst (Authentication) gestartet wurde und ordnungsgemäße Anmeldeinformationen ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="539e3-483">Verifying that the Skype for Business Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>

   - <span data-ttu-id="539e3-484">Überprüfen, ob der Skype for Business Server bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="539e3-484">Verifying that the Skype for Business Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="539e3-485">Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-485">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-486">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-486">Output</span></span>

<span data-ttu-id="539e3-487">Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-487">The tool outputs the results of each of the operations.</span></span>

- <span data-ttu-id="539e3-488">Wenn der **AudioVideoEdgeServer** -Test durchgeführt wird, werden die Ausgaben des Tools folgendermaßen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="539e3-488">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="539e3-489">Die Testergebnisse der Computer, die den Skype for Business Server 2015-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="539e3-489">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Authentication service in the topology</span></span>

  - <span data-ttu-id="539e3-490">Die Testergebnisse der Computer, die den Skype for Business Server 2015 Audio/Video-Edgedienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="539e3-490">The test results of the computers that provide the Skype for Business Server 2015 Audio/Video Edge service in the topology</span></span>

- <span data-ttu-id="539e3-491">Wenn der **BandwidthPolicyServer** -Test durchgeführt wird, werden die Ausgaben des Tools folgendermaßen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="539e3-491">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>

  - <span data-ttu-id="539e3-492">Die Testergebnisse der Computer, die den Skype for Business Server 2015 bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="539e3-492">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Authentication) in the topology</span></span>

  - <span data-ttu-id="539e3-493">Die Testergebnisse der Computer, die den Skype for Business Server 2015 bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="539e3-493">The test results of the computers that provide the Skype for Business Server 2015 Bandwidth Policy Service (Core) in the topology</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-494">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-494">Requirements</span></span>

- <span data-ttu-id="539e3-495">Dieses Tool muss von einem Computer ausgeführt werden, der sich in der Topologie befindet und über den lokalen Speicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="539e3-495">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

- <span data-ttu-id="539e3-496">Das Tool muss als Administrator ausgeführt werden, der Zugriff auf den lokalen Speicher hat.</span><span class="sxs-lookup"><span data-stu-id="539e3-496">The tool must be run as an administrator who has access to the local store.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-497">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-497">Examples</span></span>

<span data-ttu-id="539e3-498">Nachfolgend sehen Sie ein Beispiel für die Tool Eingabe.</span><span class="sxs-lookup"><span data-stu-id="539e3-498">The following is an example of the tool input.</span></span>

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a><span data-ttu-id="539e3-499">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-499">Summary</span></span>

<span data-ttu-id="539e3-500">Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015 Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste durchführen.</span><span class="sxs-lookup"><span data-stu-id="539e3-500">This tool can be a valuable resource to Skype for Business Server 2015 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

## <a name="network-configuration-viewer"></a><span data-ttu-id="539e3-501">Netzwerk Konfigurationsanzeige</span><span class="sxs-lookup"><span data-stu-id="539e3-501">Network Configuration Viewer</span></span>
<span data-ttu-id="539e3-502"><a name="NCV"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-502"><a name="NCV"> </a></span></span>

<span data-ttu-id="539e3-503">Die Netzwerkkonfigurations-Anzeige kann von Skype for Business Server 2015 Kommunikationssoftware Administratoren verwendet werden, um die Anruf Steuerungs Netzwerk-Topologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zuzulassen, beispielsweise Sprach-oder Videoanrufe basierend auf der angegebenen Bandbreitenkapazität.</span><span class="sxs-lookup"><span data-stu-id="539e3-503">Network Configuration Viewer can be used by Skype for Business Server 2015 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="539e3-504">Skype for Business Server 2015 Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit Skype for Business Server 2015 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-504">Skype for Business Server 2015 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Skype for Business Server 2015.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-505">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-505">Description</span></span>

<span data-ttu-id="539e3-506">Network Configuration Viewer (NetworkConfigurationViewer. exe) ermöglicht Administratoren das Ausführen der folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="539e3-506">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

- <span data-ttu-id="539e3-507">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung in einem grafischen Format.</span><span class="sxs-lookup"><span data-stu-id="539e3-507">Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format.</span></span>

- <span data-ttu-id="539e3-508">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format.</span><span class="sxs-lookup"><span data-stu-id="539e3-508">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

- <span data-ttu-id="539e3-509">Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="539e3-509">Save and store CAC network topology in an XML format on the disk.</span></span>

- <span data-ttu-id="539e3-510">Speichern und speichern Sie das Diagramm der CAC-Netzwerktopologie im JPG-oder BMP-Format.</span><span class="sxs-lookup"><span data-stu-id="539e3-510">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

- <span data-ttu-id="539e3-511">Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie.</span><span class="sxs-lookup"><span data-stu-id="539e3-511">View CAC network topology configuration data.</span></span>

- <span data-ttu-id="539e3-512">View CAC Network Topology in a Tree-View Style.</span><span class="sxs-lookup"><span data-stu-id="539e3-512">View CAC network topology in a tree-view style.</span></span>

- <span data-ttu-id="539e3-513">Definieren Sie benutzerdefinierte Connectors für CAC-Netzwerktopologie-Links (beispielsweise Standort-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links).</span><span class="sxs-lookup"><span data-stu-id="539e3-513">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

- <span data-ttu-id="539e3-514">Anzeigen der Informationen zur CAC-Netzwerktopologie, Regionsinformationen sowie Richtlinien für die verfügbare Bandbreite und Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="539e3-514">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-515">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-515">Purpose</span></span>

<span data-ttu-id="539e3-516">Anzeigen der Verknüpfungen der Enterprise-CAC-Netzwerktopologie in einer grafischen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="539e3-516">View enterprise CAC network topology links in a graphical interface.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-517">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-517">Examples</span></span>

 <span data-ttu-id="539e3-518">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Skype for Business Server 2015-Bereitstellung im grafischen Format**: Skype for Business Server 2015 Administratoren können die Konfiguration der CAC-Netzwerktopologie auf einem beliebigen Skype for Business Server 2015 Computer mithilfe der Option " **Netzwerkkonfiguration herunterladen** " Laden und anzeigen, wie in der Abbildung unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-518">**Load and view CAC network topology from a Skype for Business Server 2015 deployment in a graphical format**: Skype for Business Server 2015 administrators can load and view CAC network topology configuration on any Skype for Business Server 2015 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="539e3-519">Das Tool kann eine solche Konfiguration nicht herunterladen oder anzeigen, wenn Sie auf einem Computer bereitgestellt wird, der nicht über eine Verbindung mit dem Skype for Business Server 2015 Konfigurationsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="539e3-519">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Skype for Business Server 2015 configuration store.</span></span>

![Herunterladen der Netzwerkkonfiguration.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 <span data-ttu-id="539e3-521">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei im grafischen Format:** Skype for Business Server 2015 Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Skype for Business Server 2015 Dateifreigabespeicherort.</span><span class="sxs-lookup"><span data-stu-id="539e3-521">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Skype for Business Server 2015 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Skype for Business Server 2015 file share location.</span></span> <span data-ttu-id="539e3-522">Skype for Business Server 2015 Administratoren können eine solche Datei mit der **Open Network Configuration** -Option wie unten gezeigt in einem grafischen Format anzeigen.</span><span class="sxs-lookup"><span data-stu-id="539e3-522">Skype for Business Server 2015 administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

![Öffnen einer Bandbreitenrichtlinien Server-Protokolldatei.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

<span data-ttu-id="539e3-524">Speichern und speichern Sie die Anrufsteuerung-Netzwerktopologie in einem XML-Format auf dem Datenträger: Skype for Business Server 2015 Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** wie unten gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="539e3-524">Save and store CAC network topology in an XML format on the disk: Skype for Business Server 2015 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="539e3-525">Die gespeicherte Konfigurationsdatei kann dann offline für grafische Anzeigezwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-525">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

![Speichern der Netzwerkkonfiguration als XML-Datei.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

<span data-ttu-id="539e3-527">Speichern und Speichern von Diagrammen der CAC-Netzwerktopologie im JPG-oder BMP-Format: Skype for Business Server 2015 Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie die Option **Netzwerk Konfigurations Diagramm als Bild speichern** wie unten gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="539e3-527">Save and Store CAC network topology diagram in JPG or BMP format: Skype for Business Server 2015 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

![Speichern der Netzwerkkonfiguration als Bild.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <span data-ttu-id="539e3-529"><strong>Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:</strong> Skype for Business Server 2015 Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerkstandorte, Bandbreiten Profile und IP-Adressen von Standort Netzwerken in einem Text Format anzeigen, indem Sie die Option "Netzwerkkonfigurationsdaten anzeigen" wie unten dargestellt verwenden.</span><span class="sxs-lookup"><span data-stu-id="539e3-529"><strong>View CAC network topology configuration data:</strong>Skype for Business Server 2015 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

![Anzeigen von Netzwerkkonfigurationsdaten.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 <span data-ttu-id="539e3-531">**Anzeigen der Anruf Steuerungs Netzwerktopologie in einem Struktur Ansichtsstil:** Skype for Business Server 2015 Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsformat mithilfe der Systemsteuerung auf der linken Seite des Toolfensters anzeigen, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-531">**View CAC network topology in a tree-view style:** Skype for Business Server 2015 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 <span data-ttu-id="539e3-533">**Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Standort-zu-Region, Region-zu-Region und Standort-zu-Standort-Links):** Skype for Business Server 2015 Administratoren können benutzerdefinierte grafische Konnektoren für Netzwerk Konfigurations-WAN-Verbindungen mithilfe der Einstellungsoption wie unten dargestellt definieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-533">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Skype for Business Server 2015 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="539e3-534">Dies hilft bei der Unterscheidung zwischen verschiedenen Typen von Netzwerkverbindungen, die in der Netzwerkkonfiguration bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-534">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

![Tools](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 <span data-ttu-id="539e3-536">**Anzeigen der Informationen zur CAC-Netzwerktopologie, Regionsinformationen und Richtlinien für die verfügbare Bandbreite:** Skype for Business Server 2015 Administratoren können Informationen zu zugehörigen CAC-netzwerkregionen, Standortinformationen und Informationen zur Anruf Steuerungs Bandbreite mithilfe der unten aufgeführten Optionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="539e3-536">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Skype for Business Server 2015 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="539e3-537">(Klicken Sie beispielsweise in einer netzwerkregion oder einem Netzwerkstandort Objekt auf **Info** .)</span><span class="sxs-lookup"><span data-stu-id="539e3-537">(For example, click **Info** in a network region or network site object.)</span></span>

![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a><span data-ttu-id="539e3-539">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-539">Summary</span></span>

<span data-ttu-id="539e3-540">Dieses Tool kann eine wertvolle Ressource für Skype for Business Server 2015 Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="539e3-540">This tool can be a valuable resource to Skype for Business Server 2015 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

## <a name="response-group-agent-live"></a><span data-ttu-id="539e3-541">Reaktionsgruppen-Agent Live</span><span class="sxs-lookup"><span data-stu-id="539e3-541">Response Group Agent Live</span></span>
<span data-ttu-id="539e3-542"><a name="RGAL"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-542"><a name="RGAL"> </a></span></span>

<span data-ttu-id="539e3-543">Mit dem Reaktionsgruppenanwendung können Agents mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="539e3-543">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="539e3-544">Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="539e3-544">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="539e3-545">Das Reaktionsgruppen-Agent-Live Resource Kit-Tool löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die mit Echt Zeit Skype for Business Kommunikationssoftware Informationen wie etwa dem vorhanden sein anderer Agents erweitert wurde.</span><span class="sxs-lookup"><span data-stu-id="539e3-545">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Skype for Business communications software information such as the presence of other agents.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-546">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-546">Description</span></span>

<span data-ttu-id="539e3-547">Bei Agent Live für Reaktionsgruppen handelt es sich um eine Windows-Anwendung, die die Funktionen für die Anmeldung und Abmeldung sowie einige Echtzeitinformationen (beispielsweise die Gruppenmitgliedschaft und die aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-547">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="539e3-548">Es handelt sich um eine erweiterte Version der Seite "Agentgruppen" (verfügbar über Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="539e3-548">It is meant to be an enhanced version of the Agent Groups page (accessible from Skype for Business.</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-549">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-549">Purpose</span></span>

<span data-ttu-id="539e3-550">In der Reaktionsgruppenanwendung werden eingehende Anrufe in die Warteschlange eingereiht und an Agentgruppen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="539e3-550">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="539e3-551">Um fundierte Entscheidungen darüber zu treffen, welche Anrufe für Dienste durchzuführen sind, können Agents auf Echtzeitinformationen zu ihren Agentgruppen zugreifen, beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschlange warten.</span><span class="sxs-lookup"><span data-stu-id="539e3-551">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="539e3-552">Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst zugänglich sind, werden auf intuitive Weise vom Reaktionsgruppen-Agent Live zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-552">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

#### <a name="features"></a><span data-ttu-id="539e3-553">Features</span><span class="sxs-lookup"><span data-stu-id="539e3-553">Features</span></span>

<span data-ttu-id="539e3-554">Das Live-Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem Skype for Business Server 2015 SDK.</span><span class="sxs-lookup"><span data-stu-id="539e3-554">The Response Group Agent Live tool is built on the Response Group service and the Skype for Business Server 2015 SDK.</span></span> <span data-ttu-id="539e3-555">Sie stellt Reaktionsgruppen-Agents die Informationen und Funktionen zur Verfügung, die über den Reaktionsgruppendienst verfügbar sind (wie Gruppenmitgliedschaft, Anwesenheit von anderen Agents und Anzahl der wartenden Anrufe).</span><span class="sxs-lookup"><span data-stu-id="539e3-555">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="539e3-556">In der folgenden Abbildung ist die Hauptschnittstelle des Reaktionsgruppen-Agents Live dargestellt.</span><span class="sxs-lookup"><span data-stu-id="539e3-556">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

![Das Live-Tool für Reaktionsgruppen-Agents.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

<span data-ttu-id="539e3-558">Die folgenden drei Hauptfeatures stehen für Agents im Reaktionsgruppen-Agent Live zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="539e3-558">The following three main features are available for agents in Response Group Agent Live:</span></span>

- <span data-ttu-id="539e3-559">**Anmelden/Auschecken:** Im Gegensatz zur Seite "Agentgruppen" (auf die von Skype for Business Server 2015 zugegriffen werden kann) kann der Reaktionsgruppen-Agent Live nur Agents auf einmal anmelden oder sich bei allen Agentgruppen abmelden.</span><span class="sxs-lookup"><span data-stu-id="539e3-559">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Skype for Business Server 2015), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="539e3-560">Diese Anwendung bietet drei schnelle Methoden für die Anmeldung von Agents:</span><span class="sxs-lookup"><span data-stu-id="539e3-560">This application provides three quick ways for agents to sign in or out:</span></span>

  - <span data-ttu-id="539e3-561">Klicken Sie in der Anwendung auf die Schaltflächen zum Anmelden/Auschecken (grün und rot).</span><span class="sxs-lookup"><span data-stu-id="539e3-561">Click the Sign-in/out (green and red) buttons within the application.</span></span>

  - <span data-ttu-id="539e3-562">Klicken Sie mit der rechten Maustaste auf das Symbol in der Taskleiste, und wählen Sie anmelden oder Abmelden aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-562">Right-click the system tray icon, and select sign in or sign out.</span></span>

  - <span data-ttu-id="539e3-563">Verwenden von konfigurierbaren Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="539e3-563">Using configurable keyboard shortcuts.</span></span>

- <span data-ttu-id="539e3-564">**Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an.</span><span class="sxs-lookup"><span data-stu-id="539e3-564">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="539e3-565">Wenn Skype for Business Server 2015 auf demselben Computer wie diese Anwendung läuft, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-565">If Skype for Business Server 2015 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="539e3-566">Agents können direkt von dort aus einen Chat senden oder andere Agents anrufen.</span><span class="sxs-lookup"><span data-stu-id="539e3-566">Agents can send an IM or call other agents directly from there.</span></span>

- <span data-ttu-id="539e3-567">**Echtzeitstatistik:** Der Reaktionsgruppen-Agent Live bietet Echtzeitstatistiken für alle Agentgruppen.</span><span class="sxs-lookup"><span data-stu-id="539e3-567">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="539e3-568">Die Aktualisierungshäufigkeit beträgt eine Minute.</span><span class="sxs-lookup"><span data-stu-id="539e3-568">The update frequency is one minute.</span></span> <span data-ttu-id="539e3-569">Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein visuelles Symbol mit der aktuellen Anzahl von in der Warteschlange befindlichen anrufen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="539e3-569">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="539e3-570">Wenn Sie den Zeiger über eine Gruppe anhalten, wird auch die längste Wartezeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-570">Pausing the pointer over a group also displays the longest waiting time.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-571">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-571">Requirements</span></span>

<span data-ttu-id="539e3-572">Für den Reaktionsgruppen-Agent Live ist der .NET Framework 4,0 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="539e3-572">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="539e3-573">Darüber hinaus müssen Skype for Business lokal installiert sein (und ausgeführt werden), um die Anwesenheits-und Visitenkarten Funktionen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="539e3-573">In addition, to take advantage of the presence and contact card features, Skype for Business must be installed locally (and be running).</span></span>

#### <a name="configuration"></a><span data-ttu-id="539e3-574">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="539e3-574">Configuration</span></span>

<span data-ttu-id="539e3-575">Der Live Reaktionsgruppen-Agent kann mithilfe des Dialogfelds Optionen in der Anwendung an individuelle Einstellungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-575">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="539e3-576">Darüber hinaus kann der Administrator die Standardhost Adresse definieren, indem er die defaultHostAddress-Eigenschaft der Datei RGAgentLive. exe. config direkt bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="539e3-576">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="539e3-577">Die folgende Abbildung zeigt das Dialogfeldoptionen, mit dem Agents die Hostadresse und die Tastenkombinationen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="539e3-577">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="539e3-578">Der Zugriff auf dieses Dialogfeld erfolgt durch Klicken auf die Schaltfläche Optionen oben rechts auf der Hauptoberfläche.</span><span class="sxs-lookup"><span data-stu-id="539e3-578">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

![Das Dialogfeld Reaktionsgruppen-Agent-Live Optionen.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

<span data-ttu-id="539e3-580">Die folgenden drei unterschiedlichen Einstellungen können in der Live-Konfiguration des Reaktionsgruppen-Agents angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="539e3-580">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

- <span data-ttu-id="539e3-581">Host Adresse: Dies ist normalerweise der FQDN des webpools, der zum Home-Pool des Agents gehört.</span><span class="sxs-lookup"><span data-stu-id="539e3-581">Host address: This is typically the web pool FQDN belonging to the agent's home pool.</span></span> <span data-ttu-id="539e3-582">Die genaue Adresse des Reaktionsgruppendiensts wird automatisch aus diesen Informationen im Hintergrund abgeleitet (durch Anfügen des richtigen Pfads nach dem Host).</span><span class="sxs-lookup"><span data-stu-id="539e3-582">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

- <span data-ttu-id="539e3-583">Shortcuts: die genauen Verknüpfungen zum Anmelden/Auschecken können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-583">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="539e3-584">Die einzige Einschränkung besteht darin, dass beide Verknüpfungen die Taste "Windows-Logo" (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="539e3-584">The only limitation is that both shortcuts must contain the "Windows Logo" key (in addition to at least another key).</span></span>

- <span data-ttu-id="539e3-585">Beginnen mit Windows: die Anwendung kann so konfiguriert werden, dass Sie automatisch mit Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-585">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-586">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-586">Examples</span></span>

<span data-ttu-id="539e3-587">Die folgende Abbildung zeigt, wie Sie eine Sofortnachricht an einen anderen Agent aufrufen oder senden, indem Sie mit der rechten Maustaste auf den Kontakt im rechten Bereich klicken.</span><span class="sxs-lookup"><span data-stu-id="539e3-587">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

![Tätigen eines Anrufs oder Sendens eines Chats.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

<span data-ttu-id="539e3-589">Die folgende Abbildung zeigt, wie der Reaktionsgruppen-Agent Live die aktuelle Anzahl von Anrufen in der Warteschlange und die längste Wartezeit unter all diesen eingehenden Anrufen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-589">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

![Anzeigen von Warteschlangeninformationen.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a><span data-ttu-id="539e3-591">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-591">Summary</span></span>

<span data-ttu-id="539e3-592">Schnelle Anmeldung und Abmeldung, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Features für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung aus dem Reaktionsgruppendienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-592">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="539e3-593">Mit dem Reaktionsgruppen-Agent Live Resource Kit-Tool können Skype for Business Server 2015 Administratoren ihren Agents eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben schneller und grafischer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="539e3-593">With the Response Group Agent Live Resource Kit tool, Skype for Business Server 2015 administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

## <a name="sefautil"></a><span data-ttu-id="539e3-594">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="539e3-594">SEFAUtil</span></span>
<span data-ttu-id="539e3-595"><a name="SEFAUtil"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-595"><a name="SEFAUtil"> </a></span></span>

<span data-ttu-id="539e3-596">SEFAUtil (sekundäre Erweiterung Feature Activation) ist ein Befehlszeilentool, mit dem Skype for Business Server 2015 Kommunikationssoftware Administratoren und Helpdesk-Agents Delegierten Klingeln, Anrufweiterleitung, gleichzeitiges Klingeln konfigurieren können, Team Anrufeinstellungen und gruppenanrufannahme im Auftrag eines Skype for Business Server 2015 Benutzers.</span><span class="sxs-lookup"><span data-stu-id="539e3-596">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Skype for Business Server 2015 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="539e3-597">Das Tool ermöglicht es Administratoren auch, die Anrufweiterleitungseinstellungen abzufragen, die für einen bestimmten Benutzer veröffentlicht werden. Das SEFAUtil-Tool ermöglicht dem Administrator das aktivieren/deaktivieren/Ändern der Anrufweiterleitung oder das gleichzeitige Klingeln im Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="539e3-597">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="539e3-598">Der Administrator kann das Ziel (in Form eines SIP-URI) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="539e3-598">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="539e3-599">Mit diesem Tool können Administratoren auch Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzufügen oder entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-599">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil.</span></span>

<span data-ttu-id="539e3-600">SEFAUtil (sekundäre Erweiterung Feature Activation) ermöglicht es Skype for Business Server 2015 Administratoren und Helpdesk-Agents, Stellvertreter-Klingeln, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anrufeinstellungen und gruppenanrufannahme im Namen eines Skype-Benutzers zu konfigurieren. for Business Server 2015-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="539e3-600">SEFAUtil (secondary extension feature activation) enables Skype for Business Server 2015 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Skype for Business Server 2015 user.</span></span> <span data-ttu-id="539e3-601">Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen Abfragen, die für einen bestimmten Benutzer veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-601">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-602">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-602">Description</span></span>

<span data-ttu-id="539e3-603">Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="539e3-603">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="539e3-604">Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="539e3-604">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="539e3-605">Die Funktionen in diesem Tool ermöglichen Administratoren und Helpdesk-Agents Folgendes:</span><span class="sxs-lookup"><span data-stu-id="539e3-605">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

- <span data-ttu-id="539e3-606">Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Delegierung, gleichzeitiges Klingeln, Team-und gruppenanrufannahme)</span><span class="sxs-lookup"><span data-stu-id="539e3-606">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

- <span data-ttu-id="539e3-607">Aktivieren/Deaktivieren/Ändern der Einstellung für die Anrufweiterleitung (schließt den Ziel-und den nicht-Antwort-Timer ein)</span><span class="sxs-lookup"><span data-stu-id="539e3-607">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

- <span data-ttu-id="539e3-608">Aktivieren/Deaktivieren/Ändern der unmittelbaren Konfigurationen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="539e3-608">Enable/disable/modify call-forwarding immediate configurations</span></span>

- <span data-ttu-id="539e3-609">Aktivieren/Deaktivieren/ändern von Delegierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="539e3-609">Enable/disable/modify delegation settings</span></span>

- <span data-ttu-id="539e3-610">Aktivieren/Deaktivieren/ändern von Einstellungen für die Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="539e3-610">Enable/disable/modify team-call group settings</span></span>

    > [!NOTE]
    > <span data-ttu-id="539e3-611">Neu in Skype for Business Server 2015 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="539e3-611">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="539e3-612">Aktivieren/Deaktivieren/ändern gleichzeitiger Klingel Einstellungen (umfasst das Ziel)</span><span class="sxs-lookup"><span data-stu-id="539e3-612">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>

    > [!NOTE]
    > <span data-ttu-id="539e3-613">Neu in Skype for Business Server 2015 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="539e3-613">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

- <span data-ttu-id="539e3-614">Aktivieren/Deaktivieren/ändern von Einstellungen für die gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="539e3-614">Enable/disable/modify group call pickup settings</span></span>

    > [!CAUTION]
    > <span data-ttu-id="539e3-615">Neu in Skype for Business Server 2015 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="539e3-615">New in Skype for Business Server 2015 SEFAUtil tool</span></span>

<span data-ttu-id="539e3-616">Dieses Tool hat die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="539e3-616">This tool has the following limitations:</span></span>

- <span data-ttu-id="539e3-617">Nur für Benutzer unterstützt, die in einem Skype for Business Server-Pool verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="539e3-617">Supported only for users homed in a Skype for Business Server pool</span></span>

- <span data-ttu-id="539e3-618">Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="539e3-618">Bulk-edit of call routing settings for several users is not supported</span></span>

### <a name="output"></a><span data-ttu-id="539e3-619">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-619">Output</span></span>

<span data-ttu-id="539e3-620">Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster eine Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="539e3-620">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="539e3-621">Ausführliche Informationen finden Sie im Abschnitt "Beispiele" weiter unten in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="539e3-621">For details, see the Examples section later in this document.</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-622">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-622">Purpose</span></span>

<span data-ttu-id="539e3-623">Im folgenden finden Sie einige der wichtigsten Szenarien, in denen dieses Tool verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="539e3-623">Following are some of the key scenarios where this tool may be used:</span></span>

- <span data-ttu-id="539e3-624">Bob ist eine Führungskraft und wurde in Skype for Business Server Telefonie verschoben.</span><span class="sxs-lookup"><span data-stu-id="539e3-624">Bob is an executive and has been moved to Skype for Business Server telephony.</span></span> <span data-ttu-id="539e3-625">Er verfügt über eine Delegation für sein vorhandenes PBX-System.</span><span class="sxs-lookup"><span data-stu-id="539e3-625">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="539e3-626">Im Rahmen des Umstiegs auf Skype for Business Server 2015 kann der Administrator Bobs Routing so konfigurieren, dass er seine bereits vorhandene Delegierungs Konfiguration widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="539e3-626">As part of the move to Skype for Business Server 2015, the administrator is able to configure Bob's routing to reflect his pre-existing delegation configuration.</span></span>

- <span data-ttu-id="539e3-627">Alice reist und erkennt, dass Sie einen wichtigen Anruf von einem ihrer Kunden erwartet.</span><span class="sxs-lookup"><span data-stu-id="539e3-627">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="539e3-628">Sie befindet sich jedoch in einem Hotel und hat keinen Zugriff auf einen Computer.</span><span class="sxs-lookup"><span data-stu-id="539e3-628">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="539e3-629">Sie ruft den Helpdesk an und fordert an, dass Sie alle Anrufe an Ihre Telefonnummer an Ihre Mobiltelefonnummer weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="539e3-629">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="539e3-630">Das Helpdesk-Personal kann die Konfiguration in Ihrem Auftrag durchführen.</span><span class="sxs-lookup"><span data-stu-id="539e3-630">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

- <span data-ttu-id="539e3-631">Joes Anrufe an seine Arbeitsnummer gehen zu seiner mobilen Voicemail, wenn er bei der Arbeit ist; in den meisten anderen Speicherorten scheinen die Dinge jedoch korrekt zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="539e3-631">Joe's calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="539e3-632">Der Helpdesk-Techniker kann Joes Routingkonfiguration anzeigen und feststellt, dass Joe das gleichzeitige Klingeln auf seinem Mobiltelefon konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="539e3-632">The helpdesk technician is able to view Joe's routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="539e3-633">Der Techniker fragt Joe nach der mobilen Abdeckung in seinem Büro und kann feststellen, dass die gleichzeitige Klingel Regel ist, was dazu führt, dass die Anrufe an Joes Mobile Voicemail gehen, wenn seine Netzwerkabdeckung schlecht ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-633">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe's mobile voicemail when his network coverage is poor.</span></span>

- <span data-ttu-id="539e3-634">Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, für das alle Mitglieder für Teamanrufe konfiguriert sind, wenn es für Skype for Business Server 2015 aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass er alle neuen Teammitglieder einschließt. Zusätzlich fügt der Administrator Mike für jedes Mitglied in seinem Team als Teamanrufgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="539e3-634">Mike is a new employee at Contoso and he's joining a new team on which all members are configured for team-call, when being enabled for Skype for Business Server 2015, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

- <span data-ttu-id="539e3-635">Eine Kundendienst Praxis in der Personalabteilung von Contoso ist die Bereitstellung persönlicher Dienste für alle Anrufer seit dem ersten Anruf.</span><span class="sxs-lookup"><span data-stu-id="539e3-635">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="539e3-636">Da alle Mitglieder der Abteilung sehr nahe beieinander sitzen, ist es für das Team sehr störend, dass alle Telefone gleichzeitig mit dem Team Anruf Klingeln.</span><span class="sxs-lookup"><span data-stu-id="539e3-636">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="539e3-637">Um den besten Dienst bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der Skype for Business Server 2015 Administrator die Möglichkeit der gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="539e3-637">To provide the best service without disrupting the team members, the Skype for Business Server 2015 administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="539e3-638">Der Administrator fügt alle Abteilungsmitglieder zu einer Pickup-Gruppe hinzu und kommuniziert mit der Abteilung mit der Abhol Gruppennummer.</span><span class="sxs-lookup"><span data-stu-id="539e3-638">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="539e3-639">Wenn Samantha von Ihrem Schreibtisch abwesend ist, merkt Joe, dass Ihr Telefon klingelt und er den Anruf von seinem Schreibtisch aus beantwortet.</span><span class="sxs-lookup"><span data-stu-id="539e3-639">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-640">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-640">Requirements</span></span>

<span data-ttu-id="539e3-641">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-641">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="539e3-642">UCMA 3.0 muss auf diesem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="539e3-642">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="539e3-643">Zum Ausführen des Tools muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-643">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a><span data-ttu-id="539e3-644">Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="539e3-644">Creating a new Trusted Application for the SEFAUtil tool</span></span>

1. <span data-ttu-id="539e3-645">Das SEFAUTil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-645">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="539e3-646">Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die Skype for Business Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:</span><span class="sxs-lookup"><span data-stu-id="539e3-646">If needed, adding a pool as a new trusted application pool can be done via the Skype for Business Server Management Shell with the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > <span data-ttu-id="539e3-647">UCMA 3.0 muss auf jedem Computer installiert sein, der zum Ausführen des SEFAUtil-Tools verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-647">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

2. <span data-ttu-id="539e3-648">Eine vertrauenswürdige Anwendung muss in der Topologie für das SEFAUtil-Tool definiert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-648">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="539e3-649">Um SEFAUtil als neue vertrauenswürdige Anwendung zu definieren, verwenden Sie die Skype for Business Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="539e3-649">To define SEFAUtil as a new trusted application, use the Skype for Business Server Management Shell and execute the following cmdlet:</span></span>

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="539e3-650">Bei Bedarf kann ein anderer Port verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-650">A different port can be used if needed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="539e3-651">Pool-FQDN: der FQDN des Servers oder Pools, der als Host für die SEFAUtil-Anwendung verwendet wird (in der Regel ein Skype for Business-Front-End-Server-> oder-Pool).</span><span class="sxs-lookup"><span data-stu-id="539e3-651">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server     > or pool).</span></span>
    > <span data-ttu-id="539e3-652">FQDN des Pool Registrierungsstelle: der FQDN des Skype for Business Front-End-Servers oder Pools, der diesem Anwendungspool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-652">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="539e3-653">Pool Website: die Website-ID der Website, auf der dieser Pool verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-653">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

3. <span data-ttu-id="539e3-654">Die Topologie-Änderungen müssen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="539e3-654">The topology changes need to be enabled.</span></span> <span data-ttu-id="539e3-655">Das Aktivieren der Topologie-Änderungen kann über die Skype for Business Server Management Shell durch Ausführen des folgenden Cmdlets erfolgen:</span><span class="sxs-lookup"><span data-stu-id="539e3-655">Enabling the topology changes can be done via the Skype for Business Server Management Shell by executing the following cmdlet:</span></span>

   ```powershell
   Enable-CsToplogy
   ```

4. <span data-ttu-id="539e3-656">Installieren Sie bei Bedarf die Skype for Business Server 2015 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).</span><span class="sxs-lookup"><span data-stu-id="539e3-656">If needed, install the Skype for Business Server 2015 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5. <span data-ttu-id="539e3-657">Stellen Sie sicher, dass die SEFAUtil ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-657">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="539e3-658">Führen Sie dazu das Tool über eine Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="539e3-658">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="539e3-659">Das Tool befindet sich standardmäßig in: ". ..\Programme\Microsoft Files\Skype for Business Server 2015 \ reskit".</span><span class="sxs-lookup"><span data-stu-id="539e3-659">By default the tool will be located in: "…\Program Files\Skype for Business Server 2015\Reskit".</span></span> <span data-ttu-id="539e3-660">Verwenden Sie den folgenden Befehl, um die Anrufweiterleitungseinstellungen eines Benutzers anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="539e3-660">To display the call forwarding settings of a user, use the following command:</span></span>

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    <span data-ttu-id="539e3-661">Die Einstellungen für die Anrufweiterleitung des Benutzers sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-661">The call forwarding settings of the user should be displayed.</span></span>

#### <a name="group-call-pickup"></a><span data-ttu-id="539e3-662">Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="539e3-662">Group Call Pickup</span></span>

<span data-ttu-id="539e3-663">Für die gruppenanrufannahme ist eine zusätzliche Konfiguration in Skype for Business Server 2015 erforderlich, damit die Funktion vollständig aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="539e3-663">Group Call Pickup requires additional configuration in Skype for Business Server 2015 for the capability to be fully enabled.</span></span> <span data-ttu-id="539e3-664">Vor dem Zuweisen von Pickup-Gruppen zu Benutzern finden Sie in der Group Call Pickup-Produktdokumentation die Planungs-und Bereitstellungsschritte dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="539e3-664">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-665">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-665">Examples</span></span>

#### <a name="display-current-call-handling-settings"></a><span data-ttu-id="539e3-666">Anzeigen der aktuellen Einstellungen für die Anrufverarbeitung</span><span class="sxs-lookup"><span data-stu-id="539e3-666">Display Current Call Handling Settings</span></span>

<span data-ttu-id="539e3-667">Mit dem folgenden Befehl wird die Anrufbehandlung für den Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="539e3-667">The following command displays the call handling for the user.</span></span>  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> <span data-ttu-id="539e3-668">In diesem Beispiel wird **die Option/** Tausch verwendet, um die Skype for Business Server anzugeben, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="539e3-668">This example uses the **/server** switch to specify the Skype for Business Server to connect to.</span></span>

 <span data-ttu-id="539e3-669">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-669">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="539e3-670">Festlegen des Ziels "Anrufweiterleitung/Nein-Antwort"</span><span class="sxs-lookup"><span data-stu-id="539e3-670">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="539e3-671">In diesem Beispiel werden das Ziel für die Anrufweiterleitung/keine Antwort und die Ring Verzögerung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="539e3-671">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="539e3-672">Hier wird die Option// SEFAUtil versucht, die Skype for Business Server 2015 zu AutoErmittlung.</span><span class="sxs-lookup"><span data-stu-id="539e3-672">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Skype for Business Server 2015.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 <span data-ttu-id="539e3-673">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-673">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="539e3-674">Sofortiges Aktivieren der Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="539e3-674">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="539e3-675">In diesem Beispiel wird die Anrufweiterleitung sofort an einen anderen Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-675">This example immediately enables call-forwarding to another user.</span></span>

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 <span data-ttu-id="539e3-676">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-676">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="539e3-677">Sofortiges Deaktivieren der Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="539e3-677">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="539e3-678">In diesem Beispiel wird die Anrufweiterleitung sofort deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-678">This example immediately disables call forwarding.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 <span data-ttu-id="539e3-679">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-679">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="539e3-680">Hinzufügen eines Benutzers als Stellvertreter und Einrichten des gleichzeitigen Klingelns von Stellvertretern</span><span class="sxs-lookup"><span data-stu-id="539e3-680">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="539e3-681">In diesem Beispiel wird ein Benutzer als Stellvertreter hinzugefügt und das gleichzeitige Klingeln von Stellvertretern eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="539e3-681">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 <span data-ttu-id="539e3-682">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-682">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="539e3-683">Ändern der gleichzeitigen Klingel Regel für Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="539e3-683">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="539e3-684">In diesem Beispiel wird die Regel für das gleichzeitige Klingeln, die im vorherigen Beispiel festgelegt wurde, auf die verzögerte Klingel Regel geändert.</span><span class="sxs-lookup"><span data-stu-id="539e3-684">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 <span data-ttu-id="539e3-685">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-685">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a><span data-ttu-id="539e3-686">Entfernen der Stellvertretung</span><span class="sxs-lookup"><span data-stu-id="539e3-686">Remove the Delegate</span></span>

<span data-ttu-id="539e3-687">In diesem Beispiel wird die Stellvertretung entfernt.</span><span class="sxs-lookup"><span data-stu-id="539e3-687">This example removes the delegate.</span></span>

> [!NOTE]
> <span data-ttu-id="539e3-688">Wenn der letzte Stellvertreter entfernt wird, wird das Delegieren von Klingeln automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-688">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 <span data-ttu-id="539e3-689">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-689">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="539e3-690">Hinzufügen einer Stellvertretung und Einrichten der Regel "Anrufweiterleitung an Stellvertretungen"</span><span class="sxs-lookup"><span data-stu-id="539e3-690">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="539e3-691">In diesem Beispiel wird eine Stellvertretung hinzugefügt und die Regel "Anrufweiterleitung an Stellvertretungen" eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="539e3-691">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 <span data-ttu-id="539e3-692">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-692">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="539e3-693">Gleichzeitiges Klingeln aktivieren und Zielrufnummer festlegen</span><span class="sxs-lookup"><span data-stu-id="539e3-693">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="539e3-694">In diesem Beispiel wird das gleichzeitige Klingeln aktiviert und eine Ziel Nummer für das gleichzeitige Klingeln festgelegt.</span><span class="sxs-lookup"><span data-stu-id="539e3-694">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> <span data-ttu-id="539e3-695">Wenn Sie die Ziel Nummer für das gleichzeitige Klingeln eines Benutzers ändern möchten, der bereits das gleichzeitige Klingeln aktiviert hat, halten Sie den Befehl mit dem/enablesimulring-Schalter an, andernfalls wird die Zielrufnummer nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="539e3-695">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>

 <span data-ttu-id="539e3-696">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-696">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a><span data-ttu-id="539e3-697">Gleichzeitiges Klingeln deaktivieren</span><span class="sxs-lookup"><span data-stu-id="539e3-697">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="539e3-698">In diesem Beispiel wird das gleichzeitige Klingeln deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-698">This example disables simultaneous ringing.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 <span data-ttu-id="539e3-699">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-699">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="539e3-700">Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Gruppe "Team Anruf Mitglieder"</span><span class="sxs-lookup"><span data-stu-id="539e3-700">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="539e3-701">In diesem Beispiel wird der Teamanrufgruppe eines Benutzers ein Teammitglied hinzugefügt und das gleichzeitige Klingeln für die Teamanrufgruppe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-701">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="539e3-702">Durch das Hinzufügen eines Mitglieds zur Teamanrufgruppe eines Benutzers wird automatisch das gleichzeitige Klingeln der Einstellungen der Benutzer zu gleich seiner Teamanrufgruppe gewechselt.</span><span class="sxs-lookup"><span data-stu-id="539e3-702">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>

 <span data-ttu-id="539e3-703">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-703">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="539e3-704">Entfernen eines Mitglieds aus der Team anrufgruppe</span><span class="sxs-lookup"><span data-stu-id="539e3-704">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="539e3-705">In diesem Beispiel wird ein Teammitglied der Teamanrufgruppe eines Benutzers entfernt.</span><span class="sxs-lookup"><span data-stu-id="539e3-705">This example removes a team member of the team-call group of a user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> <span data-ttu-id="539e3-706">Wenn das zu entfernende Element das einzige Mitglied der Teamanrufgruppe ist, wird das gleichzeitige Klingeln für die Teamanrufgruppe automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-706">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>

 <span data-ttu-id="539e3-707">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-707">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="539e3-708">Festlegen des verzögerten Rings auf die Team anrufgruppe</span><span class="sxs-lookup"><span data-stu-id="539e3-708">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="539e3-709">In diesem Beispiel wird der verzögerte Ring in die Zeiteinstellung für die Teamanrufgruppe geändert.</span><span class="sxs-lookup"><span data-stu-id="539e3-709">This example changes the delayed ring to the team-call group time setting.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 <span data-ttu-id="539e3-710">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-710">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a><span data-ttu-id="539e3-711">Aktivieren des Team Anrufs</span><span class="sxs-lookup"><span data-stu-id="539e3-711">Enable Team-Call</span></span>

<span data-ttu-id="539e3-712">In diesem Beispiel wird der Team Aufruf für einen bestimmten Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-712">This example enables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> <span data-ttu-id="539e3-713">Wenn die Teamanrufgruppe des Benutzers keine Mitglieder enthält, wird die Teamanruffunktion nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-713">If the team-call group of the user has no members, team-call won't be enabled.</span></span>

 <span data-ttu-id="539e3-714">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-714">**Output**</span></span>

#### <a name="disable-team-call"></a><span data-ttu-id="539e3-715">Team Anruf deaktivieren</span><span class="sxs-lookup"><span data-stu-id="539e3-715">Disable Team-Call</span></span>

<span data-ttu-id="539e3-716">In diesem Beispiel wird der Team Aufruf für einen bestimmten Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-716">This example disables team-call for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 <span data-ttu-id="539e3-717">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-717">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="539e3-718">Aktivieren der gruppenanrufannahme und Zuweisen einer Abhol Gruppe zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="539e3-718">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="539e3-719">In diesem Beispiel wird einem Benutzer eine Abhol Gruppe zugewiesen, und es wird eine gruppenanrufannahme aktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-719">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 <span data-ttu-id="539e3-720">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="539e3-720">**Output**</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a><span data-ttu-id="539e3-721">Deaktivieren der gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="539e3-721">Disable Group Call Pickup</span></span>

<span data-ttu-id="539e3-722">In diesem Beispiel wird die gruppenanrufannahme für einen bestimmten Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="539e3-722">This example disables Group Call Pickup for a given user.</span></span>

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> <span data-ttu-id="539e3-723">Wenn Sie die gruppenanrufannahme für einen Benutzer deaktivieren, wird die dem Benutzer zugewiesene Gruppennummer nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="539e3-723">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="539e3-724">Wenn Sie anschließend die gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Gruppennummer mit dem/enablegrouppickup-Schalter erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="539e3-724">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a><span data-ttu-id="539e3-725">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="539e3-725">SYSPrep.ps1</span></span>
<span data-ttu-id="539e3-726"><a name="SYSPrep"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-726"><a name="SYSPrep"> </a></span></span>

### <a name="description"></a><span data-ttu-id="539e3-727">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-727">Description</span></span>

<span data-ttu-id="539e3-728">SYSPrep. ps1 ist ein Windows PowerShell Skript, mit dem die folgenden Skype for Business Server 2015 erforderlichen Komponenten auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-728">SYSPrep.ps1 is a Windows PowerShell script that will install the following Skype for Business Server 2015 prerequisites on your Windows Server 2008 operating system machine.</span></span>

- <span data-ttu-id="539e3-729">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="539e3-729">Microsoft .Net Framework 4.5</span></span>

- <span data-ttu-id="539e3-730">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="539e3-730">Microsoft SQL Server Express</span></span>

- <span data-ttu-id="539e3-731">Windows PowerShell, Version 3,0</span><span class="sxs-lookup"><span data-stu-id="539e3-731">Windows Powershell version 3.0</span></span>

- <span data-ttu-id="539e3-732">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="539e3-732">Visual C++ 2010 Redistributable</span></span>

- <span data-ttu-id="539e3-733">Internet Informations Server-Updates</span><span class="sxs-lookup"><span data-stu-id="539e3-733">Internet Information Server Updates</span></span>

- <span data-ttu-id="539e3-734">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="539e3-734">Windows Identity Foundation</span></span>

- <span data-ttu-id="539e3-735">Skype for Business Server 2015 Kerndateien</span><span class="sxs-lookup"><span data-stu-id="539e3-735">Skype for Business Server 2015 Core files</span></span>

  <span data-ttu-id="539e3-736">Während der Skriptname dem System Vorbereitungs Tool für Microsoft Windows-Betriebssysteme ähnelt, sind Sie unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="539e3-736">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="539e3-737">Mit diesem Skript werden nur die erforderlichen Voraussetzungen für Skype for Business Server 2015 installiert.</span><span class="sxs-lookup"><span data-stu-id="539e3-737">This script will only install the required prerequisites for Skype for Business Server 2015.</span></span> <span data-ttu-id="539e3-738">Sobald diese Voraussetzungen installiert sind, kann das Windows-SYSPrep-Tool verwendet werden, um ein Abbild des Servers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="539e3-738">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-739">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-739">Requirements</span></span>

<span data-ttu-id="539e3-740">Vor dem Ausführen des Skripts "SYSPrep. ps1" müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (beispielsweise **D:\setup)**.</span><span class="sxs-lookup"><span data-stu-id="539e3-740">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\Setup)**.</span></span> <span data-ttu-id="539e3-741">Dieser Ordner muss auch eine Kopie der Skype for Business Server 2015 Dateien enthalten, insbesondere **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="539e3-741">This folder must also include a copy of the Skype for Business Server 2015 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="539e3-742">Die erforderlichen Dateien können von den folgenden Speicherorten heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="539e3-742">The prerequisite files can be downloaded from the following locations:</span></span>


| <span data-ttu-id="539e3-743">**Voraussetzung**</span><span class="sxs-lookup"><span data-stu-id="539e3-743">**Prerequisite**</span></span>                                | <span data-ttu-id="539e3-744">**Standort**</span><span class="sxs-lookup"><span data-stu-id="539e3-744">**Location**</span></span>                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| <span data-ttu-id="539e3-745">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="539e3-745">Microsoft .Net Framework 4.5</span></span>  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| <span data-ttu-id="539e3-746">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="539e3-746">Microsoft SQL Server Express 2008 R2</span></span>  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| <span data-ttu-id="539e3-747">Windows PowerShell, Version 3,0</span><span class="sxs-lookup"><span data-stu-id="539e3-747">Windows Powershell version 3.0</span></span>  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| <span data-ttu-id="539e3-748">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="539e3-748">Visual C++ 2010 Redistributable</span></span>  <br/>          | <https://www.microsoft.com/download/details.aspx?id=5555>  <br/>  |
| <span data-ttu-id="539e3-749">Internet Informations Server-Updates</span><span class="sxs-lookup"><span data-stu-id="539e3-749">Internet Information Server Updates</span></span>  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| <span data-ttu-id="539e3-750">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="539e3-750">Windows Identity Foundation</span></span>  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| <span data-ttu-id="539e3-751">Skype for Business Server 2015 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="539e3-751">Skype for Business Server 2015 Setup.exe</span></span>  <br/> | <span data-ttu-id="539e3-752">Kopieren von Skype for Business Server 2015 Medien</span><span class="sxs-lookup"><span data-stu-id="539e3-752">Copy from Skype for Business Server 2015 media</span></span>  <br/>                   |

### <a name="parameter"></a><span data-ttu-id="539e3-753">Parameter</span><span class="sxs-lookup"><span data-stu-id="539e3-753">Parameter</span></span>

<span data-ttu-id="539e3-754">Der **-SetupFolder-** Parameter verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.</span><span class="sxs-lookup"><span data-stu-id="539e3-754">The **-SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-755">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-755">Examples</span></span>

<span data-ttu-id="539e3-756">Führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um das Skript "SYSPrep. ps1" auszuführen und die erforderlichen Komponenten für Skype for Business Server 2015 zu installieren:</span><span class="sxs-lookup"><span data-stu-id="539e3-756">To run the SYSPrep.ps1 script and install the Skype for Business Server 2015 prerequisites, run the following command from an elevated command prompt:</span></span>

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="539e3-757">Migration nicht zugewiesener Nummern Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="539e3-757">Unassigned Number Announcements Migration</span></span>
<span data-ttu-id="539e3-758"><a name="UNAM"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-758"><a name="UNAM"> </a></span></span>

<span data-ttu-id="539e3-759">Mit dem Migrationstool für nicht zugewiesene Nummern Ankündigungen kann ein Skype for Business Server 2015 Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung aus einer Quell Skype for Business Server oder einem Pool gewartet wird, in eine Ziel-Skype for Business Server oder-Pool.</span><span class="sxs-lookup"><span data-stu-id="539e3-759">The Unassigned Number Announcements Migration tool enables a Skype for Business Server 2015 administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Skype for Business Server or Pool to a destination Skype for Business Server or Pool.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-760">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-760">Description</span></span>

<span data-ttu-id="539e3-761">Das Migrationstool für nicht zugewiesene Nummern Ankündigungen ist ein Windows PowerShells Skript, mit dem die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung eines Quellservers oder Pools aus gewartet wird, auf einen anderen Server oder Pool verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-761">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="539e3-762">Bei der Ausführung des Migrationsskripts für unassigned number Announcements werden die folgenden Vorgänge ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="539e3-762">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1. <span data-ttu-id="539e3-763">Verschiebt alle Audiodateien, die von den Ankündigungen nicht zugewiesener Nummern der in dem Quellserver oder Pool gehosteten Ankündigungs Anwendung verwendet werden, in den Dateispeicher des Zielservers oder-Pools.</span><span class="sxs-lookup"><span data-stu-id="539e3-763">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="539e3-764">Die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="539e3-764">The audio files are removed from the source pool once they're copied to the destination pool.</span></span>

2. <span data-ttu-id="539e3-765">Verschiebt alle Ankündigungen für nicht zugewiesene Nummern, die für die im Quellserver oder Pool gehostete Ankündigungs Anwendung konfiguriert sind, auf den Zielserver oder-Pool.</span><span class="sxs-lookup"><span data-stu-id="539e3-765">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3. <span data-ttu-id="539e3-766">Weisen Sie dem Zielserver oder-Pool alle nicht zugewiesenen Nummernbereiche, die von der auf dem Quellserver oder Pool gehosteten Ankündigungs Anwendung gewartet werden, neu zu.</span><span class="sxs-lookup"><span data-stu-id="539e3-766">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="539e3-767">Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der auf dem Quellserver oder Pool gehosteten Ankündigungs Anwendung gewartet wurden, jetzt mit der gleichen Konfiguration vom Zielserver oder-Pool aus gewartet.</span><span class="sxs-lookup"><span data-stu-id="539e3-767">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-768">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-768">Output</span></span>

<span data-ttu-id="539e3-769">Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster der Skype for Business Server-Verwaltungsshell an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-769">The **Move-CsAnnouncementConfiguration** script indicates in the Skype for Business Server Management Shell window from where it's executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="539e3-770">Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die nicht zugewiesenen Nummernbereiche, die erfolgreich in das Ziel verschoben wurden, in einem operativen Formular im Ziel und die restlichen nicht zugewiesenen Nummernbereiche, die migriert werden sollen, werden in die Quelle als auch in einem operativen Formular.</span><span class="sxs-lookup"><span data-stu-id="539e3-770">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="539e3-771">Um den Rest der Konfiguration vollständig zu migrieren, führen Sie das Skript nach dem Beheben des Fehlers erneut aus.</span><span class="sxs-lookup"><span data-stu-id="539e3-771">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

### <a name="purpose"></a><span data-ttu-id="539e3-772">Zweck</span><span class="sxs-lookup"><span data-stu-id="539e3-772">Purpose</span></span>

<span data-ttu-id="539e3-773">Das Migrationsskript "nicht zugewiesene Nummern Ankündigungen" kann in den folgenden drei Szenarien verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="539e3-773">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

- <span data-ttu-id="539e3-774">**Migrieren von Konfigurationseinstellungen zu einer neuen Version von Skype for Business Server:** Contoso wird gerade zu Skype for Business Server 2015 migriert, und im Rahmen des Migrationsprozesses möchte der Skype for Business Server Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2013-Bereitstellung in die neue Skype for Business Server 2015-Bereitstellung verschieben.</span><span class="sxs-lookup"><span data-stu-id="539e3-774">**Migrating configuration settings to a new version of Skype for Business Server:** Contoso is in the process of migrating to Skype for Business Server 2015 and as part of the migration process the Skype for Business Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2013 deployment to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="539e3-775">Zum Migrieren der Konfigurationseinstellungen verwendet der Skype for Business Server Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="539e3-775">To move the configuration settings, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

- <span data-ttu-id="539e3-776">**Rollback einer Bereitstellung von Skype for Business Server 2015 auf lync Server 2013:** Aufgrund unerwarteter Faktoren muss Contoso die Migration in die neue Skype for Business Server 2015-Bereitstellung rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-776">**Rolling back a deployment from Skype for Business Server 2015 to Lync Server 2013:** Due unexpected factors, Contoso has to roll back the migration to the new Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="539e3-777">Zum Minimieren von Unterbrechungen des Diensts verwendet der Skype for Business Server Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen, um die Konfiguration von der Skype for Business Server 2015-Bereitstellung auf die lync Server 2013-Bereitstellung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="539e3-777">To minimize disruptions to the service, the Skype for Business Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Skype for Business Server 2015 deployment to the Lync Server 2013 deployment.</span></span>

- <span data-ttu-id="539e3-778">**Verschieben von Daten zwischen Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neuere Server zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="539e3-778">**Moving data between deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="539e3-779">Ihre Strategie besteht darin, einen neuen Skype for Business Server 2015 Pool bereitzustellen, alle Daten aus dem alten in den neuen Pool zu verlagern und dann den alten Pool zu veraltern.</span><span class="sxs-lookup"><span data-stu-id="539e3-779">Their strategy is to deploy a new Skype for Business Server 2015 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="539e3-780">Nachdem der neue Pool bereitgestellt wurde, wird das Migrationstool für unassigned number Announcements verwendet, um die Konfiguration aus dem alten Pool in die neue zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="539e3-780">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

#### <a name="requirements"></a><span data-ttu-id="539e3-781">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-781">Requirements</span></span>

<span data-ttu-id="539e3-782">Die folgenden Hauptanforderungen müssen erfüllt sein, um das Tool erfolgreich auszuführen:</span><span class="sxs-lookup"><span data-stu-id="539e3-782">The following are the main requirements needed to successfully run the tool:</span></span>

1. <span data-ttu-id="539e3-783">Das Skript muss von einem Computer aus ausgeführt werden, auf dem Skype for Business Server Management Shell installiert ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-783">The script must be run from a computer that has Skype for Business Server Management Shell installed.</span></span>

2. <span data-ttu-id="539e3-784">Die Ankündigungs Anwendung muss erfolgreich in den Quell-und Ziel Skype for Business-Servern oder-Pools bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-784">The announcement application has to be successfully deployed in the source and destination Skype for Business Servers or Pools.</span></span>

#### <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="539e3-785">CsAnnouncementConfiguration-Skript</span><span class="sxs-lookup"><span data-stu-id="539e3-785">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="539e3-786">Das CsAnnouncementConfiguration-Skript erfordert die beiden Parameter, die in der folgenden Tabelle beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-786">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

![CsAnnouncementConfiguration-Parameter.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a><span data-ttu-id="539e3-788">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-788">Examples</span></span>

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a><span data-ttu-id="539e3-789">Verschieben der Konfiguration nicht zugewiesener Nummern Ankündigungen von einem lync Server 2013 Pool in einen Skype for Business Server 2015 Pool</span><span class="sxs-lookup"><span data-stu-id="539e3-789">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Skype for Business Server 2015 Pool</span></span>

<span data-ttu-id="539e3-790">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2013) in den Ziel Pool (Skype for Business Server 2015) verschoben.</span><span class="sxs-lookup"><span data-stu-id="539e3-790">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Skype for Business Server 2015).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="539e3-791">Verschieben der Konfiguration nicht zugewiesener Nummern Ankündigungen von einem Skype for Business Server 2015 Pool in einen lync Server 2013 Pool</span><span class="sxs-lookup"><span data-stu-id="539e3-791">Moving the Unassigned Number Announcements Configuration from a Skype for Business Server 2015 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="539e3-792">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (Skype for Business Server 2015) in den Ziel Pool (lync Server 2013) verschoben.</span><span class="sxs-lookup"><span data-stu-id="539e3-792">This example moves the unassigned number announcements from the source pool (Skype for Business Server 2015) to the destination pool (Lync Server 2013).</span></span>

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a><span data-ttu-id="539e3-793">Webconf-Daten</span><span class="sxs-lookup"><span data-stu-id="539e3-793">Web Conf Data</span></span>
<span data-ttu-id="539e3-794"><a name="WebConfData"> </a></span><span class="sxs-lookup"><span data-stu-id="539e3-794"><a name="WebConfData"> </a></span></span>

<span data-ttu-id="539e3-795">Mit dem Tool "webconf Data" kann ein Administrator von Skype for Business Server 2015 Kommunikationssoftware mehr Kontrolle über die Daten haben, die den Webkonferenzen eines Organisators zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-795">The Web Conf Data Tool allows an administrator of Skype for Business Server 2015 communications software to have more control over the data associated with an organizer's Web conferences.</span></span> <span data-ttu-id="539e3-796">Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers basierend auf einem Zeitstempel Kriterium zu löschen.</span><span class="sxs-lookup"><span data-stu-id="539e3-796">Scenarios include the ability to delete a specific user's meeting data based on a time stamp criteria.</span></span>

### <a name="description"></a><span data-ttu-id="539e3-797">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="539e3-797">Description</span></span>

<span data-ttu-id="539e3-798">Mit diesem Tool kann der Administrator die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="539e3-798">This tool allows the administrator to perform the following operations:</span></span>

1. <span data-ttu-id="539e3-799">Hier finden Sie alle mit einem einzelnen Benutzer verknüpften Webkonferenz Daten.</span><span class="sxs-lookup"><span data-stu-id="539e3-799">Find all Web conferencing data associated with a single user.</span></span>

2. <span data-ttu-id="539e3-800">Löschen Sie alle Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="539e3-800">Delete all Web conferencing data associated with a single user.</span></span>

3. <span data-ttu-id="539e3-801">Löschen Sie alle Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, der älter als ein bestimmtes Datum ist.</span><span class="sxs-lookup"><span data-stu-id="539e3-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4. <span data-ttu-id="539e3-802">Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

    > [!NOTE]
    > <span data-ttu-id="539e3-803">Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="539e3-804">Diese Funktionalität ist nun in diesem Tool für den **MoveConferenceData** -Parameter veraltet.</span><span class="sxs-lookup"><span data-stu-id="539e3-804">That functionality is now deprecated from this tool in favor of the **MoveConferenceData** parameter.</span></span> <span data-ttu-id="539e3-805">Ausführliche Informationen zu diesem Parameter finden Sie unter dem Cmdlet " [Verschiebe-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="539e3-805">For details about this parameter, see the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="539e3-806">Das Tool löscht Besprechungsdaten nur für nicht aktive Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="539e3-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="539e3-807">Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="539e3-808">Dieses Tool muss von einem Computer aus ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="539e3-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="539e3-809">Der Benutzer, dessen Besprechungsinhalts Daten von diesem Tool verwaltet werden, muss sich in demselben Benutzerpool befinden.</span><span class="sxs-lookup"><span data-stu-id="539e3-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

### <a name="output"></a><span data-ttu-id="539e3-810">Output</span><span class="sxs-lookup"><span data-stu-id="539e3-810">Output</span></span>

<span data-ttu-id="539e3-811">Dieses Tool gibt die Ergebnisse der einzelnen Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="539e3-811">This tool outputs the results of each of the operations:</span></span>

- <span data-ttu-id="539e3-812">Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdaten Ordner aus, die diesen Benutzer als Organisator haben.</span><span class="sxs-lookup"><span data-stu-id="539e3-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

- <span data-ttu-id="539e3-813">Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdaten Ordner aus, deren Daten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

### <a name="requirements"></a><span data-ttu-id="539e3-814">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="539e3-814">Requirements</span></span>

<span data-ttu-id="539e3-815">Das Tool muss in demselben Pool ausgeführt werden, in dem der Organisator derzeit verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="539e3-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="539e3-816">Das Tool muss mit Administratorrechten mit Zugriff auf die Inhalts Dateispeicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

### <a name="examples"></a><span data-ttu-id="539e3-817">Beispiele</span><span class="sxs-lookup"><span data-stu-id="539e3-817">Examples</span></span>

<span data-ttu-id="539e3-818">In der folgenden Tabelle werden die Parameter beschrieben, von denen einige in den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="539e3-818">The following table describes the parameters, some of which are used in the examples.</span></span>

![Parameter des webconf-Datentools.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

<span data-ttu-id="539e3-820">Das obige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde.</span><span class="sxs-lookup"><span data-stu-id="539e3-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="539e3-821">Bei der Ausgabe eines solchen Befehls handelt es sich um eine Liste aller Besprechungsinhalts Ordner, die von diesem Tool betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="539e3-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

<span data-ttu-id="539e3-822">Das vorangehende ist ein Beispiel für einen DELETE-Befehl.</span><span class="sxs-lookup"><span data-stu-id="539e3-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="539e3-823">Mit dem Befehl Delete werden alle inaktiven Besprechungs Ordner von diesem Benutzer entfernt.</span><span class="sxs-lookup"><span data-stu-id="539e3-823">The delete command will remove all inactive meeting folders from this user.</span></span>

### <a name="summary"></a><span data-ttu-id="539e3-824">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="539e3-824">Summary</span></span>

<span data-ttu-id="539e3-825">Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenz Besprechungsdaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="539e3-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>



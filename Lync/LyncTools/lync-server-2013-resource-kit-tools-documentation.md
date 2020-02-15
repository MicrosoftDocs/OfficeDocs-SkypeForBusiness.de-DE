---
title: Dokumentation zu lync Server 2013 Resource Kit-Tools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1cb9d5f72d03d9c4899c16e35968109819b09d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="cd9fa-102">Dokumentation zu lync Server 2013 Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="cd9fa-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd9fa-103">_**Letztes Änderungsstand des Themas:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="cd9fa-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="cd9fa-104">In diesem Thema werden die Tools beschrieben, die Teil des lync Server 2013 Resource Kits sind, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Die lync Server 2013, Resource Kit-Tools helfen Ihnen, Routineaufgaben für IT-Administratoren einfacher zu machen, die lync Server 2013 bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="cd9fa-105">Beispielsweise kann das Tool **webconf-Daten** verwendet werden, um Daten, die von Benutzern während einer Onlinebesprechung hochgeladen werden, ganz einfach zu steuern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="cd9fa-106">Das **SEFAUtil** -Tool kann zum Einrichten von Delegate-Anrufweiterleitung und-Beantwortung für Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="cd9fa-107">Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um lync Server 2013 effektiver zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="cd9fa-108">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="cd9fa-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="cd9fa-109">Zum Installieren der lync Server 2013 Resource Kit-Tools laden Sie **OCSReskit. msi**herunter.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="cd9fa-110">Sie können den Resource Kit Tools [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)-Installer aus dem Download Center herunterladen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="cd9fa-111">Führen Sie **OCSResKit. msi** aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="cd9fa-112">Die MSI-Datei installiert alle Tools im folgenden Pfad: **% Programmdateien%\\\\Microsoft lync Server 2013 reskit**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="cd9fa-113">Tools mit eigenständigen ausführbaren Dateien befinden sich in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="cd9fa-114">Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="cd9fa-115">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-115">Supported Environments</span></span>

<span data-ttu-id="cd9fa-116">Für eine optimale Leistung sollten die lync Server 2013 Resource Kit-Tools in derselben Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="cd9fa-117">Resource Kit-Tools (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="cd9fa-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="cd9fa-118">In der folgenden Liste werden die Tools beschrieben, die im lync Server 2013 Resource Kit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="cd9fa-119">Eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung, wird im folgenden Abschnitt behandelt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="cd9fa-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="cd9fa-120">ABSConfig</span></span>

  - <span data-ttu-id="cd9fa-121">Bandbreitenrichtlinie-Dienst Monitor</span><span class="sxs-lookup"><span data-stu-id="cd9fa-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="cd9fa-122">Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="cd9fa-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="cd9fa-123">Parkometer aufrufen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-123">Call Parkometer</span></span>

  - <span data-ttu-id="cd9fa-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="cd9fa-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="cd9fa-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="cd9fa-125">DBAnalyze</span></span>

  - <span data-ttu-id="cd9fa-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="cd9fa-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="cd9fa-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="cd9fa-127">LCSSync</span></span>

  - <span data-ttu-id="cd9fa-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="cd9fa-128">LookupUserConsole</span></span>

  - <span data-ttu-id="cd9fa-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="cd9fa-129">MsTurnPing</span></span>

  - <span data-ttu-id="cd9fa-130">Netzwerk Konfigurationsanzeige</span><span class="sxs-lookup"><span data-stu-id="cd9fa-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="cd9fa-131">Reaktionsgruppen-Agent Live</span><span class="sxs-lookup"><span data-stu-id="cd9fa-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="cd9fa-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="cd9fa-132">SEFAUtil</span></span>

  - <span data-ttu-id="cd9fa-133">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="cd9fa-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="cd9fa-134">Migration nicht zugewiesener Nummern Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="cd9fa-135">Webconf-Daten</span><span class="sxs-lookup"><span data-stu-id="cd9fa-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="cd9fa-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="cd9fa-136">ABSConfig</span></span>

<span data-ttu-id="cd9fa-137">Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in lync Server 2013 anpassen können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="cd9fa-138">Mit diesem Tool können lync Server 2013 Administratoren auch die Standardeinstellungen für den Adressbuchdienst wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-139">Description</span></span>

<span data-ttu-id="cd9fa-140">ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienste Attribute konfigurieren können, die sich auf den Adressbuchdienst beziehen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="cd9fa-141">Die primären Szenarien für das Tool lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="cd9fa-142">Damit Administratoren den Attributen für lync Server 2013 Attribute in Active Directory-Domänendienste zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="cd9fa-143">Damit Administratoren das Active Directory-Domänendienste Attribut angeben können, das in die Adressbuchdienst Dateien eingeschlossen oder ausgeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="cd9fa-144">Damit Administratoren Standardeinstellungen für den Adressbuchdienst wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="cd9fa-145">Das ABSConfig-Tool kann mithilfe der Datei ABSConfig. exe gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="cd9fa-146">Das Tool wird auf der Registerkarte **Configure Attributes** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen Active Directory-Domänendienste Attribute zu den Attributfeldern für lync Server 2013 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern eingeschlossen oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="cd9fa-147">Außerdem gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="cd9fa-148">Die Option **Standardeinstellungen wiederherstellen** ermöglicht Administratoren das Wiederherstellen von Einstellungen für den Adressbuchdienst auf Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="cd9fa-149">Änderungen aus lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cd9fa-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="cd9fa-150">In lync Server 2013 ABS-Konfigurationstool können Attribute (Zeilen) durch Deaktivieren des Kontrollkästchens "aktivieren" für das Attribut entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="cd9fa-151">Dies hat dieselbe Auswirkung wie das Löschen der Zeile in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-152">Das Kontrollkästchen aktivieren befindet sich in der rechten Spalte ganz rechts; Sie müssen möglicherweise nach rechts scrollen, um die Spalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-153">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-153">Output</span></span>

<span data-ttu-id="cd9fa-154">In ABSConfig wird die Konfiguration des Adressbuchdiensts in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-155">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-155">Purpose</span></span>

<span data-ttu-id="cd9fa-156">ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen lync Server 2013 Adressbuchdiensts.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="cd9fa-158">Computer</span><span class="sxs-lookup"><span data-stu-id="cd9fa-158">Computer</span></span>

<span data-ttu-id="cd9fa-159">ABSConfig kann nur von einem Computer ausgeführt werden, der der Domäne angehört und auf dem lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="cd9fa-160">Im Fall von lync Server 2013 Enterprise Edition kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="cd9fa-161">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="cd9fa-161">Network</span></span>

<span data-ttu-id="cd9fa-162">Der Computer sollte in der Lage sein, eine Verbindung mit der Front-End-Pool-und Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="cd9fa-163">Software</span><span class="sxs-lookup"><span data-stu-id="cd9fa-163">Software</span></span>

<span data-ttu-id="cd9fa-164">Die folgenden Softwarekomponenten müssen installiert sein, bevor Sie das ABSConfig-Tool ausführen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="cd9fa-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd9fa-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="cd9fa-166">Benutzer</span><span class="sxs-lookup"><span data-stu-id="cd9fa-166">Users</span></span>

<span data-ttu-id="cd9fa-167">Administratoren, die über die erforderlichen Berechtigungen zum Aktualisieren der lync Server 2013-Bereitstellung verfügen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-168">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-168">Examples</span></span>

<span data-ttu-id="cd9fa-169">ABSConfig kann gestartet werden, indem Sie **ABSConfig. exe** an einer Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-169">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt.</span></span> <span data-ttu-id="cd9fa-170">Unten sehen Sie die Benutzeroberfläche des ABSConfig-Tools.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-170">Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="cd9fa-171">![Das Tool ABSConfig. exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Das Tool ABSConfig. exe.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-172">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-172">Summary</span></span>

<span data-ttu-id="cd9fa-173">Mit dem ABSConfig-Tool können Administratoren schnell und einfach Tools verwenden, um lync Server 2013 Adressbuchdienst anzupassen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="cd9fa-174">Bandbreitenrichtlinie-Dienst Monitor</span><span class="sxs-lookup"><span data-stu-id="cd9fa-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="cd9fa-175">Das Tool Bandbreitenrichtlinien-Dienstüberwachung soll Administratoren die Möglichkeit geben, eine Liste der folgenden anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="cd9fa-176">Alle konfigurierten lync Server 2013 Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie</span><span class="sxs-lookup"><span data-stu-id="cd9fa-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="cd9fa-177">Die Verbindungen, die von jedem Dienst für andere Bandbreitenrichtlinien Dienste und für die Edgeserver erstellt werden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="cd9fa-178">Alle Links, die im Netzwerk Konfigurationsdokument konfiguriert sind, sowie die Echtzeitbandbreite, die von den einzelnen Bandbreitenrichtlinien Diensten gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-179">Description</span></span>

<span data-ttu-id="cd9fa-180">Das Tool Bandwidth Policy Service Monitor wird als GUI-basierte Anwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-180">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application.</span></span> <span data-ttu-id="cd9fa-181">Administratoren starten das Tool durch Ausführung von PDPMonUI. exe.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-181">Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="cd9fa-182">Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreitenrichtlinien Dienste in der Topologie zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-182">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology.</span></span> <span data-ttu-id="cd9fa-183">Nachdem die anfängliche Aktualisierung abgeschlossen ist, wird der Bereich links neben dem Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-183">After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="cd9fa-184">Wenn Administratoren einen bestimmten bandbreitenrichtliniendienst auswählen, zeigt der Bereich auf der rechten Seite die Informationen zu diesem bestimmten Dienst an.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-184">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service.</span></span> <span data-ttu-id="cd9fa-185">Dieser Bereich verfügt auch über zwei Hauptregisterkarten, in denen Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-185">That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="cd9fa-186">Registerkarte "Machine Info"</span><span class="sxs-lookup"><span data-stu-id="cd9fa-186">Machine Info Tab</span></span>

<span data-ttu-id="cd9fa-187">Auf der Registerkarte **Computer Informationen** werden die Details des ausgewählten Bandbreitenrichtlinien Diensts sowie die Liste und der Status aller Verbindungen angezeigt, die vom ausgewählten bandbreitenrichtliniendienst für andere Dienste vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="cd9fa-188">Registerkarte "Topologieinformationen"</span><span class="sxs-lookup"><span data-stu-id="cd9fa-188">Topology Info Tab</span></span>

<span data-ttu-id="cd9fa-189">Auf der Registerkarte **Topologieinformationen** wird eine Liste aller Links angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-189">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings.</span></span> <span data-ttu-id="cd9fa-190">Für jeden Link wird die Kapazität der Audio-und Videobandbreite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-190">For each link, the audio and video bandwidth capacity is displayed.</span></span> <span data-ttu-id="cd9fa-191">Darüber hinaus wird die derzeit verwendete Bandbreite sowohl in Kbit/s als auch als Prozentsatz der Kapazität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-191">Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity.</span></span> <span data-ttu-id="cd9fa-192">Das Tool verwendet Farbcodierung, um Links hervorzuheben, deren Auslastung der Kapazität nahe liegt, sodass Administratoren solche Links schnell isolieren können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-192">The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-193">Wenn beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreitenrichtlinien Dienste beim bandbreitenrichtliniendienst Monitor ein Fehler auftritt, werden die Informationen in den Registerkarten <STRONG>Computer Info</STRONG> und <STRONG>Topologieinformationen</STRONG> nicht aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-193">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated.</span></span> <span data-ttu-id="cd9fa-194">Es kann jedoch sein, dass das Tool anfänglich eine Verbindung herstellen kann, aber die Verbindung mit dem Dienst anschließend verloren geht.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-194">However, it is possible that the tool might connect initially but subsequently lose its connection to the service.</span></span> <span data-ttu-id="cd9fa-195">In diesen Fällen werden Administratoren möglicherweise veraltete Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-195">In such cases, administrators might see outdated information.</span></span> <span data-ttu-id="cd9fa-196">Auf jeder Registerkarte gibt es einen <STRONG>letzten aktualisierten</STRONG> Zeitstempel, mit dem Administratoren sehen können, wann die Daten zuletzt für einen bestimmten bandbreitenrichtliniendienst aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-196">There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-197">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-197">Output</span></span>

<span data-ttu-id="cd9fa-198">Es gibt keine Befehlszeilenausgabe; die Programmausgabe ist in der Haupt grafischen Benutzeroberfläche (Graphical User Interface, GUI) enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-199">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-199">Purpose</span></span>

<span data-ttu-id="cd9fa-200">Der Zweck des Bandwidth Policy Service Monitor-Tools besteht darin, Administratoren Einblick in den Status der einzelnen Bandbreitenrichtlinien Dienste zu gewähren, die in der Topologie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-200">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology.</span></span> <span data-ttu-id="cd9fa-201">Darüber hinaus können Administratoren die Echtzeitbandbreite für alle im Netzwerk Konfigurationsdokument definierten Links sehen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-201">In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-202">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-202">Requirements</span></span>

<span data-ttu-id="cd9fa-203">Das Tool für Bandbreitenrichtlinien-Dienstüberwachung muss auf einem Computer ausgeführt werden, der Teil der lync Server Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-204">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-204">Summary</span></span>

<span data-ttu-id="cd9fa-205">Das Tool Bandbreitenrichtlinien-Dienstüberwachung kann eine wertvolle Ressource für Administratoren sein, damit Sie den Status aller Bandbreitenrichtlinien Dienste in der Topologie überprüfen können-und was noch wichtiger ist-Sie können eine Echtzeitbandbreite für die Links erhalten, die in den Netzwerkkonfigurationseinstellungen definiert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="cd9fa-206">Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="cd9fa-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="cd9fa-207">Bandwidth Auslastung Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-207">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="cd9fa-208">Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und die Planung von Bandbreitenkapazitäten zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-208">These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-209">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-209">Description</span></span>

<span data-ttu-id="cd9fa-210">Bandbreiten Auslastungsanalyse wird als GUI-basierte Anwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-210">Bandwidth Utilization Analyzer is implemented as a GUI-based application.</span></span> <span data-ttu-id="cd9fa-211">Dieses Tool generiert Berichte speziell für die audionutzung im gesamten Netzwerk und hilft bei der Kapazitätsplanung.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-211">This tool generates reports specifically for audio utilization across the network and helps with capacity planning.</span></span> <span data-ttu-id="cd9fa-212">Außerdem wird die Bandbreitenkapazität durchlaufen, die verschiedenen Links zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-212">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-213">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-213">Output</span></span>

<span data-ttu-id="cd9fa-214">Bandbreiten Auslastungsanalyse bietet Grafik Al-Plots mit Bandbreitenkapazität und-Nutzung für alle im System konfigurierten WAN-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-215">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-215">Purpose</span></span>

<span data-ttu-id="cd9fa-216">In jeder sprach-und Videobereitstellung ist es wichtig, den Trend der Bandbreitenauslastung des Mediendaten Verkehrs im gesamten Unternehmensnetzwerk zu überwachen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-216">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network.</span></span> <span data-ttu-id="cd9fa-217">Das Tool Bandbreiten Auslastungsanalyse ermöglicht es einem Administrator, genau dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-217">The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that.</span></span> <span data-ttu-id="cd9fa-218">Dieses Tool führt folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-218">This tool does the following:</span></span>

  - <span data-ttu-id="cd9fa-219">Generiert spezifische Berichte für die audionutzung im gesamten Netzwerk</span><span class="sxs-lookup"><span data-stu-id="cd9fa-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="cd9fa-220">Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Links zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="cd9fa-221">Bandbreiten Auslastungsanalyse kann grafische Plots von Bandbreitenkapazität und Auslastungsberichten generieren. Dabei handelt es sich um folgende:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="cd9fa-222">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="cd9fa-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="cd9fa-223">Gefiltert nach ausgewählten WAN-Verbindungen, die ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="cd9fa-224">Gefiltert nach WAN-Verbindungen, die die Link Kapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="cd9fa-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="cd9fa-225">Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite unter Verwenden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="cd9fa-226">Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (Bandbreitenauslastung, die größer ist als 90% der Bandbreitenkapazität der WAN-Verbindung)</span><span class="sxs-lookup"><span data-stu-id="cd9fa-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="cd9fa-227">Gefiltert nach WAN-Linktyp – Netzwerkstandort Verknüpfungen, interregionale Links und Links innerhalb eines Standorts</span><span class="sxs-lookup"><span data-stu-id="cd9fa-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="cd9fa-228">Gefiltert nach netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="cd9fa-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="cd9fa-229">Applications</span><span class="sxs-lookup"><span data-stu-id="cd9fa-229">Applications</span></span>

<span data-ttu-id="cd9fa-230">Bandbreiten Auslastungsanalyse verfügt über die beiden folgenden Anwendungen (Tools):</span><span class="sxs-lookup"><span data-stu-id="cd9fa-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="cd9fa-231">**"Wanlinklogcollector. exe**   mit diesem Tool können die Benutzer die erforderlichen Informationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="cd9fa-232">**"Bandwidthutilizationanalyzer. xlsm**  ein Microsoft Excel-Tabellenkalkulationssoftware Bericht wird automatisch von" wanlinklogcollector. exe gestartet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="cd9fa-233">Diese Anwendung ermöglicht dem Benutzer das Anwenden von Filtern auf den Bericht, wie weiter unten in diesem Artikel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="cd9fa-234">Phasen der Verwendung des Analyseprogramms für Bandbreitenauslastung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="cd9fa-235">Es gibt zwei Phasen bei der Verwendung des Bandbreiten Auslastungsanalyse Programms:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="cd9fa-236">Sammeln von Protokollen, die mithilfe von "wanlinklogcollector. exe ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="cd9fa-237">Anpassen von Berichten, die mithilfe von "bandwidthutilizationanalyzer. xlsm ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cd9fa-238">Es wird dringend empfohlen, dass "bandwidthutilizationanalyzer. xlsm nicht von Endbenutzern manuell gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="cd9fa-239">Starten der Bandbreiten Auslastungsanalyse</span><span class="sxs-lookup"><span data-stu-id="cd9fa-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="cd9fa-240">Starten Sie "wanlinklogcollector. exe an der Eingabeaufforderung oder mithilfe von Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="cd9fa-241">**Verwenden von "wanlinklogcollector. exe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="cd9fa-242">Es gibt drei Schritte zur Verwendung von "wanlinklogcollector. exe:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="cd9fa-243">**Protokollieren der Zeitachse**   geben Sie die Zeitachse an, für die der Bericht generiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="cd9fa-244">**Angeben der Dateiverzeichnisse**   zur Bereitstellung von Dateispeicherort Informationen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="cd9fa-245">**Erfassen der Protokolle und Starten der Berichtsanzeige**  führen Sie den Befehl aus, um den Bericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="cd9fa-246">Schritt 1 – Protokollieren der Zeitachse</span><span class="sxs-lookup"><span data-stu-id="cd9fa-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="cd9fa-247">Durch die Protokollierung der Zeitachse kann der Benutzer des Tools Folgendes angeben: wie in der Abbildung unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="cd9fa-248">**Start Datum** Dies ist der Anfangstermin des Zeitplans, für den der Bericht generiert werden soll. Beispiel: August 1, 2010.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="cd9fa-249">**Enddatum** Dies ist das Enddatum des Zeitplans, für den der Bericht generiert werden soll. Beispiel: 30. September 2010.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="cd9fa-250">![Start-und Enddatum in der Bandbreitenauslastung A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start-und Enddatum in der Bandbreitenauslastung A")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="cd9fa-251">Schritt 2 – angeben der Dateiverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="cd9fa-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="cd9fa-252">Die folgenden Dateiverzeichnisse können vom Benutzer wie dargestellt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="cd9fa-253">**Speicherort der Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="cd9fa-254">Dies ist in der \<Regel in\>\\\<Fileserver Choice\>\\von\\FE AppServerFiles PDP.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="cd9fa-255">**Speicherplatz für temporäre Dateien** Der temporäre Dateispeicherort, an dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="cd9fa-256">![Dateiverzeichnisse in der Bandbreitenauslastung Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Dateiverzeichnisse in der Bandbreitenauslastung Anal")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-257">Stellen Sie sicher, dass der Benutzer des Tools über einen ausreichenden Dateizugriff auf die Serverprotokolle und den temporären Dateispeicherordner verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="cd9fa-258">Schritt 3: Erfassen der Protokolle und Starten der Berichtanzeige</span><span class="sxs-lookup"><span data-stu-id="cd9fa-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="cd9fa-259">Um die Protokolle zu sammeln und die Berichtsanzeige zu starten, klicken Sie wie unten gezeigt auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="cd9fa-259">To collect the logs and start the report viewer, click **Execute** as shown below.</span></span> <span data-ttu-id="cd9fa-260">In diesem Schritt werden die erforderlichen Daten erfasst.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-260">This step collects the required data.</span></span>

<span data-ttu-id="cd9fa-261">![Sammeln von Daten in der Bandbreitenauslastung Anal](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Sammeln von Daten in der Bandbreitenauslastung Anal")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="cd9fa-262">Wenn die Eingabeüberprüfung erfolgreich ist, wird die unten gezeigte Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="cd9fa-263">![Protokolliert erfasste Benachrichtigung in der Bandbreite utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Protokolliert erfasste Benachrichtigung in der Bandbreite utili")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="cd9fa-264">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-264">Click **OK**.</span></span> <span data-ttu-id="cd9fa-265">"Bandwidthutilizationanalyzer. xlsm wird automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-265">BandwidthUtilizationAnalyzer.xlsm is automatically started.</span></span> <span data-ttu-id="cd9fa-266">Befolgen Sie die Anweisungen im Meldungsfeld.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-266">Follow the instructions in the message box.</span></span> <span data-ttu-id="cd9fa-267">Ausführliche Informationen finden Sie unter **using "bandwidthutilizationanalyzer. xlsm** im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-267">For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="cd9fa-268">**Verwenden von "bandwidthutilizationanalyzer. xlsm**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="cd9fa-269">Wenn "bandwidthutilizationanalyzer. xlsm automatisch gestartet wird, klicken Sie wie unten gezeigt auf **Aktualisieren** .</span><span class="sxs-lookup"><span data-stu-id="cd9fa-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="cd9fa-270">!["Bandwidthutilizationanalyzer. xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg ""Bandwidthutilizationanalyzer. xlsm")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="cd9fa-271">Wenn ein Datei Ordner geöffnet wird, wählen Sie konsolidiert. CSV aus dem Speicherort aus, der im Meldungsfeld angegeben ist, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="cd9fa-272">Außerdem wird der Speicherort als **C:\\Temp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="cd9fa-273">![Öffnen eines Ordners in "bandwidthutilizationanalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Öffnen eines Ordners in "bandwidthutilizationanalyzer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="cd9fa-274">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-274">Click **Import**.</span></span>

4.  <span data-ttu-id="cd9fa-275">Die grafische Darstellung wird automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-275">The graphical plot is automatically generated.</span></span> <span data-ttu-id="cd9fa-276">Sie ist verfügbar, wenn der Zeiger für die Hintergrundarbeit ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-276">It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="cd9fa-277">![Anwenden von Filtern in der Berichtsansicht.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="cd9fa-278">Anwenden von Filtern auf die Berichtsansicht</span><span class="sxs-lookup"><span data-stu-id="cd9fa-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="cd9fa-279">Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden wie folgt beschrieben:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="cd9fa-280">![Anwenden von Filtern in der Berichtsansicht.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="cd9fa-281">**Name** Nach WAN-Links Filtern (der Filter befindet sich auf der rechten Seite des Diagramms). Das Präfix kennzeichnet die folgenden Verknüpfungstypen; Siehe vertikales Feld (blau):</span><span class="sxs-lookup"><span data-stu-id="cd9fa-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="cd9fa-282">**S-Website** Die WAN-Verbindung von einem Netzwerkstandort zu einer netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="cd9fa-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="cd9fa-283">**Ist Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="cd9fa-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="cd9fa-284">**R Inter-Region** Die WAN-Verbindung zwischen zwei netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="cd9fa-285">**Überschreitungs Grenzwert** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mehr als die Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="cd9fa-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="cd9fa-286">**Kritische Ebenen** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung 90% oder mehr als die Bandbreitenkapazität erreicht hat</span><span class="sxs-lookup"><span data-stu-id="cd9fa-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="cd9fa-287">Nicht **ausgelastet** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25% der Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="cd9fa-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="cd9fa-288">**Verknüpfungstyp** Filtern Sie nach den folgenden WAN-Verbindungstypen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="cd9fa-289">Typ des **Netzwerkstandorts**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-289">**Network site** type</span></span>
    
      - <span data-ttu-id="cd9fa-290">**Standortübergreifender** Typ</span><span class="sxs-lookup"><span data-stu-id="cd9fa-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="cd9fa-291">**Zwischen Regionen-Linktyp**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="cd9fa-292">**Region** Nach netzwerkregion Filtern</span><span class="sxs-lookup"><span data-stu-id="cd9fa-292">**Region** Filter by network region</span></span>

<span data-ttu-id="cd9fa-293">Die folgenden Abbildungen zeigen die zuvor beschriebenen Filter.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="cd9fa-294">Nach **Name**filtern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-294">Filter by **Name**.</span></span> <span data-ttu-id="cd9fa-295">Wählen Sie die Liste der Links aus, die im Diagramm angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-295">Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="cd9fa-296">![Filtern nach Namen in "bandwidthutilizationanalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtern nach Namen in "bandwidthutilizationanalyzer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="cd9fa-297">Filtern nach **überschreitungs Grenzwert**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="cd9fa-298">Wählen Sie **true** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="cd9fa-299">![Filterung nach Überschreitung des Grenzwerts.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filterung nach Überschreitung des Grenzwerts.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="cd9fa-300">Nach **kritischen Ebenen**filtern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="cd9fa-301">Wählen Sie **true** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="cd9fa-302">![Filtern nach kritischen Ebenen.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtern nach kritischen Ebenen.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="cd9fa-303">Filtern nach **unter verwendet**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="cd9fa-304">Wählen Sie **true** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="cd9fa-305">![Filterung nach unter verwendet.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filterung nach unter verwendet.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="cd9fa-306">Nach **Linktyp**filtern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-306">Filter by **Link Type**.</span></span> <span data-ttu-id="cd9fa-307">Wählen Sie die Typen aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="cd9fa-308">![Filterung nach Linktyp.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filterung nach Linktyp.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="cd9fa-309">Filtern nach **Region**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-309">Filter by **Region**.</span></span> <span data-ttu-id="cd9fa-310">Wählen Sie eine Liste der Regionen aus, deren Verknüpfungen angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="cd9fa-311">![Filtern nach Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtern nach Region.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-312">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-312">Requirements</span></span>

  - <span data-ttu-id="cd9fa-313">Die Microsoft .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="cd9fa-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="cd9fa-314">Microsoft Excel 2010 oder Excel 2007</span><span class="sxs-lookup"><span data-stu-id="cd9fa-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-315">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-315">Summary</span></span>

<span data-ttu-id="cd9fa-316">Bandbreiten Auslastungsanalyse wird verwendet, um die Nutzung der Audiobandbreite für UC-Datenverkehr über das Netzwerk darzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-316">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network.</span></span> <span data-ttu-id="cd9fa-317">Dieses Tool kann verwendet werden, um die Nutzung der Videobandbreite auch im Netzwerk zu melden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-317">This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="cd9fa-318">Parkometer aufrufen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-318">Call Parkometer</span></span>

<span data-ttu-id="cd9fa-319">Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Orbit-Datenbank für das Parken von Anrufen bietet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-320">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-320">Description</span></span>

<span data-ttu-id="cd9fa-321">Call Parkometer ist ein Tool zum Nachverfolgen von zurzeit geparkten anrufen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="cd9fa-322">Außerdem werden Statistiken zu Orbits und zur Verwendung durch den Anruf Park Server (CPS) gesammelt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="cd9fa-323">Dieses Befehlszeilentool bietet sowohl Lese-als auch Schreibzugriff auf die CPS-Umlaufbahn SQL Server Datenbank von einem lokalen oder Remote verbundenen Computer.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="cd9fa-324">Alle Optionen schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-324">All options are mutually exclusive.</span></span> <span data-ttu-id="cd9fa-325">Die Befehlszeilensyntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-325">Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="cd9fa-326">**– o** -Parameter – listet alle Umlaufbahn Bereiche auf, die für diesen Pool konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="cd9fa-327">**– n** -Parameter – listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-327">**–n** parameter—lists all currently used orbits in this pool.</span></span> <span data-ttu-id="cd9fa-328">Die angezeigten Informationen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-328">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="cd9fa-329">SIP-URI (Uniform Resource Identifier) der parkee und Parker.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="cd9fa-330">Hostname des CPS, in dem der Anruf geparkt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="cd9fa-331">Zeitstempel des Zeitraums, in dem der Anruf geparkt wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="cd9fa-332">**– f** -Parameter – listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="cd9fa-333">\*\*– r \<n\> \*\* Parameter – listet die \<n\> zuletzt geparkten Anrufe auf.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="cd9fa-334">Die angezeigten Informationen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="cd9fa-335">SIP-URI des geparkten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="cd9fa-336">Parker-SIP-URI.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="cd9fa-337">Hostname des CPS, in dem der Anruf geparkt wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="cd9fa-338">Zeitstempel für den Zeitpunkt, zu dem der Anruf abgerufen oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="cd9fa-339">\*\*-t\<n\> \*\* Parameter-testet das Reservieren einer Umlaufbahn in der Datenbank, um die Zufälligkeit der zugewiesenen Umlaufbahn Nummern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-340">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-340">Output</span></span>

<span data-ttu-id="cd9fa-341">Abhängig von den Eingabeparametern, die an einer Eingabeaufforderung angegeben werden, zeigt Call Parkometer die folgende Ausgabe an:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="cd9fa-342">Alle Umlaufbahn Bereiche, die für diesen Pool konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="cd9fa-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="cd9fa-343">Zurzeit geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-343">Currently parked calls</span></span>

  - <span data-ttu-id="cd9fa-344">Anzahl freier (verfügbarer) Umlaufbahnen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="cd9fa-345">Zuletzt geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-345">Recently parked calls</span></span>

  - <span data-ttu-id="cd9fa-346">Reservierte Umlaufbahnen zum Testen von einheitlichen und zufälligen Umlaufbahn Werten</span><span class="sxs-lookup"><span data-stu-id="cd9fa-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-347">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-347">Purpose</span></span>

<span data-ttu-id="cd9fa-348">Der Zweck des CPS-Tools besteht darin, den Befehlszeilenzugriff auf die CPS-Datenbank bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-348">The purpose of the CPS tool is to provide command-line access to the CPS database.</span></span> <span data-ttu-id="cd9fa-349">Der Administrator kann die CPS-Verwendung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-349">The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-350">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-350">Requirements</span></span>

<span data-ttu-id="cd9fa-351">Es gibt keine Anforderungen, wenn dieses Tool auf demselben Computer ausgeführt wird, auf dem CPS ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="cd9fa-352">Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von lync Server 2013 verwendete SQL Server Datenbank so konfiguriert werden, dass der Remotezugriff zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="cd9fa-353">Der Aufruf Parkometer muss mit einer SQL Server Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="cd9fa-354">Diese SQL Server Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Es muss sich in demselben Verzeichnis befinden, in dem sich parkometer. exe befindet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="cd9fa-355">Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Die Parameter, die konfiguriert werden müssen, sind Benutzername (beispielsweise mydomain\\Administrator), Kennwort (beispielsweise mypassword) und Hostname (beispielsweise MyServer).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-356">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-356">Examples</span></span>

<span data-ttu-id="cd9fa-357">Bereitgestellte Umlaufbahn Bereiche: der Parameter "– o" listet alle Umlaufbahn Bereiche auf, die für diesen Pool konfiguriert sind (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="cd9fa-358">![Orbitbereiche in der Anruf Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbitbereiche in der Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="cd9fa-359">Zurzeit geparkte Anrufe: der Parameter "– n" listet alle derzeit verwendeten Umlaufbahnen in diesem Pool auf (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="cd9fa-360">![Zurzeit geparkte Anrufe in Anruf Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Zurzeit geparkte Anrufe in Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="cd9fa-361">Anzahl der freien Umlaufbahnen: der Parameter "– f" listet die Anzahl der derzeit freien Umlaufbahnen im Pool auf (siehe Abbildung).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="cd9fa-362">![Freie Umlaufbahnen in der Anruf Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Freie Umlaufbahnen in der Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="cd9fa-363">Zuletzt geparkte Anrufe: der Parameter \<–\> r n listet \<die\> n zuletzt geparkten Anrufe wie dargestellt auf.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="cd9fa-364">![Zuletzt geparkte Anrufe in Anruf Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Zuletzt geparkte Anrufe in Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="cd9fa-365">Test Orbit-Reservierung: der – \<t\> n-Parameter testet, wie in der Abbildung gezeigt, eine Umlaufbahn in der Datenbank reserviert</span><span class="sxs-lookup"><span data-stu-id="cd9fa-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="cd9fa-366">![Testen Sie die Orbit-Reservierungen in der Anruf Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testen Sie die Orbit-Reservierungen in der Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-367">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-367">Summary</span></span>

<span data-ttu-id="cd9fa-368">Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Server für das Parken von Anrufen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="cd9fa-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="cd9fa-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="cd9fa-370">Mit dem CleanupStorageServiceData Resource Kit-Tool können verwaiste Daten aus der vom lync Server Storage Service (LYSS) verwendeten Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="cd9fa-371">Eine Funktion des Speicher Diensts besteht darin, die Kommunikation zwischen lync Server und verschiedenen Back-End-Datenspeicher Endpunkten wie SQL Server und Exchange zu puffern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-372">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-372">Description</span></span>

<span data-ttu-id="cd9fa-373">Zur Unterstützung von hoher Verfügbarkeit akzeptiert und speichert LYSS vorübergehend Kopien der Daten auf mehreren Front-End-Servern im Pool und entfernt diese Daten, sobald Sie an ihren endgültigen langfristigen Speicherort übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="cd9fa-374">Es gibt ungewöhnliche Situationen, die im ansonsten normalen Betrieb auftreten können, wenn ein Server abstürzt oder ein Verarbeitungsproblem auftritt und einige Daten möglicherweise nicht ordnungsgemäß bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="cd9fa-375">Diese Daten sind harmlos, verbrauchen jedoch nur beschränkte Verarbeitungsressourcen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="cd9fa-376">Ein Großteil der normalerweise erforderlichen Datenwartung ist automatisiert, aber dieses Tool ermöglicht die sichere Identifizierung und Entfernung solcher verwaister Daten, wenn das automatisierte entfernen nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="cd9fa-377">Die Verwendung dieses Tools wird angezeigt, wenn eine System Center Operations Manager (SCOM)-Warnung ausgelöst wird, die den Administrator auffordert, die nicht benötigten Daten aus den lokalen LYSS-Datenbanken im Pool zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="cd9fa-378">Es wird ein entsprechendes Ereignis im Ereignisprotokoll auf dem Front-End, das die Warnung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="cd9fa-379">Die Ereignisdetails enthalten Informationen über die Menge an verwaisten Daten, die auf dem Front-End enthalten sind, und werden ausgelöst, wenn diese Daten bestimmte Schwellenwerte überschreiten, die vor der Festlegung liegen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-380">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-380">Requirements</span></span>

<span data-ttu-id="cd9fa-381">Installieren Sie die lync Server 2013 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="cd9fa-382">Das Tool wird auf Computern mit Domänenbeitritt ausgeführt, auf denen lync Server und lync Server 2013 Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="cd9fa-383">Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="cd9fa-384">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="cd9fa-385">Diese Datenbank wird vom CleanupStorageServiceData-Tool verwendet, um die Verbindungsdetails abzurufen, die für die Kommunikation mit dem lync Server Routing Dienst erforderlich sind. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über Lese-/Schreibzugriff auf die Dateifreigabe verfügen, in die das Ausgabeprotokoll geschrieben werden soll. Außerdem hängt dieses Tool davon ab, dass sich der Pool in einem stabilen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="cd9fa-386">Im Wesentlichen bedeutet dies, dass jeder Front-End-Server voraussichtlich betriebsbereit ist, die SQL Server LYNCLOCAL-Instanz und die Lysser-Datenbank müssen mit verbunden sein, und jede Routinggruppe muss über einen vollständigen Satzes von 1 primären Front-End-Servern und 2 sekundären Front-End-s verfügen. Server aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-387">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-387">Examples</span></span>

<span data-ttu-id="cd9fa-388">C:\\Programmdateien\\Microsoft lync Server 2013\\reskit\\StorageService\> ImportStorageServiceData. exe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a><span data-ttu-id="cd9fa-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="cd9fa-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-390">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-390">Description</span></span>

<span data-ttu-id="cd9fa-391">Dbanalyze ist ein Befehlszeilentool, mit dem Administratoren Analyseberichte zu den lync Server 2013 Datenbanken sammeln können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="cd9fa-392">Dbanalyze verfügt über die folgenden Modi: Diagnose, Benutzerdaten, Konferenz, MCU und Datenträgerfragmentierung:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="cd9fa-393">**Der Diagnosemodus**   erstellt einen Bericht mit Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern mit Microsoft Office Communications Server, die durchschnittliche Anzahl von Berechtigungen, Kontakte, Container, Abonnements, Publikationen, Endpunkte pro Benutzer, nicht ordnungsgemäß verwaltete Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplant Konferenzen, aktive Konferenzen und die Datenbankversion.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd9fa-394">Die Ausführung des Diagnosemodus kann sich auf die Serverleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="cd9fa-395">Der **Benutzerdaten Modus**  meldet Kontakt-, Container-, Abonnement-, Publikations-, Berechtigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="cd9fa-396">In diesem Modus werden auch Zusammenfassungsdaten für Konferenzen gemeldet, die ein Benutzer organisiert oder dazu eingeladen wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="cd9fa-397">**Der Konferenzmodus**   meldet detaillierte Daten für eine bestimmte Konferenz, einschließlich aller Terminplanzeit Details für die Konferenz, der Einladungsliste, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und des Signalisierungs Status jedes Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="cd9fa-398">**Decodieren von Besprechungs-IDs**  decodiert eine PSTN-Besprechungs-ID (Public Switched Telephone Network), die durch den **Parameter/pstnid** -Switch angegeben wird, aber keine Verbindung zum Back-End für detaillierte Informationen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="cd9fa-399">**Konferenz auflösen**   decodiert eine PSTN-Besprechungs-ID, die vom **Parameter/pstnid** -Schalter angegeben wird, und zeigt Informationen über die Konferenz an, die durch die ID angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="cd9fa-400">**Der MCU-Modus**  meldet die ID, den Medientyp, die URL, den Takt Status, die Konferenz Last und die Teilnehmer Auslastung für jede MCU im Pool.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="cd9fa-401">**Im Modus "Datenträgerfragmentierung"**  wird der Fragmentierungs Status aller Datenträger angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="cd9fa-402">Dieses Tool kann verwendet werden, um verschiedene Probleme zu diagnostizieren oder Administratoren bei der Kapazitätsplanung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-402">This tool can be used to diagnose various problems or to assist administrators with capacity planning.</span></span> <span data-ttu-id="cd9fa-403">Wenn beispielsweise die meisten der Benutzer, die sich auf dem Server a befinden, Benutzer auf Server b als Kontakte verwaltet haben, kann der Administrator die Benutzer auf Server a auf Server b umstellen, um den serverübergreifenden Datenverkehr zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-403">For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-404">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-404">Output</span></span>

<span data-ttu-id="cd9fa-405">Dieses Tool gibt vordefinierte Berichte zur lync Server 2013 Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="cd9fa-406">**Pfad:** % Programme%\\Microsoft lync Server 2013\\reskit</span><span class="sxs-lookup"><span data-stu-id="cd9fa-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-407">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-407">Purpose</span></span>

<span data-ttu-id="cd9fa-408">Um Dbanalyze. exe zu installieren, kopieren Sie Sie in einen lokalen Ordner, und führen Sie das Tool aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="cd9fa-409">Führen Sie den folgenden Befehl an der Befehlszeile aus, um das Tool zu verwenden.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="cd9fa-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="cd9fa-410">Die Beschreibungen der Befehlszeilenoptionen werden unten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="cd9fa-411">![Befehlszeilenoptionen für Dbanalyze. exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Befehlszeilenoptionen für Dbanalyze. exe.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-412">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-412">Requirements</span></span>

<span data-ttu-id="cd9fa-413">**Computer** Dbanalyze kann nur von einem Computer ausgeführt werden, der der Domäne angehört und auf dem lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="cd9fa-414">**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="cd9fa-415">**Software** Lync Server 2013 Softwarekomponenten müssen vor dem Ausführen von Dbanalyze installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="cd9fa-416">**Benutzer** Die folgende Tabelle zeigt die Administratoren, die über die erforderlichen Berechtigungen für den Zugriff auf lync Server 2013-Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="cd9fa-417">![Berechtigungstabelle für Dbanalyze. exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Berechtigungstabelle für Dbanalyze. exe.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-418">Für/Report ist ein lokales Administratorkonto erforderlich <STRONG>: Datenträger</STRONG> Modus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-419">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-419">Examples</span></span>

<span data-ttu-id="cd9fa-420">Im folgenden sind Beispiele für gültige Dbanalyze. exe-Befehle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-421">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-421">Summary</span></span>

<span data-ttu-id="cd9fa-422">Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse lync Server 2013 Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="cd9fa-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="cd9fa-423">ImportStorageServiceData</span></span>

<span data-ttu-id="cd9fa-424">Das ImportStorageServiceData Resource Kit-Tool ermöglicht das erneute Importieren von Warteschlangen-und Endpunkt Daten, die aus dem Speicherdienst (LYSS) wieder in den Speicherdienst geleert wurden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-425">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-425">Description</span></span>

<span data-ttu-id="cd9fa-426">Die aus dem Speicherdienst gelöschten Daten konnten auf der Grundlage des Warteschlangenelement Status oder der Datenbankgröße automatisch (regelmäßig) sein.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="cd9fa-427">Möglicherweise ist dies auf den manuellen Aufruf des Cmdlets "Pool Failover" oder auf das StorageServiceFullFlush-Cmdlet zurückzuführen, das vom Pool-Failover-Cmdlet aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="cd9fa-428">Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, da dies wahrscheinlich dazu führt, dass mehr Daten zurück exportiert werden. Außerdem sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange ansteigt, zuerst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="cd9fa-429">**Szenario 1:** während des Pool Failovers können Dateien für jedes Front-End aus dem Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="cd9fa-430">Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="cd9fa-431">**Szenario 2:** die Daten werden jeden Tag automatisch oder als Reaktion auf die Speicherdienst Datenbank geleert, die bestimmte größenschwellenwerte überschreitet (beispielsweise 60%, 80%, 90% vollständig).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="cd9fa-432">Diese automatisch gespülten Daten sollten vom Administrator routinemäßig erneut importiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="cd9fa-433">Wenn das Monitoring-SCOM-Paket nicht bereitgestellt ist, gibt es in der obigen Situation Ereignisse für lync Server Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="cd9fa-434">Ereignis-IDs von 32075 (vollständiger Löschvorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Wartungsebene ist leer), 32089 (Flush erfolgte aufgrund des Füllens der Datenbank).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="cd9fa-435">Hinweis Diese Ereignis-IDs entsprechen der RTM-Version.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="cd9fa-436">Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien geleert wurden. Diese Daten sollten mit diesem Tool routinemäßig wieder importiert werden, beispielsweise einmal pro Woche.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="cd9fa-437">Wenn für die Online Dienstversion die SCOM Pack for lync Server-Integritätsüberwachung bereitgestellt wird, werden möglicherweise neue Warnungen ausgelöst, die den Administrator auffordern, die gelöschten Daten wieder in den Speicherdienst zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="cd9fa-438">Im Ereignisprotokoll auf dem Front-End-Server, der die Warnung ausgelöst hat, ist ein entsprechendes Ereignis vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="cd9fa-439">Das Ereignis gibt eine Beschreibung des übergeordneten Pfads an, unter dem sich die geleerten Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="cd9fa-440">Die Warnungskriterien sind, dass es x oder mehr Dateien unter dem bestimmten übergeordneten Pfad gibt, die mindestens Y Tage alt sind (wobei x und y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei außer Kraft gesetzt werden können). Im folgenden werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können: der Unterschied ist der übergeordnete Pfad.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="cd9fa-441">Eine Möglichkeit besteht unter Webdienst-Dateifreigabe, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="cd9fa-442">(zum Beispiel c:\\ProgramData\\Microsoft\\lync Server\\StorageService).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="cd9fa-443">Der Administrator führt dann dieses reskit-Tool aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="cd9fa-444">Dieses Tool erhöht die CPU-und e/a-Last auf dem Front-End, auf dem es ausgeführt wird, sowie anderen Front-Ends in der Situation, dass die Daten nicht dem Front-End gehören, auf dem das Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="cd9fa-445">Es wird empfohlen, dieses Tool Ausführung, wenn die Front-Ends nicht unter starker CPU-und e/a-Last stehen, beispielsweise außerhalb der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="cd9fa-446">Zweitens kann dieses Tool 2 bis 3 Minuten, um eine Datendatei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="cd9fa-447">Beachten Sie dies, wenn Sie schätzen, wie lange das Tool in Betrieb sein wird. Die vom Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="cd9fa-448">Löschen Sie es, wenn keine Fehler gemeldet werden, da die Protokolldatei zehn MB oder mehr sein kann.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="cd9fa-449">![Beispiele für Ereignisprotokoll Ereignisse des Speicherservers.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Beispiele für Ereignisprotokoll Ereignisse des Speicherservers.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-450">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-450">Requirements</span></span>

<span data-ttu-id="cd9fa-451">Installieren Sie die lync Server 2013 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="cd9fa-452">Das Tool wird auf Computern mit Domänenbeitritt ausgeführt, auf denen lync Server und lync Server-Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="cd9fa-453">Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="cd9fa-454">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="cd9fa-455">Diese Datenbank wird vom Tool zum Abrufen des Speicherorts der Webservice-Dateifreigabe für den Pool verwendet. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools Windows PowerShell Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer, von dem aus das Tool ausgeführt wird, aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="cd9fa-456">Andernfalls tritt für Remote Windows PowerShell-Befehle dieses Tools ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="cd9fa-457">Windows PowerShell Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="cd9fa-458">Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über Lese-/Schreibzugriff auf die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="cd9fa-459">Andernfalls kann das Tool mit e/a-Berechtigungsfehlern fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-460">In Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht auf dem Betriebssystem Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-461">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-461">Examples</span></span>

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

</div>

</div>

<div>

## <a name="lcssync"></a><span data-ttu-id="cd9fa-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="cd9fa-462">LCSSync</span></span>

<span data-ttu-id="cd9fa-463">Das LCSSync-Tool hilft bei der Bereitstellung lync Server 2013 Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="cd9fa-464">Dieses Tool dient zum Synchronisieren von Benutzern und Gruppen aus unterschiedlichen Benutzergesamtstrukturen als Active Directory-Domänendienste Kontaktobjekt mit einer zentralen Gesamtstruktur, in der lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-465">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-465">Description</span></span>

<span data-ttu-id="cd9fa-466">LCSSync verwendet die synchronisierten Active Directory-Domänendienste Contact-Objekte in der zentralen Gesamtstruktur, um Benutzer für lync Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="cd9fa-467">Um die einmalige Anmeldung bereitstellen zu können, muss das primäre Benutzerkonto dem Active Directory-Domänendienste Contact-Objekt in der zentralen Gesamtstruktur für lync Server 2013 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="cd9fa-468">Dieses Tool unterstützt Sie bei der Durchführung dieser Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="cd9fa-469">Dieses Tool enthält Vorlagen zum Erstellen von Verwaltungs-Agents auf dem Microsoft Identity Integration Server.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-470">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-470">Summary</span></span>

<span data-ttu-id="cd9fa-471">Das LCSSync-Tool hilft bei der Bereitstellung von lync Server in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="cd9fa-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="cd9fa-472">LookupUserConsole</span></span>

<span data-ttu-id="cd9fa-473">Das LookupUserConsole-Tool zeigt interne lync Server Routinginformationen zu bestimmten Benutzern an.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="cd9fa-474">Diese Informationen können für den Microsoft-Support persönlich hilfreich sein, wenn Sie Bereitstellungs-und Routingprobleme diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-475">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-475">Description</span></span>

<span data-ttu-id="cd9fa-476">Durch die Ausführung von LookupUserConsole. exe wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne lync Server Routinginformationen anzuzeigen, die Sie betreffen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="cd9fa-477">Geben Sie **Exit** ein, um das LookupUserConsole-Tool zu beenden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-478">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-478">Requirements</span></span>

<span data-ttu-id="cd9fa-479">Installieren Sie die lync Server 2013 Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="cd9fa-480">Das Tool wird auf Domänencomputern ausgeführt, auf denen lync Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-481">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-481">Examples</span></span>

<span data-ttu-id="cd9fa-482">C:\\Programmdateien\\Microsoft lync Server 2013\\reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

</div>

</div>

<div>

## <a name="msturnping"></a><span data-ttu-id="cd9fa-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="cd9fa-483">MsTurnPing</span></span>

<span data-ttu-id="cd9fa-484">Mit dem MSTurnPing-Tool kann ein Administrator von Microsoft lync Server 2013 Kommunikationssoftware den Status der Server, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste durchführen, sowie die Server überprüfen, auf denen Bandbreitenrichtlinien Dienste in der Topologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-485">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-485">Description</span></span>

<span data-ttu-id="cd9fa-486">Mit dem MSTurnPing-Tool kann ein Administrator von lync Server 2013 Kommunikationssoftware den Status der Server, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste durchführen, sowie die Server überprüfen, auf denen Bandbreitenrichtlinien Dienste in der Topologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="cd9fa-487">Das Tool ermöglicht es dem Administrator, die folgenden Tests auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="cd9fa-488">A/v-Edgeserver Test: das Tool führt Tests für alle A/v-Edgeserver in der Topologie aus, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="cd9fa-489">Überprüfen, ob der lync Server Audio/Video-Authentifizierungsdienst gestartet wurde, und Sie können ordnungsgemäße Anmeldeinformationen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="cd9fa-490">Überprüfen, ob der lync Server Audio/Video-Edgedienst gestartet wurde, und die Ressourcen auf dem externen edgevorgang erfolgreich zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="cd9fa-491">Bandbreitenrichtliniendienst Test: das Tool führt Tests für alle Server aus, auf denen die Bandbreitenrichtlinien Dienste in der Topologie ausgeführt werden, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="cd9fa-492">Überprüfen, ob der lync Server bandbreitenrichtliniendienst (Authentication) gestartet wurde und ordnungsgemäße Anmeldeinformationen ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="cd9fa-493">Überprüfen, ob der lync Server bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="cd9fa-494">Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-495">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-495">Output</span></span>

<span data-ttu-id="cd9fa-496">Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="cd9fa-497">Wenn der **AudioVideoEdgeServer** -Test durchgeführt wird, werden die Ausgaben des Tools folgendermaßen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="cd9fa-498">Die Testergebnisse der Computer, die den lync Server-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="cd9fa-499">Die Testergebnisse der Computer, die den lync Server Audio/Video-Edgedienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="cd9fa-500">Wenn der **BandwidthPolicyServer** -Test durchgeführt wird, werden die Ausgaben des Tools folgendermaßen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="cd9fa-501">Die Testergebnisse der Computer, die den lync Server bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="cd9fa-502">Die Testergebnisse der Computer, die den lync Server bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-503">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-503">Requirements</span></span>

  - <span data-ttu-id="cd9fa-504">Dieses Tool muss von einem Computer ausgeführt werden, der sich in der Topologie befindet und über den lokalen Speicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="cd9fa-505">Das Tool muss als Administrator ausgeführt werden, der Zugriff auf den lokalen Speicher hat.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-506">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-506">Examples</span></span>

<span data-ttu-id="cd9fa-507">Nachfolgend sehen Sie ein Beispiel für die Tool Eingabe.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-508">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-508">Summary</span></span>

<span data-ttu-id="cd9fa-509">Dieses Tool kann eine wertvolle Ressource für lync Server 2013 Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste durchführen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="cd9fa-510">Netzwerk Konfigurationsanzeige</span><span class="sxs-lookup"><span data-stu-id="cd9fa-510">Network Configuration Viewer</span></span>

<span data-ttu-id="cd9fa-511">Die Netzwerkkonfigurations-Anzeige kann von Microsoft lync Server 2013 Kommunikationssoftware Administratoren verwendet werden, um die Anruf Steuerungs Netzwerk-Topologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zu ermöglichen, beispielsweise sprach-oder Videoanrufe basierend auf der angegebenen Bandbreitenkapazität.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="cd9fa-512">Lync Server 2013 Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit lync Server 2013 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-513">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-513">Description</span></span>

<span data-ttu-id="cd9fa-514">Network Configuration Viewer (NetworkConfigurationViewer. exe) ermöglicht Administratoren das Ausführen der folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="cd9fa-515">Laden und Anzeigen der CAC-Netzwerktopologie aus einer lync Server 2013-Bereitstellung in einem grafischen Format.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="cd9fa-516">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="cd9fa-517">Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="cd9fa-518">Speichern und speichern Sie das Diagramm der CAC-Netzwerktopologie im JPG-oder BMP-Format.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="cd9fa-519">Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="cd9fa-520">View CAC Network Topology in a Tree-View Style.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="cd9fa-521">Definieren Sie benutzerdefinierte Connectors für CAC-Netzwerktopologie-Links (beispielsweise Standort-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="cd9fa-522">Anzeigen der Informationen zur CAC-Netzwerktopologie, Regionsinformationen sowie Richtlinien für die verfügbare Bandbreite und Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-523">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-523">Purpose</span></span>

<span data-ttu-id="cd9fa-524">Anzeigen der Verknüpfungen der Enterprise-CAC-Netzwerktopologie in einer grafischen Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-525">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-525">Examples</span></span>

<span data-ttu-id="cd9fa-526">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer lync Server 2013-Bereitstellung im grafischen Format:** Lync Server 2013 Administratoren können die Konfiguration der CAC-Netzwerktopologie auf einem beliebigen lync Server 2013 Computer mithilfe der Option " **Netzwerkkonfiguration herunterladen** " Laden und anzeigen, wie in der Abbildung unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="cd9fa-527">Das Tool kann eine solche Konfiguration nicht herunterladen oder anzeigen, wenn Sie auf einem Computer bereitgestellt wird, der nicht über eine Verbindung mit dem lync-Konfigurationsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="cd9fa-528">![Herunterladen der Netzwerkkonfiguration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Herunterladen der Netzwerkkonfiguration.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="cd9fa-529">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei im grafischen Format:** Lync Server 2013 Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem lync Server 2013 Dateifreigabespeicherort.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="cd9fa-530">Lync Server Administratoren können eine solche Datei mit der **Open Network Configuration** -Option wie unten gezeigt in einem grafischen Format anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="cd9fa-531">![Öffnen einer Bandbreitenrichtlinien Server-Protokolldatei.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Öffnen einer Bandbreitenrichtlinien Server-Protokolldatei.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="cd9fa-532">Speichern und speichern Sie die Anrufsteuerung-Netzwerktopologie in einem XML-Format auf dem Datenträger: lync Server 2013 Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** wie unten gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="cd9fa-533">Die gespeicherte Konfigurationsdatei kann dann offline für grafische Anzeigezwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="cd9fa-534">![Speichern der Netzwerkkonfiguration als XML-Datei.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Speichern der Netzwerkkonfiguration als XML-Datei.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="cd9fa-535">Speichern und Speichern von Diagrammen der CAC-Netzwerktopologie im JPG-oder BMP-Format: lync Server 2013 Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie die Option **Netzwerk Konfigurations Diagramm als Bild speichern** wie unten gezeigt verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="cd9fa-536">![Speichern der Netzwerkkonfiguration als Bild.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Speichern der Netzwerkkonfiguration als Bild.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="cd9fa-537">**Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:** Lync Server 2013 Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerkstandorte, Bandbreiten Profile und IP-Adressen von Standort Netzwerken in einem Text Format anzeigen, indem Sie die Option "Netzwerkkonfigurationsdaten anzeigen" wie unten dargestellt verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="cd9fa-538">![Anzeigen von Netzwerkkonfigurationsdaten.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="cd9fa-539">**Anzeigen der Anruf Steuerungs Netzwerktopologie in einem Struktur Ansichtsstil:** Lync Server 2013 Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsformat mithilfe der Systemsteuerung auf der linken Seite des Toolfensters anzeigen, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="cd9fa-540">![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="cd9fa-541">**Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Standort-zu-Region, Region-zu-Region und Standort-zu-Standort-Links):** Lync Server 2013 Administratoren können benutzerdefinierte grafische Konnektoren für Netzwerk Konfigurations-WAN-Verbindungen mithilfe der Einstellungsoption wie unten dargestellt definieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="cd9fa-542">Dies hilft bei der Unterscheidung zwischen verschiedenen Typen von Netzwerkverbindungen, die in der Netzwerkkonfiguration bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="cd9fa-543">![Definieren von benutzerdefinierten Connectors für die Anruf Steuerungs Netzwerktopologie](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für die Anruf Steuerungs Netzwerktopologie")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="cd9fa-544">**Anzeigen der Informationen zur CAC-Netzwerktopologie, Regionsinformationen und Richtlinien für die verfügbare Bandbreite:** Lync Server 2013 Administratoren können Informationen zu zugehörigen CAC-netzwerkregionen, Standortinformationen und Informationen zur Anruf Steuerungs Bandbreite mithilfe der unten aufgeführten Optionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="cd9fa-545">(Klicken Sie beispielsweise in einer netzwerkregion oder einem Netzwerkstandort Objekt auf **Info** .)</span><span class="sxs-lookup"><span data-stu-id="cd9fa-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="cd9fa-546">![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für Ihr Netzwerk.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-547">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-547">Summary</span></span>

<span data-ttu-id="cd9fa-548">Dieses Tool kann eine wertvolle Ressource für lync Server 2013 Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="cd9fa-549">Reaktionsgruppen-Agent Live</span><span class="sxs-lookup"><span data-stu-id="cd9fa-549">Response Group Agent Live</span></span>

<span data-ttu-id="cd9fa-550">Mit dem Reaktionsgruppenanwendung können Agents mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="cd9fa-551">Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="cd9fa-552">Das Reaktionsgruppen-Agent-Live Resource Kit-Tool löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die mit Echt Zeit Microsoft lync 2013 Kommunikationssoftware Informationen wie etwa dem vorhanden sein anderer Agents erweitert wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-553">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-553">Description</span></span>

<span data-ttu-id="cd9fa-554">Bei Agent Live für Reaktionsgruppen handelt es sich um eine Windows-Anwendung, die die Funktionen für die Anmeldung und Abmeldung sowie einige Echtzeitinformationen (beispielsweise die Gruppenmitgliedschaft und die aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="cd9fa-555">Es handelt sich um eine erweiterte Version der Seite "Agentgruppen" (verfügbar über lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-556">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-556">Purpose</span></span>

<span data-ttu-id="cd9fa-557">In der Reaktionsgruppenanwendung werden eingehende Anrufe in die Warteschlange eingereiht und an Agentgruppen weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-557">The Response Group application queues incoming calls, and then routes them to agent groups.</span></span> <span data-ttu-id="cd9fa-558">Um fundierte Entscheidungen darüber zu treffen, welche Anrufe für Dienste durchzuführen sind, können Agents auf Echtzeitinformationen zu ihren Agentgruppen zugreifen, beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschlange warten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-558">To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue.</span></span> <span data-ttu-id="cd9fa-559">Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst zugänglich sind, werden auf intuitive Weise vom Reaktionsgruppen-Agent Live zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-559">This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="cd9fa-560">Features</span><span class="sxs-lookup"><span data-stu-id="cd9fa-560">Features</span></span>

<span data-ttu-id="cd9fa-561">Das Live-Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem SDK für Microsoft lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="cd9fa-562">Sie stellt Reaktionsgruppen-Agents die Informationen und Funktionen zur Verfügung, die über den Reaktionsgruppendienst verfügbar sind (wie Gruppenmitgliedschaft, Anwesenheit von anderen Agents und Anzahl der wartenden Anrufe).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="cd9fa-563">In der folgenden Abbildung ist die Hauptschnittstelle des Reaktionsgruppen-Agents Live dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="cd9fa-564">![Das Live-Tool für Reaktionsgruppen-Agents.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Das Live-Tool für Reaktionsgruppen-Agents.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="cd9fa-565">Die folgenden drei Hauptfeatures stehen für Agents im Reaktionsgruppen-Agent Live zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="cd9fa-566">**Anmelden/Auschecken:** Im Gegensatz zur Seite "Agentgruppen" (auf die von lync 2013 zugegriffen werden kann) kann der Reaktionsgruppen-Agent Live nur Agents auf einmal anmelden oder sich bei allen Agentgruppen abmelden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="cd9fa-567">Diese Anwendung bietet drei schnelle Methoden für die Anmeldung von Agents:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="cd9fa-568">Klicken Sie in der Anwendung auf die Schaltflächen zum Anmelden/Auschecken (grün und rot).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="cd9fa-569">Klicken Sie mit der rechten Maustaste auf das Symbol in der Taskleiste, und wählen Sie anmelden oder Abmelden aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="cd9fa-570">Verwenden von konfigurierbaren Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="cd9fa-571">**Gruppenmitgliedschaft:** Wenn eine Agentgruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="cd9fa-572">Wenn lync 2013 auf demselben Computer wie diese Anwendung läuft, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="cd9fa-573">Agents können direkt von dort aus einen Chat senden oder andere Agents anrufen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="cd9fa-574">**Echtzeitstatistik:** Der Reaktionsgruppen-Agent Live bietet Echtzeitstatistiken für alle Agentgruppen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-574">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups.</span></span> <span data-ttu-id="cd9fa-575">Die Aktualisierungshäufigkeit beträgt eine Minute.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-575">The update frequency is one minute.</span></span> <span data-ttu-id="cd9fa-576">Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein visuelles Symbol mit der aktuellen Anzahl von in der Warteschlange befindlichen anrufen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-576">When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls.</span></span> <span data-ttu-id="cd9fa-577">Wenn Sie den Zeiger über eine Gruppe anhalten, wird auch die längste Wartezeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-577">Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-578">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-578">Requirements</span></span>

<span data-ttu-id="cd9fa-579">Für den Reaktionsgruppen-Agent Live ist der .NET Framework 4,0 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="cd9fa-580">Darüber hinaus müssen lync 2013 lokal installiert sein (und ausgeführt werden), um die Anwesenheits-und Visitenkarten Funktionen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="cd9fa-581">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="cd9fa-581">Configuration</span></span>

<span data-ttu-id="cd9fa-582">Der Live Reaktionsgruppen-Agent kann mithilfe des Dialogfelds Optionen in der Anwendung an individuelle Einstellungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-582">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application.</span></span> <span data-ttu-id="cd9fa-583">Darüber hinaus kann der Administrator die Standardhost Adresse definieren, indem er die defaultHostAddress-Eigenschaft der Datei RGAgentLive. exe. config direkt bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-583">In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="cd9fa-584">Die folgende Abbildung zeigt das Dialogfeldoptionen, mit dem Agents die Hostadresse und die Tastenkombinationen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-584">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys.</span></span> <span data-ttu-id="cd9fa-585">Der Zugriff auf dieses Dialogfeld erfolgt durch Klicken auf die Schaltfläche Optionen oben rechts auf der Hauptoberfläche.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-585">This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="cd9fa-586">![Das Dialogfeld Reaktionsgruppen-Agent-Live Optionen.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Das Dialogfeld Reaktionsgruppen-Agent-Live Optionen.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="cd9fa-587">Die folgenden drei unterschiedlichen Einstellungen können in der Live-Konfiguration des Reaktionsgruppen-Agents angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="cd9fa-588">Host Adresse: Dies ist normalerweise der FQDN des webpools, der zum Home-Pool des Agents gehört.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-588">Host address: This is typically the web pool FQDN belonging to the agent’s home pool.</span></span> <span data-ttu-id="cd9fa-589">Die genaue Adresse des Reaktionsgruppendiensts wird automatisch aus diesen Informationen im Hintergrund abgeleitet (durch Anfügen des richtigen Pfads nach dem Host).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-589">The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="cd9fa-590">Shortcuts: die genauen Verknüpfungen zum Anmelden/Auschecken können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-590">Shortcuts: The exact shortcuts to sign-in/out can be customized.</span></span> <span data-ttu-id="cd9fa-591">Die einzige Einschränkung besteht darin, dass beide Verknüpfungen die Taste "Windows-Logo" (zusätzlich zu mindestens einem anderen Schlüssel) enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-591">The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="cd9fa-592">Beginnen mit Windows: die Anwendung kann so konfiguriert werden, dass Sie automatisch mit Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-593">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-593">Examples</span></span>

<span data-ttu-id="cd9fa-594">Die folgende Abbildung zeigt, wie Sie eine Sofortnachricht an einen anderen Agent aufrufen oder senden, indem Sie mit der rechten Maustaste auf den Kontakt im rechten Bereich klicken.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="cd9fa-595">![Tätigen eines Anrufs oder Sendens eines Chats.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Tätigen eines Anrufs oder Sendens eines Chats.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="cd9fa-596">Die folgende Abbildung zeigt, wie der Reaktionsgruppen-Agent Live die aktuelle Anzahl von Anrufen in der Warteschlange und die längste Wartezeit unter all diesen eingehenden Anrufen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="cd9fa-597">![Anzeigen von Warteschlangeninformationen.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Anzeigen von Warteschlangeninformationen.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-598">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-598">Summary</span></span>

<span data-ttu-id="cd9fa-599">Schnelle Anmeldung und Abmeldung, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Features für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung aus dem Reaktionsgruppendienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="cd9fa-600">Mit dem Reaktionsgruppen-Agent Live Resource Kit-Tool können lync-Administratoren ihren Agents eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben schneller und grafischer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="cd9fa-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="cd9fa-601">SEFAUtil</span></span>

<span data-ttu-id="cd9fa-602">SEFAUtil (Secondary Extension Feature Activation) ist ein Befehlszeilentool, mit dem Microsoft lync Server 2013 Kommunikationssoftware Administratoren und Helpdesk-Agents Delegate-Klingeln, Anrufweiterleitung, gleichzeitiges Klingeln, Teamanrufe konfigurieren können. Einstellungen und Gruppenanruf Abholung im Auftrag eines lync Server 2013 Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="cd9fa-603">Das Tool ermöglicht es Administratoren auch, die Anrufweiterleitungseinstellungen abzufragen, die für einen bestimmten Benutzer veröffentlicht werden. Das SEFAUtil-Tool ermöglicht dem Administrator das aktivieren/deaktivieren/Ändern der Anrufweiterleitung oder das gleichzeitige Klingeln im Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="cd9fa-604">Der Administrator kann das Ziel (in Form eines SIP-URI) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="cd9fa-605">Mit diesem Tool können Administratoren auch Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzufügen oder entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="cd9fa-606">SEFAUtil (sekundäre Erweiterung Feature Activation) ermöglicht es lync Server 2013 Administratoren und Helpdesk-Agents, Stellvertreter-Klingeln, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anrufeinstellungen und gruppenanrufannahme im Auftrag eines lync Server 2013 Benutzers zu konfigurieren. .</span><span class="sxs-lookup"><span data-stu-id="cd9fa-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="cd9fa-607">Mit diesem Tool können Administratoren auch die Anrufweiterleitungseinstellungen Abfragen, die für einen bestimmten Benutzer veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-608">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-608">Description</span></span>

<span data-ttu-id="cd9fa-609">Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="cd9fa-610">Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3.0.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="cd9fa-611">Die Funktionen in diesem Tool ermöglichen Administratoren und Helpdesk-Agents Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="cd9fa-612">Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Delegierung, gleichzeitiges Klingeln, Team-und gruppenanrufannahme)</span><span class="sxs-lookup"><span data-stu-id="cd9fa-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="cd9fa-613">Aktivieren/Deaktivieren/Ändern der Einstellung für die Anrufweiterleitung (schließt den Ziel-und den nicht-Antwort-Timer ein)</span><span class="sxs-lookup"><span data-stu-id="cd9fa-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="cd9fa-614">Aktivieren/Deaktivieren/Ändern der unmittelbaren Konfigurationen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="cd9fa-615">Aktivieren/Deaktivieren/ändern von Delegierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="cd9fa-616">Aktivieren/Deaktivieren/ändern von Einstellungen für die Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd9fa-617">Neu in lync Server 2013 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="cd9fa-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="cd9fa-618">Aktivieren/Deaktivieren/ändern gleichzeitiger Klingel Einstellungen (umfasst das Ziel)</span><span class="sxs-lookup"><span data-stu-id="cd9fa-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd9fa-619">Neu in lync Server 2013 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="cd9fa-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="cd9fa-620">Aktivieren/Deaktivieren/ändern von Einstellungen für die gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="cd9fa-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="cd9fa-621">Neu in lync Server 2013 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="cd9fa-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="cd9fa-622">Dieses Tool hat die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="cd9fa-623">Nur für Benutzer unterstützt, die in einem lync Server-Pool verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="cd9fa-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="cd9fa-624">Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="cd9fa-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-625">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-625">Output</span></span>

<span data-ttu-id="cd9fa-626">Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster eine Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-626">The current version of this tool provides output only in the Command Prompt window.</span></span> <span data-ttu-id="cd9fa-627">Ausführliche Informationen finden Sie im Abschnitt "Beispiele" weiter unten in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-627">For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-628">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-628">Purpose</span></span>

<span data-ttu-id="cd9fa-629">Im folgenden finden Sie einige der wichtigsten Szenarien, in denen dieses Tool verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="cd9fa-630">Bob ist eine Führungskraft und wurde in lync Server Telefonie verschoben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="cd9fa-631">Er verfügt über eine Delegation für sein vorhandenes PBX-System.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="cd9fa-632">Im Rahmen des Wechsels zu lync kann der Administrator Bobs Routing so konfigurieren, dass er seine bereits vorhandene Delegierungs Konfiguration widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="cd9fa-633">Alice reist und erkennt, dass Sie einen wichtigen Anruf von einem ihrer Kunden erwartet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-633">Alice is travelling and realizes that she is expecting an important call from one of her customers.</span></span> <span data-ttu-id="cd9fa-634">Sie befindet sich jedoch in einem Hotel und hat keinen Zugriff auf einen Computer.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-634">However, she is in a hotel and has no access to a computer.</span></span> <span data-ttu-id="cd9fa-635">Sie ruft den Helpdesk an und fordert an, dass Sie alle Anrufe an Ihre Telefonnummer an Ihre Mobiltelefonnummer weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-635">She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number.</span></span> <span data-ttu-id="cd9fa-636">Das Helpdesk-Personal kann die Konfiguration in Ihrem Auftrag durchführen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-636">The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="cd9fa-637">Joes Anrufe an seine Arbeitsnummer gehen zu seiner mobilen Voicemail, wenn er bei der Arbeit ist; in den meisten anderen Speicherorten scheinen die Dinge jedoch korrekt zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-637">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations.</span></span> <span data-ttu-id="cd9fa-638">Der Helpdesk-Techniker kann Joes Routingkonfiguration anzeigen und feststellt, dass Joe das gleichzeitige Klingeln auf seinem Mobiltelefon konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-638">The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone.</span></span> <span data-ttu-id="cd9fa-639">Der Techniker fragt Joe nach der mobilen Abdeckung in seinem Büro und kann feststellen, dass die gleichzeitige Klingel Regel ist, was dazu führt, dass die Anrufe an Joes Mobile Voicemail gehen, wenn seine Netzwerkabdeckung schlecht ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-639">The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="cd9fa-640">Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, für das alle Mitglieder für Teamanrufe konfiguriert sind, wenn es für Microsoft lync aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass alle seine neuen Teammitglieder hinzugefügt werden. der Administrator fügt Mike als Teamanrufgruppe für jedes Mitglied in seinem Team hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="cd9fa-641">Eine Kundendienst Praxis in der Personalabteilung von Contoso ist die Bereitstellung persönlicher Dienste für alle Anrufer seit dem ersten Anruf.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="cd9fa-642">Da alle Mitglieder der Abteilung sehr nahe beieinander sitzen, ist es für das Team sehr störend, dass alle Telefone gleichzeitig mit dem Team Anruf Klingeln.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="cd9fa-643">Um den besten Dienst bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der lync-Administrator die Funktion für die gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="cd9fa-644">Der Administrator fügt alle Abteilungsmitglieder zu einer Pickup-Gruppe hinzu und kommuniziert mit der Abteilung mit der Abhol Gruppennummer.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="cd9fa-645">Wenn Samantha von Ihrem Schreibtisch abwesend ist, merkt Joe, dass Ihr Telefon klingelt und er den Anruf von seinem Schreibtisch aus beantwortet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-646">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-646">Requirements</span></span>

<span data-ttu-id="cd9fa-647">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-647">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool.</span></span> <span data-ttu-id="cd9fa-648">UCMA 3.0 muss auf diesem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-648">UCMA 3.0 must be installed on that computer.</span></span> <span data-ttu-id="cd9fa-649">Zum Ausführen des Tools muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-649">To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="cd9fa-650">**Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="cd9fa-651">Das SEFAUTil-Tool kann nur auf einem Computer ausgeführt werden, der Teil eines vertrauenswürdigen Anwendungspools ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="cd9fa-652">Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die lync Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd9fa-653">UCMA 3.0 muss auf jedem Computer installiert sein, der zum Ausführen des SEFAUtil-Tools verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="cd9fa-654">Eine vertrauenswürdige Anwendung muss in der Topologie für das SEFAUtil-Tool definiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="cd9fa-655">Um SEFAUtil als neue vertrauenswürdige Anwendung zu definieren, verwenden Sie die lync Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd9fa-656">Bei Bedarf kann ein anderer Port verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="cd9fa-657">Die Topologie-Änderungen müssen aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="cd9fa-658">Das Aktivieren der Topologie-Änderungen kann über die lync Server-Verwaltungsshell durch Ausführen des folgenden Cmdlets erfolgen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="cd9fa-659">Installieren Sie bei Bedarf die lync Server 2013 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).</span><span class="sxs-lookup"><span data-stu-id="cd9fa-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="cd9fa-660">Stellen Sie sicher, dass die SEFAUtil ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="cd9fa-661">Führen Sie dazu das Tool über eine Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="cd9fa-662">Das Tool befindet sich standardmäßig in: "... \\Programmdateien\\Microsoft lync Server 2013\\"resketch".</span><span class="sxs-lookup"><span data-stu-id="cd9fa-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="cd9fa-663">Verwenden Sie den folgenden Befehl, um die Anrufweiterleitungseinstellungen eines Benutzers anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="cd9fa-664">Die Einstellungen für die Anrufweiterleitung des Benutzers sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="cd9fa-665">Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="cd9fa-665">Group Call Pickup</span></span>

<span data-ttu-id="cd9fa-666">Für die gruppenanrufannahme ist eine zusätzliche Konfiguration in lync Server erforderlich, damit die Funktion vollständig aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="cd9fa-667">Vor dem Zuweisen von Pickup-Gruppen zu Benutzern finden Sie in der Group Call Pickup-Produktdokumentation die Planungs-und Bereitstellungsschritte dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-668">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="cd9fa-669">Anzeigen der aktuellen Einstellungen für die Anrufverarbeitung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="cd9fa-670">Mit dem folgenden Befehl wird die Anrufbehandlung für den Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-671">In diesem Beispiel wird <STRONG>die Option/</STRONG> Tausch verwendet, um die lync Server anzugeben, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="cd9fa-672">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="cd9fa-673">Festlegen des Ziels "Anrufweiterleitung/Nein-Antwort"</span><span class="sxs-lookup"><span data-stu-id="cd9fa-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="cd9fa-674">In diesem Beispiel werden das Ziel für die Anrufweiterleitung/keine Antwort und die Ring Verzögerung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="cd9fa-675">Hier wird die Option// SEFAUtil versucht, die lync Server zu AutoErmittlung.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="cd9fa-676">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="cd9fa-677">Sofortiges Aktivieren der Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="cd9fa-678">In diesem Beispiel wird die Anrufweiterleitung sofort an einen anderen Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="cd9fa-679">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="cd9fa-680">Sofortiges Deaktivieren der Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="cd9fa-681">In diesem Beispiel wird die Anrufweiterleitung sofort deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="cd9fa-682">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="cd9fa-683">Hinzufügen eines Benutzers als Stellvertreter und Einrichten des gleichzeitigen Klingelns von Stellvertretern</span><span class="sxs-lookup"><span data-stu-id="cd9fa-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="cd9fa-684">In diesem Beispiel wird ein Benutzer als Stellvertreter hinzugefügt und das gleichzeitige Klingeln von Stellvertretern eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="cd9fa-685">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="cd9fa-686">Ändern der gleichzeitigen Klingel Regel für Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="cd9fa-687">In diesem Beispiel wird die Regel für das gleichzeitige Klingeln, die im vorherigen Beispiel festgelegt wurde, auf die verzögerte Klingel Regel geändert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="cd9fa-688">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="cd9fa-689">Entfernen der Stellvertretung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-689">Remove the Delegate</span></span>

<span data-ttu-id="cd9fa-690">In diesem Beispiel wird die Stellvertretung entfernt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-691">Wenn der letzte Stellvertreter entfernt wird, wird das Delegieren von Klingeln automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="cd9fa-692">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="cd9fa-693">Hinzufügen einer Stellvertretung und Einrichten der Regel "Anrufweiterleitung an Stellvertretungen"</span><span class="sxs-lookup"><span data-stu-id="cd9fa-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="cd9fa-694">In diesem Beispiel wird eine Stellvertretung hinzugefügt und die Regel "Anrufweiterleitung an Stellvertretungen" eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="cd9fa-695">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="cd9fa-696">Gleichzeitiges Klingeln aktivieren und Zielrufnummer festlegen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="cd9fa-697">In diesem Beispiel wird das gleichzeitige Klingeln aktiviert und eine Ziel Nummer für das gleichzeitige Klingeln festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-698">Wenn Sie die Ziel Nummer für das gleichzeitige Klingeln eines Benutzers ändern möchten, der bereits das gleichzeitige Klingeln aktiviert hat, halten Sie den Befehl mit dem/enablesimulring-Schalter an, andernfalls wird die Zielrufnummer nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="cd9fa-699">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="cd9fa-700">Gleichzeitiges Klingeln deaktivieren</span><span class="sxs-lookup"><span data-stu-id="cd9fa-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="cd9fa-701">In diesem Beispiel wird das gleichzeitige Klingeln deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="cd9fa-702">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="cd9fa-703">Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Gruppe "Team Anruf Mitglieder"</span><span class="sxs-lookup"><span data-stu-id="cd9fa-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="cd9fa-704">In diesem Beispiel wird der Teamanrufgruppe eines Benutzers ein Teammitglied hinzugefügt und das gleichzeitige Klingeln für die Teamanrufgruppe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-705">Durch das Hinzufügen eines Mitglieds zur Teamanrufgruppe eines Benutzers wird automatisch das gleichzeitige Klingeln der Einstellungen der Benutzer zu gleich seiner Teamanrufgruppe gewechselt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="cd9fa-706">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="cd9fa-707">Entfernen eines Mitglieds aus der Team anrufgruppe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="cd9fa-708">In diesem Beispiel wird ein Teammitglied der Teamanrufgruppe eines Benutzers entfernt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-709">Wenn das zu entfernende Element das einzige Mitglied der Teamanrufgruppe ist, wird das gleichzeitige Klingeln für die Teamanrufgruppe automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="cd9fa-710">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="cd9fa-711">Festlegen des verzögerten Rings auf die Team anrufgruppe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="cd9fa-712">In diesem Beispiel wird der verzögerte Ring in die Zeiteinstellung für die Teamanrufgruppe geändert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="cd9fa-713">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="cd9fa-714">Aktivieren des Team Anrufs</span><span class="sxs-lookup"><span data-stu-id="cd9fa-714">Enable Team-Call</span></span>

<span data-ttu-id="cd9fa-715">In diesem Beispiel wird der Team Aufruf für einen bestimmten Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-716">Wenn die Teamanrufgruppe des Benutzers keine Mitglieder enthält, wird die Teamanruffunktion nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="cd9fa-717">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="cd9fa-718">Team Anruf deaktivieren</span><span class="sxs-lookup"><span data-stu-id="cd9fa-718">Disable Team-Call</span></span>

<span data-ttu-id="cd9fa-719">In diesem Beispiel wird der Team Aufruf für einen bestimmten Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="cd9fa-720">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="cd9fa-721">Aktivieren der gruppenanrufannahme und Zuweisen einer Abhol Gruppe zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="cd9fa-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="cd9fa-722">In diesem Beispiel wird einem Benutzer eine Abhol Gruppe zugewiesen, und es wird eine gruppenanrufannahme aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="cd9fa-723">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="cd9fa-724">Deaktivieren der gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="cd9fa-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="cd9fa-725">In diesem Beispiel wird die gruppenanrufannahme für einen bestimmten Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-726">Wenn Sie die gruppenanrufannahme für einen Benutzer deaktivieren, wird die dem Benutzer zugewiesene Gruppennummer nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-726">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="cd9fa-727">Wenn Sie anschließend die gruppenanrufannahme für diesen Benutzer erneut aktivieren möchten, müssen Sie die Gruppennummer mit dem/enablegrouppickup-Schalter erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-727">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="cd9fa-728">SYSPrep. ps1</span><span class="sxs-lookup"><span data-stu-id="cd9fa-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-729">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-729">Description</span></span>

<span data-ttu-id="cd9fa-730">SYSPrep. ps1 ist ein Windows PowerShell Skript, mit dem die folgenden lync Server 2013 erforderlichen Komponenten auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="cd9fa-731">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="cd9fa-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="cd9fa-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="cd9fa-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="cd9fa-733">Windows PowerShell, Version 3,0</span><span class="sxs-lookup"><span data-stu-id="cd9fa-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="cd9fa-734">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="cd9fa-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="cd9fa-735">Internet Informations Server-Updates</span><span class="sxs-lookup"><span data-stu-id="cd9fa-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="cd9fa-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="cd9fa-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="cd9fa-737">Lync Server 2013 Kerndateien</span><span class="sxs-lookup"><span data-stu-id="cd9fa-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="cd9fa-738">Während der Skriptname dem System Vorbereitungs Tool für Microsoft Windows-Betriebssysteme ähnelt, sind Sie unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="cd9fa-739">Mit diesem Skript werden nur die erforderlichen Voraussetzungen für lync Server 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="cd9fa-740">Sobald diese Voraussetzungen installiert sind, kann das Windows-SYSPrep-Tool verwendet werden, um ein Abbild des Servers zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-741">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-741">Requirements</span></span>

<span data-ttu-id="cd9fa-742">Vor dem Ausführen des Skripts "SYSPrep. ps1" müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (zum Beispiel **D:\\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="cd9fa-743">Dieser Ordner muss auch eine Kopie der lync Server 2013 Dateien enthalten, insbesondere **Setup. exe.**</span><span class="sxs-lookup"><span data-stu-id="cd9fa-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="cd9fa-744">Die erforderlichen Dateien können von den folgenden Speicherorten heruntergeladen werden:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd9fa-745">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-745">Prerequisite</span></span></th>
<th><span data-ttu-id="cd9fa-746">Ort</span><span class="sxs-lookup"><span data-stu-id="cd9fa-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd9fa-747">Microsoft .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="cd9fa-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9fa-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cd9fa-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9fa-749">Windows PowerShell, Version 3,0</span><span class="sxs-lookup"><span data-stu-id="cd9fa-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9fa-750">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="cd9fa-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9fa-751">Internet Informations Server-Updates</span><span class="sxs-lookup"><span data-stu-id="cd9fa-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd9fa-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="cd9fa-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd9fa-753">Lync Server 2013 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="cd9fa-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="cd9fa-754">Kopieren von lync Server 2013 Medien</span><span class="sxs-lookup"><span data-stu-id="cd9fa-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="cd9fa-755">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd9fa-755">Parameter</span></span>

<span data-ttu-id="cd9fa-756">Der Parameter **– SetupFolder** verwendet als Argument den Verzeichnisspeicherort der erforderlichen Dateien.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-757">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-757">Examples</span></span>

<span data-ttu-id="cd9fa-758">Führen Sie den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um das Skript "SYSPrep. ps1" auszuführen und die erforderlichen Komponenten für lync Server 2013 zu installieren:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="cd9fa-759">Migration nicht zugewiesener Nummern Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="cd9fa-760">Mit dem Migrationstool für nicht zugewiesene Nummern Ankündigungen kann ein lync-Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung aus einer Quell lync Server oder einem Pool gewartet wird, zu einem Ziel lync Server oder-Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-761">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-761">Description</span></span>

<span data-ttu-id="cd9fa-762">Das Migrationstool für nicht zugewiesene Nummern Ankündigungen ist ein Windows PowerShells Skript, mit dem die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung eines Quellservers oder Pools aus gewartet wird, auf einen anderen Server oder Pool verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="cd9fa-763">Bei der Ausführung des Migrationsskripts für unassigned number Announcements werden die folgenden Vorgänge ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="cd9fa-764">Verschiebt alle Audiodateien, die von den Ankündigungen nicht zugewiesener Nummern der in dem Quellserver oder Pool gehosteten Ankündigungs Anwendung verwendet werden, in den Dateispeicher des Zielservers oder-Pools.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd9fa-765">die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="cd9fa-766">Verschiebt alle Ankündigungen für nicht zugewiesene Nummern, die für die im Quellserver oder Pool gehostete Ankündigungs Anwendung konfiguriert sind, auf den Zielserver oder-Pool.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="cd9fa-767">Weisen Sie dem Zielserver oder-Pool alle nicht zugewiesenen Nummernbereiche, die von der auf dem Quellserver oder Pool gehosteten Ankündigungs Anwendung gewartet werden, neu zu.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="cd9fa-768">Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der auf dem Quellserver oder Pool gehosteten Ankündigungs Anwendung gewartet wurden, jetzt mit der gleichen Konfiguration vom Zielserver oder-Pool aus gewartet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-769">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-769">Output</span></span>

<span data-ttu-id="cd9fa-770">Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster von lync Management Shell an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="cd9fa-771">Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die nicht zugewiesenen Nummernbereiche, die erfolgreich in das Ziel verschoben wurden, in einem operativen Formular im Ziel und die restlichen nicht zugewiesenen Nummernbereiche, die migriert werden sollen, werden in die Quelle als auch in einem operativen Formular.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-771">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form.</span></span> <span data-ttu-id="cd9fa-772">Um den Rest der Konfiguration vollständig zu migrieren, führen Sie das Skript nach dem Beheben des Fehlers erneut aus.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-772">To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="cd9fa-773">Zweck</span><span class="sxs-lookup"><span data-stu-id="cd9fa-773">Purpose</span></span>

<span data-ttu-id="cd9fa-774">Das Migrationsskript "nicht zugewiesene Nummern Ankündigungen" kann in den folgenden drei Szenarien verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="cd9fa-775">**Migrieren von Konfigurationseinstellungen zu einer neuen Version von lync Server:** Contoso wird gerade zu lync Server 2013 migriert, und im Rahmen des Migrationsprozesses möchte der lync Server Administrator die Konfiguration nicht zugewiesener Nummern, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2010-Bereitstellung in die neue lync Server 2013-Bereitstellung verschieben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="cd9fa-776">Zum Migrieren der Konfigurationseinstellungen verwendet der lync Server Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="cd9fa-777">**Rollback einer Bereitstellung von lync Server 2013 auf lync Server 2010:** Aufgrund unerwarteter Faktoren muss Contoso die Migration in die neue lync Server 2013-Bereitstellung rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="cd9fa-778">Zum Minimieren von Unterbrechungen des Diensts verwendet der lync Server Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen, um die Konfiguration von der lync Server 2013-Bereitstellung auf die lync Server 2010-Bereitstellung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="cd9fa-779">**Verschieben von Daten zwischen lync-Bereitstellungen:** Contoso ist dabei, alle Server eines Pools durch neuere Server zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="cd9fa-780">Ihre Strategie besteht darin, einen neuen lync Server 2013 Pool bereitzustellen, alle Daten aus dem alten in den neuen Pool zu verlagern und dann den alten Pool zu veraltern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="cd9fa-781">Nachdem der neue Pool bereitgestellt wurde, wird das Migrationstool für unassigned number Announcements verwendet, um die Konfiguration aus dem alten Pool in die neue zu verlagern.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-782">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-782">Requirements</span></span>

<span data-ttu-id="cd9fa-783">Die folgenden Hauptanforderungen müssen erfüllt sein, um das Tool erfolgreich auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="cd9fa-784">Das Skript muss von einem Computer aus ausgeführt werden, auf dem lync Server 2013 Management Shell installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="cd9fa-785">Die Ankündigungs Anwendung muss erfolgreich in den lync-Quell-und-Zielservern oder-Pools bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="cd9fa-786">CsAnnouncementConfiguration-Skript</span><span class="sxs-lookup"><span data-stu-id="cd9fa-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="cd9fa-787">Das CsAnnouncementConfiguration-Skript erfordert die beiden Parameter, die in der folgenden Tabelle beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="cd9fa-788">![CsAnnouncementConfiguration-Parameter.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "CsAnnouncementConfiguration-Parameter.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-789">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="cd9fa-790">Verschieben der Konfiguration nicht zugewiesener Nummern Ankündigungen von einem lync Server 2010 Pool in einen lync Server 2013 Pool</span><span class="sxs-lookup"><span data-stu-id="cd9fa-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="cd9fa-791">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2010) in den Ziel Pool (lync Server 2013) verschoben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="cd9fa-792">Verschieben der Konfiguration nicht zugewiesener Nummern Ankündigungen von einem lync Server 2013 Pool in einen lync Server 2010 Pool</span><span class="sxs-lookup"><span data-stu-id="cd9fa-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="cd9fa-793">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2013) in den Ziel Pool (lync Server 2010) verschoben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="cd9fa-794">Webconf-Daten</span><span class="sxs-lookup"><span data-stu-id="cd9fa-794">Web Conf Data</span></span>

<span data-ttu-id="cd9fa-795">Mit dem Tool "webconf Data" kann ein Administrator von lync Server 2013 Kommunikationssoftware mehr Kontrolle über die Daten haben, die den Webkonferenzen eines Organisators zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="cd9fa-796">Szenarien umfassen die Möglichkeit, die Besprechungsdaten eines bestimmten Benutzers basierend auf einem Zeitstempel Kriterium zu löschen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="cd9fa-797">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-797">Description</span></span>

<span data-ttu-id="cd9fa-798">Mit diesem Tool kann der Administrator die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="cd9fa-799">Hier finden Sie alle mit einem einzelnen Benutzer verknüpften Webkonferenz Daten.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="cd9fa-800">Löschen Sie alle Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="cd9fa-801">Löschen Sie alle Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, der älter als ein bestimmtes Datum ist.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="cd9fa-802">Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9fa-803">Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool in einen anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="cd9fa-804">Diese Funktionalität ist nun in diesem Tool für den <STRONG>MoveConferenceData</STRONG> -Parameter veraltet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="cd9fa-805">Ausführliche Informationen zu diesem Parameter finden Sie unter dem Cmdlet " <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Verschiebe-CsUser</A> ".</span><span class="sxs-lookup"><span data-stu-id="cd9fa-805">For details about this parameter, see the <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="cd9fa-806">Das Tool löscht Besprechungsdaten nur für nicht aktive Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-806">The tool deletes meeting data only for meetings that are inactive.</span></span> <span data-ttu-id="cd9fa-807">Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-807">Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="cd9fa-808">Dieses Tool muss von einem Computer aus ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-808">This tool must be run from a computer that is in the same pool as the target user.</span></span> <span data-ttu-id="cd9fa-809">Der Benutzer, dessen Besprechungsinhalts Daten von diesem Tool verwaltet werden, muss sich in demselben Benutzerpool befinden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-809">The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="cd9fa-810">Output</span><span class="sxs-lookup"><span data-stu-id="cd9fa-810">Output</span></span>

<span data-ttu-id="cd9fa-811">Dieses Tool gibt die Ergebnisse der einzelnen Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="cd9fa-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="cd9fa-812">Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdaten Ordner aus, die diesen Benutzer als Organisator haben.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="cd9fa-813">Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdaten Ordner aus, deren Daten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="cd9fa-814">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd9fa-814">Requirements</span></span>

<span data-ttu-id="cd9fa-815">Das Tool muss in demselben Pool ausgeführt werden, in dem der Organisator derzeit verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="cd9fa-816">Das Tool muss mit Administratorrechten mit Zugriff auf die Inhalts Dateispeicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="cd9fa-817">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd9fa-817">Examples</span></span>

<span data-ttu-id="cd9fa-818">In der folgenden Tabelle werden die Parameter beschrieben, von denen einige in den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="cd9fa-819">![Parameter des webconf-Datentools.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parameter des webconf-Datentools.")</span><span class="sxs-lookup"><span data-stu-id="cd9fa-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="cd9fa-820">Das obige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-820">The preceding example shows how a query command would work.</span></span> <span data-ttu-id="cd9fa-821">Bei der Ausgabe eines solchen Befehls handelt es sich um eine Liste aller Besprechungsinhalts Ordner, die von diesem Tool betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-821">The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="cd9fa-822">Das vorangehende ist ein Beispiel für einen DELETE-Befehl.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-822">The preceding is an example of a delete command.</span></span> <span data-ttu-id="cd9fa-823">Mit dem Befehl Delete werden alle inaktiven Besprechungs Ordner von diesem Benutzer entfernt.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-823">The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="cd9fa-824">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cd9fa-824">Summary</span></span>

<span data-ttu-id="cd9fa-825">Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenz Besprechungsdaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="cd9fa-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

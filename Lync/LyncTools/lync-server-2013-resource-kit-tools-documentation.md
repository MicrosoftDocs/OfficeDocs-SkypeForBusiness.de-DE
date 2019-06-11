---
title: Dokumentation zur lync Server 2013 Resource Kit-Tools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589285948bd9d3f82fae0ed7c7916029716514f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a><span data-ttu-id="00353-102">Dokumentation zur lync Server 2013 Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="00353-102">Lync Server 2013 Resource Kit Tools Documentation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00353-103">_**Letztes Änderungsdatum des Themas:** 2014-01-09_</span><span class="sxs-lookup"><span data-stu-id="00353-103">_**Topic Last Modified:** 2014-01-09_</span></span>

<span data-ttu-id="00353-104">In diesem Thema werden die Tools beschrieben, die Teil des lync Server 2013 Resource Kits sind, einschließlich des Zwecks der einzelnen Tools und Beispiele für deren Verwendung. Die lync Server 2013, Resource Kit-Tools helfen Ihnen, Routineaufgaben einfacher für IT-Administratoren zu machen, die lync Server 2013 bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="00353-104">This topic describes the tools that are part of the Lync Server 2013 Resource Kit, including the purpose of each tool, and examples of its use.The Lync Server 2013, Resource Kit Tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="00353-105">Beispielsweise kann das Tool **Web Conf Data** verwendet werden, um bequem Daten zu steuern, die während einer Onlinebesprechung von Benutzern hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="00353-105">For example, the **Web Conf Data** tool can be used to easily control data that is uploaded by users during an online meeting.</span></span> <span data-ttu-id="00353-106">Mithilfe des **SEFAUtil**-Tools können Sie Stellvertretungsanrufweiterleitung und -beantwortung für Benutzer einrichten.</span><span class="sxs-lookup"><span data-stu-id="00353-106">The **SEFAUtil** tool can be used to set up delegate call forwarding and answering for users.</span></span> <span data-ttu-id="00353-107">Wir empfehlen IT-Administratoren, diese Tools zu verwenden, um lync Server 2013 effektiver zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="00353-107">We encourage IT administrators to use these tools to more effectively manage Lync Server 2013.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="00353-108">Installation der Resource Kit-Tools</span><span class="sxs-lookup"><span data-stu-id="00353-108">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="00353-109">Zum Installieren der lync Server 2013, Resource Kit-Tools, laden Sie **OCSReskit. msi**herunter.</span><span class="sxs-lookup"><span data-stu-id="00353-109">To install the Lync Server 2013, Resource Kit Tools, download **OCSReskit.msi**.</span></span> <span data-ttu-id="00353-110">Sie können das Resource Kit Tools-Installationsprogramm aus dem Download Center [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429)unter herunterladen.</span><span class="sxs-lookup"><span data-stu-id="00353-110">You can download the Resource Kit Tools installer from the Download Center at [http://go.microsoft.com/fwlink/p/?LinkID=330429](http://go.microsoft.com/fwlink/p/?linkid=330429).</span></span>

<span data-ttu-id="00353-111">Führen Sie \*\*OCSResKit.msi \*\* aus, um eine einfache Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="00353-111">Run **OCSResKit.msi** to do a simple installation.</span></span> <span data-ttu-id="00353-112">Die MSI-Datei installiert alle Tools im folgenden Pfad: **% Program Files%\\Microsoft lync Server 2013\\**-reskit.</span><span class="sxs-lookup"><span data-stu-id="00353-112">The .msi installs all the tools in the following path: **%Program Files%\\Microsoft Lync Server 2013\\ResKit**.</span></span> <span data-ttu-id="00353-113">Tools, bei denen es sich um eigenständige ausführbare Dateien handelt, befinden sich in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="00353-113">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="00353-114">Tools, die auch Dateien enthalten, befinden sich in ihren eigenen Unterordnern.</span><span class="sxs-lookup"><span data-stu-id="00353-114">Tools that also have files are in their own subfolders.</span></span>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="00353-115">Unterstützte Umgebungen</span><span class="sxs-lookup"><span data-stu-id="00353-115">Supported Environments</span></span>

<span data-ttu-id="00353-116">Um eine optimale Leistung zu erzielen, sollten die lync Server 2013, Resource Kit-Tools in der gleichen Umgebung und mit den gleichen Spezifikationen installiert werden, die für lync Server 2013 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="00353-116">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="00353-117">Resource Kit-Tools – Übersicht</span><span class="sxs-lookup"><span data-stu-id="00353-117">Resource Kit Tools Overview</span></span>

<span data-ttu-id="00353-118">In der folgenden Liste werden die Tools beschrieben, die im lync Server 2013 Resource Kit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-118">The following list describes the tools that are provided in the Lync Server 2013 Resource Kit.</span></span> <span data-ttu-id="00353-119">Eine Beschreibung der einzelnen Tools, einschließlich der Anforderungen und der Beispiel Verwendung, wird im folgenden Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="00353-119">A description of each tool, including the requirements and example usage is covered in the following section.</span></span>

  - <span data-ttu-id="00353-120">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="00353-120">ABSConfig</span></span>

  - <span data-ttu-id="00353-121">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="00353-121">Bandwidth Policy Service Monitor</span></span>

  - <span data-ttu-id="00353-122">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="00353-122">Bandwidth Utilization Analyzer</span></span>

  - <span data-ttu-id="00353-123">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="00353-123">Call Parkometer</span></span>

  - <span data-ttu-id="00353-124">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="00353-124">CleanupStorageServiceData</span></span>

  - <span data-ttu-id="00353-125">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="00353-125">DBAnalyze</span></span>

  - <span data-ttu-id="00353-126">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="00353-126">ImportStorageServiceData</span></span>

  - <span data-ttu-id="00353-127">LCSSync</span><span class="sxs-lookup"><span data-stu-id="00353-127">LCSSync</span></span>

  - <span data-ttu-id="00353-128">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="00353-128">LookupUserConsole</span></span>

  - <span data-ttu-id="00353-129">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="00353-129">MsTurnPing</span></span>

  - <span data-ttu-id="00353-130">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="00353-130">Network Configuration Viewer</span></span>

  - <span data-ttu-id="00353-131">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="00353-131">Response Group Agent Live</span></span>

  - <span data-ttu-id="00353-132">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="00353-132">SEFAUtil</span></span>

  - <span data-ttu-id="00353-133">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="00353-133">SYSPrep.ps1</span></span>

  - <span data-ttu-id="00353-134">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="00353-134">Unassigned Number Announcements Migration</span></span>

  - <span data-ttu-id="00353-135">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="00353-135">Web Conf Data</span></span>

</div>

<div>

## <a name="absconfig"></a><span data-ttu-id="00353-136">ABSConfig</span><span class="sxs-lookup"><span data-stu-id="00353-136">ABSConfig</span></span>

<span data-ttu-id="00353-137">Das Adressbuchdienst-Konfigurationstool (ABSConfig) ist ein Verwaltungstool, mit dem Administratoren die Konfiguration des Adressbuchdiensts in lync Server 2013 anpassen können.</span><span class="sxs-lookup"><span data-stu-id="00353-137">The Address Book Service Configuration tool (ABSConfig) is an administrative tool that helps administrators customize Address Book Service configuration in Lync Server 2013.</span></span> <span data-ttu-id="00353-138">Mit diesem Tool können lync Server 2013-Administratoren auch die Standardeinstellungen für den Adressbuchdienst wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="00353-138">This tool also enables Lync Server 2013 administrators to restore the default Address Book Service settings.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-139">Description</span></span>

<span data-ttu-id="00353-140">ABSConfig ist eine grafische Benutzeroberflächenanwendung, mit der Administratoren Active Directory-Domänendienst Attribute konfigurieren können, die mit dem Adressbuchdienst verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="00353-140">ABSConfig is a graphical user interface application that enables administrators to configure Active Directory Domain Services attributes that are related to Address Book Service.</span></span>

<span data-ttu-id="00353-141">Dies sind die primären Verwendungsszenarien für das Tool:</span><span class="sxs-lookup"><span data-stu-id="00353-141">The primary scenarios for the tool are the following:</span></span>

  - <span data-ttu-id="00353-142">So können Administratoren Attribute in den Active Directory-Domänendiensten den Attributen für lync Server 2013 zuordnen.</span><span class="sxs-lookup"><span data-stu-id="00353-142">To enable administrators to map attributes in Active Directory Domain Services to the attributes for Lync Server 2013.</span></span>

  - <span data-ttu-id="00353-143">Administratoren das Angeben des Attributs in Active Directory Domain Services ermöglichen, das in die Adressbuchdienst-Dateien aufgenommen oder aus diesen ausgeschlossen werden soll</span><span class="sxs-lookup"><span data-stu-id="00353-143">To enable administrators to specify the Active Directory Domain Services attribute to be included or excluded in the Address Book Service files.</span></span>

  - <span data-ttu-id="00353-144">Administratoren das Wiederherstellen der Standardeinstellungen des Adressbuchdiensts ermöglichen</span><span class="sxs-lookup"><span data-stu-id="00353-144">To enable administrators to restore default Address Book Service settings.</span></span>

<span data-ttu-id="00353-145">Das ABSConfig-Tool kann mithilfe der Datei "ABSConfig. exe" gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="00353-145">The ABSConfig tool can be started by using the absConfig.exe file.</span></span> <span data-ttu-id="00353-146">Das Tool wird auf der Registerkarte **Attribute konfigurieren** geöffnet. Diese Tabelle enthält Optionen zum Zuordnen von Active Directory-Domänendienst Attributen zu den Attributfeldern für lync Server 2013 und zum Angeben der Benutzer, die in Adressbuchdienst Dateien basierend auf bestimmten Attribut Filtern enthalten oder ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00353-146">The tool opens to the **Configure Attributes** tab. This table has options to map Active Directory Domain Services attributes to the attribute fields for Lync Server 2013 and to specify which users to include or exclude in Address Book Service files based on specific attribute filters.</span></span> <span data-ttu-id="00353-147">Darüber hinaus gibt es Optionen, um den Wert der Telefonnummer anzupassen, der in die Adressbuchdatei aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="00353-147">It also has options to customize which value of the phone number to be included in the Address Book file.</span></span> <span data-ttu-id="00353-148">Mit der Option **Standard wiederherstellen** können Administratoren die Einstellungen des Adressbuchdiensts auf Standardwerte zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="00353-148">The **Restore Defaults** option enables administrators to restore Address Book Service settings to default values.</span></span>

</div>

<div>

## <a name="changes-from-lync-server-2010"></a><span data-ttu-id="00353-149">Änderungen von lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="00353-149">Changes from Lync Server 2010</span></span>

<span data-ttu-id="00353-150">Im lync Server 2013 ABS-Konfigurationstool können Attribute (Zeilen) entfernt werden, indem Sie das Kontrollkästchen "aktivieren" für das Attribut deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="00353-150">In Lync Server 2013 ABS Configuration tool, attributes (rows) may be removed by unchecking the “enable” checkbox for the attribute.</span></span> <span data-ttu-id="00353-151">Dies hat dieselbe Wirkung wie das Löschen der Zeile in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="00353-151">This has the same effect as deleting the row in Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-152">Das Kontrollkästchen "aktivieren" befindet sich in der äußerst rechten Spalte. Möglicherweise müssen Sie nach rechts scrollen, um die Spalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-152">The enable checkbox is in the far right column; you may need to scroll right to see the column</span></span>



</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-153">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-153">Output</span></span>

<span data-ttu-id="00353-154">ABSConfig speichert die Konfiguration des Adressbuchdiensts in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="00353-154">ABSConfig stores the Address Book Service configuration in the database.</span></span>

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-155">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-155">Purpose</span></span>

<span data-ttu-id="00353-156">ABSConfig bietet eine schnelle und einfache Möglichkeit zum Anpassen des lync Server 2013-Adressbuchdiensts.</span><span class="sxs-lookup"><span data-stu-id="00353-156">ABSConfig provides a quick and easy way to customize Lync Server 2013 Address Book Service.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-157">Requirements</span></span>

<div>

## <a name="computer"></a><span data-ttu-id="00353-158">Computer</span><span class="sxs-lookup"><span data-stu-id="00353-158">Computer</span></span>

<span data-ttu-id="00353-159">ABSConfig kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-159">ABSConfig can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span> <span data-ttu-id="00353-160">Im Fall von lync Server 2013, Enterprise Edition, kann dieses Tool auf allen Front-End-Servern ausgeführt werden, auf denen der Adressbuchdienst während des Setups aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-160">In the case of Lync Server 2013, Enterprise Edition, this tool can be run on any Front End servers that have the Address Book Service enabled during setup.</span></span>

</div>

<div>

## <a name="network"></a><span data-ttu-id="00353-161">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="00353-161">Network</span></span>

<span data-ttu-id="00353-162">Der Computer sollte in der Lage sein, eine Verbindung mit dem Front-End-Pool und der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="00353-162">The computer should be able to connect to the Front End pool and back-end database.</span></span>

</div>

<div>

## <a name="software"></a><span data-ttu-id="00353-163">Software</span><span class="sxs-lookup"><span data-stu-id="00353-163">Software</span></span>

<span data-ttu-id="00353-164">Die folgenden Softwarekomponenten müssen vor der Ausführung des ABSConfig-Tools installiert werden:</span><span class="sxs-lookup"><span data-stu-id="00353-164">The following software components must be installed before running the ABSConfig tool:</span></span>

  - <span data-ttu-id="00353-165">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00353-165">Microsoft Lync Server 2013</span></span>

</div>

<div>

## <a name="users"></a><span data-ttu-id="00353-166">Nutzer</span><span class="sxs-lookup"><span data-stu-id="00353-166">Users</span></span>

<span data-ttu-id="00353-167">Administratoren, die über die erforderlichen Berechtigungen verfügen, um die lync Server 2013-Bereitstellung zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="00353-167">Administrators who have the permissions required to update the Lync Server 2013 deployment.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-168">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-168">Examples</span></span>

<span data-ttu-id="00353-p109">ABSConfig kann durch Eingeben von **ABSConfig.exe** an einer Eingabeaufforderung gestartet werden. Unten sehen Sie eine Abbildung der Benutzeroberfläche des ABSConfig-Tools.</span><span class="sxs-lookup"><span data-stu-id="00353-p109">ABSConfig can be started by typing **ABSConfig.exe** at a command prompt. Shown below is the ABSConfig tool user interface.</span></span>

<span data-ttu-id="00353-171">![Das Tool "ABSConfig. exe".] (images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Das Tool \"ABSConfig. exe\".")</span><span class="sxs-lookup"><span data-stu-id="00353-171">![The ABSConfig.exe tool.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "The ABSConfig.exe tool.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-172">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-172">Summary</span></span>

<span data-ttu-id="00353-173">Das ABSConfig-Tool bietet Administratoren ein schnelles und einfach zu Bedientool zum Anpassen des lync Server 2013-Adressbuchdiensts.</span><span class="sxs-lookup"><span data-stu-id="00353-173">The ABSConfig tool provides administrators a quick and easy to use tool to customize Lync Server 2013 Address Book Service.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a><span data-ttu-id="00353-174">Bandwidth Policy Service Monitor</span><span class="sxs-lookup"><span data-stu-id="00353-174">Bandwidth Policy Service Monitor</span></span>

<span data-ttu-id="00353-175">Mit dem Tool Bandwidth Policy Service Monitor können Administratoren eine Liste der folgenden Elemente anzeigen:</span><span class="sxs-lookup"><span data-stu-id="00353-175">The Bandwidth Policy Service Monitor tool is intended to allow administrators to view a list of the following:</span></span>

1.  <span data-ttu-id="00353-176">Alle konfigurierten lync Server 2013-Bandbreitenrichtlinien Dienste (Authentifizierung und Kern) in der Topologie</span><span class="sxs-lookup"><span data-stu-id="00353-176">All the configured Lync Server 2013 Bandwidth Policy services (Authentication and Core) in the topology</span></span>

2.  <span data-ttu-id="00353-177">Die Verbindungen, die jeder Dienst mit anderen Bandbreiten-Richtliniendiensten und Edgeservern herstellt</span><span class="sxs-lookup"><span data-stu-id="00353-177">The connections that each service makes to other Bandwidth Policy services and to the Edge servers</span></span>

3.  <span data-ttu-id="00353-178">Alle Verbindungen, die im Netzwerkkonfigurationsdokument konfiguriert sind, und die von den einzelnen Bandbreiten-Richtliniendiensten gemeldete Echtzeit-Bandbreitennutzung</span><span class="sxs-lookup"><span data-stu-id="00353-178">All the links that are configured in the Network configuration document and real-time bandwidth usage as reported by each of the Bandwidth Policy services</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-179">Description</span></span>

<span data-ttu-id="00353-p110">Das Tool Bandwidth Policy Service Monitor ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Administratoren starten das Tool durch Ausführen der Datei „PDPMonUI.exe“.</span><span class="sxs-lookup"><span data-stu-id="00353-p110">The Bandwidth Policy Service Monitor tool is implemented as a GUI-based application. Administrators start the tool by running PDPMonUI.exe.</span></span>

<span data-ttu-id="00353-p111">Wenn das Tool gestartet wird, versucht es, die Liste der Bandbreiten-Richtliniendienste in der Topologie zu ermitteln. Nach Abschluss der anfänglichen Aktualisierung wird der linke Bereich im Fenster mit einer Liste von Diensten aufgefüllt, die nach den Clustern gruppiert sind, zu denen sie gehören.</span><span class="sxs-lookup"><span data-stu-id="00353-p111">When the tool starts, it attempts to discover the list of Bandwidth Policy services in the topology. After the initial update is done, the pane to the left of the window is populated with a list of services that are grouped by the clusters that they belong to.</span></span>

<span data-ttu-id="00353-p112">Wenn Administratoren einen bestimmten Bandbreiten-Richtliniendienst auswählen, werden im rechten Bereich die Informationen zu dem jeweiligen Dienst angezeigt. Dieser Bereich enthält außerdem zwei Hauptregisterkarten, auf denen Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-p112">When administrators select a particular Bandwidth Policy Service, the pane on the right displays the information about that particular service. That pane also has two main tabs that display information.</span></span>

<div>

## <a name="machine-info-tab"></a><span data-ttu-id="00353-186">Registerkarte „Machine Info“</span><span class="sxs-lookup"><span data-stu-id="00353-186">Machine Info Tab</span></span>

<span data-ttu-id="00353-187">Auf der Registerkarte **Machine Info** werden die Details des ausgewählten Bandbreiten-Richtliniendiensts angezeigt sowie die Liste und die Zustände aller Verbindungen, die der ausgewählte Bandbreiten-Richtliniendienst mit anderen Diensten herstellt.</span><span class="sxs-lookup"><span data-stu-id="00353-187">The **Machine Info** tab shows the details of the Bandwidth Policy Service that is selected and the list and state of all the connections that are made by the selected Bandwidth Policy Service to other services.</span></span>

</div>

<div>

## <a name="topology-info-tab"></a><span data-ttu-id="00353-188">Registerkarte „Topology Info“</span><span class="sxs-lookup"><span data-stu-id="00353-188">Topology Info Tab</span></span>

<span data-ttu-id="00353-p113">Auf der Registerkarte **Topology Info** wird eine Liste aller Verbindungen angezeigt, die in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Für jede Verbindung wird die Bandbreitenkapazität für Audio und Video angezeigt. Zusätzlich wird die zurzeit verwendete Bandbreite in KB/s und als Prozentsatz der Kapazität angezeigt. Das Tool verwendet Farbcodierungen zum Hervorheben von Verbindungen, deren Nutzung fast der Kapazität entspricht. So können Administratoren solche Verbindungen schnell erkennen.</span><span class="sxs-lookup"><span data-stu-id="00353-p113">The **Topology Info** tab shows a list of all the links that are configured in the Network configuration settings. For each link, the audio and video bandwidth capacity is displayed. Additionally, the currently utilized bandwidth is displayed, both in Kbps and as a percentage of the capacity. The tool uses color-coding to highlight links that have utilization that is close to the capacity—this allows administrators to quickly isolate such links.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-p114"> Wenn es beim Herstellen einer Verbindung mit einem der konfigurierten Bandbreiten-Richtliniendienste zu einem Fehler im Tool Bandwidth Policy Service Monitor kommt, werden die Informationen auf den Registerkarten <STRONG>Machine Info</STRONG> und <STRONG>Topology Info</STRONG> nicht aufgefüllt. Es ist aber möglich, dass das Tool anfangs eine Verbindung mit dem Dienst herstellt, die dann später verloren geht. In solchen Fällen werden Administratoren eventuell veraltete Informationen angezeigt. Beide Registerkarten enthalten einen Zeitstempel <STRONG>Last Updated</STRONG>, mit dessen Hilfe Administratoren bestimmen können, wann die Daten für einen bestimmten Bandbreiten-Richtliniendienst zum letzten Mal aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="00353-p114">If the Bandwidth Policy Service Monitor tool experiences failure when it connects to any of the configured Bandwidth Policy services, the information in the <STRONG>Machine Info</STRONG> and the <STRONG>Topology Info</STRONG> tabs won’t be populated. However, it is possible that the tool might connect initially but subsequently lose its connection to the service. In such cases, administrators might see outdated information. There is a <STRONG>Last Updated</STRONG> time stamp on each of the tabs that can allow administrators to see when the data was last updated for a particular Bandwidth Policy Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-197">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-197">Output</span></span>

<span data-ttu-id="00353-198">Es gibt keine Befehlszeilenausgabe. Die Programmausgabe erfolgt auf der grafischen Hauptbenutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="00353-198">There is no command-line output; the program output is contained within the main graphical user interface (GUI).</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-199">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-199">Purpose</span></span>

<span data-ttu-id="00353-p115">Das Tool Bandwidth Policy Service Monitor soll Administratoren Einblick in den Zustand jedes Bandbreiten-Richtliniendiensts zu verschaffen, der in der Topologie definiert ist. Zusätzlich können Administratoren die Echtzeit-Bandbreitennutzung für alle Verbindungen anzeigen, die im Netzwerkkonfigurationsdokument definiert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-p115">The purpose of the Bandwidth Policy Service Monitor tool is to allow administrators visibility into the state of each of the Bandwidth Policy services that are defined in the topology. In addition, administrators can see real-time bandwidth usage for all the links that are defined in the Network configuration document.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-202">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-202">Requirements</span></span>

<span data-ttu-id="00353-203">Das Tool für bandbreitenrichtliniendienst Monitor muss auf einem Computer ausgeführt werden, der Teil der lync Server-Topologie ist.</span><span class="sxs-lookup"><span data-stu-id="00353-203">The Bandwidth Policy Service Monitor tool needs to be run on a computer that is part of the Lync Server topology.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-204">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-204">Summary</span></span>

<span data-ttu-id="00353-205">Das Tool Bandwidth Policy Service Monitor kann eine wertvolle Ressource für Administratoren sein, um den Zustand aller Bandbreiten-Richtliniendienste in der Topologie untersuchen zu können. Wichtiger noch ist, dass die Echtzeit-Bandbreitenauslastung für die Verbindungen ermittelt werden kann, die in den Netzwerkkonfigurationseinstellungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-205">The Bandwidth Policy Service Monitor tool can be a valuable resource to administrators so they can inspect the state of all the Bandwidth Policy services in the topology—and more importantly—they can obtain real-time bandwidth utilization for the links that are defined in the Network configuration settings.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a><span data-ttu-id="00353-206">Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="00353-206">Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="00353-p116">Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Muster des Bandbreitenverbrauchs analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="00353-p116">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network. These reports can be used to understand the current bandwidth consumption pattern and to aid in bandwidth capacity planning.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-209">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-209">Description</span></span>

<span data-ttu-id="00353-p117">Bandwidth Utilization Analyzer ist als Anwendung mit grafischer Benutzeroberfläche implementiert. Dieses Tool erzeugt Berichte speziell für die Audionutzung über das Netzwerk und hilft bei der Kapazitätsplanung. Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="00353-p117">Bandwidth Utilization Analyzer is implemented as a GUI-based application. This tool generates reports specifically for audio utilization across the network and helps with capacity planning. It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-213">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-213">Output</span></span>

<span data-ttu-id="00353-214">Bandwidth Utilization Analyzer bietet grafische Diagramme der Bandbreitenkapazität und -auslastung durch Audio für alle WAN-Verbindungen, die im System konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-214">Bandwidth Utilization Analyzer provides graphic al plots of bandwidth capacity and utilization for audio for all the WAN links that are configured in the system.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-215">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-215">Purpose</span></span>

<span data-ttu-id="00353-p118">Bei allen VoIP- und Videobereitstellungen ist es von entscheidender Bedeutung, Trends der Bandbreitenauslastung durch Mediendatenverkehr im Unternehmensnetzwerk zu überwachen und zu verstehen. Genau dies ermöglicht das Tool Bandwidth Utilization Analyzer Administratoren. Das Tool bietet folgende Funktionen:</span><span class="sxs-lookup"><span data-stu-id="00353-p118">In any voice and video deployment, it’s critical to monitor and understand the trend of bandwidth utilization of media traffic across the enterprise network. The Bandwidth Utilization Analyzer tool allows an administrator to achieve just that. This tool does the following:</span></span>

  - <span data-ttu-id="00353-219">Erzeugung spezifischer Berichte für die Audionutzung über das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="00353-219">Generates specific reports for audio utilization across the network</span></span>

  - <span data-ttu-id="00353-220">Hilfe bei einer effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="00353-220">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="00353-221">Bandwidth Utilization Analyzer kann aus Bandbreitenkapazitäts- und -auslastungsberichten die folgenden grafischen Diagramme generieren:</span><span class="sxs-lookup"><span data-stu-id="00353-221">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and utilization reports; they are as follows:</span></span>

  - <span data-ttu-id="00353-222">Alle WAN-Verbindungen im Unternehmensnetzwerk</span><span class="sxs-lookup"><span data-stu-id="00353-222">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="00353-223">Gefiltert nach ausgewählten WAN-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="00353-223">Filtered by selected WAN links that have been chosen</span></span>

  - <span data-ttu-id="00353-224">Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben</span><span class="sxs-lookup"><span data-stu-id="00353-224">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="00353-225">Gefiltert nach WAN-Verbindungen, die nicht die gesamte bereitgestellte Bandbreite nutzen</span><span class="sxs-lookup"><span data-stu-id="00353-225">Filtered by WAN links that have been under-utilizing the provisioned bandwidth</span></span>

  - <span data-ttu-id="00353-226">Gefiltert nach WAN-Verbindungen, die kritische Grenzwerte erreicht haben (eine Bandbreitenauslastung von mehr als 90 % der Bandbreitenkapazität der WAN-Verbindung)</span><span class="sxs-lookup"><span data-stu-id="00353-226">Filter by WAN links that have been reaching critical levels (a bandwidth utilization that is greater than 90% of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="00353-227">Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts</span><span class="sxs-lookup"><span data-stu-id="00353-227">Filtered by WAN link type—network-site links, interregional links, and links within a site</span></span>

  - <span data-ttu-id="00353-228">Gefiltert nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="00353-228">Filtered by network region</span></span>

<div>

## <a name="applications"></a><span data-ttu-id="00353-229">Anwendungen</span><span class="sxs-lookup"><span data-stu-id="00353-229">Applications</span></span>

<span data-ttu-id="00353-230">Bandwidth Utilization Analyzer besteht aus den zwei folgenden Anwendungen (Tools):</span><span class="sxs-lookup"><span data-stu-id="00353-230">Bandwidth Utilization Analyzer has the following two applications (tools):</span></span>

  - <span data-ttu-id="00353-231">**WanLinkLogCollector. exe**   mit diesem Tool kann der Benutzer die erforderlichen Informationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="00353-231">**WanLinkLogCollector.exe**   This tool enables its user to input the required information.</span></span>

  - <span data-ttu-id="00353-232">**BandwidthUtilizationAnalyzer. xlsm**  ein Microsoft Excel-Kalkulationstabellen-softwarebericht wird automatisch von WanLinkLogCollector. exe gestartet.</span><span class="sxs-lookup"><span data-stu-id="00353-232">**BandwidthUtilizationAnalyzer.xlsm**  A Microsoft Excel spreadsheet software report is automatically launched by WanLinkLogCollector.exe.</span></span> <span data-ttu-id="00353-233">Mit dieser Anwendung können Benutzer, wie später in diesem Artikel gezeigt, Filter auf den Bericht anwenden.</span><span class="sxs-lookup"><span data-stu-id="00353-233">This application allows the user to apply filters to the report as shown later in this article.</span></span>

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a><span data-ttu-id="00353-234">Phasen der Verwendung von Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="00353-234">Phases of Using Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="00353-235">Es gibt zwei Phasen bei der Verwendung von Bandwidth Utilization Analyzer:</span><span class="sxs-lookup"><span data-stu-id="00353-235">There are two phases when using Bandwidth Utilization Analyzer:</span></span>

  - <span data-ttu-id="00353-236">Erfassen von Protokollen mithilfe von „WanLinkLogCollector.exe“</span><span class="sxs-lookup"><span data-stu-id="00353-236">Collect logs, which is performed by using WanLinkLogCollector.exe</span></span>

  - <span data-ttu-id="00353-237">Anpassen von Berichten mithilfe von „BandwidthUtilizationAnalyzer.xlsm“</span><span class="sxs-lookup"><span data-stu-id="00353-237">Customize reports, which is performed by using BandwidthUtilizationAnalyzer.xlsm</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="00353-238">„BandwidthUtilizationAnalyzer.xlsm“ sollte auf keinen Fall manuell von Endbenutzern gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="00353-238">We strongly recommend that BandwidthUtilizationAnalyzer.xlsm not be manually launched by end users.</span></span>



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a><span data-ttu-id="00353-239">Starten von Bandwidth Utilization Analyzer</span><span class="sxs-lookup"><span data-stu-id="00353-239">Starting Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="00353-240">Starten Sie „WanLinkLogCollector.exe“ an der Eingabeaufforderung oder mithilfe von Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="00353-240">Start WanLinkLogCollector.exe at the command prompt or by using Windows Explorer.</span></span>

<span data-ttu-id="00353-241">**Verwenden von „WanLinkLogCollector.exe“**</span><span class="sxs-lookup"><span data-stu-id="00353-241">**Using WanLinkLogCollector.exe**</span></span>

<span data-ttu-id="00353-242">„WanLinkLogCollector.exe“ wird in drei Schritten verwendet:</span><span class="sxs-lookup"><span data-stu-id="00353-242">There are three steps to using WanLinkLogCollector.exe:</span></span>

1.  <span data-ttu-id="00353-243">**Protokollieren der Zeitachse**   geben Sie die Zeitachse an, für die der Bericht generiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="00353-243">**Log the timeline**   Provide the timeline that the report needs to be generated for</span></span>

2.  <span data-ttu-id="00353-244">**Angeben der Dateiverzeichnisse**   zur Bereitstellung von Dateispeicherort Informationen</span><span class="sxs-lookup"><span data-stu-id="00353-244">**Specify the file directories**   Provide file location information</span></span>

3.  <span data-ttu-id="00353-245">**Sammeln der Protokolle und Starten der Berichtsanzeige**  führen Sie den Befehl aus, um den Bericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="00353-245">**Collect the logs and launch the report viewer**  Execute the command to generate the report</span></span>

<div>

## <a name="step-1---log-the-timeline"></a><span data-ttu-id="00353-246">Schritt 1 – Protokollieren des Zeitraums</span><span class="sxs-lookup"><span data-stu-id="00353-246">Step 1 - Log the timeline</span></span>

<span data-ttu-id="00353-247">Durch die Protokollierung des Zeitraums können die Benutzer des Tools, wie in der Abbildung unten dargestellt, Folgendes angeben. </span><span class="sxs-lookup"><span data-stu-id="00353-247">Logging the timeline allows the tool user to specify the following as shown in the figure below.</span></span>

1.  <span data-ttu-id="00353-248">**Startdatum** Dies ist das Startdatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 1. August 2010.</span><span class="sxs-lookup"><span data-stu-id="00353-248">**Start date** This is the start date of the timeline that the report is to be generated for; for example, August 1, 2010.</span></span>

2.  <span data-ttu-id="00353-249">**Enddatum** Dies ist das Enddatum des Zeitraums, für den der Bericht generiert werden soll, beispielsweise 30. September 2010.</span><span class="sxs-lookup"><span data-stu-id="00353-249">**End date** This is the end date of the timeline that the report is to be generated for; for example, September 30, 2010.</span></span>
    
    <span data-ttu-id="00353-250">![Anfangs-und Endtermine in der Bandbreitennutzung A] (images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Anfangs-und Endtermine in der Bandbreitennutzung A")</span><span class="sxs-lookup"><span data-stu-id="00353-250">![Start and End dates in the Bandwidth Utilization A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Start and End dates in the Bandwidth Utilization A")</span></span>  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a><span data-ttu-id="00353-251">Schritt 2 – Angeben der Dateiverzeichnisse</span><span class="sxs-lookup"><span data-stu-id="00353-251">Step 2 - Specify the file directories</span></span>

<span data-ttu-id="00353-252">Die folgenden Dateiverzeichnisse können von den Benutzern wie gezeigt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="00353-252">The following file directories can be specified by the user as shown.</span></span>

  - <span data-ttu-id="00353-253">**Speicherort für Server Protokolldateien** Der Speicherort des Ordners, in dem die Bandbreitenrichtlinien Serverprotokolle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-253">**Server log files location** The folder location where Bandwidth policy server logs are stored.</span></span> <span data-ttu-id="00353-254">Dies ist normal \<erweise in\>\\\<der Fileserver\>\\-\\Auswahl von FE AppServerFiles PDP.</span><span class="sxs-lookup"><span data-stu-id="00353-254">This is typically in \<fileserver\>\\\<choice of FE\>\\AppServerFiles\\PDP.</span></span>

  - <span data-ttu-id="00353-255">**Speicherort für temporären Dateispeicher** Der Speicherort der temporären Datei, in dem zwischen Dateien gespeichert werden, während der Bericht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="00353-255">**Temporary file storage location** The temporary file location where intermediate files are stored while the report is being generated.</span></span>

<span data-ttu-id="00353-256">![Dateiverzeichnisse in der Bandbreitennutzung Anal] (images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Dateiverzeichnisse in der Bandbreitennutzung Anal")</span><span class="sxs-lookup"><span data-stu-id="00353-256">![File directories in the Bandwidth Utilization Anal](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "File directories in the Bandwidth Utilization Anal")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-257">Stellen Sie sicher, dass den Benutzern des Tools ausreichender Dateizugriff auf den Speicherort der Serverprotokolle und der temporären Dateien gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="00353-257">Ensure that sufficient file access to the server logs and the temporary file store folder is provided to the tool user.</span></span>



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a><span data-ttu-id="00353-258">Schritt 3 – Erfassen der Protokolle und Starten der Berichtanzeige</span><span class="sxs-lookup"><span data-stu-id="00353-258">Step 3 - Collect the logs and start the report viewer</span></span>

<span data-ttu-id="00353-p121">Um die Protokolle zu erfassen und die Berichtanzeige zu starten, klicken Sie, wie unten gezeigt, auf **Execute**. In diesem Schritt werden die erforderlichen Daten erfasst.</span><span class="sxs-lookup"><span data-stu-id="00353-p121">To collect the logs and start the report viewer, click **Execute** as shown below. This step collects the required data.</span></span>

<span data-ttu-id="00353-261">![Sammeln von Daten in der Bandbreitennutzung Analy] (images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Sammeln von Daten in der Bandbreitennutzung Analy")</span><span class="sxs-lookup"><span data-stu-id="00353-261">![Collecting data in the Bandwidth Utilization Analy](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Collecting data in the Bandwidth Utilization Analy")</span></span>

<span data-ttu-id="00353-262">Nach erfolgreicher Überprüfung der Eingabe wird die unten wiedergegebene Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-262">When the input validation is successful, the message shown below is displayed.</span></span>

<span data-ttu-id="00353-263">![Protokolliert die gesammelte Benachrichtigung in der Bandbreiten] -utili (images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Protokolliert die gesammelte Benachrichtigung in der Bandbreiten") -utili</span><span class="sxs-lookup"><span data-stu-id="00353-263">![Logs collected notification in the Bandwidth Utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Logs collected notification in the Bandwidth Utili")</span></span>

<span data-ttu-id="00353-p122">Klicken Sie auf **OK**. „BandwidthUtilizationAnalyzer.xlsm“ wird automatisch gestartet. Befolgen Sie die im Meldungsfeld angezeigten Anweisungen. Ausführliche Informationen finden Sie im nächsten Abschnitt unter **Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**.</span><span class="sxs-lookup"><span data-stu-id="00353-p122">Click **OK**. BandwidthUtilizationAnalyzer.xlsm is automatically started. Follow the instructions in the message box. For details, see **Using BandwidthUtilizationAnalyzer.xlsm** in the next section.</span></span>

</div>

<div>


<span data-ttu-id="00353-268">**Verwenden von „BandwidthUtilizationAnalyzer.xlsm“**</span><span class="sxs-lookup"><span data-stu-id="00353-268">**Using BandwidthUtilizationAnalyzer.xlsm**</span></span>

1.  <span data-ttu-id="00353-269">Wenn „BandwidthUtilizationAnalyzer.xlsm“ automatisch gestartet wurde, klicken Sie wie unten gezeigt auf **Refresh**.</span><span class="sxs-lookup"><span data-stu-id="00353-269">When BandwidthUtilizationAnalyzer.xlsm is automatically started, click **Refresh** as shown below.</span></span>
    
    <span data-ttu-id="00353-270">![BandwidthUtilizationAnalyzer. xlsm] (images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer. xlsm")</span><span class="sxs-lookup"><span data-stu-id="00353-270">![BandwidthUtilizationAnalyzer.xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer.xlsm")</span></span>

2.  <span data-ttu-id="00353-271">Wenn ein Dateiordner geöffnet wird, wählen Sie die Datei „consolidated.csv“ an dem Speicherort aus, der in dem unten gezeigten Meldungsfeld angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="00353-271">When a file folder is opened, select consolidated.csv from the location that is specified in the message box as shown below.</span></span> <span data-ttu-id="00353-272">Außerdem wird die Position als **C:\\Temp**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-272">It also shows the location as **C:\\Temp**.</span></span>
    
    <span data-ttu-id="00353-273">![Öffnen eines Ordners in BandwidthUtilizationAnalyzer] (images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Öffnen eines Ordners in BandwidthUtilizationAnalyzer")</span><span class="sxs-lookup"><span data-stu-id="00353-273">![Opening a folder in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Opening a folder in BandwidthUtilizationAnalyzer.")</span></span>

3.  <span data-ttu-id="00353-274">Klicken Sie auf **Import**.</span><span class="sxs-lookup"><span data-stu-id="00353-274">Click **Import**.</span></span>

4.  <span data-ttu-id="00353-p124">Das grafische Diagramm wird automatisch generiert. Es ist verfügbar, sobald der Hintergrundaktivitäts-Mauszeiger nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="00353-p124">The graphical plot is automatically generated. It is available when the working-in-the-background pointer disappears.</span></span>
    
    <span data-ttu-id="00353-277">![Anwenden von Filtern in der Berichtsansicht] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht")</span><span class="sxs-lookup"><span data-stu-id="00353-277">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a><span data-ttu-id="00353-278">Anwenden von Filtern auf die Berichtsansicht</span><span class="sxs-lookup"><span data-stu-id="00353-278">Applying Filters to the Report View</span></span>

<span data-ttu-id="00353-279">Die Filter, die wie unten gezeigt auf die Berichtsansicht angewendet werden können, werden nachfolgend beschrieben:</span><span class="sxs-lookup"><span data-stu-id="00353-279">The filters that can be applied to the report view as shown below are described as follows:</span></span>

<span data-ttu-id="00353-280">![Anwenden von Filtern in der Berichtsansicht] (images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Anwenden von Filtern in der Berichtsansicht")</span><span class="sxs-lookup"><span data-stu-id="00353-280">![Applying filters in Report View.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applying filters in Report View.")</span></span>

1.  <span data-ttu-id="00353-281">**Name** Filtern nach WAN-Verbindungen (der Filter befindet sich rechts von der Grafik). Das Präfix identifiziert die folgenden Verbindungstypen, siehe im vertikalen (blauen) Feld:</span><span class="sxs-lookup"><span data-stu-id="00353-281">**Name** Filter by WAN links (the filter is on the right side of the graph).The prefix denotes the following link types; see the vertical (blue) box:</span></span>
    
      - <span data-ttu-id="00353-282">**S Site** Die WAN-Verbindung von einem Netzwerkstandort zu einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="00353-282">**S Site** The WAN link from a network site to a network region</span></span>
    
      - <span data-ttu-id="00353-283">**IS Inter-Site** Die WAN-Verbindung zwischen zwei Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="00353-283">**IS Inter-Site** The WAN link between two network sites</span></span>
    
      - <span data-ttu-id="00353-284">**R Inter-Region** Die WAN-Verbindung zwischen zwei Netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="00353-284">**R Inter-Region** The WAN link between two network region</span></span>

2.  <span data-ttu-id="00353-285">**Exceeded limit** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung die Bandbreitenkapazität übersteigt</span><span class="sxs-lookup"><span data-stu-id="00353-285">**Exceeded limit** Filter by WAN links whose bandwidth utilization is more than the bandwidth capacity</span></span>

3.  <span data-ttu-id="00353-286">**Critical levels** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung mindestens 90 % der Bandbreitenkapazität erreicht hat</span><span class="sxs-lookup"><span data-stu-id="00353-286">**Critical levels** Filter by WAN links whose bandwidth utilization has reached 90% or more than the bandwidth capacity</span></span>

4.  <span data-ttu-id="00353-287">**Under-utilized** Filtern nach WAN-Verbindungen, deren Bandbreitenauslastung weniger als 25 % der Bandbreitenkapazität beträgt</span><span class="sxs-lookup"><span data-stu-id="00353-287">**Under-utilized** Filter by WAN links whose bandwidth utilization has been less than 25% of the bandwidth capacity</span></span>

5.  <span data-ttu-id="00353-288">**Link type** Filtern nach den folgenden WAN-Verbindungstypen:</span><span class="sxs-lookup"><span data-stu-id="00353-288">**Link type** Filter by the following WAN links types:</span></span>
    
      - <span data-ttu-id="00353-289">
            Typ **Network site**</span><span class="sxs-lookup"><span data-stu-id="00353-289">**Network site** type</span></span>
    
      - <span data-ttu-id="00353-290">
            Typ **Inter-site**</span><span class="sxs-lookup"><span data-stu-id="00353-290">**Inter-site** type</span></span>
    
      - <span data-ttu-id="00353-291">
            Typ \*\*Inter-Region link**</span><span class="sxs-lookup"><span data-stu-id="00353-291">**Inter-Region link** type</span></span>

6.  <span data-ttu-id="00353-292">**Region** Filtern nach Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="00353-292">**Region** Filter by network region</span></span>

<span data-ttu-id="00353-293">Die folgenden Abbildungen zeigen die oben beschriebenen Filter.</span><span class="sxs-lookup"><span data-stu-id="00353-293">The following figures show the previously described filters.</span></span>

<span data-ttu-id="00353-p125">Filtern nach **Name**. Wählen Sie die Liste der Verbindungen aus, die in dem Diagramm angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00353-p125">Filter by **Name**. Select the list of links that need to be displayed in the graph.</span></span>

<span data-ttu-id="00353-296">![Filtern nach Name in BandwidthUtilizationAnalyzer] (images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtern nach Name in BandwidthUtilizationAnalyzer")</span><span class="sxs-lookup"><span data-stu-id="00353-296">![Filtering by Name in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtering by Name in BandwidthUtilizationAnalyzer.")</span></span>

<span data-ttu-id="00353-297">Filtern nach **Exceeded limit**.</span><span class="sxs-lookup"><span data-stu-id="00353-297">Filter by **Exceeded limit**.</span></span> <span data-ttu-id="00353-298">Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="00353-298">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="00353-299">![Filterung nach Überschreitung des Grenzwerts.] (images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filterung nach Überschreitung des Grenzwerts.")</span><span class="sxs-lookup"><span data-stu-id="00353-299">![Filtering by Exceeded Limit.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtering by Exceeded Limit.")</span></span>

<span data-ttu-id="00353-300">Filtern nach **Critical levels**.</span><span class="sxs-lookup"><span data-stu-id="00353-300">Filter by **Critical levels**.</span></span> <span data-ttu-id="00353-301">Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="00353-301">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="00353-302">![Filtern nach kritischen Ebenen.] (images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtern nach kritischen Ebenen.")</span><span class="sxs-lookup"><span data-stu-id="00353-302">![Filtering by Critical Levels.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtering by Critical Levels.")</span></span>

<span data-ttu-id="00353-303">Filtern nach **Under utilized**.</span><span class="sxs-lookup"><span data-stu-id="00353-303">Filter by **Under utilized**.</span></span> <span data-ttu-id="00353-304">Wählen Sie **True** aus, um den Filter zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="00353-304">Select **True** to enforce the filter.</span></span>

<span data-ttu-id="00353-305">![Filtern nach unter verwendet.] (images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtern nach unter verwendet.")</span><span class="sxs-lookup"><span data-stu-id="00353-305">![Filtering by Under Utilized.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtering by Under Utilized.")</span></span>

<span data-ttu-id="00353-306">Filtern nach **Link Type**.</span><span class="sxs-lookup"><span data-stu-id="00353-306">Filter by **Link Type**.</span></span> <span data-ttu-id="00353-307">Wählen Sie die Typen aus, die angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00353-307">Select the type or types that need to be displayed.</span></span>

<span data-ttu-id="00353-308">![Filtern nach Verknüpfungstyp.] (images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtern nach Verknüpfungstyp.")</span><span class="sxs-lookup"><span data-stu-id="00353-308">![Filtering by Link Type.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtering by Link Type.")</span></span>

<span data-ttu-id="00353-309">Filtern nach **Region**.</span><span class="sxs-lookup"><span data-stu-id="00353-309">Filter by **Region**.</span></span> <span data-ttu-id="00353-310">Wählen Sie eine Liste der Regionen aus, deren Verbindungen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00353-310">Select a list of regions whose links need to be displayed.</span></span>

<span data-ttu-id="00353-311">![Filtern nach Region.] (images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtern nach Region.")</span><span class="sxs-lookup"><span data-stu-id="00353-311">![Filtering by Region.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtering by Region.")</span></span>

</div>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-312">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-312">Requirements</span></span>

  - <span data-ttu-id="00353-313">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="00353-313">The .NET Framework 3.5</span></span>

  - <span data-ttu-id="00353-314">Microsoft Excel 2010 oder Excel 2007</span><span class="sxs-lookup"><span data-stu-id="00353-314">Microsoft Excel 2010 or Excel 2007</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-315">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-315">Summary</span></span>

<span data-ttu-id="00353-p131">Bandwidth Utilization Analyzer wird verwendet, um die Bandbreitenauslastung durch Audio für UC-Datenverkehr über das Netzwerk grafisch darzustellen. Mithilfe dieses Tools kann auch die Bandbreitenauslastung durch Video im Netzwerk dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-p131">Bandwidth Utilization Analyzer is used to plot the audio bandwidth utilization for UC traffic across the network. This tool can be used to report the utilization of video bandwidth on the network as well.</span></span>

</div>

</div>

<div>

## <a name="call-parkometer"></a><span data-ttu-id="00353-318">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="00353-318">Call Parkometer</span></span>

<span data-ttu-id="00353-319">Call Parkometer ist eine Befehlszeilenanwendung, die einfachen Zugriff auf die Datenbank mit den Orbits der geparkten Anrufe ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="00353-319">Call Parkometer is a command-line application that provides easy access to the Call Park orbit database.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-320">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-320">Description</span></span>

<span data-ttu-id="00353-321">Call Parkometer ist ein Tool zum Nachverfolgen der zurzeit geparkten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="00353-321">Call Parkometer is a tool to track currently parked calls.</span></span> <span data-ttu-id="00353-322">Es erfasst außerdem Statistiken über Orbits und die Nutzung des Anrufparkservers (Call Park Server, CPS).</span><span class="sxs-lookup"><span data-stu-id="00353-322">It also collects statistics about orbits and Call Park Server (CPS) usage.</span></span> <span data-ttu-id="00353-323">Dieses Befehlszeilentool bietet Lese-und Schreibzugriff auf die CPS-Orbit-SQL Server-Datenbank von einem lokalen oder Remote verbundenen Computer.</span><span class="sxs-lookup"><span data-stu-id="00353-323">This command-line tool provides both read and write-access to the CPS orbit SQL Server database from a local or remotely connected computer.</span></span>

<span data-ttu-id="00353-p133">Alle Optionen schließen sich gegenseitig aus. Befehlszeilensyntax:</span><span class="sxs-lookup"><span data-stu-id="00353-p133">All options are mutually exclusive. Command-line syntax is as follows:</span></span>

  - <span data-ttu-id="00353-326">**–o** (Parameter) – Listet alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-326">**–o** parameter—lists all orbit ranges configured for this pool.</span></span>

  - <span data-ttu-id="00353-p134">**–n** (Parameter) – Listet alle zurzeit in diesem Pool verwendeten Orbits auf. Folgende Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="00353-p134">**–n** parameter—lists all currently used orbits in this pool. The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="00353-329">Der SIP-URI (Session Initiation Protocol Uniform Resource Identifier) der geparkten und der parkenden Person</span><span class="sxs-lookup"><span data-stu-id="00353-329">SIP Uniform Resource Identifier (URI) of the parkee and parker.</span></span>
    
      - <span data-ttu-id="00353-330">Der Hostname des Anrufparkservers, auf dem der Anruf geparkt ist</span><span class="sxs-lookup"><span data-stu-id="00353-330">Host name of the CPS where the call is parked.</span></span>
    
      - <span data-ttu-id="00353-331">Der Zeitstempel, aus dem hervorgeht, wann der Anruf geparkt wurde</span><span class="sxs-lookup"><span data-stu-id="00353-331">Time stamp of when the call was parked.</span></span>

  - <span data-ttu-id="00353-332">**–f** (Parameter) – Listet die Anzahl der zurzeit freien Orbits im Pool auf.</span><span class="sxs-lookup"><span data-stu-id="00353-332">**–f** parameter—lists the number of currently free orbits in the pool.</span></span>

  - <span data-ttu-id="00353-333">\*\*– r \<n\> \*\* -Parameter – listet \<die\> n letzten geparkten Anrufe auf.</span><span class="sxs-lookup"><span data-stu-id="00353-333">**–r \<n\>** parameter—lists the \<n\> last parked calls.</span></span> <span data-ttu-id="00353-334">Folgende Informationen werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="00353-334">The information displayed is as follows:</span></span>
    
      - <span data-ttu-id="00353-335">SIP-URI der geparkten Person</span><span class="sxs-lookup"><span data-stu-id="00353-335">Parkee SIP URI.</span></span>
    
      - <span data-ttu-id="00353-336">SIP-URI der parkenden Person</span><span class="sxs-lookup"><span data-stu-id="00353-336">Parker SIP URI.</span></span>
    
      - <span data-ttu-id="00353-337">Der Hostname des Anrufparkservers, auf dem der Anruf geparkt wurde</span><span class="sxs-lookup"><span data-stu-id="00353-337">Host name of the CPS where the call was parked.</span></span>
    
      - <span data-ttu-id="00353-338">Der Zeitstempel, aus dem hervorgeht, wann der Anruf herangeholt oder abgebrochen wurde</span><span class="sxs-lookup"><span data-stu-id="00353-338">Time stamp of when the call was retrieved or dropped.</span></span>

  - <span data-ttu-id="00353-339">\*\*-t\<n\> \*\* Parameter – testet, wie eine Umlaufbahn in der Datenbank reserviert wird, um die Zufälligkeit der zugewiesenen Orbit-Nummern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-339">**-t\<n\>** parameter - tests reserving an orbit in the database to show the randomness of the assigned orbit numbers.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-340">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-340">Output</span></span>

<span data-ttu-id="00353-341">Abhängig von den Eingabeparametern, die an der Eingabeaufforderung angegeben werden, zeigt Call Parkometer folgende Ausgaben an:</span><span class="sxs-lookup"><span data-stu-id="00353-341">Depending on the input parameters that are specified at a command prompt, Call Parkometer displays the following output:</span></span>

  - <span data-ttu-id="00353-342">Alle für diesen Pool konfigurierten Orbitbereiche</span><span class="sxs-lookup"><span data-stu-id="00353-342">All orbit ranges that are configured for this pool</span></span>

  - <span data-ttu-id="00353-343">Zurzeit geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="00353-343">Currently parked calls</span></span>

  - <span data-ttu-id="00353-344">Anzahl der freien (verfügbaren) Orbits</span><span class="sxs-lookup"><span data-stu-id="00353-344">Number of free (available) orbits</span></span>

  - <span data-ttu-id="00353-345">Zuletzt geparkte Anrufe</span><span class="sxs-lookup"><span data-stu-id="00353-345">Recently parked calls</span></span>

  - <span data-ttu-id="00353-346">Für das Testen einheitlicher und zufälliger Orbitwerte reservierte Orbits</span><span class="sxs-lookup"><span data-stu-id="00353-346">Reserved orbits for testing uniform and random orbit values</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-347">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-347">Purpose</span></span>

<span data-ttu-id="00353-p136">Das Anrufparkserver-Tool soll Befehlszeilenzugriff auf die Anrufparkserver-Datenbank ermöglichen. Administratoren können die Anrufparkserver-Nutzung anzeigen und die Anzahl der Orbits bestimmen, die einem Pool zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="00353-p136">The purpose of the CPS tool is to provide command-line access to the CPS database. The administrator can view the CPS usage and determine the number of orbits assigned to a pool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-350">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-350">Requirements</span></span>

<span data-ttu-id="00353-351">Wenn das Tool auf dem gleichen Computer wie der Anrufparkserver ausgeführt wird, gelten keine Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="00353-351">There are no requirements if this tool is run on the same computer that is running CPS.</span></span> <span data-ttu-id="00353-352">Wenn dieses Tool auf einem Remotecomputer ausgeführt wird, muss die von lync Server 2013 verwendete SQL Server-Datenbank so konfiguriert sein, dass der Remotezugriff zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="00353-352">If this tool is run on a remote computer, the SQL Server database used by Lync Server 2013 must be configured to allow remote access.</span></span> <span data-ttu-id="00353-353">Anruf Parkometer muss mit einer SQL Server-Datenbankverbindungszeichenfolge konfiguriert werden, um eine Verbindung mit dem SQL Server des Pools herzustellen.</span><span class="sxs-lookup"><span data-stu-id="00353-353">Call Parkometer must be configured with a SQL Server database connection string to connect to the pool’s SQL Server.</span></span> <span data-ttu-id="00353-354">Diese SQL Server-Datenbankverbindungszeichenfolge ist in der Konfigurationsdatei **parkometer. exe. config**definiert. Sie muss sich im gleichen Verzeichnis befinden, in dem sich parkometer. exe befindet.</span><span class="sxs-lookup"><span data-stu-id="00353-354">This SQL Server database connection string is defined in the configuration file, **parkometer.exe.config**. It must be placed in the same directory where parkometer.exe is located.</span></span> <span data-ttu-id="00353-355">Die folgende XML-Datei ist ein Beispiel für eine parkometer. exe. config. Bei den zu konfigurierbaren Parametern handelt es sich um den Benutzernamen\\(beispielsweise mydomain Administrator), ein Kennwort (beispielsweise mypassword) und einen Hostnamen (beispielsweise MyServer).</span><span class="sxs-lookup"><span data-stu-id="00353-355">The following XML file is an example of a parkometer.exe.config. The parameters that must be configured are user name (for example, mydomain\\Administrator), password (for example, mypassword), and host name (for example, myserver).</span></span>

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

## <a name="examples"></a><span data-ttu-id="00353-356">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-356">Examples</span></span>

<span data-ttu-id="00353-357">Bereitgestellte Orbitbereiche: Der Parameter „–o“ listet wie gezeigt alle Orbitbereiche auf, die für diesen Pool konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-357">Deployed orbit ranges: the –o parameter lists all orbit ranges that are configured for this pool as shown</span></span>

<span data-ttu-id="00353-358">![Umlaufbahn Bereiche in der Anruf Parkometer.] (images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Umlaufbahn Bereiche in der Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="00353-358">![Orbit ranges in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Orbit ranges in Call Parkometer.")</span></span>

<span data-ttu-id="00353-359">Zurzeit geparkte Anrufe: Der Parameter „–n“ listet wie gezeigt alle zurzeit verwendeten Orbits in diesem Pool auf.</span><span class="sxs-lookup"><span data-stu-id="00353-359">Currently parked calls: the –n parameter lists all currently used orbits on this pool as shown</span></span>

<span data-ttu-id="00353-360">![Zurzeit geparkte Anrufe in Anruf Parkometer.] (images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Zurzeit geparkte Anrufe in Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="00353-360">![Currently-parked calls in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Currently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="00353-361">Anzahl freier Orbits: Der Parameter „–f“ listet wie gezeigt die Anzahl der zurzeit freien Orbits im Pool auf.</span><span class="sxs-lookup"><span data-stu-id="00353-361">Number of free orbits: the –f parameter lists the number of currently free orbits in the pool as shown</span></span>

<span data-ttu-id="00353-362">![Freie Umlaufbahnen in Anruf Parkometer.] (images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Freie Umlaufbahnen in Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="00353-362">![Free orbits in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Free orbits in Call Parkometer.")</span></span>

<span data-ttu-id="00353-363">Zuletzt geparkte Anrufe: der Parameter \<–\> r n listet \<die\> n letzten geparkten Anrufe auf, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-363">Recently parked calls: the –r \<n\> parameter lists the \<n\> last parked calls as shown</span></span>

<span data-ttu-id="00353-364">![Vor kurzem geparkte Anrufe in Anruf Parkometer.] (images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Vor kurzem geparkte Anrufe in Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="00353-364">![Recently-parked calls in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Recently-parked calls in Call Parkometer.")</span></span>

<span data-ttu-id="00353-365">Test Orbit-Reservierung: der – \<t\> n-Parameter testet, wie eine Umlaufbahn in der Datenbank reserviert wird (siehe Abbildung)</span><span class="sxs-lookup"><span data-stu-id="00353-365">Test orbit reservation: the –t \<n\> parameter tests reserving an orbit in the database as shown</span></span>

<span data-ttu-id="00353-366">![Testen Sie Orbit-Reservierungen in Anruf Parkometer.] (images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testen Sie Orbit-Reservierungen in Anruf Parkometer.")</span><span class="sxs-lookup"><span data-stu-id="00353-366">![Test orbit reservations in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Test orbit reservations in Call Parkometer.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-367">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-367">Summary</span></span>

<span data-ttu-id="00353-368">Call Parkometer ist ein Befehlszeilentool, das detaillierte Informationen zum Anrufparkserver bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="00353-368">Call Parkometer is a command-line tool that provides detailed information about the Call Park Server.</span></span>

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a><span data-ttu-id="00353-369">CleanupStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="00353-369">CleanupStorageServiceData</span></span>

<span data-ttu-id="00353-370">Das CleanupStorageServiceData Resource Kit-Tool ermöglicht das Löschen von verwaisten Daten aus der Datenbank, die vom lync Server-Speicherdienst (LYSS) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00353-370">The CleanupStorageServiceData resource kit tool allows for deleting of orphaned data from the database used by the Lync Server Storage Service (LYSS).</span></span> <span data-ttu-id="00353-371">Eine Funktion des Speicher Diensts besteht darin, die Kommunikation zwischen lync Server und verschiedenen Endpunkten des Back-End-Datenspeichers zu puffern, wie SQL Server und Exchange.</span><span class="sxs-lookup"><span data-stu-id="00353-371">One function of the storage service is to buffer communication between Lync Server and various back-end data storage endpoints, like SQL Server and Exchange.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-372">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-372">Description</span></span>

<span data-ttu-id="00353-373">Um eine hohe Verfügbarkeit zu unterstützen, akzeptiert und speichert LYSS Kopien der Daten auf mehreren Front-End-Servern im Pool temporär und entfernt diese Daten, sobald Sie an den endgültigen langfristigen Speicherplatz übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="00353-373">To support high availability, LYSS accepts and saves copies of the data on multiple front end servers in the pool temporarily, and removes that data once it has been delivered to its final long-term storage location.</span></span> <span data-ttu-id="00353-374">Es gibt ungewöhnliche Situationen, die bei einem ansonsten normalen Betrieb auftreten können, wenn ein Server abstürzt oder ein Verarbeitungsproblem auftritt und einige Daten möglicherweise nicht ordnungsgemäß bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-374">There are unusual situations which may occur during otherwise normal operation, when a server might crash or experience a processing issue, and some data might not get cleaned up properly.</span></span> <span data-ttu-id="00353-375">Diese Daten sind harmlos, aber es werden nur begrenzte Verarbeitungsressourcen beansprucht.</span><span class="sxs-lookup"><span data-stu-id="00353-375">This data is harmless, but it does consume limited processing resources.</span></span> <span data-ttu-id="00353-376">Ein Großteil der normalen erforderlichen Datenwartung ist automatisiert, aber dieses Tool ermöglicht die sichere Identifikation und Entfernung solcher verwaister Daten, wenn eine automatisierte Entfernung nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="00353-376">Much of the normal required data maintenance is automated, but this tool allows for the safe identification and removal of such orphaned data when automated removal is not possible.</span></span> <span data-ttu-id="00353-377">Die Verwendung dieses Tools wird angezeigt, wenn eine Integritäts Überwachungs System Center Operations Manager (SCOM)-Warnung ausgelöst wird, die den Administrator auffordert, die nicht benötigten Daten aus den lokalen LYSS-Datenbanken im Pool zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="00353-377">Usage of this tool is indicated when a health monitoring System Center Operations Manager (SCOM) alert is raised which asks the administrator to remove the unneeded data from the local LYSS databases in the pool.</span></span> <span data-ttu-id="00353-378">Im Ereignisprotokoll auf dem Front-End, das die Benachrichtigung ausgelöst hat, wird ein entsprechendes Ereignis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-378">There will be a corresponding event in the event log on the front end which triggered the alert.</span></span> <span data-ttu-id="00353-379">Die Ereignisdetails enthalten Informationen über die Anzahl der verwaisten Daten, die auf dem Front-End enthalten sind, und werden ausgelöst, wenn diese Daten bestimmte vordefinierte Schwellenwerte überschreiten.</span><span class="sxs-lookup"><span data-stu-id="00353-379">The event details will contain information about the amount of orphaned data contained on the front end, and is raised when that data exceeds certain pre-determine thresholds</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-380">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="00353-380">Requirements</span></span>

<span data-ttu-id="00353-381">Installieren Sie die lync Server 2013, Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="00353-381">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="00353-382">Das Tool wird auf Domänen verbundenen Computern ausgeführt, auf denen lync Server und lync Server 2013-Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-382">The tool runs on domain-joined machines where Lync Server and Lync Server 2013 Management Shell are installed.</span></span> <span data-ttu-id="00353-383">Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00353-383">The tool uses a cmdlet from the management shell to identify all Front End servers in the pool.</span></span> <span data-ttu-id="00353-384">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-384">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="00353-385">Diese Datenbank wird vom CleanupStorageServiceData-Tool verwendet, um die Verbindungsdetails abzurufen, die für die Kommunikation mit dem lync Server-Routing Dienst erforderlich sind. Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über die Berechtigung "Lesen/Schreiben" für die Dateifreigabe verfügen, auf die Sie möchten das Ausgabeprotokoll schreiben. Dieses Tool hängt auch davon ab, dass sich der Pool in einem stabilen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="00353-385">This database is used by the CleanupStorageServiceData tool to get the connection details needed to communicate with the Lync Server Routing Service.Finally, the account or credential invoking the tool must have read/write permission to the file share to which they want to write the output log.Also, this tool depends on the pool being in a stable state.</span></span> <span data-ttu-id="00353-386">Im Wesentlichen bedeutet dies, dass jeder Front-End-Server ausgeführt werden soll, dass die SQL Server LYNCLOCAL-Instanz und die LYSS-Datenbank eine Verbindung herstellen können, und jede Routinggruppe einen vollständigen Satz von 1 primären Front-End-Servern und 2 sekundären Front-End-Servern aufweisen muss. Server aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="00353-386">In essence this means that every Front End server is expected to be up and running, the SQL Server LYNCLOCAL instance and LYSS database must be able to be connected to, and each routing group must have a complete set of 1 primary Front End servers and 2 secondary Front End servers.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-387">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-387">Examples</span></span>

<span data-ttu-id="00353-388">C:\\Programmdateien\\Microsoft lync Server 2013\\reskit\\StorageService\> ImportStorageServiceData. exe</span><span class="sxs-lookup"><span data-stu-id="00353-388">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\\StorageService\> ImportStorageServiceData.exe</span></span>

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

## <a name="dbanalyze"></a><span data-ttu-id="00353-389">DBAnalyze</span><span class="sxs-lookup"><span data-stu-id="00353-389">DBAnalyze</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-390">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-390">Description</span></span>

<span data-ttu-id="00353-391">Dbanalyze ist ein Befehlszeilentool, das Administratoren hilft, Analyseberichte zu den lync Server 2013-Datenbanken zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="00353-391">DBAnalyze is a command-line tool that helps administrators to gather analysis reports about the Lync Server 2013 databases.</span></span> <span data-ttu-id="00353-392">DBAnalyze verfügt über folgende Modi: Diagnose, Benutzerdaten, Konferenz, MCUs und Datenträgerfragmentierung:</span><span class="sxs-lookup"><span data-stu-id="00353-392">DBAnalyze has the following modes: diagnostic, user data, conference, MCUs, and disk fragmentation:</span></span>

  - <span data-ttu-id="00353-393">**Im Diagnosemodus**   wird ein Bericht erstellt, der Informationen zu Tabellen (Anzahl der Datensätze, Fragmentierung, Datengröße und Indexgröße), Daten-und Protokolldateigrößen, die letzte Sicherungszeit, die Kontaktverteilung zwischen Servern, auf denen Microsoft ausgeführt wird, enthält. Office Communications Server, die durchschnittliche Anzahl von Berechtigungen, Kontakten, Containern, Abonnements, Publikationen, Endpunkten pro Benutzer, nicht ordnungsgemäß vernetzte Benutzer, Benutzer, die nicht weitergeleitet werden können, die durchschnittliche Anzahl der pro Benutzer organisierten Konferenzen, geplant Konferenzen, aktive Konferenzen und die Datenbankversion.</span><span class="sxs-lookup"><span data-stu-id="00353-393">**Diagnostic mode**   Creates a report that includes information about tables (number of records, fragmentation, data size, and index size), data and log file sizes, the last back-up time, contact distribution among servers that are running Microsoft Office Communications Server, the average number of permissions, contacts, containers, subscriptions, publications, endpoints per user, any improperly homed users, users that can’t be routed, the average number of conferences organized per user, scheduled conferences, active conferences, and the database version.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00353-394">Die Ausführung im Diagnosemodus kann die Serverleistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="00353-394">Running diagnostic mode can affect server performance.</span></span>

    
    </div>

  - <span data-ttu-id="00353-395">**Benutzerdaten Modus**  Meldet Kontakt-, Container-, Abonnement-, Veröffentlichungs-, Genehmigungs-und Kontaktgruppen Daten für einen bestimmten Benutzer oder für Benutzer, die diesen Benutzer in seinen Kontakt-und Berechtigungslisten haben.</span><span class="sxs-lookup"><span data-stu-id="00353-395">**User data mode**  Reports contact, container, subscription, publication, permission, and contact-group data for a specified user or for users who have that user in their contact and permission lists.</span></span> <span data-ttu-id="00353-396">Dieser Modus berichtet außerdem Zusammenfassungsdaten für Konferenzen, die von einem Benutzer organisiert werden oder zu denen er eingeladen ist.</span><span class="sxs-lookup"><span data-stu-id="00353-396">This mode also reports summary data for conferences that a user organizes or is invited to.</span></span>

  - <span data-ttu-id="00353-397">**Im Konferenzmodus**   werden detaillierte Daten für eine bestimmte Konferenz gemeldet, einschließlich aller Details zur Terminplanung für die Konferenz, der Liste der eingeladenen Personen, der Liste der für die Konferenz zulässigen Medientypen, der aktiven MCU (Multipoint Control Units), der aktiven Teilnehmerliste und den Signalisierungs Status jedes Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="00353-397">**Conference mode**   Reports detailed data for a specific conference, including all schedule-time details for the conference, the invitee list, the list of media types allowed for the conference, active MCUs (multipoint control units), the active participant list, and each participant’s signaling state.</span></span>

  - <span data-ttu-id="00353-398">**Decodieren der Besprechungs-ID**  dekodiert eine vom **/pstnid** -Schalter angegebene PSTN-Besprechungs-ID (Public Switched Telephone Network), die jedoch nicht mit dem Back-End verbunden ist, um detaillierte Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="00353-398">**Decode Meeting ID**  Decodes a public switched telephone network (PSTN) meeting ID that is specified by the **/pstnid** switch but does not connect to the back end for detailed information.</span></span>

  - <span data-ttu-id="00353-399">**Konferenz auflösen**   decodiert eine PSTN-Besprechungs-ID, die vom **/pstnid** -Schalter angegeben wird, und zeigt Informationen zu der Konferenz an, die von der ID angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="00353-399">**Resolve conference**   Decodes a PSTN meeting ID that is specified by the **/pstnid** switch and displays information about the conference indicated by the ID.</span></span>

  - <span data-ttu-id="00353-400">**Im MCU-Modus**  werden die ID, der Medientyp, die URL, der Heartbeat-Status, die Konferenz Auslastung und die Teilnehmer Auslastung für jede MCU im Pool gemeldet.</span><span class="sxs-lookup"><span data-stu-id="00353-400">**MCUs mode**  Reports the ID, media type, URL, heartbeat status, conference load, and participant load for each MCU in the pool.</span></span>

  - <span data-ttu-id="00353-401">**Der Datenträger Fragmentierungs Modus**  zeigt den Fragmentierungs Status aller Datenträger an.</span><span class="sxs-lookup"><span data-stu-id="00353-401">**Disk fragmentation mode**  Displays the fragmentation status of all disks.</span></span>

<span data-ttu-id="00353-p143">Dieses Tool kann zum Diagnostizieren verschiedener Probleme verwendet werden oder Administratoren bei der Kapazitätsplanung unterstützen. Wenn beispielsweise die meisten der auf Server A verwalteten Benutzer auf Server B verwaltete Benutzer als Kontakte wählen, kann der Administrator die Benutzer von Server A auf Server B verschieben, um den Datenverkehr zwischen den Servern zu verringern.</span><span class="sxs-lookup"><span data-stu-id="00353-p143">This tool can be used to diagnose various problems or to assist administrators with capacity planning. For example, if most of the users homed on server A choose users homed on server B as their contacts, the administrator can move the users on server A to server B to reduce cross-server traffic.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-404">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-404">Output</span></span>

<span data-ttu-id="00353-405">Dieses Tool gibt vordefinierte Berichte zur lync Server 2013-Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="00353-405">This tool outputs predefined reports about the Lync Server 2013 database.</span></span> <span data-ttu-id="00353-406">**Pfad:** % Programme%\\Microsoft lync Server 2013\\-reskit</span><span class="sxs-lookup"><span data-stu-id="00353-406">**Path:** %ProgramFiles%\\Microsoft Lync Server 2013\\Reskit</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-407">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-407">Purpose</span></span>

<span data-ttu-id="00353-408">Wenn Sie Dbanalyze. exe installieren möchten, kopieren Sie Sie in einen lokalen Ordner, und führen Sie dann das Tool aus.</span><span class="sxs-lookup"><span data-stu-id="00353-408">To install Dbanalyze.exe, copy it to a local folder and then run the tool.</span></span> <span data-ttu-id="00353-409">Führen Sie den folgenden Befehl in der Befehlszeile aus, um das Tool zu verwenden.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span><span class="sxs-lookup"><span data-stu-id="00353-409">To use the tool, run the following command from the command line.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`</span></span> <span data-ttu-id="00353-410">Die Beschreibungen für die Befehlszeilenoptionen sind unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-410">The descriptions for the command-line options are shown below.</span></span>

<span data-ttu-id="00353-411">![Befehlszeilenoptionen für "Dbanalyze. exe".] (images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Befehlszeilenoptionen für \"Dbanalyze. exe\".")</span><span class="sxs-lookup"><span data-stu-id="00353-411">![Command line options for Dbanalyze.exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Command line options for Dbanalyze.exe.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-412">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="00353-412">Requirements</span></span>

<span data-ttu-id="00353-413">**Computer** Dbanalyze kann nur von einem Domänen verbundenen Computer ausgeführt werden, auf dem lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-413">**Computer** DBAnalyze can be run only from a domain-joined computer that has Lync Server 2013 installed.</span></span>

<span data-ttu-id="00353-414">**Netzwerk** Der Computer sollte in der Lage sein, eine Verbindung mit der Back-End-Datenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="00353-414">**Network** The computer should be able to connect to the back-end database.</span></span>

<span data-ttu-id="00353-415">**Software** Die lync Server 2013-Softwarekomponenten müssen vor der Ausführung von Dbanalyze installiert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-415">**Software** Lync Server 2013 software components must be installed before running DBAnalyze.</span></span>

<span data-ttu-id="00353-416">**Benutzer** In der folgenden Tabelle sind die Administratoren aufgeführt, die über die erforderlichen Berechtigungen für den Zugriff auf lync Server 2013-Datenbanken verfügen.</span><span class="sxs-lookup"><span data-stu-id="00353-416">**Users**The table below shows the administrators who have the necessary permissions to access Lync Server 2013 databases.</span></span>

<span data-ttu-id="00353-417">![Berechtigungstabelle für "Dbanalyze. exe".] (images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Berechtigungstabelle für \"Dbanalyze. exe\".")</span><span class="sxs-lookup"><span data-stu-id="00353-417">![Permissions table for Dbanalyze.exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Permissions table for Dbanalyze.exe.")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-418">Für den <STRONG>/report:disk</STRONG>-Modus ist ein lokales Administratorkonto erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00353-418">A local administrator account is required for <STRONG>/report:disk</STRONG> mode.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-419">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-419">Examples</span></span>

<span data-ttu-id="00353-420">Hier sind Beispiele für gültige „Dbanalyze.exe“-Befehle:</span><span class="sxs-lookup"><span data-stu-id="00353-420">The following are examples of valid Dbanalyze.exe commands:</span></span>

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-421">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-421">Summary</span></span>

<span data-ttu-id="00353-422">Dbanalyzer bietet Administratoren eine schnelle und einfache Analyse von lync Server 2013-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="00353-422">DBAnalyzer provides administrators a quick and easy to analyze Lync Server 2013 databases.</span></span>

</div>

</div>

<div>

## <a name="importstorageservicedata"></a><span data-ttu-id="00353-423">ImportStorageServiceData</span><span class="sxs-lookup"><span data-stu-id="00353-423">ImportStorageServiceData</span></span>

<span data-ttu-id="00353-424">Mit dem Resource Kit-Tool „ImportStorageServiceData“ können Warteschlangen- und Endpunktdaten, die aus dem Speicherdienst (LYSS) geleert wurden, wieder zurück in den Speicherdienst importiert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-424">The ImportStorageServiceData resource kit tool allows for re-importing Queue and Endpoint data that was flushed out of the Storage Service (LYSS) back into the Storage Service.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-425">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-425">Description</span></span>

<span data-ttu-id="00353-426">Die Leerung der Daten aus dem Speicherdienst kann automatisch (regelmäßig) auf Grundlage des Warteschlangenelementstatus oder der Datenbankgröße erfolgt sein.</span><span class="sxs-lookup"><span data-stu-id="00353-426">The data flushed out of the Storage Service could have been automatic (periodic) based on Queue Item status or database size.</span></span> <span data-ttu-id="00353-427">Das Leeren kann aufgrund eines manuellen Aufrufs des Cmdlets für Poolfailover oder des Cmdlets „StorageServiceFullFlush“ (das vom Cmdlet für Poolfailover aufgerufen wird) erfolgt sein.</span><span class="sxs-lookup"><span data-stu-id="00353-427">It could have happened due to the manual invocation of the pool failover cmdlet, or the StorageServiceFullFlush cmdlet (which the pool failover cmdlet invokes).</span></span> <span data-ttu-id="00353-428">Beachten Sie, dass Daten im Idealfall nicht erneut importiert werden sollten, wenn sich die Datenbankgröße des Speicher Diensts (LYSS) auf den Front-Ends über der normalen Ebene befindet, weil dies wahrscheinlich dazu führt, dass mehr Daten wieder exportiert werden. Darüber hinaus sollten alle Probleme, die zu Fehlern beigetragen haben, die dazu geführt haben, dass die Speicherdienst Warteschlange anwächst, zunächst aufgelöst werden (beispielsweise Exchange-Endpunkt Fehler, Netzwerkprobleme oder andere Probleme).</span><span class="sxs-lookup"><span data-stu-id="00353-428">Note that data should ideally not be re-imported if any of the Storage Service (LYSS ) database size on the front ends is above the normal level, because doing so will likely just cause more data to be exported back out. Furthermore, any problems which could have contributed to errors that caused the Storage Service Queue to grow should first be resolved (for example Exchange endpoint errors, network issues, or other problems).</span></span>

<span data-ttu-id="00353-429">**Szenario 1:** während des Pool-Failovers können Dateien für jedes Front-End vom Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-429">**Scenario 1:** during pool failover, files may be flushed out from storage service for each front end.</span></span> <span data-ttu-id="00353-430">Nach Abschluss des Failovers sollte das Tool ausgeführt werden, um die Daten erneut zu importieren.</span><span class="sxs-lookup"><span data-stu-id="00353-430">After failover is completed, the tool should be run to re-import the data.</span></span>

<span data-ttu-id="00353-431">**Szenario 2:** die Daten werden jeden Tag automatisch geleert oder als Antwort auf eine Speicherdienst Datenbank, die bestimmte Größengrenzwerte überschreitet (beispielsweise 60%, 80%, 90% voll).</span><span class="sxs-lookup"><span data-stu-id="00353-431">**Scenario 2:** data is being flushed automatically each day or in response to Storage Service database exceeding certain size thresholds ( for example 60%, 80%, 90% full ).</span></span> <span data-ttu-id="00353-432">Diese automatisch geleerten Daten sollten vom Administrator routinemäßig erneut importiert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-432">This automatically flushed data should be re-imported routinely by the administrator.</span></span> <span data-ttu-id="00353-433">Wenn das SCOM-Überwachungspaket nicht bereitgestellt wird, gibt es in der obigen Situation Ereignisse für den lync Server-Speicherdienst, die sich auf Daten beziehen, die vom Speicherdienst geleert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-433">In the above situation, if the monitoring SCOM pack is not deployed, there are events for Lync Server Storage Service relating to data being flushed from the Storage Service.</span></span> <span data-ttu-id="00353-434">Ereignis-IDs von 32075 (vollständiger Flush-Vorgang wird gestartet), 32076 (vollständiger Flush wurde abgeschlossen), 32082 (Wartungsebene wurde gestartet), 32083 (Maintenance Level Flush Complete), 32089 (Flush ist aufgrund des Auffüllens der Datenbank aufgetreten).</span><span class="sxs-lookup"><span data-stu-id="00353-434">Event IDs of 32075 (full flush operation is started), 32076 (full flush has completed), 32082 (maintenance level flush started), 32083 (maintenance level flush complete), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="00353-435">Hinweis Diese Ereignis-IDs entsprechen der RTM-Version.</span><span class="sxs-lookup"><span data-stu-id="00353-435">Note these event Ids correspond to the RTM release.</span></span> <span data-ttu-id="00353-436">Wenn ein Administrator diese Ereignisse sieht, bedeutet dies, dass Dateien vorhanden sind, die geleert wurden. Diese Daten sollten routinemäßig mit diesem Tool wieder importiert werden, beispielsweise einmal pro Woche.</span><span class="sxs-lookup"><span data-stu-id="00353-436">When an administrator sees these events, it means that there are files that have been flushed out. This data should routinely be imported back using this tool, for example once per week.</span></span>

<span data-ttu-id="00353-437">Wenn für die Online Dienstversion die Statusüberwachung SCOM Pack für lync Server bereitgestellt wird, gibt es neue Warnungen, die möglicherweise ausgelöst werden, die den Administrator auffordern, die leeren Daten wieder in den Speicherdienst zu importieren.</span><span class="sxs-lookup"><span data-stu-id="00353-437">For the Online Service release, if health monitoring SCOM pack for Lync Server is deployed, there are new alerts which may be raised which ask the administrator to re-import the flushed data back into Storage Service.</span></span> <span data-ttu-id="00353-438">Im Ereignisprotokoll auf dem Front-End-Server befindet sich ein entsprechendes Ereignis, das die Benachrichtigung ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="00353-438">There will be a corresponding event in the event log on the Front End server which triggered the alert.</span></span> <span data-ttu-id="00353-439">Das Ereignis enthält eine Beschreibung des übergeordneten Pfads, unter dem sich die gelesenen Datendateien befinden, sowie die Anzahl der Dateien, die den Warnungskriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="00353-439">The event will give a description of the Parent path under which the flushed data files are located, as well as how many files there are which meet the alert criteria.</span></span> <span data-ttu-id="00353-440">Bei den Warnungskriterien handelt es sich um x oder mehr Dateien unter dem bestimmten übergeordneten Pfad, die mindestens Y Tage alt sind (wobei x und Y im StorageService voreingestellt sind, aber durch Ändern der APPCONFIG-Datei überschrieben werden können). Nachfolgend werden zwei Beispiele für Ereignisse angezeigt, die die Integritäts Warnung auslösen können, wobei der Unterschied der übergeordnete Pfad ist.</span><span class="sxs-lookup"><span data-stu-id="00353-440">The alert criteria is that there are X or more files under the particular parent path which are at least Y days old ( where X and Y are preset within the StorageService but can be overridden by changing the APPCONFIG file.)Two examples of events which can trigger the health alert are shown below, with the difference being their parent path.</span></span> <span data-ttu-id="00353-441">Eine Möglichkeit ist unter Web Service File Share zu finden, während die andere Möglichkeit das lokale Anwendungsdatenverzeichnis jedes Front-End ist.</span><span class="sxs-lookup"><span data-stu-id="00353-441">One possibility is under Web service file share, while the other possibility is the local Application Data directory of each front end.</span></span> <span data-ttu-id="00353-442">(Beispiel: c:\\ProgramData\\Microsoft\\lync Server\\StorageService).</span><span class="sxs-lookup"><span data-stu-id="00353-442">( for example c:\\ProgramData\\Microsoft\\Lync Server\\StorageService ).</span></span> <span data-ttu-id="00353-443">Der Administrator führt dann dieses reskit-Tool aus.</span><span class="sxs-lookup"><span data-stu-id="00353-443">The administrator will then run this reskit tool.</span></span>

<span data-ttu-id="00353-444">Dieses Tool erhöht die Auslastung von CPU und E/A-Vorgängen auf dem Front-End-Server, auf dem es ausgeführt wird, sowie auf anderen Front-End-Servern, wenn der Front-End-Server, auf dem das Tool ausgeführt wird, nicht Besitzer der Daten ist.</span><span class="sxs-lookup"><span data-stu-id="00353-444">This tool will increase CPU and IO load on the front end it is running on, as well as other front ends, in the situation that the data is not owned by the front end that the tool is executed on.</span></span> <span data-ttu-id="00353-445">Wir empfehlen die Ausführung dieses Tools, wenn die Auslastung von CPU und E/A-Vorgängen auf den Front-End-Servern niedrig ist, beispielsweise außerhalb der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="00353-445">We recommend runng this tool when front ends are not under heavy CPU and IO load, for example outside of peak hours.</span></span> <span data-ttu-id="00353-446">Darüber hinaus kann dieses Tool zwei bis drei Minuten für den Import einer Datendatei benötigen.</span><span class="sxs-lookup"><span data-stu-id="00353-446">Secondly, this tool can 2 to 3 minutes to import one data file.</span></span> <span data-ttu-id="00353-447">Beachten Sie Folgendes, wenn Sie schätzen, wie lange das Tool ausgeführt wird. Die vom Tool generierte ausführliche Protokolldatei wird standardmäßig im Dateispeicher angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-447">Keep this in mind when estimating how long tool will be running.The verbose log file generated by the tool will by default appear on the File Store.</span></span> <span data-ttu-id="00353-448">Löschen Sie sie, wenn darin keine Fehler gemeldet werden, da die Protokolldatei mehrere 10 MB übersteigen kann.</span><span class="sxs-lookup"><span data-stu-id="00353-448">Delete it if there are no errors reported, because the log file can be tens of MB or more.</span></span>

<span data-ttu-id="00353-449">![Beispiel Ereignisse für das Speicher Server-Ereignisprotokoll.] (images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Beispiel Ereignisse für das Speicher Server-Ereignisprotokoll.")</span><span class="sxs-lookup"><span data-stu-id="00353-449">![Sample Storage Server event log events.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Sample Storage Server event log events.")</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-450">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="00353-450">Requirements</span></span>

<span data-ttu-id="00353-451">Installieren Sie die lync Server 2013, Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="00353-451">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="00353-452">Das Tool wird auf Domänen verbundenen Computern ausgeführt, auf denen lync Server und lync Server-Verwaltungsshell installiert sind.</span><span class="sxs-lookup"><span data-stu-id="00353-452">The tool runs on domain-joined machines where Lync Server and Lync Server Management Shell are installed.</span></span> <span data-ttu-id="00353-453">Das Tool verwendet ein Cmdlet aus der Verwaltungsshell, um alle Front-End-Server im Pool zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="00353-453">The tool uses a cmdlet from the management shell to identify all the Front End servers in the pool.</span></span> <span data-ttu-id="00353-454">Zweitens muss das Tool von einem Computer im Pool ausgeführt werden, auf dem die **RtcLocal** -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-454">Secondly, the tool must be executed from a machine in the pool which has the **RtcLocal** database installed.</span></span> <span data-ttu-id="00353-455">Diese Datenbank wird vom Tool verwendet, um den Speicherort der Webservice-Dateifreigabe für den Pool abzurufen. Darüber hinaus muss jeder Front-End-Server vor der Verwendung des Tools zunächst Windows PowerShell-Remoting mithilfe von **enable-PSRemoting** auf jedem Front-End-Server und dem Computer aktivieren, von dem aus das Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="00353-455">This database is used by the tool to retrieve the location of the WEBSERVICE file share for the pool.Additionally, before using the tool, each Front End server must first enable Windows PowerShell Remoting using **Enable-PSRemoting** on each Front End server, as well as the machine that the tool is executed from.</span></span> <span data-ttu-id="00353-456">Andernfalls schlagen die Remote-Windows PowerShell-Befehle dieses Tools fehl.</span><span class="sxs-lookup"><span data-stu-id="00353-456">Otherwise, remote Windows PowerShell commands from this tool will fail.</span></span> <span data-ttu-id="00353-457">Windows PowerShell-Remoting kann auf allen Front-End-Servern im Pool deaktiviert werden, nachdem Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="00353-457">Windows PowerShell Remoting can be turned off on all Front End servers in the pool after it is finished.</span></span> <span data-ttu-id="00353-458">Schließlich muss das Konto oder die Anmeldeinformationen, die das Tool aufrufen, über die Berechtigung "Lesen/Schreiben" für die Webservice-Dateifreigabe für den Pool verfügen, auf dem dieses Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="00353-458">Finally, the account or credential invoking the tool must have read/write permission to the webservice file share for the pool they are executing this tool on.</span></span> <span data-ttu-id="00353-459">Andernfalls schlägt das Tool mit IO-Berechtigungsfehlern fehl.</span><span class="sxs-lookup"><span data-stu-id="00353-459">Otherwise the tool will fail with IO Permission errors.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-460">Unter Windows Server 2012 ist Windows PowerShell Remoting standardmäßig aktiviert, jedoch nicht unter dem BetriebssystemWindows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="00353-460">On Windows Server 2012, Windows PowerShell Remoting is enabled by default, but not on the Windows Server 2008 operating system.</span></span>



</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-461">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-461">Examples</span></span>

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

## <a name="lcssync"></a><span data-ttu-id="00353-462">LCSSync</span><span class="sxs-lookup"><span data-stu-id="00353-462">LCSSync</span></span>

<span data-ttu-id="00353-463">Das LCSSync-Tool hilft beim Bereitstellen von lync Server 2013-Kommunikationssoftware in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="00353-463">The LCSSync tool helps to deploy Lync Server 2013 communications software in a multi-forest environment.</span></span> <span data-ttu-id="00353-464">Dieses Tool wird verwendet, um Benutzer und Gruppen aus verschiedenen Benutzergesamtstrukturen als ein Active Directory-Domänendienst-Kontaktobjekt mit einer zentralen Gesamtstruktur zu synchronisieren, in der lync Server 2013 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-464">This tool is used to synchronize users and groups from different user forests as an Active Directory Domain Services contact object to a central forest where Lync Server 2013 is installed.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-465">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-465">Description</span></span>

<span data-ttu-id="00353-466">LCSSync verwendet die synchronisierten Active Directory-Domänendienste-Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer für lync Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="00353-466">LCSSync uses the synchronized Active Directory Domain Services contact objects in the central forest to enable users for Lync Server.</span></span> <span data-ttu-id="00353-467">Zum Bereitstelleneiner einmaligen Anmeldung muss das primäre Benutzerkonto dem Active Directory-Domänendienste-Kontaktobjekt in der zentralen Gesamtstruktur für lync Server 2013 zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="00353-467">To provide single sign-in, the primary user account must be mapped to the Active Directory Domain Services contact object in the central forest for Lync Server 2013.</span></span> <span data-ttu-id="00353-468">Dieses Tool hilft bei der Durchführung dieser Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="00353-468">This tool helps perform that mapping.</span></span> <span data-ttu-id="00353-469">Das Tool stellt Vorlagen zum Erstellen von Verwaltungs-Agents in Microsoft Identity Integration Server bereit.</span><span class="sxs-lookup"><span data-stu-id="00353-469">This tool provides templates for creating Management Agents in the Microsoft Identity Integration Server.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-470">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-470">Summary</span></span>

<span data-ttu-id="00353-471">Das LCSSync-Tool hilft beim Bereitstellen von lync Server in einer Umgebung mit mehreren Gesamtstrukturen.</span><span class="sxs-lookup"><span data-stu-id="00353-471">The LCSSync tool helps to deploy Lync Server in a multi-forest environment.</span></span>

</div>

</div>

<div>

## <a name="lookupuserconsole"></a><span data-ttu-id="00353-472">LookupUserConsole</span><span class="sxs-lookup"><span data-stu-id="00353-472">LookupUserConsole</span></span>

<span data-ttu-id="00353-473">Das LookupUserConsole-Tool zeigt interne lync Server-Routinginformationen zu bestimmten Benutzern an.</span><span class="sxs-lookup"><span data-stu-id="00353-473">The LookupUserConsole tool displays internal Lync Server routing information about specific users.</span></span> <span data-ttu-id="00353-474">Diese Informationen können den Mitarbeitern des Microsoft-Supports dabei helfen, Probleme bei der Bereitstellung und beim Routing zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="00353-474">This information may be useful to Microsoft support personal in diagnosing deployment and routing problems.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-475">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-475">Description</span></span>

<span data-ttu-id="00353-476">Beim Ausführen von "LookupUserConsole. exe" wird eine Eingabeaufforderung geöffnet, die SIP-Adressen akzeptiert, und versucht, interne lync Server-Routinginformationen in Bezug auf diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-476">Executing LookupUserConsole.exe will open a command prompt that accepts SIP addresses and attempts to display internal Lync Server routing information relating them.</span></span> <span data-ttu-id="00353-477">Geben Sie **exit** ein, um das LookupUserConsole-Tool zu beenden.</span><span class="sxs-lookup"><span data-stu-id="00353-477">Type **exit** to quit the LookupUserConsole tool.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-478">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-478">Requirements</span></span>

<span data-ttu-id="00353-479">Installieren Sie die lync Server 2013, Resource Kit-Tools.</span><span class="sxs-lookup"><span data-stu-id="00353-479">Install the Lync Server 2013, Resource Kit Tools.</span></span> <span data-ttu-id="00353-480">Das Tool wird auf von der Domäne verbundenen Computern ausgeführt, auf denen lync Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-480">The tool runs on domain-joined machines where Lync Server is installed</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-481">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-481">Examples</span></span>

<span data-ttu-id="00353-482">C:\\Programmdateien\\Microsoft lync Server 2013\\reskit\>LookupUserConsole. exe</span><span class="sxs-lookup"><span data-stu-id="00353-482">C:\\Program Files\\Microsoft Lync Server 2013\\ResKit\>LookupUserConsole.exe</span></span>

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

## <a name="msturnping"></a><span data-ttu-id="00353-483">MsTurnPing</span><span class="sxs-lookup"><span data-stu-id="00353-483">MsTurnPing</span></span>

<span data-ttu-id="00353-484">Mit dem MSTurnPing-Tool kann ein Administrator der Microsoft lync Server 2013-Kommunikationssoftware den Status der Server überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien ausgeführt werden. Dienste in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="00353-484">The MSTurnPing tool allows an administrator of Microsoft Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-485">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-485">Description</span></span>

<span data-ttu-id="00353-486">Das MSTurnPing-Tool ermöglicht einem Administrator der lync Server 2013-Kommunikationssoftware, den Status der Server zu überprüfen, auf denen die Audio/Video-Edge-und Audio/Video-Authentifizierungsdienste ausgeführt werden, sowie die Server, auf denen Bandbreitenrichtlinien Dienste ausgeführt werden, im Topologie.</span><span class="sxs-lookup"><span data-stu-id="00353-486">The MSTurnPing tool allows an administrator of Lync Server 2013 communications software to check the status of the servers running the Audio/Video Edge and Audio/Video Authentication services as well as the servers that are running Bandwidth Policy Services in the topology.</span></span>

<span data-ttu-id="00353-487">Mit dem Tool können Administratoren die folgenden Tests durchführen:</span><span class="sxs-lookup"><span data-stu-id="00353-487">The tool allows the administrator to perform the following tests:</span></span>

1.  <span data-ttu-id="00353-488">A/V-Edgeservertest: Das Tool führt mit allen A/V-Edgeservern in der Topologie die folgenden Tests durch:</span><span class="sxs-lookup"><span data-stu-id="00353-488">A/V Edge Server test: The tool performs tests against all A/V Edge Servers in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="00353-489">Vergewissern Sie sich, dass der lync Server-Audio/Video-Authentifizierungsdienst gestartet wurde, und können Sie die richtigen Anmeldeinformationen ausgeben.</span><span class="sxs-lookup"><span data-stu-id="00353-489">Verifying that the Lync Server Audio/Video Authentication service is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="00353-490">Überprüfen, ob der lync Server-Audio/Video-Edgedienst gestartet wurde und die Ressourcen auf dem externen Edge erfolgreich zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="00353-490">Verifying that the Lync Server Audio/Video Edge service is started and can allocate the resources on the external edge successfully.</span></span>

2.  <span data-ttu-id="00353-491">Test für Bandbreiten-Richtliniendienste: Das Tool führt mit allen Servern in der Topologie, auf denen die Bandbreiten-Richtliniendienste ausgeführt werden, die folgenden Tests durch:</span><span class="sxs-lookup"><span data-stu-id="00353-491">Bandwidth Policy Service test: The tool performs tests against all the servers that are running the Bandwidth Policy Services in the topology by doing the following:</span></span>
    
      - <span data-ttu-id="00353-492">Überprüfen, ob der lync Server-bandbreitenrichtliniendienst (Authentication) gestartet wurde und geeignete Anmeldeinformationen ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="00353-492">Verifying that the Lync Server Bandwidth Policy Service (Authentication) is started and can issue proper credentials.</span></span>
    
      - <span data-ttu-id="00353-493">Überprüfen, ob der lync Server-bandbreitenrichtliniendienst (Core) gestartet wurde und die Bandbreiten Überprüfung erfolgreich durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="00353-493">Verifying that the Lync Server Bandwidth Policy Service (Core) is started and can perform the bandwidth check successfully.</span></span>

<span data-ttu-id="00353-494">Dieses Tool muss auf einem Computer ausgeführt werden, der Teil der Topologie ist und auf dem der lokale Speicher installiert ist. </span><span class="sxs-lookup"><span data-stu-id="00353-494">This tool must be run from a computer that is part of the topology and has the local store installed.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-495">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-495">Output</span></span>

<span data-ttu-id="00353-496">Das Tool gibt die Ergebnisse der einzelnen Vorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="00353-496">The tool outputs the results of each of the operations.</span></span>

  - <span data-ttu-id="00353-497">Wenn der **AudioVideoEdgeServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="00353-497">If the **AudioVideoEdgeServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="00353-498">Die Testergebnisse der Computer, die den lync Server-Audio/Video-Authentifizierungsdienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="00353-498">The test results of the computers that provide the Lync Server Audio/Video Authentication service in the topology</span></span>
    
      - <span data-ttu-id="00353-499">Die Testergebnisse der Computer, die den lync Server-Audio/Video-Edgedienst in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="00353-499">The test results of the computers that provide the Lync Server Audio/Video Edge service in the topology</span></span>

  - <span data-ttu-id="00353-500">Wenn der **BandwidthPolicyServer**-Test durchgeführt wird, gibt das Tool Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="00353-500">If the **BandwidthPolicyServer** test is performed, the tool outputs are the following:</span></span>
    
      - <span data-ttu-id="00353-501">Die Testergebnisse der Computer, die den lync Server-bandbreitenrichtliniendienst (Authentifizierung) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="00353-501">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Authentication) in the topology</span></span>
    
      - <span data-ttu-id="00353-502">Die Testergebnisse der Computer, die den lync Server-bandbreitenrichtliniendienst (Core) in der Topologie bereitstellen</span><span class="sxs-lookup"><span data-stu-id="00353-502">The test results of the computers that provide the Lync Server Bandwidth Policy Service (Core) in the topology</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-503">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-503">Requirements</span></span>

  - <span data-ttu-id="00353-504">Dieses Tool muss auf einem Computer ausgeführt werden, der zur Topologie gehört und auf dem sich der lokale Speicher befindet.</span><span class="sxs-lookup"><span data-stu-id="00353-504">This tool must be run from a computer that is in the topology and that has the local store.</span></span>

  - <span data-ttu-id="00353-505">Das Tool muss als Administrator mit Zugriff auf den lokalen Speicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-505">The tool must be run as an administrator who has access to the local store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-506">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-506">Examples</span></span>

<span data-ttu-id="00353-507">Hier ist ein Beispiel für die Tooleingabe.</span><span class="sxs-lookup"><span data-stu-id="00353-507">The following is an example of the tool input.</span></span>

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-508">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-508">Summary</span></span>

<span data-ttu-id="00353-509">Dieses Tool kann eine wertvolle Ressource für lync Server 2013-Administratoren sein, die den Status der Server überprüfen möchten, auf denen Audio/Video-und Bandbreitenrichtlinien Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-509">This tool can be a valuable resource to Lync Server 2013 administrators who want to check the status of the servers that are running audio/video and bandwidth policy services.</span></span>

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a><span data-ttu-id="00353-510">Network Configuration Viewer</span><span class="sxs-lookup"><span data-stu-id="00353-510">Network Configuration Viewer</span></span>

<span data-ttu-id="00353-511">Die Netzwerkkonfigurations-Anzeige kann von Microsoft lync Server 2013-Kommunikationssoftware Administratoren verwendet werden, um die Anruf Zulassungs Steuerung (CAC)-Netzwerktopologie für ein Unternehmen anzuzeigen, das bereitgestellt wird, um Echt Zeit Kommunikationssitzungen zu ermöglichen, wie etwa sprach-oder Videoanrufe auf der Grundlage der angegebenen Bandbreitenkapazität.</span><span class="sxs-lookup"><span data-stu-id="00353-511">Network Configuration Viewer can be used by Microsoft Lync Server 2013 communications software administrators to view call admission control (CAC) network topology for an enterprise that is provisioned to allow real-time communication sessions, such as voice or video calls based on specified bandwidth capacity.</span></span> <span data-ttu-id="00353-512">Lync Server 2013-Administratoren definieren CAC-Richtlinien, die von den Bandbreitenrichtlinien Diensten erzwungen werden, die mit lync Server 2013 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-512">Lync Server 2013 administrators define CAC policies, which are enforced by the Bandwidth Policy services that are installed with Lync Server 2013.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-513">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-513">Description</span></span>

<span data-ttu-id="00353-514">Mit Network Configuration Viewer („NetworkConfigurationViewer.exe“) können Administratoren die folgenden Aufgaben durchführen:</span><span class="sxs-lookup"><span data-stu-id="00353-514">Network Configuration Viewer (NetworkConfigurationViewer.exe) allows administrators to perform the following tasks:</span></span>

  - <span data-ttu-id="00353-515">Laden und Anzeigen der CAC-Netzwerktopologie aus einer lync Server 2013-Bereitstellung in einem grafischen Format</span><span class="sxs-lookup"><span data-stu-id="00353-515">Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format.</span></span>

  - <span data-ttu-id="00353-516">Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinienserver-Protokolldatei in einem Grafikformat</span><span class="sxs-lookup"><span data-stu-id="00353-516">Load and view CAC network topology from a Bandwidth Policy Server log file in a graphical format.</span></span>

  - <span data-ttu-id="00353-517">Sichern und Speichern der CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger</span><span class="sxs-lookup"><span data-stu-id="00353-517">Save and store CAC network topology in an XML format on the disk.</span></span>

  - <span data-ttu-id="00353-518">Sichern und Speichern des CAC-Netzwerktopologiediagramms im JPG- oder BMP-Format</span><span class="sxs-lookup"><span data-stu-id="00353-518">Save and store CAC network topology diagram in JPG or BMP format.</span></span>

  - <span data-ttu-id="00353-519">Anzeigen von Konfigurationsdaten der CAC-Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="00353-519">View CAC network topology configuration data.</span></span>

  - <span data-ttu-id="00353-520">Anzeigen der CAC-Netzwerktopologie in einer Strukturansicht</span><span class="sxs-lookup"><span data-stu-id="00353-520">View CAC network topology in a tree-view style.</span></span>

  - <span data-ttu-id="00353-521">Definieren benutzerdefinierter Connectors für Verbindungen in der CAC-Netzwerktopologie (beispielsweise Standort-zu-Region-, Region-zu-Region- oder Standort-zu-Standort-Verbindungen)</span><span class="sxs-lookup"><span data-stu-id="00353-521">Define custom connectors for CAC network topology links (for example, site-to-region, region-to-region, and site-to-site links).</span></span>

  - <span data-ttu-id="00353-522">Anzeigen von CAC-Netzwerktopologie-Standortinformationen, -Regionsinformationen und bereitgestellten Bandbreitenrichtlinien und Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="00353-522">View CAC network topology site information, region Information, and provisioned bandwidth policies and network links.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-523">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-523">Purpose</span></span>

<span data-ttu-id="00353-524">Anzeigen der Verbindungen in der CAC-Netzwerktopologie des Unternehmens auf einer grafischen Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="00353-524">View enterprise CAC network topology links in a graphical interface.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-525">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-525">Examples</span></span>

<span data-ttu-id="00353-526">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer lync Server 2013-Bereitstellung in einem grafischen Format:** Lync Server 2013-Administratoren können die Konfiguration der CAC-Netzwerktopologie auf jedem lync Server 2013-Computer mithilfe der Option **Netzwerkkonfiguration herunterladen** wie in der folgenden Abbildung gezeigt laden und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-526">**Load and view CAC network topology from a Lync Server 2013 deployment in a graphical format:** Lync Server 2013 administrators can load and view CAC network topology configuration on any Lync Server 2013 computer by using the **Download Network Configuration** option as shown in the figure below.</span></span> <span data-ttu-id="00353-527">Bei der Bereitstellung auf einem Computer, der keine Verbindung zum lync-Konfigurationsspeicher hat, kann das Tool keine derartige Konfiguration herunterladen oder anzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-527">The tool will fail to download or view such a configuration when deployed on a computer that does not have connectivity to the Lync configuration store.</span></span>

<span data-ttu-id="00353-528">![Herunterladen der Netzwerkkonfiguration.] (images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Herunterladen der Netzwerkkonfiguration.")</span><span class="sxs-lookup"><span data-stu-id="00353-528">![Downloading the network configuration.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Downloading the network configuration.")</span></span>

<span data-ttu-id="00353-529">**Laden und Anzeigen der CAC-Netzwerktopologie aus einer Bandbreitenrichtlinien Server-Protokolldatei in einem grafischen Format:** Lync Server 2013-Bandbreitenrichtlinien Server speichern die CAC-Netzwerktopologie als Teil des Protokollierungsmechanismus unter dem Dateifreigabespeicherort von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00353-529">**Load and View CAC network topology from a Bandwidth Policy server log file in a graphical format:** Lync Server 2013 Bandwidth Policy servers save the CAC network topology as a part of the logging mechanism under the Lync Server 2013 file share location.</span></span> <span data-ttu-id="00353-530">Lync Server-Administratoren können eine solche Datei in einem grafischen Format anzeigen, indem Sie die Option **Netzwerkkonfiguration öffnen** verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-530">Lync Server administrators can view such a file in a graphical format by using the **Open Network Configuration** option as shown below.</span></span>

<span data-ttu-id="00353-531">![Öffnen einer Protokolldatei für den Bandbreitenrichtlinien Server] (images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Öffnen einer Protokolldatei für den Bandbreitenrichtlinien Server")</span><span class="sxs-lookup"><span data-stu-id="00353-531">![Opening a Bandwidth Policy Server log file.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Opening a Bandwidth Policy Server log file.")</span></span>

<span data-ttu-id="00353-532">Speichern und speichern Sie die CAC-Netzwerktopologie in einem XML-Format auf dem Datenträger: lync Server 2013-Administratoren können die Konfigurationsdatei der CAC-Netzwerktopologie in einem XML-Format speichern, indem Sie die Option **Kopie der Netzwerkkonfiguration speichern** verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-532">Save and store CAC network topology in an XML format on the disk: Lync Server 2013 administrators can save the CAC network topology configuration file in an XML format by using the **Save a copy of Network Configuration** option as shown below.</span></span> <span data-ttu-id="00353-533">Die gespeicherte Konfigurationsdatei kann dann offline als Grafik angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-533">The saved configuration file can then be used offline for graphical viewing purposes.</span></span>

<span data-ttu-id="00353-534">![Speichern Sie die Netzwerkkonfiguration als XML-Datei.] (images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Speichern Sie die Netzwerkkonfiguration als XML-Datei.")</span><span class="sxs-lookup"><span data-stu-id="00353-534">![Saving the network configuration as an XML file.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Saving the network configuration as an XML file.")</span></span>

<span data-ttu-id="00353-535">Speichern und Speichern der CAC-Netzwerktopologie im JPG-oder BMP-Format: lync Server 2013-Administratoren können die Konfiguration der CAC-Netzwerktopologie in einem grafischen Format (JPG-und BMP-Dateiformate) speichern, indem Sie das **Diagramm "Netzwerkkonfiguration speichern als Bild** " verwenden. (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="00353-535">Save and Store CAC network topology diagram in JPG or BMP format: Lync Server 2013 administrators can save the CAC network topology configuration in a graphical format (JPG and BMP file formats) by using the **Save Network Configuration diagram as picture** option as shown below.</span></span>

<span data-ttu-id="00353-536">![Speichern der Netzwerkkonfiguration als Bild] (images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Speichern der Netzwerkkonfiguration als Bild")</span><span class="sxs-lookup"><span data-stu-id="00353-536">![Saving the network configuration as a picture.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Saving the network configuration as a picture.")</span></span>

<span data-ttu-id="00353-537">**Anzeigen der Konfigurationsdaten der CAC-Netzwerktopologie:** Lync Server 2013-Administratoren können verwandte Netzwerkkonfigurationsdaten wie netzwerkregionen, Netzwerk Websites, Bandbreiten Profile und IP-Adressen von Standort-Subnetzen in einem Text Format anzeigen, indem Sie die Option Netzwerkkonfigurationsdaten anzeigen verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-537">**View CAC network topology configuration data:** Lync Server 2013 administrators can view related network configuration data such as network regions, network sites, bandwidth profiles, and site subnet IP addresses in a textual format by using the View Network Configuration data option as shown below.</span></span>

<span data-ttu-id="00353-538">![Anzeigen von Netzwerkkonfigurationsdaten] (images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten")</span><span class="sxs-lookup"><span data-stu-id="00353-538">![Viewing network configuration data.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Viewing network configuration data.")</span></span>

<span data-ttu-id="00353-539">**Anzeigen der CAC-Netzwerktopologie in einer Struktur Ansichtsformatvorlage:** Lync Server 2013-Administratoren können verwandte Netzwerkkonfigurationsdaten in einem grafischen Struktur Ansichtsformat anzeigen, indem Sie die Systemsteuerung auf der linken Seite des Toolfensters verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-539">**View CAC network topology in a tree-view style:** Lync Server 2013 administrators can view related network configuration data in a graphical tree view style by using the control panel on the left side of the tool window as shown below.</span></span>

<span data-ttu-id="00353-540">![Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht] (images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Anzeigen von Netzwerkkonfigurationsdaten in einer Strukturansicht")</span><span class="sxs-lookup"><span data-stu-id="00353-540">![Viewing network configuration data in a tree-view.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Viewing network configuration data in a tree-view.")</span></span>

<span data-ttu-id="00353-541">**Definieren von benutzerdefinierten Connectors für CAC-Netzwerktopologie-Links (wie Website-zu-Region-, Region-zu-Region-und Standort-zu-Standort-Links):** Lync Server 2013-Administratoren können benutzerdefinierte grafische Connectors für CAC-Netzwerkkonfigurations-WAN-Links definieren, indem Sie die Option Einstellungen verwenden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-541">**Define custom connectors for CAC network topology links (such as site-to-region, region-to-region, and site-to-site links):** Lync Server 2013 administrators can define custom graphical connectors for CAC network configuration WAN links by using the Settings option as shown below.</span></span> <span data-ttu-id="00353-542">Dies erleichtert die Unterscheidung zwischen verschiedenen Netzwerkverbindungstypen, die in der Netzwerkkonfiguration bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="00353-542">This helps differentiate between various types of network links that are provisioned in the network configuration.</span></span>

<span data-ttu-id="00353-543">![Definieren von benutzerdefinierten Connectors für die CAC-Netzwerktopologie] (images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für die CAC-Netzwerktopologie")</span><span class="sxs-lookup"><span data-stu-id="00353-543">![Define custom connectors for CAC network topology](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Define custom connectors for CAC network topology")</span></span>

<span data-ttu-id="00353-544">**Anzeigen der Informationen zur CAC-Netzwerktopologie, der Regionsinformationen und der bereitgestellten Bandbreitenrichtlinien:** Lync Server 2013-Administratoren können verwandte CAC-Netzwerk Regionsinformationen, Website Informationen und Informationen zur Bereitstellung von CAC-Bandbreiten mithilfe der nachstehend aufgeführten Optionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-544">**View CAC network topology site information, region information, and provisioned bandwidth policies:** Lync Server 2013 administrators can view related CAC network region information, site information, and CAC bandwidth provisioning information by using options shown below.</span></span> <span data-ttu-id="00353-545">(Klicken Sie beispielsweise in einer Netzwerkregion oder einem Netzwerkstandortobjekt auf **Info**.)</span><span class="sxs-lookup"><span data-stu-id="00353-545">(For example, click **Info** in a network region or network site object.)</span></span>

<span data-ttu-id="00353-546">![Definieren von benutzerdefinierten Connectors für Ihr Netzwerk] (images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definieren von benutzerdefinierten Connectors für Ihr Netzwerk")</span><span class="sxs-lookup"><span data-stu-id="00353-546">![Defining custom connectors for your network.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Defining custom connectors for your network.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-547">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-547">Summary</span></span>

<span data-ttu-id="00353-548">Dieses Tool kann eine wertvolle Ressource für lync Server 2013-Administratoren sein, die die CAC-Netzwerktopologie für Ihre Bereitstellung in einem grafischen Format anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="00353-548">This tool can be a valuable resource to Lync Server 2013 administrators who would like to view CAC network topology for their deployment in a graphical format.</span></span>

</div>

</div>

<div>

## <a name="response-group-agent-live"></a><span data-ttu-id="00353-549">Response Group Agent Live</span><span class="sxs-lookup"><span data-stu-id="00353-549">Response Group Agent Live</span></span>

<span data-ttu-id="00353-550">Die reaktionsgruppenanwendung bietet Agents die Möglichkeit, mithilfe des integrierten Webdiensts auf nützliche Echtzeitinformationen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="00353-550">The Response Group application gives agents the ability to access useful real-time information using its built-in Web service.</span></span> <span data-ttu-id="00353-551">Leider ist keine grafische Ansicht dieser Daten außerhalb der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="00353-551">Unfortunately, no graphical view of this data is available outside the application.</span></span> <span data-ttu-id="00353-552">Das Tool für den Reaktionsgruppen-Agent Live Resource Kit löst dieses Problem, indem es eine einfache und grafische Möglichkeit bietet, auf diese Informationen zuzugreifen, die mit Microsoft lync 2013-Kommunikationssoftware Informationen wie dem vorhanden sein anderer Agents verbessert wurde.</span><span class="sxs-lookup"><span data-stu-id="00353-552">The Response Group Agent Live Resource Kit tool solves this issue by providing a simple and graphical way to access this information, enhanced with real-time Microsoft Lync 2013 communications software information such as the presence of other agents.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-553">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-553">Description</span></span>

<span data-ttu-id="00353-554">Response Group Agent Live ist eine Windows-Anwendung, die An- und Abmeldefunktionen sowie einige Echtzeitinformationen (wie Gruppenmitgliedschaft und aktuelle Anzahl von Anrufen) für Reaktionsgruppen-Agents bietet.</span><span class="sxs-lookup"><span data-stu-id="00353-554">Response Group Agent Live is a Windows application that provides sign-in and sign-out functionality and some real-time information (such as group membership and current number of calls) to Response Group agents.</span></span> <span data-ttu-id="00353-555">Es handelt sich um eine erweiterte Version der Seite "Agentengruppen" (auf die von lync 2013 aus zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="00353-555">It is meant to be an enhanced version of the Agent Groups page (accessible from Lync 2013.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-556">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-556">Purpose</span></span>

<span data-ttu-id="00353-p165">Die Reaktionsgruppenanwendung stellt eingehende Anrufe in die Warteschleife und leitet sie dann an Agent-Gruppen weiter. Um informierte Entscheidungen darüber treffen zu können, welche Anrufe bedient werden sollen, können Agents auf Echtzeitinformationen zu ihren Agent-Gruppen zugreifen. Dabei erfahren sie beispielsweise, welche anderen Agents verfügbar sind und wie viele Anrufe in jeder Warteschleife warten. Diese Informationen, die anfänglich nur über den Reaktionsgruppendienst verfügbar sind, werden auf intuitive Weise von Response Group Agent Live zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-p165">The Response Group application queues incoming calls, and then routes them to agent groups. To make informed decisions about which calls to service, agents can access real-time information about their agent groups, such as what other agents are available and how many calls are waiting in each queue. This information, initially accessible only through the Response Group service, is made available in an intuitive way by Response Group Agent Live.</span></span>

<div>

## <a name="features"></a><span data-ttu-id="00353-560">Funktionen</span><span class="sxs-lookup"><span data-stu-id="00353-560">Features</span></span>

<span data-ttu-id="00353-561">Das Live Tool für Reaktionsgruppen-Agents basiert auf dem Reaktionsgruppendienst und dem Microsoft lync 2013 SDK.</span><span class="sxs-lookup"><span data-stu-id="00353-561">The Response Group Agent Live tool is built on the Response Group service and the Microsoft Lync 2013 SDK.</span></span> <span data-ttu-id="00353-562">Es bietet Reaktionsgruppen-Agents die Informationen und Funktionen, die durch den Reaktionsgruppendienst zur Verfügung gestellt werden (beispielsweise Gruppenmitgliedschaft, Anwesenheit anderer Agents und Anzahl der wartenden Anrufe).</span><span class="sxs-lookup"><span data-stu-id="00353-562">It provides Response Group agents the information and capabilities that are available from the Response Group service (such as group membership, presence of other agents, and number of waiting calls).</span></span>

<span data-ttu-id="00353-563">Die Abbildung unten zeigt die Hauptoberfläche von Response Group Agent Live.</span><span class="sxs-lookup"><span data-stu-id="00353-563">The figure below illustrates the main interface of Response Group Agent Live.</span></span>

<span data-ttu-id="00353-564">![Das Live Tool für Reaktionsgruppen-Agents] (images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Das Live Tool für Reaktionsgruppen-Agents")</span><span class="sxs-lookup"><span data-stu-id="00353-564">![The Response Group Agent Live tool.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "The Response Group Agent Live tool.")</span></span>

<span data-ttu-id="00353-565">Folgende drei Hauptfeatures stehen Agents in Response Group Agent Live zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="00353-565">The following three main features are available for agents in Response Group Agent Live:</span></span>

  - <span data-ttu-id="00353-566">**Anmeldung/** Abmeldung: Im Gegensatz zur Seite "Agentengruppen" (auf die von lync 2013 aus zugegriffen werden kann) kann der Reaktionsgruppen-Agent Live nur die Anmeldung oder Abmeldung aller Agentengruppen gleichzeitig ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="00353-566">**Sign-in/out:** Contrary to the Agent Groups page (accessible from Lync 2013), Response Group Agent Live allows only agents to sign-in or out of all agent groups at once.</span></span> <span data-ttu-id="00353-567">Diese Anwendung bietet drei schnelle Methoden zum Anmelden oder Abmelden für Agents:</span><span class="sxs-lookup"><span data-stu-id="00353-567">This application provides three quick ways for agents to sign in or out:</span></span>
    
      - <span data-ttu-id="00353-568">Klicken auf die Schaltflächen zum An-/Abmelden (grün und rot) in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="00353-568">Click the Sign-in/out (green and red) buttons within the application.</span></span>
    
      - <span data-ttu-id="00353-569">Klicken auf das Taskleistensymbol mit der rechten Maustaste und Auswählen von „Sign-in“ oder „Sign-out“</span><span class="sxs-lookup"><span data-stu-id="00353-569">Right-click the system tray icon, and select sign in or sign out.</span></span>
    
      - <span data-ttu-id="00353-570">Verwenden konfigurierbarer Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="00353-570">Using configurable keyboard shortcuts.</span></span>

  - <span data-ttu-id="00353-571">**Gruppenmitgliedschaft:** Wenn eine Agentengruppe ausgewählt ist, zeigt der Reaktionsgruppen-Agent Live die Liste der Agents in dieser Gruppe im rechten Bereich an.</span><span class="sxs-lookup"><span data-stu-id="00353-571">**Group membership:** When an agent group is selected, Response Group Agent Live displays the list of agents in this group in the right pane.</span></span> <span data-ttu-id="00353-572">Wenn lync 2013 auf demselben Computer wie diese Anwendung ausgeführt wird, werden Anwesenheitsinformationen und die Visitenkarte im Reaktionsgruppen-Agent Live angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-572">If Lync 2013 is running on the same computer as this application, presence information and the contact card are displayed in the Response Group Agent Live.</span></span> <span data-ttu-id="00353-573">Agents können direkt von dort aus eine Chatnachricht senden oder andere Agents anrufen.</span><span class="sxs-lookup"><span data-stu-id="00353-573">Agents can send an IM or call other agents directly from there.</span></span>

  - <span data-ttu-id="00353-p169">**Echtzeitstatistiken:** Response Group Agent Live bietet Echtzeitstatistiken für alle Agent-Gruppen. Die Statistiken werden minütlich aktualisiert. Wenn ein Anruf von einer Reaktionsgruppe beantwortet wird, wird neben dem Gruppennamen ein optischer Indikator mit der aktuellen Anzahl der wartenden Anrufe hinzugefügt. Wenn Sie mit dem Mauszeiger auf einer Gruppe verweilen, wird außerdem die längste Wartezeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-p169">**Real-time statistics:** Response Group Agent Live provides real-time statistics for all agent groups. The update frequency is one minute. When a call is answered by a Response Group, a visual indicator is added next to the group name with the current number of queued calls. Pausing the pointer over a group also displays the longest waiting time.</span></span>

</div>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-578">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-578">Requirements</span></span>

<span data-ttu-id="00353-579">Response Group Agent Live erfordert .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="00353-579">Response Group Agent Live requires the .NET Framework 4.0.</span></span> <span data-ttu-id="00353-580">Um die Anwesenheits-und Visitenkarten Features nutzen zu können, muss lync 2013 auch lokal installiert sein (und ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="00353-580">In addition, to take advantage of the presence and contact card features, Lync 2013 must be installed locally (and be running).</span></span>

<div>

## <a name="configuration"></a><span data-ttu-id="00353-581">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="00353-581">Configuration</span></span>

<span data-ttu-id="00353-p171">Response Group Agent Live kann mithilfe des Dialogfelds „Options“ in der Anwendung an die individuellen Anforderungen angepasst werden. Darüber hinaus können Administratoren die Standardhostadresse definieren, indem sie die Eigenschaft „defaultHostAddress“ in der Datei „RGAgentLive.exe.config“ direkt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="00353-p171">Response Group Agent Live can be customized to individual preferences by using the Options dialog box in the application. In addition, the administrator can define the default host address by editing directly the defaultHostAddress property of the RGAgentLive.exe.config file.</span></span>

<span data-ttu-id="00353-p172">Die Abbildung unten zeigt das Dialogfeld „Options“, in dem Agents die Hostadresse und Tastenkombinationen konfigurieren können. Auf dieses Dialogfeld können Sie zugreifen, indem Sie auf der Hauptbenutzeroberfläche rechts oben auf die Schaltfläche „Options“ klicken.</span><span class="sxs-lookup"><span data-stu-id="00353-p172">The figure below illustrates the Options dialog box that agents can use to configure the host address and shortcut keys. This dialog is accessed by clicking the Options button on the top right of the main interface.</span></span>

<span data-ttu-id="00353-586">![Das Dialogfeld "Live Optionen" des Reaktionsgruppen-Agents] (images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "Das Dialogfeld \"Live Optionen\" des Reaktionsgruppen-Agents")</span><span class="sxs-lookup"><span data-stu-id="00353-586">![The Response Group Agent Live Options dialog box.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "The Response Group Agent Live Options dialog box.")</span></span>

<span data-ttu-id="00353-587">Folgende drei unterschiedliche Einstellungen können in der Konfiguration von Response Group Agent Live angepasst werden:</span><span class="sxs-lookup"><span data-stu-id="00353-587">The following three different settings can be customized in the Response Group Agent Live configuration:</span></span>

  - <span data-ttu-id="00353-p173">Hostadresse: Dies ist normalerweise der FQDN des Webpools, der zum Home-Pool des Agents gehört. Die genaue Adresse des Reaktionsgruppendiensts wird automatisch im Hintergrund aus diesen Informationen abgeleitet (durch Anfügen des richtigen Pfads an den Host).</span><span class="sxs-lookup"><span data-stu-id="00353-p173">Host address: This is typically the web pool FQDN belonging to the agent’s home pool. The exact Response Group service address is automatically derived in the background from this information (by appending the right path after the host).</span></span>

  - <span data-ttu-id="00353-p174">Tastenkombinationen: Die genauen Tastenkombinationen zum An- und Abmelden können angepasst werden. Die einzige Einschränkung besteht darin, dass beide Tastenkombinationen die Windows-Logo-Taste enthalten müssen (zusätzlich zu mindestens einer weiteren Taste).</span><span class="sxs-lookup"><span data-stu-id="00353-p174">Shortcuts: The exact shortcuts to sign-in/out can be customized. The only limitation is that both shortcuts must contain the “Windows Logo” key (in addition to at least another key).</span></span>

  - <span data-ttu-id="00353-592">Starten mit Windows: Die Anwendung kann so konfiguriert werden, dass sie automatisch beim Starten von Windows gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="00353-592">Start with Windows: The application can be configured to start automatically with Windows.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-593">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-593">Examples</span></span>

<span data-ttu-id="00353-594">Die Abbildung unten zeigt, wie Sie andere Agents anrufen oder ihnen eine Chatnachricht senden, indem Sie mit der rechten Maustaste im rechten Bereich auf den Kontakt klicken.</span><span class="sxs-lookup"><span data-stu-id="00353-594">The figure below illustrates how to call or send an IM to another agent by right-clicking the contact in the right pane.</span></span>

<span data-ttu-id="00353-595">![Tätigen eines Anrufs oder Senden einer Chatnachricht] (images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Tätigen eines Anrufs oder Senden einer Chatnachricht")</span><span class="sxs-lookup"><span data-stu-id="00353-595">![Making a call or sending an IM.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Making a call or sending an IM.")</span></span>

<span data-ttu-id="00353-596">Die Abbildung unten zeigt, wie Response Group Agent Live die aktuelle Anzahl der Anrufe in der Warteschleife sowie die längste Wartezeit all dieser eingehenden Anrufe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="00353-596">The figure below illustrates how Response Group Agent Live displays the current number of calls in the queue and the longest waiting time among all these incoming calls.</span></span>

<span data-ttu-id="00353-597">![Anzeigen von Warteschlangeninformationen] (images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Anzeigen von Warteschlangeninformationen")</span><span class="sxs-lookup"><span data-stu-id="00353-597">![Viewing queue information.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Viewing queue information.")</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-598">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-598">Summary</span></span>

<span data-ttu-id="00353-599">Schnelles An- und Abmelden, Gruppenmitgliedschaft und grundlegende Echtzeitstatistiken sind interessante Funktionen für Reaktionsgruppen-Agents, die nur außerhalb der Anwendung über den Reaktionsgruppendienst verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="00353-599">Fast sign-in and sign-out, group membership, and basic real-time statistics are interesting Response Group agent features that are only available outside the application from the Response Group service.</span></span> <span data-ttu-id="00353-600">Mit dem Live Resource Kit-Tool für Reaktionsgruppen-Agents können lync-Administratoren ihren Agents eine Windows-Anwendung zur Verfügung stellen, die es Ihnen ermöglicht, Aufgaben auf eine schnellere und grafische Weise durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="00353-600">With the Response Group Agent Live Resource Kit tool, Lync administrators can provide their agents with a Windows application that allows them to perform tasks in a faster and graphical way.</span></span>

</div>

</div>

<div>

## <a name="sefautil"></a><span data-ttu-id="00353-601">SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="00353-601">SEFAUtil</span></span>

<span data-ttu-id="00353-602">SEFAUtil (Secondary Extension Feature Activation) ist ein Befehlszeilentool, mit dem Microsoft lync Server 2013 Communications Software-Administratoren und Helpdesk-Agents Stellvertretungen, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anruf konfigurieren können. Einstellungen und Gruppenanruf Abholung im Auftrag eines lync Server 2013-Benutzers.</span><span class="sxs-lookup"><span data-stu-id="00353-602">SEFAUtil (secondary extension feature activation) is a command-line tool that enables Microsoft Lync Server 2013 communications software administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="00353-603">Das Tool ermöglicht es Administratoren auch, die für einen bestimmten Benutzer veröffentlichten Anrufweiterleitungseinstellungen abzufragen. Das SEFAUtil-Tool ermöglicht es dem Administrator, die Anrufweiterleitung zu aktivieren/zu deaktivieren/zu ändern oder gleichzeitig im Namen des Benutzers Klingeln zu lassen.</span><span class="sxs-lookup"><span data-stu-id="00353-603">The tool also allows administrators to query the call-routing settings that are published for a particular user.The SEFAUtil tool allows the administrator to enable/disable/modify call forwarding or simultaneously ringing on behalf of the user.</span></span> <span data-ttu-id="00353-604">Der Administrator kann das Ziel (in Form eines SIP-URIs) angeben oder ein Ziel verwenden, das bereits vom Benutzer veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="00353-604">The administrator can specify the target (in the form of a SIP URI) or use a target that has already been published by the user.</span></span> <span data-ttu-id="00353-605">Dieses Tool ermöglicht es Administratoren auch, Stellvertretungen oder Teamanrufgruppen Mitglieder im Namen des Benutzers hinzuzufügen oder zu entfernen. Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0 und erfordert, dass Administratoren eine vertrauenswürdige Anwendung im zentralen Verwaltungsspeicher für SEFAUtil erstellen.</span><span class="sxs-lookup"><span data-stu-id="00353-605">This tool also allows administrators to add or remove delegates or team-call group members on behalf of the user.This tool is built on Microsoft Unified Communications Managed API (UCMA) 3.0 and requires that administrators create a trusted application in the Central Management store for SEFAUtil</span></span>

<span data-ttu-id="00353-606">SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht lync Server 2013-Administratoren und Helpdesk-Agents die Konfiguration von Delegate-Ringing, Anrufweiterleitung, gleichzeitiges Klingeln, Team Anrufeinstellungen und Abholung von Gruppen anrufen im Auftrag eines lync Server 2013-Benutzers .</span><span class="sxs-lookup"><span data-stu-id="00353-606">SEFAUtil (secondary extension feature activation) enables Lync Server 2013 administrators and helpdesk agents to configure delegate-ringing, call-forwarding, simultaneous ringing, team-call settings and group call pickup on behalf of a Lync Server 2013 user.</span></span> <span data-ttu-id="00353-607">Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.</span><span class="sxs-lookup"><span data-stu-id="00353-607">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-608">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-608">Description</span></span>

<span data-ttu-id="00353-609">Die aktuelle Version von SEFAUtil ist nur ein Befehlszeilentool; Es gibt keine unterstützende grafische Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="00353-609">The current version of SEFAUtil is only a command-line tool; there is no supporting graphical user interface.</span></span> <span data-ttu-id="00353-610">Dieses Tool basiert auf Microsoft Unified Communications Managed API (UCMA) 3,0.</span><span class="sxs-lookup"><span data-stu-id="00353-610">This tool is based on Microsoft Unified Communications Managed API (UCMA) 3.0.</span></span> <span data-ttu-id="00353-611">Mit den Features in diesem Tool können Administratoren und Helpdesk-Agents die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="00353-611">The features in this tool allow administrators and helpdesk agents to do the following:</span></span>

  - <span data-ttu-id="00353-612">Anzeigen aller Anrufweiterleitungseinstellungen für einen Benutzer (einschließlich Anrufweiterleitung, Stellvertretung, gleichzeitiges Klingeln, Teamanruf- und Gruppenanrufannahme)</span><span class="sxs-lookup"><span data-stu-id="00353-612">View all call routing settings for a user (includes call-forwarding, delegation, simultaneous ringing, team-call and group call pickup)</span></span>

  - <span data-ttu-id="00353-613">Aktivieren/Deaktivieren/Ändern der Anrufweiterleitungseinstellungen (einschließlich Ziel und Timer für „Keine Antwort“)</span><span class="sxs-lookup"><span data-stu-id="00353-613">Enable/disable/modify call-forwarding setting (includes destination and no-answer timer)</span></span>

  - <span data-ttu-id="00353-614">Aktivieren/Deaktivieren/Ändern der Konfiguration für sofortige Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="00353-614">Enable/disable/modify call-forwarding immediate configurations</span></span>

  - <span data-ttu-id="00353-615">Aktivieren/Deaktivieren/Ändern von Stellvertretungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="00353-615">Enable/disable/modify delegation settings</span></span>

  - <span data-ttu-id="00353-616">Aktivieren/Deaktivieren/Ändern von Teamanrufgruppen-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="00353-616">Enable/disable/modify team-call group settings</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00353-617">Neu im lync Server 2013 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="00353-617">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="00353-618">Aktivieren/Deaktivieren/Ändern der Einstellungen für gleichzeitiges Klingeln (einschließlich Ziel)</span><span class="sxs-lookup"><span data-stu-id="00353-618">Enable/disable/modify simultaneous ringing settings (includes destination)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00353-619">Neu im lync Server 2013 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="00353-619">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

  - <span data-ttu-id="00353-620">Aktivieren/Deaktivieren/Ändern von Einstellungen für Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="00353-620">Enable/disable/modify group call pickup settings</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="00353-621">Neu im lync Server 2013 SEFAUtil-Tool</span><span class="sxs-lookup"><span data-stu-id="00353-621">New in Lync Server 2013 SEFAUtil tool</span></span>

    
    </div>

<span data-ttu-id="00353-622">Für das Tool gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="00353-622">This tool has the following limitations:</span></span>

  - <span data-ttu-id="00353-623">Nur für Benutzer unterstützt, die in einem lync Server-Pool verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="00353-623">Supported only for users homed in a Lync Server pool</span></span>

  - <span data-ttu-id="00353-624">Keine Unterstützung für die Massenbearbeitung von Anrufweiterleitungseinstellungen für mehrere Benutzer</span><span class="sxs-lookup"><span data-stu-id="00353-624">Bulk-edit of call routing settings for several users is not supported</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-625">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-625">Output</span></span>

<span data-ttu-id="00353-p179">Die aktuelle Version dieses Tools stellt nur im Eingabeaufforderungsfenster Ausgaben zur Verfügung. Details hierzu finden Sie weiter unten in diesem Dokument im Abschnitt mit den Beispielen.</span><span class="sxs-lookup"><span data-stu-id="00353-p179">The current version of this tool provides output only in the Command Prompt window. For details, see the Examples section later in this document.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-628">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-628">Purpose</span></span>

<span data-ttu-id="00353-629">Hier sind einige der Hauptszenarien, in denen dieses Tool eingesetzt werden kann:</span><span class="sxs-lookup"><span data-stu-id="00353-629">Following are some of the key scenarios where this tool may be used:</span></span>

  - <span data-ttu-id="00353-630">Bob ist ein Executive-Mitarbeiter und wurde in die lync Server-Telefonie verschoben.</span><span class="sxs-lookup"><span data-stu-id="00353-630">Bob is an executive and has been moved to Lync Server telephony.</span></span> <span data-ttu-id="00353-631">In seiner vorhandenen Nebenstellenanlage hat er Stellvertretungen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="00353-631">He has delegation on his existing PBX system.</span></span> <span data-ttu-id="00353-632">Im Rahmen des Wechsels zu lync kann der Administrator das Routing von Bobs so konfigurieren, dass es seine bereits vorhandene Delegierungs Konfiguration widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="00353-632">As part of the move to Lync, the administrator is able to configure Bob’s routing to reflect his pre-existing delegation configuration.</span></span>

  - <span data-ttu-id="00353-p181">Alice ist auf Reisen und stellt fest, dass sie einen wichtigen Anruf eines ihrer Kunden erwartet. Sie befindet sich aber gerade im Hotel und hat keinen Computer zur Verfügung. Sie ruft den Helpdesk an und bittet darum, alle Anrufe an ihre Büronummer an ihr Mobiltelefon weiterzuleiten. Die Helpdeskmitarbeiter können diese Konfiguration in ihrem Auftrag vornehmen.</span><span class="sxs-lookup"><span data-stu-id="00353-p181">Alice is travelling and realizes that she is expecting an important call from one of her customers. However, she is in a hotel and has no access to a computer. She calls the helpdesk and requests that they forward to her mobile number all the calls made to her work number. The helpdesk personnel are able to do the configuration on her behalf.</span></span>

  - <span data-ttu-id="00353-p182">Die Anrufe an Joes Büronummer landen immer auf seiner mobilen Voicemail, wenn er bei der Arbeit ist. An den meisten anderen Standorten scheint aber alles richtig zu funktionieren. Der Helpdesktechniker kann sich Joes Weiterleitungskonfiguration ansehen und entdeckt, dass Joe für sein Mobiltelefon gleichzeitiges Klingeln konfiguriert hat. Der Techniker fragt Joe nach der Qualität der mobilen Netzabdeckung an seinem Arbeitsplatz und kann so bestimmen, dass die Regel für gleichzeitiges Klingeln dafür verantwortlich ist, dass bei schlechter Netzabdeckung alle Anrufe an Joes mobile Voicemail gehen.</span><span class="sxs-lookup"><span data-stu-id="00353-p182">Joe’s calls to his work number are going to his mobile voicemail whenever he is at work; however, things appear to be working correctly in most other locations. The helpdesk technician is able to view Joe’s routing configuration and discovers that Joe has simultaneous ringing configured to his mobile phone. The technician asks Joe about the mobile coverage at his office and is able to determine that the simultaneous ringing rule is what is causing the calls to go to Joe’s mobile voicemail when his network coverage is poor.</span></span>

  - <span data-ttu-id="00353-640">Mike ist ein neuer Mitarbeiter bei Contoso und er nimmt an einem neuen Team Teil, bei dem alle Mitglieder für die Team anrufkonfiguration konfiguriert sind, wenn der Administrator für Microsoft lync aktiviert ist, kann der Administrator seine Teamanrufgruppen Einstellungen so festlegen, dass er alle seine neuen Teammitglieder enthält, darüber hinaus die der Administrator fügt Mike als Team Anruf-Gruppenmitglied für alle Mitglieder in seinem Team hinzu.</span><span class="sxs-lookup"><span data-stu-id="00353-640">Mike is a new employee at Contoso and he’s joining a new team on which all members are configured for team-call, when being enabled for Microsoft Lync, the administrator is able to set his team-call group settings to include all his new team members, additionally, the administrator adds Mike as a team-call group member for each of the members in his team.</span></span>

  - <span data-ttu-id="00353-641">Eine Praxis des Kundendiensts in der Personalabteilung bei Contoso besteht darin, allen Anrufern vom ersten Anruf an persönlichen Service zu bieten.</span><span class="sxs-lookup"><span data-stu-id="00353-641">A customer service practice in the human resources department at Contoso is to provide personal service for all callers since the first call.</span></span> <span data-ttu-id="00353-642">Da alle Mitglieder der Abteilung sehr nah beieinander sitzen, kann das gleichzeitige Klingeln auf allen Telefonen bei Teamanrufen sehr störend für das Team sein.</span><span class="sxs-lookup"><span data-stu-id="00353-642">Given that all members of the department sit very close to each other, having all phones ringing at the same time with team-call is very disruptive for the team.</span></span> <span data-ttu-id="00353-643">Um den besten Service bereitzustellen, ohne die Teammitglieder zu unterbrechen, nutzt der lync-Administrator die Funktion zur Abhol Funktion für Gruppenanrufe.</span><span class="sxs-lookup"><span data-stu-id="00353-643">To provide the best service without disrupting the team members, the Lync administrator takes advantage of the Group Call Pickup capability.</span></span> <span data-ttu-id="00353-644">Der Administrator fügt alle Abteilungsmitglieder einer Annahmegruppe hinzu und teilt der Abteilung die Annahmegruppennummer mit.</span><span class="sxs-lookup"><span data-stu-id="00353-644">The administrator adds all department members to a pickup group and communicates to the department the pickup group number.</span></span> <span data-ttu-id="00353-645">Wenn nun Samantha nicht an ihrem Platz ist, bemerkt Joe, dass ihr Telefon klingelt, und kann den Anruf von seinem Platz aus annehmen.</span><span class="sxs-lookup"><span data-stu-id="00353-645">When Samantha is absent from her desk, Joe notices her phone ringing and he proceeds to answer the call from his desk.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-646">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="00353-646">Requirements</span></span>

<span data-ttu-id="00353-p184">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört. Auf diesem Computer muss UCMA 3.0 installiert sein. Um das Tool auszuführen, muss in diesem Pool eine neue vertrauenswürdige Anwendung mit der SEFAUtil-Anwendungs-ID erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-p184">The SEFAUtil tool can be run only on a computer that is a part of a Trusted Application Pool. UCMA 3.0 must be installed on that computer. To run the tool, a new Trusted Application with the SEFAUtil application ID must be created on that pool.</span></span>

<span data-ttu-id="00353-650">**Erstellen einer neuen vertrauenswürdigen Anwendung für das SEFAUtil-Tool**</span><span class="sxs-lookup"><span data-stu-id="00353-650">**Creating a new Trusted Application for the SEFAUtil tool**</span></span>

1.  <span data-ttu-id="00353-651">Das SEFAUtil-Tool kann nur auf einem Computer ausgeführt werden, der zu einem Pool mit vertrauenswürdigen Anwendungen gehört.</span><span class="sxs-lookup"><span data-stu-id="00353-651">The SEFAUTil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="00353-652">Falls erforderlich, kann das Hinzufügen eines Pools als neuer vertrauenswürdiger Anwendungspool über die lync Server-Verwaltungsshell mit dem folgenden Cmdlet erfolgen:</span><span class="sxs-lookup"><span data-stu-id="00353-652">If needed, adding a pool as a new trusted application pool can be done via the Lync Server Management Shell with the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00353-653">Auf allen Computern, auf denen das SEFAUtil-Tool ausgeführt werden soll, muss UCMA 3.0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="00353-653">UCMA 3.0 must be installed on any computer that will be used to run the SEFAUtil tool.</span></span>

    
    </div>

2.  <span data-ttu-id="00353-654">In der Topologie muss eine vertrauenswürdige Anwendung für das SEFAUtil-Tool definiert sein.</span><span class="sxs-lookup"><span data-stu-id="00353-654">A trusted application needs to be defined in the topology for the SEFAUtil tool.</span></span> <span data-ttu-id="00353-655">Wenn Sie SEFAUtil als neue vertrauenswürdige Anwendung definieren möchten, verwenden Sie die lync Server-Verwaltungsshell, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="00353-655">To define SEFAUtil as a new trusted application, use the Lync Server Management Shell and execute the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00353-656">Gegebenenfalls kann ein anderer Port verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00353-656">A different port can be used if needed.</span></span>

    
    </div>

3.  <span data-ttu-id="00353-657">Die Topologieänderungen müssen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-657">The topology changes need to be enabled.</span></span> <span data-ttu-id="00353-658">Das Aktivieren der Topologie-Änderungen kann über die lync Server-Verwaltungsshell erfolgen, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="00353-658">Enabling the topology changes can be done via the Lync Server Management Shell by executing the following cmdlet:</span></span>
    
        Enable-CsToplogy

4.  <span data-ttu-id="00353-659">Installieren Sie bei Bedarf die lync Server 2013 Resource Kit-Tools auf dem Server, der zum Ausführen des SEFAUtil-Tools verwendet wird (der Server muss Teil eines vertrauenswürdigen Anwendungspools sein).</span><span class="sxs-lookup"><span data-stu-id="00353-659">If needed, install the Lync Server 2013 Resource Kit Tools in the server that will be used to run the SEFAUtil tool (the server must be part of a trusted application pool).</span></span>

5.  <span data-ttu-id="00353-660">Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="00353-660">Verify the SEFAUtil is running correctly.</span></span> <span data-ttu-id="00353-661">Führen Sie hierzu das Tool an einer Windows-Eingabeaufforderung mit Administratorrechten aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00353-661">To do this, run the tool from a windows command prompt with administrator privileges to display the call forwarding settings of a user in the deployment.</span></span> <span data-ttu-id="00353-662">Standardmäßig befindet sich das Tool in: "... \\Programmdateien\\Microsoft lync Server 2013\\reskit ".</span><span class="sxs-lookup"><span data-stu-id="00353-662">By default the tool will be located in: “…\\Program Files\\Microsoft Lync Server 2013\\Reskit”.</span></span> <span data-ttu-id="00353-663">Verwenden Sie zum Anzeigen der Anrufweiterleitungseinstellungen eines Benutzers den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="00353-663">To display the call forwarding settings of a user, use the following command:</span></span>
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    <span data-ttu-id="00353-664">Die Anrufweiterleitungseinstellungen des Benutzers sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-664">The call forwarding settings of the user should be displayed.</span></span>

<div>

## <a name="group-call-pickup"></a><span data-ttu-id="00353-665">Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="00353-665">Group Call Pickup</span></span>

<span data-ttu-id="00353-666">Für die Gruppenanruf Abholung ist eine zusätzliche Konfiguration in lync Server erforderlich, damit die Funktion vollständig aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="00353-666">Group Call Pickup requires additional configuration in Lync Server for the capability to be fully enabled.</span></span> <span data-ttu-id="00353-667">Bevor Sie Benutzern Annahmegruppen zuweisen, sollten Sie in der Produktdokumentation der Gruppenanrufannahme die Schritte zur Planung und Bereitstellung dieser Funktion nachlesen.</span><span class="sxs-lookup"><span data-stu-id="00353-667">Before assigning pickup groups to users, refer to the Group Call Pickup product documentation for the planning and deployment steps of this capability.</span></span>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-668">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-668">Examples</span></span>

<div>

## <a name="display-current-call-handling-settings"></a><span data-ttu-id="00353-669">Anzeigen aktueller Anrufbehandlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="00353-669">Display Current Call Handling Settings</span></span>

<span data-ttu-id="00353-670">Der folgende Befehl zeigt die Anrufbehandlung für den entsprechenden Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="00353-670">The following command displays the call handling for the user.</span></span> `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> <span data-ttu-id="00353-671">In diesem Beispiel wird <STRONG></STRONG> der Server-Schalter verwendet, um den lync-Server anzugeben, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="00353-671">This example uses the <STRONG>/server</STRONG> switch to specify the Lync Server to connect to.</span></span>



</div>

<span data-ttu-id="00353-672">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-672">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a><span data-ttu-id="00353-673">Festlegen des Ziels für Anrufweiterleitung/Keine Antwort</span><span class="sxs-lookup"><span data-stu-id="00353-673">Set the Call Forward/No Answer Destination</span></span>

<span data-ttu-id="00353-674">In diesem Beispiel wird das Ziel des Anruf Weiterleitungs-/Nein-Anrufs und die Klingelverzögerung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00353-674">This example sets the call forward/no answer destination and the ring delay.</span></span> <span data-ttu-id="00353-675">Hier wird der Schalter//////-Schalter nicht bereitgestellt. SEFAUtil versucht, den lync-Server zu autodiscover.</span><span class="sxs-lookup"><span data-stu-id="00353-675">Here, the /server switch is not provided; SEFAUtil attempts to autodiscover the Lync Server.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

<span data-ttu-id="00353-676">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-676">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a><span data-ttu-id="00353-677">Aktivieren der sofortigen Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="00353-677">Enable Call Forwarding Immediately</span></span>

<span data-ttu-id="00353-678">Dieses Beispiel aktiviert sofort die Anrufweiterleitung an einen anderen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00353-678">This example immediately enables call-forwarding to another user.</span></span>

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

<span data-ttu-id="00353-679">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-679">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a><span data-ttu-id="00353-680">Deaktivieren der sofortigen Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="00353-680">Disable Call Forwarding Immediately</span></span>

<span data-ttu-id="00353-681">Dieses Beispiel deaktiviert sofort die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="00353-681">This example immediately disables call forwarding.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

<span data-ttu-id="00353-682">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-682">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a><span data-ttu-id="00353-683">Hinzufügen eines Benutzers als Stellvertretung und Einrichten von gleichzeitigem Klingeln bei Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="00353-683">Add a User as a Delegate and Set Up Simultaneous Ringing of Delegates</span></span>

<span data-ttu-id="00353-684">Dieses Beispiel fügt einen Benutzer als Stellvertretung hinzu und richtet das gleichzeitige Klingeln bei Stellvertretungen ein.</span><span class="sxs-lookup"><span data-stu-id="00353-684">This example adds a user as a delegate and sets up simultaneous ringing of delegates.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

<span data-ttu-id="00353-685">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-685">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a><span data-ttu-id="00353-686">Ändern der Regel für gleichzeitiges Klingeln bei Stellvertretungen</span><span class="sxs-lookup"><span data-stu-id="00353-686">Change Simultaneous Ringing Rule of Delegates</span></span>

<span data-ttu-id="00353-687">Dieses Beispiel ändert die Regel für gleichzeitiges Klingeln bei Stellvertretungen, die im vorherigen Beispiel festgelegt wurde, in die Anrufverzögerungsregel.</span><span class="sxs-lookup"><span data-stu-id="00353-687">This example changes the simultaneous ringing rule that was set in the previous example to the delayed ringing rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

<span data-ttu-id="00353-688">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-688">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a><span data-ttu-id="00353-689">Entfernen der Stellvertretung</span><span class="sxs-lookup"><span data-stu-id="00353-689">Remove the Delegate</span></span>

<span data-ttu-id="00353-690">Dieses Beispiel entfernt die Stellvertretung.</span><span class="sxs-lookup"><span data-stu-id="00353-690">This example removes the delegate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-691">Wenn die letzte Stellvertretung entfernt wurde, wird das Anrufen von Stellvertretungen automatisch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="00353-691">When the last delegate is removed, delegate ringing is automatically disabled.</span></span>



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

<span data-ttu-id="00353-692">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-692">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a><span data-ttu-id="00353-693">Hinzufügen einer Stellvertretung und Einrichten der Regel „Anrufweiterleitung an Stellvertretungen“</span><span class="sxs-lookup"><span data-stu-id="00353-693">Add a Delegate and Set Up the Call-Forward to Delegates Rule</span></span>

<span data-ttu-id="00353-694">Dieses Beispiel fügt eine Stellvertretung hinzu und richtet die Regel „Anrufweiterleitung an Stellvertretungen“ ein.</span><span class="sxs-lookup"><span data-stu-id="00353-694">This example adds a delegate and sets up the call-forward to delegates rule.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

<span data-ttu-id="00353-695">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-695">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a><span data-ttu-id="00353-696">Aktivieren von gleichzeitigem Klingeln und Festlegen einer Zielnummer</span><span class="sxs-lookup"><span data-stu-id="00353-696">Enable Simultaneous Ringing and Set a Destination Number</span></span>

<span data-ttu-id="00353-697">Diese Beispiel aktiviert gleichzeitiges Klingeln und legt eine Zielnummer für diese Funktion fest.</span><span class="sxs-lookup"><span data-stu-id="00353-697">This example enables simultaneous ringing and sets a simultaneous ringing destination number.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> <span data-ttu-id="00353-698">Um die Zielnummer für gleichzeitiges Klingeln eines Benutzers zu ändern, für den gleichzeitiges Klingeln bereits aktiviert ist, behalten Sie den Befehl mit dem Parameter „/enablesimulring“. Andernfalls wird die Zielnummer nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="00353-698">To change the simultaneous ringing destination number of a user that has already simultaneous ringing enabled, keep the command with the /enablesimulring switch, otherwise the destination number will not be changed.</span></span>



</div>

<span data-ttu-id="00353-699">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-699">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a><span data-ttu-id="00353-700">Deaktivieren von gleichzeitigem Klingeln</span><span class="sxs-lookup"><span data-stu-id="00353-700">Disable Simultaneous Ringing</span></span>

<span data-ttu-id="00353-701">Dieses Beispiel deaktiviert gleichzeitiges Klingeln.</span><span class="sxs-lookup"><span data-stu-id="00353-701">This example disables simultaneous ringing.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

<span data-ttu-id="00353-702">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-702">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a><span data-ttu-id="00353-703">Hinzufügen eines Teammitglieds für Teamanrufe und Einrichten von gleichzeitigem Klingeln für die Teamanrufgruppen-Mitglieder</span><span class="sxs-lookup"><span data-stu-id="00353-703">Add a Team Member for Team-Call and Set up Simultaneous Ringing to the Team-Call Members Group</span></span>

<span data-ttu-id="00353-704">Dieses Beispiel fügt der Teamanrufgruppe eines Benutzers ein Teammitglied hinzu und aktiviert gleichzeitiges Klingeln für die Teamanrufgruppe.</span><span class="sxs-lookup"><span data-stu-id="00353-704">This example adds a team member to the team-call group of a user and enables simultaneous ringing to the team-call group.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="00353-705">Durch das Hinzufügen eines Teammitglieds zur Teamanrufgruppe eines Benutzers werden die Einstellungen der Benutzer für gleichzeitiges Klingeln automatisch auf gleichzeitiges Klingeln für die Teamanrufgruppe umgestellt.</span><span class="sxs-lookup"><span data-stu-id="00353-705">Adding a member to the team-call group of a user will automatically switch the simultaneous ringing settigs of the users to simulring his team-call group.</span></span>



</div>

<span data-ttu-id="00353-706">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-706">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a><span data-ttu-id="00353-707">Entfernen eines Mitglieds aus der Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="00353-707">Remove a Member from the Team-Call Group</span></span>

<span data-ttu-id="00353-708">Diese Beispiel entfernt ein Teammitglied aus der Teamanrufgruppe eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="00353-708">This example removes a team member of the team-call group of a user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> <span data-ttu-id="00353-709">Wenn das einzige Mitglied der Teamanrufgruppe entfernt wird, wird automatisch das gleichzeitige Klingeln für die Teamanrufgruppe deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="00353-709">If the member being removed is the only member of the team-call group, simultaneously ringing to the team-call group will be automatically disabled.</span></span>



</div>

<span data-ttu-id="00353-710">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-710">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a><span data-ttu-id="00353-711">Festlegen der Anrufverzögerung für die Teamanrufgruppe</span><span class="sxs-lookup"><span data-stu-id="00353-711">Set the Delayed Ring to the Team-Call Group</span></span>

<span data-ttu-id="00353-712">Dieses Beispiel ändert die Zeiteinstellung der Anrufverzögerung für die Teamanrufgruppe.</span><span class="sxs-lookup"><span data-stu-id="00353-712">This example changes the delayed ring to the team-call group time setting.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

<span data-ttu-id="00353-713">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-713">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a><span data-ttu-id="00353-714">Aktivieren des Teamanrufs</span><span class="sxs-lookup"><span data-stu-id="00353-714">Enable Team-Call</span></span>

<span data-ttu-id="00353-715">Dieses Beispiel aktiviert den Teamanruf für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00353-715">This example enables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> <span data-ttu-id="00353-716">Wenn die Teamanrufgruppe des Benutzers keine Mitglieder hat, wird der Teamanruf nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="00353-716">If the team-call group of the user has no members, team-call won’t be enabled.</span></span>



</div>

<span data-ttu-id="00353-717">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-717">**Output**</span></span>

</div>

<div>

## <a name="disable-team-call"></a><span data-ttu-id="00353-718">Deaktivieren des Teamanrufs</span><span class="sxs-lookup"><span data-stu-id="00353-718">Disable Team-Call</span></span>

<span data-ttu-id="00353-719">Dieses Beispiel deaktiviert den Teamanruf für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00353-719">This example disables team-call for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

<span data-ttu-id="00353-720">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-720">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a><span data-ttu-id="00353-721">Aktivieren der Gruppenanrufannahme und Zuweisen einer Annahmegruppe zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="00353-721">Enable Group Call Pickup and Assign a Pickup Group to a User</span></span>

<span data-ttu-id="00353-722">Dieses Beispiel weist einem Benutzer eine Annahmegruppe zu und aktiviert die Gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="00353-722">This example assigns a pickup group to a user and enables Group Call Pickup.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

<span data-ttu-id="00353-723">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="00353-723">**Output**</span></span>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a><span data-ttu-id="00353-724">Deaktivieren der Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="00353-724">Disable Group Call Pickup</span></span>

<span data-ttu-id="00353-725">Dieses Beispiel deaktiviert die Gruppenanrufannahme für einen angegebenen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="00353-725">This example disables Group Call Pickup for a given user.</span></span>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> <span data-ttu-id="00353-p191">Wenn Sie die Gruppenanrufannahme für einen Benutzer deaktivieren, bleibt die Gruppennummer, die dem Benutzer zugewiesen war, nicht erhalten. Wenn Sie die Gruppenanrufannahme für diesen Benutzer anschließend wieder aktivieren möchten, müssen Sie die Gruppennummer erneut mithilfe des Parameters „/enablegrouppickup“ zuweisen.</span><span class="sxs-lookup"><span data-stu-id="00353-p191">When you disable Group Call Pickup for a user, the group number that was assigned to the user is not retained. If you subsequently want to re-enable Group Call Pickup for that user, you must assign the group number again with the /enablegrouppickup switch.</span></span>



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a><span data-ttu-id="00353-728">SYSPrep.ps1</span><span class="sxs-lookup"><span data-stu-id="00353-728">SYSPrep.ps1</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-729">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-729">Description</span></span>

<span data-ttu-id="00353-730">"SYSPrep. ps1" ist ein Windows PowerShell-Skript, mit dem die folgenden lync Server 2013-Voraussetzungen auf Ihrem Windows Server 2008-Betriebssystem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="00353-730">SYSPrep.ps1 is a Windows PowerShell script that will install the following Lync Server 2013 prerequisites on your Windows Server 2008 operating system machine.</span></span>

  - <span data-ttu-id="00353-731">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="00353-731">Microsoft .Net Framework 4.5</span></span>

  - <span data-ttu-id="00353-732">Microsoft SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="00353-732">Microsoft SQL Server Express</span></span>

  - <span data-ttu-id="00353-733">Windows PowerShell, Version 3.0</span><span class="sxs-lookup"><span data-stu-id="00353-733">Windows Powershell version 3.0</span></span>

  - <span data-ttu-id="00353-734">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="00353-734">Visual C++ 2010 Redistributable</span></span>

  - <span data-ttu-id="00353-735">Updates für Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="00353-735">Internet Information Server Updates</span></span>

  - <span data-ttu-id="00353-736">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="00353-736">Windows Identity Foundation</span></span>

  - <span data-ttu-id="00353-737">Core-Dateien für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00353-737">Lync Server 2013 Core files</span></span>

<span data-ttu-id="00353-738">Zwar ähnelt der Skriptname dem des Systemvorbereitungsprogramms für die Microsoft Windows-Betriebssysteme, doch sind beide unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="00353-738">While the script name is similar to the System Preparation Tool for the Microsoft Windows operating systems, they are different.</span></span> <span data-ttu-id="00353-739">Mit diesem Skript werden nur die erforderlichen Voraussetzungen für lync Server 2013 installiert.</span><span class="sxs-lookup"><span data-stu-id="00353-739">This script will only install the required prerequisites for Lync Server 2013.</span></span> <span data-ttu-id="00353-740">Sobald diese installiert sind, kann mit dem Windows-Tool für die Systemvorbereitung ein Image des Servers erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-740">Once those prerequisites are installed, the Windows SYSPrep tool can then be used to create an image of the server.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-741">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-741">Requirements</span></span>

<span data-ttu-id="00353-742">Bevor Sie das SYSPrep. ps1-Skript ausführen können, müssen Sie die erforderlichen Dateien in einen lokalen Ordner auf dem Windows Server 2008-Betriebssystem Computer kopieren (zum Beispiel **D:\\Setup)**.</span><span class="sxs-lookup"><span data-stu-id="00353-742">Prior to running the SYSPrep.ps1 script, you must copy the prerequisite files to a local folder on the Windows Server 2008 operating system machine (for example **D:\\Setup)**.</span></span> <span data-ttu-id="00353-743">Dieser Ordner muss auch eine Kopie der lync Server 2013-Dateien, insbesondere **Setup. exe** , beinhalten.</span><span class="sxs-lookup"><span data-stu-id="00353-743">This folder must also include a copy of the Lync Server 2013 files, specifically **Setup.exe.**</span></span> <span data-ttu-id="00353-744">Die erforderlichen Dateien können Sie an folgenden Orten herunterladen:</span><span class="sxs-lookup"><span data-stu-id="00353-744">The prerequisite files can be downloaded from the following locations:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00353-745">Erforderliche Komponente</span><span class="sxs-lookup"><span data-stu-id="00353-745">Prerequisite</span></span></th>
<th><span data-ttu-id="00353-746">Ort</span><span class="sxs-lookup"><span data-stu-id="00353-746">Location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00353-747">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="00353-747">Microsoft .Net Framework 4.5</span></span></p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00353-748">Microsoft SQL Server Express 2008 R2</span><span class="sxs-lookup"><span data-stu-id="00353-748">Microsoft SQL Server Express 2008 R2</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00353-749">Windows PowerShell, Version 3.0</span><span class="sxs-lookup"><span data-stu-id="00353-749">Windows Powershell version 3.0</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00353-750">Visual C++ 2010 Redistributable</span><span class="sxs-lookup"><span data-stu-id="00353-750">Visual C++ 2010 Redistributable</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00353-751">Updates für Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="00353-751">Internet Information Server Updates</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00353-752">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="00353-752">Windows Identity Foundation</span></span></p></td>
<td><p>http://www.microsoft.com/en-us/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00353-753">Lync Server 2013 Setup. exe</span><span class="sxs-lookup"><span data-stu-id="00353-753">Lync Server 2013 Setup.exe</span></span></p></td>
<td><p><span data-ttu-id="00353-754">Kopieren von lync Server 2013-Medien</span><span class="sxs-lookup"><span data-stu-id="00353-754">Copy from Lync Server 2013 media</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a><span data-ttu-id="00353-755">Parameter</span><span class="sxs-lookup"><span data-stu-id="00353-755">Parameter</span></span>

<span data-ttu-id="00353-756">Der Parameter **–SetupFolder** akzeptiert als Argument den Verzeichnisspeicherort der erforderlichen Dateien.</span><span class="sxs-lookup"><span data-stu-id="00353-756">The **–SetupFolder** parameter takes as an argument the directory location of the prerequisite files</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-757">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-757">Examples</span></span>

<span data-ttu-id="00353-758">Führen Sie an einer Eingabeaufforderung mit erhöhten Rechten den folgenden Befehl aus, um das Skript "SYSPrep. ps1" auszuführen und die Voraussetzungen für lync Server 2013 zu installieren:</span><span class="sxs-lookup"><span data-stu-id="00353-758">To run the SYSPrep.ps1 script and install the Lync Server 2013 prerequisites, run the following command from an elevated command prompt:</span></span>

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a><span data-ttu-id="00353-759">Unassigned Number Announcements Migration</span><span class="sxs-lookup"><span data-stu-id="00353-759">Unassigned Number Announcements Migration</span></span>

<span data-ttu-id="00353-760">Mit dem Migrationstool "nicht zugewiesene Nummern Ankündigungen" kann ein lync-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von einem lync-Quellserver oder-Pool zu einem lync-Zielserver oder-Pool verschieben.</span><span class="sxs-lookup"><span data-stu-id="00353-760">The Unassigned Number Announcements Migration tool enables a Lync administrator to move the unassigned numbers configuration that is serviced by the announcement application from a source Lync Server or Pool to a destination Lync Server or Pool.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-761">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-761">Description</span></span>

<span data-ttu-id="00353-762">Das Tool Unassigned Number Announcements Migration ist ein Windows PowerShell-Skript, das die Konfiguration für nicht zugewiesene Nummern, die von der Ankündigungsanwendung bedient wird, von einem Quellserver oder -pool zu einem anderen Server oder Pool verschiebt.</span><span class="sxs-lookup"><span data-stu-id="00353-762">The Unassigned Number Announcements Migration tool is a Windows PowerShell script that moves the unassigned numbers configuration serviced by the announcement application of a source server or pool to a different server or pool.</span></span>

<span data-ttu-id="00353-763">Bei Ausführung des Unassigned Number Announcements Migration-Skripts werden folgende Vorgänge durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="00353-763">When executed, the Unassigned Number Announcements Migration script will perform the following operations:</span></span>

1.  <span data-ttu-id="00353-764">Verschieben aller Audiodateien, die von den Ankündigungen für nicht zugewiesene Nummern der Ankündigungsanwendung verwendet werden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Dateispeicher des Zielservers oder -pools</span><span class="sxs-lookup"><span data-stu-id="00353-764">Move all the audio files used by the unassigned number announcements of the announcement application hosted in the source server or pool to the file store of the destination server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00353-765">die Audiodateien werden aus dem Quell Pool entfernt, nachdem Sie in den Ziel Pool kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="00353-765">the audio files are removed from the source pool once they’re copied to the destination pool.</span></span>

    
    </div>

2.  <span data-ttu-id="00353-766">Verschieben aller Ankündigungen für nicht zugewiesene Nummern, die für die Ankündigungsanwendung konfiguriert sind, die auf dem Quellserver bzw. im Quellpool verwaltet wird, in den Zielserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="00353-766">Move all unassigned number announcements configured for the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

3.  <span data-ttu-id="00353-767">Erneutes Zuweisen aller nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient werden, die auf dem Quellserver oder -pool verwaltet wird, zum Zielserver oder -pool</span><span class="sxs-lookup"><span data-stu-id="00353-767">Reassign all the unassigned number ranges that are serviced by the announcement application hosted in the source server or pool to the destination server or pool.</span></span>

<span data-ttu-id="00353-768">Nach erfolgreicher Ausführung des Skripts werden alle nicht zugewiesenen Nummernbereiche, die von der Ankündigungsanwendung bedient wurden, die auf dem Quellserver bzw. im Quellpool verwaltet wird, nun mit derselben Konfiguration vom Zielserver oder -pool bedient.</span><span class="sxs-lookup"><span data-stu-id="00353-768">After successfully running the script, all the unassigned number ranges that were serviced by the announcement application hosted in the source server or pool will now be serviced with the same configuration by the destination server or pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-769">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-769">Output</span></span>

<span data-ttu-id="00353-770">Das **CsAnnouncementConfiguration-** Skript zeigt im Fenster der lync-Verwaltungsshell an, wo es den Erfolg oder Misserfolg des Migrationsvorgangs ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="00353-770">The **Move-CsAnnouncementConfiguration** script indicates in the Lync Management Shell window from where it’s executed the success or failure of the migration operation.</span></span>

<span data-ttu-id="00353-p194">Wenn die Ausführung des Vorgangs durch einen Fehler unterbrochen wird, verbleiben die erfolgreich in das Ziel verschobenen nicht zugewiesenen Nummernbereiche in funktionsfähiger Form am Ziel, während der Rest der noch zu migrierenden nicht zugewiesenen Nummernbereiche in der Quelle verbleibt – ebenfalls in funktionsfähigem Zustand. Um die restliche Konfiguration vollständig zu migrieren, führen Sie das Skript erneut aus, nachdem Sie den Fehler behoben haben.</span><span class="sxs-lookup"><span data-stu-id="00353-p194">If the execution of the operation is interrupted by any error, the unassigned number ranges that were successfully moved to the destination will remain in the destination in an operational form and the rest of the unassigned number ranges to be migrated will remain in the source as well in an operational form. To fully migrate the rest of the configuration, rerun the script after addressing the error.</span></span>

</div>

<div>

## <a name="purpose"></a><span data-ttu-id="00353-773">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="00353-773">Purpose</span></span>

<span data-ttu-id="00353-774">Das Unassigned Number Announcements Migration-Skript kann in den drei folgenden Szenarien eingesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="00353-774">The Unassigned Number Announcements Migration script can be used in the following three scenarios:</span></span>

  - <span data-ttu-id="00353-775">**Migrieren von Konfigurationseinstellungen zu einer neuen Version von lync Server:** Contoso ist dabei, zu lync Server 2013 zu migrieren, und im Rahmen des Migrationsprozesses möchte der lync Server-Administrator die nicht zugewiesene Nummern Konfiguration, die von der Ankündigungs Anwendung gewartet wird, von der lync Server 2010-Bereitstellung auf die neue lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="00353-775">**Migrating configuration settings to a new version of Lync Server:** Contoso is in the process of migrating to Lync Server 2013 and as part of the migration process the Lync Server administrator would like to move the unassigned numbers configuration serviced by the announcement application from the Lync Server 2010 deployment to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="00353-776">Um die Konfigurationseinstellungen zu verschieben, verwendet der lync Server-Administrator das Migrationstool für nicht zugewiesene Nummern Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="00353-776">To move the configuration settings, the Lync Server administrator uses the Unassigned Number Announcements Migration tool.</span></span>

  - <span data-ttu-id="00353-777">Rollback **einer Bereitstellung von lync Server 2013 auf lync Server 2010:** Aufgrund unerwarteter Faktoren muss Contoso die Migration auf die neue lync Server 2013-Bereitstellung zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="00353-777">**Rolling back a deployment from Lync Server 2013 to Lync Server 2010:** Due unexpected factors, Contoso has to roll back the migration to the new Lync Server 2013 deployment.</span></span> <span data-ttu-id="00353-778">Um die Unterbrechungen des Diensts zu minimieren, verwendet der lync Server-Administrator das Migrationstool "nicht zugewiesene Nummern Ankündigungen", um die Konfiguration von der lync Server 2013-Bereitstellung auf die lync Server 2010-Bereitstellung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="00353-778">To minimize disruptions to the service, the Lync Server administrator uses the Unassigned Number Announcements Migration tool to roll back the configuration from the Lync Server 2013 deployment to the Lync Server 2010 deployment.</span></span>

  - <span data-ttu-id="00353-779">**Verschieben von Daten zwischen lync-Bereitstellungen:** Contoso ersetzt alle Server eines Pools durch neuere Server.</span><span class="sxs-lookup"><span data-stu-id="00353-779">**Moving data between Lync deployments:** Contoso is in the process of replacing all the servers of one pool with newer servers.</span></span> <span data-ttu-id="00353-780">Ihre Strategie ist die Bereitstellungeines neuen lync Server 2013-Pools, das Verschieben aller Daten aus dem alten in den neuen Pool und das anschließende verwerfen des alten Pools.</span><span class="sxs-lookup"><span data-stu-id="00353-780">Their strategy is to deploy a new Lync Server 2013 pool, move all the data from the old to the new pool, and then deprecate the old pool.</span></span> <span data-ttu-id="00353-781">Sobald der neue Pool bereitgestellt ist, wird die Konfiguration mit dem Tool Unassigned Number Announcements Migration aus dem alten Pool in den neuen verschoben.</span><span class="sxs-lookup"><span data-stu-id="00353-781">Once the new pool is deployed, the Unassigned Number Announcements Migration tool is used to move the configuration from the old pool to the new one.</span></span>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-782">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="00353-782">Requirements</span></span>

<span data-ttu-id="00353-783">Hier sind die Hauptanforderungen für eine erfolgreiche Ausführung des Tools:</span><span class="sxs-lookup"><span data-stu-id="00353-783">The following are the main requirements needed to successfully run the tool:</span></span>

1.  <span data-ttu-id="00353-784">Das Skript muss von einem Computer ausgeführt werden, auf dem die lync Server 2013-Verwaltungsshell installiert ist.</span><span class="sxs-lookup"><span data-stu-id="00353-784">The script must be run from a computer that has Lync Server 2013 Management Shell installed.</span></span>

2.  <span data-ttu-id="00353-785">Die Ankündigungs Anwendung muss erfolgreich auf den lync-Servern oder-Pools für Quell-und Zielserver bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-785">The announcement application has to be successfully deployed in the source and destination Lync Servers or Pools.</span></span>

<div>

## <a name="move-csannouncementconfiguration-script"></a><span data-ttu-id="00353-786">Skript „Move-CsAnnouncementConfiguration“</span><span class="sxs-lookup"><span data-stu-id="00353-786">Move-CsAnnouncementConfiguration script</span></span>

<span data-ttu-id="00353-787">Das Skript „Move-CsAnnouncementConfiguration“ erfordert die in der Tabelle unten beschriebenen zwei Parameter. </span><span class="sxs-lookup"><span data-stu-id="00353-787">The Move-CsAnnouncementConfiguration script requires the two parameters that are described in the table below.</span></span>

<span data-ttu-id="00353-788">![Move-CsAnnouncementConfiguration-Parameter.] (images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration-Parameter.")</span><span class="sxs-lookup"><span data-stu-id="00353-788">![Move-CsAnnouncementConfiguration parameters.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Move-CsAnnouncementConfiguration parameters.")</span></span>

</div>

</div>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-789">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-789">Examples</span></span>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a><span data-ttu-id="00353-790">Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem lync Server 2010-Pool in einen lync Server 2013-Pool</span><span class="sxs-lookup"><span data-stu-id="00353-790">Moving the Unassigned Number Announcements Configuration from a Lync Server 2010 Pool to a Lync Server 2013 Pool</span></span>

<span data-ttu-id="00353-791">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2010) in den Ziel Pool (lync Server 2013) verschoben.</span><span class="sxs-lookup"><span data-stu-id="00353-791">This example moves the unassigned number announcements from the source pool (Lync Server 2010) to the destination pool (Lync Server 2013).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a><span data-ttu-id="00353-792">Verschieben der Konfiguration "nicht zugewiesene Nummern Ankündigungen" aus einem lync Server 2013-Pool in einen lync Server 2010-Pool</span><span class="sxs-lookup"><span data-stu-id="00353-792">Moving the Unassigned Number Announcements Configuration from a Lync Server 2013 Pool to a Lync Server 2010 Pool</span></span>

<span data-ttu-id="00353-793">In diesem Beispiel werden die Ankündigungen nicht zugewiesener Nummern aus dem Quell Pool (lync Server 2013) in den Ziel Pool (lync Server 2010) verschoben.</span><span class="sxs-lookup"><span data-stu-id="00353-793">This example moves the unassigned number announcements from the source pool (Lync Server 2013) to the destination pool (Lync Server 2010).</span></span>

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a><span data-ttu-id="00353-794">Web Conf Data</span><span class="sxs-lookup"><span data-stu-id="00353-794">Web Conf Data</span></span>

<span data-ttu-id="00353-795">Das Tool Web conf Data ermöglicht einem Administrator der lync Server 2013-Kommunikationssoftware, mehr Kontrolle über die Daten zu haben, die den Webkonferenzen eines Organisators zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="00353-795">The Web Conf Data Tool allows an administrator of Lync Server 2013 communications software to have more control over the data associated with an organizer’s Web conferences.</span></span> <span data-ttu-id="00353-796">Die Szenarien umfassen unter anderem die Möglichkeit, die Besprechungsdaten bestimmter Benutzer auf Grundlage eines Zeitstempelkriteriums zu löschen.</span><span class="sxs-lookup"><span data-stu-id="00353-796">Scenarios include the ability to delete a specific user’s meeting data based on a time stamp criteria.</span></span>

<div>

## <a name="description"></a><span data-ttu-id="00353-797">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00353-797">Description</span></span>

<span data-ttu-id="00353-798">Mit diesem Tool können Administratoren die folgenden Vorgänge durchführen:</span><span class="sxs-lookup"><span data-stu-id="00353-798">This tool allows the administrator to perform the following operations:</span></span>

1.  <span data-ttu-id="00353-799">Suchen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="00353-799">Find all Web conferencing data associated with a single user.</span></span>

2.  <span data-ttu-id="00353-800">Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="00353-800">Delete all Web conferencing data associated with a single user.</span></span>

3.  <span data-ttu-id="00353-801">Löschen aller Webkonferenzdaten, die einzelnen Benutzern zugeordnet sind und deren Alter einen bestimmten Wert überschreitet</span><span class="sxs-lookup"><span data-stu-id="00353-801">Delete all Web conferencing data associated with a single user that is older than a certain date.</span></span>

4.  <span data-ttu-id="00353-802">Verschieben aller Webkonferenzdaten, die einem Benutzern zugeordnet sind, wenn diese Benutzer aus einem Pool in einen anderen verschoben werden</span><span class="sxs-lookup"><span data-stu-id="00353-802">Move all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00353-803">Die Resource Kit-Tools für lync Server 2010 unterstützt das Verschieben aller Webkonferenz Daten, die einem einzelnen Benutzer zugeordnet sind, wenn dieser Benutzer von einem Pool zu einem anderen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="00353-803">The Resource Kit Tools for Lync Server 2010 supported moving all Web conferencing data associated with a single user when that user is moved from one pool to another.</span></span> <span data-ttu-id="00353-804">Diese Funktionalität ist jetzt aus diesem Tool für den <STRONG>MoveConferenceData</STRONG> -Parameter veraltet.</span><span class="sxs-lookup"><span data-stu-id="00353-804">That functionality is now deprecated from this tool in favor of the <STRONG>MoveConferenceData</STRONG> parameter.</span></span> <span data-ttu-id="00353-805">Details zu diesem Parameter finden Sie unter dem Cmdlet <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> .</span><span class="sxs-lookup"><span data-stu-id="00353-805">For details about this parameter, see the <A href="https://technet.microsoft.com/en-us/library/gg398528(v=ocs.15)">Move-CsUser</A> cmdlet.</span></span>



</div>

<span data-ttu-id="00353-p200">Das Tool löscht Besprechungsdaten nur für inaktive Besprechungen. Aktive Besprechungen (oder Besprechungen in Sitzungen) können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="00353-p200">The tool deletes meeting data only for meetings that are inactive. Active meetings (or meetings in sessions) cannot be deleted.</span></span>

<span data-ttu-id="00353-p201">Dieses Tool muss auf einem Computer ausgeführt werden, der sich im selben Pool wie der Zielbenutzer befindet. Der Benutzer, dessen Besprechungsinhaltsdaten von diesem Tool verwaltet werden, muss im selben Benutzerpool verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="00353-p201">This tool must be run from a computer that is in the same pool as the target user. The user whose meeting content data is being managed by this tool must be homed in the same user pool.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="00353-810">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="00353-810">Output</span></span>

<span data-ttu-id="00353-811">Dieses Tool gibt die Ergebnisse der folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="00353-811">This tool outputs the results of each of the operations:</span></span>

  - <span data-ttu-id="00353-812">Wenn eine Abfrage ausgeführt wird, gibt das Tool die Liste aller inaktiven Besprechungsdatenordner aus, deren Organisator dieser Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="00353-812">If a query is performed, the tool outputs the list of all inactive meeting data folders that have that user as an organizer.</span></span>

  - <span data-ttu-id="00353-813">Wenn ein Löschvorgang ausgeführt wird, gibt das Tool die Liste aller Besprechungsdatenordner aus, deren Daten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="00353-813">If a delete is performed, the tool outputs the list of all meeting data folders whose data will be deleted.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="00353-814">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00353-814">Requirements</span></span>

<span data-ttu-id="00353-815">Das Tool muss im selben Pool ausgeführt werden, in dem der Organisator zurzeit verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="00353-815">The tool needs to be run in the same pool where the organizer is currently homed.</span></span>

<span data-ttu-id="00353-816">Das Tool muss mit Administratorrechten und mit Zugriff auf den Inhaltsdateispeicher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="00353-816">The tool must be run using administrator privileges with access to the Content File Store.</span></span>

</div>

<div>

## <a name="examples"></a><span data-ttu-id="00353-817">Beispiele</span><span class="sxs-lookup"><span data-stu-id="00353-817">Examples</span></span>

<span data-ttu-id="00353-818">In der folgenden Tabelle werden die Parameter beschrieben, die zum Teil in den Beispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00353-818">The following table describes the parameters, some of which are used in the examples.</span></span>

<span data-ttu-id="00353-819">![Parameter des Web conf-Datentools.] (images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parameter des Web conf-Datentools.")</span><span class="sxs-lookup"><span data-stu-id="00353-819">![Web Conf Data Tool parameters.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Web Conf Data Tool parameters.")</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

<span data-ttu-id="00353-p202">Das vorherige Beispiel zeigt, wie ein Abfragebefehl funktionieren würde. Die Ausgabe eines solchen Befehls wäre eine Liste aller Besprechungsinhaltsordner, die von diesem Tool betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="00353-p202">The preceding example shows how a query command would work. The output of such a command would be a list of all meeting content folders that would be affected by this tool.</span></span>

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

<span data-ttu-id="00353-p203">Oben sehen Sie ein Beispiel für einen Löschbefehl. Der Löschbefehl entfernt alle inaktiven Besprechungsordner dieses Benutzers.</span><span class="sxs-lookup"><span data-stu-id="00353-p203">The preceding is an example of a delete command. The delete command will remove all inactive meeting folders from this user.</span></span>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="00353-824">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00353-824">Summary</span></span>

<span data-ttu-id="00353-825">Dieses Tool kann eine wertvolle Ressource für Administratoren sein, die eine präzisere Kontrolle über Konferenzbesprechungsdaten benötigen.</span><span class="sxs-lookup"><span data-stu-id="00353-825">This tool can be a valuable resource to administrators who need more precise control over conference meeting data.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

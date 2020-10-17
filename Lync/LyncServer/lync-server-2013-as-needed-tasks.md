---
title: 'Lync Server 2013: erforderliche Aufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529542"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="34c0d-102">Erforderliche Aufgaben in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34c0d-102">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34c0d-103">_**Letztes Änderungsstand des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="34c0d-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="34c0d-104">Führen Sie bei Bedarf die folgenden Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="34c0d-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="34c0d-105">Sie werden häufig auch von Standardverfahren abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="34c0d-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="34c0d-106">**Vollständige Sicherheitsüberwachung   ** Sie können diese Überprüfung regelmäßig als Reaktion auf ein Upgrade oder ein Neuentwurf des Messagingsystems oder als Reaktion auf eine versuchte (oder erfolgreiche) Sicherheitsverletzung durchführen.</span><span class="sxs-lookup"><span data-stu-id="34c0d-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="34c0d-107">Das Verfahren kann Portscans auf Servern und Firewalls, Überwachung der Sicherheitsfixes und Tests hinsichtlich Zugriffsverletzungen durch Dritte beinhalten.</span><span class="sxs-lookup"><span data-stu-id="34c0d-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="34c0d-108">**Ersetzen von Zertifikaten zum Ablaufdatum**     Das Überprüfen lync Server Zertifikate ist eine der regelmäßigen wöchentlichen Aufgaben, und im Rahmen des Verfahrens sollte ein Administrator einen Datensatz mit Ablaufdatum aller Zertifikate aufweisen.</span><span class="sxs-lookup"><span data-stu-id="34c0d-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="34c0d-109">Dieser Datensatz ermöglicht es einem Administrator, eine Benachrichtigung zu erstellen, wenn ein bestimmtes Zertifikat abgelaufen ist und bei Bedarf ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="34c0d-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="34c0d-110">**Aktualisieren von Leistungsbasislinien**     Aktualisieren der Leistungsbasislinien nach einem Upgrade oder einer Konfigurationsänderung.</span><span class="sxs-lookup"><span data-stu-id="34c0d-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="34c0d-111">Ihre Organisation kann Basispläne verwenden, um Leistungsänderungen zu messen und Probleme zu erkennen, die sich auf die Systemleistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="34c0d-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="34c0d-112">**Verwalten von Enterprise-Pool**     Die anfängliche Konfiguration von Enterprise-Pools, Standard Edition-Servern und anderen Servern in der Umgebung Ihres Unternehmens erfolgte während der Bereitstellung der einzelnen Server.</span><span class="sxs-lookup"><span data-stu-id="34c0d-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="34c0d-113">Die Verwaltung nach der Bereitstellung von Servern und Pools für Standard Edition-Server und Enterprise-Pools umfasst die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="34c0d-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="34c0d-114">Verwalten von Front-End-Servern</span><span class="sxs-lookup"><span data-stu-id="34c0d-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="34c0d-115">Verwalten von Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="34c0d-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="34c0d-116">Verwalten von Konferenzen</span><span class="sxs-lookup"><span data-stu-id="34c0d-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="34c0d-117">Ändern von Dienstkontoanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="34c0d-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="34c0d-118">Verwalten von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="34c0d-118">Managing Databases</span></span>
    
      - <span data-ttu-id="34c0d-119">Starten und Beenden von Diensten und Deaktivieren von Server Rollen</span><span class="sxs-lookup"><span data-stu-id="34c0d-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="34c0d-120">Entfernen von Servern und Serverrollen, Entfernen von Pools und Außerbetriebnahme von Servern und Pools</span><span class="sxs-lookup"><span data-stu-id="34c0d-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="34c0d-121">**Verwalten der Verwendung**     Sie können lync Server 2013 so konfigurieren, dass die Features und Funktionen bereitgestellt werden, die für Ihre Organisation am besten geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="34c0d-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="34c0d-122">Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="34c0d-122">This includes the following:</span></span>
    
      - <span data-ttu-id="34c0d-123">Verwalten der Unterstützung für lokale Webkonferenzbesprechungen</span><span class="sxs-lookup"><span data-stu-id="34c0d-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="34c0d-124">Verwalten der Verwendung von Verteilergruppen zum Senden von Chatnachrichten</span><span class="sxs-lookup"><span data-stu-id="34c0d-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="34c0d-125">Verwalten von Kontakten, Anwesenheit und Abfragen</span><span class="sxs-lookup"><span data-stu-id="34c0d-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="34c0d-126">Konfigurieren der Client Versions Filterung</span><span class="sxs-lookup"><span data-stu-id="34c0d-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="34c0d-127">Konfigurieren der intelligenten Sofortnachrichtenfilterung</span><span class="sxs-lookup"><span data-stu-id="34c0d-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="34c0d-128">Konfigurieren der Archivierung, Aufzeichnung von Kommunikationsdatensätzen und erfüllen der Compliance</span><span class="sxs-lookup"><span data-stu-id="34c0d-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="34c0d-129">**Verwalten von Edgeserver Konnektivität**     Die laufende Verwaltung der Server und Einstellungen, die für die Bereitstellung externer Konnektivität erforderlich sind, umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="34c0d-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="34c0d-130">Verwalten der Konnektivität zwischen internen Servern und Edge-Servern</span><span class="sxs-lookup"><span data-stu-id="34c0d-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="34c0d-131">Konfigurieren interner und externer Schnittstellen und Zertifikate für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="34c0d-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="34c0d-132">Verwalten des Zugriffs durch Verbund Partner</span><span class="sxs-lookup"><span data-stu-id="34c0d-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="34c0d-133">**Verwalten des Adressbuchs**     Das Verwalten von Adressbuch Servern umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="34c0d-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="34c0d-134">Konfigurieren der Adressbuch Server-Telefon Normalisierung</span><span class="sxs-lookup"><span data-stu-id="34c0d-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="34c0d-135">Verwalten des Adressbuchservers über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="34c0d-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="34c0d-136">**Verwalten von Benutzerkonten**     Die Verwaltung von Benutzerkonten umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="34c0d-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="34c0d-137">Aktivieren von Benutzerkonten für lync Server</span><span class="sxs-lookup"><span data-stu-id="34c0d-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="34c0d-138">Konfigurieren von lync Server Benutzern mithilfe des Assistenten</span><span class="sxs-lookup"><span data-stu-id="34c0d-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="34c0d-139">Konfigurieren einzelner lync Server Benutzerkontoeigenschaften</span><span class="sxs-lookup"><span data-stu-id="34c0d-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="34c0d-140">Suchen nach lync Server Benutzern</span><span class="sxs-lookup"><span data-stu-id="34c0d-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="34c0d-141">Verschieben von lync Server Benutzern</span><span class="sxs-lookup"><span data-stu-id="34c0d-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="34c0d-142">Löschen von lync Server Benutzern</span><span class="sxs-lookup"><span data-stu-id="34c0d-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="34c0d-143">**Analysieren von lync Server 2013 Protokolldateien**     Ein sehr hilfreiches Tool, das in der Regel für die Problembehandlung verwendet wird, ist das lync Server 2013 Protokollierungstool, das ausführlich unter [using lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="34c0d-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="34c0d-144">Da das Protokollierungstool Protokolldateien (auf Serverebene) generiert, können diese Protokolldateien mithilfe des Tools Snooper angezeigt und analysiert werden, wenn die Microsoft Office Server 12 Resource Kit-Tools auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="34c0d-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="34c0d-145">Andernfalls können Protokolle auch mithilfe eines Text-Editors analysiert werden, was weitaus weniger transparent und komplexer ist als die Verwendung des Snooper-Dienstprogramms.</span><span class="sxs-lookup"><span data-stu-id="34c0d-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="34c0d-146">So zeigen Sie Protokollnachrichten an und analysieren Sie</span><span class="sxs-lookup"><span data-stu-id="34c0d-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="34c0d-147">Wenn Sie im Protokollierungstool die Debugsitzung beendet haben, klicken Sie auf Protokolldateien analysieren, um die Protokolldateien mithilfe des Tools Snooper anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="34c0d-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="34c0d-148">Sie können Protokoll Protokolle für die folgenden Komponenten analysieren:</span><span class="sxs-lookup"><span data-stu-id="34c0d-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="34c0d-149">Lync Server SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="34c0d-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="34c0d-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="34c0d-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="34c0d-151">Lync Server Konferenz Signalisierungs Datenverkehr (C3P), einschließlich MCU Infra C3P und Focus C3P</span><span class="sxs-lookup"><span data-stu-id="34c0d-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="34c0d-152">Lync Server-Webkonferenz Datenverkehr (PSOM)</span><span class="sxs-lookup"><span data-stu-id="34c0d-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="34c0d-153">Lync Server Unified Communications Clientplattform-Client (uccp)</span><span class="sxs-lookup"><span data-stu-id="34c0d-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="34c0d-154">Fehlerberichte aus der Archivierungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="34c0d-154">Error reports from the archiving database</span></span>

<span data-ttu-id="34c0d-155">Informationen zum Organisieren der Leistung von nach Bedarf ausgeführten Aufgaben finden Sie unter Checkliste für As-Needed Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="34c0d-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="34c0d-156">Ausführliche Verwaltungs-und Verwaltungsverfahren finden Sie im Microsoft lync Server 2013 Administration Guide.</span><span class="sxs-lookup"><span data-stu-id="34c0d-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="34c0d-157">Sicherungs-(und Wiederherstellungs-) Richtlinien oder Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="34c0d-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="34c0d-158">Lync Server 2013 können Sie das gesamte System sichern und wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="34c0d-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="34c0d-159">IIf Sie möchten eine einzelne Richtlinie oder eine einzelne Auflistung von Konfigurationseinstellungen sichern (und dann möglicherweise eines Tages wiederherstellen), die entsprechende Richtlinie abrufen und das Objekt dann an das Export-Clixml-Cmdlet weiterleiten, wodurch die Richtlinieninformationen als XML-Datei gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="34c0d-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="34c0d-160">Sie können jetzt mit RedmondClientPolicy experimentieren und viele Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="34c0d-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="34c0d-161">Wenn Sie stattdessen die alte Richtlinie wiederherstellen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="34c0d-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="34c0d-162">Beachten Sie, dass dieser Ansatz für die meisten Richtlinien und Einstellungen funktioniert, aber nicht mit einigen der komplexeren Elemente – Elemente, die mehrere unter Objekte enthalten (wie Routing Konfigurationseinstellungen, die viele getrennte VoIP-Routen enthalten).</span><span class="sxs-lookup"><span data-stu-id="34c0d-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


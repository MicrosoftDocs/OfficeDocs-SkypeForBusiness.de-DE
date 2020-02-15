---
title: 'Lync Server 2013: neue und geänderte Einstellungen für lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45282476beac35df7248c4ef6bd04c6642a0f1e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="a4c43-102">Neue und geänderte Einstellungen für lync 2013</span><span class="sxs-lookup"><span data-stu-id="a4c43-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4c43-103">_**Letztes Änderungsstand des Themas:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="a4c43-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="a4c43-104">In diesem Thema werden Änderungen an lync Server-Verwaltungsshell-Cmdlets erläutert, die direkt mit der Clientverwaltung in Zusammenhangstehen.</span><span class="sxs-lookup"><span data-stu-id="a4c43-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="a4c43-105">In lync Server 2013 werden mehrere neue Parameter eingeführt, und Parameter für Features, die mit anderen Mitteln konfiguriert werden können, werden veraltet.</span><span class="sxs-lookup"><span data-stu-id="a4c43-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="a4c43-106">Neue Client Verwaltungsparameter</span><span class="sxs-lookup"><span data-stu-id="a4c43-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c43-107">Neu</span><span class="sxs-lookup"><span data-stu-id="a4c43-107">New</span></span></th>
<th><span data-ttu-id="a4c43-108">Lync Server-Verwaltungsshell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4c43-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="a4c43-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4c43-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="a4c43-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="a4c43-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-112">Bei Festlegung auf "true" wird die Software Ablaufverfolgung in lync aktiviert; bei Festlegung auf "false" wird die Software Ablaufverfolgung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4c43-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="a4c43-113">Die Softwareablaufverfolgung umfasst das Aufzeichnen detaillierter Informationen zu allen Abläufen in einem Programm (einschließlich API-Aufrufe).</span><span class="sxs-lookup"><span data-stu-id="a4c43-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="a4c43-114">Die Ablaufverfolgung ist vor allem für Entwickler und Anwendungssupport Mitarbeiter hilfreich. Diese Einstellung entspricht der Einstellung &quot;Communications Server 2007 R2 Gruppenrichtlinie die Ablaufverfolgung für Communicator aktivieren. &quot; Die Einstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a4c43-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4c43-115">Off = Ablaufverfolgung ist deaktiviert, und der Benutzer kann diese Einstellung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a4c43-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="a4c43-116">Light = minimale Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a4c43-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="a4c43-117">On = ausführliche Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a4c43-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="a4c43-118">Standardmäßig ist TracingLevel auf einen NULL-Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4c43-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="a4c43-119">Das bedeutet, dass eine minimale Ablaufverfolgung durchgeführt wird, der Benutzer jedoch diese minimale Ablaufverfolgung aktivieren oder deaktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="a4c43-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-120">"Enablemediaredirection"</span><span class="sxs-lookup"><span data-stu-id="a4c43-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="a4c43-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-122">Bei Festlegung auf "true" ($true) können Audio-und Videostreams von anderem Netzwerkdatenverkehr getrennt werden, dies wiederum ermöglicht Clientgeräten das Codieren und Decodieren von Audio-und Videodaten lokal.</span><span class="sxs-lookup"><span data-stu-id="a4c43-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="a4c43-123">Die Medien Umleitung führt in der Regel zu einer niedrigeren Bandbreitennutzung, höherer Serverskalierbarkeit und einer optimalen Benutzererfahrung im Vergleich zu ähnlichen Techniken wie Geräte Remoting oder Codec-Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="a4c43-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="a4c43-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="a4c43-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="a4c43-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="a4c43-126">Bei Festlegung auf "true" werden alle lync- &quot;Besprechungen als große Besprechungen behandelt. &quot; Bei einer großen Besprechung werden Einschränkungen für die Anzahl der Benachrichtigungen, die an die Teilnehmer gesendet werden, zusätzlich zur Größe der standardmäßig übermittelten Besprechungsliste erteilt.</span><span class="sxs-lookup"><span data-stu-id="a4c43-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="a4c43-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="a4c43-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="a4c43-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="a4c43-129">Bei Festlegung auf "true" ($true) können Benutzer keine Anmerkungen zu PowerPoint-Folien hinzufügen, die in einer Konferenz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4c43-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="a4c43-130">(Abhängig vom Wert der AllowAnnotations-Eigenschaft) können Benutzer jedoch weiterhin auf andere Whiteboardfunktionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a4c43-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="a4c43-131">Der Standardwert ist false, was bedeutet, dass PowerPoint-Anmerkungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a4c43-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="a4c43-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="a4c43-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="a4c43-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="a4c43-134">Bei Festlegung auf "true" (Standardwert) werden alle geöffneten OneNote-Notizbücher, die mit der Konferenz verknüpft sind, automatisch mit Informationen wie Konferenzteilnehmern und Details zu Inhalten aktualisiert, die während der Konferenz freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a4c43-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="a4c43-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="a4c43-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a4c43-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="a4c43-137">Wird zusammen mit den anderen neuen CsMeetingConfiguration-Parametern verwendet, um die vom Online-Besprechungs-Add-in generierten Besprechungseinladungen für lync 2013 anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a4c43-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="a4c43-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="a4c43-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a4c43-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="a4c43-140">Fügt das Logo Ihrer Organisation allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a4c43-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="a4c43-141">Sie geben die URL eines GIF-oder JPG-Bilds an.</span><span class="sxs-lookup"><span data-stu-id="a4c43-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-142">HelpUrl</span><span class="sxs-lookup"><span data-stu-id="a4c43-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="a4c43-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a4c43-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="a4c43-144">Fügt die Hilfe-oder Support-URL Ihrer Organisation zu allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a4c43-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="a4c43-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="a4c43-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a4c43-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="a4c43-147">Fügt alle Einladungen, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden, juristischen Text oder Haftungsausschluss Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4c43-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="a4c43-148">Sie geben die URL für den Speicherort des Texts an.</span><span class="sxs-lookup"><span data-stu-id="a4c43-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="a4c43-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="a4c43-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a4c43-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="a4c43-151">Fügt eine benutzerdefinierte Fußzeile zu allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a4c43-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="a4c43-152">Sie geben die URL für den Speicherort des benutzerdefinierten Fußzeilentexts an.</span><span class="sxs-lookup"><span data-stu-id="a4c43-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="a4c43-153">Veraltete Client Verwaltungsparameter</span><span class="sxs-lookup"><span data-stu-id="a4c43-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4c43-154">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4c43-154">Parameter</span></span></th>
<th><span data-ttu-id="a4c43-155">Lync Server-Verwaltungsshell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a4c43-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="a4c43-156">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4c43-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="a4c43-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="a4c43-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-159">Dieser Parameter ist für die Verwendung mit lync Server 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a4c43-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="a4c43-160">Bei Verwendung in Verbindung mit EnableEnterpriseCustomizedHelp wurde mit diesem Parameter eine Organisation zur Angabe einer URL aktiviert, sodass Benutzer, die auf das Hilfemenü in lync geklickt haben, eine angepasste Hilfe anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="a4c43-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="a4c43-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="a4c43-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-163">Dieser Parameter ist für die Verwendung mit lync Server 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a4c43-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="a4c43-164">Wenn dieser Parameter in Verbindung mit CustomizedHelpUrl verwendet wird, konnten Organisationen angepasste Hilfe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a4c43-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="a4c43-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="a4c43-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-167">Der Parameter EnableSQMData des Cmdlets "CSClientPolicy" wurde in lync Server 2013 entfernt.</span><span class="sxs-lookup"><span data-stu-id="a4c43-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="a4c43-168">Stattdessen können Sie die freigegebene Gruppenrichtlinieneinstellung für QM-Daten (Software Quality Management) verwenden, um die Benutzeroberfläche für die Option zur Verbesserung der Benutzerfreundlichkeit auf der Seite Allgemeine lync-Clientoptionen zu bestimmen:</span><span class="sxs-lookup"><span data-stu-id="a4c43-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="a4c43-169">HKEY_CURRENT_USER \software\policies\microsoft\office\common\qmenable</span><span class="sxs-lookup"><span data-stu-id="a4c43-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="a4c43-170">Werte</span><span class="sxs-lookup"><span data-stu-id="a4c43-170">Values:</span></span></p>
<p><span data-ttu-id="a4c43-171">1 = anzeigen und Aktivieren des Kontrollkästchens (der Benutzer kann das Kontrollkästchen deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="a4c43-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="a4c43-172">0 = das Kontrollkästchen deaktivieren und deaktivieren (Benutzer kann nicht außer Kraft gesetzt werden)</span><span class="sxs-lookup"><span data-stu-id="a4c43-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="a4c43-173">NULL = der Wert wird durch das Office-Setup festgelegt, und das Kontrollkästchen wird angezeigt, damit Benutzer sich bei Ihrer Wahl festlegen können.</span><span class="sxs-lookup"><span data-stu-id="a4c43-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="a4c43-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="a4c43-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-176">Dieser Parameter wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="a4c43-176">This parameter has been removed.</span></span> <span data-ttu-id="a4c43-177">Wenn Sie stattdessen lync Server 2013 bereitstellen und die Topologie veröffentlichen, wird der einheitliche Kontaktspeicher standardmäßig für alle Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a4c43-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="a4c43-178">Dies bedeutet, dass alle Kontakte eines Benutzers in Exchange aufbewahrt werden und in lync, Outlook und Outlook Web Access verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a4c43-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="a4c43-179">Mit dem Cmdlet "csuserservicespolicy" "können Sie anpassen, welche Benutzer einen einheitlichen Kontaktspeicher zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="a4c43-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="a4c43-180">Sie können Benutzer Global, nach Standort, nach Mandanten oder nach Einzelpersonen oder Personengruppen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a4c43-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="a4c43-181">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a4c43-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4c43-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="a4c43-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="a4c43-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-184">Dieser Parameter wird von lync 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4c43-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="a4c43-185">In früheren Versionen hat dieser Parameter angegeben, wie oft der Client MAPI-Daten aus öffentlichen Exchange-Ordnern abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="a4c43-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4c43-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="a4c43-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="a4c43-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="a4c43-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="a4c43-188">Dieser Parameter wurde in lync 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a4c43-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


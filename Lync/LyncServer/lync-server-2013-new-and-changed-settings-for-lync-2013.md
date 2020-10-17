---
title: 'Lync Server 2013: neue und geänderte Einstellungen für lync 2013'
description: 'Lync Server 2013: neue und geänderte Einstellungen für lync 2013.'
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
ms.openlocfilehash: 1bf744e1bae774904733390ec624be523ad32bc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561391"
---
# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="c453d-103">Neue und geänderte Einstellungen für lync 2013</span><span class="sxs-lookup"><span data-stu-id="c453d-103">New and changed settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c453d-104">_**Letztes Änderungsstand des Themas:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="c453d-104">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="c453d-105">In diesem Thema werden Änderungen an lync Server-Verwaltungsshell-Cmdlets erläutert, die direkt mit der Clientverwaltung in Zusammenhangstehen.</span><span class="sxs-lookup"><span data-stu-id="c453d-105">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="c453d-106">In lync Server 2013 werden mehrere neue Parameter eingeführt, und Parameter für Features, die mit anderen Mitteln konfiguriert werden können, werden veraltet.</span><span class="sxs-lookup"><span data-stu-id="c453d-106">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="c453d-107">Neue Client Verwaltungsparameter</span><span class="sxs-lookup"><span data-stu-id="c453d-107">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c453d-108">Neu</span><span class="sxs-lookup"><span data-stu-id="c453d-108">New</span></span></th>
<th><span data-ttu-id="c453d-109">Lync Server-Verwaltungsshell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c453d-109">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="c453d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c453d-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c453d-111">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="c453d-111">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="c453d-112">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-112">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-113">Bei Festlegung auf "true" wird die Software Ablaufverfolgung in lync aktiviert; bei Festlegung auf "false" wird die Software Ablaufverfolgung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c453d-113">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="c453d-114">Die Softwareablaufverfolgung umfasst das Aufzeichnen detaillierter Informationen zu allen Abläufen in einem Programm (einschließlich API-Aufrufe).</span><span class="sxs-lookup"><span data-stu-id="c453d-114">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="c453d-115">Die Ablaufverfolgung ist vor allem für Entwickler und Anwendungssupport Mitarbeiter hilfreich. Diese Einstellung entspricht der Einstellung Communications Server 2007 R2 Gruppenrichtlinie die &quot; Ablaufverfolgung für Communicator aktivieren. &quot; Die Einstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c453d-115">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c453d-116">Off = Ablaufverfolgung ist deaktiviert, und der Benutzer kann diese Einstellung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c453d-116">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="c453d-117">Light = minimale Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c453d-117">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="c453d-118">On = ausführliche Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c453d-118">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="c453d-119">Standardmäßig ist TracingLevel auf einen NULL-Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c453d-119">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="c453d-120">Das bedeutet, dass eine minimale Ablaufverfolgung durchgeführt wird, der Benutzer jedoch diese minimale Ablaufverfolgung aktivieren oder deaktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="c453d-120">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-121">"Enablemediaredirection"</span><span class="sxs-lookup"><span data-stu-id="c453d-121">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="c453d-122">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-122">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-123">Bei Festlegung auf "true" ($true) können Audio-und Videostreams von anderem Netzwerkdatenverkehr getrennt werden, dies wiederum ermöglicht Clientgeräten das Codieren und Decodieren von Audio-und Videodaten lokal.</span><span class="sxs-lookup"><span data-stu-id="c453d-123">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="c453d-124">Die Medien Umleitung führt in der Regel zu einer niedrigeren Bandbreitennutzung, höherer Serverskalierbarkeit und einer optimalen Benutzererfahrung im Vergleich zu ähnlichen Techniken wie Geräte Remoting oder Codec-Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="c453d-124">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c453d-125">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="c453d-125">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="c453d-126">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="c453d-126">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="c453d-127">Bei Festlegung auf "true" werden alle lync-Besprechungen als &quot; große Besprechungen behandelt. &quot; Bei einer großen Besprechung werden Einschränkungen für die Anzahl der Benachrichtigungen, die an die Teilnehmer gesendet werden, zusätzlich zur Größe der standardmäßig übermittelten Besprechungsliste erteilt.</span><span class="sxs-lookup"><span data-stu-id="c453d-127">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-128">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="c453d-128">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="c453d-129">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="c453d-129">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="c453d-130">Bei Festlegung auf "true" ($true) können Benutzer keine Anmerkungen zu PowerPoint-Folien hinzufügen, die in einer Konferenz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c453d-130">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="c453d-131">(Abhängig vom Wert der AllowAnnotations-Eigenschaft) können Benutzer jedoch weiterhin auf andere Whiteboardfunktionen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c453d-131">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="c453d-132">Der Standardwert ist false, was bedeutet, dass PowerPoint-Anmerkungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="c453d-132">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c453d-133">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="c453d-133">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="c453d-134">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="c453d-134">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="c453d-135">Bei Festlegung auf "true" (Standardwert) werden alle geöffneten OneNote-Notizbücher, die mit der Konferenz verknüpft sind, automatisch mit Informationen wie Konferenzteilnehmern und Details zu Inhalten aktualisiert, die während der Konferenz freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="c453d-135">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-136">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="c453d-136">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="c453d-137">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c453d-137">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="c453d-138">Wird zusammen mit den anderen neuen CsMeetingConfiguration-Parametern verwendet, um die vom Online-Besprechungs-Add-in generierten Besprechungseinladungen für lync 2013 anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c453d-138">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c453d-139">LogoURL</span><span class="sxs-lookup"><span data-stu-id="c453d-139">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="c453d-140">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c453d-140">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="c453d-141">Fügt das Logo Ihrer Organisation allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c453d-141">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="c453d-142">Sie geben die URL eines GIF-oder JPG-Bilds an.</span><span class="sxs-lookup"><span data-stu-id="c453d-142">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-143">HelpUrl</span><span class="sxs-lookup"><span data-stu-id="c453d-143">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="c453d-144">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c453d-144">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="c453d-145">Fügt die Hilfe-oder Support-URL Ihrer Organisation zu allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c453d-145">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c453d-146">LegalURL</span><span class="sxs-lookup"><span data-stu-id="c453d-146">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="c453d-147">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c453d-147">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="c453d-148">Fügt alle Einladungen, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden, juristischen Text oder Haftungsausschluss Text hinzu.</span><span class="sxs-lookup"><span data-stu-id="c453d-148">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="c453d-149">Sie geben die URL für den Speicherort des Texts an.</span><span class="sxs-lookup"><span data-stu-id="c453d-149">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-150">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="c453d-150">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="c453d-151">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c453d-151">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="c453d-152">Fügt eine benutzerdefinierte Fußzeile zu allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c453d-152">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="c453d-153">Sie geben die URL für den Speicherort des benutzerdefinierten Fußzeilentexts an.</span><span class="sxs-lookup"><span data-stu-id="c453d-153">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="c453d-154">Veraltete Client Verwaltungsparameter</span><span class="sxs-lookup"><span data-stu-id="c453d-154">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c453d-155">Parameter</span><span class="sxs-lookup"><span data-stu-id="c453d-155">Parameter</span></span></th>
<th><span data-ttu-id="c453d-156">Lync Server-Verwaltungsshell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c453d-156">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="c453d-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c453d-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c453d-158">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="c453d-158">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="c453d-159">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-159">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-160">Dieser Parameter ist für die Verwendung mit lync Server 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="c453d-160">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="c453d-161">Bei Verwendung in Verbindung mit EnableEnterpriseCustomizedHelp wurde mit diesem Parameter eine Organisation zur Angabe einer URL aktiviert, sodass Benutzer, die auf das Hilfemenü in lync geklickt haben, eine angepasste Hilfe anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c453d-161">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-162">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="c453d-162">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="c453d-163">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-163">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-164">Dieser Parameter ist für die Verwendung mit lync Server 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="c453d-164">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="c453d-165">Wenn dieser Parameter in Verbindung mit CustomizedHelpUrl verwendet wird, konnten Organisationen angepasste Hilfe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c453d-165">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c453d-166">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="c453d-166">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="c453d-167">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-167">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-168">Der Parameter EnableSQMData des Cmdlets Set-CSClientPolicy wurde in lync Server 2013 entfernt.</span><span class="sxs-lookup"><span data-stu-id="c453d-168">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="c453d-169">Stattdessen können Sie die freigegebene Gruppenrichtlinieneinstellung für QM-Daten (Software Quality Management) verwenden, um die Benutzeroberfläche für die Option zur Verbesserung der Benutzerfreundlichkeit auf der Seite Allgemeine lync-Clientoptionen zu bestimmen:</span><span class="sxs-lookup"><span data-stu-id="c453d-169">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="c453d-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="c453d-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="c453d-171">Werte</span><span class="sxs-lookup"><span data-stu-id="c453d-171">Values:</span></span></p>
<p><span data-ttu-id="c453d-172">1 = anzeigen und Aktivieren des Kontrollkästchens (der Benutzer kann das Kontrollkästchen deaktivieren)</span><span class="sxs-lookup"><span data-stu-id="c453d-172">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="c453d-173">0 = das Kontrollkästchen deaktivieren und deaktivieren (Benutzer kann nicht außer Kraft gesetzt werden)</span><span class="sxs-lookup"><span data-stu-id="c453d-173">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="c453d-174">NULL = der Wert wird durch das Office-Setup festgelegt, und das Kontrollkästchen wird angezeigt, damit Benutzer sich bei Ihrer Wahl festlegen können.</span><span class="sxs-lookup"><span data-stu-id="c453d-174">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-175">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="c453d-175">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="c453d-176">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-176">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-177">Dieser Parameter wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="c453d-177">This parameter has been removed.</span></span> <span data-ttu-id="c453d-178">Wenn Sie stattdessen lync Server 2013 bereitstellen und die Topologie veröffentlichen, wird der einheitliche Kontaktspeicher standardmäßig für alle Benutzer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c453d-178">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="c453d-179">Dies bedeutet, dass alle Kontakte eines Benutzers in Exchange aufbewahrt werden und in lync, Outlook und Outlook Web Access verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c453d-179">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="c453d-180">Mit dem Set-CsUserServicesPolicy-Cmdlet können Sie anpassen, welche Benutzer einen einheitlichen Kontaktspeicher zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="c453d-180">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="c453d-181">Sie können Benutzer Global, nach Standort, nach Mandanten oder nach Einzelpersonen oder Personengruppen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c453d-181">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="c453d-182">Ausführliche Informationen finden Sie unter <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c453d-182">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c453d-183">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="c453d-183">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="c453d-184">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-184">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-185">Dieser Parameter wird von lync 2013 nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c453d-185">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="c453d-186">In früheren Versionen hat dieser Parameter angegeben, wie oft der Client MAPI-Daten aus öffentlichen Exchange-Ordnern abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="c453d-186">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c453d-187">DisableICE</span><span class="sxs-lookup"><span data-stu-id="c453d-187">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="c453d-188">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c453d-188">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="c453d-189">Dieser Parameter wurde in lync 2013 veraltet.</span><span class="sxs-lookup"><span data-stu-id="c453d-189">This parameter was deprecated in Lync 2013.</span></span></p></td>
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


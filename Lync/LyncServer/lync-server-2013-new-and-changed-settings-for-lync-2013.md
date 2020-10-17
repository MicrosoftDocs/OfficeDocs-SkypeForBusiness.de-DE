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
ms.openlocfilehash: 5aa98f8935a692f06b78db523e4e109e8cba9ddf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505432"
---
# <a name="new-and-changed-settings-for-lync-2013"></a>Neue und geänderte Einstellungen für lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-05_

In diesem Thema werden Änderungen an lync Server-Verwaltungsshell-Cmdlets erläutert, die direkt mit der Clientverwaltung in Zusammenhangstehen. In lync Server 2013 werden mehrere neue Parameter eingeführt, und Parameter für Features, die mit anderen Mitteln konfiguriert werden können, werden veraltet.

<div>

## <a name="new-client-management-parameters"></a>Neue Client Verwaltungsparameter


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Neu</th>
<th>Lync Server-Verwaltungsshell-Cmdlet</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Bei Festlegung auf "true" wird die Software Ablaufverfolgung in lync aktiviert; bei Festlegung auf "false" wird die Software Ablaufverfolgung deaktiviert. Die Softwareablaufverfolgung umfasst das Aufzeichnen detaillierter Informationen zu allen Abläufen in einem Programm (einschließlich API-Aufrufe). Die Ablaufverfolgung ist vor allem für Entwickler und Anwendungssupport Mitarbeiter hilfreich. Diese Einstellung entspricht der Einstellung Communications Server 2007 R2 Gruppenrichtlinie die &quot; Ablaufverfolgung für Communicator aktivieren. &quot; Die Einstellungen lauten wie folgt:</p>
<ul>
<li><p>Off = Ablaufverfolgung ist deaktiviert, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
<li><p>Light = minimale Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
<li><p>On = ausführliche Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
</ul>
<p>Standardmäßig ist TracingLevel auf einen NULL-Wert festgelegt. Das bedeutet, dass eine minimale Ablaufverfolgung durchgeführt wird, der Benutzer jedoch diese minimale Ablaufverfolgung aktivieren oder deaktivieren kann.</p></td>
</tr>
<tr class="even">
<td><p>"Enablemediaredirection"</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Bei Festlegung auf "true" ($true) können Audio-und Videostreams von anderem Netzwerkdatenverkehr getrennt werden, dies wiederum ermöglicht Clientgeräten das Codieren und Decodieren von Audio-und Videodaten lokal. Die Medien Umleitung führt in der Regel zu einer niedrigeren Bandbreitennutzung, höherer Serverskalierbarkeit und einer optimalen Benutzererfahrung im Vergleich zu ähnlichen Techniken wie Geräte Remoting oder Codec-Komprimierung.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf "true" werden alle lync-Besprechungen als &quot; große Besprechungen behandelt. &quot; Bei einer großen Besprechung werden Einschränkungen für die Anzahl der Benachrichtigungen, die an die Teilnehmer gesendet werden, zusätzlich zur Größe der standardmäßig übermittelten Besprechungsliste erteilt.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf "true" ($true) können Benutzer keine Anmerkungen zu PowerPoint-Folien hinzufügen, die in einer Konferenz verwendet werden. (Abhängig vom Wert der AllowAnnotations-Eigenschaft) können Benutzer jedoch weiterhin auf andere Whiteboardfunktionen zugreifen. Der Standardwert ist false, was bedeutet, dass PowerPoint-Anmerkungen zulässig sind.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf "true" (Standardwert) werden alle geöffneten OneNote-Notizbücher, die mit der Konferenz verknüpft sind, automatisch mit Informationen wie Konferenzteilnehmern und Details zu Inhalten aktualisiert, die während der Konferenz freigegeben wurden.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Wird zusammen mit den anderen neuen CsMeetingConfiguration-Parametern verwendet, um die vom Online-Besprechungs-Add-in generierten Besprechungseinladungen für lync 2013 anzupassen.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt das Logo Ihrer Organisation allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden. Sie geben die URL eines GIF-oder JPG-Bilds an.</p></td>
</tr>
<tr class="even">
<td><p>HelpUrl</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt die Hilfe-oder Support-URL Ihrer Organisation zu allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt alle Einladungen, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden, juristischen Text oder Haftungsausschluss Text hinzu. Sie geben die URL für den Speicherort des Texts an.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt eine benutzerdefinierte Fußzeile zu allen Einladungen hinzu, die vom Online-Besprechungs-Add-in für lync 2013 generiert wurden. Sie geben die URL für den Speicherort des benutzerdefinierten Fußzeilentexts an.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>Veraltete Client Verwaltungsparameter


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Lync Server-Verwaltungsshell-Cmdlet</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter ist für die Verwendung mit lync Server 2013 veraltet. Bei Verwendung in Verbindung mit EnableEnterpriseCustomizedHelp wurde mit diesem Parameter eine Organisation zur Angabe einer URL aktiviert, sodass Benutzer, die auf das Hilfemenü in lync geklickt haben, eine angepasste Hilfe anzeigen können.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter ist für die Verwendung mit lync Server 2013 veraltet. Wenn dieser Parameter in Verbindung mit CustomizedHelpUrl verwendet wird, konnten Organisationen angepasste Hilfe anzeigen.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Der Parameter EnableSQMData des Cmdlets Set-CSClientPolicy wurde in lync Server 2013 entfernt. Stattdessen können Sie die freigegebene Gruppenrichtlinieneinstellung für QM-Daten (Software Quality Management) verwenden, um die Benutzeroberfläche für die Option zur Verbesserung der Benutzerfreundlichkeit auf der Seite Allgemeine lync-Clientoptionen zu bestimmen:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Werte</p>
<p>1 = anzeigen und Aktivieren des Kontrollkästchens (der Benutzer kann das Kontrollkästchen deaktivieren)</p>
<p>0 = das Kontrollkästchen deaktivieren und deaktivieren (Benutzer kann nicht außer Kraft gesetzt werden)</p>
<p>NULL = der Wert wird durch das Office-Setup festgelegt, und das Kontrollkästchen wird angezeigt, damit Benutzer sich bei Ihrer Wahl festlegen können.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wurde entfernt. Wenn Sie stattdessen lync Server 2013 bereitstellen und die Topologie veröffentlichen, wird der einheitliche Kontaktspeicher standardmäßig für alle Benutzer aktiviert. Dies bedeutet, dass alle Kontakte eines Benutzers in Exchange aufbewahrt werden und in lync, Outlook und Outlook Web Access verfügbar sind. Mit dem Set-CsUserServicesPolicy-Cmdlet können Sie anpassen, welche Benutzer einen einheitlichen Kontaktspeicher zur Verfügung haben. Sie können Benutzer Global, nach Standort, nach Mandanten oder nach Einzelpersonen oder Personengruppen aktivieren. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wird von lync 2013 nicht verwendet. In früheren Versionen hat dieser Parameter angegeben, wie oft der Client MAPI-Daten aus öffentlichen Exchange-Ordnern abgerufen hat.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wurde in lync 2013 veraltet.</p></td>
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


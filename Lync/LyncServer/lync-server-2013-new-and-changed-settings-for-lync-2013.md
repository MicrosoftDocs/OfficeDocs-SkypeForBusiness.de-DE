---
title: 'Lync Server 2013: neue und geänderte Einstellungen für lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Neue und geänderte Einstellungen für lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-05_

In diesem Thema werden Änderungen an Cmdlets der lync Server-Verwaltungsshell erläutert, die sich direkt auf die Clientverwaltung beziehen. Lync Server 2013 führt verschiedene neue Parameter ein und verwirft Parameter für Features, die auf andere Weise konfiguriert werden können.

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
<th>Cmdlet "lync Server-Verwaltungsshell"</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Wenn Sie auf "true" festgelegt ist, wird die Software Ablaufverfolgung in lync aktiviert. Wenn Sie auf false festgelegt ist, wird die Software Ablaufverfolgung deaktiviert. Bei der Software Ablaufverfolgung wird eine detaillierte Aufzeichnung aller Elemente des Programms (einschließlich nach Verfolgungs-API-aufrufen) unterhalten. Die Ablaufverfolgung ist für Entwickler und das Supportpersonal der Anwendung hauptsächlich hilfreich. Diese Einstellung entspricht der Gruppenrichtlinieneinstellung &quot;Communications Server 2007 R2 aktivieren der Ablaufverfolgung für Communicator. &quot; Die Einstellungen lauten wie folgt:</p>
<ul>
<li><p>Off = Ablaufverfolgung ist deaktiviert, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
<li><p>Light = minimale Nachverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
<li><p>On = Verbose-Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
</ul>
<p>Standardmäßig ist TracingLevel auf einen NULL-Wert festzulegen. Das bedeutet, dass die minimale Ablaufverfolgung ausgeführt wird, aber der Benutzer kann diese minimale Ablaufverfolgung aktivieren oder deaktivieren.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Wenn der Wert auf true ($true) festgelegt ist, können Audio-und Videodatenströme vom anderen Netzwerkdatenverkehr getrennt werden, was wiederum Clientgeräten ermöglicht, Audio-und Videodaten lokal zu codieren und zu decodieren. Die Medien Umleitung führt in der Regel zu einer niedrigeren Bandbreitennutzung, höherer Serverskalierbarkeit und einer optimierten Benutzererfahrung im Vergleich zu ähnlichen Techniken wie Geräte-Remoting oder Codec-Komprimierung.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Wenn Sie auf "true" festgelegt ist, werden &quot;alle lync-Besprechungen als große Besprechungen behandelt. &quot; Bei einer großen Besprechung werden Einschränkungen für die Anzahl der Benachrichtigungen, die an die Teilnehmer gesendet werden, sowie die Größe des standardmäßig übermittelten Besprechungs Arbeitsplans festgestellt.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf true ($true) können Benutzer keine Anmerkungen zu PowerPoint-Folien hinzufügen, die in einer Konferenz verwendet werden. Je nach dem Wert der AllowAnnotations-Eigenschaft können die Benutzer jedoch weiterhin auf andere Whiteboard-Features zugreifen. Der Standardwert ist "falsch", was bedeutet, dass PowerPoint-Anmerkungen zulässig sind.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Wenn auf "true" (der Standardwert) festgelegt ist, werden alle geöffneten OneNote-Notizbücher, die mit der Konferenz verknüpft sind, automatisch mit Informationen wie Konferenzteilnehmern und Details zu den während der Konferenz freigegebenen Inhalten aktualisiert.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Wird zusammen mit den anderen neuen CsMeetingConfiguration-Parametern verwendet, um die vom Online Besprechungs-Add-in für lync 2013 generierten Besprechungseinladungen anzupassen.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt dem Logo Ihrer Organisation alle Einladungen hinzu, die vom Online Besprechungs-Add-in für lync 2013 generiert wurden. Sie geben die URL eines GIF-oder JPG-Bilds an.</p></td>
</tr>
<tr class="even">
<td><p>HelpUrl</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt die Hilfe-oder Support-URL Ihrer Organisation zu allen Einladungen hinzu, die vom Online Besprechungs-Add-in für lync 2013 generiert wurden.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt allen Einladungen, die vom Online Besprechungs-Add-in für lync 2013 generiert wurden, juristischen Text oder Verzichts Text hinzu. Sie geben die URL für den Speicherort des Texts an.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt allen Einladungen, die vom Online Besprechungs-Add-in für lync 2013 generiert wurden, eine benutzerdefinierte Fußzeile hinzu. Sie geben die URL für den Speicherort des benutzerdefinierten Fußzeilentexts an.</p></td>
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
<th>Cmdlet "lync Server-Verwaltungsshell"</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wurde für die Verwendung mit lync Server 2013 veraltet. Bei Verwendung in Verbindung mit EnableEnterpriseCustomizedHelp ermöglicht dieser Parameter einer Organisation, eine URL anzugeben, damit Benutzer, die auf das Menü "Hilfe" in lync geklickt haben, eine angepasste Hilfe anzeigen können.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wurde für die Verwendung mit lync Server 2013 veraltet. Wenn dieser Parameter in Verbindung mit CustomizedHelpUrl verwendet wird, konnten Organisationen angepasste Hilfe anzeigen.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Der EnableSQMData-Parameter des Cmdlets "Satz-CSClientPolicy" wurde in lync Server 2013 entfernt. Stattdessen können Sie die freigegebene Gruppenrichtlinieneinstellung für Software Quality Management (qm)-Daten verwenden, um die Benutzeroberfläche für die Option zur Verbesserung der Benutzerfreundlichkeit auf der Seite lync-Client-allgemeine Optionen zu ermitteln:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Werte</p>
<p>1 = Anzeige und Aktivieren des Kontrollkästchens (der Benutzer kann das Kontrollkästchen deaktivieren)</p>
<p>0 = deaktivieren und Deaktivieren des Kontrollkästchens (Benutzer können nicht überschreiben)</p>
<p>NULL = der Wert wird durch das Office-Setup festgelegt, und das Kontrollkästchen wird angezeigt, damit die Benutzer Ihre Auswahl treffen können.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wurde entfernt. Wenn Sie stattdessen lync Server 2013 bereitstellen und die Topologie veröffentlichen, ist der Unified Contact Store standardmäßig für alle Benutzer aktiviert. Dies bedeutet, dass alle Kontakte eines Benutzers in Exchange aufbewahrt werden und in lync, Outlook und Outlook Web Access zur Verfügung stehen. Sie können das Cmdlet "festlegen-CsUserServicesPolicy" verwenden, um die verfügbaren Unified Contact Store-Benutzer anzupassen. Sie können Benutzer Global, nach Website, nach Mandanten oder nach Einzelpersonen oder Gruppen von Personen aktivieren. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Aktivieren von Benutzern für den Unified Contact Store in lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wird von lync 2013 nicht verwendet. In früheren Versionen hat dieser Parameter angegeben, wie oft der Client MAPI-Daten aus öffentlichen Exchange-Ordnern abgerufen hat.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter war in lync 2013 veraltet.</p></td>
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


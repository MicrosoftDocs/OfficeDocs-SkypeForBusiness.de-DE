---
title: Neue und geänderte Einstellungen für Lync 2013
TOCTitle: Neue und geänderte Einstellungen für Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205204(v=OCS.15)
ms:contentKeyID: 49295222
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue und geänderte Einstellungen für Lync 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Thema werden Änderungen an Lync Server-Verwaltungsshell-Cmdlets behandelt, die im Rahmen der Clientverwaltung eingesetzt werden. In Lync Server 2013 gibt es mehrere neue Parameter, und Parameter für Features, die anderweitig konfiguriert werden können, werden nicht mehr unterstützt.

## Neue Parameter für die Clientverwaltung


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
<td><p>Bei Festlegung auf True wird die Softwareablaufverfolgung in Lync aktiviert, bei Festlegung auf False deaktiviert. Die Softwareablaufverfolgung umfasst das Aufzeichnen detaillierter Informationen zu allen Abläufen in einem Programm (einschließlich API-Aufrufen). Die Ablaufverfolgung ist überaus hilfreich für Entwickler und Mitarbeiter des Anwendungssupports. Diese Einstellung entspricht der Gruppenrichtlinieneinstellung Ablaufverfolgung für Communicator aktivieren von Communications Server 2007 R2. Es gibt die folgenden Einstellungen:</p>
<ul>
<li><p>Off = Die Ablaufverfolgung ist deaktiviert, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
<li><p>Light = Eine minimale Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
<li><p>On = Eine ausführliche Ablaufverfolgung wird ausgeführt, und der Benutzer kann diese Einstellung nicht ändern.</p></li>
</ul>
<p>Für TracingLevel ist standardmäßig ein Nullwert festgelegt. Dies bedeutet, dass eine minimale Ablaufverfolgung ausgeführt wird, aber der Benutzer kann diese minimale Ablaufverfolgung aktivieren bzw. deaktivieren.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Bei Festlegung auf &quot;True&quot; ($True) können Audio- und Videostreams von anderem Netzwerkdatenverkehr getrennt werden. Dadurch kann wiederum Audio und Video durch Clientgeräte lokal codiert und decodiert werden. Die Medienumleitung bedeutet in der Regel eine niedrigere Bandbreitennutzung, eine höhere Serverskalierbarkeit und eine verbesserte Benutzerfreundlichkeit im Vergleich zu ähnlichen Techniken wie Geräte-Remoting oder Codec-Komprimierung.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf True werden alle Lync-Besprechungen als &quot;große Besprechungen&quot; behandelt. Bei einer großen Besprechung gelten neben der Größe der Besprechungsliste, die standardmäßig übertragen wird, Einschränkungen bezüglich der Anzahl von an Teilnehmer gesendeten Benachrichtigungen.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf &quot;True&quot; ($True) können Benutzer PowerPoint-Folien, die in einer Konferenz verwendet werden, keine Anmerkungen hinzufügen. Benutzer haben jedoch (in Abhängigkeit vom Wert der AllowAnnotations-Eigenschaft) weiterhin Zugriff auf andere Whiteboardfeatures. Der Standardwert lautet False, womit PowerPoint-Anmerkungen zulässig sind.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Bei Festlegung auf True (Standardwert) werden alle geöffneten OneNote-Notizbücher im Zusammenhang mit der Konferenz automatisch mit Informationen wie z. B. den Konferenzteilnehmern und Details zu Inhalten, die während Konferenz weitergegeben werden, aktualisiert.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Dieser Parameter wird zusammen mit den anderen neuen CsMeetingConfiguration-Parametern zum Anpassen der Besprechungseinladungen verwendet, die vom Onlinebesprechungs-Add-In für Lync 2013 generiert werden.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt allen Einladungen, die vom Onlinebesprechungs-Add-In für Lync 2013 generiert werden, das Logo Ihrer Organisation hinzu. Sie geben die URL eines GIF- oder JPG-Bilds an.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt allen Einladungen, die vom Onlinebesprechungs-Add-In für Lync 2013 generiert werden, die Hilfe- oder Support-URL Ihrer Organisation hinzu.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt allen Einladungen, die vom Onlinebesprechungs-Add-In für Lync 2013 generiert werden, rechtliche oder Haftungsausschlusshinweise hinzu. Sie geben die URL für die Position dieser Hinweise an.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Fügt allen Einladungen, die vom Onlinebesprechungs-Add-In für Lync 2013 generiert werden, eine benutzerdefinierte Fußzeile hinzu. Sie geben die URL für die Position der benutzerdefinierten Fußzeile an.</p></td>
</tr>
<tr class="odd">
<td><p>IsPublicDisclosureAllowed</p></td>
<td><p>CsWebServiceConfiguration</p></td>
<td><p>Aktiviert die neue Version 2013 der Lync Web App. Die neue Version der Lync Web App ist standardmäßig nicht aktiviert und muss vom Administrator aktiviert werden.</p></td>
</tr>
</tbody>
</table>


## Nicht mehr unterstützte Parameter für die Clientverwaltung


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
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Der EnableSQMData-Parameter des Set-CSClientPolicy-Cmdlets wurde in Lync Server 2013 entfernt. Stattdessen können Sie mithilfe der gemeinsamen Gruppenrichtlinieneinstellung für SQM-Daten (Software Quality Management, Softwarequalitätsmanagement) die Benutzeroberfläche für das Programm zur Verbesserung der Benutzerfreundlichkeit auf der Seite Allgemeine Optionen des Lync-Clients bestimmen:</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Werte:</p>
<p>1 = Kontrollkästchen anzeigen und aktivieren (der Benutzer kann das Kontrollkästchen deaktivieren)</p>
<p>0 = Kontrollkästchen nicht anzeigen und deaktivieren (der Benutzer kann dies nicht überschreiben)</p>
<p>Null = Der Wert wird von Office Setup bestimmt, und das Kontrollkästchen wird für Benutzer angezeigt und kann von diesen aktiviert bzw. deaktiviert werden</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wurde entfernt. Stattdessen wird beim Bereitstellen von Lync Server 2013 und Veröffentlichen der Topologie standardmäßig ein einheitlicher Kontaktspeicher für alle Benutzer aktiviert. Dies bedeutet, dass alle Kontakte eines Benutzers in Exchange verwaltet werden und in Lync, Outlook und Outlook Web Access verfügbar sind. Mit dem Set-CsUserServicesPolicy-Cmdlet können Sie anpassen, für welche Benutzer ein einheitlicher Kontaktspeicher verfügbar sein soll. Benutzer aktivieren Sie global, nach Standort, nach Mandant oder nach Einzelpersonen oder Personengruppen. Ausführliche Informationen finden Sie unter <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Aktivieren von Benutzern für den einheitlichen Kontaktspeicher in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Dieser Parameter wird von Lync 2013 nicht verwendet. In früheren Versionen wurde mit diesem Parameter angegeben, wie oft der Client MAPI-Daten aus öffentlichen Exchange-Ordnern abgerufen hat.</p></td>
</tr>
</tbody>
</table>


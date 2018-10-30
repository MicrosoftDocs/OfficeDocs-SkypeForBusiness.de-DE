---
title: Prüfliste zur Bereitstellung für Webkonferenzen in Lync Server 2013
TOCTitle: Prüfliste zur Bereitstellung für Webkonferenzen in Lync Server 2013
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205104(v=OCS.15)
ms:contentKeyID: 49294847
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für Webkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wie für die Bereitstellung Ihrer anderen Lync Server 2013-Komponenten wird auch für Webkonferenzen der Topologie-Generator benötigt, um eine Topologie zu erstellen und zu veröffentlichen, die Konferenzen aufnimmt.

## Bereitstellungsreihenfolge

Sie können Konferenzen gleichzeitig mit Ihrer ersten Topologie bereitstellen oder nachdem Sie mindestens einen Front-End-Pool oder einen Standard Edition-Server bereitgestellt haben.

## Bereitstellungsverfahren für Konferenzen

Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung von Konferenzen in einer vorhandenen Topologie.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Rollen und Gruppenmitgliedschaften</th>
<th>Dokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installieren der erforderlichen Hardware und Software</strong></p></td>
<td><p>Konferenzen werden auf Front-End-Servern in einem Front-End-Pool und auf Standard Edition-Servern ausgeführt. Es bestehen keine zusätzlichen Hardware- oder Softwareanforderungen, die die Installationsanforderungen für diese Server übersteigen.</p>
<div>

> [!NOTE]
> Lync Server 2013 nutzt Office Web Apps und den Office Web Apps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen durchzuführen. Informationen zur Installation und Konfiguration von Office Web Apps-Server finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013</A>.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Serversoftware- und Infrastrukturunterstützung in Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a> in der Planungsdokumentation</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Anforderungen für die Archivierung in Lync Server 2013</a> in der Planungsdokumentation</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung von Konferenzen</strong></p></td>
<td><p>Führen Sie das Topologie-Generator aus, um Konferenzen zur Topologie hinzuzufügen und die Topologie dann zu veröffentlichen.</p></td>
<td><p>Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</p>
<p>Zum Veröffentlichen der Topologie: Konto, das Mitglied der Gruppen &quot;Domänen-Admins&quot; und &quot;RTCUniversalServerAdmins&quot; ist und über Vollzugriff (Lesen/Schreiben/Ändern) für die Dateifreigabe verfügt, auf der sich der Lync Server 2013-Dateispeicher befindet (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator</a> in der Bereitstellungsdokumentation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren von Konferenzrichtlinien und -unterstützung</strong></p></td>
<td><p>Verwenden Sie die Systemsteuerung für Lync Server 2013 oder die Lync Server-Verwaltungsshell, um Einstellungen für Konferenzen zu konfigurieren.</p></td>
<td><p>Gruppe &quot;RTCUniversalServerAdmins&quot; (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle &quot;CSAdministrator&quot;</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in Lync Server 2013</a> in der Betriebsdokumentation</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 besitzt nun die Einstellung **MaxUploadFileSizeMb**, mit der die Größe von Dateien, die während einer Besprechung hochgeladen werden können, beschränkt wird. Der Standardwert für diese Einstellung ist "500 MB". **MaxUploadFileSizeMb** kann mit dem **Set-CsConferencingConfiguration**-Cmdlet angepasst werden.

**MaxUploadFileSizeMb** nimmt keine Beschränkung der Einstellung für das Hochladen von Dateien der Lync Web App vor. Der Grenzwert für die Größe hochgeladener Dateien ist in der Lync Web App auf rund 30 MB festgelegt und wird über die IIS "web.config"-Datei gesteuert: /DataCollabWeb/Int\[Ext\]/Handler/web.config. Zur Konfiguration des Grenzwerts für die Größe hochgeladener Dateien für die Lync Web App müssen Sie in der Datei "web.config" `maxRequestLength` und `maxAllowedContentLength` wie im Folgenden dargestellt aktualisieren.

    <system.web>
        <!-- Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Die Datei "web.config" muss für jeden Front-End-Server aktualisiert werden.


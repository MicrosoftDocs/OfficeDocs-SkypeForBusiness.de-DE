---
title: Checkliste für die lync Server 2013-Bereitstellung für Webkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f845fd57846d7f9b58351d1cb77f3f1c0142ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Bereitstellungscheckliste für Webkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wie bei der Bereitstellung Ihrer anderen lync Server 2013-Komponenten erfordert die Bereitstellung von Webkonferenzen, dass Sie den Topologie-Generator verwenden, um eine Topologie zu erstellen und zu veröffentlichen, in der Konferenzen integriert sind.

<div>

## <a name="deployment-sequence"></a>Bereitstellungssequenz

Sie können Konferenzen gleichzeitig bereitstellen, indem Sie Ihre anfängliche Topologie bereitstellen oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Konferenz Bereitstellungsprozess

Die folgende Tabelle enthält eine Übersicht über die erforderlichen Schritte zum Bereitstellen von Konferenzen in einer vorhandenen Topologie.


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
<td><p>Konferenzen werden auf Front-End-Servern in einem Front-End-Pool und auf Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.</p>
<div>

> [!NOTE]  
> In lync Server 2013 werden Office Web Apps und der Office Web Apps-Server verwendet, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten. Informationen zum Installieren und Konfigurieren von Office Web Apps Server finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration in Office Web Apps Server und lync Server 2013</A>.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Dokumentation zur Unterstützung</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung für Server Software und-Infrastruktur in lync Server 2013</a> in der Dokumentation zur Unterstützung</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln der Systemanforderungen für lync Server 2013</a> in der Planungsdokumentation</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung von Konferenzen</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie Konferenzen hinzuzufügen, und veröffentlichen Sie dann die Topologie.</p></td>
<td><p>Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</p>
<p>So veröffentlichen Sie die Topologie: ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und das Vollzugriffsberechtigungen (Lesen/Schreiben/ändern) für die Dateifreigabe hat, die für den lync Server 2013-Dateispeicher verwendet werden soll (damit der Topologie-Generator Konfigurieren der erforderlichen DACLs</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und konfigurieren Sie eine Topologie im Topologie-Generator für lync Server 2013</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren von Konferenzrichtlinien und-Support</strong></p></td>
<td><p>Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell, um Konferenzeinstellungen zu konfigurieren.</p></td>
<td><p>RTCUniversalServerAdmins-Gruppe (nur Windows PowerShell) oder Zuweisen von Benutzern zur []-oder CSAdministrator-Rolle</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</a> in der Betriebsdokumentation.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 enthält jetzt die **MaxUploadFileSizeMb** -Einstellung, die die Größe von Dateien begrenzt, die während einer Besprechung hochgeladen werden können. Der Standardwert für diese Einstellung ist 500 MB. Sie können **MaxUploadFileSizeMb** mit dem Cmdlet " **Satz-CsConferencingConfiguration** " anpassen.

**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein. Der Grenzwert für die Upload-Dateigröße für lync Web App ist auf ungefähr 30 MB festgesetzt und wird von der IIS Web.\[config\]-Datei gesteuert:/DataCollabWeb/int ext/Handler/Web.config. Zum Konfigurieren des Upload-Grenzwerts für die Dateigröße für lync `maxRequestLength` Web `maxAllowedContentLength` APP aktualisieren Sie die Datei Web. config wie unten dargestellt.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
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

Sie müssen die Datei Web. config für jeden Front-End-Server aktualisieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>


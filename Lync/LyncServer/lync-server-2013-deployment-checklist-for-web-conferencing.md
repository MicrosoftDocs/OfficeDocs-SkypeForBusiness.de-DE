---
title: Prüfliste für lync Server 2013-Bereitstellung für Webkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c20bd593e11f032ba0a0ed852a50b6d417fa604
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531092"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Prüfliste für die Bereitstellung von Webkonferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-30_

Wie bei der Bereitstellung Ihrer anderen lync Server 2013 Komponenten erfordert die Bereitstellung von Webkonferenzen die Verwendung des Topologie-Generators zum Erstellen und Veröffentlichen einer Topologie, in der Konferenzen integriert werden.

<div>

## <a name="deployment-sequence"></a>Bereitstellungsreihenfolge

Sie können Konferenzen gleichzeitig bereitstellen, wenn Sie die anfängliche Topologie bereitstellen oder nachdem Sie mindestens eine Front-End-Pool oder Standard Edition-Server bereitgestellt haben.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Bereitstellungsverfahren für Konferenzen

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
<td><p>Konferenzen werden auf Front-End-Servern auf einem Front-End-Pool-und Standard Edition-Server ausgeführt. Es bestehen keine zusätzlichen Hardware- oder Softwareanforderungen, die die Installationsanforderungen für diese Server übersteigen.</p>
<div>

> [!NOTE]  
> Lync Server 2013 verwendet Office-Webanwendungen und den Office-webapps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten. Informationen zum Installieren und Konfigurieren des Office-webapps-Servers finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</A>.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software-und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a> in der Planungsdokumentation.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung von Konferenzen</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie Konferenzen hinzuzufügen, und veröffentlichen Sie dann die Topologie.</p></td>
<td><p>Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</p>
<p>So veröffentlichen Sie die Topologie, ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und die über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die Dateifreigabe verfügt, die für den lync Server 2013 Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren von Konferenzrichtlinien und -unterstützung</strong></p></td>
<td><p>Verwenden Sie die lync Server 2013-Systemsteuerung oder lync Server-Verwaltungsshell, um Konferenzeinstellungen zu konfigurieren.</p></td>
<td><p>RTCUniversalServerAdmins-Gruppe (nur Windows PowerShell) oder Zuweisen von Benutzern zur Rolle "[]" oder "CSAdministrator"</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</a> in der Betriebsdokumentation.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 enthält jetzt die **MaxUploadFileSizeMb** -Einstellung, die die Größe von Dateien beschränkt, die während einer Besprechung hochgeladen werden können. Der Standardwert für diese Einstellung ist "500 MB". **MaxUploadFileSizeMb** kann mit dem **Set-CsConferencingConfiguration**-Cmdlet angepasst werden.

**MaxUploadFileSizeMb** schränkt die Einstellung für den Dateiupload für lync Web App nicht ein. Der Grenzwert für die Dateigrößen Uploads für lync Web App wird auf ungefähr 30 MB festgelegt und wird von der IIS-web.config Datei gesteuert:/DataCollabWeb/int \[ Ext \] /Handler/web.config. Um den Upload-Grenzwert für die Dateigröße für lync Web App zu konfigurieren, aktualisieren Sie `maxRequestLength` und `maxAllowedContentLength` in der web.config Datei, wie unten dargestellt.

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

Sie müssen die web.config Datei für jeden Front-End-Server aktualisieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>


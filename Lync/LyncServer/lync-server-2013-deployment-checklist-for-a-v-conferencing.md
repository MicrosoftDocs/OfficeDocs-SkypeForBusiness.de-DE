---
title: Lync Server 2013-Bereitstellungscheckliste für A/V-Konferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Bereitstellungscheckliste für A/V-Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-30_

Wie bei der Bereitstellung Ihrer anderen lync Server 2013-Komponenten erfordert die Bereitstellung von a/V-Konferenzen, dass Sie den Topologie-Generator verwenden, um eine Topologie zu erstellen und zu veröffentlichen, in der Konferenzen integriert sind.

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
<td><p>Konferenzen werden auf Front-End-Servern eines Front-End-Pools und von Standard Edition-Servern ausgeführt. Abgesehen von den herkömmlichen Anforderungen zur Installation dieser Server bestehen keine zusätzlichen Hardware- oder Softwareanforderungen.</p>
<div>

> [!NOTE]  
> In lync Server 2013 werden Office Web Apps und der Office Web Apps-Server verwendet, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten. Details zum Installieren und Konfigurieren des Office Web Apps-Servers finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration in Office Web Apps Server und lync Server 2013</A>.


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
<p>So veröffentlichen Sie die Topologie: ein Konto, das ein Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und das Vollzugriffsberechtigungen (Lesen/Schreiben/ändern) für die Dateifreigabe hat, die für den lync Server 2013-Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann)</p></td>
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


</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über Konferenzen in Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Definieren der Anforderungen für Konferenzen in Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Bereitstellungsprozess für die Ankündigungs Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Bereitstellungsprozess für die Ankündigungs Anwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen der Ankündigungs Anwendung erforderlich sind. Sie müssen Enterprise-VoIP bereitstellen, bevor Sie Ankündigungen konfigurieren. Die von der Ankündigungs Anwendung benötigten Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### <a name="announcement-deployment-process"></a>Bereitstellungsprozess für Ansagen

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
<th>Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konfigurieren von Ansageeinstellungen</p></td>
<td><ul>
<li><p>Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS)</p></li>
<li><p>Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Erstellen einer Ankündigung in lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Überprüfen Ihrer Bereitstellung von Ansagen</p></td>
<td><p>Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Optional Überprüfen der Ankündigungs Bereitstellung in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


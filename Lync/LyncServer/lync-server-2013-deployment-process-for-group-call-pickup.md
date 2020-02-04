---
title: 'Lync Server 2013: Bereitstellungsprozess für die Gruppenanruf Abholung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Bereitstellungsprozess für die Gruppenanruf Abholung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen von Gruppenanruf Pickups erforderlich sind. Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie die Gruppenanruf Abholung konfigurieren. Die für die Gruppenanruf Abholung erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### <a name="group-call-pickup-deployment-process"></a>Bereitstellungsprozess für die Gruppenanrufannahme

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
<th>Erforderliche Gruppen und Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktivieren des SEFAUtil Resource Kit-Tools in der Topologie</p></td>
<td><ol>
<li><p>Erstellen Sie mithilfe des Cmdlets <strong>New-CsTrustedApplicationPool</strong> einen neuen vertrauenswürdigen Anwendungspool.</p></li>
<li><p>Legen Sie mithilfe des Cmdlets <strong>New-CsTrustedApplication</strong> das SEFAUtil-Tool als vertrauenswürdige Anwendung fest.</p></li>
<li><p>Führen Sie das Cmdlet <strong>Enable-CsTopology</strong> aus, um die Topologie zu aktivieren.</p></li>
<li><p>Installieren Sie die Resource Kit-Tools auf einem Front-End-Server, der sich im vertrauenswürdigen Anwendungspool befindet, der in Schritt 1 erstellt wurde.</p></li>
<li><p>Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>New-CSCallParkOrbit</strong> , um die Nummernbereiche für die Anruf Abholung in der Umlaufbahn Tabelle des Anrufs zu erstellen, und weisen Sie den Anruf-abholbereich den Typ GroupPickup zu.</p>
<div>

> [!NOTE]  
> Sie müssen die lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Pickup-Nummernbereichen in der Orbit-Tabelle des Anruf Parks verwenden. Gruppenanruf-Abhol Nummernbereiche sind in der lync Server-Systemsteuerung nicht verfügbar.


</div>
<div>

> [!NOTE]  
> Um eine nahtlose Integration in vorhandene Wählpläne zu ermöglichen, sind Nummernbereiche in der Regel als Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID (Direct Inward Dialing)-Nummern als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Konfigurieren von Gruppennummern für die Anruf Abholung in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Zuweisen einer Anruf-Abholnummer zu Benutzern und Aktivieren der Gruppenanruf Abholung für die Benutzer</p></td>
<td><p>Verwenden Sie den/enablegrouppickup-Parameter im SEFAUtil Resource Kit-Tool, um die Gruppenanruf Abholung zu aktivieren und Benutzern eine Anruf-Abholnummer zuzuweisen.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</a></p></td>
</tr>
<tr class="even">
<td><p>Informieren der Benutzer über die ihnen zugewiesene Nummer für die Anrufannahme und weitere relevante Nummern</p></td>
<td><p>Da Benutzer einen Anruf an einen Gruppenanruf-Pickup-Benutzer abrufen können, möchten Sie möglicherweise mehr als eine Gruppe überwachen.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Übermitteln von Gruppenanruf-Abholaufträgen an Benutzer in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Bereitstellung Ihrer Gruppenanruf Abholung</p></td>
<td><p>Testen Sie Anrufe und das Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Überprüfen der Bereitstellung für die Gruppenanruf Abholung in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Bereitstellungsprozess für die gruppenanrufannahme'
description: 'Lync Server 2013: Bereitstellungsprozess für die Gruppenanruf Abholung.'
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
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552491"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Bereitstellungsprozess für die Gruppenanruf Abholung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Dieser Abschnitt enthält eine Übersicht über die Schritte zur Bereitstellung der gruppenanrufannahme. Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie die gruppenanrufannahme konfigurieren. Die für die gruppenanrufannahme erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### <a name="group-call-pickup-deployment-process"></a>Bereitstellungsprozess für Gruppenanruf Pickups

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
<li><p>Verwenden Sie das Cmdlet <strong>New-CsTrustedApplicationPool</strong> , um einen neuen vertrauenswürdigen Anwendungspool zu erstellen.</p></li>
<li><p>Verwenden Sie das Cmdlet <strong>New-CsTrustedApplication</strong> , um das SEFAUtil-Tool als vertrauenswürdige Anwendung anzugeben.</p></li>
<li><p>Führen Sie das Cmdlet <strong>enable-CsTopology</strong> aus, um die Topologie zu aktivieren.</p></li>
<li><p>Installieren Sie die Resource Kit-Tools auf einem Front-End-Server im vertrauenswürdigen Anwendungspool, der in Schritt 1 erstellt wurde.</p></li>
<li><p>Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird, indem Sie es zur Anzeige der Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung führen.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Bereitstellen des SEFAUtil-Tools in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbit-Tabelle "Parken"</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>New-CSCallParkOrbit</strong> , um Nummernbereiche für die Anrufannahme in der Orbit-Tabelle für das Parken von Anrufen zu erstellen und den Anruf abholbereichen den Typ GroupPickup zuzuweisen.</p>
<div>

> [!NOTE]  
> Sie müssen lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Abhol Nummernbereichen in der Orbit-Tabelle für das Parken von Anrufen verwenden. Gruppenanruf-Pickup-Nummernbereiche sind in lync Server-Systemsteuerung nicht verfügbar.


</div>
<div>

> [!NOTE]  
> Für die nahtlose Integration in vorhandene Wählpläne werden Nummernbereiche in der Regel als Block virtueller Erweiterungen konfiguriert. Das Zuweisen von Durchwahlnummern (DID) als Bereichs Nummern in der Orbit-Tabelle für das Parken von Anrufen wird nicht unterstützt.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Konfigurieren von Nummern für die Anrufannahme Gruppe in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Zuweisen einer Anruf Abholnummer zu Benutzern und Aktivieren der gruppenanrufannahme für die Benutzer</p></td>
<td><p>Verwenden Sie den Parameter/enablegrouppickup im SEFAUtil Resource Kit-Tool, um die gruppenanrufannahme zu aktivieren und eine Anrufannahme Nummer für Benutzer zuzuweisen.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</a></p></td>
</tr>
<tr class="even">
<td><p>Benachrichtigen der Benutzer über die zugewiesene Anruf Abholnummer und andere Interessen</p></td>
<td><p>Da ein beliebiger Benutzer einen Anruf an einen Benutzer der gruppenanrufannahme abrufen kann, möchten Benutzer möglicherweise mehrere Gruppen überwachen.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Mitteilen von Gruppenanruf-Pickup-Zuweisungen an Benutzer in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Bereitstellung von Gruppenanruf Pickups</p></td>
<td><p>Testen Sie das platzieren und Abrufen von anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Überprüfen der Gruppenanruf-Pickup-Bereitstellung in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Bereitstellungsprozess für den Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Bereitstellungsprozess für den Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen der Anwendung für den Parken von Anrufen erforderlich sind. Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie den Anruf Park konfigurieren. Die für das Parken von Anrufen erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### <a name="call-park-deployment-process"></a>Bereitstellungsprozess für die Funktion zum Parken von Anrufen

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
<td><p>Konfigurieren der Orbitbereiche zum Parken von Anrufen in der Orbittabelle</p></td>
<td><p>Verwenden Sie die lync Server-Systemsteuerung oder das Cmdlet " <strong>New-CSCallParkOrbit</strong> ", um die Umlaufbahn Bereiche in der Orbit-Tabelle des Anruf Parks zu erstellen und Sie dem Anwendungsdienst zuzuordnen, der die Anwendung "Parken des Anrufs" hostet.</p>
<div>

> [!NOTE]  
> Für eine nahtlose Integration in einen vorhandenen Wählplan werden Orbitbereiche typischerweise als ein Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Erstellen oder Ändern eines orbitbereichs für einen Anruf Bereich in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Einstellungen für das Parken von Anrufen</p></td>
<td><p>Verwenden Sie das Cmdlet " <strong>Satz-CsCpsConfiguration</strong> ", um die Einstellungen für den Anruf Park zu konfigurieren. Wir empfehlen, die <strong>OnTimeoutURI</strong> -Option so zu konfigurieren, dass das Fall Back Ziel so konfiguriert wird, dass bei einem geparkten Anruf ein Timeout festgestellt wird. Sie können auch die folgenden Einstellungen konfigurieren:</p>
<ul>
<li><p>(Optional) <strong>EnableMusicOnHold</strong> zum Aktivieren oder Deaktivieren von Wartemusik.</p></li>
<li><p>(Optional) <strong>MaxCallPickupAttempts</strong> zum Festlegen der Anzahl von Rückrufversuchen, die für einen geparkten Anruf beim antwortenden Telefon erfolgen, bevor der Anruf an den Fallback-URI (Uniform Resource Locator) weitergeleitet wird.</p></li>
<li><p>(Optional) <strong>CallPickupTimeoutThreshold</strong> zum Festlegen der Zeitspanne, für die ein Anruf geparkt bleibt, bevor ein Rückruf beim antwortenden Telefon erfolgt.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Konfigurieren von Einstellungen für den Anruf Park in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Wartemusik anpassen (optional)</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige Wartemusik verwenden möchten.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Anpassen der Musik zum Parken von Anrufen im Wartebereich in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren der VoIP-Richtlinie zum Aktivieren des Anruf Parks für Benutzer</p></td>
<td><p>Verwenden Sie die lync Server-Systemsteuerung oder das Cmdlet " <strong>festlegen-CSVoicePolicy</strong> " mit der Option " <strong>EnableCallPark</strong> ", um den Anruf Park für Benutzer in der VoIP-Richtlinie zu aktivieren.</p>
<div>

> [!NOTE]  
> Standardmäßig ist der Parken von Anrufen für alle Benutzer deaktiviert.


</div>
<div>

> [!NOTE]  
> Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft „EnableCallPark“ nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Aktivieren des Anruf Parks für Benutzer in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Normalisierungsregeln für das Parken von Anrufen</p></td>
<td><p>Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Überprüfen von Normalisierungsregeln für den Parken von Anrufen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Überprüfen der Bereitstellung des Anruf Parks</p></td>
<td><p>Testen Sie das Parken und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


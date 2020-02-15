---
title: 'Lync Server 2013: Bereitstellungsprozess für das Parken von Anrufen'
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
ms.openlocfilehash: 29e896aa89fe6fadecab3d17689d92671ffe6966
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Bereitstellungsprozess für das Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-25_

Dieser Abschnitt enthält eine Übersicht über die Schritte zur Bereitstellung des Anwendung zum Parken von anrufen. Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie das Parken von anrufen konfigurieren. Die für das Parken von Anrufen erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

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
<td><p>Verwenden Sie lync Server-Systemsteuerung oder das Cmdlet <strong>New-CSCallParkOrbit</strong> , um die Umlaufbahn Bereiche in der Orbit-Tabelle für das Parken von Anrufen zu erstellen und Sie dem Anwendungsdienst zuzuordnen, der die Anwendung zum Parken von Anrufen hostet.</p>
<div>

> [!NOTE]  
> Für eine nahtlose Integration in vorhandene Wähleinstellungen werden Orbitbereiche typischerweise als ein Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Erstellen oder Ändern eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Einstellungen für das Parken von Anrufen</p></td>
<td><p>Verwenden Sie das Cmdlet " <strong>CsCpsConfiguration</strong> ", um die Einstellungen für das Parken von Anrufen zu konfigurieren. Es wird empfohlen, die <strong>OnTimeoutURI</strong> -Option so zu konfigurieren, dass das Fallback-Ziel beim Timeout eines geparkten Anrufs verwendet wird. Sie können auch die folgenden Einstellungen konfigurieren:</p>
<ul>
<li><p>(Optional) <strong>EnableMusicOnHold</strong> zum Aktivieren oder Deaktivieren von Wartemusik.</p></li>
<li><p>(Optional) <strong>MaxCallPickupAttempts</strong> zum Festlegen der Anzahl von Rückrufversuchen, die für einen geparkten Anruf beim antwortenden Telefon erfolgen, bevor der Anruf an den Fallback-URI (Uniform Resource Locator) weitergeleitet wird.</p></li>
<li><p>(Optional) <strong>CallPickupTimeoutThreshold</strong> zum Festlegen der Zeitspanne, für die ein Anruf geparkt bleibt, bevor ein Rückruf beim antwortenden Telefon erfolgt.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Konfigurieren von Einstellungen für das Parken von Anrufen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Wartemusik anpassen (optional)</p></td>
<td><p>Verwenden Sie das <strong>Set-CsCallParkServiceMusicOnHoldFile</strong>-Cmdlet zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige Wartemusik verwenden möchten.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren der VoIP-Richtlinie zum Aktivieren des Anruf Parks für Benutzer</p></td>
<td><p>Verwenden Sie lync Server-Systemsteuerung oder das Cmdlet " <strong>CSVoicePolicy</strong> " mit der Option " <strong>EnableCallPark</strong> ", um den Anruf Park für Benutzer in der VoIP-Richtlinie zu aktivieren.</p>
<div>

> [!NOTE]  
> Standardmäßig ist das Parken von Anrufen für alle Benutzer deaktiviert.


</div>
<div>

> [!NOTE]  
> Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft "EnableCallPark" nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Parken von Anrufen für Benutzer in lync Server 2013 aktivieren</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Normalisierungsregeln für das Parken von Anrufen</p></td>
<td><p>Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Überprüfen der Bereitstellung des Anruf Parks</p></td>
<td><p>Testen Sie das Parken und Abrufen von anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert.</p></td>
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


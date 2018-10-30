---
title: 'Lync Server 2013: Bereitstellungsprozess für die Funktion zum Parken von Anrufen'
TOCTitle: Bereitstellungsprozess für die Funktion zum Parken von Anrufen
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398283(v=OCS.15)
ms:contentKeyID: 49293390
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für die Funktion zum Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen der Anwendung zum Parken von Anrufen. Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie Parken von Anrufen konfigurieren. Die für das Parken von Anrufen erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### Bereitstellungsprozess für die Funktion zum Parken von Anrufen

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
<td><p>Verwenden Sie die Lync Server-Systemsteuerung oder das Cmdlet <strong>New-CSCallParkOrbit</strong>, um die Orbitbereiche in der Orbittabelle für das Parken von Anrufen zu erstellen und die Bereiche dem Anwendungsdienst zuzuordnen, der die Anwendung zum Parken von Anrufen hostet.</p>
<div>

> [!NOTE]
> Für eine nahtlose Integration in vorhandene Wähleinstellungen werden Orbitbereiche typischerweise als ein Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Erstellen oder Ändern eines Orbitbereichs für das Parken von Anrufen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Einstellungen für die Parken von Anrufen</p></td>
<td><p>Verwenden Sie das <strong>Set-CsCpsConfiguration</strong>-Cmdlet, um Einstellungen für das Parken von Anrufen zu konfigurieren. Es wird empfohlen, mindestens die Option <strong>OnTimeoutURI</strong> zu konfigurieren, um ein Fallbackziel anzugeben, das bei Auftreten einer Zeitüberschreitung für geparkte Anrufe verwendet wird. Sie können außerdem die folgenden Einstellungen konfigurieren:</p>
<ul>
<li><p>(Optional) <strong>EnableMusicOnHold</strong> zum Aktivieren oder Deaktivieren von Wartemusik.</p></li>
<li><p>(Optional) <strong>MaxCallPickupAttempts</strong> zum Festlegen der Anzahl von Rückrufversuchen, die für einen geparkten Anruf beim antwortenden Telefon erfolgen, bevor der Anruf an den Fallback-URI (Uniform Resource Locator) weitergeleitet wird.</p></li>
<li><p>(Optional) <strong>CallPickupTimeoutThreshold</strong> zum Festlegen der Zeitspanne, für die ein Anruf geparkt bleibt, bevor ein Rückruf beim antwortenden Telefon erfolgt.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Konfigurieren von Einstellungen für das Parken von Anrufen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Wartemusik anpassen (optional)</p></td>
<td><p>Verwenden Sie das <strong>Set-CsCallParkServiceMusicOnHoldFile</strong>-Cmdlet zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige Wartemusik verwenden möchten.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Anpassen der Wartemusik für das Parken von Anrufen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren einer VoIP-Richtlinie zum Aktivieren der Parken von Anrufen für Benutzer</p></td>
<td><p>Verwenden Sie die Lync Server-Systemsteuerung oder das <strong>Set-CSVoicePolicy</strong> -Cmdlet mit der Option <strong>EnableCallPark</strong> , um das Parken von Anrufen für Benutzer in der VoIP-Richtlinie zu aktivieren.</p>
<div>

> [!NOTE]
> In der Standardeinstellung ist die Parken von Anrufen für alle Benutzer deaktiviert.


</div>
<div>

> [!NOTE]
> Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft "EnableCallPark" nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Aktivieren der Funktion zum Parken von Anrufen für Benutzer in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen der Normalisierungsregeln für die Parken von Anrufen</p></td>
<td><p>Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Überprüfen der Bereitstellung der Parken von Anrufen</p></td>
<td><p>Testen Sie das Parken und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Überprüfen der Bereitstellung der Funktion zum Parken von Anrufen in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


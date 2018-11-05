---
title: Bereitstellungsprozess für die Gruppenanrufannahme
TOCTitle: Bereitstellungsprozess für die Gruppenanrufannahme
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945615(v=OCS.15)
ms:contentKeyID: 52056281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für die Gruppenanrufannahme

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieser Abschnitt bietet eine Übersicht über die Schritte zur Bereitstellung der Gruppenanrufannahme. Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie die Gruppenanrufannahme konfigurieren können. Die für die Gruppenanrufannahme erforderlichen Komponenten werden mit der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### Bereitstellungsprozess für die Gruppenanrufannahme

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
<td><p>Aktivieren des SEFAUtil-Resource Kit-Tools in der Topologie</p></td>
<td><ol>
<li><p>Erstellen Sie mithilfe des Cmdlets <strong>New-CsTrustedApplicationPool</strong> einen neuen vertrauenswürdigen Anwendungspool.</p></li>
<li><p>Legen Sie mithilfe des Cmdlets <strong>New-CsTrustedApplication</strong> das SEFAUtil-Tool als vertrauenswürdige Anwendung fest.</p></li>
<li><p>Führen Sie das Cmdlet <strong>Enable-CsTopology</strong> aus, um die Topologie zu aktivieren.</p></li>
<li><p>Installieren Sie die Tools im Resource Kit auf einem Front-End-Server, der sich in dem in Schritt 1 erstellten vertrauenswürdigen Anwendungspool befindet.</p></li>
<li><p>Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Bereitstellen des SEFAUtil-Tools</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>New-CSCallParkOrbit</strong>, um Nummernbereiche für die Anrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen und den Nummernbereiche für die Anrufannahme den Typ &quot;GroupPickup&quot; zuzuweisen.</p>
<div>

> [!NOTE]
> Sie müssen die Lync Server-Verwaltungsshell zum Erstellen, Ändern, Entfernen und Anzeigen von Nummern für die Gruppenanrufannahme in der Orbittabelle für das Parken von Anrufen verwenden. Nummern für die Gruppenanrufannahme sind in Lync Server-Systemsteuerung nicht verfügbar.


</div>
<div>

> [!NOTE]
> Um eine nahtlose Integration in vorhandene Wählpläne zu ermöglichen, sind Nummernbereiche in der Regel als Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID (Direct Inward Dialing)-Nummern als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Konfigurieren von Nummern für die Gruppenanrufannahme</a></p></td>
</tr>
<tr class="odd">
<td><p>Zuweisen einer Nummer Anrufannahme an Benutzer und Aktivieren der Gruppenanrufannahme für die Benutzer</p></td>
<td><p>Verwenden Sie den Parameter &quot;/enablegrouppickup&quot; im SEFAUtil-Resource Kit-Tool zum Aktivieren der Gruppenanrufannahme und zum Zuweisen einer Nummer für die Anrufannahme an Benutzer.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer</a></p></td>
</tr>
<tr class="even">
<td><p>Informieren der Benutzer über die ihnen zugewiesene Nummer für die Anrufannahme und weitere relevante Nummern</p></td>
<td><p>Da jeder Benutzer einen Anruf an einen Benutzer der Gruppenanrufannahme abrufen kann, sollten Benutzer mehr als eine Gruppe überwachen.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Mitteilen der Zuweisung der Gruppenanrufannahme an Benutzer</a></p></td>
</tr>
<tr class="odd">
<td><p>Überprüfen Ihrer Bereitstellung der Gruppenanrufannahme</p></td>
<td><p>Testen Sie Anrufe und das Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Überprüfen der Bereitstellung der Gruppenanrufannahme</a></p></td>
</tr>
</tbody>
</table>


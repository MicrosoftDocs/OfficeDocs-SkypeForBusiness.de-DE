---
title: 'Lync Server 2013: Testen der Telefonnummer für eine VoIP-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a234419dc6f06ae9bdc8d7c198873bdc3c706701
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Testen der Telefonnummer für eine VoIP-Richtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Monatlich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsVoicePolicy verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Die Fähigkeit von Enterprise-VoIP-Benutzern, ausgehende Anrufe über das Festnetz-Scharnier (Public Switched Telephone Network, PSTN) zu tätigen, besteht zu einem großen Teil aus drei Punkten:

  - Die dem Benutzer zugewiesene VoIP-Richtlinie.

  - Die VoIP-Routen, die zum Weiterleiten von Anrufen von lync Server an das PSTN-Netzwerk verwendet werden.

  - Die PSTN-Verwendung, eine lync Server Eigenschaft, die eine VoIP-Richtlinie mit einer VoIP-Route verbindet.

Die PSTN-Verwendung ist besonders wichtig: Sie ist die Eigenschaft, die eine VoIP-Richtlinie mit einer VoIP-Route verbindet. (Eine VoIP-Richtlinie und eine VoIP-Route werden als verbunden bezeichnet, wenn Sie mindestens eine PSTN-Nutzung gemeinsam haben.) VoIP-Richtlinien können ohne Angabe einer PSTN-Verwendung konfiguriert werden. In diesem Fall können Benutzer, denen diese Richtlinie zugewiesen wurde, keine ausgehenden Anrufe über das PSTN-Netzwerk tätigen. Ebenso können VoIP-Routen, die nicht über mindestens eine festgelegte PSTN-Verwendung verfügen, keine Anrufe an das PSTN-Netzwerk weiterleiten.

Das Cmdlet Test-CsVoicePolicy überprüft, ob eine bestimmte VoIP-Richtlinie über eine PSTN-Verwendung verfügt und dass die Nutzung von mindestens einer VoIP-Route gemeinsam genutzt wird. Wenn die Überprüfung durch Test-CsVoicePolicy erfolgreich ausgeführt wird, meldet das Cmdlet den Namen der ersten gültigen VoIP-Route, die gefunden wird, sowie den Namen der PSTN-Verwendung, die die Richtlinie mit der Route verbindet.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Zum Ausführen des Test-CsVoicePolicy-Cmdlets müssen Sie zunächst das Cmdlet Get-CsVoicePolicy verwenden, um eine Instanz der zu testenden VoIP-Richtlinie abzurufen. Diese Instanz muss anschließend an Test-CsVoicePolicy weitergeleitet werden. Beispiel:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Beachten Sie, dass dieser Befehl, der nicht get-CsVoicePolicy zum Abrufen einer VoIP-Richtlinieninstanz verwendet, fehlschlägt:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Wenn Sie alle VoIP-Richtlinien anhand einer bestimmten Telefonnummer überprüfen möchten, verwenden Sie einen Befehl wie den folgenden:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Beachten Sie, dass das TargetNumber mithilfe des E. 164-Formats angegeben werden muss. Test-CsVoicePolicy versucht nicht, Telefonnummern in das E. 164-Format zu normalisieren oder zu übersetzen.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die VoIP-Richtlinie sowohl eine übereinstimmende VoIP-Route als auch eine entsprechende PSTN-Verwendung finden kann, werden sowohl die Route als auch die Nutzung auf dem Bildschirm angezeigt:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Wenn entweder eine entsprechende VoIP-Route oder eine entsprechende PSTN-Verwendung nicht gefunden werden kann, werden leere Eigenschaftswerte auf dem Bildschirm angezeigt:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn mit Test-CsVoicePolicy keine Übereinstimmung zurückgegeben wird, kann dies bedeuten, dass die VoIP-Richtlinie nicht eine PSTN-Verwendung mit einer VoIP-Route teilt. Verwenden Sie zum Überprüfen eines Cmdlets wie das folgende ein Cmdlet, um zu überprüfen, ob PSTN-Verwendungen der VoIP-Richtlinie zugewiesen sind:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Führen Sie als nächstes den folgenden Befehl aus, um festzustellen, welche PSTN-Verwendungen den einzelnen VoIP-Routen zugewiesen werden:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Wenn Übereinstimmungen angezeigt werden (wenn eine oder mehrere VoIP-Routen angezeigt werden, die mindestens eine PSTN-Verwendung mit Ihrer VoIP-Richtlinie aufweisen), sollten Sie das Cmdlet Test-CsVoiceRoute ausführen, um sicherzustellen, dass die VoIP-Route die angegebene Telefonnummer wählen kann.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen einer Telefonnummer mit einer VoIP-Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a1e24a07a0f6e1e985c9fc42f7468838074d3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Testen einer Telefonnummer für eine VoIP-Richtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-20_


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
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoicePolicy-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Die Möglichkeit von Enterprise-VoIP-Benutzern, ausgehende Telefonanrufe über das öffentlich geschaltete Telefonnetz (PSTN) zu tätigen, hängt zu einem Großteil von drei Dingen ab:

  - Die dem Benutzer zugewiesene VoIP-Richtlinie.

  - Die VoIP-Routen, die zum Weiterleiten von Anrufen von lync Server an das PSTN-Netzwerk verwendet werden.

  - Die PSTN-Nutzung, eine lync Server-Eigenschaft, die eine VoIP-Richtlinie mit einer VoIP-Route verbindet.

Die PSTN-Nutzung ist besonders wichtig: Es handelt sich um die Eigenschaft, die eine VoIP-Richtlinie mit einer VoIP-Route verbindet. (Eine VoIP-Richtlinie und eine VoIP-Route werden als verbunden bezeichnet, wenn Sie mindestens eine PSTN-Nutzung gemeinsam haben.) VoIP-Richtlinien können ohne Angabe einer PSTN-Nutzung konfiguriert werden. In diesem Fall können Benutzer, denen diese Richtlinie zugewiesen wurde, keine ausgehenden Anrufe über das PSTN-Netzwerk führen. Ebenso können VoIP-Routen, die nicht über mindestens eine festgelegte PSTN-Nutzung verfügen, keine Anrufe an das PSTN-Netzwerk weiterleiten.

Das Cmdlet Test-CsVoicePolicy überprüft, ob eine bestimmte VoIP-Richtlinie über eine PSTN-Nutzung verfügt und dass die Nutzung von mindestens einer VoIP-Route freigegeben wird. Wenn die Überprüfung durch Test-CsVoicePolicy erfolgreich ausgeführt wird, meldet das Cmdlet den Namen der ersten gültigen VoIP-Route, die gefunden wird, und auch den Namen der PSTN-Nutzung, die die Richtlinie mit der Route verbindet.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Damit Sie das Cmdlet Test-CsVoicePolicy ausführen können, müssen Sie zuerst das Cmdlet Get-CsVoicePolicy verwenden, um eine Instanz der VoIP-Richtlinie abzurufen, die getestet werden soll. Diese Instanz muss dann zu Test-CsVoicePolicy umgeleitet werden. Beispiel:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Beachten Sie, dass dieser Befehl, der keine Get-CsVoicePolicy zum Abrufen einer VoIP-Richtlinieninstanz verwendet, fehlerhaft ist:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Wenn Sie alle VoIP-Richtlinien für eine bestimmte Telefonnummer überprüfen möchten, verwenden Sie einen ähnlichen Befehl wie den folgenden:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Beachten Sie, dass der TargetNumber mit dem E. 164-Format angegeben werden muss. Test-CsVoicePolicy versucht nicht, Telefonnummern in das E. 164-Format zu normalisieren oder zu übersetzen.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die VoIP-Richtlinie sowohl eine übereinstimmende VoIP-Route als auch eine übereinstimmende PSTN-Nutzung finden kann, werden sowohl die Route als auch die Verwendung auf dem Bildschirm angezeigt:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Wenn entweder eine geeignete VoIP-Route oder eine entsprechende PSTN-Nutzung gefunden werden kann, werden leere Eigenschaftswerte auf dem Bildschirm angezeigt:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsVoicePolicy keine Übereinstimmung zurückgibt, kann dies bedeuten, dass die VoIP-Richtlinie keine PSTN-Nutzung mit einer VoIP-Route teilt. Um dies zu überprüfen, verwenden Sie ein Cmdlet ähnlich dem folgenden, um zu überprüfen, ob PSTN-Nutzungen der VoIP-Richtlinie zugewiesen sind:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Führen Sie als nächstes diesen Befehl aus, um festzustellen, welche PSTN-Nutzungen für Ihre VoIP-Routen zuzuweisen sind:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Wenn Sie Übereinstimmungen sehen (das heißt, wenn Sie eine oder mehrere VoIP-Routen sehen, die mindestens eine PSTN-Nutzung mit Ihrer VoIP-Richtlinie aufweisen), sollten Sie das Cmdlet Test-CsVoiceRoute ausführen, um zu überprüfen, ob die VoIP-Route die angegebene Telefonnummer wählen kann.

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


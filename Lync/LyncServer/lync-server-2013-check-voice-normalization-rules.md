---
title: 'Lync Server 2013: Überprüfen von Regeln für die sprach Normalisierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Überprüfen von VoIP-Normalisierungsregeln in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceNormalizationRule-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Regeln für die sprach Normalisierung werden verwendet, um eine Telefonnummer zu konvertieren, die von einem Benutzer gewählt wurde (beispielsweise 2065551219), in das E. 164-Format, das von lync Server (+ 12065551219) verwendet wird. Wenn Benutzer beispielsweise die Möglichkeit haben, eine Telefonnummer zu wählen, ohne die Landesvorwahl oder die Ortsvorwahl (z. b. 5551219) einzuschließen, müssen Sie über eine sprach Normalisierungsregel verfügen, mit der diese Zahl in das e. 164-Format konvertiert werden kann: + 12065551219. Ohne diese Regel ist der Benutzer nicht in der Lage, 555-1219 anzurufen.

Das Cmdlet Test-CsVoiceNormalizationRule überprüft, ob eine bestimmte Telefonnummer durch eine angegebene VoIP-Normalisierungsregel erfolgreich konvertiert werden kann. Mit diesem Befehl wird beispielsweise überprüft, ob die globale Normalisierungsregel NoAreaCode die Wählzeichenfolge 5551219 normalisieren und konvertieren kann.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Damit Sie das Cmdlet Test-CsVoiceNormalizationRule ausführen können, müssen Sie zuerst das Cmdlet Get-CsVoiceNormalizationRule verwenden, um eine Instanz der getesteten Regel abzurufen, und diese Instanz dann an Test-CsVoiceNormalizationRule weiterleiten. Eine ähnliche Syntax wie diese funktioniert nicht:

Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "Global/Prefix all"

Verwenden Sie stattdessen eine Syntax wie die folgende, die sowohl das Cmdlet "Get-CsVoiceNormalizationRule" als auch die Test-CsVoiceNormalizationRule-Cmdlets kombiniert:

Get-CsVoiceNormalizationRule-Identity "Global/Präfix alle" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . Sie können auch diesen Ansatz verwenden, um eine Instanz einer Regel abzurufen und diese Regel dann mit einer angegebenen Telefonnummer zu testen:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Geben Sie den Wert für den DialedNumber-Parameter genau so ein, wie Sie erwarten, dass die Nummer gewählt wird. Wenn beispielsweise die angegebene sprach Normalisierungsregel die Landesvorwahl (die Initiale 1 im Wert 12065551219) automatisch hinzufügen soll, sollten Sie die Landesvorwahl nicht angeben:

`-DialedNumber "2065551219"`

Wenn die Regel ordnungsgemäß konfiguriert ist, wird beim Übersetzen der Nummer automatisch die Landesvorwahl in das von lync Server verwendete E. 164-Format hinzugefügt.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die angegebene sprach Normalisierungsregel die angegebene Nummer übersetzen kann, wird die übersetzte Nummer auf dem Bildschirm angezeigt:

TranslatedNumber

\----------------

\+12065551219

Wenn der Test fehlschlägt, wird eine leere übersetzte Zahl zurückgegeben:

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn der Test-CsVoiceNormalizationRule eine übersetzte Zahl zurückgibt, bedeutet dies, dass die angegebene sprach Normalisierungsregel die angegebene Telefonnummer nicht in das E. 164-Format übersetzen konnte, das von lync Server verwendet wird. Um dies zu überprüfen, stellen Sie zuerst sicher, dass Sie die Telefonnummer richtig eingegeben haben. Sie würden beispielsweise davon ausgehen, dass die Regel für die sprach Normalisierung Probleme hat, eine Zahl zu übersetzen, die der folgenden ähnelt:

`-DialedNumber "1"`

Wenn die Nummer richtig eingegeben wurde, sollte der nächste Schritt darin liegen, zu überprüfen, ob die angegebene Normalisierungsregel für die Behandlung dieser Telefonnummer vorgesehen ist. Beispielsweise kann eine Normalisierungsregel zur Behandlung des Formats 12065551219 entwickelt werden, aber eine zweite Regel kann für die Behandlung der Zahl 2065551219 entworfen werden. (Das ist die gleiche Telefonnummer, abzüglich der Landesvorwahl 1 am Anfang.) Wenn Sie detaillierte Informationen zu einer Regel für die sprach Normalisierung zurückgeben möchten, führen Sie einen Befehl wie den folgenden aus:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Führen Sie stattdessen diesen Befehl aus, um detaillierte Informationen zu allen Regeln für die sprach Normalisierung zurückzugeben:

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


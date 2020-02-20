---
title: 'Lync Server 2013: Überprüfen der VoIP-Normalisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cf48022fc62f959bbddcd3cb6978e2e668a9334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Überprüfen der VoIP-Normalisierungsregeln in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsVoiceNormalizationRule verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Regeln für die VoIP-Normalisierung werden verwendet, um eine von einem Benutzer gewählte Telefonnummer (beispielsweise 2065551219) in das E. 164-Format zu konvertieren, das von lync Server (+ 12065551219) verwendet wird. Wenn Benutzer beispielsweise die Gewohnheit haben, eine Telefonnummer zu wählen, ohne die Landesvorwahl oder die Vorwahl (z.b. 5551219) einzuschließen, benötigen Sie eine sprach Normalisierungsregel, mit der diese Nummer in das e. 164-Format konvertiert werden kann: + 12065551219. Ohne eine solche Regel kann der Benutzer 555-1219 nicht aufrufen.

Das Cmdlet Test-CsVoiceNormalizationRule überprüft, ob eine angegebene sprach Normalisierungsregel eine angegebene Telefonnummer erfolgreich konvertieren kann. Beispielsweise überprüft dieser Befehl, ob die globale Normalisierungsregel NoAreaCode die Wählzeichenfolge 5551219 normalisieren und konvertieren kann.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Zum Ausführen des Test-CsVoiceNormalizationRule-Cmdlets müssen Sie zunächst das Cmdlet Get-CsVoiceNormalizationRule verwenden, um eine Instanz der getesteten Regel abzurufen, und diese Instanz dann an Test-CsVoiceNormalizationRule weiterleiten. Syntax ähnlich wie dies funktioniert nicht:

Test-CsVoiceNormalizationRule-"DialedNumber" "12065551219" – normalizationrule "" Global/Präfix all "

Verwenden Sie stattdessen eine Syntax wie die folgende, die sowohl die Get-CsVoiceNormalizationRule-als auch die Test-CsVoiceNormalizationRule-Cmdlets kombiniert:

Get-CsVoiceNormalizationRule-Identity "Global/Präfix all" | Test-CsVoiceNormalizationRule-"DialedNumber" "12065551219"

<div>


> [!NOTE]  
> . Sie können auch diesen Ansatz verwenden, um eine Instanz einer Regel abzurufen und diese Regel dann anhand einer bestimmten Telefonnummer zu testen:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Geben Sie den Wert für den Parameter "DialedNumber" genau so ein, wie Sie davon ausgehen, dass die Nummer gewählt wird. Wenn beispielsweise die angegebene sprach Normalisierungsregel automatisch die Landesvorwahl (die erste 1 im Wert 12065551219) hinzufügen soll, sollten Sie die Landesvorwahl verlassen:

`-DialedNumber "2065551219"`

Wenn die Regel ordnungsgemäß konfiguriert ist, wird automatisch der Landescode hinzugefügt, wenn die Nummer in das von lync Server verwendete E. 164-Format übersetzt wird.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die angegebene sprach Normalisierungsregel die angegebene Nummer übersetzen kann, wird die übersetzte Nummer auf dem Bildschirm angezeigt:

TranslatedNumber

\----------------

\+12065551219

Wenn der Test fehlschlägt, wird eine leere übersetzte Nummer zurückgegeben:

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn der Test-CsVoiceNormalizationRule eine übersetzte Zahl zurückgibt, bedeutet dies, dass die angegebene sprach Normalisierungsregel die bereitgestellte Telefonnummer nicht in das von lync Server verwendete E. 164-Format übersetzen konnte. Um dies zu überprüfen, müssen Sie zunächst sicherstellen, dass Sie die Telefonnummer richtig eingegeben haben. Beispielsweise würden Sie davon ausgehen, dass Ihre VoIP-Normalisierungsregel Probleme mit der Übersetzung einer Zahl ähnlich der folgenden hat:

`-DialedNumber "1"`

Unter der Voraussetzung, dass die Nummer richtig eingegeben wurde, sollten Sie im nächsten Schritt überprüfen, ob die angegebene Normalisierungsregel für die Verarbeitung dieser Telefonnummer ausgelegt ist. Beispielsweise kann eine Normalisierungsregel entworfen werden, um das Format 12065551219 zu verarbeiten, aber eine zweite Regel kann für die Verarbeitung der Zahl 2065551219 ausgelegt sein. (Das ist die gleiche Telefonnummer, abzüglich der Landesvorwahl 1 ganz am Anfang.) Wenn Sie detaillierte Informationen zu einer sprach Normalisierungsregel zurückgeben möchten, führen Sie einen Befehl wie den folgenden aus:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Wenn Sie detaillierte Informationen zu allen VoIP-Normalisierungsregeln zurückgeben möchten, führen Sie stattdessen den folgenden Befehl aus:

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


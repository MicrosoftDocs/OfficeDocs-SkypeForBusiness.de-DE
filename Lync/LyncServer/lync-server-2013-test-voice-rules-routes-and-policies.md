---
title: 'Lync Server 2013: Testen von VoIP-Regeln,-Routen und-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Testen von VoIP-Regeln,-Routen und-Richtlinien in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceUser-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Wenn ein Benutzer einen Telefonanruf tätigt, hängt die Route, die der Anruf zum Erreichen seines Ziels benötigt, von den Richtlinien und den Wählplänen ab, die diesem Benutzer zugewiesen sind. Angesichts der SIP-Adresse und einer Telefonnummer eines Benutzers überprüft das Cmdlet Test-CsVoiceUser, ob der betreffende Benutzer einen Anruf an diese Nummer durchführen kann. Wenn der Test erfolgreich ist, gibt Test-CsVoiceUser Folgendes zurück:

  - Die im E. 164-Format übersetzte Zahl (basierend auf dem Wählplan des Benutzers)

  - Die Normalisierungsregel, die die Übersetzung bereitgestellt hat

  - Die verwendete VoIP-Route (basierend auf der Routen Priorität);

  - Die Telefonverwendung, die die VoIP-Richtlinie des Benutzers mit der VoIP-Route verknüpft hat.

Mit Test-CsVoiceUser können Sie feststellen, ob eine bestimmte Telefonnummer wie erwartet weitergeleitet und übersetzt wird, und Sie können bei der Behandlung von Problemen mit dem Anruf helfen, die von einzelnen Benutzern erlebt werden.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Wenn Sie das Cmdlet Test-CsVoiceUser ausführen, müssen Sie zwei Informationen angeben: die Nummer, die gewählt wird (DialedNumber), und die Identität des zu testenden Benutzerkontos. Dieser Befehl testet beispielsweise die Fähigkeit des Benutzers, der die SIP-Adresse SIP:kenmyer@litwareinc.com, um einen Anruf an die Telefonnummer + 1206555-1219 zu führen:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

Die Telefonnummer sollte so formatiert sein, wie Sie Sie erwarten. Wenn Benutzer beispielsweise in der Regel nicht die 1 wählen, bevor Sie einen Ferngespräch führen, sollten Sie folgendes Format verwenden:

`-DialedNumber "2065551219"`

In diesem Fall schlägt der Test natürlich fehl, wenn keine Normalisierungsregel vorhanden ist, mit der die Zahl 2065551219 ordnungsgemäß in das von lync Server verwendete E. 164-Telefon Format übersetzt werden kann. Weitere Informationen finden Sie im Hilfethema Cmdlet New-CsVoiceNormalizationRule.

Wenn Sie denselben Test für alle Benutzerkonten ausführen möchten, können Sie einen Befehl wie den folgenden verwenden:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der Test erfolgreich abgeschlossen wurde (das heißt, wenn der Benutzer einen Anruf mit der angegebenen Nummer führen kann), werden in der Ausgabe Informationen wie die übersetzte Telefonnummer und die übereinstimmende Normalisierungsregel sowie die VoIP-Route angezeigt:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219...    LocalRoute local

Aufgrund der Einschränkungen des Windows PowerShell-Bildschirms werden mindestens einige zurückgegebene Informationen (insbesondere die vollständige Beschreibung der übereinstimmenden Normalisierungsregel) möglicherweise nicht auf dem Bildschirm angezeigt. Wenn Sie nur an dem Erfolg oder Misserfolg des Tests interessiert sind, ist dies möglicherweise nicht wichtig. Wenn Sie die vollständigen Details der zurückgegebenen Daten anzeigen möchten, leiten Sie die Ausgabe an das Cmdlet Format-List weiter, wenn Sie den Test ausführen:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Dadurch wird die Ausgabe in einem Leser freundlicheren Format angezeigt:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Muster = ^ (\\d{11}) $; Übersetzung = + $1;

Name = Präfix alle; IsInternalExtension = falsch

FirsMatchingRoute : LocalRoute

MatchingUsage: lokal

Wenn der Test fehlschlägt, gibt Test-CsVoiceUser einen leeren Satz von Eigenschaftswerten zurück:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Es gibt eine Reihe von Gründen, warum das Cmdlet Test-CsVoiceUser möglicherweise fehlschlägt: Es gibt möglicherweise keine Normalisierungsregel, die die angegebene Telefonnummer übersetzen kann. Es können Probleme mit der VoIP-Route auftreten. Es könnte ein Konfigurationsproblem mit dem Wählplan geben, der dem betreffenden Benutzer zugewiesen ist. Aus diesem Grund sollten Sie den Verbose-Parameter einbeziehen, wenn Sie das Cmdlet Test-CsVoiceUser ausführen:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Wenn das Cmdlet "Verbose" enthalten ist, gibt Test-CsVoiceUser eine detaillierte Übersicht über alle Schritte, die bei der Durchführung der Überprüfungen erforderlich sind. So können Sie beispielsweise die folgenden Schritte sehen: 

Ausführlich: Suchen des Benutzers mit der Identität "SIP:kenmyer@litwareinc.com"

Ausführlich: Wähleinstellungen werden geladen: "redmonddialplan" "

Diese zusätzlichen Informationen können Hinweise auf die Schritte liefern, die Sie ausführen können, um die Ursache des Fehlers zu ermitteln. Die hier gezeigte ausführliche Ausgabe zeigt beispielsweise an, dass dem getesteten Benutzer der Wählplan redmonddialplan "zugewiesen wurde. Wenn der Test fehlgeschlagen ist, besteht ein logischer nächster Schritt darin, zu überprüfen, ob redmonddialplan "die angegebene Telefonnummer übersetzen kann.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


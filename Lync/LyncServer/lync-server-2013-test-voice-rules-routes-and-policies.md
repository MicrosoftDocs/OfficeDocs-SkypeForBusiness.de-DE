---
title: 'Lync Server 2013: Testen von VoIP-Regeln,-Routen und-Richtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 689f591b416cdab6eb5d325a7dade2c54659d072
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42017886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Testen von VoIP-Regeln,-Routen und-Richtlinien in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsVoiceUser verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Wenn ein Benutzer einen Anruf tätigt, richtet sich die Route, die der Anruf zum Erreichen seines Ziels benötigt, sowohl nach den Richtlinien als auch den Wählplänen, die diesem Benutzer zugewiesen sind. Wenn die SIP-Adresse und eine Telefonnummer eines Benutzers angegeben werden, überprüft das Cmdlet Test-CsVoiceUser, ob der betreffende Benutzer einen Anruf an diese Nummer abschließen kann. Wenn der Test erfolgreich ist, gibt Test-CsVoiceUser Folgendes zurück:

  - Die im E. 164-Format übersetzte Nummer (basierend auf den Wähleinstellungen des Benutzers)

  - Die Normalisierungsregel, die die Übersetzung bereitgestellt hat

  - Die verwendete VoIP-Route (basierend auf der Routen Priorität);

  - Die Telefonverwendung, die die VoIP-Richtlinie des Benutzers mit der VoIP-Route verknüpft hat.

Mit Test-CsVoiceUser können Sie bestimmen, ob eine bestimmte Telefonnummer wie erwartet weitergeleitet und übersetzt wird und kann bei der Behandlung von anrufbezogenen Problemen behilflich sein, die von einzelnen Benutzern auftreten.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Wenn Sie das Cmdlet Test-CsVoiceUser ausführen, müssen Sie zwei Informationen angeben: die Nummer, die gewählt wird ("DialedNumber") und die Identität des zu testenden Benutzerkontos. Beispielsweise testet dieser Befehl die Fähigkeit des Benutzers, der über die SIP-Adresse SIP:kenmyer@litwareinc.com verfügt, um einen Anruf an die Telefonnummer + 1206555-1219 zu tätigen:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

Die Telefonnummer sollte so formatiert sein, dass Sie von Ihrer Wahl ausgehen. Wenn beispielsweise Benutzer normalerweise nicht die 1 wählen, bevor Sie einen Ferngesprächen tätigen, sollten Sie dieses Format verwenden:

`-DialedNumber "2065551219"`

In diesem Fall schlägt der Test natürlich fehl, wenn keine Normalisierungsregel vorhanden ist, mit der die Nummer 2065551219 korrekt in das von lync Server verwendete E. 164-Telefon Format übersetzt werden kann. Weitere Informationen finden Sie im Hilfethema New-CsVoiceNormalizationRule-Cmdlet.

Wenn Sie denselben Test für jedes Ihrer Benutzerkonten ausführen möchten, können Sie einen Befehl wie den folgenden verwenden:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der Test erfolgreich abgeschlossen wurde (also, wenn der Benutzer einen Anruf für die angegebene Nummer tätigen kann), werden in der Ausgabe Informationen wie die übersetzte Telefonnummer und die passende Normalisierungsregel und VoIP-Route angezeigt:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti...    LocalRoute lokal

Aufgrund der Einschränkungen des Windows PowerShell Bildschirms werden mindestens einige zurückgegebene Informationen (insbesondere die vollständige Beschreibung der übereinstimmenden Normalisierungsregel) möglicherweise nicht auf dem Bildschirm angezeigt. Wenn Sie nur am Erfolg oder Misserfolg des Tests interessiert sind, ist dies möglicherweise nicht wichtig. Wenn Sie die vollständigen Details der zurückgegebenen Daten sehen möchten, übergeben Sie die Ausgabe an das Cmdlet Format-List, wenn Sie den Test ausführen:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Dadurch wird die Ausgabe in einem Leser freundlicheren Format angezeigt:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Muster = ^ (\\d{11}) $; Übersetzung = + $1;

Name = Prefix all; IsInternalExtension = false

FirsMatchingRoute: LocalRoute

MatchingUsage: lokal

Wenn der Test fehlschlägt, gibt Test-CsVoiceUser eine leere Gruppe von Eigenschaftswerten zurück:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Es gibt eine Reihe von Gründen, aus denen das Test-CsVoiceUser-Cmdlet möglicherweise fehlschlägt: Es ist möglicherweise keine Normalisierungsregel vorhanden, mit der die bereitgestellte Telefonnummer übersetzt werden kann. Es kann Probleme mit der VoIP-Route geben. Es kann ein Konfigurationsproblem mit den Wähleinstellungen geben, die dem betreffenden Benutzer zugewiesen sind. Aus diesem Grund sollten Sie den Verbose-Parameter einschließen, wenn Sie das Cmdlet Test-CsVoiceUser ausführen:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Wenn das Verbose-Cmdlet enthalten ist, gibt Test-CsVoiceUser ein detailliertes Konto aller Schritte aus, die bei der Durchführung der Überprüfungen ausgeführt werden. Beispielsweise können Sie die folgenden Schritte wie folgt sehen: 

Ausführlich: Suchen von Benutzern mit der Identität "SIP:kenmyer@litwareinc.com"

Ausführlich: Wähleinstellungen werden geladen: "" redmonddialplan ""

Diese zusätzlichen Informationen können Hinweise auf die Schritte liefern, die Sie ausführen können, um die Ursache des Fehlers zu ermitteln. Die hier gezeigte ausführliche Ausgabe gibt beispielsweise an, dass der getestete Benutzer dem Wählplan "redmonddialplan" zugewiesen wurde. Wenn der Test fehlgeschlagen ist, besteht ein logischer nächster Schritt darin, zu überprüfen, ob die angegebene Telefonnummer von "redmonddialplan" übersetzt werden kann.

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


---
title: 'Lync Server 2013: Testen des PSTN-Telefonanrufs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c9c0b0441ea31e2419101aba188c33b0bbfd70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Testen des PSTN-Anrufs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Täglich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsRegistration verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsPstnOutboundCall testet, ob ein Benutzer einen Anruf bei einer Telefonnummer im PSTN tätigen kann. Wenn Sie Test-CsPstnOutboundCall ausführen, versucht das Cmdlet zunächst, den Testbenutzer bei lync Server zu protokollieren. Wenn die Anmeldung erfolgreich verläuft, versucht das Cmdlet dann, einen Anruf über das PSTN-Gateway zu tätigen. Dieser Anruf erfolgt mithilfe des Wählplans, der VoIP-Richtlinie und anderer Richtlinien und Einstellungen, die dem Testkonto zugewiesen sind. Wenn der Anruf angenommen wird, sendet das Cmdlet DTMF-Codes (Dual-Tone Multi-Frequency) über das Netzwerk, um die Medien Konnektivität zu überprüfen.

Im Rahmen der Tests wird mit Test-CsPstnOutboundCall ein tatsächlicher Telefonanruf durchgeführt: Das angerufene Telefon klingelt, und der Anruf muss für einen erfolgreichen Abschluss des Tests entgegengenommen werden. Dieser Anruf muss zudem manuell vom Administrator beendet werden.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsPstnOutboundCall kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet wird, und die PSTN-Telefonnummer, die aufgerufen wird. Zum Beispiel:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsPstnOutboundCall aufrufen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der angegebene Benutzer den Anruf tätigen kann und der Anruf angenommen wird, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als "Success" markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn der angegebene Benutzer den Anruf nicht tätigen kann oder wenn der Anruf nicht beantwortet wird, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:0987365

Fehler: 403, unzulässig

Diagnose: errorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User

Richtlinie enthält keine Telefonrouten Nutzung

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie keine Telefonnutzung enthält. (Telefonverwendungen binden VoIP-Richtlinien an VoIP-Routen. Ohne sowohl eine VoIP-Richtlinie als auch eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN tätigen.)

Wenn "Test-CsPstnOutboundCall" fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, einschließlich des Verbose-Parameters:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnOutboundCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Diese Ausgabe gibt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:

Einrichten eines Audiovideo-Anrufs zu "SIP: + 12065551219@litwareinc. com; User = Phone".

Eine Ausnahme "A 404 (nicht gefunden) Antwort wurde aus dem Netzwerk empfangen und der Vorgang ist fehlgeschlagen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsPstnOutboundCall möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie hat keine gültige PSTN-Verwendung. Sie können die VoIP-Richtlinie bestimmen, die einem Benutzer zugewiesen ist, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Anschließend können Sie die PSTN-Verwendungen (falls vorhanden) bestimmen, die dieser Richtlinie zugewiesen sind, indem Sie einen Befehl wie den folgenden verwenden, der Informationen zur benutzerbezogenen VoIP-"redmondvoicepolicy" abruft:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen des PSTN-Peer-to-Peer-Anrufs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33aa0447c90ea9c76a1956cb817f0e61ce0d626e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504042"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Testen des PSTN-Peer-to-Peer-Anrufs in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPstnPeerToPeerCall-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Test-CsPstnPeerToPeerCall-Cmdlet überprüft, ob ein Benutzer paar über das PSTN-Gateway (Public Switched Telephone Network) einen Peer-to-Peer-Anruf durchführen muss. Wenn Sie Test-CsPstnPeerToPeerCall aufrufen, versucht das Cmdlet zunächst, sich bei zwei Test Benutzern anzumelden, um lync Server. Unter der Voraussetzung, dass die Anmeldungen erfolgreich sind, wird das Cmdlet dann den Benutzer 1 versuchen, Benutzer 2 über das PSTN-Gateway aufzurufen. In Test-CsPstnPeerToPeerCall wird dieser Aufruf mithilfe des Wählplans, der VoIP-Richtlinie und anderer Richtlinien-und Konfigurationseinstellungen durchführen, die dem Testbenutzer zugewiesen sind. Wenn der Test wie geplant verläuft, überprüft das Cmdlet, dass Benutzer 2 den Anruf annehmen konnte, und meldet sich dann beide Testkonten vom System ab.

Test-CsPstnPeerToPeerCall führt einen tatsächlichen Telefonanruf aus, der überprüft, ob eine Verbindung hergestellt werden kann und der auch DTMF-Codes über das Netzwerk sendet, um festzustellen, ob Medien über die Verbindung gesendet werden können. Der Anruf wird vom Cmdlet selbst beantwortet, und es ist keine manuelle Beendigung des Anrufs erforderlich. (Das heißt, niemand muss Antworten und dann das Telefon aufhängen, das aufgerufen wurde.)

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsPstnPeerToPeerCall-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll. Zum Beispiel:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsPstnPeerToPeerCall aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die angegebenen Benutzer einen Peer-to-Peer-Anruf ausführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn die angegebenen Benutzer einen Peer-to-Peer-Anruf nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:0182361

Fehler: 403, unzulässig

Diagnose: errorCode = 12001, Source = ATL-CS-001.litwareinc.com,

Reason = Benutzerrichtlinie enthält keine Telefonrouten Nutzung

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die VoIP-Richtlinie, die mindestens einem der angegebenen Benutzer zugewiesen ist, keine Telefonnutzung enthält. (Telefonverwendungen binden VoIP-Richtlinien an VoIP-Routen. Ohne sowohl eine VoIP-Richtlinie als auch eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN tätigen.)

Wenn Test-CsPstnPeerToPeerCall fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnPeerToPeerCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden. Diese Ausgabe gibt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:

Einrichten eines Audiovideo-Anrufs zu "SIP: + 12065551219@litwareinc. com; User = Phone".

Eine Ausnahme "A 404 (nicht gefunden) Antwort wurde aus dem Netzwerk empfangen und der Vorgang ist fehlgeschlagen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsPstnPeerToPeerCall Fehler auftreten können:

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


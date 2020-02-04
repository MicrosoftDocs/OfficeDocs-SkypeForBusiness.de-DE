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
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Testen des PSTN-Peer-to-Peer-Anrufs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-05_


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
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPstnPeerToPeerCall-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsPstnPeerToPeerCall überprüft, ob ein paar von Benutzern einen Peer-to-Peer-Anruf über das PSTN-Gateway (Public Switched Telephone Network) durchführen muss. Wenn Sie Test-CsPstnPeerToPeerCall aufrufen, versucht das Cmdlet zunächst, sich bei zwei Test Benutzern mit lync Server anzumelden. Unter der Voraussetzung, dass die Anmeldungen erfolgreich sind, wird das Cmdlet dann vom Benutzer 1 versuchen, Benutzer 2 über das PSTN-Gateway anzurufen. In Test-CsPstnPeerToPeerCall wird dieser Anruf unter Verwendung des Wählplans, der VoIP-Richtlinie und anderer Richtlinien-und Konfigurationseinstellungen durchführen, die dem Testbenutzer zugewiesen sind. Wenn der Test planmäßig verläuft, überprüft das Cmdlet, ob Benutzer 2 den Anruf annehmen konnte, und melden Sie sich dann beide Testkonten vom System ab.

Test-CsPstnPeerToPeerCall führt einen tatsächlichen Telefonanruf durch, der überprüft, ob eine Verbindung hergestellt werden kann, und der auch DTMF-Codes über das Netzwerk überträgt, um festzustellen, ob Medien über die Verbindung gesendet werden können. Der Anruf wird vom Cmdlet selbst beantwortet, und es ist keine manuelle Kündigung des Anrufs erforderlich. (Das heißt, niemand muss Antworten und dann das angerufene Telefon auflegen.)

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsPstnPeerToPeerCall" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben. Beispiel:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsPstnPeerToPeerCall aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die angegebenen Benutzer einen Peer-zu-Peer-Anruf abschließen können, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.8630376

Fehler

Diagnose

Wenn die angegebenen Benutzer keinen Peer-to-Peer-Anruf abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:0182361

Fehler: 403, unzulässig

Diagnose: errorCode = 12001, Source = ATL-CS-001.litwareinc.com,

Reason = Benutzerrichtlinie enthält keine Nutzung der Telefonroute

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die VoIP-Richtlinie, die mindestens einem der angegebenen Benutzer zugewiesen ist, keine Telefonnutzung umfasst. (Telefon-Nutzungen binden VoIP-Richtlinien an VoIP-Routen. Ohne eine VoIP-Richtlinie und eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN führen.)

Wenn Test-CsPstnPeerToPeerCall fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnPeerToPeerCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde. Diese Ausgabe zeigt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:

Einrichten eines Audio-Video Anrufs zu "SIP: + 12065551219@litwareinc. com; Benutzer = Telefon".

Eine Ausnahme "eine 404-Antwort (nicht gefunden)" wurde vom Netzwerk empfangen, und der Vorgang konnte nicht ausgeführt werden.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsPstnPeerToPeerCall möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

  - Die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie hat keine gültige PSTN-Nutzung. Sie können die VoIP-Richtlinie ermitteln, die einem Benutzer zugewiesen ist, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Und dann können Sie die PSTN-Nutzungen (sofern vorhanden) ermitteln, die dieser Richtlinie zugewiesen sind, indem Sie einen Befehl ähnlich der folgenden verwenden, der Informationen zur pro-Benutzer-VoIP-Richtlinien RedmondVoicePolicy abruft:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>


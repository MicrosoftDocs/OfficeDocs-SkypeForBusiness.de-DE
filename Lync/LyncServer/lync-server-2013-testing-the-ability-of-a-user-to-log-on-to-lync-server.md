---
title: 'Lync Server 2013: Testen der Fähigkeit eines Benutzers, sich bei lync Server anzumelden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b40479bc11fc1f46062423d63876b33d9c179aa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Testen der Fähigkeit eines Benutzers, sich bei lync Server 2013 anzumelden

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsRegistration können Sie sicherstellen, dass sich die Benutzer in Ihrer Organisation bei lync Server anmelden können. Wenn Sie Test-CsRegistration ausführen, versucht das Cmdlet, sich an einem Testbenutzer anzumelden, um lync Server und dann, wenn es erfolgreich ist, die Verbindung zwischen diesem Testbenutzer und dem System zu trennen. All dies geschieht ohne Benutzerinteraktion und ohne Auswirkungen auf tatsächliche Benutzer. Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der über ein echtes lync Server Konto verfügt. In diesem Fall wird der Test ohne Unterbrechung des realen Ken Myers durchgeführt. Wenn sich das Ken Myers-Test Konto vom System abmeldet, bleibt die Person angemeldet.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsRegistration kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server registrierungspools angeben, der getestet wird. Beispiel:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsRegistration aufrufen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn sich der angegebene Benutzer bei anmelden kann (und dann Abmelden von) lync Server, erhalten Sie eine Ausgabe ähnlich der folgenden, wobei die Result-Eigenschaft als Success markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn sich der angegebene Benutzer nicht anmelden oder abmelden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: 404, nicht gefunden

Diagnose: errorCode = 1003, Source = ATL-CS-001. litwareinc. com, Reason = Benutzer does

nicht vorhanden

Microsoft. RTC. Signaling. DiagnosticHeader

Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da der angegebene Benutzer nicht gefunden werden konnte. Sie können ermitteln, ob eine SIP-Adresse gültig ist (und ob der Benutzer, dem diese SIP-Adresse zugewiesen ist, für lync Server aktiviert ist), indem Sie den folgenden Befehl ausführen:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Wenn Test-CsRegistration fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsRegistration eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Beispiel:

Ausführlich: Aktivität "registrieren" gestartet.

Senden der Registrierungsanforderung:

Ziel-FQDN = ATL-CS-011.litwareinc.com

SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

Registrierungsstelle Port = 5061.

Der Authentifizierungstyp "vertrauenswürdig" ist ausgewählt.

Eine Ausnahme "der Endpunkt kann nicht registriert werden. Lesen Sie den ErrorCode aus einem bestimmten Grund ", der während der Ausführung des Workflows" Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow "aufgetreten ist.

Ausnahmeaufrufliste: unter Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsRegistration möglicherweise fehlschlägt:

  - Sie haben ein falsches Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Sie haben einen falschen registrierungsstellenpool angegeben. Mit dem folgenden Befehl können Sie die FQDNs ihrer Registrierungsstellen Pools zurückgeben:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Der registrierungsstellenpool ist derzeit nicht verfügbar. Versuchen Sie, den Pool zu pingen, um zu sehen, ob er antwortet:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen der Fähigkeit eines Benutzers zur Anmeldung bei lync Server'
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
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Testen der Fähigkeit eines Benutzers zur Anmeldung bei lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsRegistration-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsRegistration können Sie überprüfen, ob sich die Benutzer in Ihrer Organisation bei lync Server anmelden können. Wenn Sie Test-CsRegistration ausführen, versucht das Cmdlet, sich bei einem Testbenutzer bei lync Server anzumelden, und trennt dann, falls dies erfolgreich ist, den Testbenutzer vom System. All dies geschieht ohne Benutzerinteraktion und ohne Auswirkungen auf tatsächliche Benutzer. Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der ein echtes lync Server-Konto hat. In diesem Fall wird der Test ohne Unterbrechung des echten Ken Myers durchgeführt. Wenn sich das Ken Myers Test-Konto vom System abmeldet, bleibt die Person angemeldet.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsRegistration" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den FQDN des zu testenden lync Server-registrierungspools angeben. Beispiel:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält. Sie müssen das Anmeldeinformationen-Objekt und die SIP-Adresse, die dem Konto zugewiesen ist, beim Aufrufen von Test-CsRegistration einfügen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn sich der angegebene Benutzer bei lync Server anmelden (und dann abmelden kann), erhalten Sie eine ähnliche Ausgabe, wobei die Ergebniseigenschaft als erfolgreich markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.8630376

Fehler

Diagnose

Wenn sich der angegebene Benutzer nicht anmelden oder abmelden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: 404, nicht gefunden

Diagnose: errorCode = 1003, Source = ATL-CS-001. "litwareinc. com, Reason = User

nicht vorhanden

Microsoft. RTC. Signalisierungs-DiagnosticHeader

Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer nicht gefunden wurde. Sie können feststellen, ob eine SIP-Adresse gültig ist (und ob der Benutzer, der diese SIP-Adresse zugewiesen hat, für lync Server aktiviert ist), indem Sie den folgenden Befehl ausführen:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Wenn Test-CsRegistration fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsRegistration eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde. Beispiel:

Ausführlich: die Aktivität "registrieren" wurde gestartet.

Registrierungsanfrage wird gesendet:

Ziel-FQDN = ATL-CS-011.litwareinc.com

SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

Registrar Port = 5061.

Auth-Typ "vertrauenswürdig" ist ausgewählt.

Eine Ausnahme "der Endpunkt kann nicht registriert werden. Informationen dazu finden Sie unter Fehler begründete Fehler während der Workflow-Ausführung "Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow".

Ausnahmeaufrufliste: unter Microsoft. RTC. Signalisierungs-SipAsyncResult'1. throwiffailedplatform ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsRegistration möglicherweise fehlschlägt:

  - Sie haben ein falsches Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

  - Sie haben einen falschen Registrierungspool angegeben. Mit diesem Befehl können Sie die FQDNs ihrer registrierungspools zurückgeben:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Der Registrierungspool steht zurzeit nicht zur Verfügung. Versuchen Sie, den Pool zu pingen, um zu sehen, ob er antwortet:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


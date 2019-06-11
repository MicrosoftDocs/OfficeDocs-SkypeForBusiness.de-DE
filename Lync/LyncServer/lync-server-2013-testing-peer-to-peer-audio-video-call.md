---
title: 'Lync Server 2013: Testen von Peer-to-Peer-Audio/Video-Anruf'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43fc4da7619dcc4cfd88417b52543dc23c447883
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Testen des Peer-to-Peer-Audio/Video-Anrufs in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsP2PAV-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Test-CsP2PAV wird verwendet, um zu ermitteln, ob ein paar Testbenutzer an einer Peer-to-Peer-a/V-Unterhaltung teilnehmen können. Um dieses Szenario zu testen, wird das Cmdlet gestartet, indem die beiden Benutzer zu lync Server angemeldet werden. Wenn die beiden Anmeldungen erfolgreich sind, lädt der erste Benutzer den zweiten Benutzer ein, an einem A/V-Anruf teilzunehmen. Der zweite Benutzer akzeptiert den Anruf, die Verbindung zwischen den beiden Benutzern wird getestet, und der Anruf wird beendet, und die Testbenutzer werden vom System abgemeldet.

Test-CsP2PAV führt tatsächlich keinen A/V-Anruf durch. Es werden keine Multimedia-Informationen zwischen den Testbenutzern ausgetauscht. Stattdessen überprüft das Cmdlet lediglich, ob die entsprechenden Verbindungen hergestellt werden können und dass die beiden Benutzer einen solchen Anruf durchführen können.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsP2PAV" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben. Beispiel:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Anmeldeinformationsobjekte für lync Server (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsP2PAV aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die beiden Testbenutzer einen Peer-to-Peer-a/V-Anruf durchführen können, erhalten Sie eine ähnliche Ausgabe wie die Ergebniseigenschaft, die als erfolgreich markiert wurde **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.8630376

Fehler

Diagnose

Wenn die Testbenutzer den Anruf nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: 480, vorübergehend nicht verfügbar

Diagnose: errorCode = 15030, Quelle = ATL-CS-001. "litwareinc. com, Reason = fehlgeschlagen

So leiten Sie zu Exchange Server weiter

Microsoft. RTC. Signalisierungs-DiagnosticHeader

In der vorherigen Ausgabe wird beispielsweise angegeben, dass der Test fehlgeschlagen ist, weil der Microsoft Exchange-Server nicht kontaktiert werden konnte. Diese Fehlermeldung weist in der Regel auf ein Problem bei der Konfiguration von Exchange Unified Messaging hin.

Wenn Test-CsP2PAV fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

Test-CsP2PAV-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsP2PAV eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während Sie die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Nehmen Sie beispielsweise an, dass Ihr Test mit der folgenden Diagnose fehlgeschlagen ist:

ErrorCode = 6003, Source = ATL-CS-001. "litwareinc. com; Reason = nicht unterstützte Dialog Anfrage

Wenn Sie Test-CsP2PAV erneut ausführen und den Verbose-Parameter hinzufügen, erhalten Sie eine Ausgabe, die der folgenden ähnelt:

Ausführlich: die Aktivität "registrieren" wurde gestartet.

Registrierungsanfrage wird gesendet:

Ziel-FQDN = ATL-CS-011.litwareinc.com

SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

Registrar Port = 5062.

Auth-Typ "IWA" ist ausgewählt.

Eine Ausnahme "der Endpunkt konnte nicht registriert werden. Lesen Sie den ErrorCode aus bestimmten Gründen. während des Workflows Microsoft. RTC. SyntheticTransactions. Workflows. STP2PAVWorkflow-Ausführung aufgetreten.

Es ist zwar nicht unmittelbar klar, ob Sie die Ausgabe sorgfältig untersuchen, doch wird ein falscher Registrierungs Port (Port 5062) angegeben. Dies führte wiederum dazu, dass der Test fehlschlug.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsP2PAV möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
    Get-CsUser "SIP:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen von Peer-to-Peer-Audio/Video-Anruf'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462442b7afea193866dc96aaf57085d780f43a39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Testen von Peer-to-Peer-Audio/Video-anrufen in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsP2PAV verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Test-CsP2PAV wird verwendet, um zu bestimmen, ob ein paar von Testbenutzern an einer Peer-zu-Peer-a/V-Unterhaltung teilnehmen kann. Um dieses Szenario zu testen, wird das Cmdlet durch die Protokollierung der beiden Benutzer lync Server. Unter der Voraussetzung, dass die beiden Anmeldungen erfolgreich sind, lädt der erste Benutzer den zweiten Benutzer ein, an einem A/V-Aufruf teilzunehmen. Der zweite Benutzer nimmt den Anruf an, die Verbindung zwischen den beiden Benutzern wird getestet, und der Anruf wird beendet, und die Testbenutzer werden vom System abgemeldet.

Test-CsP2PAV führt tatsächlich keinen A/V-Aufruf durch. Es werden keine Multimedia-Informationen zwischen den Testbenutzern ausgetauscht. Stattdessen überprüft das Cmdlet lediglich, dass die entsprechenden Verbindungen hergestellt werden können und dass die beiden Benutzer einen solchen Anruf durchführen können.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsP2PAV kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll. Beispiel:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsP2PAV aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die beiden Testbenutzer einen Peer-to-Peer-a/V-Aufruf abschließen können, erhalten Sie eine ähnliche Ausgabe wie diese, wobei die Result-Eigenschaft als Success markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn die Testbenutzer den Anruf nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: 480, vorübergehend nicht verfügbar

Diagnose: errorCode = 15030, Source = ATL-CS-001. litwareinc. com, Reason = failed

So leiten Sie zu Exchange Server um

Microsoft. RTC. Signaling. DiagnosticHeader

Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da die Exchange Server nicht kontaktiert werden konnte. Diese Fehlermeldung weist in der Regel auf ein Problem bei der Konfiguration von Exchange Unified Messaging hin.

Wenn "Test-CsP2PAV" fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, einschließlich des Verbose-Parameters:

Test-CsP2PAV-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsP2PAV eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Nehmen Sie beispielsweise an, dass Ihr Test mit der folgenden Diagnose fehlgeschlagen ist:

ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, Reason = nicht unterstützte out-of-Dialog-Anforderung

Wenn Sie Test-CsP2PAV erneut ausführen und den Parameter Verbose hinzufügen, erhalten Sie eine Ausgabe, die der folgenden ähnelt:

Ausführlich: Aktivität "registrieren" gestartet.

Senden der Registrierungsanforderung:

Ziel-FQDN = ATL-CS-011.litwareinc.com

SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

Registrierungsstelle Port = 5062.

Der Authentifizierungstyp "IWA" ist ausgewählt.

Eine Ausnahme "der Endpunkt konnte sich nicht registrieren. Lesen Sie den ErrorCode aus einem bestimmten Grund. ' während der Ausführung des Workflows "Microsoft. RTC. SyntheticTransactions. Workflows. STP2PAVWorkflow" aufgetreten.

Obwohl es möglicherweise nicht sofort offensichtlich ist, werden Sie feststellen, dass ein falscher Registrierungs Port (Port 5062) angegeben wurde, wenn Sie die Ausgabe sorgfältig untersuchen. Dies hat wiederum dazu geführt, dass der Test fehlschlägt.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsP2PAV möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
    Get-CsUser "SIP:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>


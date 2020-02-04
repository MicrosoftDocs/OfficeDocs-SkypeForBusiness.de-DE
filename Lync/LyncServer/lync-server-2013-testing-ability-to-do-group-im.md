---
title: 'Lync Server 2013: Testen der Gruppen-Chatfunktion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Testen der Fähigkeit zum Gruppieren von Chatnachrichten in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsGroupIM-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsGroupIM überprüft, ob Benutzer in Ihrer Organisation Gruppen-Chatsitzungen durchführen können. Wenn Sie Test-CsGroupIM ausführen, versucht das Cmdlet, ein paar Test Benutzer mit lync Server zu signieren. Wenn Sie erfolgreich sind, erstellt Test-CsGroupIM eine neue Konferenz mit dem ersten Testbenutzer und lädt den zweiten Benutzer ein, an der Konferenz teilzunehmen. Nach einem Austausch von Nachrichten werden beide Benutzer vom System getrennt. Beachten Sie, dass dies alles ohne Benutzerinteraktion und ohne Auswirkungen auf tatsächliche Benutzer geschieht. Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der ein echtes lync Server-Konto hat. In diesem Fall wird der Test ohne Unterbrechung des echten Ken Myers durchgeführt. Auch wenn sich das Ken Myers Test-Konto vom System abmeldet, bleibt die Person beispielsweise angemeldet. Ebenso erhält der wirkliche Ken Myers keine Einladung zur Teilnahme an der Konferenz. Diese Einladung wird an das Testkonto gesendet und von diesem akzeptiert.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsGroupIM" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben. Beispiel:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Anmeldedaten Objekte der lync Server-Verwaltungsshell (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsGroupIM aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die beiden Benutzer eine Gruppen-Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Ergebniseigenschaft als erfolgreich markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.3812203

Fehler

Diagnose

Wenn die beiden Benutzer nicht in der Lage sind, die Chat-Sitzung abzuschließen, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: 404, nicht gefunden

Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht

existieren.

Microsoft. RTC. Signalisierungs-DiagnosticHeader

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, weil mindestens eines der Testkonten ungültig war, weil das Konto nicht vorhanden ist oder der Benutzer nicht für lync Server aktiviert wurde. Sie können überprüfen, ob das Konto vorhanden ist, und ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen ähnlichen Befehl wie den folgenden ausführen:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Wenn Test-CsGroupIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsGroupIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer Gruppen-Chatsitzung überprüft hat. Wenn Ihr Test beispielsweise fehlschlägt und Ihnen mitgeteilt wird, dass ein oder mehrere Benutzerkonten ungültig sind, können Sie den Test mit dem Verbose-Parameter erneut ausführen und feststellen, welches Benutzerkonto ungültig ist:

Registrierungsanfrage wird gesendet:

 Ziel-FQDN = ATL-CS-001.litwareinc.com

 SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

 Port registrieren = 5061

Auth-Typ "IWA" ist ausgewählt.

Eine Ausnahme "die Anmeldung wurde abgelehnt. Überprüfen Sie, ob die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist. "

Wie Sie sehen können, war in diesem Beispiel der Benutzer, der die SIP-Adresse SIP:kenmyer@litwareinc.com, nicht in der Lage, sich anzumelden.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsGroupIM möglicherweise fehlschlägt:

  - Sie haben ein falsches Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert war, führen Sie einen Befehl ähnlich der folgenden aus:
    
    Get-CsUser "SIP:kenmyer@litwareinc.com" | SELECT-Objekt aktiviert
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

  - Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar. Mit lync Server können Sie das System so konfigurieren, dass Sofortnachrichten nicht verfügbar sind, wenn auf die Archivierungsdatenbank nicht zugegriffen werden kann. Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Wenn BlockOnArchiveFailure auf "true" festgelegt ist, sollten Sie ermitteln, ob die Archivierungsdatenbank verfügbar ist. Sie können die Speicherorte ihrer Archivierungsdatenbanken mithilfe des folgenden Befehls zurückgeben:
    
        Get-CsService -ArchivingDatabase

  - Der Archivierungs Server steht möglicherweise nicht zur Verfügung. Mit diesem Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:
    
        Get-CsService -ArchivingServer
    
    Sie können dann den entsprechenden Server anpingen, um zu überprüfen, ob er verfügbar ist. Beispiel:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


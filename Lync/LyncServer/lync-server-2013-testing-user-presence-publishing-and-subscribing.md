---
title: 'Lync Server 2013: Testen der Veröffentlichung und des Abonnierens von Benutzer Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcf12b50a1284a7218789c5964ce714a3a4bdd7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Testen der Veröffentlichung von Benutzer Anwesenheit und abonnieren in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsPresence verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Test-CsPresence wird verwendet, um zu bestimmen, ob ein paar von Testbenutzern sich bei lync Server anmelden und dann Anwesenheitsinformationen austauschen kann. Hierzu meldet das Cmdlet die beiden Benutzer zunächst am System an. Wenn beide erfolgreich angemeldet werden können, fordert der erste Testbenutzer Anwesenheitsinformationen vom zweiten Benutzer an. Der zweite Benutzer veröffentlicht diese Informationen, und mit Test-CsPresence wird geprüft, ob die Informationen erfolgreich an den ersten Benutzer übermittelt wurden. Nach dem Austausch von Anwesenheitsinformationen werden die beiden Testbenutzer dann von lync Server abgemeldet.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsPresence kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll. Beispiel:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsPresence aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die angegebenen Benutzeranwesenheitsinformationen austauschen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.3280315

Fehler

Diagnose

Wenn die beiden Benutzer keine Anwesenheitsinformationen austauschen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: 404, nicht gefunden

Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht

existieren.

Microsoft. RTC. Signaling. DiagnosticHeader

In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, da mindestens eines der beiden Benutzerkonten ungültig ist: entweder ist das Konto nicht vorhanden oder es wurde nicht für lync Server aktiviert. Sie können überprüfen, ob die Konten vorhanden sind, und bestimmen, ob Sie für lync Server aktiviert sind, indem Sie einen Befehl wie den folgenden ausführen:

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

Wenn Test-CsPresence fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPresence eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Beispiel:

Registrierungs Anforderungs Treffer gegen unbekannt

"Registrierung"-Aktivität abgeschlossen in "0,0345791" Sek.

"SelfSubscribeActivity"-Aktivität wurde gestartet.

"SelfSubscribeActivity"-Aktivität wurde in "0,0041174" Sek. abgeschlossen.

"SubscribePresence"-Aktivität wurde gestartet.

"SubscribePresence"-Aktivität wurde in "0,0038764" Sek. abgeschlossen.

"PublishPresence"-Aktivität wurde gestartet.

Eine Ausnahme "Anwesenheits Benachrichtigung wird nicht innerhalb von 25 Sekunden empfangen." bereut Workflow "Microsoft. RTC. SyntheticTransactions. Workflows. STPresenceWorkflow-Ausführung" aufgetreten.

Die Tatsache, dass die Anwesenheits Benachrichtigung nicht innerhalb von 25 Sekunden empfangen wurde, deutet möglicherweise darauf hin, dass Netzwerkprobleme das Austauschen von Informationen verhindern.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsPresence möglicherweise fehlschlägt:

  - Sie haben ein falsches Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>


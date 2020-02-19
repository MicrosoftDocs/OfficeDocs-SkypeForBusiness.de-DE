---
title: 'Lync Server 2013: Testen der Einwahlkonferenz Sitzung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11a5126d0555e39c5e0c4637a70939227c787299
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Testen der Einwahlkonferenz Sitzung in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsDialInConferencing verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsDialInConferencing überprüft, ob ein Benutzer an einer Einwahlkonferenz teilnehmen kann. Test-CsDialInConferencing funktioniert, indem versucht wird, einen Testbenutzer auf dem System zu protokollieren. Wenn die Anmeldung erfolgreich verläuft, verwendet das Cmdlet dann die Anmeldeinformationen und Berechtigungen des Benutzers, um alle verfügbaren Zugriffsnummern für Einwahlkonferenzen zu testen. Der Erfolg oder Misserfolg der einzelnen Einwahl Versuche wird notiert, dann wird der Testbenutzer von lync Server abgemeldet. Test-CsDialInConferencing nur überprüft, ob die entsprechenden Verbindungen hergestellt werden können. Das Cmdlet tätigt keine echten Anrufe und erstellt keine Einwahlkonferenzen, an denen andere Benutzer teilnehmen können.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsDialInConferencing kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll. Zum Beispiel:

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die SIP-Adresse des Kontos zum aufrufenden Test-CsDialInConferencing hinzufügen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn sich der angegebene Benutzer bei lync Server anmelden und dann eine Verbindung mit einer der verfügbaren Zugriffsnummern für Einwahlkonferenzen herstellen kann, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als "Success" markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: das Anmelden wurde verweigert. Stellen Sie sicher, dass die richtigen Anmeldeinformationen

verwendet wird und das Konto aktiv ist.

Innere Ausnahme: NegotiateSecurityAssociation fehlgeschlagen, Fehler:-

2146893044

Diagnose

Die vorherige Ausgabe gibt an, dass dem Testbenutzer der Zugriff auf lync Server selbst verweigert wurde. Dies bedeutet normalerweise, dass die an Test-CsDialInConferencing übergebenen Benutzeranmeldeinformationen ungültig waren. Sie sollten wiederum das Windows PowerShell Credentials-Objekt neu erstellen. Obwohl Sie das Kennwort für das Benutzerkonto abrufen können, können Sie die SIP-Adresse überprüfen, indem Sie einen Befehl wie den folgenden verwenden:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsDialInConferencing möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Möglicherweise verfügen Sie über eine falsche Zugriffsnummer für Einwahlkonferenzen. Sie können die aktuell konfigurierte Liste der Zugriffsnummern für Einwahlkonferenzen mithilfe dieses Befehls zurückgeben:
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>


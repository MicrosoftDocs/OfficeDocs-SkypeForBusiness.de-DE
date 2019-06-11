---
title: 'Lync Server 2013: Testen der Chat Fähigkeit zwischen zwei Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea824216c456e9f673a5383eab0b788933bf53d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Testen der Chat Fähigkeit zwischen zwei Benutzern in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsIM-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsIM überprüft, ob ein paar Testbenutzer Sofortnachrichten austauschen können. Wenn das Cmdlet Test-CsIM aufgerufen wird, versuchen Sie, sich bei einem Paar Testbenutzern mit lync Server anzumelden. Wenn die beiden Anmeldungen erfolgreich sind, startet das Cmdlet dann eine Chatsitzung zwischen den beiden Testbenutzern. (Benutzer 1 lädt Benutzer 2 zu einer Chatsitzung ein, und Benutzer 2 nimmt die Einladung an.) Nachdem Sie überprüft haben, ob Nachrichten zwischen den beiden Benutzern ausgetauscht werden können, beendet Test-CsIM dann die Chatsitzung und protokolliert beide Benutzer vom System.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsIM" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben. Beispiel:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsIM aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die beiden Benutzer eine Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.6630911

Fehler

Diagnose

Wenn die Testbenutzer die Sitzung nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: 504, Server Timeout

Diagnose: errorCode = 2, Quelle = ATL-CS-001. "litwareinc. com, Reason = siehe

Antwortcode und Ursachen Ausdruck.

Microsoft. RTC. Signalisierungs-DiagnosticHeader

Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer nicht gefunden wurde. Sie können feststellen, ob eine SIP-Adresse gültig ist (und ob der Benutzer, der diese SIP-Adresse zugewiesen hat, für lync Server aktiviert wurde), indem Sie den folgenden Befehl ausführen:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Wenn Test-CsIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der beiden Test Benutzer zur Teilnahme an einer Chatsitzung überprüft hat. Hier finden Sie beispielsweise eine Beispielausgabe, die auftritt, wenn eine falsche Gruppe von Benutzeranmeldeinformationen (in diesem Fall ein falsches Kennwort) für Test-CsIM bereitgestellt wird:

Registrierungsanfrage wird gesendet:

Ziel-FQDN = ATL-CS-011.litwareinc.com

SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

Registrar Port = 5061

Auth-Typ "IWA" ist ausgewählt.

Registrierungs Treffer für SIP/ATL-CS-001. "litwareinc. com

' Registrieren '-Aktivität abgeschlossen in ' 0,0601795 ' Sek.

Eine Ausnahme "die Anmeldung wurde abgelehnt. Überprüfen Sie, ob die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist. während des Workflows aufgetreten.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsIM möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

  - Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar. Mit lync Server können Sie das System so konfigurieren, dass Sofortnachrichten nicht verfügbar sind, wenn auf die Archivierungsdatenbank nicht zugegriffen werden kann. Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Wenn BlockOnArchiveFailure auf "true" festgelegt ist, sollten Sie ermitteln, ob die Archivierungsdatenbank verfügbar ist. Sie können die Speicherorte ihrer Archivierungsdatenbanken mithilfe des folgenden Befehls zurückgeben:
    
        Get-CsService -ArchivingDatabase

  - Der Archivierungsserver steht möglicherweise nicht zur Verfügung. Mit diesem Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:
    
        Get-CsService -ArchivingServer
    
    Sie können dann den entsprechenden Server anpingen, um zu überprüfen, ob er verfügbar ist. Beispiel:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


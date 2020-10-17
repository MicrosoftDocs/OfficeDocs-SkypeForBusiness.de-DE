---
title: 'Lync Server 2013: Testen der Fähigkeit zum chatten zwischen zwei Benutzern'
description: 'Lync Server 2013: Testen der Fähigkeit, im zwischen zwei Benutzern zu chatten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560801"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Testen der Fähigkeit zum chatten zwischen zwei Benutzern in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsIM-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Test-CsIM-Cmdlet überprüft, ob ein paar von Testbenutzern Chatnachrichten austauschen kann. Wenn der Aufruf erfolgt, wird das Test-CsIM-Cmdlet gestartet, indem versucht wird, sich an einem Paar von Testbenutzern anzumelden, um lync Server. Wenn die beiden Anmeldungen erfolgreich sind, startet das Cmdlet dann eine Sofortnachrichtensitzung zwischen den beiden Testbenutzern. (Benutzer 1 lädt Benutzer 2 zu einer Sofortnachrichtensitzung ein, und Benutzer 2 nimmt die Einladung an.) Nachdem Sie überprüft haben, ob Nachrichten zwischen den beiden Benutzern ausgetauscht werden können, beendet Test-CsIM dann die Chatsitzung und protokolliert beide Benutzer vom System.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsIM-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll. Zum Beispiel:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsIM aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die beiden Benutzer eine Chatsitzung abschließen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.6630911

Fehler

Diagnose

Wenn die Testbenutzer die Sitzung nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: 504, Server Timeout

Diagnose: errorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = siehe

Antwortcode und Grund Phrase.

Microsoft. RTC. Signaling. DiagnosticHeader

Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da der angegebene Benutzer nicht gefunden werden konnte. Sie können ermitteln, ob eine SIP-Adresse gültig ist (und ob der Benutzer, dem diese SIP-Adresse zugewiesen wurde, für lync Server aktiviert wurde), indem Sie den folgenden Befehl ausführen:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Wenn Test-CsIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die beiden Testbenutzer die Möglichkeit zur Teilnahme an einer Sofortnachrichtensitzung überprüft haben. Hier ist beispielsweise die Beispielausgabe, die auftritt, wenn eine falsche Gruppe von Benutzeranmeldeinformationen (in diesem Fall ein falsches Kennwort) für Test-CsIM bereitgestellt wird:

Senden der Registrierungsanforderung:

Ziel-FQDN = ATL-CS-011.litwareinc.com

SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

Registrierungsstelle = 5061

Der Authentifizierungstyp "IWA" ist ausgewählt.

Registrierungs Treffer gegen SIP/ATL-CS-001. litwareinc. com

"Registrierung"-Aktivität abgeschlossen in "0,0601795" Sek.

Eine Ausnahme: "das Anmelden wurde verweigert. Stellen Sie sicher, dass die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist. während des Workflows aufgetreten.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsIM Fehler auftreten können:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar. Mit lync Server können Sie das System so konfigurieren, dass Sofortnachrichten nicht verfügbar ist, wenn nicht auf die Archivierungsdatenbank zugegriffen werden kann. Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Wenn BlockOnArchiveFailure auf true festgelegt ist, sollten Sie bestimmen, ob die Archivierungsdatenbank verfügbar ist. Mit dem folgenden Befehl können Sie die Speicherorte ihrer Archivierungsdatenbanken zurückgeben:
    
        Get-CsService -ArchivingDatabase

  - Der Archivierungsserver ist möglicherweise nicht verfügbar. Mit dem folgenden Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:
    
        Get-CsService -ArchivingServer
    
    Anschließend können Sie den entsprechenden Server anpingen, um sicherzustellen, dass dieser verfügbar ist. Beispiel:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


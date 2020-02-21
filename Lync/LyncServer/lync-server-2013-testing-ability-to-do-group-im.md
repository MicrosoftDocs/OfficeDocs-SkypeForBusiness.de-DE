---
title: 'Lync Server 2013: Testen der Fähigkeit, Gruppen-Chat zu durchführen'
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
ms.openlocfilehash: eef76c8728a7b5a569efee9305505f4e19f6bceb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Testen der Fähigkeit, Gruppen-Chat in lync Server 2013 zu ausführen

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsGroupIM verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsGroupIM überprüft, ob Benutzer in Ihrer Organisation Gruppen-Chatsitzungen durchführen können. Wenn Sie Test-CsGroupIM ausführen, versucht das Cmdlet, sich an einem Paar von Testbenutzern anzumelden, um lync Server. Wenn die Methode erfolgreich verläuft, erstellt Test-CsGroupIM eine neue Konferenz mit dem ersten Testbenutzer und lädt den zweiten Benutzer ein, an der Konferenz teilzunehmen. Nach dem Austausch von Nachrichten werden beide Benutzer vom System getrennt. Beachten Sie, dass dies alles ohne Benutzerinteraktion und ohne Beeinträchtigung von tatsächlichen Benutzern geschieht. Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der über ein echtes lync Server Konto verfügt. In diesem Fall wird der Test ohne Unterbrechung des realen Ken Myers durchgeführt. Wenn sich beispielsweise das Ken Myers-Test Konto vom System abmeldet, bleibt die Person angemeldet. Ebenso wird der wirkliche Ken Myers keine Einladung erhalten, an der Konferenz teilzunehmen. Diese Einladung wird an das Test Konto gesendet und von diesem akzeptiert.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsGroupIM kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll. Zum Beispiel:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server-Verwaltungsshell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsGroupIM aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die beiden Benutzer eine Gruppen-Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success** markiert ist:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.3812203

Fehler

Diagnose

Wenn die beiden Benutzer nicht in der Lage sind, die Sofortnachrichtensitzung abzuschließen, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: 404, nicht gefunden

Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht

existieren.

Microsoft. RTC. Signaling. DiagnosticHeader

Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da mindestens eines der Testkonten ungültig war, da das Konto nicht vorhanden ist oder der Benutzer nicht für lync Server aktiviert wurde. Sie können überprüfen, ob das Konto vorhanden ist, und ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Wenn Test-CsGroupIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsGroupIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer Gruppe von Chatsitzungen überprüft hat. Wenn der Test beispielsweise fehlschlägt und Ihnen mitgeteilt wird, dass ein oder mehrere Benutzerkonten ungültig sind, können Sie den Test mit dem Verbose-Parameter erneut ausführen und bestimmen, welches Benutzerkonto ungültig ist:

Senden der Registrierungsanforderung:

 Ziel-FQDN = ATL-CS-001.litwareinc.com

 SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com

 Register Port = 5061

Der Authentifizierungstyp "IWA" ist ausgewählt.

Eine Ausnahme: "das Anmelden wurde verweigert. Stellen Sie sicher, dass die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist.

Wie Sie sehen können, konnte sich der Benutzer, der über die SIP-Adresse SIP:kenmyer@litwareinc.com verfügt, in diesem Beispiel nicht anmelden.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsGroupIM möglicherweise fehlschlägt:

  - Sie haben ein falsches Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:
    
    Get-CsUser "SIP:kenmyer@litwareinc.com" | SELECT-Objekt aktiviert
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar. Mit lync Server können Sie das System so konfigurieren, dass Chatnachrichten nicht verfügbar sind, wenn nicht auf die Archivierungsdatenbank zugegriffen werden kann. Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Wenn BlockOnArchiveFailure auf true festgelegt ist, sollten Sie bestimmen, ob die Archivierungsdatenbank verfügbar ist. Mit dem folgenden Befehl können Sie die Speicherorte ihrer Archivierungsdatenbanken zurückgeben:
    
        Get-CsService -ArchivingDatabase

  - Die Archivierungsserver ist möglicherweise nicht verfügbar. Mit dem folgenden Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:
    
        Get-CsService -ArchivingServer
    
    Anschließend können Sie den entsprechenden Server anpingen, um sicherzustellen, dass dieser verfügbar ist. Beispiel:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


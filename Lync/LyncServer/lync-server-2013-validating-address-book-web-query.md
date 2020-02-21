---
title: 'Lync Server 2013: Überprüfen der Adressbuch-Webabfrage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 548ec62a56de829955647a696e33578b9ab3dfd8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Überprüfen der Adressbuch-Webabfrage in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsAddressBookWebQuery verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsAddressBookWebQuery können Administratoren überprüfen, ob Benutzer mit der Adressbuch-Webabfragedienst nach einem bestimmten Kontakt suchen können. Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookWebQuery zunächst eine Verbindung mit dem webticketdienst her, der authentifiziert werden soll. Wenn die Authentifizierung erfolgreich ist, stellt das Cmdlet eine Verbindung mit dem Adressbuch-Webabfragedienst her und sucht nach dem angegebenen Kontakt. Wird der Kontakt gefunden, versucht das Cmdlet, diese Informationen an den lokalen Computer zurückzugeben. Der Test wird nur dann als erfolgreich markiert, wenn alle diese Schritte ausgeführt werden können.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsAddressBookWebQuery kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools und die SIP-Adresse des Benutzers angeben, der als Ziel der Suche fungiert. Zum Beispiel:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie ein Windows PowerShell Credentials-Objekt erstellen, das einen gültigen Benutzernamen und ein gültiges Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse einschließen, wenn der Code Test-CsAddressBookWebQuery aufruft:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der angegebene Benutzer eine Verbindung mit dem Adressbuchdienst herstellen und die Zielbenutzer Adresse abrufen kann, wird die Ausgabe wie folgt zurückgegeben, wobei die Ergebniseigenschaft als "Success" markiert ist:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.2611356

Fehler

Diagnose

Wenn der angegebene Benutzer keine Verbindung herstellen kann oder die Zielbenutzer Adresse nicht abgerufen werden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: die Webdienstanforderung für das Adressbuch ist mit dem Antwortcode fehlgeschlagen.

NoEntryFound.

Diagnose

Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da der Zielbenutzer nicht gefunden werden konnte. Sie können ermitteln, ob eine gültige SIP-Adresse an Test-CsAddressBookWebQuery übergeben wurde, indem Sie einen Befehl wie den folgenden ausführen:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Wenn Test-CsAddressBookWebQuery fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsAddressBookWebQuery eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wird. Diese Ausgabe gibt beispielsweise an, dass Test-CsAddressBookWebQuery eine Verbindung mit dem Adressbuchdienst herstellen konnte, aber die Ziel-SIP-Adresse konnte nicht gefunden werden:

"QueryAddressBookWebService"-Aktivität wurde gestartet.

Adressbuch-Webabfrage Dienst wird aufgerufen. ABWS-URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Adressbuch-Abfrage Ausnahme: Fehler bei der Adressbuch-Webdienstanforderung mit Antwortcode NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsAddressBookWebQuery möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Der Zielbenutzer ist möglicherweise nicht im Adressbuch.

  - Das Adressbuch wurde möglicherweise nicht vollständig aktualisiert und repliziert. Sie können eine Aktualisierung aller Adressbuchserver in Ihrer Organisation erzwingen, indem Sie den folgenden Befehl ausführen:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>


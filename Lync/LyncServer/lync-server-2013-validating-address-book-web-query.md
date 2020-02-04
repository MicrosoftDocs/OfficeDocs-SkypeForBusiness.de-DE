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
ms.openlocfilehash: 31d6a38c0c1d8a67977f9dd66da2a94b51a4f9ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Überprüfen von Adressbuch-Webabfragen in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAddressBookWebQuery-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsAddressBookWebQuery ermöglicht Administratoren, zu überprüfen, ob Benutzer den Adressbuch-Webabfrage Dienst verwenden können, um nach einem bestimmten Kontakt zu suchen. Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookWebQuery zuerst eine Verbindung mit dem Web Ticket-Dienst her, um authentifiziert zu werden. Wenn die Authentifizierung erfolgreich ist, stellt das Cmdlet eine Verbindung mit dem Adressbuch-Webabfrage Dienst her und sucht nach dem angegebenen Kontakt. Wenn dieser Kontakt gefunden wird, versucht das Cmdlet, diese Informationen an den lokalen Computer zurückzugeben. Der Test wird nur dann als erfolgreich markiert, wenn alle diese Schritte ausgeführt werden können.

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsAddressBookWebQuery" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist. Damit diese Überprüfung mit einem Testkonto ausgeführt werden kann, müssen Sie lediglich den FQDN des lync Server-Pools und die SIP-Adresse des Benutzers angeben, der als Ziel für die Suche fungiert. Beispiel:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das einen gültigen Benutzernamen und ein Kennwort enthält. Sie müssen dann das Anmeldeinformationsobjekt und die SIP-Adresse einbeziehen, die dem Konto zugewiesen ist, wenn der Code Test-CsAddressBookWebQuery aufruft:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der angegebene Benutzer eine Verbindung mit dem Adressbuchdienst herstellen und die Zieladresse des Benutzers abrufen kann, geben Sie eine ähnliche Ausgabe zurück, wobei die Ergebniseigenschaft als erfolgreich markiert ist:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.2611356

Fehler

Diagnose

Wenn der angegebene Benutzer keine Verbindung herstellen kann oder wenn die Zielbenutzer Adresse nicht abgerufen werden kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: die Adressbuch-Webdienstanforderung ist mit dem Antwortcode fehlgeschlagen.

NoEntryFound.

Diagnose

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, weil der Zielbenutzer nicht gefunden wurde. Sie können feststellen, ob eine gültige SIP-Adresse an Test-CsAddressBookWebQuery übergeben wurde, indem Sie einen Befehl wie den folgenden ausführen:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Wenn Test-CsAddressBookWebQuery fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsAddressBookWebQuery eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde. Diese Ausgabe zeigt beispielsweise an, dass Test-CsAddressBookWebQuery eine Verbindung mit dem Adressbuchdienst herstellen konnte, aber die Ziel-SIP-Adresse konnte nicht gefunden werden:

Die Aktivität "QueryAddressBookWebService" wurde gestartet.

Aufruf des Adressbuch-Webabfrage Diensts. ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Ausnahme für Adressbuch Abfragen: die Adressbuch-Webdienstanforderung ist mit dem Antwortcode NoEntryFound fehlgeschlagen.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsAddressBookWebQuery möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

  - Der Zielbenutzer befindet sich möglicherweise nicht im Adressbuch.

  - Das Adressbuch wurde möglicherweise nicht vollständig aktualisiert und repliziert. Sie können eine Aktualisierung aller Adressbuchserver in Ihrer Organisation erzwingen, indem Sie den folgenden Befehl ausführen:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>


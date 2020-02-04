---
title: 'Lync Server 2013: Überprüfen des Zugriffs auf das Adressbuch'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Überprüfen des Adressbuch Zugriffs in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAddressBookService-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsAddressBookService bietet eine Möglichkeit, um zu überprüfen, ob ein Benutzer eine Verbindung mit dem Webdienst des Adressbuchs herunterladen kann. Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookService eine Verbindung mit dem Download-Webdienst des Adressbuchs im angegebenen Pool her und fordert den Speicherort der Adressbuchdateien an. Wenn das Adressbuch, das vom Webdienst heruntergeladen wird, diesen Speicherort bereitstellt, wird der Test als erfolgreich angesehen. Wenn die Anforderung abgelehnt wird, wird der Test als Fehler gewertet.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsAddressBookService" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde. Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des zu testenden lync-Server Pools angeben. Beispiel:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält. Sie müssen das Anmeldeinformationsobjekt und die SIP-Adresse, die dem Konto zugewiesen ist, beim Aufrufen von Test-CsAddressBookService einfügen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der angegebene Benutzer in der Lage ist, eine Verbindung mit dem Adressbuchdienst herzustellen, erhalten Sie eine ähnliche Ausgabe wie diese, wobei die Eigenschaft Ergebnis als **erfolgreich**markiert ist:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.2260399

Fehler

Diagnose

Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetUri

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht

existieren.

Microsoft. RTC. Signalisierungs-DiagnosticHeader

In der vorhergehenden Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer (also der "Ziel-URI") entweder nicht vorhanden ist oder für lync Server nicht aktiviert wurde. Sie können überprüfen, ob ein Benutzerkonto gültig ist, und sicherstellen, dass Sie die richtige SIP-Adresse angegeben haben, indem Sie einen Befehl wie den folgenden ausführen:

Get-CsUser-Identity "SIP:kenmyer@litwareinc.com" | Select-Object SipAddress, aktiviert

Wenn Test-CsAddressBookService fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

Test-CsAddressBookService-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose

Wenn der Verbose-Parameter enthalten ist, gibt CsAddressBookService eine Schritt-für-Schritt-Konto für jede Aktion zurück, die beim Überprüfen der Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server versucht wurde. Diese Beispielausgabe zeigt beispielsweise, dass Test-CsAddressBookService, zumindest in diesem Beispiel, die Adressbuchdatei herunterladen konnte:

Sendet eine HTTP GET-Anforderung.

Dateipfad =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Nummer des Versuchs = 1

Timeout (MS) = 60000

Die ABS-Datei wurde erfolgreich heruntergeladenhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsAddressBookService möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


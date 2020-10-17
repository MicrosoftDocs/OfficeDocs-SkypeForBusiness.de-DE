---
title: 'Lync Server 2013: Überprüfen des Adressbuch Zugriffs'
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
ms.openlocfilehash: ea3344c0a0a4f1992cc9ef67cd14bc2321419307
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508582"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a>Überprüfen des Adressbuch Zugriffs in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAddressBookService-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Test-CsAddressBookService-Cmdlet können Sie überprüfen, ob ein Benutzer eine Verbindung mit dem Webdienst für den Adressbuch Download herstellen kann. Wenn Sie das Cmdlet ausführen, stellt Test-CsAddressBookService eine Verbindung mit dem Adressbuch-Download-Webdienst im angegebenen Pool her und fordert den Speicherort der Adressbuchdateien an. Wenn der Adressbuch-Download-Webdienst diesen Speicherort bereitstellt, wird der Test als erfolgreich betrachtet. Wenn die Anforderung abgelehnt wird, wird der Test als nicht erfolgreich betrachtet.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsAddressBookService-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert wurde. Um diese Prüfung mit einem Testkonto auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Tests lync Server Pools angeben. Zum Beispiel:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn Sie Test-CsAddressBookService aufrufen:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der angegebene Benutzer eine Verbindung mit dem Adressbuchdienst herstellen kann, wird die Ausgabe wie folgt zurückgegeben, wobei die Result-Eigenschaft als **Success**markiert ist:

TargetUri https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.2260399

Fehler

Diagnose

Wenn der angegebene Benutzer diese Verbindung nicht herstellen kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetUri

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht

existieren.

Microsoft. RTC. Signaling. DiagnosticHeader

Die obige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da der angegebene Benutzer (also der "Ziel-URI") entweder nicht vorhanden oder für lync Server nicht aktiviert wurde. Sie können überprüfen, ob ein Benutzerkonto gültig ist, und sicherstellen, dass Sie die richtige SIP-Adresse angegeben haben, indem Sie einen Befehl wie den folgenden ausführen:

Get-CsUser-Identity "SIP:kenmyer@litwareinc.com" | Select-Object SipAddress, aktiviert

Wenn Test-CsAddressBookService fehlschlägt, möchten Sie den Test möglicherweise erneut ausführen, und zwar mit dem Verbose-Parameter:

Test-CsAddressBookService-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose

Wenn der Verbose-Parameter enthalten ist Test-CsAddressBookService gibt eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Fähigkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden. Beispielsweise zeigt diese Beispielausgabe, dass Test-CsAddressBookService zumindest in diesem Beispiel die Adressbuchdatei herunterladen konnte:

Senden der HTTP GET-Anforderung.

Dateipfad = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Nummer des Versuchs = 1

Timeout (MS) = 60000

Die ABS-Datei wurde erfolgreich heruntergeladen. https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsAddressBookService Fehler auftreten können:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

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


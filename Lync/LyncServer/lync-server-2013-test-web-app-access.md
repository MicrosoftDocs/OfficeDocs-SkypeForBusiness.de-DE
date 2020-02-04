---
title: 'Lync Server 2013: Testen des Web App-Zugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Testen des Web App-Zugriffs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Monatlich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsWebApp-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsWebApp überprüft, ob authentifizierte Benutzer mit lync Web App an lync Server-Konferenzen teilnehmen können. Wenn Sie das Cmdlet ausführen, kontaktiert Test-CsWebApp den Web-Ticket Dienst, um Web-Tickets für die angegebenen Benutzer zu erhalten. Diese Tickets fungieren effektiv als "Eintrittskarten" für die lync Server-Konferenz. Wenn die Tickets abgerufen werden können und die Benutzer authentifiziert werden können, setzt sich Test-CsWebApp dann mit dem lync-Server in Verbindung und versucht, getrennte Konferenzen für Chats, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.

Beachten Sie, dass Test-CsWebApp nur die APIs und Verbindungen überprüft, die zum Erstellen dieser Konferenzen verwendet werden. Mit dem Cmdlet soll überprüft werden, ob lync Web App zum Erstellen und teilnehmen an Konferenzen verwendet werden kann. Es wird jedoch nicht tatsächlich eine Konferenz erstellt und durchgeführt.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsWebApp" kann entweder mit einem vorkonfigurierten Test Konto oder mit den Konten zweier Benutzer ausgeführt werden, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des lync-Server Pools angeben, der getestet wird. Beispiel:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsWebApp aufrufen:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Beachten Sie, dass Test-CsWebApp für die Verwendung in lync Server 2013 veraltet war.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Test-CsWebApp die Benutzer an Ihren Konferenzen teilnehmen kann, gibt das Cmdlet den Erfolg des Testergebnisses zurück:

Ziel-FQDN:

Ergebnis: Erfolg

Latenz: 00:00:00

Fehlermeldung:

Diagnose

Wenn die Benutzer nicht an den erforderlichen Konferenzen teilnehmen können, wird das Testergebnis als Fehler gekennzeichnet. In der Regel wird in Test-CsWebApp auch eine detaillierte Fehlermeldung und Diagnose zurückgemeldet:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehlermeldung: keine Antwort für Web-Ticket-Service erhalten

Diagnose: die HTTP-Anforderung ist mit dem Client nicht autorisiert

Authentifizierungsschema "NTLM". Die Authentifizierung

der vom Server empfangene Header lautet "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Bei Test-CsWebApp-Fehlern sind in der Regel Benutzer Authentifizierungsfehler aufgetreten. Wenn Test-CsWebApp fehlschlägt, sollten Sie zuerst überprüfen, ob die angegebenen Benutzer über gültige Benutzerkonten verfügen und für lync Server aktiviert sind. Sie können Kontoinformationen abrufen, indem Sie einen Befehl wie den folgenden verwenden:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder der Befehl fehlschlägt, bedeutet dies, dass der Benutzer kein gültiges lync Server-Konto hat. Sie sollten auch sicherstellen, dass die für das Cmdlet angegebenen Kennwörter gültig sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>


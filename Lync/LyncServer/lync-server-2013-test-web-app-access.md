---
title: 'Lync Server 2013: Testen des webapp-Zugriffs'
description: 'Lync Server 2013: Testen Sie den webapp-Zugriff.'
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
ms.openlocfilehash: fc3bbc8008df4fe47fc5a39571356383fe5a6035
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560831"
---
# <a name="test-web-app-access-in-lync-server-2013"></a>Testen des webapp-Zugriffs in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-07_


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
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsWebApp-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Test-CsWebApp-Cmdlet überprüft, ob authentifizierte Benutzer lync Server Konferenzen mithilfe der lync Web App beitreten können. Wenn Sie das Cmdlet ausführen, kontaktiert Test-CsWebApp den Webdienst, um webtickets für die angegebenen Benutzer zu erhalten. Diese Tickets fungieren effektiv als "Eintrittskarten" für die lync Server Konferenz. Wenn die Tickets abgerufen werden können und die Benutzer authentifiziert werden können, kontaktieren Test-CsWebApp dann lync Server und versuchen, separate Konferenzen für Chatnachrichten, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.

Beachten Sie, dass Test-CsWebApp nur die APIs und Verbindungen überprüft, die zum Erstellen dieser Konferenzen verwendet wurden. Das Cmdlet soll sicherstellen, dass lync Web App zum Erstellen und beitreten von Konferenzen verwendet werden kann. Es wird jedoch nicht tatsächlich erstellt und eine Konferenz durchführen.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsWebApp-Cmdlet kann entweder mit vorkonfigurierten Testkonten oder mit den Konten von zwei Benutzern ausgeführt werden, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des getesteten lync Server Pools angeben. Zum Beispiel:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsWebApp aufrufen:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Beachten Sie, dass Test-CsWebApp für die Verwendung in lync Server 2013 veraltet ist.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Test-CsWebApp die Benutzer zu ihren Konferenzen hinzufügen können, gibt das Cmdlet das Testergebnis Success zurück:

Ziel-FQDN:

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn die Benutzer nicht an den erforderlichen Konferenzen teilnehmen können, wird das Testergebnis als Fehler gekennzeichnet. Normalerweise werden Test-CsWebApp auch eine ausführliche Fehlermeldung und Diagnose zurückmelden:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: keine Antwort für Web-Ticket Dienst empfangen

Diagnose: die HTTP-Anforderung ist nicht autorisiert mit dem Client

Authentifizierungsschema ' NTLM '. Die Authentifizierung

vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Test-CsWebApp Fehler beziehen sich in der Regel auf Benutzer Authentifizierungsfehler. Wenn Test-CsWebApp fehlschlägt, sollten Sie zunächst überprüfen, ob die angegebenen Benutzer über gültige Benutzerkonten verfügen und für lync Server aktiviert sind. Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt. Sie sollten auch überprüfen, ob die Kennwörter, die Sie für das Cmdlet angegeben haben, gültig sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>


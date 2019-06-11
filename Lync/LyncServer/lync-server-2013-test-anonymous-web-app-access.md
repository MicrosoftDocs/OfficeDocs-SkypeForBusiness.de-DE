---
title: 'Lync Server 2013: Testen des anonymen Web App-Zugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 701954a872645e80d6aac82cab1fbf5745ad6984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Testen des anonymen Web App-Zugriffs in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsWebAppAnonymous-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsWebAppAnonymous überprüft, ob ein anonymer Benutzer mit lync Web App an lync Server-Konferenzen teilnehmen kann. Wenn Sie das Cmdlet ausführen, kontaktiert Test-CsWebAppAnonymous den Web Ticket-Dienst, um ein WebTICKET für den anonymen Benutzer zu erhalten. Wenn es dem Cmdlet gelingt, dieses Ticket zu erhalten, kontaktiert Test-CsWebAppAnonymous dann den lync-Server und versucht, getrennte Konferenzen für Chats, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.

Beachten Sie, dass Test-CsWebAppAnonymous nur die APIs und Verbindungen überprüft, die zum Erstellen dieser Konferenzen verwendet werden. Das Cmdlet erstellt und führt keine Konferenzen aus.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet "Test-CsWebAppAnonymous" kann entweder mit einem vorkonfigurierten Test Konto oder mit den Konten zweier Benutzer ausgeführt werden, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des lync-Server Pools angeben, der getestet wird. Beispiel:

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Anmeldedaten Objekte der lync Server-Verwaltungsshell (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsWebAppAnonymous aufrufen:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Weitere Informationen finden Sie im Hilfethema zum Cmdlet Test-CsWebAppAnonymous. Beachten Sie, dass Test-CsWebAppAnonymous für die Verwendung in lync Server 2013 veraltet ist.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Test-CsWebAppAnonymous dem anonymen Benutzer zu seinen Konferenzen beitreten kann, gibt das Cmdlet den Erfolg des Testergebnisses zurück:

Ziel-FQDN:

Ergebnis: Erfolg

Latenz: 00:00:00

Fehlermeldung:

Diagnose

Wenn der anonyme Benutzer nicht an den erforderlichen Konferenzen teilnehmen kann, wird das Testergebnis als Fehler gekennzeichnet. In der Regel wird in Test-CsWebAppAnonymous auch eine detaillierte Fehlermeldung und Diagnose zurückgemeldet:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:05.9746266

Fehlermeldung: keine Antwort für Web-Ticket-Service erhalten

Diagnose: die HTTP-Anforderung ist mit dem Client nicht autorisiert

Authentifizierungsschema "NTLM". Die Authentifizierung

der vom Server empfangene Header lautet "Negotiate, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

CsWebAppAnonymous-Fehler in der Regel drehen sich um Benutzer Authentifizierungsfehler: Sie müssen den Test mit einem gültigen Benutzerkonto ausführen, obwohl das Cmdlet die Möglichkeit eines anonymen Benutzers überprüft, eine Verbindung mit lync Server herzustellen. Wenn Test-CsWebAppAnonymous fehlschlägt, sollten Sie überprüfen, ob der angegebene Benutzer ein lync Server-Benutzerkonto gültig ist. Sie können lync Server-Kontoinformationen mithilfe eines Befehls wie den folgenden abrufen:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder der Befehl fehlschlägt, bedeutet dies, dass der Benutzer kein gültiges lync Server-Konto hat.

Sie sollten auch sicherstellen, dass das Kennwort, das Sie beim Ausführen des Cmdlets angegeben haben, ein gültiges Kennwort ist.

Konfigurationsprobleme mit Office Web Apps Server können auch dazu führen, dass Test-CsWebAppAnonymous fehlschlägt. Das ist häufig der Fall, wenn Sie die folgende Diagnose erhalten:

Die HTTP-Anforderung ist mit dem Clientauthentifizierungsschema "NTLM" nicht autorisiert. Der vom Server empfangene Authentifizierungsheader lautet "Negotiate, NTLM".

Weitere Informationen zum Diagnostizieren und Beheben von Problemen mit dem Office Web Apps-Server finden Sie im Blogbeitrag [Office Web Apps Server 2013 – Computer werden immer als](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)fehlerhaft gemeldet.

</div>

</div>

<span> </span>

</div>

</div>

</div>


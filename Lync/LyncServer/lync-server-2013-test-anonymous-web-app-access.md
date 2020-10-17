---
title: 'Lync Server 2013: Testen des anonymen webapp-Zugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a3d90d3de8624f9965b04990ad996d9c04a954f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519312"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Testen des anonymen webapp-Zugriffs in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsWebAppAnonymous-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Test-CsWebAppAnonymous-Cmdlet wird überprüft, ob ein anonymer Benutzer lync Server Konferenzen mithilfe der lync Web App beitreten kann. Wenn Sie das-Cmdlet ausführen, kontaktiert Test-CsWebAppAnonymous den webticketdienst, um ein WebTICKET für den anonymen Benutzer zu erhalten. Wenn es dem Cmdlet gelingt, dieses Ticket zu erhalten, kontaktiert Test-CsWebAppAnonymous dann lync Server und versucht, separate Konferenzen für Sofortnachrichten, Anwendungsfreigabe und Datenzusammenarbeit einzurichten.

Beachten Sie, dass Test-CsWebAppAnonymous nur die APIs und Verbindungen überprüft, die zum Erstellen dieser Konferenzen verwendet wurden. Das Cmdlet erstellt und führt keine Konferenzen tatsächlich aus.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsWebAppAnonymous-Cmdlet kann entweder mit vorkonfigurierten Testkonten oder mit den Konten von zwei Benutzern ausgeführt werden, die für lync Server aktiviert sind. Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den vollqualifizierten Domänennamen des getesteten lync Server Pools angeben. Zum Beispiel:

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server-Verwaltungsshell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsWebAppAnonymous aufrufen:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Weitere Informationen finden Sie im Hilfethema zum Cmdlet Test-CsWebAppAnonymous. Beachten Sie, dass Test-CsWebAppAnonymous für die Verwendung in lync Server 2013 veraltet ist.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Test-CsWebAppAnonymous den anonymen Benutzer zu seinen Konferenzen hinzufügen können, gibt das Cmdlet das Testergebnis Success zurück:

Ziel-FQDN:

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn der anonyme Benutzer nicht an den erforderlichen Konferenzen teilnehmen kann, wird das Testergebnis als Fehler markiert. Normalerweise werden Test-CsWebAppAnonymous auch eine ausführliche Fehlermeldung und Diagnose zurückmelden:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:05.9746266

Fehlermeldung: keine Antwort für Web-Ticket Dienst empfangen

Diagnose: die HTTP-Anforderung ist nicht autorisiert mit dem Client

Authentifizierungsschema ' NTLM '. Die Authentifizierung

vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Bei Test-CsWebAppAnonymous Fehlern dreht sich in der Regel um Benutzer Authentifizierungsfehler: Sie müssen den Test mit einem gültigen Benutzerkonto ausführen, obwohl das Cmdlet die Möglichkeit eines anonymen Benutzers prüft, eine Verbindung mit lync Server herzustellen. Wenn Test-CsWebAppAnonymous fehlschlägt, sollten Sie überprüfen, ob der angegebene Benutzer über ein gültiges lync Server Benutzerkonto verfügt. Sie können lync Server Kontoinformationen abrufen, indem Sie einen Befehl wie den folgenden verwenden:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt.

Sie sollten auch überprüfen, ob das Kennwort, das Sie beim Ausführen des Cmdlets angegeben haben, ein gültiges Kennwort ist.

Konfigurationsprobleme mit Office-webapps Server können auch dazu führen, dass Test-CsWebAppAnonymous fehlschlägt; Dies wird häufig der Fall sein, wenn Sie die folgende Diagnose erhalten:

Die HTTP-Anforderung ist nicht autorisiert mit dem Clientauthentifizierungsschema "NTLM". Der vom Server empfangene Authentifizierungsheader lautete "aushandeln, NTLM".

Weitere Informationen zum Diagnostizieren und Beheben von Problemen mit Office-webapps-Servern finden Sie im Blog Post [Office-webapps Server 2013-Computer werden immer als](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)fehlerhaft gemeldet.

</div>

</div>

<span> </span>

</div>

</div>

</div>


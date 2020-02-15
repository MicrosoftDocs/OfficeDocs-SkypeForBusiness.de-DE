---
title: 'Lync Server 2013: Testen der Fähigkeit von mobilen Benutzern zum Austauschen von Chatnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84e4a79f511247b3c335872b7a1ec31fb9f2201e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Testen der Fähigkeit von mobilen Benutzern zum Austauschen von Chatnachrichten in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsMcxP2PIM verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Mobilitätsdienst können Benutzer mobiler Geräte folgende Aufgaben ausführen:

1.  Exchange-Sofortnachrichten und Anwesenheitsinformationen.

2.  Speichern und Abrufen von Voicemail intern statt mit Ihrem drahtlosen Anbieter.

3.  Nutzen Sie lync Server Funktionen wie "Anruf über Arbeit" und "Einwahlkonferenzen".

Das Cmdlet Test-CsMxcP2PIM bietet eine schnelle und einfache Möglichkeit, um sicherzustellen, dass Benutzer den Mobilitätsdienst zum Austauschen von Sofortnachrichten verwenden können.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Zum Ausführen dieses Tests müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsMcxP2PIM aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die beiden Testbenutzer Chatnachrichten mithilfe des mobilitätsdiensts austauschen können, gibt Test-CsMcxP2PIM Testergebnis Erfolg zurück:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:http://atl-cs-001.litwareinc.com:443/mcx

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn der Test fehlschlägt, wird das Ergebnis auf "Failure" festgelegt, und es wird eine ausführliche Fehlermeldung und Diagnose angezeigt:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:https://atl-cs-001.litwareinc.com:443/mcx

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: Es wurde keine Antwort für den WebTICKET Dienst empfangen.

Innere Ausnahme: die HHTP-Anforderung ist nicht autorisiert mit

Client-Aushandlungs Schema ' NTLM '. Die Authentifizierung

vom Server empfangene Kopfzeile lautete "aushandeln, NTLM".

Innere Ausnahme: der Remoteserver hat einen Fehler zurückgegeben:

(401) nicht autorisiert.

Diagnose

Innere Diagnose: X-MS-Server-Fqdb: ATL-CS-

001.litwareinc.com

Cache-Control: privat

Content-Type: Text/HTML; charset = UTF-8.

Server: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-powered by: ASP.net

X-Content-Type-Optionen: nosniff

Date: Mi, 28 May 2014 19:16:05 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsMcxP2PIM fehlschlägt, sollte der erste Schritt sein, um zu überprüfen, ob der Mobilitätsdienst ausgeführt wird. Dies kann mithilfe eines Webbrowsers erfolgen, um sicherzustellen, dass auf die Mobilitätsdienst-URL für Ihren lync Server-Pool zugegriffen werden kann. Mit diesem Befehl wird beispielsweise die URL für die ATL-CS-001.litwareinc.com des Pools überprüft:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Wenn der Mobilitätsdienst scheinbar ausgeführt wird, stellen Sie sicher, dass Ihre beiden Testbenutzer über gültige lync Server Konten verfügen. Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt.

Sie sollten auch sicherstellen, dass der Benutzer für Mobilität aktiviert ist. Ermitteln Sie dazu zunächst die Mobilitätsrichtlinie, die dem Konto zugewiesen ist:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Nachdem Sie den Richtliniennamen kennen, verwenden Sie das Cmdlet Get-CsMobilityPolicy, um zu überprüfen, ob die betreffende Richtlinie (beispielsweise RedmondMobilityPolicy) die EnableMobility-Eigenschaft auf true festgelegt ist:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Wenn Sie eine Fehlermeldung mit Authentifizierungs Headern erhalten, bedeutet dies häufig, dass Sie kein gültiges Benutzerkonto angegeben haben. Überprüfen Sie den Benutzernamen und das Kennwort, und führen Sie den Test erneut aus. Wenn Sie davon überzeugt sind, dass das Benutzerkonto gültig ist, verwenden Sie das Cmdlet Get-CsWebServiceConfiguration, und überprüfen Sie den Wert der UseWindowsAuth-Eigenschaft. Dadurch erfahren Sie, welche Authentifizierungsmethoden in Ihrer Organisation aktiviert sind. Weitere Tipps zur Problembehandlung für den Mobilitätsdienst finden Sie im Blogbeitrag [Troubleshooting External lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>


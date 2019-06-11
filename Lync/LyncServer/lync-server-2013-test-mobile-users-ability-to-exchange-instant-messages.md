---
title: 'Lync Server 2013: Testen der Fähigkeit von mobilen Benutzern zum Austauschen von Sofortnachrichten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Testen der Fähigkeit von mobilen Benutzern zum Austauschen von Chatnachrichten in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsMcxP2PIM-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Mobilitätsdienst können Benutzer mobiler Geräte wie folgt vorgehen:

1.  Tauschen Sie Sofortnachrichten und Anwesenheitsinformationen aus.

2.  Speichern und Abrufen von Voicemail intern und nicht mit Ihrem WLAN-Anbieter.

3.  Nutzen Sie die Vorteile von lync-Server Funktionen wie Anruf über Arbeit und Einwahlkonferenzen.

Das Cmdlet Test-CsMxcP2PIM bietet eine schnelle und einfache Möglichkeit, um zu überprüfen, ob Benutzer den Mobilitätsdienst zum Austauschen von Sofortnachrichten verwenden können.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Damit dieser Test ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen. Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsMcxP2PIM aufrufen:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die beiden Testbenutzer Sofortnachrichten mithilfe des mobilitätsdiensts austauschen können, gibt Test-CsMcxP2PIM den Erfolg des Testergebnisses zurück:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:http://atl-cs-001.litwareinc.com:443/mcx

Ergebnis: Erfolg

Latenz: 00:00:00

Fehlermeldung:

Diagnose

Wenn der Test fehlschlägt, wird das Ergebnis auf Failure gesetzt, und es wird eine detaillierte Fehlermeldung und Diagnose angezeigt:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:https://atl-cs-001.litwareinc.com:443/mcx

Ergebnis: Fehler

Latenz: 00:00:00

Fehlermeldung: beim Web-Ticket-Service wurde keine Antwort empfangen.

Innere Ausnahme: die HHTP-Anforderung ist nicht autorisiert mit

Client-Aushandlungs Schema "NTLM". Die Authentifizierung

der vom Server empfangene Header lautet "Negotiate, NTLM".

Innere Ausnahme: der Remoteserver hat einen Fehler zurückgegeben:

(401) nicht autorisiert.

Diagnose

Innere Diagnose: X-MS-Server-Fqdb: ATL-CS-

001.litwareinc.com

Cache-Control: privat

Content-Type: Text/HTML; charset = UTF-8.

Server: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-powered-by: ASP.net

X-Content-Type-Optionen: nosniff

Datum: Wed, 28 May 2014 19:16:05 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsMcxP2PIM fehlschlägt, sollte der erste Schritt darin liegen, zu überprüfen, ob der Mobilitätsdienst ausgeführt wird. Dies kann mithilfe eines Webbrowsers erfolgen, um zu überprüfen, ob auf die Mobilitätsdienst-URL für Ihren lync Server-Pool zugegriffen werden kann. Mit diesem Befehl wird beispielsweise die URL für den Pool ATL-CS-001.litwareinc.com überprüft:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Wenn der Mobilitätsdienst anscheinend ausgeführt wird, überprüfen Sie, ob die beiden Testbenutzer über gültige lync Server-Konten verfügen. Sie können Kontoinformationen abrufen, indem Sie einen Befehl wie den folgenden verwenden:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder der Befehl fehlschlägt, bedeutet dies, dass der Benutzer kein gültiges lync Server-Konto hat.

Sie sollten auch sicherstellen, dass der Benutzer für Mobilität aktiviert ist. Ermitteln Sie dazu zunächst die Mobilitätsrichtlinie, die dem Konto zugewiesen ist:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Nachdem Sie den Richtliniennamen kennen, verwenden Sie das Cmdlet Get-CsMobilityPolicy, um zu überprüfen, ob die fragliche Richtlinie (beispielsweise RedmondMobilityPolicy) die EnableMobility-Eigenschaft auf true festgelegt ist:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Wenn Sie eine Fehlermeldung mit Authentifizierungs Headern erhalten, bedeutet dies häufig, dass Sie kein gültiges Benutzerkonto angegeben haben. Überprüfen Sie den Benutzernamen und das Kennwort, und versuchen Sie dann erneut, den Test zu testen. Wenn Sie davon überzeugt sind, dass das Benutzerkonto gültig ist, verwenden Sie das Cmdlet Get-CsWebServiceConfiguration, und überprüfen Sie den Wert der UseWindowsAuth-Eigenschaft. Damit erfahren Sie, welche Authentifizierungsmethoden in Ihrer Organisation aktiviert sind. Weitere Tipps zur Problembehandlung beim Mobilitätsdienst finden Sie im Blogbeitrag zur [Problembehandlung von externen lync-Mobilitäts Verbindungsproblemen Schritt-für-Schritt](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>


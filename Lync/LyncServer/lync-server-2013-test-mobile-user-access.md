---
title: 'Lync Server 2013: Testen des Zugriffs durch mobile Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f284332507d06bf9ef55abecc894b3047965472c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Testen des Zugriffs auf mobile Benutzer in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsMcxConference verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Mobilitätsdienst können Benutzer mobiler Geräte folgende Aufgaben ausführen:

1.  Exchange-Sofortnachrichten und Anwesenheitsinformationen.

2.  Speichern und Abrufen von Voicemail intern statt mit Ihrem drahtlosen Anbieter.

3.  Nutzen Sie lync Server Funktionen wie "Anruf über Arbeit" und "Einwahlkonferenzen". Das Cmdlet Test-CsMcxConference bietet eine schnelle und einfache Möglichkeit, um zu überprüfen, ob Benutzer an lync Server Konferenzen teilnehmen können, indem Sie ein mobiles Gerät verwenden.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Um diese Prüfung auszuführen, müssen Sie drei Windows PowerShell Credential-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen. Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsMcxConference wie im folgenden Beispiel gezeigt aufrufen:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die Überprüfung erfolgreich ist, wird mit Test-CsMcxConference ein Testergebnis von Success gemeldet:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:http://atl-cs-001.litwareinc.com:443/mcx

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn die Überprüfung nicht erfolgreich ist, meldet CsMcxConference ein Testergebnis des Fehlers. Dieses Testergebnis wird in der Regel von einer detaillierten Fehlermeldung und Diagnose begleitet. Zum Beispiel:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ziel-URI:https://atl-cs-001.litwareinc.com:443/mcx

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: Es wurde keine Antwort für den WebTICKET Dienst empfangen.

Innere Ausnahme: die HHTP-Anforderung ist mit dem Client nicht autorisiert

Aushandlungs Schema ' NTLM '. Der empfangene Authentifizierungsheader

auf dem Server war "aushandeln".

Innere Ausnahme: der Remoteserver hat einen Fehler zurückgegeben: (401)

Unbefugte.

Diagnose

Innere Diagnose: X-MS-Server-Fqdb: ATL-CS-001.litwareinc.com

Cache-Control: privat

Content-Type: Text/HTML; charset = UTF-8.

Server: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-powered by: ASP.net

X-Content-Type-Optionen: nosniff

Date: Mi, 28 May 2014 19:22:19 GMT

Content-length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsMcxConference fehlschlägt, sollten Sie zunächst überprüfen, ob der Mobilitätsdienst ausgeführt wird und auf den zugegriffen werden kann. Dies kann mithilfe eines Webbrowsers erfolgen, um sicherzustellen, dass auf die Mobilitätsdienst-URL für Ihren lync Server-Pool zugegriffen werden kann. Mit diesem Befehl wird beispielsweise die URL für die ATL-CS-001.litwareinc.com des Pools überprüft:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Wenn Sie auf den Mobilitätsdienst zugreifen können, sollten Sie sicherstellen, dass Ihre Testbenutzer über gültige lync Server Konten verfügen. Sie können Kontoinformationen mithilfe eines Befehls abrufen, der dem folgenden ähnelt:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Wenn die Enabled-Eigenschaft nicht gleich true ist oder wenn der Befehl fehlschlägt, bedeutet dies, dass der Benutzer über kein gültiges lync Server Konto verfügt. Sie sollten auch sicherstellen, dass jedes Benutzerkonto für Mobility aktiviert ist. Ermitteln Sie dazu zunächst die Mobilitätsrichtlinie, die dem Konto zugewiesen ist:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Nachdem Sie den Richtliniennamen kennen, verwenden Sie das Cmdlet Get-CsMobilityPolicy, um zu überprüfen, ob die betreffende Richtlinie (beispielsweise RedmondMobilityPolicy) die EnableMobility-Eigenschaft auf true festgelegt ist:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Wenn Sie beim Ausführen von Test-CsMcxConference eine Fehlermeldung "Authentifizierungsheader" erhalten, die häufig bedeutet, dass Sie kein gültiges Benutzerkonto angegeben haben, überprüfen Sie den Benutzernamen und das Kennwort, und testen Sie den Test erneut. Wenn Sie davon überzeugt sind, dass das Benutzerkonto gültig ist, verwenden Sie das Cmdlet Get-CsWebServiceConfiguration, und überprüfen Sie den Wert der UseWindowsAuth-Eigenschaft. Dadurch erfahren Sie, welche Authentifizierungsmethoden in Ihrer Organisation aktiviert sind.

Weitere Tipps zur Problembehandlung für den Mobilitätsdienst finden Sie im Blogbeitrag [Troubleshooting External lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen von Drittanbieter-Audiokonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34e55661d2d28052f7672798059d458563ab5c8d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Testen von Drittanbieter-Audiokonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-11-01_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsAudioConferencingProvider verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Bei einem Audiokonferenzanbieter handelt es sich um ein Drittanbieterunternehmen, das Konferenzdienste für Organisationen bereitstellt. Audiokonferenzanbieter bieten Benutzern u. a. die Möglichkeit, von außerhalb eines Standorts und ohne Verbindung mit dem Unternehmensnetzwerk oder dem Internet am Audioteil einer Konferenz oder Besprechung teilzunehmen. Audiokonferenzanbieter stellen oft hochwertige Dienstleistungen wie Simultanübersetzung, Transkription und operatorgestützte Livekonferenzen bereit.

Das Cmdlet **Test-CsAudioConferencingProvider** wird verwendet, um zu überprüfen, ob ein Benutzer in der Lage ist, eine Verbindung mit seinem Audiokonferenz-Anbieter herzustellen. Beachten Sie, dass dieses Cmdlet auf zwei Arten ausgeführt werden kann. Viele Administratoren verwenden die Cmdlets vom Typ "CsHealthMonitoringConfiguration", um für jeden Registrierungsstellenpool Testbenutzer einzurichten. Bei diesen Testbenutzern handelt es sich um ein Paar von Benutzerkonten, das für synthetische Transaktionen vorkonfiguriert wurde. (In der Regel handelt es sich um Testkonten und nicht um Konten, die tatsächlichen Benutzern angehören.) Wenn Testbenutzer für einen Pool konfiguriert sind, können Administratoren das **Test-CsAudioConferencingProvider-** Cmdlet für diesen Pool ausführen, ohne die Identität (und die Anmeldeinformationen für) des an dem Test beteiligten Benutzerkontos angeben zu müssen.

Alternativ können Administratoren das Cmdlet **Test-CsAudioConferencingProvider** mit einem tatsächlichen Benutzerkonto ausführen. Denken Sie beim Ausführen der Tests mit einem tatsächlichen Benutzerkonto daran, dass Sie den Anmeldenamen und das Kennwort jedes Benutzers angeben müssen.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

In Beispiel 1 wird überprüft, ob ein für den Pool ATL-CS-001.litwareinc.com definierter Testbenutzer in der Lage ist, eine Verbindung mit seinem Audiokonferenz-Anbieter herzustellen. Für diesen Befehl muss mindestens ein Testbenutzer für den Pool definiert sein. Wenn keine Testbenutzer für ATL-CS-001.litwareinc.com definiert wurden, tritt beim Befehl ein Fehler auf. Das liegt daran, dass das **Test-CsAudioConferencingProvider-** Cmdlet nicht weiß, welcher Benutzer im Test verwendet werden soll. Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den UserSipAddress-Parameter und die Anmeldeinformationen des Benutzerkontos einschließen, das der Befehl bei der Überprüfung der Verbindung mit einem Anbieter für Audiokonferenzen verwenden sollte.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers (\\litwareinc kenmyer), eine Verbindung mit seinem Anbieter für Audiokonferenzen herzustellen. Dazu wird im ersten Befehl des Beispiels das Cmdlet Get-Credential verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Ken Myers enthält. (Da der Anmeldename litwareinc\\kenmyer als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Ken Myers-Konto angeben.) Das resultierende Credentials-Objekt wird in einer Variablen namens $Credential gespeichert.

Der zweite Befehl prüft anschließend, ob dieser Benutzer eine Verbindung mit dem Audiokonferenzanbieter herstellen kann. Zur Ausführung dieser Aufgabe wird das Cmdlet Test-CsAudioConferencingProvider zusammen mit drei Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Ken Myers enthält); und UserSipAddress (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der Anbieter für Audiokonferenzen ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**

Ziel-FQDN: ATL-SQL-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn sich der angegebene Benutzer nicht anmelden oder abmelden kann, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

Ziel-FQDN: ATL-SQL-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei

nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder

Fehler bei hergestellter Verbindung, da der verbundene Host

Fehler bei der \[Antwort 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.

Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host

Fehler beim Antworten

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Diagnose

Die vorherige Ausgabe enthält beispielsweise den Hinweis "der verbundene Teilnehmer hat nicht ordnungsgemäß reagiert", der in der Regel ein Problem mit dem Edgeserver angibt.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsAudioConferencingProvider** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wie im vorherigen Beispiel gezeigt, müssen die optionalen Parameter ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Beachten Sie, dass der Test fehlschlägt, wenn der Benutzer, der mit dem Cmdlet **Test-CsAudioConferencingProvider** beschäftigt ist, keinem Anbieter für Audiokonferenzen zugewiesen wurde.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>


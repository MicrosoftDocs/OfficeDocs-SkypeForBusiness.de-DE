---
title: 'Lync Server 2013: Testen von Audiokonferenzen von Drittanbietern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Testen von Audiokonferenzen von Drittanbietern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-01_


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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAudioConferencingProvider-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Bei einem Audiokonferenzdienst handelt es sich um ein drittanbieterunternehmen, das Organisationen Konferenzdienste bereitstellt. Audiokonferenz-Anbieter ermöglichen unter anderem, dass Benutzer, die sich außerhalb des Standorts befinden und nicht mit dem Unternehmensnetzwerk oder dem Internet verbunden sind, am Audioteil einer Konferenz oder Besprechung teilnehmen können. Audiokonferenz-Anbieter bieten häufig Highend-Dienste wie Live-Übersetzungen, Transkriptionen und Live-Unterstützung für pro-Konferenz-Nutzer.

Das Cmdlet **Test-CsAudioConferencingProvider** wird verwendet, um zu überprüfen, ob ein Benutzer eine Verbindung mit seinem Audiokonferenz-Anbieter herstellen kann. Beachten Sie, dass dieses Cmdlet auf eine von zwei Arten ausgeführt werden kann. Viele Administratoren verwenden die CsHealthMonitoringConfiguration-Cmdlets, um Testbenutzer für die einzelnen registrierungspools einzurichten. Diese Testbenutzer stellen ein paar Benutzerkonten dar, die für die Verwendung mit synthetischen Transaktionen vorkonfiguriert wurden. (In der Regel handelt es sich hierbei um Testkonten und nicht um Konten, die tatsächlichen Benutzern gehören.) Wenn Testbenutzer für einen Pool konfiguriert sind, können Administratoren das Cmdlet **Test-CsAudioConferencingProvider** für diesen Pool ausführen, ohne die Identität des an dem Test beteiligten Benutzerkontos angeben zu müssen (und die Anmeldeinformationen einzugeben).

Alternativ können Administratoren das Cmdlet **Test-CsAudioConferencingProvider** unter Verwendung eines tatsächlichen Benutzerkontos ausführen. Wenn Sie den Test mit einem tatsächlichen Benutzerkonto durchführen möchten, müssen Sie den Anmeldenamen und das Kennwort für dieses Konto angeben.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Beispiel 1 überprüft, ob ein für den Pool ATL-CS-001.litwareinc.com definierter Testbenutzer in der Lage ist, eine Verbindung mit seinem Audiokonferenz-Anbieter herzustellen. Dieser Befehl setzt voraus, dass mindestens ein Testbenutzer für den Pool definiert ist. Wenn für ATL-CS-001.litwareinc.com keine Testbenutzer definiert wurden, schlägt der Befehl fehl; Das liegt daran, dass das Cmdlet **Test-CsAudioConferencingProvider** nicht weiß, welcher Benutzer im Test verwendet werden soll. Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den "usersipaddress"-Parameter und die Anmeldeinformationen des Benutzerkontos angeben, das der Befehl verwenden soll, wenn die Verbindung mit einem Audiokonferenzdienst überprüft wird.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines bestimmten Benutzers (\\"litwareinc kenmyer), eine Verbindung zu seinem Audiokonferenz-Anbieter herzustellen. Dazu verwendet der erste Befehl im Beispiel das Cmdlet "Get-Credential", um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Ken Myers enthält. (Da der Anmeldename "litwareinc\\kenmyer als Parameter enthalten ist, muss das Windows PowerShell-Dialogfeld Anmeldeinformationen anfordern nur dem Administrator das Kennwort für das Ken Myers-Konto eingeben.) Das resultierende Credentials-Objekt wird in einer Variablen mit dem Namen $Credential gespeichert.

Der zweite Befehl überprüft dann, ob dieser Benutzer eine Verbindung mit seinem Audiokonferenz-Anbieter herstellen kann. Um diese Aufgabe auszuführen, wird das Cmdlet Test-CsAudioConferencingProvider zusammen mit drei Parametern aufgerufen: TargetFqdn (dem FQDN des registrierungspools); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Ken Myers enthält); und "usersipaddress" (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der Audiokonferenz-Anbieter ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich** markiert ist:

Ziel-FQDN: ATL-SQL-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:00

Fehlermeldung:

Diagnose

Wenn sich der angegebene Benutzer nicht anmelden oder sich abmelden kann, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

Ziel-FQDN: ATL-SQL-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei

hat nach einer bestimmten Zeit nicht richtig reagiert, oder

Fehler beim Herstellen einer Verbindung, weil der verbundene Host

Fehler bei der \[Antwort 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert

Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host

hat nicht reagiert

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Diagnose

Die vorherige Ausgabe enthält beispielsweise die Notiz "die verbundene Partei hat nicht richtig reagiert", die in der Regel auf ein Problem mit dem Edgeserver hindeutet.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsAudioConferencingProvider** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wie im vorherigen Beispiel gezeigt, müssen die optionalen Parameter richtig konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Beachten Sie, dass der Test fehlschlägt, wenn dem vom **Test-CsAudioConferencingProvider-** Cmdlet verwendeten Benutzer kein Audiokonferenz-Anbieter zugewiesen wurde.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>


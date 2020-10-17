---
title: 'Lync Server 2013: Testen der Freigabe in Konferenzen'
description: 'Lync Server 2013: Testen der Freigabe in Konferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e569a97d102664b64c201af9b60061813df69ef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556241"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Testen der Freigabe in Konferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csdataconference "</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

In lync Server 2013 handelt es sich bei einer Datenkonferenz um eine Konferenz, in der kollaborative Aktivitäten wie Whiteboards oder Anmerkungen verwendet werden. Mit dem Cmdlet **Test-csdataconference "** können Sie überprüfen, ob ein Benutzer Paar an einer Datenkonferenz teilnehmen kann.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Der Befehl in Beispiel 1 prüft, ob in Pool "atl-cs-001.litwareinc.com" eine Datenkonferenz stattfinden kann. Dieser Befehl setzt voraus, dass Sie ein Testbenutzerpaar für den angegebenen Pool konfiguriert haben. Wenn keine Testbenutzer vorhanden sind, schlägt der Befehl fehl.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (litwareinc \\ Pilar und litwareinc kenmyer), sich bei \\ lync Server 2013 anzumelden und dann eine Datenkonferenz durchzuführen. Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Pilar Ackerman-Konto angeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert. Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.

Wenn die Credential-Objekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Datenkonferenz durchführen können. Zur Ausführung dieser Aufgabe wird das Cmdlet **Test-csdataconference "** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); "Sendersipaddress" (die SIP-Adresse für den ersten Testbenutzer); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); "Receiversipaddress" (die SIP-Adresse für den anderen Testbenutzer); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die Datenkonferenz ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine Datenfreigabe verwenden können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei

nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder

Fehler bei hergestellter Verbindung, da der verbundene Host

Fehler bei der Antwort \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.

Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host

Fehler beim Antworten

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061

Diagnose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csdataconference "** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Die Möglichkeit zum Durchführen einer Datenkonferenz hängt von der konferenzrichtlinie ab, die dem Benutzer zugewiesen wurde, der die Konferenz organisiert hat (im Fall des **Test-csdataconference "-** Cmdlets, also des" Absenders "). Wenn der Organisator keine kollaborativen Aktivitäten in seine Besprechung einschließen darf (Wenn beispielsweise die EnableDataCollaboration-Eigenschaft für die konferenzrichtlinie auf false festgelegt ist), tritt das **Test-csdataconference "-** Cmdlet nicht mehr auf.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>


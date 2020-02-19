---
title: 'Lync Server 2013: Testen der Anwendungsfreigabe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb9f5771651f68d36666e039a9af71436ac3635b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a>Testen der Anwendungsfreigabe in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-csasconference "verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-csasconference "** überprüft, ob ein Testbenutzer Paar an einer Onlinekonferenz teilnehmen kann, die die Anwendungsfreigabe umfasst. Hierzu registriert das Cmdlet die beiden Benutzer mit lync Server 2013 und verwendet dann eines der Benutzerkonten, um eine neue Konferenz zu erstellen, die die Freigabe von Anwendungen umfasst. Anschließend prüft das Cmdlet, ob der zweite Benutzer dieser Konferenz beitreten kann.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Der Befehl in Beispiel 1 prüft, ob in Pool "atl-cs-001.litwareinc.com" eine Konferenz zur Anwendungsfreigabe stattfinden kann. Dieser Befehl setzt voraus, dass Sie ein Testbenutzerpaar für den angegebenen Pool konfiguriert haben. Wenn keine Testbenutzer vorhanden sind, schlägt der Befehl fehl.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

In Beispiel 2 wird gestestet, ob der Join Launcher Service an einer Konferenz zur Anwendungsfreigabe in Pool "atl-cs-001.litwareinc.com" teilnehmen kann. Mit diesem Befehl wird nur der Dienst getestet, für die Ausführung des Befehls sind keine Mobilgeräte erforderlich.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (\\litwareinc Pilar und\\litwareinc kenmyer), sich bei lync Server 2013 anzumelden und dann eine Anwendungsfreigabe Konferenz durchzuführen. Dazu wird im ersten Befehl des Beispiels das Cmdlet Get-Credential verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename litwareinc\\Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Pilar Ackerman-Konto angeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert. Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.

Wenn die Credential-Objekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Anwendungsfreigabe Konferenz durchführen können. Zur Ausführung dieser Aufgabe wird das Cmdlet **Test-csasconference "** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); "Sendersipaddress" (die SIP-Adresse für den ersten Testbenutzer); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); "Receiversipaddress" (die SIP-Adresse für den anderen Testbenutzer); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die Anwendungsfreigabe ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:01

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine Anwendungen freigeben können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei

nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder

Fehler bei hergestellter Verbindung, da der verbundene Host

Fehler beim Antworten auf 10.188.116.96:5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.

Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host

Fehler beim Antworten auf 10.188.116.96:5061

Diagnose

Die vorherige Ausgabe enthält beispielsweise den Hinweis "der verbundene Teilnehmer hat nicht ordnungsgemäß reagiert", der in der Regel ein Problem mit dem Edgeserver angibt.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csasconference "** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Dieser Befehl schlägt fehl, wenn dem Testbenutzer eine konferenzrichtlinie zugewiesen wurde, die verhindert, dass die Anwendungsfreigabe verwendet wird.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-csdataconference "](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


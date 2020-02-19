---
title: 'Lync Server 2013: Testen der Benutzerverbindung mit Exchange um'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72552f56041103e381291bf13ab13283a3c47ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Testen der Benutzerverbindung mit Exchange um in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csexumconnectivity "</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-csexumconnectivity "** überprüft, ob der angegebene Benutzer eine Verbindung mit dem Microsoft Exchange Server 2013 Unified Messaging-Dienst herstellen kann. Beachten Sie, dass dieses Cmdlet nur überprüft, ob eine Verbindung mit dem Dienst hergestellt werden kann. Der Dienst wird nicht getestet. Verwenden Sie das Test-CsExUMVoiceMail-Cmdlet, um den Unified Messaging-Dienst zu testen (indem ein Cmdlet für synthetische Transaktionen ausgeführt wird, das tatsächlich eine Voicemailnachricht im Postfach eines Benutzers hinterlässt).

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Im folgenden Beispiel wird die Exchange Unified Messaging-Konnektivität für den Pool ATL-CS-001.litwareinc.com getestet. Dieser Befehl ist nur möglich, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert wurden. Wenn dies der Fall ist, wird mit dem Befehl ermittelt, ob der erste Testbenutzer eine Verbindung mit Unified Messaging herstellen kann. Wenn Testbenutzer nicht für den Pool konfiguriert wurden, tritt beim Ausführen des Befehls ein Fehler auf.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

Die im folgenden Beispiel gezeigten Befehle testen die Exchange Unified Messaging-Konnektivität für\\den Benutzer litwareinc kenmyer. Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Objekt der Befehlszeilen-Schnittstellen Anmeldeinformationen für den Benutzer litwareinc\\kenmyer zu erstellen. Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Credentials-Objekt zu erstellen und sicherzustellen, dass das **Test-csexumconnectivity "-** Cmdlet seine Überprüfung ausführen kann.

Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des\\Benutzers litwareinc kenmyer, um zu bestimmen, ob dieser Benutzer eine Verbindung mit Exchange Unified Messaging herstellen kann.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Der im nächsten Beispiel gezeigte Befehl ist eine Variation des soeben angezeigten Befehls. In diesem Fall ist der OutLoggerVariable-Parameter enthalten, um ein detailliertes Protokoll aller Schritte zu generieren, die von der **Test-csexumconnectivity "** ausgeführt werden, um den Erfolg oder Misserfolg jedes dieser Schritte cmdletand. Hierzu wird der Parameter OutLoggerVariable zusammen mit dem Parameterwert ExumText hinzugefügt. Dadurch werden ausführliche Protokollierungsinformationen in einer Variablen namens $ExumTest gespeichert. Im letzten Befehl im Beispiel wird die ToXml ()-Methode verwendet, um die Protokollinformationen in das XML-Format zu konvertieren. Diese XML-Daten werden dann mithilfe des Cmdlets Out-File in\\eine\\Datei mit dem Namen C: Logs ExumTest. XML geschrieben.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert wurde:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn der angegebene Benutzer keine Benachrichtigungen empfangen kann, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csexumconnectivity "** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Dieser Befehl schlägt fehl, wenn der Exchange Server falsch konfiguriert oder noch nicht bereitgestellt wurde.

  - Dieser Befehl schlägt fehl, wenn der Exchange Server nicht über Ihr Netzwerk erreichbar ist.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-csexumvoicemail "](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


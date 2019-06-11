---
title: 'Lync Server 2013: Testen der Anwendungsfreigabe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a>Testen der Anwendungsfreigabe in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsASConference-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsASConference** überprüft, ob ein paar Testbenutzer an einer Onlinekonferenz teilnehmen können, die die Anwendungsfreigabe umfasst. Dazu registriert das Cmdlet die beiden Benutzer mit lync Server 2013 und verwendet dann eines der Benutzerkonten, um eine neue Konferenz zu erstellen, die die Freigabe von Anwendungen umfasst. Das Cmdlet überprüft dann, ob der zweite Benutzer an dieser Konferenz teilnehmen kann.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Der in Beispiel 1 gezeigte Befehl überprüft, ob eine Anwendungsfreigabe Konferenz im Pool ATL-CS-001.litwareinc.com durchgeführt werden kann. Bei diesem Befehl wird davon ausgegangen, dass Sie ein paar Testbenutzer für den angegebenen Pool konfiguriert haben. Wenn keine solchen Testbenutzer vorhanden sind, wird der Befehl nicht ausgeführt.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

Beispiel 2 testet die Möglichkeit des Join-Startprogrammdiensts, an einer Konferenz zur Anwendungsfreigabe im Pool ATL-CS-001.litwareinc.com teilzunehmen. Beachten Sie, dass dieser Befehl nur den Dienst selbst testet; Sie benötigen keine mobilen Geräte, um den Befehl auszuführen.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines Paars von Benutzern\\("litwareinc Pilar\\und" litwareinc kenmyer), sich bei lync Server 2013 anzumelden und dann eine Konferenz zur Anwendungsfreigabe durchzuführen. Dazu wird im ersten Befehl im Beispiel das Cmdlet Get-Credential verwendet, um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename, "litwareinc\\Pilar, als Parameter hinzugefügt wurde, erfordert das Dialogfeld Windows PowerShell-Anmeldeinformationen nur, dass der Administrator das Kennwort für das Pilar Ackerman-Konto eingegeben hat.) Das resultierende Anmeldeinformationsobjekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert. Der zweite Befehl führt dieselbe Aufgabe aus, wobei dieses Mal ein Anmeldeinformationsobjekt für das Ken Myers-Konto zurückgegeben wird.

Wenn die Anmeldeinformationsobjekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Konferenz zur Anwendungsfreigabe durchführen können. Um diese Aufgabe auszuführen, wird das Cmdlet **Test-CsASConference** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (der FQDN des registrierungspools); SenderSipAddress (die SIP-Adresse des ersten Testbenutzers); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für denselben Benutzer enthält); ReceiverSipAddress (die SIP-Adresse des anderen Testbenutzers); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die Anwendungsfreigabe ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich** markiert ist:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:01

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine Anwendungen freigeben können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehlermeldung: 10060, Fehler bei einem Verbindungsversuch, weil die verbundene Partei

hat nach einer bestimmten Zeit nicht richtig reagiert, oder

Fehler beim Herstellen einer Verbindung, weil der verbundene Host

Fehler beim Antworten 10.188.116.96:5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer gewissen Zeit nicht richtig reagiert

Zeit, oder die Verbindung konnte nicht hergestellt werden, weil der verbundene Host

Fehler beim Antworten 10.188.116.96:5061

Diagnose

Die vorherige Ausgabe enthält beispielsweise die Notiz "die verbundene Partei hat nicht richtig reagiert", die in der Regel auf ein Problem mit dem Edgeserver hindeutet.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsASConference** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Dieser Befehl schlägt fehl, wenn den Testbenutzern eine konferenzrichtlinie zugewiesen wurde, die verhindert, dass Sie die Anwendungsfreigabe verwenden können.

  - Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


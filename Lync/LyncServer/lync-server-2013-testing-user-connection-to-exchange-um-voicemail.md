---
title: 'Lync Server 2013: Testen der Benutzerverbindung mit Exchange um Voicemail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f09921d62eddb1f1b426e0e3b1fc4984a0987a8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Testen der Benutzerverbindung mit Exchange um Voicemail in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsExUMVoiceMail-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet **Test-CsExUMVoiceMail** können Administratoren überprüfen, ob ein Benutzer auf den Microsoft Exchange Server 2013 Unified Messaging-Dienst zugreifen und ihn verwenden kann. Zu diesem Zweck stellt das Cmdlet eine Verbindung mit dem Unified Messaging-Dienst her und verlässt eine Voicemail im angegebenen Postfach. Dies kann eine vom System bereitgestellte Voicemail sein, oder es kann sich um eine benutzerdefinierte Nachricht handeln. WAV-Datei, die Sie selbst aufgenommen haben.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Im folgenden Beispiel wird die Exchange Unified Messaging-Voicemail-Konnektivität für den Pool ATL-CS-001.litwareinc.com getestet. Dieser Befehl funktioniert nur, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert wurden. Wenn ja, bestimmt der Befehl, ob der erste Testbenutzer Unified Messaging-Voicemail verwenden kann. Wenn Testbenutzer nicht für den Pool konfiguriert wurden, schlägt der Befehl fehl.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

Die im nächsten Beispiel gezeigten Befehle testen die Exchange Unified Messaging-Voicemail-Konnektivität für\\den Benutzer "litwareinc kenmyer. Dazu wird im ersten Befehl im Beispiel das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilenschnittstellen-Anmeldeinformationsobjekt für den Benutzer "litwareinc\\kenmyer zu erstellen. Beachten Sie, dass Sie das Kennwort für dieses Konto angeben müssen, um ein gültiges Anmeldeinformationsobjekt zu erstellen und sicherzustellen, dass das **Test-CsExUMVoiceMail-** Cmdlet seine Überprüfung ausführen kann.

Der zweite Befehl in diesem Beispiel verwendet das angegebene Credentials-Objekt ($x) und die SIP-Adresse des\\Benutzers "litwareinc kenmyer, um zu ermitteln, ob dieser Benutzer eine Verbindung mit der Exchange Unified Messaging-Voicemail herstellen kann.

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

Der im nächsten Beispiel angezeigte Befehl ist eine Variation des Befehls, die in Beispiel 1 gezeigt wird. in diesem Fall ist der OutLoggerVariable-Parameter enthalten, um ein detailliertes Protokoll aller Schritte zu generieren, die vom **Test-CsExUMVoiceMail** cmdletand den Erfolg oder Misserfolg jedes dieser Schritte durchgeführt wurden. Dazu wird der OutLoggerVariable-Parameter neben dem Parameterwert ExumText hinzugefügt. Dies bewirkt, dass detaillierte Protokollierungsinformationen in einer Variablen mit dem Namen $ExumTest gespeichert werden. Im letzten Befehl im Beispiel wird die ToXml ()-Methode verwendet, um die Protokollinformationen in das XML-Format zu konvertieren. Diese XML-Daten werden dann mit dem Cmdlet "Out-File"\\in\\eine Datei mit dem Namen C: Logs VoicemailTest. XML geschrieben.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die Exchange-Integration ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als **erfolgreich**markiert ist:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:02.9911345

Fehlermeldung:

Diagnose

Wenn der angegebene Benutzer keine Verbindung mit Voicemail herstellen kann, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte

Domänenname (FQDN). Verwenden der standardmäßigen Registrierungs Portnummer Ausnahme

System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.

am

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsExUMVoiceMail** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Dieser Befehl schlägt fehl, wenn der Exchange-Server falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


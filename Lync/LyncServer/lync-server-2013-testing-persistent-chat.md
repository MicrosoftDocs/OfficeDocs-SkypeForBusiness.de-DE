---
title: 'Lync Server 2013: Testen des beständigen Chats'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1980d66649ff465ad251d5b95a9642e5bcd43c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504072"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a>Testen des beständigen Chats in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-11-03_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-cspersistentchatmessage "</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-cspersistentchatmessage "** überprüft, ob ein paar Testbenutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können. Hierzu protokolliert das Cmdlet die beiden Benutzer in lync Server 2013, verbindet die Benutzer mit einem beständigen Chatroom, tauscht ein Nachrichtenpaar aus, verlässt dann den Chatroom und meldet die beiden Benutzer ab. Beachten Sie, dass Aufrufe dieses Cmdlets fehlschlagen, wenn Sie keine Chatrooms erstellt haben oder wenn den beiden Testbenutzerkonten keine Richtlinie für beständigen Chat zugewiesen ist, die Ihnen Zugriff auf den Dienst für beständigen Chat gewährt.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Die im folgenden Beispiel gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (litwareinc \\ Pilar und litwareinc \\ kenmyer), sich bei lync Server 2013 anzumelden und dann Nachrichten mit dem Dienst für beständigen Chat auszutauschen. Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, erfordert das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator, das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Credentials-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert. Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.

Wenn die Credential-Objekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und Nachrichten mithilfe des beständigen Chats austauschen können. Um diese Aufgabe auszuführen, wird das Cmdlet **Test-cspersistentchatmessage "** mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); "Sendersipaddress" (die SIP-Adresse für den ersten Testbenutzer); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); "Receiversipaddress" (die SIP-Adresse für den anderen Testbenutzer); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der angegebene Benutzer über eine gültige Standortrichtlinie verfügt, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert ist:

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:00

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer Nachrichten nicht mit dem Dienst für beständigen Chat austauschen können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte

Domänenname (FQDN). Verwenden der standardmäßigen Registrierungsstellen-Portnummer. Ausnahme

System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.

auf

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von cspersistentchatmessage "** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Die erforderlichen Testkonten sind möglicherweise nicht vorhanden oder wurden ordnungsgemäß erstellt.

  - Möglicherweise wurde ein Netzwerkproblem verursacht eine unerwartete Verzögerung, die den Test Zeitüberschreitung.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Grant-cspersistentchatpolicy "](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-cspersistentchatpolicy "](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Gruppe-cspersistentchatpolicy "](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


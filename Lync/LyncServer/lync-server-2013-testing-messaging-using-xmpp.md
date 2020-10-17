---
title: 'Lync Server 2013: Testen von Messaging mit xmpp'
description: 'Lync Server 2013: Testen von Messaging mit xmpp.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556301"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Testen von Messaging mithilfe von xmpp in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csxmppim "</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Extensible Messaging and Presence-Protokoll (XMPP) ist ein Standardkommunikationsprotokoll (basierend auf XML), das zum Senden von Nachrichten über das Internet verwendet wird. XMPP wurde ursprünglich Jabber genannt und wird von verschiedenen Internet-Messaging-und Kommunikationsanwendungen wie Google Talk und Facebook-Chat unterstützt. Das Cmdlet **Test-csxmppim "** überprüft, ob ein Benutzer Chatnachrichten mit einem Benutzer in einem XMPP-Netzwerk austauschen kann. Beachten Sie, dass Sie für den Erfolg dieses Tests eine gültige SIP-Adresse für den XMPP-Benutzer haben müssen und dass sich diese SIP-Adresse in einem Netzwerk befinden muss, das als zulässiger XMPP-Partner konfiguriert wurde.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Im folgenden Beispiel werden die Funktionen der XMPP-Sofortnachrichten für den Pool ATL-CS-001.litwareinc.com überprüft. Dieser Befehl ist nur möglich, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind. Wenn dies der Fall ist, wird mit dem Befehl ermittelt, ob der erste Testbenutzer eine XMPP-Sofortnachricht an einen Benutzer senden kann, der über die SIP-Adresse adelaney@contoso.com.

Wenn Testbenutzer nicht definiert sind, tritt beim Ausführen des Befehls ein Fehler auf, da er nicht weiß, welcher Benutzer sich anmelden muss. Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den UserSipAddress-Parameter und die Anmeldeinformationen des Benutzers angeben, den der Befehl beim Anmelden verwenden soll.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Die im nächsten Beispiel gezeigten Befehle testen die Fähigkeit eines bestimmten Benutzers (litwareinc \\ Pilar), sich anzumelden, um eine XMPP-Sofortnachricht an den Benutzer adelaney@contoso.com zu senden. Dazu wird im ersten Befehl des Beispiels das Get-Credential-Cmdlet verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur vom Administrator eingegeben werden, um das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.

Der zweite Befehl prüft dann, ob sich dieser Benutzer am Pool ATL-CS-001.litwareinc.com anmelden und die XMPP-Sofortnachricht senden kann. Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-csxmppim "** zusammen mit vier Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); Empfänger (die SIP-Adresse des Benutzers, an den die Nachricht adressiert wird); UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und UserSipAddress (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die XMPP-Sofortnachrichtenfunktion ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:02.5361946

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine XMPP-Sofortnachrichten verwenden können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

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

Fehler beim Antworten auf 10.188.116.96:5061

Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die

die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.

Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host

Fehler beim Antworten auf 10.188.116.96:5061

Diagnose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csxmppim "** möglicherweise fehlschlägt:

  - Ein falscher Parameterwert wurde angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.

  - Dieser Befehl schlägt fehl, wenn die XMPP-Gateway-Konfiguration falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Gruppe-csxmppgatewayconfiguration "stehen](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


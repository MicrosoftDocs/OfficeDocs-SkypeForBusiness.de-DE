---
title: 'Lync Server 2013: Testen von Nachrichten mithilfe von XMPP'
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
ms.openlocfilehash: d5a1840e344ee19114cca424822fa1df14028495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Testen von Nachrichten mithilfe von xmpp in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-03_


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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsXmppIM-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Extensible Messaging and Presence Protocol (XMPP) ist ein Standardkommunikationsprotokoll (basierend auf XML), das für das Senden von Nachrichten über das Internet verwendet wird. XMPP wurde ursprünglich Jabber genannt und wird von verschiedenen Internet-Messaging-und Kommunikationsanwendungen wie Google Talk und Facebook-Chat unterstützt. Das Cmdlet **Test-CsXmppIM** überprüft, ob ein Benutzer Sofortnachrichten mit einem Benutzer in einem XMPP-Netzwerk austauschen kann. Beachten Sie, dass Sie für diesen Test erfolgreich sein müssen, wenn Sie über eine gültige SIP-Adresse für den XMPP-Benutzer verfügen und diese SIP-Adresse in einem Netzwerk vorhanden sein muss, das als zugelassener XMPP-Partner konfiguriert wurde.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Im folgenden Beispiel werden die Funktionen des XMPP-Chats für den Pool ATL-CS-001.litwareinc.com überprüft. Dieser Befehl funktioniert nur, wenn Testbenutzer für den Pool ATL-CS-001.litwareinc.com definiert sind. Wenn ja, bestimmt der Befehl, ob der erste Testbenutzer eine XMPP-Sofortnachricht an einen Benutzer senden kann, der über die SIP-Adresse adelaney@contoso.com.

Wenn Testbenutzer nicht definiert sind, schlägt der Befehl fehl, da er nicht weiß, zu welchem Benutzer Sie sich anmelden müssen. Wenn Sie für einen Pool keine Testbenutzer definiert haben, müssen Sie den "usersipaddress"-Parameter und die Anmeldeinformationen des Benutzers einbeziehen, der beim Versuch, sich anzumelden, verwendet werden soll.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Die im nächsten Beispiel gezeigten Befehle testen die Möglichkeit eines bestimmten Benutzers ("litwareinc\\Pilar), sich anzumelden, um eine XMPP-Sofortnachricht an den Benutzer adelaney@contoso.com zu senden. Dazu verwendet der erste Befehl im Beispiel das Cmdlet "Get-Credential", um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält. (Da der Anmeldename "litwareinc\\Pilar als Parameter enthalten war, erfordert das Windows PowerShell-Dialogfeld Anmelde Informationsanforderung nur den Administrator, das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Anmeldeinformationsobjekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert.

Der zweite Befehl überprüft dann, ob sich dieser Benutzer beim Pool ATL-CS-001.litwareinc.com anmelden und die XMPP-Sofortnachricht senden kann. Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-CsXmppIm** zusammen mit vier Parametern aufgerufen: TargetFqdn (der FQDN des registrierungspools); Receiver (die SIP-Adresse des Benutzers, an den die Nachricht adressiert wird) UserCredential (das Windows PowerShell-Objekt, das die Benutzeranmeldeinformationen von Pilar Ackerman enthält); und "usersipaddress" (die SIP-Adresse, die den angegebenen Benutzeranmeldeinformationen entspricht).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn XMPP Instant Messaging ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**

Ziel-FQDN: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:02.5361946

Fehlermeldung:

Diagnose

Wenn die angegebenen Benutzer keine XMPP-Sofortnachrichten verwenden können, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

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

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsXmppIM** möglicherweise fehlschlägt:

  - Es wurde ein falscher Parameterwert angegeben. Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl. Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.

  - Dieser Befehl schlägt fehl, wenn die XMPP-Gateway-Konfiguration falsch konfiguriert oder noch nicht bereitgestellt wurde.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


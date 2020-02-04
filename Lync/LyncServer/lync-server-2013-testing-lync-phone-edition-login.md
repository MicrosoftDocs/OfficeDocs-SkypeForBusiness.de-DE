---
title: 'Lync Server 2013: Testen der lync Phone Edition-Anmeldung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bfce8b1e034fd9772e10178366b0ed524fdbd55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Testen der lync Phone Edition-Anmeldung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-05_


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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPhoneBootstrap-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsPhoneBootstrap können Administratoren überprüfen, ob ein bestimmter Benutzer – unter Verwendung der ihm zugewiesenen Telefonnummer und der ihm zugewiesenen PIN – sich über ein lync 2013 Phone Edition-kompatibles Gerät am System anmelden kann. (Für die Ausführung des Tests ist eigentlich kein Gerät erforderlich.)

Damit Test-CsPhoneBootstrap seine Prüfung durchführen kann, muss der Registrierungspool, der das getestete Benutzerkonto hostet, mithilfe von DHCP auffindbar sein. Um zu ermitteln, ob eine Registrierungsstelle auf diese Weise auffindbar ist, verwenden Sie das Cmdlet Get-CsRegistrarConfiguration, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft. Wenn diese Eigenschaft auf "false" festgelegt ist, müssen Sie "CsRegistrarConfiguration" verwenden, um den Eigenschaftswert auf "true" festzulegen und die Registrierungsstelle mithilfe von DHCP auffindbar zu machen. Dies kann auch über den Enterprise-DHCP-Server und die Konfiguration der lync Server-spezifischen Optionen erfolgen.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Damit Sie das Cmdlet Test-CsPhoneBootstrap ausführen können, müssen Sie mindestens die Telefonnummer und die persönliche Identifikationsnummer (PIN) des Clients für einen gültigen lync Server-Benutzer angeben. Dieser Befehl testet beispielsweise die Anmeldefähigkeit des Benutzers, der die Telefonnummer 12065551219 und die PIN 0712 hat:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Für eine umfassendere Überprüfung können Sie auch die SIP-Adresse des Benutzers angeben. In diesem Fall müssen die Telefonnummer, die Client-PIN und die SIP-Adresse gültig sein, damit der Test erfolgreich ist:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn der angegebene Benutzer eine Verbindung mit lync Server herstellen konnte, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als erfolgreich markiert wurde **:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.3981276

Fehler

Diagnose

Wenn der angegebene Benutzer keine Verbindung herstellen konnte, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:04.1993845

Fehler: Fehler – es wurde keine Antwort für den Web-Ticket-Dienst empfangen.

Diagnose

In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, weil der Web-Ticket Dienst nicht reagiert hat. Dies kann auf ein Problem mit dem Dienst selbst zurückzuführen sein, oder es kann daran liegen, dass die SIP-Adresse, die Telefonnummer oder die Client-PIN an Test-CsPhoneBootstrap übergeben wurde. Sie können die SIP-Adresse und Telefonnummer des Benutzers mithilfe eines Befehls wie den folgenden überprüfen:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Und Sie können überprüfen, ob der Benutzer über eine gültige Pin verfügt, indem Sie einen Befehl wie folgt verwenden:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Wenn Test-CsPhoneBootstrap fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPhoneBootstrap eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde. Hier sehen Sie beispielsweise einen Teil der Ausgabe für eine erfolglose Anmeldung, eine Sitzung, in der eine falsche PIN enthalten war:

Verwenden der PIN-Authentifizierung\\mit Telefon extern: 12065551219-PIN: 0712

Web-Ticket konnte nicht abgerufen werden

Kontroll

\-Die Webdienst-URL ist gültig, und die Webdienste funktionieren.

\-Wenn Sie die\\PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen

\-Stellen Sie bei\\Verwendung der NTLM-Kerberos-Authentifizierung sicher, dass Sie gültige Anmeldeinformationen angegeben haben.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsPhoneBootstrap möglicherweise fehlschlägt:

  - Möglicherweise haben Sie eine ungültige SIP-Adresse angegeben. Sie können überprüfen, ob eine SIP-Adresse richtig ist, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Möglicherweise haben Sie eine ungültige PIN angegeben. Obwohl Sie die PIN-Nummer des Benutzers nicht abrufen können, können Sie überprüfen, ob der Benutzer mindestens über eine PIN-Nummer verfügt, indem Sie einen ähnlichen Befehl wie den folgenden verwenden:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Möglicherweise haben Sie eine ungültige Telefonnummer angegeben. Sie können das Telefon eines Benutzers überprüfen, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Der Registrierungspool ist nicht DHCP-fähig. Wenn Sie feststellen möchten, ob Ihr Registrierungspool für DHCP aktiviert ist, führen Sie das Cmdlet "Get-CsRegistrarConfiguration" aus, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft. Beispiel:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>


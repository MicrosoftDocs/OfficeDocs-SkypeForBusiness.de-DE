---
title: 'Lync Server 2013: Testen der Anmeldung von lync Phone Edition'
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
ms.openlocfilehash: dbacccabc98829c90e01dc49099b65b829274c82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Testen von lync Phone Edition Anmeldung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-05_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-csphonebootstrap aus verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-csphonebootstrap aus können Administratoren überprüfen, ob ein bestimmter Benutzer – unter Verwendung der ihm zugewiesenen Telefonnummer und PIN – sich über ein lync 2013 Phone Edition kompatibles Gerät beim System anmelden kann. (Zum Ausführen des Tests ist tatsächlich kein Gerät erforderlich.)

Damit Test-CsPhoneBootstrap den Test durchführen kann, muss der Registrierungsstellenpool, der das zu testende Benutzerkonto hostet, mit DHCP erkannt werden. Um zu ermitteln, ob eine Registrierungsstelle auf diese Weise erkannt werden kann, verwenden Sie das Cmdlet Get-CsRegistrarConfiguration, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft. Wenn diese Eigenschaft auf false festgelegt ist, müssen Sie mit setCsRegistrarConfiguration den Eigenschaftswert auf true festlegen und die Registrierungsstelle mithilfe von DHCP auffindbar machen. Dies kann auch mithilfe des Enterprise-DHCP-Servers und der Konfiguration der lync Server spezifischen Optionen erfolgen.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Damit Sie das Cmdlet Test-csphonebootstrap aus ausführen können, müssen Sie mindestens die Telefonnummer und die persönliche Identifikationsnummer (PIN) des Clients für einen gültigen lync Server Benutzer angeben. Beispielsweise testet dieser Befehl die Anmeldefähigkeit für den Benutzer mit der Telefonnummer 12065551219 und dem PIN 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Für eine umfassendere Überprüfung können Sie auch die SIP-Adresse des Benutzers einschließen. In diesem Fall müssen die Telefonnummer, die Client-PIN und die SIP-Adresse gültig sein, damit der Test erfolgreich ausgeführt wird:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-csphonebootstrap aus](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn der angegebene Benutzer eine Verbindung mit lync Server herstellen konnte, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.3981276

Fehler

Diagnose

Wenn der angegebene Benutzer keine Verbindung herstellen konnte, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:04.1993845

Fehler: Fehler – es wurde keine Antwort für den WebTICKET Dienst empfangen.

Diagnose

Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da der webticketdienst nicht antwortete. Dies kann auf ein Problem mit dem Dienst selbst oder auf die SIP-Adresse, Telefonnummer oder Client-Pin zurückzuführen sein, die an Test-csphonebootstrap aus übergeben wurde. Sie können die SIP-Adresse und Telefonnummer des Benutzers überprüfen, indem Sie einen Befehl wie den folgenden verwenden:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

Sie können überprüfen, ob der Benutzer über eine gültige Pin verfügt, indem Sie einen Befehl wie folgt verwenden:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Wenn Test-csphonebootstrap aus fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-csphonebootstrap aus eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Hier ist beispielsweise ein Teil der Ausgabe für eine nicht erfolgreiche Anmeldung, eine Sitzung, in der eine falsche PIN enthalten war:

Verwenden der PIN-Authentifizierung\\mit Telefon-ext: 12065551219-PIN: 0712

Das Webdienst Ticket konnte nicht abgerufen werden.

Kontroll

\-Die Webdienst-URL ist gültig, und die Webdienste sind funktionsfähig.

\-Wenn Sie die\\PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen.

\-Wenn Sie NTLM\\-Kerberos-Authentifizierung verwenden, stellen Sie sicher, dass Sie gültige Anmeldeinformationen angegeben haben

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von csphonebootstrap aus möglicherweise fehlschlägt:

  - Möglicherweise haben Sie eine ungültige SIP-Adresse angegeben. Sie können überprüfen, ob eine SIP-Adresse korrekt ist, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Möglicherweise haben Sie eine ungültige PIN angegeben. Die PIN-Nummer des Benutzers kann zwar nicht abgerufen werden, aber Sie können überprüfen, ob der Benutzer mindestens über eine PIN-Nummer verfügt, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Möglicherweise haben Sie eine ungültige Telefonnummer angegeben. Sie können das Telefon eines Benutzers überprüfen, indem Sie einen Befehl wie den folgenden verwenden:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - Der registrierungsstellenpool ist nicht DHCP-fähig. Um zu ermitteln, ob Ihr registrierungsstellenpool für DHCP aktiviert ist, führen Sie das Cmdlet Get-CsRegistrarConfiguration aus, und überprüfen Sie den Wert der EnableDHCPServer-Eigenschaft. Beispiel:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>


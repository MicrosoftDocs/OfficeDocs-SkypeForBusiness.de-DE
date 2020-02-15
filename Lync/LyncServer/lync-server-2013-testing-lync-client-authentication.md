---
title: 'Lync Server 2013: Testen der lync-Client Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efc07ff877d5692c2871a8b0481233d3bd8c58b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Testen der lync-Client Authentifizierung in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsClientAuth verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsClientAuth können Sie bestimmen, ob sich ein Benutzer bei der lync Server mithilfe eines Clientzertifikats anmelden kann, indem Sie das Test-CsClientAuth-Cmdlet ausführen. Nach dem Aufruf von Test-CsClientAuth wird das Cmdlet mit dem Dienst für die Bereitstellung von Zertifikaten Kontakt aufnehmen und eine Kopie aller Clientzertifikate für den angegebenen Benutzer herunterladen. Wenn ein Clientzertifikat gefunden und heruntergeladen werden kann, versucht Test-CsClientAuth, sich mit diesem Zertifikat anzumelden. Wenn die Anmeldung erfolgreich ist, meldet sich Test-CsClientAuth ab und meldet, dass der Test erfolgreich war. Falls kein Zertifikat gefunden oder heruntergeladen werden kann oder wenn das Cmdlet sich mit dem Zertifikat nicht anmelden kann, meldet Test-CsClientAuth den Test als nicht erfolgreich.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsClientAuth wird mithilfe des Kontos eines beliebigen Benutzers ausgeführt, der für lync Server aktiviert ist. Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält. Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse hinzufügen, wenn das System Test-CsClientAuth aufruft:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsClientAuth](http://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn sich der angegebene Benutzer bei lync Server mithilfe eines Clientzertifikats anmelden kann, erhalten Sie eine ähnliche Ausgabe wie diese, wobei die Result-Eigenschaft als Success markiert wird **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn sich der angegebene Benutzer nicht anmelden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Error und Diagnostic aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:03.3645259

Fehler: das CS-Zertifikat für den angegebenen Benutzer konnte nicht heruntergeladen werden. Prüfen Sie, ob

der angegebene URI und die Anmeldeinformationen sind korrekt.

Diagnose

Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da ein gültiges Clientzertifikat für den angegebenen Benutzer nicht gefunden werden konnte. Sie können eine Liste der für einen Benutzer ausgestellten Clientzertifikate zurückgeben, indem Sie einen Befehl wie folgt ausführen:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Wenn Test-CsClientAuth fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsClientAuth eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat. Beispiel:

Versuch, ein CS-Zertifikat für den Benutzer herunterzuladen: kenmyer@litwareinc.com-Endpunkt: Step-up

Webdienst-URL:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

CS-Zertifikat konnte nicht aus dem Webdienst heruntergeladen werden.

Kontroll

\-Die Webdienst-URL ist gültig, und die Webdienste sind funktionsfähig.

\-Wenn Sie die\\\\PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen.

\-Wenn Sie NTLM\\-Kerberos-Authentifizierung verwenden, stellen Sie sicher, dass Sie gültige Anmeldeinformationen angegeben haben

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsClientAuth möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert. Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.

  - Der Testbenutzer verfügt möglicherweise nicht über ein gültiges Clientzertifikat. Sie können Informationen zu den einem Benutzer zugewiesenen Clientzertifikaten mithilfe eines Befehls wie dem folgenden zurückgeben:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>


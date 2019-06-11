---
title: 'Lync Server 2013: Testen der lync-Client Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8ea26c39582a69062526c7b4ae00343bb19482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Testen der lync-Client Authentifizierung in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsClientAuth-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsClientAuth können Sie ermitteln, ob sich ein Benutzer mit einem Clientzertifikat am lync-Server anmelden kann, indem Sie das Cmdlet Test-CsClientAuth ausführen. Nach dem Aufruf von Test-CsClientAuth wird das Cmdlet mit dem Dienst für die Zertifikatbereitstellung Kontakt aufnehmen und eine Kopie aller Clientzertifikate für den angegebenen Benutzer herunterladen. Wenn ein Clientzertifikat gefunden und heruntergeladen werden kann, versucht Test-CsClientAuth, sich mit diesem Zertifikat anzumelden. Wenn die Anmeldung erfolgreich ist, wird sich Test-CsClientAuth abmelden und melden, dass der Test erfolgreich war. Wenn ein Zertifikat nicht gefunden oder heruntergeladen werden kann oder wenn sich das Cmdlet nicht mit diesem Zertifikat anmelden kann, meldet Test-CsClientAuth, dass der Test fehlgeschlagen ist.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet Test-CsClientAuth wird mithilfe des Kontos eines beliebigen Benutzers ausgeführt, der für lync Server aktiviert ist. Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält. Sie müssen dann das Anmeldeinformationsobjekt und die SIP-Adresse einbeziehen, die dem Konto zugewiesen ist, wenn das System Test-CsClientAuth aufruft:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn sich der angegebene Benutzer mit einem Clientzertifikat bei lync Server anmelden kann, wird die Ausgabe ähnlich wie diese angezeigt, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.8630376

Fehler

Diagnose

Wenn der angegebene Benutzer sich nicht anmelden kann, wird das Ergebnis als Fehler angezeigt, und zusätzliche Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:03.3645259

Fehler: Es konnte kein CS-Zertifikat für den angegebenen Benutzer heruntergeladen werden. Überprüfen Sie, ob

der angegebene URI und die Anmeldeinformationen sind richtig.

Diagnose

In der vorherigen Ausgabe wird beispielsweise angegeben, dass der Test fehlgeschlagen ist, da für den angegebenen Benutzer kein gültiges Clientzertifikat gefunden werden konnte. Sie können eine Liste der für einen Benutzer ausgestellten Clientzertifikate zurückgeben, indem Sie einen Befehl wie folgt ausführen:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Wenn Test-CsClientAuth fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Wenn der Verbose-Parameter enthalten ist, gibt Test-CsClientAuth eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde. Beispiel:

Versuch, ein CS-Zertifikat für Benutzer herunterzuladen: kenmyer@litwareinc.com-Endpunkt: Schritt-Nr

Webdienst-URL:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

CS-Zertifikat konnte nicht vom Webdienst heruntergeladen werden.

Kontroll

\-Die Webdienst-URL ist gültig, und die Webdienste funktionieren.

\-Wenn Sie die\\\\PhoneNo-Pin zur Authentifizierung verwenden, stellen Sie sicher, dass Sie mit dem Benutzer-URI übereinstimmen

\-Stellen Sie bei\\Verwendung der NTLM-Kerberos-Authentifizierung sicher, dass Sie gültige Anmeldeinformationen angegeben haben.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsClientAuth möglicherweise fehlschlägt:

  - Sie haben ein ungültiges Benutzerkonto angegeben. Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert. Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.

  - Der Testbenutzer verfügt möglicherweise nicht über ein gültiges Clientzertifikat. Sie können Informationen zu den einem Benutzer zugewiesenen Clientzertifikaten mithilfe eines Befehls zurückgeben, der dem folgenden ähnelt:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>


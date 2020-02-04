---
title: 'Lync Server 2013: Testen der Möglichkeit zum Herstellen einer Verbindung mit einer Verbunddomäne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Testen der Möglichkeit zum Herstellen einer Verbindung mit einer Verbunddomäne von lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsFederatedPartner-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Test-CsFederatedPartner überprüft Ihre Möglichkeiten zum Herstellen einer Verbindung mit der Domäne eines Verbundpartners. Um die Konnektivität zu einer Domäne zu überprüfen, muss diese Domäne in der Sammlung zulässiger (Verbund-) Domänen aufgelistet sein. Mit diesem Befehl können Sie eine Liste der Domänen in der Liste der zulässigen Domänen abrufen:

    Get-CsAllowedDomain

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet Test-FederatedPartner erfordert zwei Informationen: den FQDN des Edge-Servers und den FQDN des Partner Partners. Dieser Befehl testet beispielsweise die Möglichkeit zum Herstellen einer Verbindung mit dem Domänen contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Mit diesem Befehl können Sie die Verbindungen zu allen Domänen testen, die sich derzeit in der Liste der zulässigen Domänen befinden:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die angegebene Domäne kontaktiert werden kann, erhalten Sie eine ähnliche Ausgabe, wobei die Ergebniseigenschaft als erfolgreich markiert wurde **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:00

Fehler

Diagnose

Wenn die angegebene Domäne nicht kontaktiert werden kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Latenz: 00:00:00

Fehler: 504, Server Timeout

Diagnose: errorCode = 2, Quelle = ATL-CS-001. "litwareinc. com, Reason = siehe

Antwortcode und Ursachen Ausdruck.

Microsoft. RTC. Signalisierungs-DiagnosticHeader

In der vorherigen Ausgabe wird beispielsweise angegeben, dass der Test aufgrund eines Servertimeout Fehlers fehlgeschlagen ist. Dies weist in der Regel auf Netzwerkverbindungsprobleme oder Probleme beim Kontaktieren des Edge-Servers hin.

Wenn Test-CsFederatedPartner fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsFederatedPartner möglicherweise fehlschlägt:

  - Der Edgeserver steht möglicherweise nicht zur Verfügung. Mit diesem Befehl können Sie die FQDNs ihrer Edgeserver verwenden:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Anschließend können Sie die einzelnen Edgeserver anpingen, um zu überprüfen, ob Sie über das Netzwerk darauf zugreifen können. Beispiel:
    
        ping atl-edge-001.litwareinc.com

  - Die angegebene Domäne ist in der Liste zugelassene Domänen möglicherweise nicht aufgeführt. Verwenden Sie diesen Befehl, um die Domänen zu überprüfen, die der Liste zugelassene Domänen hinzugefügt wurden:
    
        Get-CsAllowedDomain
    
    Wenn Sie eine Liste der Domänen sehen möchten, mit denen die Kommunikation von Benutzern blockiert wurde, verwenden Sie diesen Befehl:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>


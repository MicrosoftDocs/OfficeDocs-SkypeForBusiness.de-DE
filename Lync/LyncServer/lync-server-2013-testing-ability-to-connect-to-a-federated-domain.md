---
title: 'Lync Server 2013: Testen der Fähigkeit, eine Verbindung mit einer Verbunddomäne herzustellen'
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
ms.openlocfilehash: a565c09e09e10eeb160b1d0514c89499427d1283
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532922"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Testen der Fähigkeit zum Herstellen einer Verbindung mit einer Verbunddomäne von lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsFederatedPartner-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Test-CsFederatedPartner überprüft die Fähigkeit, eine Verbindung mit der Domäne eines Verbundpartners herzustellen. Um die Verbindung mit einer Domäne zu überprüfen, muss diese Domäne in der Auflistung zulässiger (Verbund-) Domänen aufgeführt sein. Mit dem folgenden Befehl können Sie eine Liste der Domänen in der Liste der zugelassenen Domänen abrufen:

    Get-CsAllowedDomain

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-FederatedPartner-Cmdlet erfordert zwei Informationen: den FQDN des Edgeserver und den FQDN des Partnerverbund Partners. Beispielsweise testet dieser Befehl die Möglichkeit, eine Verbindung mit der Domäne contoso.com herzustellen:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Mit diesem Befehl können Sie die Verbindungen zu allen Domänen testen, die sich derzeit in der Liste der zugelassenen Domänen befinden:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Sie eine Verbindung mit der angegebenen Domäne aufnehmen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:00

Fehler

Diagnose

Wenn die angegebene Domäne nicht kontaktiert werden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Fehler

Wartezeit: 00:00:00

Fehler: 504, Server Timeout

Diagnose: errorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = siehe

Antwortcode und Grund Phrase.

Microsoft. RTC. Signaling. DiagnosticHeader

Die vorherige Ausgabe besagt beispielsweise, dass der Test aufgrund eines Servertimeout Fehlers fehlgeschlagen ist. Dies deutet normalerweise auf Netzwerkverbindungsprobleme oder Probleme beim Kontakt mit dem Edgeserver hin.

Wenn Test-CsFederatedPartner fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsFederatedPartner Fehler auftreten können:

  - Die Edgeserver ist möglicherweise nicht verfügbar. Sie können die FQDNs ihrer Edgeserver mithilfe dieses Befehls ausführen:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Anschließend können Sie jeden Edgeserver anpingen, um sicherzustellen, dass der Zugriff über das Netzwerk möglich ist. Zum Beispiel:
    
        ping atl-edge-001.litwareinc.com

  - Die angegebene Domäne ist möglicherweise nicht in der Liste der zugelassenen Domänen aufgeführt. Verwenden Sie den folgenden Befehl, um die Domänen zu überprüfen, die der Liste der zugelassenen Domänen hinzugefügt wurden:
    
        Get-CsAllowedDomain
    
    Wenn Sie eine Liste der Domänen anzeigen möchten, mit denen Benutzer die Kommunikation mit blockiert haben, verwenden Sie den folgenden Befehl:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Testen von Civic addresses anhand der Master Street Address Guide
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a55593bee333d03c71522bdd0a39cc91cb60882
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Testen von Civic addresses anhand der Master Street Address Guide in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsRegistration verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet Test-CsLisCivicAddress wird verwendet, um Speicherorte zu überprüfen, die ihrer Standortinformationsdienst Datenbank (LIS) hinzugefügt wurden. Das Cmdlet funktioniert durch Vergleichen von Speicherorten mit den in der Master Street Address Guide (MSAG), die zu Ihrem E9-1-1-Netzwerk Routing Anbieter gehört gefunden. Wenn Sie nicht über einen Netzwerkrouting Anbieter verfügen oder der Anbieter nicht erreicht werden kann, treten bei Ihren Tests Fehler auf.

Wenn Sie den optionalen Switch-Parameter UpdateValidationStatus zu Ihrem Befehl hinzufügen, wird die entsprechende MSAGValid-Datenbankeigenschaft für jede Adresse, die den Test übergibt, auf true festgelegt.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Cmdlet Test-CsLisCivicAddress kann verwendet werden, um einzelne Adressen zu testen oder um mehrere Adressen zu testen. Beispielsweise testet dieser Befehl eine einzelne Adresse, die sich in Redmond, WA befindet:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

Im Vergleich dazu testet dieser Befehl alle Adressen, die sich derzeit in ihrer LIS-Datenbank befinden:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Mit Test-CsLisCivicAddress wird der Erfolg oder Fehler für die angegebenen Adressen zurückgemeldet. Ein Adress Test schlägt fehl, wenn die Adresse nicht gefunden wird oder wenn der Dienstanbieter nicht kontaktiert werden kann.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsLisCivicAddress möglicherweise fehlschlägt:

  - Der LIS-Dienstanbieter ist möglicherweise nicht verfügbar. Sie können die URL Ihres LIS-Dienstanbieters abrufen, indem Sie das Cmdlet Get-CsLisConfiguration ausführen:
    
        Get-CsLisConfiguration 
    
    Anschließend können Sie eine Ping-URL durchführen, um zu überprüfen, ob der Dienstanbieter verfügbar ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>


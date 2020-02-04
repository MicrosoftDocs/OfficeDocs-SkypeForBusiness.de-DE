---
title: 'Lync Server 2013: Testen des PSTN-Anruf Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Testen des PSTN-Anruf Routings in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-11-01_


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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsInterTrunkRouting-</strong> Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-CsInterTrunkRouting** überprüft, ob Anrufe von einem SIP an einen anderen weitergeleitet werden können. Dazu erhält das Cmdlet eine Telefonnummer und eine trunk-Konfiguration. In **Test-CsInterTrunkRouting** werden dann übereinstimmende Routen und übereinstimmende PSTN-Verwendungen für die angegebene Nummer zurückgemeldet. Beachten Sie, dass Anrufe nur zwischen Trunks geroutet werden können, wenn die Trunks ein Zahlenmuster aufweisen, das der angegebenen Telefonnummer entspricht, und nur, wenn die Trunks mindestens eine PSTN-Nutzung aufweisen.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Die folgenden Befehle geben die übereinstimmenden Routen und die übereinstimmenden Telefonverwendungen zurück, mit denen Benutzer die Telefonnummer 1-206-555-1219 mit den trunk-Konfigurationseinstellungen für die Website "Redmond" anrufen können.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Anrufe von einem SIP an einen anderen weitergeleitet werden können, erhalten Sie eine ähnliche Ausgabe wie die folgende:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Wenn der Test nicht erfolgreich war, erhalten Sie eine ähnliche Ausgabe wie die folgende:

Test-CsInterTrunkRouting: die Argument Transformation für Parameter kann nicht verarbeitet werden

'TrunkConfiguration'. Ungültiger TrunkConfigurationsetting (Parameter). Angeben eines

gültige Einstellung (Parameter), und versuchen Sie es dann erneut.

Zeile: 1 Zeichen: 79

\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsInterTrunkRouting** möglicherweise fehlschlägt:

  - Sie haben ungültige Parameter angegeben. Der trunk ist möglicherweise noch nicht richtig konfiguriert, und die angegebene Ziel Nummer ist möglicherweise falsch oder ungültig.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


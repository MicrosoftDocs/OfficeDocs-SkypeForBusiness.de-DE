---
title: 'Lync Server 2013: Testen des Routings von PSTN-Telefon anrufen'
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
ms.openlocfilehash: 8b831aef01d80a0d68a0eea06f429502026b7ccb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Testen der PSTN-Anrufweiterleitung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-11-01_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-csintertrunkrouting "</strong> verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Das Cmdlet **Test-csintertrunkrouting "** überprüft, ob Anrufe von einem SIP an einen anderen weitergeleitet werden können. Hierzu erhält das Cmdlet eine Telefonnummer und eine trunkkonfiguration. In **Test-csintertrunkrouting "** werden dann übereinstimmende Routen und übereinstimmende PSTN-Verwendungen für die angegebene Nummer zurückgemeldet. Beachten Sie, dass Anrufe nur dann zwischen Trunks geroutet werden können, wenn die Trunks über ein Nummernmuster verfügen, das mit der angegebenen Telefonnummer übereinstimmt, und nur dann, wenn die Trunks mindestens eine PSTN-Nutzung aufweisen.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Die unten gezeigten Befehle geben die übereinstimmenden Routen und übereinstimmenden Telefonverwendungen zurück, mit denen Benutzer die Telefonnummer 1-206-555-1219 mithilfe der trunkkonfigurationseinstellungen für den Standort "Redmond" anrufen können.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Anrufe von einem SIP an einen anderen weitergeleitet werden können, erhalten Sie eine ähnliche Ausgabe wie die folgende:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Wenn der Test nicht erfolgreich war, erhalten Sie eine ähnliche Ausgabe wie die folgende:

Test-csintertrunkrouting ": Argument Transformation für Parameter kann nicht verarbeitet werden

"TrunkConfiguration". Ungültiger TrunkConfigurationsetting (-Parameter). Geben Sie einen

gültige Einstellung (Parameter), und versuchen Sie es dann erneut.

In der Reihe: 1 Char: 79

\+Test-csintertrunkrouting "-TargetNumber" Tel: + 12065551219 "

\-TrunkConfiguration $t...

\+

~~

\+CategoryInfo: InvalidData: (:) \[Test-csintertrunkrouting "\], par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

TC. Management. Voice. Cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csintertrunkrouting "** möglicherweise fehlschlägt:

  - Sie haben ungültige Parameter angegeben. Der trunk ist möglicherweise noch nicht ordnungsgemäß konfiguriert, und die angegebene Ziel Nummer ist möglicherweise falsch oder ungültig.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-cstrunk "](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


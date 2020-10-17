---
title: 'Lync Server 2013: Testen der Telefonnummer für eine VoIP-Route'
description: 'Lync Server 2013: Testen Sie die Telefonnummer anhand einer VoIP-Route.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563391"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Testen der Telefonnummer für eine VoIP-Route in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Überprüfungszeitplan</p></td>
<td><p>Monatlich</p></td>
</tr>
<tr class="even">
<td><p>Test Tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Erforderliche Berechtigungen</p></td>
<td><p>Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</p>
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceRoute-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

VoIP-Routen arbeiten zusammen mit VoIP-Richtlinien, um Enterprise-VoIP-Anrufe an das PSTN-Netzwerk weiterleiten zu können. Jede VoIP-Route enthält einen regulären Ausdruck (ein Nummernmuster), mit dem die Telefonnummern identifiziert werden, die über eine bestimmte VoIP-Route weitergeleitet werden: die Route kann alle Telefonnummern verarbeiten, die diesem regulären Ausdruck entsprechen. Beispielsweise kann eine VoIP-Route einen regulären Ausdruck haben, der es ermöglicht, eine beliebige 10-stellige Zahl zu verarbeiten. Das bedeutet, dass die Route eine Telefonnummer wie die folgende verarbeiten kann:

  - 2065551219

Die Route kann keine der folgenden zwei Zahlen verarbeiten, von denen keine 10 Ziffern enthält:

  - 5551219

  - 12065551219

Das Test-CsVoiceRoute-Cmdlet überprüft, ob eine bestimmte VoIP-Route eine angegebene Telefonnummer weiterleiten kann.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Die Überprüfung der Fähigkeit einer VoIP-Route zum Weiterleiten einer bestimmten Telefonnummer ist ein zweistufiger Prozess. Zunächst müssen Sie das Get-CsVoiceRoute-Cmdlet verwenden, um eine Instanz dieser VoIP-Route zurückzugeben, und anschließend müssen Sie das Test-CsVoiceRoute-Cmdlet verwenden, um zu überprüfen, ob diese Route die Zieltelefonnummer verarbeiten kann. Mit diesem Befehl wird beispielsweise überprüft, ob die RedmondVoiceRoute-VoIP-Route die Telefonnummer 2065551219 weiterleiten kann:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Beachten Sie, dass die Telefonnummer so eingegeben werden sollte, wie Sie davon ausgehen, dass die Benutzer diese Nummer wählen. Wenn Sie beispielsweise nicht davon ausgehen, dass Benutzer beim wählen die Landes-und Ortsvorwahl einbeziehen möchten, verwenden Sie eine ähnliche Syntax wie die folgende:

`-TargetNumber "5551219"`

In diesem Fall hinterlässt die Ziel Nummer sowohl die Ländervorwahl als auch die Vorwahl.

Verwenden Sie eine Syntax wie die folgende, um einen einzelnen Befehl zum Testen aller VoIP-Routen für eine angegebene Ziel Nummer zu verwenden:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn die VoIP-Route die Zieltelefonnummer weiterleiten kann, gibt das Test-CsVoiceRoute-Cmdlet nur den Wert true zurück:

MatchesPattern

\--------------

Richtig

Das bedeutet, dass die Route Nummern ähnlich wie die Zielrufnummer verarbeiten kann. Wenn die VoIP-Route die Ziel Nummer nicht verarbeiten kann, gibt Test-CsVoiceRoute den Wert false zurück:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Beim Testen von VoIP-Routen ist "Fehler" ein relativer Ausdruck. In diesem Fall bedeutet dies nicht, dass die Route irgendwie "kaputt" ist, sondern bedeutet nur, dass die Zielrufnummer nicht von der Route verarbeitet werden kann. Dies kann daran liegen, dass die VoIP-Route falsch konfiguriert wurde. Dies kann auch bedeuten, dass die Route nie mit diesem Muster Zahlen verarbeiten sollte. Wenn Sie beispielsweise keine Anrufe an andere Länder über eine bestimmte Route weiterleiten möchten, kann diese Route so konfiguriert werden, dass alle Telefonnummern abgelehnt werden, die eine Ländervorwahl enthalten. Wenn Test-CsVoiceRoute false zurückgibt, wenn Sie erwartet haben, dass true zurückgegeben wird, überprüfen Sie, ob Sie die Ziel Nummer richtig eingegeben haben. Wenn Sie dies getan haben, verwenden Sie einen Befehl wie den folgenden, um die für die Route konfigurierte NumberPattern anzuzeigen:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


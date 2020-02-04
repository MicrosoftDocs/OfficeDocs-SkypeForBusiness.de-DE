---
title: 'Lync Server 2013: Testen einer Telefonnummer mit einer VoIP-Route'
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
ms.openlocfilehash: 5d4105b54c7d5b745efddeeb961960c402aaa349
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Testen einer Telefonnummer für eine VoIP-Route in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-20_


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
<td><p>Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</p>
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceRoute-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

VoIP-Routen arbeiten zusammen mit VoIP-Richtlinien, um Enterprise-Sprachanrufe an das PSTN-Netzwerk weiterzuleiten. Jede VoIP-Route enthält einen regulären Ausdruck (ein Zahlenmuster), der die Telefonnummern identifiziert, die über eine bestimmte VoIP-Route weitergeleitet werden: die Route kann alle Telefonnummern behandeln, die diesem regulären Ausdruck entsprechen. Beispielsweise kann eine VoIP-Route einen regulären Ausdruck aufweisen, der es ermöglicht, eine beliebige 10-stellige Zahl zu verarbeiten. Das bedeutet, dass die Route eine Telefonnummer wie die folgende behandeln kann:

  - 2065551219

Die Route kann keine der beiden folgenden Zahlen behandeln, von denen keine 10 Ziffern umfasst:

  - 5551219

  - 12065551219

Das Cmdlet Test-CsVoiceRoute überprüft, ob eine bestimmte VoIP-Route eine bestimmte Telefonnummer weiterleiten kann.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Die Überprüfung, ob eine VoIP-Route eine bestimmte Telefonnummer weiterleiten kann, ist ein zweistufiger Prozess. Zunächst müssen Sie das Cmdlet Get-CsVoiceRoute verwenden, um eine Instanz dieser VoIP-Route zurückzugeben, und dann müssen Sie das Test-CsVoiceRoute-Cmdlet verwenden, um die Fähigkeit dieser Route zur Behandlung der Zieltelefonnummer zu überprüfen. Mit diesem Befehl wird beispielsweise überprüft, ob die RedmondVoiceRoute-VoIP-Route die Telefonnummer 2065551219 weiterleiten kann:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Beachten Sie, dass die Telefonnummer so eingegeben werden sollte, wie Sie erwarten, dass die Benutzer diese Nummer wählen. Wenn Sie beispielsweise nicht davon ausgehen, dass Benutzer beim wählen die Landes-und Ortsvorwahl einbeziehen, verwenden Sie die folgende Syntax:

`-TargetNumber "5551219"`

In diesem Fall hinterlässt die Ziel Nummer sowohl die Landesvorwahl als auch die Ortsvorwahl.

Wenn Sie mit einem einzelnen Befehl alle VoIP-Routen für eine angegebene Zielrufnummer testen möchten, verwenden Sie die folgende Syntax:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn die VoIP-Route die Zieltelefonnummer weiterleiten kann, gibt das Cmdlet "Test-CsVoiceRoute" nur den Wert "true" zurück:

MatchesPattern

\--------------

Wahr

Das bedeutet, dass die Route Zahlen ähnlich wie die Ziel Nummer verarbeiten kann. Wenn die VoIP-Route die Ziel Nummer nicht verarbeiten kann, gibt Test-CsVoiceRoute den Wert false zurück:

MatchesPattern

\--------------

Falsch

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Beim Testen von VoIP-Routen ist "Fehler" ein relativer Ausdruck. In diesem Fall bedeutet dies nicht, dass die Route irgendwie "kaputt" ist, sondern bedeutet nur, dass die Route die Ziel Nummer nicht verarbeiten kann. Dies kann daran liegen, dass die VoIP-Route falsch konfiguriert wurde. Es könnte auch bedeuten, dass die Route nie dazu bestimmt war, Zahlen unter Verwendung dieses Musters zu verarbeiten. Wenn Sie beispielsweise keine Anrufe an andere Länder über eine bestimmte Route weiterleiten möchten, kann die Route so konfiguriert werden, dass alle Telefonnummern, die eine Landesvorwahl enthalten, abgelehnt werden. Wenn Test-CsVoiceRoute false zurückgibt, wenn Sie erwartet haben, dass true zurückgegeben wird, überprüfen Sie, ob Sie die Ziel Nummer korrekt eingegeben haben. Wenn ja, verwenden Sie einen ähnlichen Befehl, um die für die Route konfigurierte NumberPattern anzuzeigen:

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


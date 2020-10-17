---
title: 'Lync Server 2013: Überprüfen der trunkkonfiguration anhand einer Telefonnummer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 881e161a01b589db2db172cb5115858b522d262b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526232"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Überprüfen der trunkkonfiguration anhand einer Telefonnummer in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsTrunkConfiguration-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

SIP-Trunks verbinden das lync Server interne Enterprise-VoIP-Netzwerk mit einem der folgenden:

  - Das Telefon Festnetz (Public Switched Telephone Network, PSTN).

  - Eine Nebenstellenanlage (IP-Public Branch Exchange, PBX).

  - Einen Session Border Controller (SBC).

Das Test-CsTrunkConfiguration-Cmdlet überprüft, ob eine Telefonnummer (wie von einem Benutzer gewählt) in das E. 164-Netzwerk konvertiert und über einen bestimmten SIP-Trunk weitergeleitet werden kann.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Zum Ausführen des Test-CsTrunkConfiguration-Cmdlets müssen Sie zunächst das Get-CsTrunkConfiguration-Cmdlet verwenden, um eine Instanz Ihrer SIP-Trunk-Konfigurationseinstellungen abzurufen. Diese Instanz wird dann an Test-CsTrunkConfiguration umgeleitet:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Das Durchführen von Test-CsTrunkConfiguration ohne vorherige Ausführung Get-CsTrunkConfiguration funktioniert nicht. Beispielsweise schlägt dieser Befehl fehl, ohne dass Daten zurückgegeben werden:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Wenn Sie über mehrere Sammlungen von SIP-Trunk-Konfigurationseinstellungen verfügen, können Sie einen Befehl wie den folgenden verwenden, um gleichzeitig jede Sammlung anhand derselben Telefonnummer zu testen:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Test-CsTrunkConfiguration einen Anruf an die gewählte Nummer senden können, dann wird die übersetzte Telefonnummer (im E. 164-Format) und die für die Übersetzung dieser Telefonnummer verwendete Regel auf dem Bildschirm angezeigt:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 Global/Redmond

Wenn der Test fehlschlägt, gibt Test-CsTrunkConfiguration leere Eigenschaftswerte zurück:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn Test-CsTrunkConfiguration keine Übereinstimmung zurückgibt, die in der Regel bedeutet, dass die trunkkonfigurationseinstellungen, die getestet werden, keine Übersetzungsregel für ausgehende Rufnummern haben, die die gewählte Nummer in das E. 164-Format konvertieren kann. Wenn Sie die Übersetzungsregeln abrufen möchten, die einer Auflistung von trunkkonfigurationseinstellungen zugewiesen sind, können Sie eine ähnliche Syntax wie die folgende verwenden:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Dadurch werden für jede Übersetzungsregel ähnliche Informationen zurückgegeben:

Beschreibung: Telefonnummern ohne Landesvorwahl oder Vorwahl.

Muster: ^ \\ + ( \\ d \* ) $

`Translation : $1`

Name: NoAreaCode

An diesem Punkt überprüfen Sie den Wert der Pattern-Eigenschaft (bei der es sich um eine [reguläre Ausdrucks](https://go.microsoft.com/fwlink/?linkid=400464) Zeichenfolge handelt), um festzustellen, ob eine der Übersetzungsregeln für die Verarbeitung der gewählten Nummer konfiguriert ist. Wenn dies nicht der Fall ist, müssen Sie entweder eine der vorhandenen Regeln ändern ("CsOutboundTranslationRule") oder das Cmdlet "New-CsOutboundTranslationRule" verwenden, um der Auflistung eine neue Regel hinzuzufügen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


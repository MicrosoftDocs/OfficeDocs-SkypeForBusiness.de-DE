---
title: 'Lync Server 2013: Testen der VoIP-Konfiguration'
description: 'Lync Server 2013: Testen Sie die VoIP-Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cc05286e5f534b4d469ef561d9ce009367e15be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557071"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a>Testen der VoIP-Konfiguration in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceTestConfiguration-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Lync Server enthält mehrere Windows PowerShell-Cmdlets (wie Test-CsVoiceRoute und Test-CsVoicePolicy, Test-CsTrunkConfiguration), mit denen Sie sicherstellen können, dass die einzelnen Teile Ihrer Enterprise-VoIP-Infrastruktur – VoIP-Routen, VoIP-Richtlinien und SIP-Trunks – ordnungsgemäß funktionieren.

Während es bei Enterprise-VoIP wichtig ist, dass alle einzelnen Teile funktionieren: Es ist möglich, eine gültige VoIP-Route, eine gültige VoIP-Richtlinie und einen gültigen SIP-Trunk zu haben, aber Benutzer können weiterhin keine Telefonanrufe tätigen oder empfangen. Aus diesem Grund bietet lync Server auch die Möglichkeit, Sprachtest Konfigurationen zu erstellen. Sprachtest Konfigurationen stellen gängige Enterprise-VoIP-Szenarien dar: Sie können beispielsweise eine VoIP-Route, eine VoIP-Richtlinie und einen Wählplan angeben und dann überprüfen, ob diese einzelnen Elemente zusammenarbeiten können, um den Telefondienst bereitzustellen. Darüber hinaus können Sie Ihre Erwartungen in einem bestimmten Szenario überprüfen. Nehmen wir beispielsweise an, dass Sie davon ausgehen, dass die Kombination aus Wähleinstellungen und VoIP-Richtlinie B dazu führen würde, dass Anrufe über die VoIP-Route C weitergeleitet würden. Sie können die VoIP-Route C als ExpectedRoute eingeben. Wenn Sie den Test ausführen, wenn die VoIP-Route C nicht verwendet wird, wird der Test als fehlgeschlagen markiert.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Bevor Sie VoIP-Konfigurations Sammlungen mit Windows PowerShell testen, müssen Sie zuerst das Get-CsVoiceTestConfiguration-Cmdlet verwenden, um eine Instanz dieser Konfigurationseinstellungen abzurufen. Diese Instanz muss dann an das Test-csvoicetestconfiguration getestet weitergeleitet werden. Zum Beispiel:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verwenden Sie den folgenden Befehl, um alle Konfigurationseinstellungen für die VoIP-Tests gleichzeitig zu überprüfen:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Das Test-CsVoiceTestConfiguration-Cmdlet meldet, ob ein Test fehlgeschlagen oder erfolgreich war, und stellt zusätzliche Informationen zu jedem erfolgreichen Test bereit, beispielsweise die Übersetzungsregel, die VoIP-Route und die PSTN-Verwendung, die zum Abschließen der Aufgabe verwendet werden:

Ergebnis: Success

TranslatedNumber: + 15551234

MatchingRule: Description =; Muster = ^ ( \\ d {4} ) $; Übersetzung = + 1 \\ d; Name = Test; IsInternalExtension = false

FirstMatchingRoute: Site: Redmond

MatchingUsage: lokal

Wenn der Test fehlschlägt, wird das Ergebnis als Fehler gemeldet:

Ergebnis: Fail

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Da Tests für die Sprachtest Konfiguration verschiedene Elemente – einschließlich VoIP-Richtlinien, Wähleinstellungen, VoIP-Routen usw. – testen, gibt es verschiedene Faktoren, die zu einem fehlgeschlagenen Test führen können. Wenn ein Test fehlschlägt, sollte der erste Schritt darin liegen, die Konfigurationseinstellungen selbst mithilfe des Get-CsVoiceTestConfiguration-Cmdlets zu überprüfen:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Wenn die Einstellungen scheinbar ordnungsgemäß konfiguriert sind, führen Sie den Test erneut aus, während Sie den Verbose-Parameter einschließen:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Der Parameter Verbose stellt eine schrittweise Anleitung für jede von Test-CsVoiceTestConfiguration durchgeführte Aktion bereit, wie in diesem Beispiel gezeigt:

Ausführlich: Wähleinstellungen werden geladen: "Global"

Verbose: Laden der VoIP-Richtlinie: "" redmonddialplan ""

Dieses Schritt-für-Schritt-Konto kann einen nützlichen Anhaltspunkt dafür liefern, wo der Test tatsächlich fehlgeschlagen ist. Wenn dies nicht der Fall ist, können Sie dann andere Windows PowerShell-Cmdlets (wie Test-CsVoicePolicy) verwenden und methodisch beginnen, die einzelnen Komponenten zu überprüfen, die in den Konfigurationseinstellungen für den VoIP-Test enthalten sind.

Beachten Sie außerdem, dass es möglich ist, dass ein Test einen Anruf weiterleitet und dennoch als Fehler gekennzeichnet wird. Dies kann vorkommen, wenn Sie Werte für ExpectedRoute, ExpectedTranslatedNumber und ExpectedUsage eingeben und diese Erwartungen nicht erfüllt werden. Nehmen wir beispielsweise an, dass Sie die VoIP-Route C als erwartete VoIP-Route eingeben, aber der Test schließt den Anruf tatsächlich mithilfe der VoIP-Route D ab. In diesem Fall wird der Test als fehlgeschlagen markiert, da die erwartete VoIP-Route nicht verwendet wurde. Wenn ein Test fehlschlägt, können Sie die Werte für ExpectedRoute, ExpectedTranslatedNumber und ExpectedUsage entfernen und dann den Test erneut ausführen. Das hilft Ihnen zu ermitteln, ob der Fehler aufgetreten ist, weil der Anruf nicht abgeschlossen werden konnte oder weil Sie eine Sache erwarten und tatsächlich eine andere erhalten haben.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-csvoicetestconfiguration getestet](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen der Sprachkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Testen der Sprachkonfiguration in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsVoiceTestConfiguration-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Lync Server umfasst mehrere Windows PowerShell-Cmdlets (wie Test-CsVoiceRoute und Test-CsVoicePolicy, Test-CsTrunkConfiguration), mit denen Sie überprüfen können, ob die einzelnen Teile Ihrer Enterprise-VoIP-Infrastruktur – VoIP-Routen, VoIP Richtlinien, SIP-Stämme, funktionieren wie erwartet.

Während es bei Enterprise-VoIP wichtig ist, dass alle einzelnen Teile funktionieren: Es ist möglich, eine gültige VoIP-Route, eine gültige VoIP-Richtlinie und einen gültigen SIP-Stamm zu haben, aber die Benutzer können dennoch keine Telefonanrufe tätigen oder empfangen. Aus diesem Grund bietet lync Server auch die Möglichkeit, Sprachtest Konfigurationen zu erstellen. Sprachtest Konfigurationen stellen allgemeine Enterprise-VoIP-Szenarien dar: Sie können beispielsweise eine VoIP-Route, eine VoIP-Richtlinie und einen Wählplan angeben und dann überprüfen, ob diese einzelnen Elemente in der Lage sind, zusammenzuarbeiten, um einen Telefondienst bereitzustellen. Darüber hinaus können Sie Ihre Erwartungen in einem bestimmten Szenario überprüfen. Angenommen, Sie gehen davon aus, dass die Kombination aus Wählplan A und VoIP-Richtlinie B dazu führen würde, dass Anrufe über die VoIP-Route C weitergeleitet werden. Sie können die sprach Route C als ExpectedRoute eingeben. Wenn Sie den Test ausführen und die VoIP-Route C nicht verwendet wird, wird der Test als fehlerhaft markiert.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Bevor Sie sprach Konfigurations Sammlungen mithilfe von Windows PowerShell testen, müssen Sie zuerst das Cmdlet Get-CsVoiceTestConfiguration verwenden, um eine Instanz dieser Konfigurationseinstellungen abzurufen. Diese Instanz muss dann an den Test-CsVoiceTestConfiguration umgeleitet werden. Beispiel:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verwenden Sie stattdessen diesen Befehl, um alle Konfigurationseinstellungen für den Sprachtest gleichzeitig zu überprüfen:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Das Cmdlet Test-CsVoiceTestConfiguration meldet, ob ein Test fehlgeschlagen oder erfolgreich war, und bietet zusätzliche Informationen zu jedem erfolgreichen Test, wie etwa die Übersetzungsregel, die VoIP-Route und die PSTN-Nutzung, die zum Ausführen der Aufgabe verwendet wird:

Ergebnis: Erfolg

TranslatedNumber: + 15551234

MatchingRule: Description =; Muster = ^ (\\d{4}) $; Übersetzung = +\\1 d; Name = Test; IsInternalExtension = falsch

FirstMatchingRoute: Website: Redmond

MatchingUsage: lokal

Wenn der Test fehlschlägt, wird das Ergebnis als Fehler gemeldet:

Ergebnis: Fehler

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Da die Tests für die Sprachtest Konfiguration verschiedene Elemente – einschließlich VoIP-Richtlinien, Wählpläne, VoIP-Routen usw. – testen, gibt es verschiedene Faktoren, die zu einem fehlgeschlagenen Test führen können. Wenn ein Test fehlschlägt, sollte der erste Schritt darin liegen, die Konfigurationseinstellungen mithilfe des Cmdlets Get-CsVoiceTestConfiguration selbst zu überprüfen:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Wenn die Einstellungen anscheinend richtig konfiguriert sind, führen Sie den Test erneut aus, während Sie den Verbose-Parameter einbeziehen:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Der Verbose-Parameter stellt eine Schritt-für-Schritt-Konto für jede Aktion bereit, die von Test-CsVoiceTestConfiguration ausgeführt wird, wie in diesem Beispiel gezeigt:

Ausführlich: Wähleinstellungen werden geladen: "Global"

Verbose: Laden der VoIP-Richtlinie: "redmonddialplan" "

Dieses Schritt-für-Schritt-Konto bietet möglicherweise einen nützlichen Anhaltspunkt dafür, wo der Test tatsächlich fehlgeschlagen ist. Wenn dies nicht der Fall ist, können Sie dann andere Windows PowerShell-Cmdlets verwenden (beispielsweise Test-CsVoicePolicy) und mit der Überprüfung der einzelnen Komponenten, die in den Einstellungen für die sprach Test Konfiguration enthalten sind, methodisch beginnen.

Beachten Sie außerdem, dass es möglich ist, dass ein Test einen Anruf weiterleiten kann und dennoch als Fehler gekennzeichnet ist. Dies kann auftreten, wenn Sie Werte für ExpectedRoute, ExpectedTranslatedNumber und ExpectedUsage eingeben und diese Erwartungen nicht erfüllt werden. Nehmen wir beispielsweise an, dass Sie die VoIP-Route C als Ihre erwartete VoIP-Route eingeben, der Test aber den Anruf tatsächlich mit der VoIP-Route D abgeschlossen hat. In diesem Fall wird der Test als fehlerhaft markiert, weil die erwartete VoIP-Route nicht verwendet wurde. Wenn ein Test fehlschlägt, entfernen Sie möglicherweise die Werte für ExpectedRoute, ExpectedTranslatedNumber und ExpectedUsage, und führen Sie dann den Test erneut aus. Damit können Sie feststellen, ob es sich um einen Fehler handelt, weil der Anruf nicht abgeschlossen werden konnte, oder weil Sie eine Aufgabe erwarten, die Sie tatsächlich erhalten haben.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


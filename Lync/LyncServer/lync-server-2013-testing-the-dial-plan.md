---
title: 'Lync Server 2013: Testen des Wählplans'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Testen des Wählplans in lync Server 2013

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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsDialPlan-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Cmdlet Test-CsDialPlan können Sie die Ergebnisse der Anwendung eines Wählplans auf eine bestimmte Telefonnummer sehen. Wählpläne liefern Informationen, wie beispielsweise die Anwendung von Normalisierungsregeln, die erforderlich sind, damit Enterprise-VoIP-Benutzer Telefonanrufe tätigen können. Mit einer gewählten Nummer und einem Wählplan wird mit diesem Cmdlet überprüft, welche Normalisierungsregel innerhalb des Wählplans angewendet wird und welche übersetzte Nummer verwendet wird.

Sie können dieses Cmdlet verwenden, um Probleme bei der Übersetzung von Zahlen zu beheben oder um zu überprüfen, wie Regeln für bestimmte Zahlen angewendet werden.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Das Cmdlet Test-CsDialPlan erfordert zwei Aufgaben. Zunächst müssen Sie eine Instanz des Wählplans abrufen, der getestet wird. Dies kann mit dem Cmdlet Get-CsDialPlan erfolgen. Als nächstes müssen Sie die Telefonnummer angeben, die normalisiert werden soll. Das für die Telefonnummer verwendete Format sollte mit der Nummer übereinstimmen, die von einem Benutzer gewählt/eingegeben wurde. Mit diesem Befehl wird beispielsweise eine Instanz des Wählplans, redmonddialplan ", abgerufen, und es wird überprüft, ob die Telefonnummer 12065551219 normalisiert werden kann:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Wenn Sie über eine Normalisierungsregel verfügen, die die Landesvorwahl (in diesem Beispiel 1) und die Ortsvorwahl (206) automatisch hinzufügt, sollten Sie die Telefonnummer 5551219 wie folgt überprüfen:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Test-CsDialPlan unterscheidet sich von vielen der lync Server Test-Cmdlets, da Sie nur indirekt angibt, ob ein Test erfolgreich war oder fehlgeschlagen ist. Bei Verwendung von Test-CsDialPlan erhalten Sie keine ähnliche Ausgabe wie diese, wobei das Ergebnis deutlich gekennzeichnet ist:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:06.8630376

Fehler

Diagnose

Wenn Test-CsDialPlan erfolgreich ist, erhalten Sie stattdessen Informationen zur Normalisierungsregel, die die angegebene Telefonnummer erfolgreich übersetzen und verwenden konnte:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Muster = ^ (\\d (11)) $; Übersetzung = + $1;

Name = Präfix alle; IsInternalExtension = falsch

Wenn Test-CsDialPlan fehlschlägt (das heißt, wenn der Wählplan nicht über eine Normalisierungsregel verfügt, die die angegebene Telefonnummer übersetzen kann), erhalten Sie einfach die "leere" Ausgabe wie folgt:

TranslatedNumber :

MatchingRule

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Nachfolgend finden Sie einige häufige Gründe, warum Test-CsDialPlan möglicherweise fehlschlägt:

  - Möglicherweise haben Sie bei der Angabe der Telefonnummer ein falsches Format verwendet. Zu den Wählplänen gehören Normalisierungsregeln, mit denen lync Server die von einem Benutzer gewählten oder eingegebenen Telefonnummern übersetzen kann. Daher sollten ihre Wähleinstellungen die Normalisierungsregeln aufweisen, die den Zahlen entsprechen, die Benutzer wahrscheinlich wählen. Wenn Benutzer beispielsweise die Landesvorwahl, Ortsvorwahl und dann die Telefonnummer selbst wählen, bedeutet dies, dass Ihr Wählplan über eine Normalisierungsregel zur Behandlung von Telefonnummern wie diesen verfügt:
    
    12065551219
    
    Wenn Sie jedoch eine falsche Telefonnummer eingeben (beispielsweise, indem Sie die letzte Ziffer verlassen), schlägt die Test-CsDialPlan fehl. Das liegt nicht daran, dass die Wähleinstellungen fehlerhaft sind, sondern weil Sie eine Telefonnummer eingegeben haben, als nicht interpretiert werden kann.

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen der Wähleinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c758f2f16d59db92841a5e7ef727a41cee8a8d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530442"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Testen der Wähleinstellungen in lync Server 2013

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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsDialPlan-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Mit dem Test-CsDialPlan-Cmdlet können Sie die Ergebnisse der Anwendung einer Wähleinstellungen auf eine bestimmte Telefonnummer anzeigen. Wählpläne bieten Informationen, beispielsweise zum Anwenden von Normalisierungsregeln, die erforderlich sind, um Enterprise-VoIP-Benutzern das tätigen von Telefon anrufen zu ermöglichen. Bei einer gewählten Nummer und einem Wählplan überprüft dieses Cmdlet, welche Normalisierungsregel innerhalb des Wählplans angewendet wird und welche übersetzte Nummer verwendet wird.

Sie können dieses Cmdlet verwenden, um Probleme bei der Übersetzung von Nummern zu beheben oder um zu überprüfen, wie Regeln für bestimmte Nummern angewendet werden.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Das Test-CsDialPlan-Cmdlet erfordert zwei Schritte. Zunächst müssen Sie eine Instanz der zu testenden Wähleinstellungen abrufen. Dies kann mithilfe des Get-CsDialPlan-Cmdlets erfolgen. Zweitens müssen Sie die Telefonnummer angeben, die normalisiert werden muss. Das für die Telefonnummer verwendete Format sollte mit der Nummer übereinstimmen, die von einem Benutzer gewählt/eingegeben wird. Mit diesem Befehl wird beispielsweise eine Instanz des Wählplans, "redmonddialplan", abgerufen, und es wird überprüft, ob die Telefonnummer 12065551219 normalisiert werden kann:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Wenn Sie eine Normalisierungsregel haben, die den Landescode automatisch hinzufügt (in diesem Beispiel 1) und die Vorwahl (206), können Sie die Telefonnummer 5551219 wie folgt überprüfen:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Test-CsDialPlan unterscheidet sich von vielen der lync Server Test-Cmdlets, da Sie nur indirekt angibt, ob ein Test erfolgreich war oder fehlgeschlagen ist. Wenn Sie Test-CsDialPlan verwenden, erhalten Sie keine ähnliche Ausgabe wie diese, sodass das Ergebnis eindeutig gekennzeichnet ist:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:06.8630376

Fehler

Diagnose

Wenn Test-CsDialPlan erfolgreich ist, erhalten Sie stattdessen Informationen zur Normalisierungsregel, mit der die angegebene Telefonnummer erfolgreich übersetzt und verwendet werden konnte:

TranslatedNumber: + 12065551219

MatchingRule: Description =; Pattern = ^ ( \\ d (11)) $; Übersetzung = + $1;

Name = alle Präfixe; IsInternalExtension = false

Wenn Test-CsDialPlan fehlschlägt (das heißt, wenn der Wählplan keine Normalisierungsregel aufweist, die die angegebene Telefonnummer übersetzen kann), erhalten Sie nur die "leere" Ausgabe wie folgt:

TranslatedNumber :

MatchingRule

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsDialPlan Fehler auftreten können:

  - Bei der Angabe der Telefonnummer haben Sie möglicherweise ein falsches Format verwendet. Zu den Wählplänen gehören Normalisierungsregeln, mit denen lync Server die von einem Benutzer gewählten oder eingegebenen Telefonnummern übersetzen können. Daher sollten ihre Wähleinstellungen Normalisierungsregeln aufweisen, die mit den Nummern übereinstimmen, die Benutzer wahrscheinlich wählen müssen. Wenn Benutzer beispielsweise die Ländervorwahl, die Vorwahl und dann die Telefonnummer selbst wählen, bedeutet dies, dass Ihr Wählplan über eine Normalisierungsregel zur Behandlung von Telefonnummern verfügt:
    
    12065551219
    
    Wenn Sie jedoch eine falsche Telefonnummer eingeben (beispielsweise die letzte Ziffer weglassen), tritt bei Test-CsDialPlan ein Fehler auf. Dies liegt nicht daran, dass die Wähleinstellungen fehlerhaft sind, sondern weil Sie eine Telefonnummer eingegeben haben, die nicht interpretiert werden kann.

</div>

</div>

<span> </span>

</div>

</div>

</div>


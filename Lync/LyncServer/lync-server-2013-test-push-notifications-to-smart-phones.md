---
title: 'Lync Server 2013: Test Push Notifications to Smart Phones'
description: 'Lync Server 2013: Test Push Notifications to Smart Phones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b92ef444a5331c9a673fd2db506631554e96eea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550841"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Testen von Push-Benachrichtigungen an Smartphones in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-03-15_


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
<p>Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsMcxPushNotification-Cmdlets verfügt. Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Der Push Notification Service (Apple Push Notification Service und Microsoft Push Notification Service) kann Benachrichtigungen zu Ereignissen wie neuen Sofortnachrichten oder neuen Voicemails an mobile Geräte wie iPhones und Windows phones senden, selbst wenn der lync-Client auf diesen Geräten derzeit angehalten ist oder im Hintergrund ausgeführt wird. Der Push Notification-Dienst ist ein Cloud-basierter Dienst, der auf Microsoft-Servern läuft. Um die Vorteile von Push-Benachrichtigungen nutzen zu können, müssen Sie in der Lage sein, eine Verbindung mit der Push Notification Clearing House herzustellen und diese zu authentifizieren. Mit dem Test-CsMcxPushNotification-Cmdlet können Administratoren überprüfen, ob Push-Benachrichtigungsanforderungen über den Edgeserver an das Clearing House für die Push-Benachrichtigung weitergeleitet werden können.

</div>

<div>

## <a name="running-the-test"></a>Durchführen des Tests

Um den Push-Benachrichtigungsdienst zu testen, rufen Sie das Cmdlet Test-CsMcxPushNotification auf. Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen Ihres Edge-Servers angeben:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Bestimmen des Erfolgs oder Fehlers

Wenn Test-CsMcxPushNotification erfolgreich ist, gibt das Cmdlet das Testergebnis Success zurück:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Success

Wartezeit: 00:00:00

Fehler

Diagnose

Wenn Test-CsMcxPushNotification keine Verbindung mit dem Push Notification-Clearing House herstellen kann, gibt das Cmdlet in der Regel kein Testergebnis des Fehlers zurück. Stattdessen wird der Befehl normalerweise vollständig fehl. Zum Beispiel:

Test-CsMcxPushNotification: eine 504-Antwort (Server Timeout) wurde aus dem Netzwerk empfangen, und der Vorgang ist fehlgeschlagen. Weitere Informationen finden Sie in den Ausnahmedetails.

In der Reihe: 1 Char: 27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , FailureResponseException

\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn der Push-Benachrichtigungsdienst fehlschlägt, gibt es normalerweise Probleme mit der Kommunikation mit Ihrem Edgeserver oder Probleme mit der Kommunikation mit dem Push Notification Clearing House. Wenn beim Ausführen von Test-CsMcxPushNotification Probleme auftreten, sollten Sie zunächst überprüfen, ob der Edgeserver ordnungsgemäß funktioniert. Eine Möglichkeit hierfür ist die Verwendung des Test-CsAVEdgeConnectivity-Cmdlets:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Mit dieser Überprüfung wird überprüft, ob ein angegebener Benutzer eine Verbindung mit dem Edgeserver herstellen kann.

Wenn der Edgeserver anscheinend ordnungsgemäß funktioniert, bedeutet dies häufig, dass Sie keine Verbindung mit dem Push Notification Clearing House herstellen können. Dies wiederum bedeutet normalerweise, dass Sie den Clearing House-URI entweder nicht ordnungsgemäß konfiguriert haben oder dass Sie keinen DNS-SRV-Eintrag haben, der auf diese URL verweist. Sie können überprüfen, ob der URI auf den korrekten Wert (SIP:Push@Push.lync.com) festgelegt ist, indem Sie den folgenden Befehl ausführen:

    Get-CsMcxConfiguration

Wenn die PushNotificationProxyUri-Eigenschaft auf einen anderen Wert als SIP:Push@Push.lync.com festgelegt ist, können Sie dieses Problem mithilfe des Set-McxConfiguration-Cmdlets korrigieren. Mit diesem Befehl wird beispielsweise der URI in Ihrer Organisation ordnungsgemäß festgelegt:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) ".

Wenn der URI ordnungsgemäß konfiguriert ist, sollten Sie im nächsten Schritt überprüfen, ob Sie über einen DNS-SRV-Eintrag verfügen, der in Ihre SIP-Domäne und ihren Edgeserver aufgelöst wird. Weitere Informationen zum Konfigurieren dieser Einträge finden Sie im Hilfethema DNS Requirements for Mobility. Beachten Sie, dass die folgende Fehlermeldung in der Regel ein Problem mit DNS-Einträgen angibt:

Eine 504-Antwort (Server Timeout) wurde aus dem Netzwerk empfangen, und der Vorgang ist fehlgeschlagen. Weitere Informationen finden Sie in den Ausnahmedetails.

Es ist auch möglich, dass Test-CsMcxConfiguration mit dieser Fehlermeldung fehlschlägt:

Test-CsMcxPushNotification: die Push-Benachrichtigungsanforderung wurde abgelehnt.

In der Reihe: 1 Char: 27

\+ Test-CsMcxPushNotification \<\<\<\<

\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , SyntheticTransactionException

\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

Die Meldung "Push Notification Request wurde abgelehnt" tritt normalerweise auf, wenn Sie die URL-Filterung aktiviert haben und die http:-und https:-Präfixe blockieren. Sie können bestimmen, welche Präfixe blockiert werden, indem Sie einen Befehl wie den folgenden verwenden:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Wenn http: oder https: in den Ergebnissen angezeigt wird, müssen Sie Sie aus der Liste der blockierten Präfixe entfernen, damit Push-Benachrichtigungen funktionieren. Dies kann mithilfe von Befehlen wie den folgenden erfolgen:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)".

</div>

</div>

<span> </span>

</div>

</div>

</div>


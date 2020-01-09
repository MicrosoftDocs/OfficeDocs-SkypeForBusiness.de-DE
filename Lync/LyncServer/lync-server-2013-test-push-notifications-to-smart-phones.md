---
title: 'Lync Server 2013: Testen von Push-Benachrichtigungen an Smartphones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Testen von Push-Benachrichtigungen an Smartphones in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-03-15_


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
<p>Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsMcxPushNotification-Cmdlets verfügt. Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Beschreibung

Der Push-Benachrichtigungsdienst (Apple Push Notification Service und Microsoft Push Notification Service) kann Benachrichtigungen zu Ereignissen wie neuen Sofortnachrichten oder neuen Voicemails an mobile Geräte wie iPhones und Windows phones senden, selbst wenn der lync-Client auf diesen Geräten ist zurzeit angehalten oder wird im Hintergrund ausgeführt. Der Push-Benachrichtigungsdienst ist ein Cloud-basierter Dienst, der auf Microsoft-Servern ausgeführt wird. Um die Vorteile von Push-Benachrichtigungen nutzen zu können, müssen Sie in der Lage sein, eine Verbindung mit der Push Notification Clearingstelle herzustellen und von ihr authentifiziert zu werden. Das Cmdlet Test-CsMcxPushNotification ermöglicht Administratoren, zu überprüfen, ob Push-Benachrichtigungsanforderungen über den Edgeserver an das "Push Notification Clearing House" weitergeleitet werden können.

</div>

<div>

## <a name="running-the-test"></a>Ausführen des Tests

Um den Push-Benachrichtigungsdienst zu testen, rufen Sie das Cmdlet Test-CsMcxPushNotification auf. Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen Ihres Edge-Servers angeben:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Ermitteln von Erfolg oder Misserfolg

Wenn Test-CsMcxPushNotification erfolgreich ist, gibt das Cmdlet den Erfolg des Testergebnisses zurück:

TargetFqdn: ATL-CS-001.litwareinc.com

Ergebnis: Erfolg

Latenz: 00:00:00

Fehler

Diagnose

Wenn Test-CsMcxPushNotification keine Verbindung mit dem Schiebe Benachrichtigungs-Clearing House herstellen kann, gibt das Cmdlet in der Regel kein Test Ergebnis des Fehlers zurück. Stattdessen wird der Befehl in der Regel vollständig fehlschlagen. Beispiel:

Test-CsMcxPushNotification: eine 504-Antwort (Server Timeout) wurde vom Netzwerk empfangen, und der Vorgang konnte nicht ausgeführt werden. Weitere Informationen finden Sie in den Ausnahmedetails.

Zeile: 1 Zeichen: 27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Gründe, warum der Test fehlgeschlagen ist

Wenn der Push-Benachrichtigungsdienst fehlschlägt, der in der Regel auf Probleme bei der Kommunikation mit Ihrem Edgeserver oder auf Probleme bei der Kommunikation mit dem Clearing House für die Push-Benachrichtigung hinweist. Wenn beim Ausführen von Test-CsMcxPushNotification Probleme auftreten, sollten Sie zunächst überprüfen, ob der Edgeserver ordnungsgemäß funktioniert. Eine Möglichkeit besteht darin, das Cmdlet Test-CsAVEdgeConnectivity zu verwenden:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Mit dieser Prüfung wird überprüft, ob ein angegebener Benutzer eine Verbindung mit dem Edgeserver herstellen kann.

Wenn der Edgeserver anscheinend ordnungsgemäß funktioniert, bedeutet dies häufig, dass Sie keine Verbindung mit der Push Notification Clearing House herstellen können. Das bedeutet wiederum in der Regel, dass Sie den Clearing House-URI entweder nicht richtig konfiguriert haben oder dass Sie keinen DNS-SRV-Eintrag haben, der auf diese URL verweist. Sie können überprüfen, ob der URI auf den richtigen Wert (SIP:Push@Push.lync.com) festgesetzt ist, indem Sie folgenden Befehl ausführen:

    Get-CsMcxConfiguration

Wenn die PushNotificationProxyUri-Eigenschaft auf einen anderen Wert als SIP:Push@Push.lync.com festgesetzt ist, können Sie dieses Problem mit dem Cmdlet "Satz-McxConfiguration" beheben. Mit diesem Befehl wird beispielsweise der URI in Ihrer Organisation richtig festgelegt:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) ".

Wenn der URI richtig konfiguriert ist, sollten Sie im nächsten Schritt überprüfen, ob ein DNS-SRV-Eintrag vorhanden ist, der in Ihre SIP-Domäne und Ihren Edge-Server aufgelöst wird. Weitere Informationen zum Konfigurieren dieser Einträge finden Sie im Hilfethema DNS-Anforderungen für Mobilität. Beachten Sie, dass die folgende Fehlermeldung in der Regel auf ein Problem mit DNS-Einträgen hinweist:

Eine 504-Antwort (Server Timeout) wurde vom Netzwerk empfangen, und der Vorgang konnte nicht ausgeführt werden. Weitere Informationen finden Sie in den Ausnahmedetails.

Es ist auch möglich, dass Test-CsMcxConfiguration mit dieser Fehlermeldung fehlschlägt:

Test-CsMcxPushNotification: die Push-Benachrichtigungsanforderung wurde abgelehnt.

Zeile: 1 Zeichen: 27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

Die Meldung "Push-Benachrichtigungsanforderung wurde abgelehnt" tritt in der Regel auf, wenn Sie die URL-Filterung aktiviert haben und die Präfixe http: und https: blockieren. Sie können bestimmen, welche Präfixe blockiert werden, indem Sie einen Befehl wie den folgenden verwenden:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Wenn "http:" oder "https:" in den Ergebnissen angezeigt wird, müssen Sie Sie aus der Liste der blockierten Präfixe entfernen, damit Push-Benachrichtigungen funktionieren. Dies kann mithilfe von Befehlen wie den folgenden erfolgen:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)".

</div>

</div>

<span> </span>

</div>

</div>

</div>


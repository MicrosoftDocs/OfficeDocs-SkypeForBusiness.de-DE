---
title: 'Lync Server 2013: Test Push Notifications to Smart Phones'
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
ms.openlocfilehash: 858c1ad3ad5776453a4a48505672c69083de1cc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="e6505-102">Testen von Push-Benachrichtigungen an Smartphones in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6505-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6505-103">_**Letztes Änderungsstand des Themas:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="e6505-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6505-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="e6505-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e6505-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="e6505-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6505-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="e6505-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e6505-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6505-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6505-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e6505-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e6505-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="e6505-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e6505-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsMcxPushNotification verfügt.</span><span class="sxs-lookup"><span data-stu-id="e6505-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="e6505-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="e6505-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e6505-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6505-112">Description</span></span>

<span data-ttu-id="e6505-113">Der Push Notification Service (Apple Push Notification Service und Microsoft Push Notification Service) kann Benachrichtigungen zu Ereignissen wie neuen Sofortnachrichten oder neuen Voicemails an mobile Geräte wie iPhones und Windows phones senden, selbst wenn der lync-Client auf diesen Geräten ist derzeit angehalten oder wird im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e6505-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="e6505-114">Der Push Notification-Dienst ist ein Cloud-basierter Dienst, der auf Microsoft-Servern läuft.</span><span class="sxs-lookup"><span data-stu-id="e6505-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="e6505-115">Um die Vorteile von Push-Benachrichtigungen nutzen zu können, müssen Sie in der Lage sein, eine Verbindung mit der Push Notification Clearing House herzustellen und diese zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6505-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="e6505-116">Mit dem Cmdlet Test-CsMcxPushNotification können Administratoren überprüfen, ob Push-Benachrichtigungsanforderungen über den Edgeserver an das Clearing House für die Push-Benachrichtigung weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="e6505-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e6505-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="e6505-117">Running the test</span></span>

<span data-ttu-id="e6505-118">Um den Push-Benachrichtigungsdienst zu testen, rufen Sie das Cmdlet Test-CsMcxPushNotification auf.</span><span class="sxs-lookup"><span data-stu-id="e6505-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="e6505-119">Stellen Sie sicher, dass Sie den vollqualifizierten Domänennamen Ihres Edge-Servers angeben:</span><span class="sxs-lookup"><span data-stu-id="e6505-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="e6505-120">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="e6505-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e6505-121">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="e6505-121">Determining success or failure</span></span>

<span data-ttu-id="e6505-122">Wenn die Test-CsMcxPushNotification erfolgreich ist, gibt das Cmdlet das Testergebnis Success zurück:</span><span class="sxs-lookup"><span data-stu-id="e6505-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="e6505-123">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e6505-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e6505-124">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="e6505-124">Result : Success</span></span>

<span data-ttu-id="e6505-125">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e6505-125">Latency : 00:00:00</span></span>

<span data-ttu-id="e6505-126">Fehler</span><span class="sxs-lookup"><span data-stu-id="e6505-126">Error :</span></span>

<span data-ttu-id="e6505-127">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e6505-127">Diagnosis :</span></span>

<span data-ttu-id="e6505-128">Wenn Test-CsMcxPushNotification keine Verbindung mit dem Push Notification-Clearing House herstellen kann, gibt das Cmdlet in der Regel kein Test Ergebnis des Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="e6505-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="e6505-129">Stattdessen wird der Befehl normalerweise vollständig fehl.</span><span class="sxs-lookup"><span data-stu-id="e6505-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="e6505-130">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e6505-130">For example:</span></span>

<span data-ttu-id="e6505-131">Test-CsMcxPushNotification: eine 504-Antwort (Server Timeout) wurde aus dem Netzwerk empfangen, und der Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="e6505-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="e6505-132">Weitere Informationen finden Sie in den Ausnahmedetails.</span><span class="sxs-lookup"><span data-stu-id="e6505-132">See the exception details for more information.</span></span>

<span data-ttu-id="e6505-133">In der Reihe: 1 Char: 27</span><span class="sxs-lookup"><span data-stu-id="e6505-133">At line:1 char:27</span></span>

<span data-ttu-id="e6505-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="e6505-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="e6505-135">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="e6505-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="e6505-136">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="e6505-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e6505-137">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="e6505-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="e6505-138">Wenn der Push-Benachrichtigungsdienst fehlschlägt, gibt es normalerweise Probleme mit der Kommunikation mit Ihrem Edgeserver oder Probleme mit der Kommunikation mit dem Push Notification Clearing House.</span><span class="sxs-lookup"><span data-stu-id="e6505-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="e6505-139">Wenn beim Ausführen von Test-CsMcxPushNotification Probleme auftreten, sollten Sie zunächst überprüfen, ob der Edgeserver ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e6505-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="e6505-140">Eine Möglichkeit hierfür ist die Verwendung des Test-csavedgeconnectivity "-Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e6505-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e6505-141">Mit dieser Überprüfung wird überprüft, ob ein angegebener Benutzer eine Verbindung mit dem Edgeserver herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e6505-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="e6505-142">Wenn der Edgeserver anscheinend ordnungsgemäß funktioniert, bedeutet dies häufig, dass Sie keine Verbindung mit dem Push Notification Clearing House herstellen können.</span><span class="sxs-lookup"><span data-stu-id="e6505-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="e6505-143">Dies wiederum bedeutet normalerweise, dass Sie den Clearing House-URI entweder nicht ordnungsgemäß konfiguriert haben oder dass Sie keinen DNS-SRV-Eintrag haben, der auf diese URL verweist.</span><span class="sxs-lookup"><span data-stu-id="e6505-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="e6505-144">Sie können überprüfen, ob der URI auf den korrekten Wert (SIP:Push@Push.lync.com) festgelegt ist, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="e6505-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="e6505-145">Wenn die PushNotificationProxyUri-Eigenschaft auf einen anderen Wert als SIP:Push@Push.lync.com festgelegt ist, können Sie dieses Problem mithilfe des Cmdlets "setMcxConfiguration" beheben.</span><span class="sxs-lookup"><span data-stu-id="e6505-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="e6505-146">Mit diesem Befehl wird beispielsweise der URI in Ihrer Organisation ordnungsgemäß festgelegt:</span><span class="sxs-lookup"><span data-stu-id="e6505-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="e6505-147">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="e6505-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="e6505-148">Wenn der URI ordnungsgemäß konfiguriert ist, sollten Sie im nächsten Schritt überprüfen, ob Sie über einen DNS-SRV-Eintrag verfügen, der in Ihre SIP-Domäne und ihren Edgeserver aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e6505-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="e6505-149">Weitere Informationen zum Konfigurieren dieser Einträge finden Sie im Hilfethema DNS Requirements for Mobility.</span><span class="sxs-lookup"><span data-stu-id="e6505-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="e6505-150">Beachten Sie, dass die folgende Fehlermeldung in der Regel ein Problem mit DNS-Einträgen angibt:</span><span class="sxs-lookup"><span data-stu-id="e6505-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="e6505-151">Eine 504-Antwort (Server Timeout) wurde aus dem Netzwerk empfangen, und der Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="e6505-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="e6505-152">Weitere Informationen finden Sie in den Ausnahmedetails.</span><span class="sxs-lookup"><span data-stu-id="e6505-152">See the exception details for more information.</span></span>

<span data-ttu-id="e6505-153">Es ist auch möglich, dass Test-CsMcxConfiguration mit dieser Fehlermeldung fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="e6505-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="e6505-154">Test-CsMcxPushNotification: die Push-Benachrichtigungsanforderung wurde abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="e6505-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="e6505-155">In der Reihe: 1 Char: 27</span><span class="sxs-lookup"><span data-stu-id="e6505-155">At line:1 char:27</span></span>

<span data-ttu-id="e6505-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="e6505-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="e6505-157">\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="e6505-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="e6505-158">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="e6505-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="e6505-159">Die Meldung "Push Notification Request wurde abgelehnt" tritt normalerweise auf, wenn Sie die URL-Filterung aktiviert haben und die http:-und https:-Präfixe blockieren.</span><span class="sxs-lookup"><span data-stu-id="e6505-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="e6505-160">Sie können bestimmen, welche Präfixe blockiert werden, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="e6505-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="e6505-161">Wenn http: oder https: in den Ergebnissen angezeigt wird, müssen Sie Sie aus der Liste der blockierten Präfixe entfernen, damit Push-Benachrichtigungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e6505-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="e6505-162">Dies kann mithilfe von Befehlen wie den folgenden erfolgen:</span><span class="sxs-lookup"><span data-stu-id="e6505-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="e6505-163">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)".</span><span class="sxs-lookup"><span data-stu-id="e6505-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


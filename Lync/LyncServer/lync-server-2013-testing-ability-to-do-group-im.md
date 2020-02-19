---
title: 'Lync Server 2013: Testen der Fähigkeit, Gruppen-Chat zu durchführen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecb197f7ce8acbd4639be9ee20b93e6008922f3c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="7e529-102">Testen der Fähigkeit, Gruppen-Chat in lync Server 2013 zu ausführen</span><span class="sxs-lookup"><span data-stu-id="7e529-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e529-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7e529-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e529-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="7e529-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7e529-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="7e529-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e529-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="7e529-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7e529-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e529-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e529-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7e529-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7e529-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="7e529-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7e529-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsGroupIM verfügt.</span><span class="sxs-lookup"><span data-stu-id="7e529-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="7e529-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="7e529-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7e529-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e529-112">Description</span></span>

<span data-ttu-id="7e529-113">Das Cmdlet Test-CsGroupIM überprüft, ob Benutzer in Ihrer Organisation Gruppen-Chatsitzungen durchführen können.</span><span class="sxs-lookup"><span data-stu-id="7e529-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="7e529-114">Wenn Sie Test-CsGroupIM ausführen, versucht das Cmdlet, sich an einem Paar von Testbenutzern anzumelden, um lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e529-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="7e529-115">Wenn die Methode erfolgreich verläuft, erstellt Test-CsGroupIM eine neue Konferenz mit dem ersten Testbenutzer und lädt den zweiten Benutzer ein, an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7e529-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="7e529-116">Nach dem Austausch von Nachrichten werden beide Benutzer vom System getrennt.</span><span class="sxs-lookup"><span data-stu-id="7e529-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="7e529-117">Beachten Sie, dass dies alles ohne Benutzerinteraktion und ohne Beeinträchtigung von tatsächlichen Benutzern geschieht.</span><span class="sxs-lookup"><span data-stu-id="7e529-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="7e529-118">Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der über ein echtes lync Server Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="7e529-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="7e529-119">In diesem Fall wird der Test ohne Unterbrechung des realen Ken Myers durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e529-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="7e529-120">Wenn sich beispielsweise das Ken Myers-Test Konto vom System abmeldet, bleibt die Person angemeldet.</span><span class="sxs-lookup"><span data-stu-id="7e529-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="7e529-121">Ebenso wird der wirkliche Ken Myers keine Einladung erhalten, an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7e529-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="7e529-122">Diese Einladung wird an das Test Konto gesendet und von diesem akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="7e529-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="7e529-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="7e529-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7e529-124">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="7e529-124">Running the test</span></span>

<span data-ttu-id="7e529-125">Das Cmdlet Test-CsGroupIM kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7e529-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="7e529-126">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e529-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="7e529-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e529-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="7e529-128">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server-Verwaltungsshell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e529-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7e529-129">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsGroupIM aufrufen:</span><span class="sxs-lookup"><span data-stu-id="7e529-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="7e529-130">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="7e529-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7e529-131">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="7e529-131">Determining Success or Failure</span></span>

<span data-ttu-id="7e529-132">Wenn die beiden Benutzer eine Gruppen-Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="7e529-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7e529-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e529-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7e529-134">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="7e529-134">Result : Success</span></span>

<span data-ttu-id="7e529-135">Wartezeit: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="7e529-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="7e529-136">Fehler</span><span class="sxs-lookup"><span data-stu-id="7e529-136">Error :</span></span>

<span data-ttu-id="7e529-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="7e529-137">Diagnosis :</span></span>

<span data-ttu-id="7e529-138">Wenn die beiden Benutzer nicht in der Lage sind, die Sofortnachrichtensitzung abzuschließen, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="7e529-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7e529-139">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e529-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7e529-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="7e529-140">Result : Failure</span></span>

<span data-ttu-id="7e529-141">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7e529-141">Latency : 00:00:00</span></span>

<span data-ttu-id="7e529-142">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="7e529-142">Error : 404, Not Found</span></span>

<span data-ttu-id="7e529-143">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="7e529-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="7e529-144">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="7e529-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="7e529-145">existieren.</span><span class="sxs-lookup"><span data-stu-id="7e529-145">exist.</span></span>

<span data-ttu-id="7e529-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="7e529-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="7e529-147">Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da mindestens eines der Testkonten ungültig war, da das Konto nicht vorhanden ist oder der Benutzer nicht für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e529-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="7e529-148">Sie können überprüfen, ob das Konto vorhanden ist, und ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="7e529-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="7e529-149">Wenn Test-CsGroupIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="7e529-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="7e529-150">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsGroupIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer Gruppe von Chatsitzungen überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="7e529-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="7e529-151">Wenn der Test beispielsweise fehlschlägt und Ihnen mitgeteilt wird, dass ein oder mehrere Benutzerkonten ungültig sind, können Sie den Test mit dem Verbose-Parameter erneut ausführen und bestimmen, welches Benutzerkonto ungültig ist:</span><span class="sxs-lookup"><span data-stu-id="7e529-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="7e529-152">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="7e529-152">Sending Registration request:</span></span>

 <span data-ttu-id="7e529-153">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e529-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="7e529-154">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e529-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="7e529-155">Register Port = 5061</span><span class="sxs-lookup"><span data-stu-id="7e529-155">Register Port    = 5061</span></span>

<span data-ttu-id="7e529-156">Der Authentifizierungstyp "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7e529-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="7e529-157">Eine Ausnahme: "das Anmelden wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="7e529-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="7e529-158">Stellen Sie sicher, dass die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="7e529-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="7e529-159">Wie Sie sehen können, konnte sich der Benutzer, der über die SIP-Adresse SIP:kenmyer@litwareinc.com verfügt, in diesem Beispiel nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="7e529-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7e529-160">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="7e529-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="7e529-161">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsGroupIM möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="7e529-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="7e529-162">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="7e529-162">You specified an incorrect user account.</span></span> <span data-ttu-id="7e529-163">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="7e529-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="7e529-164">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7e529-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="7e529-165">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="7e529-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="7e529-166">Get-CsUser "SIP:kenmyer@litwareinc.com" | SELECT-Objekt aktiviert</span><span class="sxs-lookup"><span data-stu-id="7e529-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="7e529-167">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7e529-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="7e529-168">Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7e529-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="7e529-169">Mit lync Server können Sie das System so konfigurieren, dass Chatnachrichten nicht verfügbar sind, wenn nicht auf die Archivierungsdatenbank zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e529-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="7e529-170">Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="7e529-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="7e529-171">Wenn BlockOnArchiveFailure auf true festgelegt ist, sollten Sie bestimmen, ob die Archivierungsdatenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e529-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="7e529-172">Mit dem folgenden Befehl können Sie die Speicherorte ihrer Archivierungsdatenbanken zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="7e529-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="7e529-173">Die Archivierungsserver ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7e529-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="7e529-174">Mit dem folgenden Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:</span><span class="sxs-lookup"><span data-stu-id="7e529-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="7e529-175">Anschließend können Sie den entsprechenden Server anpingen, um sicherzustellen, dass dieser verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e529-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="7e529-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e529-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


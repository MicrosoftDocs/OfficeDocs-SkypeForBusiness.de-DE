---
title: 'Lync Server 2013: Testen der Fähigkeit, Gruppen-Chat zu durchführen'
description: 'Lync Server 2013: Testen der Fähigkeit, Gruppen-Chat zu durchführen.'
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
ms.openlocfilehash: f6988a0c1a7ba569f7b4da098ae741beab5e14fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560811"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="39aaf-103">Testen der Fähigkeit, Gruppen-Chat in lync Server 2013 zu ausführen</span><span class="sxs-lookup"><span data-stu-id="39aaf-103">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39aaf-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="39aaf-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39aaf-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="39aaf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="39aaf-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="39aaf-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39aaf-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="39aaf-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="39aaf-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39aaf-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39aaf-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39aaf-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="39aaf-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="39aaf-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="39aaf-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsGroupIM-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="39aaf-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="39aaf-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="39aaf-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="39aaf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39aaf-113">Description</span></span>

<span data-ttu-id="39aaf-114">Das Test-CsGroupIM-Cmdlet überprüft, ob Benutzer in Ihrer Organisation Gruppen-Chatsitzungen durchführen können.</span><span class="sxs-lookup"><span data-stu-id="39aaf-114">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="39aaf-115">Wenn Sie Test-CsGroupIM ausführen, versucht das Cmdlet, sich an einem Paar von Testbenutzern anzumelden, um lync Server.</span><span class="sxs-lookup"><span data-stu-id="39aaf-115">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="39aaf-116">Wenn die Test-CsGroupIM erfolgreich verläuft, wird mit dem ersten Testbenutzer eine neue Konferenz erstellt, und anschließend wird der zweite Benutzer aufgefordert, an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="39aaf-116">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="39aaf-117">Nach dem Austausch von Nachrichten werden beide Benutzer vom System getrennt.</span><span class="sxs-lookup"><span data-stu-id="39aaf-117">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="39aaf-118">Beachten Sie, dass dies alles ohne Benutzerinteraktion und ohne Beeinträchtigung von tatsächlichen Benutzern geschieht.</span><span class="sxs-lookup"><span data-stu-id="39aaf-118">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="39aaf-119">Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der über ein echtes lync Server Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="39aaf-119">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="39aaf-120">In diesem Fall wird der Test ohne Unterbrechung des realen Ken Myers durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="39aaf-120">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="39aaf-121">Wenn sich beispielsweise das Ken Myers-Test Konto vom System abmeldet, bleibt die Person angemeldet.</span><span class="sxs-lookup"><span data-stu-id="39aaf-121">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="39aaf-122">Ebenso wird der wirkliche Ken Myers keine Einladung erhalten, an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="39aaf-122">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="39aaf-123">Diese Einladung wird an das Test Konto gesendet und von diesem akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="39aaf-123">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="39aaf-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="39aaf-124">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="39aaf-125">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="39aaf-125">Running the test</span></span>

<span data-ttu-id="39aaf-126">Das Test-CsGroupIM-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="39aaf-126">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="39aaf-127">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="39aaf-127">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="39aaf-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39aaf-128">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="39aaf-129">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server-Verwaltungsshell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="39aaf-129">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="39aaf-130">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsGroupIM aufrufen:</span><span class="sxs-lookup"><span data-stu-id="39aaf-130">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="39aaf-131">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="39aaf-131">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="39aaf-132">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="39aaf-132">Determining Success or Failure</span></span>

<span data-ttu-id="39aaf-133">Wenn die beiden Benutzer eine Gruppen-Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="39aaf-133">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="39aaf-134">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39aaf-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39aaf-135">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="39aaf-135">Result : Success</span></span>

<span data-ttu-id="39aaf-136">Wartezeit: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="39aaf-136">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="39aaf-137">Fehler</span><span class="sxs-lookup"><span data-stu-id="39aaf-137">Error :</span></span>

<span data-ttu-id="39aaf-138">Diagnose</span><span class="sxs-lookup"><span data-stu-id="39aaf-138">Diagnosis :</span></span>

<span data-ttu-id="39aaf-139">Wenn die beiden Benutzer nicht in der Lage sind, die Sofortnachrichtensitzung abzuschließen, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="39aaf-139">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="39aaf-140">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39aaf-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39aaf-141">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="39aaf-141">Result : Failure</span></span>

<span data-ttu-id="39aaf-142">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="39aaf-142">Latency : 00:00:00</span></span>

<span data-ttu-id="39aaf-143">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="39aaf-143">Error : 404, Not Found</span></span>

<span data-ttu-id="39aaf-144">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="39aaf-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="39aaf-145">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="39aaf-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="39aaf-146">existieren.</span><span class="sxs-lookup"><span data-stu-id="39aaf-146">exist.</span></span>

<span data-ttu-id="39aaf-147">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="39aaf-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="39aaf-148">Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, da mindestens eines der Testkonten ungültig war, da das Konto nicht vorhanden ist oder der Benutzer nicht für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="39aaf-148">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="39aaf-149">Sie können überprüfen, ob das Konto vorhanden ist, und ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="39aaf-149">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="39aaf-150">Wenn Test-CsGroupIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="39aaf-150">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="39aaf-151">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsGroupIM eine schrittweise Rechnung über jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer Gruppe von Chatsitzungen überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="39aaf-151">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="39aaf-152">Wenn der Test beispielsweise fehlschlägt und Ihnen mitgeteilt wird, dass ein oder mehrere Benutzerkonten ungültig sind, können Sie den Test mit dem Verbose-Parameter erneut ausführen und bestimmen, welches Benutzerkonto ungültig ist:</span><span class="sxs-lookup"><span data-stu-id="39aaf-152">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="39aaf-153">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="39aaf-153">Sending Registration request:</span></span>

 <span data-ttu-id="39aaf-154">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39aaf-154">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="39aaf-155">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39aaf-155">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="39aaf-156">Register Port = 5061</span><span class="sxs-lookup"><span data-stu-id="39aaf-156">Register Port    = 5061</span></span>

<span data-ttu-id="39aaf-157">Der Authentifizierungstyp "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="39aaf-157">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="39aaf-158">Eine Ausnahme: "das Anmelden wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="39aaf-158">An exception 'The log on was denied.</span></span> <span data-ttu-id="39aaf-159">Stellen Sie sicher, dass die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="39aaf-159">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="39aaf-160">Wie Sie sehen können, konnte sich der Benutzer, der über die SIP-Adresse SIP:kenmyer@litwareinc.com verfügt, in diesem Beispiel nicht anmelden.</span><span class="sxs-lookup"><span data-stu-id="39aaf-160">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="39aaf-161">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="39aaf-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="39aaf-162">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsGroupIM Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="39aaf-162">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="39aaf-163">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="39aaf-163">You specified an incorrect user account.</span></span> <span data-ttu-id="39aaf-164">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="39aaf-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="39aaf-165">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="39aaf-165">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="39aaf-166">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert wurde, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="39aaf-166">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="39aaf-167">Get-CsUser "SIP:kenmyer@litwareinc.com" | Select-Object aktiviert</span><span class="sxs-lookup"><span data-stu-id="39aaf-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="39aaf-168">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="39aaf-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="39aaf-169">Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="39aaf-169">The instant messaging service might not be available.</span></span> <span data-ttu-id="39aaf-170">Mit lync Server können Sie das System so konfigurieren, dass Chatnachrichten nicht verfügbar sind, wenn nicht auf die Archivierungsdatenbank zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="39aaf-170">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="39aaf-171">Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="39aaf-171">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="39aaf-172">Wenn BlockOnArchiveFailure auf true festgelegt ist, sollten Sie bestimmen, ob die Archivierungsdatenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="39aaf-172">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="39aaf-173">Mit dem folgenden Befehl können Sie die Speicherorte ihrer Archivierungsdatenbanken zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="39aaf-173">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="39aaf-174">Die Archivierungsserver ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="39aaf-174">The Archiving Server might not be available.</span></span> <span data-ttu-id="39aaf-175">Mit dem folgenden Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:</span><span class="sxs-lookup"><span data-stu-id="39aaf-175">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="39aaf-176">Anschließend können Sie den entsprechenden Server anpingen, um sicherzustellen, dass dieser verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="39aaf-176">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="39aaf-177">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39aaf-177">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


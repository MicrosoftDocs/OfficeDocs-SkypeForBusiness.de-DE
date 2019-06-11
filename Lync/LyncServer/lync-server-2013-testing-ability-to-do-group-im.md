---
title: 'Lync Server 2013: Testen der Gruppen-Chatfunktion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="47fdc-102">Testen der Fähigkeit zum Gruppieren von Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47fdc-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47fdc-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="47fdc-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47fdc-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="47fdc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="47fdc-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="47fdc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47fdc-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="47fdc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="47fdc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47fdc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47fdc-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="47fdc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="47fdc-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="47fdc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="47fdc-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsGroupIM-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="47fdc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="47fdc-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="47fdc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="47fdc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47fdc-112">Description</span></span>

<span data-ttu-id="47fdc-113">Das Cmdlet Test-CsGroupIM überprüft, ob Benutzer in Ihrer Organisation Gruppen-Chatsitzungen durchführen können.</span><span class="sxs-lookup"><span data-stu-id="47fdc-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="47fdc-114">Wenn Sie Test-CsGroupIM ausführen, versucht das Cmdlet, ein paar Test Benutzer mit lync Server zu signieren.</span><span class="sxs-lookup"><span data-stu-id="47fdc-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="47fdc-115">Wenn Sie erfolgreich sind, erstellt Test-CsGroupIM eine neue Konferenz mit dem ersten Testbenutzer und lädt den zweiten Benutzer ein, an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="47fdc-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="47fdc-116">Nach einem Austausch von Nachrichten werden beide Benutzer vom System getrennt.</span><span class="sxs-lookup"><span data-stu-id="47fdc-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="47fdc-117">Beachten Sie, dass dies alles ohne Benutzerinteraktion und ohne Auswirkungen auf tatsächliche Benutzer geschieht.</span><span class="sxs-lookup"><span data-stu-id="47fdc-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="47fdc-118">Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der ein echtes lync Server-Konto hat.</span><span class="sxs-lookup"><span data-stu-id="47fdc-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="47fdc-119">In diesem Fall wird der Test ohne Unterbrechung des echten Ken Myers durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="47fdc-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="47fdc-120">Auch wenn sich das Ken Myers Test-Konto vom System abmeldet, bleibt die Person beispielsweise angemeldet.</span><span class="sxs-lookup"><span data-stu-id="47fdc-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="47fdc-121">Ebenso erhält der wirkliche Ken Myers keine Einladung zur Teilnahme an der Konferenz.</span><span class="sxs-lookup"><span data-stu-id="47fdc-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="47fdc-122">Diese Einladung wird an das Testkonto gesendet und von diesem akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="47fdc-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="47fdc-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="47fdc-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="47fdc-124">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="47fdc-124">Running the test</span></span>

<span data-ttu-id="47fdc-125">Das Cmdlet "Test-CsGroupIM" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="47fdc-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="47fdc-126">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="47fdc-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="47fdc-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47fdc-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="47fdc-128">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Anmeldedaten Objekte der lync Server-Verwaltungsshell (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="47fdc-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="47fdc-129">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsGroupIM aufrufen:</span><span class="sxs-lookup"><span data-stu-id="47fdc-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="47fdc-130">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .</span><span class="sxs-lookup"><span data-stu-id="47fdc-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="47fdc-131">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="47fdc-131">Determining Success or Failure</span></span>

<span data-ttu-id="47fdc-132">Wenn die beiden Benutzer eine Gruppen-Chatsitzung durchführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Ergebniseigenschaft als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="47fdc-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="47fdc-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47fdc-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="47fdc-134">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="47fdc-134">Result : Success</span></span>

<span data-ttu-id="47fdc-135">Latenz: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="47fdc-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="47fdc-136">Fehler</span><span class="sxs-lookup"><span data-stu-id="47fdc-136">Error :</span></span>

<span data-ttu-id="47fdc-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="47fdc-137">Diagnosis :</span></span>

<span data-ttu-id="47fdc-138">Wenn die beiden Benutzer nicht in der Lage sind, die Chat-Sitzung abzuschließen, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="47fdc-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="47fdc-139">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47fdc-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="47fdc-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="47fdc-140">Result : Failure</span></span>

<span data-ttu-id="47fdc-141">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="47fdc-141">Latency : 00:00:00</span></span>

<span data-ttu-id="47fdc-142">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="47fdc-142">Error : 404, Not Found</span></span>

<span data-ttu-id="47fdc-143">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="47fdc-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="47fdc-144">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="47fdc-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="47fdc-145">existieren.</span><span class="sxs-lookup"><span data-stu-id="47fdc-145">exist.</span></span>

<span data-ttu-id="47fdc-146">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="47fdc-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="47fdc-147">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, weil mindestens eines der Testkonten ungültig war, weil das Konto nicht vorhanden ist oder der Benutzer nicht für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="47fdc-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="47fdc-148">Sie können überprüfen, ob das Konto vorhanden ist, und ob das Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen ähnlichen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="47fdc-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="47fdc-149">Wenn Test-CsGroupIM fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="47fdc-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="47fdc-150">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsGroupIM eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer Gruppen-Chatsitzung überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="47fdc-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="47fdc-151">Wenn Ihr Test beispielsweise fehlschlägt und Ihnen mitgeteilt wird, dass ein oder mehrere Benutzerkonten ungültig sind, können Sie den Test mit dem Verbose-Parameter erneut ausführen und feststellen, welches Benutzerkonto ungültig ist:</span><span class="sxs-lookup"><span data-stu-id="47fdc-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="47fdc-152">Registrierungsanfrage wird gesendet:</span><span class="sxs-lookup"><span data-stu-id="47fdc-152">Sending Registration request:</span></span>

 <span data-ttu-id="47fdc-153">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47fdc-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="47fdc-154">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="47fdc-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="47fdc-155">Port registrieren = 5061</span><span class="sxs-lookup"><span data-stu-id="47fdc-155">Register Port    = 5061</span></span>

<span data-ttu-id="47fdc-156">Auth-Typ "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="47fdc-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="47fdc-157">Eine Ausnahme "die Anmeldung wurde abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="47fdc-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="47fdc-158">Überprüfen Sie, ob die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist. "</span><span class="sxs-lookup"><span data-stu-id="47fdc-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="47fdc-159">Wie Sie sehen können, war in diesem Beispiel der Benutzer, der die SIP-Adresse SIP:kenmyer@litwareinc.com, nicht in der Lage, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="47fdc-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="47fdc-160">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="47fdc-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="47fdc-161">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsGroupIM möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="47fdc-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="47fdc-162">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="47fdc-162">You specified an incorrect user account.</span></span> <span data-ttu-id="47fdc-163">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="47fdc-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="47fdc-164">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="47fdc-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="47fdc-165">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert war, führen Sie einen Befehl ähnlich der folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="47fdc-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="47fdc-166">Get-CsUser "SIP:kenmyer@litwareinc.com" | SELECT-Objekt aktiviert</span><span class="sxs-lookup"><span data-stu-id="47fdc-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="47fdc-167">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="47fdc-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="47fdc-168">Der Instant Messaging-Dienst ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="47fdc-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="47fdc-169">Mit lync Server können Sie das System so konfigurieren, dass Sofortnachrichten nicht verfügbar sind, wenn auf die Archivierungsdatenbank nicht zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="47fdc-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="47fdc-170">Sie können dies überprüfen, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="47fdc-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="47fdc-171">Wenn BlockOnArchiveFailure auf "true" festgelegt ist, sollten Sie ermitteln, ob die Archivierungsdatenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="47fdc-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="47fdc-172">Sie können die Speicherorte ihrer Archivierungsdatenbanken mithilfe des folgenden Befehls zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="47fdc-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="47fdc-173">Der Archivierungs Server steht möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="47fdc-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="47fdc-174">Mit diesem Befehl können Sie den FQDN ihrer Archivierungsserver abrufen:</span><span class="sxs-lookup"><span data-stu-id="47fdc-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="47fdc-175">Sie können dann den entsprechenden Server anpingen, um zu überprüfen, ob er verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="47fdc-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="47fdc-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47fdc-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


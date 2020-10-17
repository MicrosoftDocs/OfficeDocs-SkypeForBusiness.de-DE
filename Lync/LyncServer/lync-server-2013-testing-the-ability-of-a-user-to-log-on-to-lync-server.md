---
title: 'Lync Server 2013: Testen der Fähigkeit eines Benutzers, sich bei lync Server anzumelden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac7f02d18f1b270b3a58a7ece84cb3a859b32b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530472"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="ac95a-102">Testen der Fähigkeit eines Benutzers, sich bei lync Server 2013 anzumelden</span><span class="sxs-lookup"><span data-stu-id="ac95a-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac95a-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ac95a-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac95a-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="ac95a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ac95a-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="ac95a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac95a-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="ac95a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ac95a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac95a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac95a-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ac95a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ac95a-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="ac95a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ac95a-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsRegistration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="ac95a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="ac95a-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="ac95a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ac95a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac95a-112">Description</span></span>

<span data-ttu-id="ac95a-113">Mit dem Test-CsRegistration-Cmdlet können Sie sicherstellen, dass sich Benutzer in Ihrer Organisation bei lync Server anmelden können.</span><span class="sxs-lookup"><span data-stu-id="ac95a-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="ac95a-114">Wenn Sie Test-CsRegistration ausführen, versucht das Cmdlet, sich an einem Testbenutzer anzumelden, um lync Server und dann, wenn es erfolgreich ist, die Verbindung zwischen diesem Testbenutzer und dem System zu trennen.</span><span class="sxs-lookup"><span data-stu-id="ac95a-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="ac95a-115">All dies geschieht ohne Benutzerinteraktion und ohne Auswirkungen auf tatsächliche Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ac95a-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="ac95a-116">Nehmen wir beispielsweise an, dass das Test Konto SIP:kenmyer@litwareinc.com einem echten Benutzer entspricht, der über ein echtes lync Server Konto verfügt.</span><span class="sxs-lookup"><span data-stu-id="ac95a-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="ac95a-117">In diesem Fall wird der Test ohne Unterbrechung des realen Ken Myers durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac95a-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="ac95a-118">Wenn sich das Ken Myers-Test Konto vom System abmeldet, bleibt die Person angemeldet.</span><span class="sxs-lookup"><span data-stu-id="ac95a-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ac95a-119">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="ac95a-119">Running the test</span></span>

<span data-ttu-id="ac95a-120">Das Test-CsRegistration-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ac95a-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="ac95a-121">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server registrierungspools angeben, der getestet wird.</span><span class="sxs-lookup"><span data-stu-id="ac95a-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="ac95a-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ac95a-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ac95a-123">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="ac95a-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="ac95a-124">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsRegistration aufrufen:</span><span class="sxs-lookup"><span data-stu-id="ac95a-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="ac95a-125">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .</span><span class="sxs-lookup"><span data-stu-id="ac95a-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ac95a-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="ac95a-126">Determining success or failure</span></span>

<span data-ttu-id="ac95a-127">Wenn sich der angegebene Benutzer bei anmelden kann (und dann Abmelden von) lync Server, erhalten Sie eine Ausgabe ähnlich der folgenden, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="ac95a-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ac95a-128">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac95a-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ac95a-129">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="ac95a-129">Result : Success</span></span>

<span data-ttu-id="ac95a-130">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="ac95a-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="ac95a-131">Fehler</span><span class="sxs-lookup"><span data-stu-id="ac95a-131">Error :</span></span>

<span data-ttu-id="ac95a-132">Diagnose</span><span class="sxs-lookup"><span data-stu-id="ac95a-132">Diagnosis :</span></span>

<span data-ttu-id="ac95a-133">Wenn sich der angegebene Benutzer nicht anmelden oder abmelden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="ac95a-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ac95a-134">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac95a-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ac95a-135">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="ac95a-135">Result : Failure</span></span>

<span data-ttu-id="ac95a-136">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ac95a-136">Latency : 00:00:00</span></span>

<span data-ttu-id="ac95a-137">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="ac95a-137">Error : 404, Not Found</span></span>

<span data-ttu-id="ac95a-138">Diagnose: errorCode = 1003, Source = ATL-CS-001. litwareinc. com, Reason = Benutzer does</span><span class="sxs-lookup"><span data-stu-id="ac95a-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="ac95a-139">nicht vorhanden</span><span class="sxs-lookup"><span data-stu-id="ac95a-139">not exist</span></span>

<span data-ttu-id="ac95a-140">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="ac95a-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="ac95a-141">Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da der angegebene Benutzer nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="ac95a-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="ac95a-142">Sie können ermitteln, ob eine SIP-Adresse gültig ist (und ob der Benutzer, dem diese SIP-Adresse zugewiesen ist, für lync Server aktiviert ist), indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ac95a-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="ac95a-143">Wenn Test-CsRegistration fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="ac95a-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="ac95a-144">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsRegistration eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ac95a-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ac95a-145">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ac95a-145">For example:</span></span>

<span data-ttu-id="ac95a-146">Ausführlich: Aktivität "registrieren" gestartet.</span><span class="sxs-lookup"><span data-stu-id="ac95a-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="ac95a-147">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="ac95a-147">Sending Registration request:</span></span>

<span data-ttu-id="ac95a-148">Ziel-FQDN = ATL-CS-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac95a-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="ac95a-149">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac95a-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="ac95a-150">Registrierungsstelle Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="ac95a-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="ac95a-151">Der Authentifizierungstyp "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ac95a-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="ac95a-152">Eine Ausnahme "der Endpunkt kann nicht registriert werden.</span><span class="sxs-lookup"><span data-stu-id="ac95a-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="ac95a-153">Lesen Sie den ErrorCode aus einem bestimmten Grund ", der während der Ausführung des Workflows" Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow "aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ac95a-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="ac95a-154">Ausnahmeaufrufliste: unter Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="ac95a-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ac95a-155">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="ac95a-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="ac95a-156">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsRegistration Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="ac95a-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="ac95a-157">Sie haben ein falsches Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac95a-157">You specified an incorrect user account.</span></span> <span data-ttu-id="ac95a-158">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="ac95a-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ac95a-159">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ac95a-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="ac95a-160">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="ac95a-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="ac95a-161">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ac95a-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="ac95a-162">Sie haben einen falschen registrierungsstellenpool angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac95a-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="ac95a-163">Mit dem folgenden Befehl können Sie die FQDNs ihrer Registrierungsstellen Pools zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="ac95a-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="ac95a-164">Der registrierungsstellenpool ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac95a-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="ac95a-165">Versuchen Sie, den Pool zu pingen, um zu sehen, ob er antwortet:</span><span class="sxs-lookup"><span data-stu-id="ac95a-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>


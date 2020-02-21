---
title: 'Lync Server 2013: Überprüfen von Audio/Video-Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb206930dae08d0c2fcf5fa6a26b427b28c03e1b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="e65df-102">Überprüfen von Audio/Video-Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e65df-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e65df-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e65df-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65df-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="e65df-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e65df-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="e65df-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e65df-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="e65df-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e65df-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e65df-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e65df-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e65df-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e65df-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="e65df-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e65df-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsAVConference verfügt.</span><span class="sxs-lookup"><span data-stu-id="e65df-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="e65df-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="e65df-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e65df-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e65df-112">Description</span></span>

<span data-ttu-id="e65df-113">Das Cmdlet Test-CsAVConference überprüft, ob zwei Test Benutzer an einer Audio/Video-Konferenz (A/V) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="e65df-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="e65df-114">Wenn das Cmdlet durchgeführt wird, werden die zwei Benutzer beim System angemeldet.</span><span class="sxs-lookup"><span data-stu-id="e65df-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="e65df-115">Nachdem Sie sich erfolgreich angemeldet haben, erstellt der erste Benutzer eine A/V-Konferenz und wartet darauf, dass der zweite Benutzer an dieser Konferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="e65df-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="e65df-116">Nach einem kurzen Datenaustausch wird die Konferenz gelöscht, und die zwei Testbenutzer werden abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="e65df-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="e65df-117">Beachten Sie, dass mit Test-CsAVConference keine tatsächliche A/V-Konferenz zwischen den beiden Testbenutzern durchzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="e65df-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="e65df-118">Stattdessen überprüft das Cmdlet, ob die beiden Benutzer alle erforderlichen Verbindungen zum Durchführen einer solchen Konferenz herstellen können.</span><span class="sxs-lookup"><span data-stu-id="e65df-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="e65df-119">Weitere Beispiele für diesen Befehl finden Sie unter [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="e65df-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e65df-120">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="e65df-120">Running the test</span></span>

<span data-ttu-id="e65df-121">Das Cmdlet Test-CsAVConference kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="e65df-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="e65df-122">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e65df-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e65df-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e65df-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e65df-124">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="e65df-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="e65df-125">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsAVConference aufrufen:</span><span class="sxs-lookup"><span data-stu-id="e65df-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="e65df-126">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="e65df-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e65df-127">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="e65df-127">Determining Success or Failure</span></span>

<span data-ttu-id="e65df-128">Wenn die angegebenen Benutzer eine A/V-Konferenz erfolgreich abschließen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="e65df-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e65df-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e65df-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e65df-130">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="e65df-130">Result : Success</span></span>

<span data-ttu-id="e65df-131">Wartezeit: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="e65df-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="e65df-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="e65df-132">Error :</span></span>

<span data-ttu-id="e65df-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e65df-133">Diagnosis :</span></span>

<span data-ttu-id="e65df-134">Wenn die Benutzer die Konferenz nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="e65df-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e65df-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e65df-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e65df-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="e65df-136">Result : Failure</span></span>

<span data-ttu-id="e65df-137">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e65df-137">Latency : 00:00:00</span></span>

<span data-ttu-id="e65df-138">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e65df-138">Error : 404, Not Found</span></span>

<span data-ttu-id="e65df-139">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="e65df-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="e65df-140">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="e65df-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="e65df-141">existieren.</span><span class="sxs-lookup"><span data-stu-id="e65df-141">exist.</span></span>

<span data-ttu-id="e65df-142">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="e65df-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="e65df-143">In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, da mindestens eines der beiden Benutzerkonten ungültig war, da das Konto nicht vorhanden ist oder das Konto nicht für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="e65df-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="e65df-144">Sie können überprüfen, ob die beiden Testkonten vorhanden sind und ob Sie für lync Server aktiviert wurden, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="e65df-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="e65df-145">Wenn Test-CsAVConference fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="e65df-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="e65df-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsAVConference eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer AV-Konferenz überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="e65df-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="e65df-147">Nehmen Sie beispielsweise an, dass Ihr Test fehlschlägt und Sie die folgende Diagnose erhalten:</span><span class="sxs-lookup"><span data-stu-id="e65df-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="e65df-148">ErrorCode = 1008, Source = accessproxy. litwareinc. com, Reason = DNS-SRV-Eintrag kann nicht aufgelöst werden</span><span class="sxs-lookup"><span data-stu-id="e65df-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="e65df-149">Wenn Sie den Test mit dem Verbose-Parameter erneut ausführen, werden die zurückgegebenen Schritt-für-Schritt-Informationen in etwa wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="e65df-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="e65df-150">Ausführlich: Aktivität "registrieren" gestartet.</span><span class="sxs-lookup"><span data-stu-id="e65df-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="e65df-151">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="e65df-151">Sending Registration request:</span></span>

<span data-ttu-id="e65df-152">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e65df-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e65df-153">SIP-Adresse des Benutzers = SIP:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e65df-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="e65df-154">Registrierungsstelle Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="e65df-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="e65df-155">Der Authentifizierungstyp "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e65df-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="e65df-156">Aktivität ' registrieren ' gestartet.</span><span class="sxs-lookup"><span data-stu-id="e65df-156">'Register' activity started.</span></span>

<span data-ttu-id="e65df-157">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="e65df-157">Sending Registration request:</span></span>

<span data-ttu-id="e65df-158">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e65df-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e65df-159">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e65df-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="e65df-160">Registrierungsstelle Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="e65df-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="e65df-161">Der Authentifizierungstyp "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e65df-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="e65df-162">Eine Ausnahme "der Endpunkt konnte sich nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="e65df-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="e65df-163">Lesen Sie den ErrorCode aus einem bestimmten Grund. '</span><span class="sxs-lookup"><span data-stu-id="e65df-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="e65df-164">während des Workflows aufgetreten</span><span class="sxs-lookup"><span data-stu-id="e65df-164">occurred during Workflow</span></span>

<span data-ttu-id="e65df-165">Die letzte Ausgabe in dieser Ausgabe gibt an, dass sich der Benutzer SIP:kenmyer@litwareinc.com nicht bei lync Server registrieren konnte.</span><span class="sxs-lookup"><span data-stu-id="e65df-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="e65df-166">Das bedeutet, dass Sie überprüfen sollten, ob die SIP-Adresse SIP:kenmyer@litwareinc.com gültig ist und dass der zugeordnete Benutzer für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e65df-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e65df-167">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="e65df-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="e65df-168">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsAVConference möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="e65df-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="e65df-169">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="e65df-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="e65df-170">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="e65df-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e65df-171">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e65df-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e65df-172">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="e65df-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e65df-173">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e65df-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


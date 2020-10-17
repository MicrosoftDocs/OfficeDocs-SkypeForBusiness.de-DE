---
title: 'Lync Server 2013: Überprüfen von Audio/Video-Konferenzen'
description: 'Lync Server 2013: Überprüfen von Audio/Video-Konferenzen.'
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
ms.openlocfilehash: ad12611e928a64b934252ec21c18b98366e0912b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547201"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="993f6-103">Überprüfen von Audio/Video-Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="993f6-103">Validating audio/video conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="993f6-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="993f6-104">_**Topic Last Modified:** 2014-06-05_</span></span>


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
<td><p><span data-ttu-id="993f6-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="993f6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="993f6-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="993f6-106">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="993f6-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="993f6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="993f6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="993f6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="993f6-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="993f6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="993f6-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="993f6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="993f6-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAVConference-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="993f6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="993f6-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="993f6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="993f6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="993f6-113">Description</span></span>

<span data-ttu-id="993f6-114">Das Test-CsAVConference-Cmdlet überprüft, ob zwei Testbenutzer an einer Audio/Video-Konferenz (A/V) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="993f6-114">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="993f6-115">Wenn das Cmdlet durchgeführt wird, werden die zwei Benutzer beim System angemeldet.</span><span class="sxs-lookup"><span data-stu-id="993f6-115">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="993f6-116">Nachdem Sie sich erfolgreich angemeldet haben, erstellt der erste Benutzer eine A/V-Konferenz und wartet darauf, dass der zweite Benutzer an dieser Konferenz teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="993f6-116">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="993f6-117">Nach einem kurzen Datenaustausch wird die Konferenz gelöscht, und die zwei Testbenutzer werden abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="993f6-117">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="993f6-118">Beachten Sie, dass Test-CsAVConference keine tatsächliche A/V-Konferenz zwischen den beiden Testbenutzern durchführt.</span><span class="sxs-lookup"><span data-stu-id="993f6-118">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="993f6-119">Stattdessen überprüft das Cmdlet, ob die beiden Benutzer alle erforderlichen Verbindungen zum Durchführen einer solchen Konferenz herstellen können.</span><span class="sxs-lookup"><span data-stu-id="993f6-119">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="993f6-120">Weitere Beispiele für diesen Befehl finden Sie unter [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="993f6-120">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="993f6-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="993f6-121">Running the test</span></span>

<span data-ttu-id="993f6-122">Das Test-CsAVConference-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="993f6-122">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="993f6-123">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="993f6-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="993f6-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="993f6-124">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="993f6-125">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="993f6-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="993f6-126">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsAVConference aufrufen:</span><span class="sxs-lookup"><span data-stu-id="993f6-126">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="993f6-127">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="993f6-127">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="993f6-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="993f6-128">Determining Success or Failure</span></span>

<span data-ttu-id="993f6-129">Wenn die angegebenen Benutzer eine A/V-Konferenz erfolgreich abschließen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="993f6-129">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="993f6-130">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="993f6-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="993f6-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="993f6-131">Result : Success</span></span>

<span data-ttu-id="993f6-132">Wartezeit: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="993f6-132">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="993f6-133">Fehler</span><span class="sxs-lookup"><span data-stu-id="993f6-133">Error :</span></span>

<span data-ttu-id="993f6-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="993f6-134">Diagnosis :</span></span>

<span data-ttu-id="993f6-135">Wenn die Benutzer die Konferenz nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="993f6-135">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="993f6-136">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="993f6-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="993f6-137">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="993f6-137">Result : Failure</span></span>

<span data-ttu-id="993f6-138">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="993f6-138">Latency : 00:00:00</span></span>

<span data-ttu-id="993f6-139">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="993f6-139">Error : 404, Not Found</span></span>

<span data-ttu-id="993f6-140">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="993f6-140">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="993f6-141">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="993f6-141">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="993f6-142">existieren.</span><span class="sxs-lookup"><span data-stu-id="993f6-142">exist.</span></span>

<span data-ttu-id="993f6-143">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="993f6-143">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="993f6-144">In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, da mindestens eines der beiden Benutzerkonten ungültig war, da das Konto nicht vorhanden ist oder das Konto nicht für lync Server aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="993f6-144">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="993f6-145">Sie können überprüfen, ob die beiden Testkonten vorhanden sind und ob Sie für lync Server aktiviert wurden, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="993f6-145">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="993f6-146">Wenn Test-CsAVConference fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="993f6-146">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="993f6-147">Wenn der Verbose-Parameter enthalten ist Test-CsAVConference gibt eine schrittweise Rechnung über jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer AV-Konferenz überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="993f6-147">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="993f6-148">Nehmen Sie beispielsweise an, dass Ihr Test fehlschlägt und Sie die folgende Diagnose erhalten:</span><span class="sxs-lookup"><span data-stu-id="993f6-148">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="993f6-149">ErrorCode = 1008, Source = accessproxy. litwareinc. com, Reason = DNS-SRV-Eintrag kann nicht aufgelöst werden</span><span class="sxs-lookup"><span data-stu-id="993f6-149">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="993f6-150">Wenn Sie den Test mit dem Verbose-Parameter erneut ausführen, werden die zurückgegebenen Schritt-für-Schritt-Informationen in etwa wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="993f6-150">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="993f6-151">Ausführlich: Aktivität "registrieren" gestartet.</span><span class="sxs-lookup"><span data-stu-id="993f6-151">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="993f6-152">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="993f6-152">Sending Registration request:</span></span>

<span data-ttu-id="993f6-153">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="993f6-153">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="993f6-154">SIP-Adresse des Benutzers = SIP:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="993f6-154">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="993f6-155">Registrierungsstelle Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="993f6-155">Registrar Port = 5061.</span></span>

<span data-ttu-id="993f6-156">Der Authentifizierungstyp "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="993f6-156">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="993f6-157">Aktivität ' registrieren ' gestartet.</span><span class="sxs-lookup"><span data-stu-id="993f6-157">'Register' activity started.</span></span>

<span data-ttu-id="993f6-158">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="993f6-158">Sending Registration request:</span></span>

<span data-ttu-id="993f6-159">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="993f6-159">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="993f6-160">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="993f6-160">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="993f6-161">Registrierungsstelle Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="993f6-161">Registrar Port = 5061.</span></span>

<span data-ttu-id="993f6-162">Der Authentifizierungstyp "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="993f6-162">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="993f6-163">Eine Ausnahme "der Endpunkt konnte sich nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="993f6-163">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="993f6-164">Lesen Sie den ErrorCode aus einem bestimmten Grund. '</span><span class="sxs-lookup"><span data-stu-id="993f6-164">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="993f6-165">während des Workflows aufgetreten</span><span class="sxs-lookup"><span data-stu-id="993f6-165">occurred during Workflow</span></span>

<span data-ttu-id="993f6-166">Die letzte Ausgabe in dieser Ausgabe gibt an, dass sich der Benutzer SIP:kenmyer@litwareinc.com nicht bei lync Server registrieren konnte.</span><span class="sxs-lookup"><span data-stu-id="993f6-166">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="993f6-167">Das bedeutet, dass Sie überprüfen sollten, ob die SIP-Adresse SIP:kenmyer@litwareinc.com gültig ist und dass der zugeordnete Benutzer für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="993f6-167">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="993f6-168">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="993f6-168">Reasons why the test might have failed</span></span>

<span data-ttu-id="993f6-169">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsAVConference Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="993f6-169">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="993f6-170">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="993f6-170">You specified a user account that is not valid.</span></span> <span data-ttu-id="993f6-171">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="993f6-171">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="993f6-172">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="993f6-172">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="993f6-173">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="993f6-173">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="993f6-174">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="993f6-174">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


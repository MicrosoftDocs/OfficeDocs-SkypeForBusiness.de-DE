---
title: 'Lync Server 2013: Überprüfen von Audio-und Videokonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0e608f0c765c4dd552645320ec947c7e8a54ac4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="27f72-102">Überprüfen von Audio-und Videokonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27f72-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27f72-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="27f72-103">_**Topic Last Modified:** 2014-06-05_</span></span>


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
<td><p><span data-ttu-id="27f72-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="27f72-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="27f72-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="27f72-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f72-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="27f72-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="27f72-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27f72-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f72-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="27f72-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="27f72-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="27f72-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="27f72-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsAVConference-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="27f72-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="27f72-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="27f72-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="27f72-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27f72-112">Description</span></span>

<span data-ttu-id="27f72-113">Das Cmdlet Test-CsAVConference überprüft, ob zwei Test Benutzer an einer Audio/Video-Konferenz (A/V) teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="27f72-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="27f72-114">Wenn das Cmdlet ausgeführt wird, sind die beiden Benutzer am System angemeldet.</span><span class="sxs-lookup"><span data-stu-id="27f72-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="27f72-115">Nachdem Sie sich erfolgreich angemeldet haben, erstellt der erste Benutzer eine A/V-Konferenz und wartet dann auf die Teilnahme des zweiten Benutzers an dieser Konferenz.</span><span class="sxs-lookup"><span data-stu-id="27f72-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="27f72-116">Nach einem kurzen Datenaustausch wird die Konferenz gelöscht, und die beiden Testbenutzer werden abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="27f72-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="27f72-117">Beachten Sie, dass Test-CsAVConference keine eigentliche A/V-Konferenz zwischen den beiden Testbenutzern durchführt.</span><span class="sxs-lookup"><span data-stu-id="27f72-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="27f72-118">Stattdessen überprüft das Cmdlet, ob die beiden Benutzer alle erforderlichen Verbindungen zum Durchführen einer solchen Konferenz vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="27f72-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="27f72-119">Weitere Beispiele für diesen Befehl finden Sie unter [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span><span class="sxs-lookup"><span data-stu-id="27f72-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="27f72-120">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="27f72-120">Running the test</span></span>

<span data-ttu-id="27f72-121">Das Cmdlet "Test-CsAVConference" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="27f72-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="27f72-122">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="27f72-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="27f72-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="27f72-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="27f72-124">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="27f72-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="27f72-125">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsAVConference aufrufen:</span><span class="sxs-lookup"><span data-stu-id="27f72-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="27f72-126">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .</span><span class="sxs-lookup"><span data-stu-id="27f72-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="27f72-127">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="27f72-127">Determining Success or Failure</span></span>

<span data-ttu-id="27f72-128">Wenn die angegebenen Benutzer eine A/V-Konferenz erfolgreich abschließen können, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="27f72-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="27f72-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27f72-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27f72-130">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="27f72-130">Result : Success</span></span>

<span data-ttu-id="27f72-131">Latenz: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="27f72-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="27f72-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="27f72-132">Error :</span></span>

<span data-ttu-id="27f72-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="27f72-133">Diagnosis :</span></span>

<span data-ttu-id="27f72-134">Wenn die Benutzer die Konferenz nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="27f72-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="27f72-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27f72-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27f72-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="27f72-136">Result : Failure</span></span>

<span data-ttu-id="27f72-137">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="27f72-137">Latency : 00:00:00</span></span>

<span data-ttu-id="27f72-138">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="27f72-138">Error : 404, Not Found</span></span>

<span data-ttu-id="27f72-139">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="27f72-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="27f72-140">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="27f72-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="27f72-141">existieren.</span><span class="sxs-lookup"><span data-stu-id="27f72-141">exist.</span></span>

<span data-ttu-id="27f72-142">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="27f72-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="27f72-143">In der vorherigen Ausgabe wird beispielsweise festgestellt, dass der Test fehlgeschlagen ist, weil mindestens eines der beiden Benutzerkonten ungültig war, weil das Konto nicht vorhanden ist oder weil das Konto für lync Server nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="27f72-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="27f72-144">Sie können überprüfen, ob die beiden Testkonten vorhanden sind und ob Sie für lync Server aktiviert wurden, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="27f72-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="27f72-145">Wenn Test-CsAVConference fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="27f72-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="27f72-146">Wenn der Verbose-Parameter enthalten ist, gibt CsAVConference eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als Sie die Fähigkeit der angegebenen Benutzer zur Teilnahme an einer AV-Konferenz überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="27f72-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="27f72-147">Nehmen wir beispielsweise an, dass Ihr Test fehlschlägt und Sie die folgende Diagnose erhalten:</span><span class="sxs-lookup"><span data-stu-id="27f72-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="27f72-148">ErrorCode = 1008, Source = accessproxy. "litwareinc. com; Reason = DNS-SRV-Eintrag konnte nicht aufgelöst werden</span><span class="sxs-lookup"><span data-stu-id="27f72-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="27f72-149">Wenn Sie den Test mit dem Verbose-Parameter erneut ausführen, beinhalten die zurückgegebenen schrittweisen Informationen eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="27f72-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="27f72-150">Ausführlich: die Aktivität "registrieren" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="27f72-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="27f72-151">Registrierungsanfrage wird gesendet:</span><span class="sxs-lookup"><span data-stu-id="27f72-151">Sending Registration request:</span></span>

<span data-ttu-id="27f72-152">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27f72-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27f72-153">SIP-Adresse des Benutzers = SIP:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27f72-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="27f72-154">Registrar Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="27f72-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="27f72-155">Auth-Typ "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="27f72-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="27f72-156">Die Aktivität "registrieren" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="27f72-156">'Register' activity started.</span></span>

<span data-ttu-id="27f72-157">Registrierungsanfrage wird gesendet:</span><span class="sxs-lookup"><span data-stu-id="27f72-157">Sending Registration request:</span></span>

<span data-ttu-id="27f72-158">Ziel-FQDN = ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27f72-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27f72-159">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27f72-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="27f72-160">Registrar Port = 5061.</span><span class="sxs-lookup"><span data-stu-id="27f72-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="27f72-161">Auth-Typ "vertrauenswürdig" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="27f72-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="27f72-162">Eine Ausnahme "der Endpunkt konnte nicht registriert werden.</span><span class="sxs-lookup"><span data-stu-id="27f72-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="27f72-163">Lesen Sie den ErrorCode aus bestimmten Gründen.</span><span class="sxs-lookup"><span data-stu-id="27f72-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="27f72-164">während des Workflows aufgetreten</span><span class="sxs-lookup"><span data-stu-id="27f72-164">occurred during Workflow</span></span>

<span data-ttu-id="27f72-165">Die letzte Zeile in dieser Ausgabe gibt an, dass der Benutzer SIP:kenmyer@litwareinc.com sich nicht bei lync Server registrieren konnte.</span><span class="sxs-lookup"><span data-stu-id="27f72-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="27f72-166">Das bedeutet, dass Sie überprüfen sollten, ob die SIP-Adresse SIP:kenmyer@litwareinc.com gültig ist und dass der zugeordnete Benutzer für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27f72-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="27f72-167">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="27f72-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="27f72-168">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsAVConference möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="27f72-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="27f72-169">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="27f72-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="27f72-170">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="27f72-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="27f72-171">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="27f72-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="27f72-172">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="27f72-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="27f72-173">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27f72-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


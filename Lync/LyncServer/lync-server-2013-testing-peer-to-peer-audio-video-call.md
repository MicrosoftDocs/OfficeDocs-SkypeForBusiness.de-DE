---
title: 'Lync Server 2013: Testen von Peer-to-Peer-Audio/Video-Anruf'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 462442b7afea193866dc96aaf57085d780f43a39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="7bf98-102">Testen von Peer-to-Peer-Audio/Video-anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bf98-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bf98-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7bf98-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7bf98-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="7bf98-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7bf98-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="7bf98-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7bf98-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="7bf98-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7bf98-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7bf98-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7bf98-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7bf98-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7bf98-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="7bf98-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7bf98-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsP2PAV verfügt.</span><span class="sxs-lookup"><span data-stu-id="7bf98-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="7bf98-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="7bf98-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7bf98-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7bf98-112">Description</span></span>

<span data-ttu-id="7bf98-113">Test-CsP2PAV wird verwendet, um zu bestimmen, ob ein paar von Testbenutzern an einer Peer-zu-Peer-a/V-Unterhaltung teilnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="7bf98-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="7bf98-114">Um dieses Szenario zu testen, wird das Cmdlet durch die Protokollierung der beiden Benutzer lync Server.</span><span class="sxs-lookup"><span data-stu-id="7bf98-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="7bf98-115">Unter der Voraussetzung, dass die beiden Anmeldungen erfolgreich sind, lädt der erste Benutzer den zweiten Benutzer ein, an einem A/V-Aufruf teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7bf98-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="7bf98-116">Der zweite Benutzer nimmt den Anruf an, die Verbindung zwischen den beiden Benutzern wird getestet, und der Anruf wird beendet, und die Testbenutzer werden vom System abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="7bf98-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="7bf98-117">Test-CsP2PAV führt tatsächlich keinen A/V-Aufruf durch.</span><span class="sxs-lookup"><span data-stu-id="7bf98-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="7bf98-118">Es werden keine Multimedia-Informationen zwischen den Testbenutzern ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="7bf98-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="7bf98-119">Stattdessen überprüft das Cmdlet lediglich, dass die entsprechenden Verbindungen hergestellt werden können und dass die beiden Benutzer einen solchen Anruf durchführen können.</span><span class="sxs-lookup"><span data-stu-id="7bf98-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="7bf98-120">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="7bf98-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7bf98-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="7bf98-121">Running the test</span></span>

<span data-ttu-id="7bf98-122">Das Cmdlet Test-CsP2PAV kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7bf98-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="7bf98-123">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7bf98-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="7bf98-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7bf98-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="7bf98-125">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei lync Server Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bf98-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7bf98-126">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsP2PAV aufrufen:</span><span class="sxs-lookup"><span data-stu-id="7bf98-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7bf98-127">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="7bf98-127">Determining success or failure</span></span>

<span data-ttu-id="7bf98-128">Wenn die beiden Testbenutzer einen Peer-to-Peer-a/V-Aufruf abschließen können, erhalten Sie eine ähnliche Ausgabe wie diese, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="7bf98-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7bf98-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7bf98-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7bf98-130">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="7bf98-130">Result : Success</span></span>

<span data-ttu-id="7bf98-131">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="7bf98-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="7bf98-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="7bf98-132">Error :</span></span>

<span data-ttu-id="7bf98-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="7bf98-133">Diagnosis :</span></span>

<span data-ttu-id="7bf98-134">Wenn die Testbenutzer den Anruf nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="7bf98-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7bf98-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7bf98-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7bf98-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="7bf98-136">Result : Failure</span></span>

<span data-ttu-id="7bf98-137">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7bf98-137">Latency : 00:00:00</span></span>

<span data-ttu-id="7bf98-138">Fehler: 480, vorübergehend nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="7bf98-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="7bf98-139">Diagnose: errorCode = 15030, Source = ATL-CS-001. litwareinc. com, Reason = failed</span><span class="sxs-lookup"><span data-stu-id="7bf98-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="7bf98-140">So leiten Sie zu Exchange Server um</span><span class="sxs-lookup"><span data-stu-id="7bf98-140">to route to Exchange Server</span></span>

<span data-ttu-id="7bf98-141">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="7bf98-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="7bf98-142">Die vorherige Ausgabe besagt beispielsweise, dass der Test fehlgeschlagen ist, da die Exchange Server nicht kontaktiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="7bf98-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="7bf98-143">Diese Fehlermeldung weist in der Regel auf ein Problem bei der Konfiguration von Exchange Unified Messaging hin.</span><span class="sxs-lookup"><span data-stu-id="7bf98-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="7bf98-144">Wenn "Test-CsP2PAV" fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, einschließlich des Verbose-Parameters:</span><span class="sxs-lookup"><span data-stu-id="7bf98-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="7bf98-145">Test-CsP2PAV-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="7bf98-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="7bf98-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsP2PAV eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="7bf98-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="7bf98-147">Nehmen Sie beispielsweise an, dass Ihr Test mit der folgenden Diagnose fehlgeschlagen ist:</span><span class="sxs-lookup"><span data-stu-id="7bf98-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="7bf98-148">ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, Reason = nicht unterstützte out-of-Dialog-Anforderung</span><span class="sxs-lookup"><span data-stu-id="7bf98-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="7bf98-149">Wenn Sie Test-CsP2PAV erneut ausführen und den Parameter Verbose hinzufügen, erhalten Sie eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="7bf98-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="7bf98-150">Ausführlich: Aktivität "registrieren" gestartet.</span><span class="sxs-lookup"><span data-stu-id="7bf98-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="7bf98-151">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="7bf98-151">Sending Registration request:</span></span>

<span data-ttu-id="7bf98-152">Ziel-FQDN = ATL-CS-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7bf98-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="7bf98-153">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7bf98-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="7bf98-154">Registrierungsstelle Port = 5062.</span><span class="sxs-lookup"><span data-stu-id="7bf98-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="7bf98-155">Der Authentifizierungstyp "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7bf98-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="7bf98-156">Eine Ausnahme "der Endpunkt konnte sich nicht registrieren.</span><span class="sxs-lookup"><span data-stu-id="7bf98-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="7bf98-157">Lesen Sie den ErrorCode aus einem bestimmten Grund. '</span><span class="sxs-lookup"><span data-stu-id="7bf98-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="7bf98-158">während der Ausführung des Workflows "Microsoft. RTC. SyntheticTransactions. Workflows. STP2PAVWorkflow" aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7bf98-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="7bf98-159">Obwohl es möglicherweise nicht sofort offensichtlich ist, werden Sie feststellen, dass ein falscher Registrierungs Port (Port 5062) angegeben wurde, wenn Sie die Ausgabe sorgfältig untersuchen.</span><span class="sxs-lookup"><span data-stu-id="7bf98-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="7bf98-160">Dies hat wiederum dazu geführt, dass der Test fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="7bf98-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7bf98-161">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="7bf98-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="7bf98-162">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsP2PAV möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="7bf98-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="7bf98-163">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="7bf98-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="7bf98-164">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="7bf98-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="7bf98-165">Get-CsUser "SIP:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="7bf98-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="7bf98-166">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7bf98-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="7bf98-167">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="7bf98-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="7bf98-168">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="7bf98-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


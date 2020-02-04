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
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="eb83b-102">Testen des Peer-to-Peer-Audio/Video-Anrufs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb83b-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb83b-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="eb83b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb83b-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="eb83b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="eb83b-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="eb83b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb83b-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="eb83b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="eb83b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb83b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb83b-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="eb83b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="eb83b-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="eb83b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="eb83b-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsP2PAV-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="eb83b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="eb83b-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="eb83b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="eb83b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb83b-112">Description</span></span>

<span data-ttu-id="eb83b-113">Test-CsP2PAV wird verwendet, um zu ermitteln, ob ein paar Testbenutzer an einer Peer-to-Peer-a/V-Unterhaltung teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="eb83b-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="eb83b-114">Um dieses Szenario zu testen, wird das Cmdlet gestartet, indem die beiden Benutzer zu lync Server angemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="eb83b-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="eb83b-115">Wenn die beiden Anmeldungen erfolgreich sind, lädt der erste Benutzer den zweiten Benutzer ein, an einem A/V-Anruf teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="eb83b-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="eb83b-116">Der zweite Benutzer akzeptiert den Anruf, die Verbindung zwischen den beiden Benutzern wird getestet, und der Anruf wird beendet, und die Testbenutzer werden vom System abgemeldet.</span><span class="sxs-lookup"><span data-stu-id="eb83b-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="eb83b-117">Test-CsP2PAV führt tatsächlich keinen A/V-Anruf durch.</span><span class="sxs-lookup"><span data-stu-id="eb83b-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="eb83b-118">Es werden keine Multimedia-Informationen zwischen den Testbenutzern ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="eb83b-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="eb83b-119">Stattdessen überprüft das Cmdlet lediglich, ob die entsprechenden Verbindungen hergestellt werden können und dass die beiden Benutzer einen solchen Anruf durchführen können.</span><span class="sxs-lookup"><span data-stu-id="eb83b-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="eb83b-120">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .</span><span class="sxs-lookup"><span data-stu-id="eb83b-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="eb83b-121">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="eb83b-121">Running the test</span></span>

<span data-ttu-id="eb83b-122">Das Cmdlet "Test-CsP2PAV" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="eb83b-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="eb83b-123">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="eb83b-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="eb83b-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eb83b-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="eb83b-125">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Anmeldeinformationsobjekte für lync Server (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb83b-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="eb83b-126">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsP2PAV aufrufen:</span><span class="sxs-lookup"><span data-stu-id="eb83b-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="eb83b-127">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="eb83b-127">Determining success or failure</span></span>

<span data-ttu-id="eb83b-128">Wenn die beiden Testbenutzer einen Peer-to-Peer-a/V-Anruf durchführen können, erhalten Sie eine ähnliche Ausgabe wie die Ergebniseigenschaft, die als erfolgreich markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="eb83b-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="eb83b-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb83b-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eb83b-130">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="eb83b-130">Result : Success</span></span>

<span data-ttu-id="eb83b-131">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="eb83b-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="eb83b-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="eb83b-132">Error :</span></span>

<span data-ttu-id="eb83b-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="eb83b-133">Diagnosis :</span></span>

<span data-ttu-id="eb83b-134">Wenn die Testbenutzer den Anruf nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="eb83b-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="eb83b-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb83b-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eb83b-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="eb83b-136">Result : Failure</span></span>

<span data-ttu-id="eb83b-137">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="eb83b-137">Latency : 00:00:00</span></span>

<span data-ttu-id="eb83b-138">Fehler: 480, vorübergehend nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="eb83b-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="eb83b-139">Diagnose: errorCode = 15030, Quelle = ATL-CS-001. "litwareinc. com, Reason = fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="eb83b-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="eb83b-140">So leiten Sie zu Exchange Server weiter</span><span class="sxs-lookup"><span data-stu-id="eb83b-140">to route to Exchange Server</span></span>

<span data-ttu-id="eb83b-141">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="eb83b-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="eb83b-142">In der vorherigen Ausgabe wird beispielsweise angegeben, dass der Test fehlgeschlagen ist, weil der Microsoft Exchange-Server nicht kontaktiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="eb83b-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="eb83b-143">Diese Fehlermeldung weist in der Regel auf ein Problem bei der Konfiguration von Exchange Unified Messaging hin.</span><span class="sxs-lookup"><span data-stu-id="eb83b-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="eb83b-144">Wenn Test-CsP2PAV fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="eb83b-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="eb83b-145">Test-CsP2PAV-TargetFqdn "ATL-CS-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="eb83b-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="eb83b-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsP2PAV eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, während Sie die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="eb83b-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="eb83b-147">Nehmen Sie beispielsweise an, dass Ihr Test mit der folgenden Diagnose fehlgeschlagen ist:</span><span class="sxs-lookup"><span data-stu-id="eb83b-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="eb83b-148">ErrorCode = 6003, Source = ATL-CS-001. "litwareinc. com; Reason = nicht unterstützte Dialog Anfrage</span><span class="sxs-lookup"><span data-stu-id="eb83b-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="eb83b-149">Wenn Sie Test-CsP2PAV erneut ausführen und den Verbose-Parameter hinzufügen, erhalten Sie eine Ausgabe, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="eb83b-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="eb83b-150">Ausführlich: die Aktivität "registrieren" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="eb83b-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="eb83b-151">Registrierungsanfrage wird gesendet:</span><span class="sxs-lookup"><span data-stu-id="eb83b-151">Sending Registration request:</span></span>

<span data-ttu-id="eb83b-152">Ziel-FQDN = ATL-CS-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb83b-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="eb83b-153">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb83b-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="eb83b-154">Registrar Port = 5062.</span><span class="sxs-lookup"><span data-stu-id="eb83b-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="eb83b-155">Auth-Typ "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="eb83b-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="eb83b-156">Eine Ausnahme "der Endpunkt konnte nicht registriert werden.</span><span class="sxs-lookup"><span data-stu-id="eb83b-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="eb83b-157">Lesen Sie den ErrorCode aus bestimmten Gründen.</span><span class="sxs-lookup"><span data-stu-id="eb83b-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="eb83b-158">während des Workflows Microsoft. RTC. SyntheticTransactions. Workflows. STP2PAVWorkflow-Ausführung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="eb83b-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="eb83b-159">Es ist zwar nicht unmittelbar klar, ob Sie die Ausgabe sorgfältig untersuchen, doch wird ein falscher Registrierungs Port (Port 5062) angegeben.</span><span class="sxs-lookup"><span data-stu-id="eb83b-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="eb83b-160">Dies führte wiederum dazu, dass der Test fehlschlug.</span><span class="sxs-lookup"><span data-stu-id="eb83b-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="eb83b-161">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="eb83b-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="eb83b-162">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsP2PAV möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="eb83b-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="eb83b-163">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="eb83b-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="eb83b-164">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="eb83b-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="eb83b-165">Get-CsUser "SIP:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="eb83b-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="eb83b-166">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eb83b-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="eb83b-167">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="eb83b-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="eb83b-168">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eb83b-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


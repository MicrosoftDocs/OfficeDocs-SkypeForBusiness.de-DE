---
title: 'Lync Server 2013: Testen der Standortrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="e80f5-102">Testen der Standortrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e80f5-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e80f5-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e80f5-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e80f5-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="e80f5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e80f5-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="e80f5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e80f5-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="e80f5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e80f5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e80f5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e80f5-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e80f5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e80f5-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="e80f5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e80f5-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsLocationPolicy-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="e80f5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="e80f5-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="e80f5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e80f5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e80f5-112">Description</span></span>

<span data-ttu-id="e80f5-113">Das Cmdlet Test-CsLocationPolicy überprüft, ob einem Benutzer eine ortungsrichtlinie zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="e80f5-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="e80f5-114">Die ortungsrichtlinie wird verwendet, um Einstellungen anzuwenden, die sich auf die E9-1-1-Funktionalität und den Clientstandort beziehen.</span><span class="sxs-lookup"><span data-stu-id="e80f5-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="e80f5-115">Die Standortrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist, und, wenn die Antwort "Ja" lautet, was das Verhalten eines Notrufs ist.</span><span class="sxs-lookup"><span data-stu-id="e80f5-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="e80f5-116">So können Sie beispielsweise mithilfe der ortungsrichtlinie definieren, welche Nummer ein Notruf ausmacht (911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e80f5-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="e80f5-117">Sie können Standortrichtlinien für Benutzer oder Netzwerk-Subnets testen.</span><span class="sxs-lookup"><span data-stu-id="e80f5-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="e80f5-118">Wenn Sie den Test für ein Subnetz ausführen (indem Sie einen Wert für den Subnet-Parameter angeben), versucht das Cmdlet, die Standortrichtlinie für dieses Subnetz zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e80f5-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="e80f5-119">Wenn dem Subnetz keine Standortrichtlinie zugewiesen ist, wird die Standortrichtlinie für den konfigurierten Benutzer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e80f5-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="e80f5-120">Wenn die Subnet-Richtlinie erfolgreich abgerufen wird, enthält die Ausgabe einen LocationPolicyTagID-Wert, der mit Subnet-TagID beginnt.</span><span class="sxs-lookup"><span data-stu-id="e80f5-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="e80f5-121">Wenn keine Standortrichtlinie für das Subnetz gefunden wurde, beginnt die LocationPolicyTagID mit Benutzer-TagID.</span><span class="sxs-lookup"><span data-stu-id="e80f5-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e80f5-122">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="e80f5-122">Running the test</span></span>

<span data-ttu-id="e80f5-123">Das Cmdlet "Test-CsLocationPolicy" kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e80f5-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="e80f5-124">Um diese Überprüfung mit einem Testkonto auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="e80f5-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e80f5-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e80f5-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e80f5-126">Damit diese Überprüfung mit einem tatsächlichen Benutzerkonto ausgeführt werden kann, müssen Sie zuerst ein Windows PowerShell-Anmeldeinformationsobjekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="e80f5-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="e80f5-127">Sie müssen das Anmeldeinformationen-Objekt und die SIP-Adresse, die dem Konto zugewiesen ist, beim Aufrufen von Test-CsLocationPolicy einfügen:</span><span class="sxs-lookup"><span data-stu-id="e80f5-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e80f5-128">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="e80f5-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e80f5-129">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="e80f5-129">Determining success or failure</span></span>

<span data-ttu-id="e80f5-130">Wenn der angegebene Benutzer über eine gültige Standortrichtlinie verfügt, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="e80f5-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e80f5-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="e80f5-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="e80f5-132">LocationPolicyTagID: Benutzer-TagID</span><span class="sxs-lookup"><span data-stu-id="e80f5-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="e80f5-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e80f5-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e80f5-134">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="e80f5-134">Result : Success</span></span>

<span data-ttu-id="e80f5-135">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="e80f5-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="e80f5-136">Fehler</span><span class="sxs-lookup"><span data-stu-id="e80f5-136">Error :</span></span>

<span data-ttu-id="e80f5-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="e80f5-137">Diagnosis :</span></span>

<span data-ttu-id="e80f5-138">Wenn für den angegebenen Benutzer keine gültige Standortrichtlinie gefunden werden kann, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="e80f5-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e80f5-139">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e80f5-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e80f5-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="e80f5-140">Result : Failure</span></span>

<span data-ttu-id="e80f5-141">Latenz: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e80f5-141">Latency : 00:00:00</span></span>

<span data-ttu-id="e80f5-142">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="e80f5-142">Error : 404, Not Found</span></span>

<span data-ttu-id="e80f5-143">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="e80f5-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="e80f5-144">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="e80f5-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="e80f5-145">existieren.</span><span class="sxs-lookup"><span data-stu-id="e80f5-145">exist.</span></span>

<span data-ttu-id="e80f5-146">Microsoft. RTC. Signalisierungs-DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="e80f5-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="e80f5-147">Die vorherige Ausgabe besagt, dass der Test fehlgeschlagen ist, weil der angegebene Benutzer ungültig ist: entweder ist das Konto nicht vorhanden, oder der Benutzer wurde nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e80f5-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="e80f5-148">Sie können die Gültigkeit eines Kontos überprüfen und ermitteln, ob dieses Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="e80f5-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="e80f5-149">Wenn Test-CsLocationPolicy fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="e80f5-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="e80f5-150">Wenn der Parameter Verbose enthalten ist, gibt Test-CsLocationPolicy eine Schritt-für-Schritt-Konto für jede Aktion zurück, die beim Überprüfen der Standortrichtlinie versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="e80f5-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="e80f5-151">Diese Ausgabe zeigt beispielsweise an, dass sich lync Server nicht bei dem Testbenutzer anmelden konnte, wahrscheinlich weil ein ungültiges Kennwort angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="e80f5-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="e80f5-152">Registrierungsanfrage wird gesendet:</span><span class="sxs-lookup"><span data-stu-id="e80f5-152">Sending Registration request :</span></span>

<span data-ttu-id="e80f5-153">Ziel-FQDN = ATL-CS-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e80f5-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="e80f5-154">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e80f5-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="e80f5-155">Registrar Port = 5061</span><span class="sxs-lookup"><span data-stu-id="e80f5-155">Registrar Port = 5061</span></span>

<span data-ttu-id="e80f5-156">Auth-Typ "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e80f5-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="e80f5-157">Registrierungs Treffer für SIP/ATL-CS-001. "litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="e80f5-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e80f5-158">' Registrieren '-Aktivität abgeschlossen in ' 0,0601795 ' Sek.</span><span class="sxs-lookup"><span data-stu-id="e80f5-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="e80f5-159">Eine Ausnahme "die Anmeldung wurde abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="e80f5-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="e80f5-160">Überprüfen Sie, ob die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e80f5-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="e80f5-161">während des Workflows aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e80f5-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e80f5-162">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="e80f5-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="e80f5-163">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsLocationPolicy möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="e80f5-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="e80f5-164">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="e80f5-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="e80f5-165">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="e80f5-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e80f5-166">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e80f5-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e80f5-167">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="e80f5-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e80f5-168">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e80f5-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


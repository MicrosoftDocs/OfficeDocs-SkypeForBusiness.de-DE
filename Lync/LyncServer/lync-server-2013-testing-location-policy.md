---
title: 'Lync Server 2013: Testen der Standortrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cd477b02aa261b762f728ca15d296f49dfbac1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535992"
---
# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="81ef8-102">Testen der Standortrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81ef8-102">Testing location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81ef8-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="81ef8-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81ef8-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="81ef8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="81ef8-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="81ef8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81ef8-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="81ef8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="81ef8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81ef8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81ef8-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="81ef8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="81ef8-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="81ef8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="81ef8-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsLocationPolicy-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="81ef8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="81ef8-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="81ef8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="81ef8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81ef8-112">Description</span></span>

<span data-ttu-id="81ef8-113">Das Test-CsLocationPolicy-Cmdlet überprüft, ob eine ortungsrichtlinie einem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="81ef8-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="81ef8-114">Die ortungsrichtlinie wird verwendet, um Einstellungen anzuwenden, die sich auf die E9-1-1-Funktionalität und den Clientstandort beziehen.</span><span class="sxs-lookup"><span data-stu-id="81ef8-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="81ef8-115">Die ortungsrichtlinie legt fest, ob ein Benutzer für E9-1-1 aktiviert ist, und, wenn die Antwort "Ja" lautet, was das Verhalten eines Notrufs ist.</span><span class="sxs-lookup"><span data-stu-id="81ef8-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="81ef8-116">Beispielsweise können Sie die ortungsrichtlinie verwenden, um zu definieren, welche Zahl einen Notruf ausstellt (911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81ef8-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="81ef8-117">Sie können Standortrichtlinien für Benutzer oder Netzwerksubnetze testen.</span><span class="sxs-lookup"><span data-stu-id="81ef8-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="81ef8-118">Wenn Sie den Test für ein Subnetz ausführen (indem Sie einen Wert für den Parameter "Subnet" angeben), versucht das Cmdlet, die Standortrichtlinie für dieses Subnetz aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="81ef8-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="81ef8-119">Wenn dem Subnetz keine Standortrichtlinie zugewiesen ist, wird die Standortrichtlinie für den konfigurierten Benutzer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="81ef8-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="81ef8-120">Wenn die Subnetz-Richtlinie erfolgreich abgerufen wird, enthält die Ausgabe einen LocationPolicyTagID-Wert, der mit Subnetz-TagID beginnt.</span><span class="sxs-lookup"><span data-stu-id="81ef8-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="81ef8-121">Wenn keine Standortrichtlinie für das Subnetz gefunden wurde, beginnt die "LocationPolicyTagID" mit "user-tagid".</span><span class="sxs-lookup"><span data-stu-id="81ef8-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="81ef8-122">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="81ef8-122">Running the test</span></span>

<span data-ttu-id="81ef8-123">Das Test-CsLocationPolicy-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="81ef8-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="81ef8-124">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81ef8-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="81ef8-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="81ef8-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="81ef8-126">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="81ef8-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="81ef8-127">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsLocationPolicy aufrufen:</span><span class="sxs-lookup"><span data-stu-id="81ef8-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="81ef8-128">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .</span><span class="sxs-lookup"><span data-stu-id="81ef8-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="81ef8-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="81ef8-129">Determining success or failure</span></span>

<span data-ttu-id="81ef8-130">Wenn der angegebene Benutzer über eine gültige Standortrichtlinie verfügt, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="81ef8-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="81ef8-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="81ef8-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="81ef8-132">LocationPolicyTagID: User-TagID</span><span class="sxs-lookup"><span data-stu-id="81ef8-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="81ef8-133">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="81ef8-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="81ef8-134">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="81ef8-134">Result : Success</span></span>

<span data-ttu-id="81ef8-135">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="81ef8-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="81ef8-136">Fehler</span><span class="sxs-lookup"><span data-stu-id="81ef8-136">Error :</span></span>

<span data-ttu-id="81ef8-137">Diagnose</span><span class="sxs-lookup"><span data-stu-id="81ef8-137">Diagnosis :</span></span>

<span data-ttu-id="81ef8-138">Wenn für den angegebenen Benutzer keine gültige ortungsrichtlinie gefunden werden kann, wird result als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="81ef8-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="81ef8-139">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="81ef8-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="81ef8-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="81ef8-140">Result : Failure</span></span>

<span data-ttu-id="81ef8-141">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="81ef8-141">Latency : 00:00:00</span></span>

<span data-ttu-id="81ef8-142">Fehler: 404, nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="81ef8-142">Error : 404, Not Found</span></span>

<span data-ttu-id="81ef8-143">Diagnose: errorCode = 4005, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="81ef8-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="81ef8-144">Reason = Ziel-URI ist entweder für SIP nicht aktiviert oder nicht</span><span class="sxs-lookup"><span data-stu-id="81ef8-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="81ef8-145">existieren.</span><span class="sxs-lookup"><span data-stu-id="81ef8-145">exist.</span></span>

<span data-ttu-id="81ef8-146">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="81ef8-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="81ef8-147">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da der angegebene Benutzer ungültig ist: entweder ist das Konto nicht vorhanden, oder der Benutzer wurde für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="81ef8-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="81ef8-148">Sie können die Gültigkeit eines Kontos überprüfen und bestimmen, ob dieses Konto für nm-OCS-14-3rd aktiviert wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="81ef8-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="81ef8-149">Wenn Test-CsLocationPolicy fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="81ef8-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="81ef8-150">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsLocationPolicy ein schrittweises Konto für jede Aktion zurück, die beim Überprüfen der ortungsrichtlinie versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="81ef8-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="81ef8-151">Diese Ausgabe gibt beispielsweise an, dass lync Server sich nicht bei dem Testbenutzer anmelden konnten, wahrscheinlich weil ein ungültiges Kennwort angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="81ef8-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="81ef8-152">Senden der Registrierungsanforderung:</span><span class="sxs-lookup"><span data-stu-id="81ef8-152">Sending Registration request :</span></span>

<span data-ttu-id="81ef8-153">Ziel-FQDN = ATL-CS-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="81ef8-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="81ef8-154">SIP-Adresse des Benutzers = SIP:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="81ef8-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="81ef8-155">Registrierungsstelle = 5061</span><span class="sxs-lookup"><span data-stu-id="81ef8-155">Registrar Port = 5061</span></span>

<span data-ttu-id="81ef8-156">Der Authentifizierungstyp "IWA" ist ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="81ef8-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="81ef8-157">Registrierungs Treffer gegen SIP/ATL-CS-001. litwareinc. com</span><span class="sxs-lookup"><span data-stu-id="81ef8-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="81ef8-158">"Registrierung"-Aktivität abgeschlossen in "0,0601795" Sek.</span><span class="sxs-lookup"><span data-stu-id="81ef8-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="81ef8-159">Eine Ausnahme: "das Anmelden wurde verweigert.</span><span class="sxs-lookup"><span data-stu-id="81ef8-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="81ef8-160">Stellen Sie sicher, dass die richtigen Anmeldeinformationen verwendet werden und das Konto aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="81ef8-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="81ef8-161">während des Workflows aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="81ef8-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="81ef8-162">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="81ef8-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="81ef8-163">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsLocationPolicy Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="81ef8-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="81ef8-164">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="81ef8-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="81ef8-165">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="81ef8-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="81ef8-166">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="81ef8-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="81ef8-167">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="81ef8-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="81ef8-168">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="81ef8-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


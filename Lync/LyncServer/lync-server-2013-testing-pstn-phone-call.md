---
title: 'Lync Server 2013: Testen des PSTN-Telefonanrufs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4092f728cc691ab73432d7ca853f6441728b5713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="61768-102">Testen des PSTN-Anrufs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61768-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61768-103">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="61768-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61768-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="61768-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="61768-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="61768-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61768-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="61768-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="61768-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61768-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61768-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="61768-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="61768-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="61768-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="61768-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsRegistration verfügt.</span><span class="sxs-lookup"><span data-stu-id="61768-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="61768-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="61768-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="61768-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61768-112">Description</span></span>

<span data-ttu-id="61768-113">Das Cmdlet Test-CsPstnOutboundCall testet, ob ein Benutzer einen Anruf bei einer Telefonnummer im PSTN tätigen kann.</span><span class="sxs-lookup"><span data-stu-id="61768-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="61768-114">Wenn Sie Test-CsPstnOutboundCall ausführen, versucht das Cmdlet zunächst, den Testbenutzer bei lync Server zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="61768-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="61768-115">Wenn die Anmeldung erfolgreich verläuft, versucht das Cmdlet dann, einen Anruf über das PSTN-Gateway zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="61768-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="61768-116">Dieser Anruf erfolgt mithilfe des Wählplans, der VoIP-Richtlinie und anderer Richtlinien und Einstellungen, die dem Testkonto zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="61768-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="61768-117">Wenn der Anruf angenommen wird, sendet das Cmdlet DTMF-Codes (Dual-Tone Multi-Frequency) über das Netzwerk, um die Medien Konnektivität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="61768-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="61768-118">Im Rahmen der Tests wird mit Test-CsPstnOutboundCall ein tatsächlicher Telefonanruf durchgeführt: Das angerufene Telefon klingelt, und der Anruf muss für einen erfolgreichen Abschluss des Tests entgegengenommen werden.</span><span class="sxs-lookup"><span data-stu-id="61768-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="61768-119">Dieser Anruf muss zudem manuell vom Administrator beendet werden.</span><span class="sxs-lookup"><span data-stu-id="61768-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="61768-120">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="61768-120">Running the test</span></span>

<span data-ttu-id="61768-121">Das Cmdlet Test-CsPstnOutboundCall kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="61768-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="61768-122">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet wird, und die PSTN-Telefonnummer, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="61768-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="61768-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="61768-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="61768-124">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="61768-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="61768-125">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsPstnOutboundCall aufrufen:</span><span class="sxs-lookup"><span data-stu-id="61768-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="61768-126">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="61768-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="61768-127">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="61768-127">Determining success or failure</span></span>

<span data-ttu-id="61768-128">Wenn der angegebene Benutzer den Anruf tätigen kann und der Anruf angenommen wird, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als "Success" markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="61768-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="61768-129">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="61768-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="61768-130">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="61768-130">Result : Success</span></span>

<span data-ttu-id="61768-131">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="61768-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="61768-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="61768-132">Error :</span></span>

<span data-ttu-id="61768-133">Diagnose</span><span class="sxs-lookup"><span data-stu-id="61768-133">Diagnosis :</span></span>

<span data-ttu-id="61768-134">Wenn der angegebene Benutzer den Anruf nicht tätigen kann oder wenn der Anruf nicht beantwortet wird, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="61768-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="61768-135">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="61768-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="61768-136">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="61768-136">Result : Failure</span></span>

<span data-ttu-id="61768-137">Wartezeit: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="61768-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="61768-138">Fehler: 403, unzulässig</span><span class="sxs-lookup"><span data-stu-id="61768-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="61768-139">Diagnose: errorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="61768-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="61768-140">Richtlinie enthält keine Telefonrouten Nutzung</span><span class="sxs-lookup"><span data-stu-id="61768-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="61768-141">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie keine Telefonnutzung enthält.</span><span class="sxs-lookup"><span data-stu-id="61768-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="61768-142">(Telefonverwendungen binden VoIP-Richtlinien an VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="61768-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="61768-143">Ohne sowohl eine VoIP-Richtlinie als auch eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN tätigen.)</span><span class="sxs-lookup"><span data-stu-id="61768-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="61768-144">Wenn "Test-CsPstnOutboundCall" fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, einschließlich des Verbose-Parameters:</span><span class="sxs-lookup"><span data-stu-id="61768-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="61768-145">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnOutboundCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als er die Fähigkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="61768-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="61768-146">Diese Ausgabe gibt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:</span><span class="sxs-lookup"><span data-stu-id="61768-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="61768-147">Einrichten eines Audiovideo-Anrufs zu "SIP: + 12065551219@litwareinc. com; User = Phone".</span><span class="sxs-lookup"><span data-stu-id="61768-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="61768-148">Eine Ausnahme "A 404 (nicht gefunden) Antwort wurde aus dem Netzwerk empfangen und der Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="61768-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="61768-149">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="61768-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="61768-150">Im folgenden werden einige häufige Gründe aufgeführt, warum das Testen von CsPstnOutboundCall möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="61768-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="61768-151">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="61768-151">You specified an invalid user account.</span></span> <span data-ttu-id="61768-152">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="61768-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="61768-153">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="61768-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="61768-154">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="61768-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="61768-155">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="61768-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="61768-156">Die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie hat keine gültige PSTN-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="61768-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="61768-157">Sie können die VoIP-Richtlinie bestimmen, die einem Benutzer zugewiesen ist, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="61768-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="61768-158">Anschließend können Sie die PSTN-Verwendungen (falls vorhanden) bestimmen, die dieser Richtlinie zugewiesen sind, indem Sie einen Befehl wie den folgenden verwenden, der Informationen zur benutzerbezogenen VoIP-"redmondvoicepolicy" abruft:</span><span class="sxs-lookup"><span data-stu-id="61768-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>


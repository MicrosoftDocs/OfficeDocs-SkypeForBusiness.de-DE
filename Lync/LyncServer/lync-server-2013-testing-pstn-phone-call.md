---
title: 'Lync Server 2013: Testen des PSTN-Telefonanrufs'
description: 'Lync Server 2013: Testen des PSTN-Anrufs.'
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
ms.openlocfilehash: b42ea6dd46145961a34386d704f8f44e9b7909ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547401"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="99d2f-103">Testen des PSTN-Anrufs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99d2f-103">Testing PSTN phone call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d2f-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="99d2f-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99d2f-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="99d2f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="99d2f-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="99d2f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99d2f-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="99d2f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="99d2f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99d2f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99d2f-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="99d2f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="99d2f-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="99d2f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="99d2f-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsRegistration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="99d2f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="99d2f-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="99d2f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="99d2f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99d2f-113">Description</span></span>

<span data-ttu-id="99d2f-114">Das Test-CsPstnOutboundCall-Cmdlet testet, ob ein Benutzer einen Anruf bei einer Telefonnummer im PSTN tätigen kann.</span><span class="sxs-lookup"><span data-stu-id="99d2f-114">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="99d2f-115">Wenn Sie Test-CsPstnOutboundCall ausführen, versucht das Cmdlet zunächst, den Testbenutzer bei lync Server zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="99d2f-115">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="99d2f-116">Wenn die Anmeldung erfolgreich verläuft, versucht das Cmdlet dann, einen Anruf über das PSTN-Gateway zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="99d2f-116">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="99d2f-117">Dieser Anruf erfolgt mithilfe des Wählplans, der VoIP-Richtlinie und anderer Richtlinien und Einstellungen, die dem Testkonto zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="99d2f-117">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="99d2f-118">Wenn der Anruf angenommen wird, sendet das Cmdlet DTMF-Codes (Dual-Tone Multi-Frequency) über das Netzwerk, um die Medien Konnektivität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="99d2f-118">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="99d2f-119">Im Rahmen der Tests wird mit Test-CsPstnOutboundCall ein tatsächlicher Telefonanruf durchgeführt: Das angerufene Telefon klingelt, und der Anruf muss für einen erfolgreichen Abschluss des Tests entgegengenommen werden.</span><span class="sxs-lookup"><span data-stu-id="99d2f-119">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="99d2f-120">Dieser Anruf muss zudem manuell vom Administrator beendet werden.</span><span class="sxs-lookup"><span data-stu-id="99d2f-120">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="99d2f-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="99d2f-121">Running the test</span></span>

<span data-ttu-id="99d2f-122">Das Test-CsPstnOutboundCall-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="99d2f-122">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="99d2f-123">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet wird, und die PSTN-Telefonnummer, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="99d2f-123">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="99d2f-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="99d2f-124">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="99d2f-125">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="99d2f-125">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="99d2f-126">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsPstnOutboundCall aufrufen:</span><span class="sxs-lookup"><span data-stu-id="99d2f-126">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="99d2f-127">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .</span><span class="sxs-lookup"><span data-stu-id="99d2f-127">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="99d2f-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="99d2f-128">Determining success or failure</span></span>

<span data-ttu-id="99d2f-129">Wenn der angegebene Benutzer den Anruf tätigen kann und der Anruf angenommen wird, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als "Success" markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="99d2f-129">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="99d2f-130">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="99d2f-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="99d2f-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="99d2f-131">Result : Success</span></span>

<span data-ttu-id="99d2f-132">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="99d2f-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="99d2f-133">Fehler</span><span class="sxs-lookup"><span data-stu-id="99d2f-133">Error :</span></span>

<span data-ttu-id="99d2f-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="99d2f-134">Diagnosis :</span></span>

<span data-ttu-id="99d2f-135">Wenn der angegebene Benutzer den Anruf nicht tätigen kann oder wenn der Anruf nicht beantwortet wird, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="99d2f-135">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="99d2f-136">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="99d2f-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="99d2f-137">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="99d2f-137">Result : Failure</span></span>

<span data-ttu-id="99d2f-138">Wartezeit: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="99d2f-138">Latency : 00:00:0987365</span></span>

<span data-ttu-id="99d2f-139">Fehler: 403, unzulässig</span><span class="sxs-lookup"><span data-stu-id="99d2f-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="99d2f-140">Diagnose: errorCode = 12001, Source = ATL-CS-001. litwareinc. com, Reason = User</span><span class="sxs-lookup"><span data-stu-id="99d2f-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="99d2f-141">Richtlinie enthält keine Telefonrouten Nutzung</span><span class="sxs-lookup"><span data-stu-id="99d2f-141">Policy does not contain phone route usage</span></span>

<span data-ttu-id="99d2f-142">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie keine Telefonnutzung enthält.</span><span class="sxs-lookup"><span data-stu-id="99d2f-142">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="99d2f-143">(Telefonverwendungen binden VoIP-Richtlinien an VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="99d2f-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="99d2f-144">Ohne sowohl eine VoIP-Richtlinie als auch eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN tätigen.)</span><span class="sxs-lookup"><span data-stu-id="99d2f-144">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="99d2f-145">Wenn Test-CsPstnOutboundCall fehlschlägt, möchten Sie den Test möglicherweise erneut ausführen, und zwar mit dem Verbose-Parameter:</span><span class="sxs-lookup"><span data-stu-id="99d2f-145">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="99d2f-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnOutboundCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="99d2f-146">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="99d2f-147">Diese Ausgabe gibt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:</span><span class="sxs-lookup"><span data-stu-id="99d2f-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="99d2f-148">Einrichten eines Audiovideo-Anrufs zu "SIP: + 12065551219@litwareinc. com; User = Phone".</span><span class="sxs-lookup"><span data-stu-id="99d2f-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="99d2f-149">Eine Ausnahme "A 404 (nicht gefunden) Antwort wurde aus dem Netzwerk empfangen und der Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="99d2f-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="99d2f-150">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="99d2f-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="99d2f-151">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsPstnOutboundCall Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="99d2f-151">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="99d2f-152">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="99d2f-152">You specified an invalid user account.</span></span> <span data-ttu-id="99d2f-153">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="99d2f-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="99d2f-154">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="99d2f-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="99d2f-155">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="99d2f-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="99d2f-156">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="99d2f-156">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="99d2f-157">Die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie hat keine gültige PSTN-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="99d2f-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="99d2f-158">Sie können die VoIP-Richtlinie bestimmen, die einem Benutzer zugewiesen ist, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="99d2f-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="99d2f-159">Anschließend können Sie die PSTN-Verwendungen (falls vorhanden) bestimmen, die dieser Richtlinie zugewiesen sind, indem Sie einen Befehl wie den folgenden verwenden, der Informationen zur benutzerbezogenen VoIP-"redmondvoicepolicy" abruft:</span><span class="sxs-lookup"><span data-stu-id="99d2f-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>


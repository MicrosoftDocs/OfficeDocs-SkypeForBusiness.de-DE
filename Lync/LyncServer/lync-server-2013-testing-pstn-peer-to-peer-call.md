---
title: 'Lync Server 2013: Testen des PSTN-Peer-to-Peer-Anrufs'
description: 'Lync Server 2013: Testen des PSTN-Peer-to-Peer-Anrufs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf8726c46374e3a799b986e071566d0ae1de138
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552681"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="967b8-103">Testen des PSTN-Peer-to-Peer-Anrufs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="967b8-103">Testing PSTN peer to peer call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="967b8-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="967b8-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="967b8-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="967b8-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="967b8-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="967b8-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967b8-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="967b8-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="967b8-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="967b8-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="967b8-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="967b8-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="967b8-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="967b8-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="967b8-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPstnPeerToPeerCall-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="967b8-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="967b8-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="967b8-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="967b8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="967b8-113">Description</span></span>

<span data-ttu-id="967b8-114">Das Test-CsPstnPeerToPeerCall-Cmdlet überprüft, ob ein Benutzer paar über das PSTN-Gateway (Public Switched Telephone Network) einen Peer-to-Peer-Anruf durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="967b8-114">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="967b8-115">Wenn Sie Test-CsPstnPeerToPeerCall aufrufen, versucht das Cmdlet zunächst, sich bei zwei Test Benutzern anzumelden, um lync Server.</span><span class="sxs-lookup"><span data-stu-id="967b8-115">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="967b8-116">Unter der Voraussetzung, dass die Anmeldungen erfolgreich sind, wird das Cmdlet dann den Benutzer 1 versuchen, Benutzer 2 über das PSTN-Gateway aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="967b8-116">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="967b8-117">In Test-CsPstnPeerToPeerCall wird dieser Aufruf mithilfe des Wählplans, der VoIP-Richtlinie und anderer Richtlinien-und Konfigurationseinstellungen durchführen, die dem Testbenutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="967b8-117">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="967b8-118">Wenn der Test wie geplant verläuft, überprüft das Cmdlet, dass Benutzer 2 den Anruf annehmen konnte, und meldet sich dann beide Testkonten vom System ab.</span><span class="sxs-lookup"><span data-stu-id="967b8-118">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="967b8-119">Test-CsPstnPeerToPeerCall führt einen tatsächlichen Telefonanruf aus, der überprüft, ob eine Verbindung hergestellt werden kann und der auch DTMF-Codes über das Netzwerk sendet, um festzustellen, ob Medien über die Verbindung gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="967b8-119">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="967b8-120">Der Anruf wird vom Cmdlet selbst beantwortet, und es ist keine manuelle Beendigung des Anrufs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="967b8-120">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="967b8-121">(Das heißt, niemand muss Antworten und dann das Telefon aufhängen, das aufgerufen wurde.)</span><span class="sxs-lookup"><span data-stu-id="967b8-121">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="967b8-122">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="967b8-122">Running the test</span></span>

<span data-ttu-id="967b8-123">Das Test-CsPstnPeerToPeerCall-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder den Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="967b8-123">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="967b8-124">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="967b8-124">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="967b8-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="967b8-125">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="967b8-126">Um diese Überprüfung mit tatsächlichen Benutzerkonten auszuführen, müssen Sie zwei Windows PowerShell Credentials-Objekte (Objekte, die den Kontonamen und das Kennwort enthalten) für jedes Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="967b8-126">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="967b8-127">Sie müssen dann diese Credentials-Objekte und die SIP-Adressen der beiden Konten einschließen, wenn Sie Test-CsPstnPeerToPeerCall aufrufen:</span><span class="sxs-lookup"><span data-stu-id="967b8-127">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="967b8-128">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="967b8-128">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="967b8-129">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="967b8-129">Determining success or failure</span></span>

<span data-ttu-id="967b8-130">Wenn die angegebenen Benutzer einen Peer-to-Peer-Anruf ausführen können, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="967b8-130">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="967b8-131">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="967b8-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="967b8-132">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="967b8-132">Result : Success</span></span>

<span data-ttu-id="967b8-133">Wartezeit: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="967b8-133">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="967b8-134">Fehler</span><span class="sxs-lookup"><span data-stu-id="967b8-134">Error :</span></span>

<span data-ttu-id="967b8-135">Diagnose</span><span class="sxs-lookup"><span data-stu-id="967b8-135">Diagnosis :</span></span>

<span data-ttu-id="967b8-136">Wenn die angegebenen Benutzer einen Peer-to-Peer-Anruf nicht abschließen können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="967b8-136">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="967b8-137">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="967b8-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="967b8-138">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="967b8-138">Result : Failure</span></span>

<span data-ttu-id="967b8-139">Wartezeit: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="967b8-139">Latency : 00:00:0182361</span></span>

<span data-ttu-id="967b8-140">Fehler: 403, unzulässig</span><span class="sxs-lookup"><span data-stu-id="967b8-140">Error : 403, Forbidden</span></span>

<span data-ttu-id="967b8-141">Diagnose: errorCode = 12001, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="967b8-141">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="967b8-142">Reason = Benutzerrichtlinie enthält keine Telefonrouten Nutzung</span><span class="sxs-lookup"><span data-stu-id="967b8-142">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="967b8-143">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die VoIP-Richtlinie, die mindestens einem der angegebenen Benutzer zugewiesen ist, keine Telefonnutzung enthält.</span><span class="sxs-lookup"><span data-stu-id="967b8-143">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="967b8-144">(Telefonverwendungen binden VoIP-Richtlinien an VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="967b8-144">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="967b8-145">Ohne sowohl eine VoIP-Richtlinie als auch eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN tätigen.)</span><span class="sxs-lookup"><span data-stu-id="967b8-145">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="967b8-146">Wenn Test-CsPstnPeerToPeerCall fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, dieses Mal einschließlich des Parameters verbose:</span><span class="sxs-lookup"><span data-stu-id="967b8-146">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="967b8-147">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnPeerToPeerCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="967b8-147">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="967b8-148">Diese Ausgabe gibt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:</span><span class="sxs-lookup"><span data-stu-id="967b8-148">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="967b8-149">Einrichten eines Audiovideo-Anrufs zu "SIP: + 12065551219@litwareinc. com; User = Phone".</span><span class="sxs-lookup"><span data-stu-id="967b8-149">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="967b8-150">Eine Ausnahme "A 404 (nicht gefunden) Antwort wurde aus dem Netzwerk empfangen und der Vorgang ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="967b8-150">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="967b8-151">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="967b8-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="967b8-152">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsPstnPeerToPeerCall Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="967b8-152">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="967b8-153">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="967b8-153">You specified a user account that is not valid.</span></span> <span data-ttu-id="967b8-154">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="967b8-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="967b8-155">Das Benutzerkonto ist gültig, aber das Konto ist derzeit nicht für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="967b8-155">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="967b8-156">Um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist, führen Sie einen Befehl wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="967b8-156">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="967b8-157">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer derzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="967b8-157">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="967b8-158">Die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie hat keine gültige PSTN-Verwendung.</span><span class="sxs-lookup"><span data-stu-id="967b8-158">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="967b8-159">Sie können die VoIP-Richtlinie bestimmen, die einem Benutzer zugewiesen ist, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="967b8-159">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="967b8-160">Anschließend können Sie die PSTN-Verwendungen (falls vorhanden) bestimmen, die dieser Richtlinie zugewiesen sind, indem Sie einen Befehl wie den folgenden verwenden, der Informationen zur benutzerbezogenen VoIP-"redmondvoicepolicy" abruft:</span><span class="sxs-lookup"><span data-stu-id="967b8-160">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>


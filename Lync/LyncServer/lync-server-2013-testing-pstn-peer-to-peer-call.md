---
title: 'Lync Server 2013: Testen des PSTN-Peer-to-Peer-Anrufs'
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
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="1b2ab-102">Testen des PSTN-Peer-to-Peer-Anrufs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b2ab-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b2ab-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1b2ab-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b2ab-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="1b2ab-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1b2ab-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="1b2ab-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b2ab-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="1b2ab-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1b2ab-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b2ab-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b2ab-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1b2ab-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1b2ab-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1b2ab-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsPstnPeerToPeerCall-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="1b2ab-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1b2ab-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b2ab-112">Description</span></span>

<span data-ttu-id="1b2ab-113">Das Cmdlet Test-CsPstnPeerToPeerCall überprüft, ob ein paar von Benutzern einen Peer-to-Peer-Anruf über das PSTN-Gateway (Public Switched Telephone Network) durchführen muss.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="1b2ab-114">Wenn Sie Test-CsPstnPeerToPeerCall aufrufen, versucht das Cmdlet zunächst, sich bei zwei Test Benutzern mit lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="1b2ab-115">Unter der Voraussetzung, dass die Anmeldungen erfolgreich sind, wird das Cmdlet dann vom Benutzer 1 versuchen, Benutzer 2 über das PSTN-Gateway anzurufen.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="1b2ab-116">In Test-CsPstnPeerToPeerCall wird dieser Anruf unter Verwendung des Wählplans, der VoIP-Richtlinie und anderer Richtlinien-und Konfigurationseinstellungen durchführen, die dem Testbenutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="1b2ab-117">Wenn der Test planmäßig verläuft, überprüft das Cmdlet, ob Benutzer 2 den Anruf annehmen konnte, und melden Sie sich dann beide Testkonten vom System ab.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="1b2ab-118">Test-CsPstnPeerToPeerCall führt einen tatsächlichen Telefonanruf durch, der überprüft, ob eine Verbindung hergestellt werden kann, und der auch DTMF-Codes über das Netzwerk überträgt, um festzustellen, ob Medien über die Verbindung gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="1b2ab-119">Der Anruf wird vom Cmdlet selbst beantwortet, und es ist keine manuelle Kündigung des Anrufs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="1b2ab-120">(Das heißt, niemand muss Antworten und dann das angerufene Telefon auflegen.)</span><span class="sxs-lookup"><span data-stu-id="1b2ab-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1b2ab-121">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="1b2ab-121">Running the test</span></span>

<span data-ttu-id="1b2ab-122">Das Cmdlet "Test-CsPstnPeerToPeerCall" kann mit einem Paar vorkonfigurierter Testkonten ausgeführt werden (siehe Einrichten von Testkonten zum Ausführen von lync Server-Tests) oder der Konten von zwei Benutzern, die für lync Server aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="1b2ab-123">Um diese Prüfung mit Testkonten auszuführen, müssen Sie lediglich den FQDN des zu testenden lync-Server Pools angeben.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="1b2ab-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="1b2ab-125">Damit diese Überprüfung mit tatsächlichen Benutzerkonten ausgeführt werden kann, müssen Sie für jedes Konto zwei Windows PowerShell-Anmeldeinformationsobjekte (Objekte, die den Kontonamen und das Kennwort enthalten) erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="1b2ab-126">Sie müssen dann diese Anmeldeinformationsobjekte und die SIP-Adressen der beiden Konten einbeziehen, wenn Sie Test-CsPstnPeerToPeerCall aufrufen:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="1b2ab-127">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .</span><span class="sxs-lookup"><span data-stu-id="1b2ab-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1b2ab-128">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="1b2ab-128">Determining success or failure</span></span>

<span data-ttu-id="1b2ab-129">Wenn die angegebenen Benutzer einen Peer-zu-Peer-Anruf abschließen können, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="1b2ab-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1b2ab-130">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1b2ab-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1b2ab-131">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="1b2ab-131">Result : Success</span></span>

<span data-ttu-id="1b2ab-132">Latenz: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="1b2ab-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="1b2ab-133">Fehler</span><span class="sxs-lookup"><span data-stu-id="1b2ab-133">Error :</span></span>

<span data-ttu-id="1b2ab-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="1b2ab-134">Diagnosis :</span></span>

<span data-ttu-id="1b2ab-135">Wenn die angegebenen Benutzer keinen Peer-to-Peer-Anruf abschließen können, wird das Ergebnis als Fehler angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1b2ab-136">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1b2ab-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1b2ab-137">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="1b2ab-137">Result : Failure</span></span>

<span data-ttu-id="1b2ab-138">Latenz: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="1b2ab-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="1b2ab-139">Fehler: 403, unzulässig</span><span class="sxs-lookup"><span data-stu-id="1b2ab-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="1b2ab-140">Diagnose: errorCode = 12001, Source = ATL-CS-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="1b2ab-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="1b2ab-141">Reason = Benutzerrichtlinie enthält keine Nutzung der Telefonroute</span><span class="sxs-lookup"><span data-stu-id="1b2ab-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="1b2ab-142">In der vorherigen Ausgabe wird angegeben, dass der Test fehlgeschlagen ist, da die VoIP-Richtlinie, die mindestens einem der angegebenen Benutzer zugewiesen ist, keine Telefonnutzung umfasst.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="1b2ab-143">(Telefon-Nutzungen binden VoIP-Richtlinien an VoIP-Routen.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="1b2ab-144">Ohne eine VoIP-Richtlinie und eine entsprechende VoIP-Route können Sie keine Anrufe über das PSTN führen.)</span><span class="sxs-lookup"><span data-stu-id="1b2ab-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="1b2ab-145">Wenn Test-CsPstnPeerToPeerCall fehlschlägt, möchten Sie möglicherweise den Test erneut ausführen, wobei dieser Zeitpunkt einschließlich des Verbose-Parameters lautet:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="1b2ab-146">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsPstnPeerToPeerCall eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers zur Anmeldung bei lync Server überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="1b2ab-147">Diese Ausgabe zeigt beispielsweise an, dass Netzwerkprobleme eine Verbindung mit dem PSTN verhindern:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="1b2ab-148">Einrichten eines Audio-Video Anrufs zu "SIP: + 12065551219@litwareinc. com; Benutzer = Telefon".</span><span class="sxs-lookup"><span data-stu-id="1b2ab-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="1b2ab-149">Eine Ausnahme "eine 404-Antwort (nicht gefunden)" wurde vom Netzwerk empfangen, und der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1b2ab-150">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="1b2ab-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="1b2ab-151">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsPstnPeerToPeerCall möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="1b2ab-152">Sie haben ein ungültiges Benutzerkonto angegeben.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="1b2ab-153">Sie können überprüfen, ob ein Benutzerkonto vorhanden ist, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1b2ab-154">Das Benutzerkonto ist gültig, das Konto ist derzeit aber für lync Server nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="1b2ab-155">Führen Sie einen Befehl ähnlich der folgenden aus, um zu überprüfen, ob ein Benutzerkonto für lync Server aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="1b2ab-156">Wenn die Enabled-Eigenschaft auf false festgelegt ist, bedeutet dies, dass der Benutzer zurzeit nicht für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="1b2ab-157">Die dem angegebenen Benutzer zugewiesene VoIP-Richtlinie hat keine gültige PSTN-Nutzung.</span><span class="sxs-lookup"><span data-stu-id="1b2ab-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="1b2ab-158">Sie können die VoIP-Richtlinie ermitteln, die einem Benutzer zugewiesen ist, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="1b2ab-159">Und dann können Sie die PSTN-Nutzungen (sofern vorhanden) ermitteln, die dieser Richtlinie zugewiesen sind, indem Sie einen Befehl ähnlich der folgenden verwenden, der Informationen zur pro-Benutzer-VoIP-Richtlinien RedmondVoicePolicy abruft:</span><span class="sxs-lookup"><span data-stu-id="1b2ab-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen des beständigen Chats'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1980d66649ff465ad251d5b95a9642e5bcd43c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504072"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="17244-102">Testen des beständigen Chats in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17244-102">Testing persistent chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17244-103">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="17244-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17244-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="17244-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="17244-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="17244-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17244-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="17244-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="17244-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17244-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17244-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="17244-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="17244-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="17244-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="17244-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-cspersistentchatmessage "</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="17244-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="17244-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="17244-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="17244-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17244-112">Description</span></span>

<span data-ttu-id="17244-113">Das Cmdlet **Test-cspersistentchatmessage "** überprüft, ob ein paar Testbenutzer Nachrichten mithilfe des Diensts für beständigen Chat austauschen können.</span><span class="sxs-lookup"><span data-stu-id="17244-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="17244-114">Hierzu protokolliert das Cmdlet die beiden Benutzer in lync Server 2013, verbindet die Benutzer mit einem beständigen Chatroom, tauscht ein Nachrichtenpaar aus, verlässt dann den Chatroom und meldet die beiden Benutzer ab.</span><span class="sxs-lookup"><span data-stu-id="17244-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="17244-115">Beachten Sie, dass Aufrufe dieses Cmdlets fehlschlagen, wenn Sie keine Chatrooms erstellt haben oder wenn den beiden Testbenutzerkonten keine Richtlinie für beständigen Chat zugewiesen ist, die Ihnen Zugriff auf den Dienst für beständigen Chat gewährt.</span><span class="sxs-lookup"><span data-stu-id="17244-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="17244-116">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="17244-116">Running the test</span></span>

<span data-ttu-id="17244-117">Die im folgenden Beispiel gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (litwareinc \\ Pilar und litwareinc \\ kenmyer), sich bei lync Server 2013 anzumelden und dann Nachrichten mit dem Dienst für beständigen Chat auszutauschen.</span><span class="sxs-lookup"><span data-stu-id="17244-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="17244-118">Dazu wird im ersten Befehl des Beispiels das Cmdlet **Get-Credential** verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="17244-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="17244-119">(Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, erfordert das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator, das Kennwort für das Pilar Ackerman-Konto einzugeben.) Das resultierende Credentials-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="17244-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="17244-120">Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.</span><span class="sxs-lookup"><span data-stu-id="17244-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="17244-121">Wenn die Credential-Objekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und Nachrichten mithilfe des beständigen Chats austauschen können.</span><span class="sxs-lookup"><span data-stu-id="17244-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="17244-122">Um diese Aufgabe auszuführen, wird das Cmdlet **Test-cspersistentchatmessage "** mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); "Sendersipaddress" (die SIP-Adresse für den ersten Testbenutzer); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); "Receiversipaddress" (die SIP-Adresse für den anderen Testbenutzer); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).</span><span class="sxs-lookup"><span data-stu-id="17244-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="17244-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="17244-123">Determining success or failure</span></span>

<span data-ttu-id="17244-124">Wenn der angegebene Benutzer über eine gültige Standortrichtlinie verfügt, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="17244-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="17244-125">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="17244-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="17244-126">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="17244-126">Result : Success</span></span>

<span data-ttu-id="17244-127">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="17244-127">Latency : 00:00:00</span></span>

<span data-ttu-id="17244-128">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="17244-128">Error Message :</span></span>

<span data-ttu-id="17244-129">Diagnose</span><span class="sxs-lookup"><span data-stu-id="17244-129">Diagnosis :</span></span>

<span data-ttu-id="17244-130">Wenn die angegebenen Benutzer Nachrichten nicht mit dem Dienst für beständigen Chat austauschen können, wird das Ergebnis als **Fehler**angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="17244-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="17244-131">Warnung: Fehler beim Lesen der Registrierungs Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="17244-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="17244-132">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="17244-132">domain name (FQDN).</span></span> <span data-ttu-id="17244-133">Verwenden der standardmäßigen Registrierungsstellen-Portnummer.</span><span class="sxs-lookup"><span data-stu-id="17244-133">Using default Registrar port number.</span></span> <span data-ttu-id="17244-134">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="17244-134">Exception:</span></span>

<span data-ttu-id="17244-135">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="17244-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="17244-136">auf</span><span class="sxs-lookup"><span data-stu-id="17244-136">at</span></span>

<span data-ttu-id="17244-137">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="17244-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="17244-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="17244-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="17244-139">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="17244-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="17244-140">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="17244-140">Result : Failure</span></span>

<span data-ttu-id="17244-141">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="17244-141">Latency : 00:00:00</span></span>

<span data-ttu-id="17244-142">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="17244-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="17244-143">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="17244-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="17244-144">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="17244-144">established connection failed because connected host has</span></span>

<span data-ttu-id="17244-145">Fehler bei der Antwort \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="17244-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="17244-146">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="17244-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="17244-147">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="17244-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="17244-148">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="17244-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="17244-149">Fehler beim Antworten</span><span class="sxs-lookup"><span data-stu-id="17244-149">has failed to respond</span></span>

<span data-ttu-id="17244-150">\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944 \] : 5061</span><span class="sxs-lookup"><span data-stu-id="17244-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="17244-151">Diagnose</span><span class="sxs-lookup"><span data-stu-id="17244-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="17244-152">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="17244-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="17244-153">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von cspersistentchatmessage "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="17244-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="17244-154">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="17244-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="17244-155">Die erforderlichen Testkonten sind möglicherweise nicht vorhanden oder wurden ordnungsgemäß erstellt.</span><span class="sxs-lookup"><span data-stu-id="17244-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="17244-156">Möglicherweise wurde ein Netzwerkproblem verursacht eine unerwartete Verzögerung, die den Test Zeitüberschreitung.</span><span class="sxs-lookup"><span data-stu-id="17244-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17244-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17244-157">See Also</span></span>


[<span data-ttu-id="17244-158">Grant-cspersistentchatpolicy "</span><span class="sxs-lookup"><span data-stu-id="17244-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="17244-159">New-cspersistentchatpolicy "</span><span class="sxs-lookup"><span data-stu-id="17244-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="17244-160">Gruppe-cspersistentchatpolicy "</span><span class="sxs-lookup"><span data-stu-id="17244-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


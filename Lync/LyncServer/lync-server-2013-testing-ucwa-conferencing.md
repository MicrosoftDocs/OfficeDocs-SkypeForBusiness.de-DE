---
title: 'Lync Server 2013: Testen von UCWA-Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="c3921-102">Testen von UCWA-Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3921-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3921-103">_**Letztes Änderungsdatum des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c3921-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3921-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="c3921-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c3921-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="c3921-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3921-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="c3921-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c3921-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3921-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3921-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c3921-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c3921-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="c3921-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c3921-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsUcwaConference-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="c3921-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="c3921-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="c3921-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c3921-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3921-112">Description</span></span>

<span data-ttu-id="c3921-113">Das Cmdlet **Test-CsUcwaConference** überprüft, ob ein paar Testbenutzer mithilfe der Unified Communications Web-API (UCWA) eine Onlinekonferenz planen, daran teilnehmen und dann eine Onlinekonferenz durchführen können.</span><span class="sxs-lookup"><span data-stu-id="c3921-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c3921-114">Dazu verwendet das Cmdlet den lync Server Web Ticket-Dienst, um die beiden Testbenutzer zu authentifizieren und bei lync Server zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c3921-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="c3921-115">Das Cmdlet startet dann eine Konferenz mit den Anmeldeinformationen des Organisators und fordert den Teilnehmer auf, an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c3921-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="c3921-116">Nachdem die Besprechung beigetreten ist, überprüft das Cmdlet " **Test-CsUcwaConference** ", ob die Benutzer die folgenden Aktionen ausführen können: Exchange-Sofortnachrichten und leiten von Pools, trennt die Konferenz und hebt die Registrierung der beiden Testbenutzer auf.</span><span class="sxs-lookup"><span data-stu-id="c3921-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="c3921-117">Die geplante Konferenz wird auch nach Abschluss des Tests gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c3921-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="c3921-118">Das Cmdlet **Test-CsUcwaConference** kann auch verwendet werden, um zu ermitteln, ob anonyme Benutzer an Online Konferenzen teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="c3921-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="c3921-119">Beachten Sie, dass das Cmdlet **Test-CsUcwaConference** nicht für einen Microsoft lync Server 2010-Pool ausgeführt werden sollte, es sei denn, UCWA wurde in diesem Pool installiert.</span><span class="sxs-lookup"><span data-stu-id="c3921-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="c3921-120">Wenn UCWA nicht installiert wurde, tritt beim Aufruf des **Test-CsUcwaConference-** Cmdlets ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c3921-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c3921-121">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="c3921-121">Running the test</span></span>

<span data-ttu-id="c3921-122">Der in Beispiel 1 gezeigte Befehl überprüft, ob ein paar Testbenutzer an einer UCWA-Konferenz im Pool-ATL-CS-001.litwareinc.com teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="c3921-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c3921-123">Beachten Sie, dass dieser Befehl fehlschlägt, wenn Sie für ATL-CS-001.litwareinc.com keine Konfigurationstest Benutzer für die Integritätsüberwachung vordefiniert haben.</span><span class="sxs-lookup"><span data-stu-id="c3921-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c3921-124">Die in Beispiel 2 gezeigten Befehle testen die Möglichkeit eines Paars von Benutzern\\("litwareinc Pilar\\und" litwareinc kenmyer), an einer UCWA Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c3921-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="c3921-125">Dazu verwendet der erste Befehl im Beispiel das Cmdlet "Get-Credential", um ein Windows PowerShell-Anmeldeinformationsobjekt für die Befehlszeilenschnittstelle zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="c3921-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="c3921-126">(Da der Anmeldename, "litwareinc\\Pilar, als Parameter enthalten war, erfordert das Dialogfeld Windows PowerShell-Anmeldeinformationen nur, dass der Administrator das Kennwort für das Pilar Ackerman-Konto eingegeben hat.) Das resultierende Credentials-Objekt wird dann in einer Variablen mit dem Namen $cred 1 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c3921-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="c3921-127">Der zweite Befehl führt dieselbe Aufgabe aus, wobei dieses Mal ein Anmeldeinformationsobjekt für das Ken Myers-Konto zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c3921-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="c3921-128">Wenn die beiden Anmeldeinformationsobjekte in der Hand sind, bestimmt der dritte Befehl im Beispiel, ob die beiden Benutzer an einer UCWA-Konferenz teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="c3921-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="c3921-129">Zum Ausführen dieser Aufgabe wird das Cmdlet **Test-CsUcwaConference** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (der FQDN des registrierungspools); OrganizerSipAddress (die SIP-Adresse für den Besprechungsorganisator); OrganizerCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für denselben Benutzer enthält); ParticipantSipAddress (die SIP-Adresse des anderen Testbenutzers); und ParticipantCredential (das Windows PowerShell-Befehlszeilen-Schnittstellenobjekt, das die Anmeldeinformationen für den anderen Benutzer enthält).</span><span class="sxs-lookup"><span data-stu-id="c3921-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c3921-130">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="c3921-130">Determining success or failure</span></span>

<span data-ttu-id="c3921-131">Wenn Conferencing richtig konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft Ergebnis als erfolgreich markiert ist **:**</span><span class="sxs-lookup"><span data-stu-id="c3921-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="c3921-132">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3921-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c3921-133">Ziel-URI: https://LyncTest-SE. LyncTest. SelfHost. Corp.</span><span class="sxs-lookup"><span data-stu-id="c3921-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="c3921-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="c3921-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="c3921-135">Ergebnis: Erfolg</span><span class="sxs-lookup"><span data-stu-id="c3921-135">Result : Success</span></span>

<span data-ttu-id="c3921-136">Latenz: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="c3921-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="c3921-137">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="c3921-137">Error Message :</span></span>

<span data-ttu-id="c3921-138">Diagnose</span><span class="sxs-lookup"><span data-stu-id="c3921-138">Diagnosis :</span></span>

<span data-ttu-id="c3921-139">Wenn die angegebenen Benutzer keine Konferenz verwenden können, wird das Ergebnis als **Fehler**angezeigt, und weitere Informationen werden in den Eigenschaften Fehler und Diagnose aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="c3921-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c3921-140">Warnung: Fehler beim Lesen der Registrierungsstellen-Portnummer für die angegebene vollqualifizierte</span><span class="sxs-lookup"><span data-stu-id="c3921-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c3921-141">Domänenname (FQDN).</span><span class="sxs-lookup"><span data-stu-id="c3921-141">domain name (FQDN).</span></span> <span data-ttu-id="c3921-142">Verwenden der standardmäßigen Registrierungs Portnummer</span><span class="sxs-lookup"><span data-stu-id="c3921-142">Using default Registrar port number.</span></span> <span data-ttu-id="c3921-143">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="c3921-143">Exception:</span></span>

<span data-ttu-id="c3921-144">System. InvalidOperationException: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="c3921-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c3921-145">am</span><span class="sxs-lookup"><span data-stu-id="c3921-145">at</span></span>

<span data-ttu-id="c3921-146">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="c3921-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c3921-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c3921-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c3921-148">Test-CsUcwaConference: Es wurde kein Testbenutzer zugewiesen</span><span class="sxs-lookup"><span data-stu-id="c3921-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="c3921-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="c3921-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="c3921-150">Überprüfen Sie die Benutzerkonfiguration testen.</span><span class="sxs-lookup"><span data-stu-id="c3921-150">Verify test user configuration.</span></span>

<span data-ttu-id="c3921-151">Zeile: 1 Zeichen: 1</span><span class="sxs-lookup"><span data-stu-id="c3921-151">At line:1 char:1</span></span>

<span data-ttu-id="c3921-152">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="c3921-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c3921-153">\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="c3921-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="c3921-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="c3921-154">, InvalidOperationException</span></span>

<span data-ttu-id="c3921-155">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. Synth</span><span class="sxs-lookup"><span data-stu-id="c3921-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="c3921-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="c3921-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c3921-157">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="c3921-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="c3921-158">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsUcwaConference** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="c3921-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="c3921-159">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="c3921-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c3921-160">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="c3921-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c3921-161">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c3921-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c3921-162">Die Möglichkeit zum Durchführen einer Konferenz hängt von der konferenzrichtlinie ab, die dem Benutzer zugewiesen wurde, der die Konferenz organisiert hat (im Fall des **Test-CsUcwaConference-** Cmdlets, bei dem es sich um den Absender handelt).</span><span class="sxs-lookup"><span data-stu-id="c3921-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="c3921-163">Wenn es dem Organisator nicht gestattet ist, in seiner Besprechung kollaborative Aktivitäten einzubeziehen (Wenn beispielsweise die EnableDataCollaboration-Eigenschaft der konferenzrichtlinie auf "false" festgelegt ist), schlägt das **Test-CsUcwaConference-** Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="c3921-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="c3921-164">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c3921-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3921-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3921-165">See Also</span></span>


[<span data-ttu-id="c3921-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="c3921-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="c3921-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="c3921-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="c3921-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="c3921-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Testen der Anwendungsfreigabe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11130c1882fd6d12784cf6c25559a4249453f5d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530532"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="55040-102">Testen der Anwendungsfreigabe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55040-102">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55040-103">_**Letztes Änderungsstand des Themas:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="55040-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55040-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="55040-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="55040-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="55040-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55040-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="55040-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="55040-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55040-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55040-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="55040-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="55040-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="55040-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="55040-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsASConference-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="55040-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="55040-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="55040-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="55040-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55040-112">Description</span></span>

<span data-ttu-id="55040-113">Das Cmdlet **Test-csasconference "** überprüft, ob ein Testbenutzer Paar an einer Onlinekonferenz teilnehmen kann, die die Anwendungsfreigabe umfasst.</span><span class="sxs-lookup"><span data-stu-id="55040-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="55040-114">Hierzu registriert das Cmdlet die beiden Benutzer mit lync Server 2013 und verwendet dann eines der Benutzerkonten, um eine neue Konferenz zu erstellen, die die Freigabe von Anwendungen umfasst.</span><span class="sxs-lookup"><span data-stu-id="55040-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="55040-115">Anschließend prüft das Cmdlet, ob der zweite Benutzer dieser Konferenz beitreten kann.</span><span class="sxs-lookup"><span data-stu-id="55040-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="55040-116">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="55040-116">Running the test</span></span>

<span data-ttu-id="55040-p103">Der Befehl in Beispiel 1 prüft, ob in Pool "atl-cs-001.litwareinc.com" eine Konferenz zur Anwendungsfreigabe stattfinden kann. Dieser Befehl setzt voraus, dass Sie ein Testbenutzerpaar für den angegebenen Pool konfiguriert haben. Wenn keine Testbenutzer vorhanden sind, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="55040-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="55040-p104">In Beispiel 2 wird gestestet, ob der Join Launcher Service an einer Konferenz zur Anwendungsfreigabe in Pool "atl-cs-001.litwareinc.com" teilnehmen kann. Mit diesem Befehl wird nur der Dienst getestet, für die Ausführung des Befehls sind keine Mobilgeräte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55040-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="55040-122">Die in Beispiel 2 gezeigten Befehle testen die Fähigkeit eines Benutzer Paares (litwareinc \\ Pilar und litwareinc kenmyer), sich bei \\ lync Server 2013 anzumelden und dann eine Anwendungsfreigabe Konferenz durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="55040-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="55040-123">Dazu wird im ersten Befehl des Beispiels das Get-Credential-Cmdlet verwendet, um ein Windows PowerShell-Befehlszeilen-Schnittstellen Anmeldeinformationsobjekt zu erstellen, das den Namen und das Kennwort des Benutzers Pilar Ackerman enthält.</span><span class="sxs-lookup"><span data-stu-id="55040-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="55040-124">(Da der Anmeldename litwareinc \\ Pilar als Parameter angegeben wurde, muss das Dialogfeld Windows PowerShell Anmeldeinformationen nur den Administrator zum Eingeben des Kennworts für das Pilar Ackerman-Konto angeben.) Das resultierende Credential-Objekt wird dann in einer Variablen mit dem Namen "$cred 1" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="55040-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="55040-125">Der zweite Befehl hat die gleiche Aufgabe, nur gibt dieser ein Objekt mit Anmeldeinformationen für das Konto "Ken Myer" zurück.</span><span class="sxs-lookup"><span data-stu-id="55040-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="55040-126">Wenn die Credential-Objekte in der Hand sind, bestimmt der dritte Befehl, ob sich diese beiden Benutzer bei lync Server 2013 anmelden und eine Anwendungsfreigabe Konferenz durchführen können.</span><span class="sxs-lookup"><span data-stu-id="55040-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="55040-127">Zur Ausführung dieser Aufgabe wird das Cmdlet **Test-csasconference "** zusammen mit den folgenden Parametern aufgerufen: TargetFqdn (FQDN des Registrierungsstellen Pools); "Sendersipaddress" (die SIP-Adresse für den ersten Testbenutzer); SenderCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für diesen Benutzer enthält); "Receiversipaddress" (die SIP-Adresse für den anderen Testbenutzer); und ReceiverCredential (das Windows PowerShell-Objekt, das die Anmeldeinformationen für den anderen Testbenutzer enthält).</span><span class="sxs-lookup"><span data-stu-id="55040-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="55040-128">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="55040-128">Determining success or failure</span></span>

<span data-ttu-id="55040-129">Wenn die Anwendungsfreigabe ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als Success markiert wurde **:**</span><span class="sxs-lookup"><span data-stu-id="55040-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="55040-130">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55040-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="55040-131">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="55040-131">Result : Success</span></span>

<span data-ttu-id="55040-132">Wartezeit: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="55040-132">Latency : 00:00:01</span></span>

<span data-ttu-id="55040-133">Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="55040-133">Error Message :</span></span>

<span data-ttu-id="55040-134">Diagnose</span><span class="sxs-lookup"><span data-stu-id="55040-134">Diagnosis :</span></span>

<span data-ttu-id="55040-135">Wenn die angegebenen Benutzer keine Anwendungen freigeben können, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="55040-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="55040-136">Ziel-FQDN: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55040-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="55040-137">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="55040-137">Result : Failure</span></span>

<span data-ttu-id="55040-138">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55040-138">Latency : 00:00:00</span></span>

<span data-ttu-id="55040-139">Fehlermeldung: 10060, ein Verbindungsversuch ist fehlgeschlagen, da die verbundene Partei</span><span class="sxs-lookup"><span data-stu-id="55040-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="55040-140">nach einem bestimmten Zeitraum nicht ordnungsgemäß reagiert oder</span><span class="sxs-lookup"><span data-stu-id="55040-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="55040-141">Fehler bei hergestellter Verbindung, da der verbundene Host</span><span class="sxs-lookup"><span data-stu-id="55040-141">established connection failed because connected host has</span></span>

<span data-ttu-id="55040-142">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="55040-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="55040-143">Innere Ausnahme: ein Verbindungsversuch ist fehlgeschlagen, da die</span><span class="sxs-lookup"><span data-stu-id="55040-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="55040-144">die verbundene Partei hat nach einer bestimmten Zeit nicht ordnungsgemäß reagiert.</span><span class="sxs-lookup"><span data-stu-id="55040-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="55040-145">Zeit oder Fehler bei hergestellter Verbindung, weil verbundener Host</span><span class="sxs-lookup"><span data-stu-id="55040-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="55040-146">Fehler beim Antworten auf 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="55040-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="55040-147">Diagnose</span><span class="sxs-lookup"><span data-stu-id="55040-147">Diagnosis :</span></span>

<span data-ttu-id="55040-148">Die vorherige Ausgabe enthält beispielsweise den Hinweis "der verbundene Teilnehmer hat nicht ordnungsgemäß reagiert", der in der Regel ein Problem mit dem Edgeserver angibt.</span><span class="sxs-lookup"><span data-stu-id="55040-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="55040-149">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="55040-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="55040-150">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von csasconference "** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="55040-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="55040-151">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="55040-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="55040-152">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="55040-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="55040-153">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="55040-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="55040-154">Dieser Befehl schlägt fehl, wenn dem Testbenutzer eine konferenzrichtlinie zugewiesen wurde, die verhindert, dass die Anwendungsfreigabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55040-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="55040-155">Dieser Befehl schlägt fehl, wenn der Edgeserver falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="55040-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55040-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55040-156">See Also</span></span>


[<span data-ttu-id="55040-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="55040-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="55040-158">Test-csdataconference "</span><span class="sxs-lookup"><span data-stu-id="55040-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

